许多工程师都喜欢在 MacOS 上进行开发工作， 笔者也是如此，所以整理了一下个人觉得好用的软件和设置并分享出来。

## 浏览器
其实这个可以归类到开发相关，但是因为浏览器在日常生活中使用的频率非常之高且内容较多，故单独列举出来， 包括浏览器拓展和油猴脚本等。

### Arc
> 目前已使用半年多，有不少人说我不久会换会 chrome 或者其他，但我并没有，相反我看到很多知名开发者都一直在使用，如 `Anthony fu` ，`Cali` 等，还有几乎清一色的油管教学博主。
> 
> 实际上我几乎都认真尝试过市面上所有浏览器，都是各有所长，但最终留下来的是 Arc。如果你对Chrome 不满意， 也许你该试着尝试 Arc，它不仅能完美替代，还非常 magic ！
> 毫不夸张地说， Arc 是个人觉得目前 Mac 上最好的浏览器，同时也非常期待今年年底推出的 Win 版本 Arc 

如果你连听都没听说过，欢迎阅读我这篇介绍 Arc 的文章：[Arc浏览器 - 备受瞩目又充满想象力的产品 - 掘金](https://juejin.cn/post/7264168916291682341)

![[CleanShot 2023-10-06 at 19.11.15.png]]

### Arc 配置
> Arc 有很多优点， 但不一定适合所有人，特别有些配置还挺别扭的

**记录下个人配置当个备忘录，请忽略😊**

- 关闭 Litter Arc
- 关闭 iCloud 同步
- 设置 Tab 自动归档时间为 30天
- 修改个别快捷键
### 浏览器拓展
> Arc 也是基于 Chromium 的， 所以自然也可以使用 Chrome Web Store 的拓展

![[CleanShot 2023-10-06 at 19.28.15.png]]

这个也是个人拓展的备份，有推荐的欢迎到评论区补充，直接贴图，个人比较推荐的是
1. Immersive Translate (沉浸式翻译)
2. Vimium 
3. Octotree
4. GitHub Web IDE
5. Tampermonkey

**沉浸式翻译** 相比传统划词翻译，直接在原文的基础上插入译文，方便对照，可以说通过它的帮助下，阅读英文资料的速度是之前远不可比拟的。
**Vimium** 则是支持通过 Vim 键位 进行一些网页操作， 如前进后退，上下滚动，打开关闭网页等等，所有操作通过键盘完成，不需要鼠标，掌握以后大部份网页操作的效率提升显著也可预防腱鞘炎。
**Octotree** 则是在 Github repo 页面增加侧边栏，可以直接预览源码目录结构和跳转对应页面，体验非常丝滑，比原生的手动一个个点进去还是方便很多。
**GitHub Web IDE** 则是支持集成了一些Github 在线沙箱环境， 无需Clone 到本地，即可在线编辑源码和查看源代码，对于只是想学习或者粗看源码到话，非常合适。
**Tampermonkey** 是大名鼎鼎的油猴插件，它可以对特定网站运行特定的javascript脚本，所以几乎无所不能。如解除网页限制，自动刷网课，去除广告，免登陆复制...等等

### 油猴脚本
油猴脚本库非常丰富，可玩性非常高，前面也提到它几乎无所不能，但是奈何个人折腾不多，，目前只保留了以下脚本，如果有好用的脚本，欢迎在评论区补充 👏～

1. 自动无缝翻页
2. B站稍后功能增强
3. CSDN Greener
4. 蓝奏云网盘增强
5. 知乎增強

**自动无缝翻页** 当滚动到页面底部自动将第二页内容插入到底部，实现流畅且自动化的浏览体验。
**B站稍后功能增强**  人如其名。
**CSDN Greener** 很多中文内容会引流至CSDN，但是CSDN 体验十分糟糕，如登录才运行复制，广告弹窗一大堆，SEO 污染搜索结果等等，总得有人治一治，当然可以考虑直接 block 掉 CSDN。
**蓝奏云网盘增强** 很遗憾，因为一些原因无法国内无法使用 Google Drive 和 OneDrive 体验非常糟糕，很多资源都只能通过蓝奏云来分享，这算是一个妥协之举。
**知乎增強** 增强知乎的阅读体验， 和 CSDN Greener 同理，总得有勇者屠恶龙。

## 开发相关

### Warp

Mac 最为流行的终端软件非 `Item2` 莫属， 但开发体验最好的却不一定。 相比之下，我会推荐 Warp，尽管曾经我对该软件需要注册帐号来使用表达过质疑，但是相比提升的效率，还是真香了。

![[Pasted image 20231006195136.png]]

### Orbstack

相信在这个云原生时代，每位开发者都在电脑上装有 Docker，容器化技术终结了之前程序员配了一个下午的环境只为打出一句 `Hello World` 的时代， 而官方的 Docker Compose 非常耗费系统资源，即便是 MacBook Pro M1 pro + 16g ram, 运行 2～3个 容器， 系统也会非常卡顿，而苹果的内存又比金子还贵，然后救星 Orbstack 来了。

> OrbStack 是运行 Docker 容器和 Linux 的快速、轻便且简单的方法。 Docker Desktop 替代方案以光速进行开发。Say goodbye to slow, clunky containers and VMs

与Dokcer Compose 相比， OrbStack 对 CPU 和磁盘的使用率低，对内存的需求少，而且是一款原生的 Swift 应用程序，可以无缝运行 Docker 容器和完整的 Linux 发行版，并提供强大的网络功能。个人也是可以完全免费使用！
![[Pasted image 20231006195650.png]]
### Surge

一个很好用的 http 调试工具， 顺带一些附加功能，比如流畅访问Github， ChatGPT 等， 嗯嗯。 需要注意的是，价格比较高昂， 而且 Mac 和 IOS 版本都需要单独购买， IOS 版本附赠 Apple TV 版本的 TV OS版

![[CleanShot 2023-10-06 at 20.00.58.png]]
### Dash
开发者离线文档库，可通过订阅 setapp 免费获取。如果你需要经常翻阅某个文档，那么下载到Dash 离线观看也许体验更加良好。


### Telegram & Discord

许多框架和服务都提供 Slack / Discord 的联系方式， 通过Discord 可以第一时间接受到 官方开发团队的一手消息，同时也见证着社区其他力量，以及练习英语，如果你有参与开源项目的打算，那么 Discord 是必备的， 或者你只是想开黑打游戏呢 🎮 ～

###  VS Code & Jetbrains
因为做的是 Web 开发， 所以这两位大家相信都比较熟悉了，直接跳过了。

## 工具相关

### Raycast

### Setapp

### PopClip

### Gifox

### Bartender

### 1Password
密码管理这块， 综合最佳还是老牌的 1Password

### AirBuddy
### Input Source Pro

### CleanShot X

### CleanMyMac X

### Live Wallpaper

### IRightMouse Pro
国产开发团队出品的精品Mac应用 - 超级右键。
因为Mac 系统原生的右键十分操蛋！如不能剪切，粘贴，新建文件等等。 超级右键则是增强系统右键功能，提升效率杠杠地！

### Rectangle

### OpenAI translator


## 影音相关
### Downie
### Infuse 

### IINA

### Spotify
### 网易云音乐

## 笔记相关
> 笔记应用都是免费的，但是可以付费解锁一些功能， 如上传更大的附件，云同步，在线访问等等
### Notion
颠覆这个领域的产品， 不解释。 甚至产生名词 - 类 Notion ， 足以证明 Notion 的成功。

### Obsidian
因为笔记还是需要离线备份，所以选择 Obsidian，Affine 也不错， 但是懒得折腾了～

### 语雀
如果只是做知识整理等， 国内做得最好的还是语雀，还是非常不错的产品的。

## 苹果内置
> 这里整理了一些苹果内置的 APP， 不一定是最好用， 但因为是内置， 所以够用的话对我个人而言是没有必要替换的

### Mail

可绑定 QQ 邮箱 和 Gmail

### iCloud
使用苹果全家桶很难离得开 iCloud， 个人使用的是美区Apple ID，速度和隐私性都得到保障。

同时也在 oneDrive， 不过 oneDrive 目前国内同步非常不稳定，无科学手段基本无法使用，但是偶尔也会和 PC 同步一些东西，加上 oneDrive 价格更加优惠，1T oneDrive 通过 office 365 家庭版拼车一年才 40+ ， 国区 iCloud 2T 一个月就 68¥ 了。
### Apple One

Apple 营收最多的产品是 iPhone，营收第二不是 Mac 也不是 Ipad， 而是 Apple Service ，也就是苹果服务，其中很大部份来自于 苹果的订阅服务 Apple One。

> **Apple One**是苹果公司推出的一项服务，将**Apple** Music、**Apple** TV Plus、**Apple** Arcade、**Apple** News Plus 和iCloud 存储整合在一起，该捆绑服务还**包括**新公布的**Apple** Fitness Plus。

根据 iCloud 的容量分为 中杯，大杯，超大杯，以及未来 加入的 iCloud 12TB 版本， 可以看到 Apple One 支持 音乐，视频，游戏，新闻，云存储等服务，如果需要的话，还是挺不错的。
友情提示： Apple One 没有在国区上线， 如果需要订阅，需要转区或者注册其他地区的Apple ID ， 如美区以及物美价廉的土耳其区等。