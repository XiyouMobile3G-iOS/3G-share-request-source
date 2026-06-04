# 3G Share — UIKit 界面练习资源

> **学长说**：学弟学妹们好！这个仓库是留给你们练手用的。里面是一套 APP 界面设计资源（PSD 源文件 + JPG 预览图 + 演示视频），不包含可直接运行的 Xcode 工程。你们需要先新建一个 iOS App 工程，再用 **Objective-C + UIKit** 把这些界面一行一行代码敲出来。设计稿用于理解功能和信息层级，不要求像素级复刻。

---

## 这是什么？

这是一个**UIKit 界面练习素材仓库**。

**3G Share** 原本是实验室前辈在 2014 年做的一套高校创意分享平台设计，包含 8 大模块、30+ 个界面。现在它成了你们的**UIKit 实战教材**。

核心任务很简单：**看着设计稿理解功能，用纯代码写出功能接近、体验合理、符合 Apple HIG 的界面。**

推荐练习技术栈：**Objective-C + UIKit + 纯代码 Auto Layout**。默认不使用 Storyboard / XIB，页面、组件、约束和跳转逻辑都用 OC 代码实现。

---

## 技术栈与现代化要求

基础要求：
- 使用 **Objective-C + UIKit**，项目可以用最新稳定版 Xcode 创建。
- 使用纯代码布局，优先练习 `NSLayoutConstraint`、`UILayoutGuide`、Safe Area、Trait Collection 和动态字体适配。
- 兼容当前主流 iOS 版本，并尽量适配最新 iOS 的系统外观和交互规范。

UI 设计要求：
- 不需要完全参考设计稿；设计稿主要用于确认页面功能、内容类型、导航关系和大致信息层级。
- 最终界面可以有自己的小巧思，例如更自然的留白、更清晰的卡片层级、更顺手的菜单入口、更符合当前系统的按钮样式。
- 自由发挥必须建立在 Apple HIG 之上。重点关注 HIG 当前强调的 hierarchy、harmony、consistency：层级清楚、视觉和设备/系统风格协调、交互遵循平台习惯。
- 开始写 UI 前，先看 Apple 官方基础设计资料和设计原则视频，再决定页面布局、控件选择、动效和反馈。
- 如果设计稿里的视觉细节和 HIG 或当前 iOS 系统习惯冲突，优先遵循 HIG 和系统控件规范。

现代化要求：
- 每次开工前先查看 Apple Developer Documentation 和 Human Interface Guidelines，以当时最新发布的 UIKit API、系统设计规范和 Xcode SDK 为准。
- 优先使用标准 UIKit 控件，例如 `UINavigationBar`、`UITabBar`、`UIToolbar`、`UIButton`、`UICollectionView`。标准控件通常能自动获得新系统的视觉更新。
- 如果最新 iOS 提供新的视觉能力，例如 iOS 26 的 Liquid Glass，可以在不破坏原设计层级的前提下做渐进增强。UIKit 中优先关注 `UIGlassEffect`、`UIGlassContainerEffect`、`UIVisualEffectView` 和新版 `UIButtonConfiguration`；旧系统必须提供降级方案，例如 `UIBlurEffect` 或普通半透明背景。
- 使用新 API 时必须做版本判断，例如 `if (@available(iOS 26.0, *))` 或 `respondsToSelector:`，不要让低版本系统编译或运行崩溃。
- 可以自由发挥加入合理的交互细节，例如 `UIImpactFeedbackGenerator`、`UISelectionFeedbackGenerator`、`UINotificationFeedbackGenerator` 的马达震动反馈。
- 可以加入课堂没有重点讲过但很实用的 UIKit 组件，例如 `UIMenu`、`UIAction`、`UIContextMenuInteraction`、`UIEditMenuInteraction`，用于更多操作、长按菜单、编辑菜单和快捷操作。
- 不要为了炫技堆满玻璃、动画和震动。新效果只服务于信息层级、反馈清晰度和操作效率。

官方资料入口：
- Apple Developer Documentation: https://developer.apple.com/documentation/uikit
- Liquid Glass 技术概览: https://developer.apple.com/documentation/technologyoverviews/liquid-glass
- UIKit 外观定制: https://developer.apple.com/documentation/uikit/appearance-customization
- Human Interface Guidelines: https://developer.apple.com/design/human-interface-guidelines
- Apple Design Pathway: https://developer.apple.com/design/get-started/
- Essential Design Principles: https://developer.apple.com/videos/play/wwdc2017/802/

---

## 为什么要做这个练习？

UIKit 光看教程是不够的，必须上手写。这个项目能帮你练到：

| 技能点 | 你会在哪些页面练到 |
|--------|------------------|
| UIView 基础布局、Frame / Auto Layout | 所有页面 |
| UITableView 列表展示与自定义 Cell | 首页、搜索结果、私信列表、我的上传 |
| UICollectionView 网格/瀑布流布局 | 首页作品展示、图片选择 |
| UINavigationController 页面跳转 | 所有含层级推进的页面 |
| UITabBarController 底部导航 | 主框架（首页-搜索-文章-活动-我的）|
| UIScrollView 横向/纵向滚动 | 首页滑动内容、图片预览 |
| 自定义 UI 组件封装 | 导航栏按钮、输入框样式、头像视图 |
| 现代 UIKit 组件 | UIMenu、UIAction、Context Menu、编辑菜单 |
| 交互反馈 | 按钮点击、选择切换、提交成功/失败的马达震动反馈 |
| 最新 iOS 视觉适配 | 标准控件新外观、Liquid Glass 渐进增强、深色模式 |
| 网络图片加载与缓存（SDWebImage）| 任何带图片的页面 |
| MVC 代码组织 | 整个项目 |

---

## 仓库结构

```
3G-share-request-source/
├── README.md                          # 本文件
├── 2020.07.19.21.24.mp4               # 项目演示视频（先看这个，建立整体印象）
└── share+4.18最终/                     # 设计资源主目录
    ├── 1 开机界面/          # 启动页 LaunchScreen
    ├── 2 登录界面/          # 登录页（UITextField、UIButton 样式）
    ├── 3 注册界面/          # 注册页（表单验证逻辑）
    ├── 4 首页/              # 主内容流（UITableView / UICollectionView）
    ├── 5 搜索/              # 搜索 + 上传流程（UISearchBar、图片选择器）
    ├── 6 文章/              # 文章详情（UILabel 富文本、图文混排）
    ├── 7 活动/              # 活动页（卡片式布局）
    ├── 8 个人信息/          # 用户中心（多组 TableView、设置项）
    ├── jpg 预览图/          # 所有界面的 JPG 截图（开发时对照用）
    ├── share logo/          # App Logo 素材
    └── 新建文件夹/          # 历史导出素材，包含 PNG 图标、图片和登录页相关素材
```

多数模块下都有：
- **`原件/`** —— PSD 源文件（需要精确尺寸/颜色时打开查看）
- **`图片/`** —— 导出的单张界面图

注意：`6 文章/` 当前只有 `原件/6 文章.psd`，导出的 JPG 请看 `share+4.18最终/jpg 预览图/6 文章.jpg`。

---

## 推荐练习顺序

不要上来就啃首页，按这个顺序循序渐进：

### 第一阶段：热身（熟悉基础控件）
1. **1 开机界面** —— 纯静态页面，练 UIView + UIImageView
2. **2 登录界面** —— UITextField、UIButton、背景图适配
3. **3 注册界面** —— 表单布局，理解输入框间距和键盘处理

### 第二阶段：核心技能（列表与导航）
4. **7 活动** —— 简单的卡片列表，练 UITableView 自定义 Cell
5. **6 文章** —— 图文详情页，练 UIScrollView + 富文本
6. **4 首页** —— 核心页面，练 UICollectionView 瀑布流 / 横向滑动

### 第三阶段：复杂交互
7. **5 搜索** —— UISearchBar、搜索结果切换、上传流程多页面跳转
8. **8 个人信息** —— 多组 UITableView（Grouped Style）、设置项逻辑

### 第四阶段：整合
9. 搭建 **UITabBarController** 主框架，把各模块串起来
10. 加上 **UINavigationController** 处理页面层级
11. 用 **UserDefaults** 模拟登录状态，实现启动页 -> 登录/首页的流程

### 第五阶段：现代化增强
12. 为常用操作补充 `UIMenu` / `UIContextMenuInteraction`，例如作品卡片的收藏、分享、举报、删除
13. 为关键交互补充 Haptic Feedback，例如 Tab 切换、点赞、上传成功、表单错误
14. 使用最新 Xcode SDK 检查系统控件外观；如果目标系统支持 Liquid Glass，再为顶部栏、底部操作区、浮动按钮等少量关键元素做渐进增强
15. 检查深色模式、动态字体、减少动态效果、降低透明度等辅助功能设置

---

## 开发建议（避坑指南）

### 1. 先"看"再"写"
每个页面动手前，先在 `share+4.18最终/jpg 预览图/` 里找到对应截图，回答：
- 这个页面是由哪些"区块"组成的？（顶部导航、中间内容、底部操作区）
- 哪些是可变内容（来自服务器/用户输入），哪些是写死的？
- 用户能在这个页面上做什么操作？（点击、滑动、输入）
- 如果按当前 iOS 设计风格重做，这个页面的主操作、辅助操作、信息层级应该如何呈现？
- 哪些地方可以自由发挥，哪些地方必须遵循系统控件和 HIG 习惯？

### 2. 从大到小，先搭骨架再填肉
```
步骤1：先放一个空白的 UIViewController，设置背景色
步骤2：把页面划分为 2-3 个大区块（上/中/下），用 UIView 占位
步骤3：在大区块里放具体的控件（Label、ImageView、Button）
步骤4：按 HIG 调整间距、字体、颜色和交互状态，让页面功能清楚、层级自然
```

### 3. 设计不是抄图
不要把练习目标理解成像素级复制。可以参考 PSD 取色和尺寸，但最终应优先保证可读性、触控舒适度、平台一致性和功能效率。颜色、字体、圆角、毛玻璃、菜单和震动反馈都可以重新设计，只要理由清楚、体验更好。

### 4. 图片资源处理
- Logo 和小图标：优先检查 `share+4.18最终/share logo/` 和 `share+4.18最终/新建文件夹/素材/` 里已有的 PNG；缺失时再从 PSD 中导出，放到 Assets.xcassets
- 内容图片（作品图、头像）：先用本地占位图写死，后面再接入网络加载
- 命名规范：`icon_xxx.png`、`bg_xxx.png`、`img_placeholder.png`

### 5. 不要一开始就追求完美
第一遍先把**布局和结构**搭出来，能跑通、能跳转就行。第二遍再回来调**细节**（间距、字体、对齐、动画）。

---

## AI 渐进式提示词（写代码时直接复制用）

以下提示词按**渐进式披露**设计，对应你开发的不同阶段。不要一次性全给 AI，按需取用。

---

### Level 1 — 项目理解（让 AI 知道你在做什么）

```
我正在使用 UIKit 对一个名为「3G Share」的 App 进行界面练习。
技术栈固定为 Objective-C + UIKit + 纯代码 Auto Layout。该项目是一套完整的高校创意分享平台 UI 设计资源，包含 8 大模块：
开机界面、登录界面、注册界面、首页、搜索、文章、活动、个人信息。

项目路径下 `share+4.18最终/jpg 预览图/` 目录中有所有界面的截图，
`share+4.18最终/` 下各模块的 `原件/` 中有 PSD 源文件。

请基于目录结构和预览图，帮我梳理：
1. 这个 App 的完整页面层级树（哪个页面跳转到哪个页面）
2. 每个页面最适合用 UIKit 的哪些控件实现
3. 哪些地方适合加入现代 UIKit 组件，例如 UIMenu、UIAction、UIContextMenuInteraction、UIFeedbackGenerator
4. 哪些地方可以根据当前最新 iOS 设计规范做渐进增强，例如 Liquid Glass、深色模式、动态字体
5. 哪些设计稿细节可以不照搬，如何在符合 Apple HIG 的前提下重新设计
6. 建议的 Objective-C 代码文件组织方式（哪些页面可以复用基类 / 通用组件）
```

**用的时候**：把这段直接发给 AI，附上你看到的预览图描述或截图。

---

### Level 2 — 单页面实现（让 AI 帮你写具体页面）

```
请帮我用 Objective-C + UIKit 实现「3G Share」App 的【填入页面名，如：登录界面】。

【参考资源】
- 预览图路径：share+4.18最终/jpg 预览图/2 登陆界面.jpg
- PSD 源文件路径：share+4.18最终/2 登录界面/原件/2 登陆界面.psd

【要求】
1. 使用纯代码布局（不用 Storyboard / XIB）
2. 支持 iPhone 各尺寸屏幕适配（使用 Auto Layout 约束）
3. 功能和信息层级要接近设计稿，但 UI 不需要像素级还原
4. 按钮需要绑定点击事件（先 print 模拟，后续接入真实逻辑）
5. 如果是输入页面，处理键盘弹出时的布局调整（键盘遮挡输入框的问题）
6. 根据当前最新 iOS 和 UIKit 官方文档，判断是否适合加入新版系统交互或视觉效果
7. 可以加入合理的 Haptic Feedback、UIMenu、UIContextMenuInteraction 等增强，但要有版本判断和旧系统降级方案
8. 如果使用 iOS 26 Liquid Glass 等新能力，优先使用 UIKit 原生 API，并提供低版本 fallback
9. 设计上可以自由发挥，但必须符合 Apple HIG。写代码前请先参考 Apple Design Pathway 和 Essential Design Principles 视频

【输出格式】
- 先简要分析这个页面包含哪些功能、信息层级、HIG 设计取舍，以及布局思路
- 给出完整的 Objective-C 代码（.h / .m，包含 import、类定义、生命周期方法）
- 说明如何在项目中使用这段代码（如何 push / present 出来查看效果）
```

**用的时候**：把 `【填入页面名】` 换成你当前要写的页面，路径也对应修改。

---

### Level 3 — 组件封装（让 AI 帮你提炼可复用代码）

```
在「3G Share」项目中，我发现多个页面都有相似的 UI 元素，请帮我封装成可复用的 UIKit 组件。

【当前遇到的重复代码】（举例）
- 多个页面有相同的圆角按钮（绿色背景、白色文字、特定圆角）
- 多个页面使用相同的输入框样式（带底边框、左侧图标、占位文字）
- 个人信息页和设置页都有类似的"箭头行"（左侧文字 + 右侧箭头）

【要求】
1. 基于 Objective-C + UIKit 封装自定义 UIView / UIButton / UITableViewCell 子类
2. 支持通过初始化参数或属性配置内容，方便在不同页面复用
3. 支持按需加入 UIMenu、UIAction、UIContextMenuInteraction 或 UIFeedbackGenerator
4. 使用最新 iOS API 时必须包含版本判断和旧系统 fallback
5. 提供使用示例代码（在某个 UIViewController 中如何使用这个组件）
6. 代码注释清晰，说明每个公开属性的作用

【输出格式】
- 组件类代码（.h / .m 文件）
- 使用示例代码
- 该组件适用于项目中哪些页面的说明
```

**用的时候**：把你实际写代码时发现的重复模式填进 `【当前遇到的重复代码】`。

---

### Level 4 — 项目架构（让 AI 帮你整合整个项目）

```
我已经用 Objective-C + UIKit 实现了「3G Share」App 的多个独立页面，现在需要把它们整合成一个完整的可运行项目。

【已完成的页面】（根据你的实际情况勾选或列出）
[ ] 开机界面（LaunchScreen.storyboard 或纯代码）
[ ] 登录界面
[ ] 注册界面
[ ] 首页
[ ] 搜索页
[ ] 文章页
[ ] 活动页
[ ] 个人信息页

【整合需求】
1. 搭建 App 主框架：使用 UITabBarController 作为根控制器，底部 5 个 Tab（首页、搜索、文章、活动、我的）
2. 每个 Tab 对应一个 UINavigationController，支持页面层级 push
3. 实现登录状态判断：未登录时显示登录页，登录后进入主框架
4. 用 UserDefaults 模拟用户登录状态（用户名、token）
5. 各页面之间的跳转逻辑（如：首页点击作品 -> 作品详情；搜索点击结果 -> 详情；个人信息点击设置 -> 设置页）
6. 根据最新 iOS 设计规范补充现代化增强：标准系统控件外观、UIMenu、Haptic Feedback、深色模式、动态字体、必要时的 Liquid Glass 渐进增强

【输出格式】
- App 整体架构图（文字描述或伪代码结构）
- AppDelegate / SceneDelegate 中的关键配置代码
- 主框架搭建代码（TabBarController + NavigationController 嵌套）
- 登录状态管理代码（简单的单例或工具类）
- 新 iOS API 的版本判断和 fallback 策略
```

**用的时候**：勾选你已经写完的页面，让 AI 基于现有进度帮你搭架构。

---

## 检查清单（做完一个页面对照一下）

| 检查项 | 是否完成 |
|--------|---------|
| 页面能在模拟器/真机上正常显示，无崩溃 | [ ] |
| 页面功能、内容类型和导航关系与设计稿大体一致 | [ ] |
| 信息层级清晰，主操作和辅助操作容易区分 | [ ] |
| UI 符合 Apple HIG，具备 hierarchy、harmony、consistency | [ ] |
| 字体、颜色、留白、触控区域和对比度清晰舒适 | [ ] |
| 图片显示正常，无拉伸变形（contentMode 设置正确）| [ ] |
| 不同屏幕尺寸（iPhone SE / 标准屏 / Max）布局正常 | [ ] |
| 页面可以正常 push / pop 或 present / dismiss | [ ] |
| 按钮点击有响应（至少 print 日志）| [ ] |
| 合理使用 UIMenu / Context Menu / Edit Menu 等现代 UIKit 组件 | [ ] |
| 关键交互有适度马达震动反馈，且不会频繁打扰用户 | [ ] |
| 新 iOS API 都有版本判断和旧系统 fallback | [ ] |
| 深色模式、动态字体、减少动态效果、降低透明度下仍可用 | [ ] |
| 代码有基本注释，变量命名清晰 | [ ] |

---

## 学长寄语

UIKit 是 iOS 开发的基石，哪怕以后用 SwiftUI，UIKit 的底层逻辑也是相通的。这个项目界面数量足够多、交互类型足够全，踏踏实实写完，你会对以下东西有肌肉记忆：

- 什么时候用 TableView，什么时候用 CollectionView
- 怎么写自定义 Cell，怎么优化复用
- 怎么处理键盘、怎么处理手势冲突
- 怎么用 Objective-C 写约束（Masonry 或原生 NSLayoutConstraint）
- 怎么把一个大页面拆成可维护的组件
- 怎么从旧设计稿提取功能和层级，再用 HIG 与新 iOS 设计语言重新组织界面

**不要复制粘贴 AI 给的代码。** 先自己写，卡住了再看 AI 的提示，或者让 AI review 你的代码。代码是敲进脑子里的，不是复制进项目的。

做完这个练习，你可以把它作为 UIKit 页面实现和多页面整合的练习经历。加油，实验室等你们出作品。

---

## 附录：资源速查

### 根目录
```
3G-share-request-source/
├── README.md
├── 2020.07.19.21.24.mp4               # 先看演示视频
└── share+4.18最终/
    ├── 1 开机界面/    (原件/ + 图片/)
    ├── 2 登录界面/    (原件/ + 图片/)
    ├── 3 注册界面/    (原件/ + 图片/)
    ├── 4 首页/        (原件/ + 图片/)
    ├── 5 搜索/        (原件/ + 图片/)
    ├── 6 文章/        (原件/；导出 JPG 在 jpg 预览图/)
    ├── 7 活动/        (原件/ + 图片/)
    ├── 8 个人信息/    (原件/ + 图片/)
    ├── jpg 预览图/    (所有界面截图，开发时主要对照这里)
    ├── share logo/    (App Logo 素材)
    └── 新建文件夹/    (历史导出素材，包含 PNG 图标、图片和登录页相关素材)
```

### 全部预览图列表
- `1 开机界面.jpg`
- `2 登陆界面.jpg`
- `3 注册界面.jpg`
- `4 首页.jpg` / `4 首页—2.jpg` / `4 首页—3.jpg` / `4 首页—4.jpg` / `4 首页-滑动内容2.jpg`
- `4 首页—作品页面.jpg` / `4 首页—作品页面2.jpg`
- `5 搜索.jpg` / `5 搜索—内容输入.jpg` / `5 搜索—搜索结果.jpg`
- `5 搜索-上传1.jpg` / `5 搜索-上传2.jpg`
- `5 搜索-上传-选择图片(1).jpg` / `5 搜索-上传-选择图片(2).jpg`
- `6 文章.jpg`
- `7 活动.jpg`
- `8 个人信息.jpg` / `8 个人信息-我的信息.jpg` / `8 个人信息-我的信息-私信.jpg` / `8 个人信息-我的信息-私信对话.jpg` / `8 个人信息-我的信息-新关注的.jpg`
- `8 个人信息-我推荐的.jpg` / `8 个人信息-我的上传.jpg`
- `8 个人信息-设置.jpg` / `8 个人信息-设置-基本资料(2).jpg` / `8 个人信息-设置- 消息设置(4).jpg` / `8 个人信息-设置-修改密码(3).jpg` / `8 个人信息-设置-清除缓存(6).jpg`

---

*Last updated by 学长 | 供学弟学妹 UIKit 练习使用*
