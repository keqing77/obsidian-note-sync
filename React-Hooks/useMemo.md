`const cachedValue = useMemo(calculateValue, dependencies)`

> 保存返回的结果 就叫做 **缓存**( `memoization`) , 这就是为什么这个 hook 叫做 `useMemo` 


>[!tip] useMemo有以下作用
>1. 跳过昂贵的重新计算   
>2. 跳过组件的重新渲染
>3. 缓存一个函数
>4. 缓存对另一个 hook 的依赖


## useage

使用 memo 通常有三个原因：
1.  ✅ 防止不必要的 effect。
2.  ❗️防止不必要的 re-render。
3.  ❗️防止不必要的重复计算

```js
// 没有使用useMemo, filterTodos函数会在每次 React 组件重新渲染时候重新执行, 尽管结果值没有发生变化, 大多数情况下计算会很快, 但是在昂贵的计算下会造成不必要的性能开销

function TodoList({ todos, tab, theme }) {
  const visibleTodos = filterTodos(todos, tab);
  // ...
}


// 使用 useMemo 包裹, 第一次计算的结果被缓存起来, 第二次渲染时候如果组件没有变化 则跳过这个 filterTodos 函数的执行
import { useMemo } from 'react';

function TodoList({ todos, tab }) {
  const visibleTodos = useMemo(
    () => filterTodos(todos, tab),
    [todos, tab]
  );
  // ...
}

```


## pitfal
不恰当地使用 `useMemo & useCallback` 不但不会提高性能, 反而造成性能下降

正确的阻止 re-render 需要我们明确三个问题：

1.  组件什么时候会 re-render。
2.  如何防止子组件 re-render。
3.  如何判断子组件需要缓存。

#### 组件什么时候会 re-render

三种情况：

1.  当本身的 props 或 state 改变时。
2.  Context value 改变时，使用该值的组件会 re-render。
3.  当父组件重新渲染时，它所有的子组件都会 re-render，形成一条 re-render 链。

第三个 re-render 时机经常被开发者忽视，**导致代码中存在大量的无效缓存**

  
## 无效的 useMemo

```js
const App = () => {
  const [state, setState] = useState(1);

  const onClick = useCallback(() => {
    console.log('Do something on click');
  }, []);

  return (
	// 无论 onClick 是否被缓存，Page 都会 re-render 
    <Page onClick={onClick} />
  );
};

当使用 setState 改变 state 时，App 会 re-render，
作为子组件的 Page 也会跟着 re-render。这里 useCallback 是完全无效的，它并不能阻止 Page 的 re-render。


```


## 防止无效的 re-render
**必须同时缓存 onClick 和组件本身，才能实现 Page 不触发 re-render。**

必须同时满足以下两个条件，子组件才不会 re-render：
1.  子组件自身被缓存。
2.  子组件所有的 prop 都被缓存。

```js
const PageMemoized = React.memo(Page);

const App = () => {
  const [state, setState] = useState(1);

  const onClick = useCallback(() => {
    console.log('Do something on click');
  }, []);

  return (
    // Page 和 onClick 同时 memorize
    <PageMemoized onClick={onClick} />
  );
};

```

## 应该把 useMemo 用在程序里渲染昂贵的组件上，而不是数值计算上。

-   **大部分的 useMemo 和 useCallback 都应该移除**，他们可能没有带来任何性能上的优化，反而增加了程序首次渲染的负担，并增加程序的复杂性。
-   使用 useMemo 和 useCallback 优化子组件 re-render 时，**必须同时满足以下条件才有效**。
    1.  子组件已通过 React.memo 或 useMemo 被缓存
    2.  子组件所有的 prop 都被缓存
-   **不推荐默认给所有组件都使用缓存**，大量组件初始化时被缓存，可能导致过多的内存消耗，并影响程序初始化渲染的速度。

## Q & A 

### 为什么不默认 useMemo

> 有这样的计划, React.forget , 会自动给需要加优化的组件加上 useMemo, 但是似乎失败了

1.  `缓存是有成本的`，小的成本可能会累加过高。
2.  默认缓存无法保证足够的正确性。



参考文献: << 如何正确地使用 useMemo 和 useCallback >>
作者：tumars  
链接：https://juejin.cn/post/7122027852492439565  
来源：稀土掘金  