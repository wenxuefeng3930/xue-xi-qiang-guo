# 声明

本项目为学习 Autojs 的开源项目，仅用于技术学习与交流，严禁用于商业用途以及非法用途，所造成的后果本项目概不负责。

## 基于 Autojs 的《学习强国》自动学习脚本v4

1. 只是模拟点击，封号应该不会（理论上哈，被封别找我！）。
2. 只限制 android 系统。
3. 仅用于技术学习与交流，不可用于作弊。
4. 感谢 [Autojs](https://github.com/hyb1996/Auto.js) 作者大大提供了这个学习工具！

## 更新日志

v4 - **2022/06/13**

* 新增了自动完成挑战答题，感谢 `www.syiban.com` 提供了搜索查询服务，万分感激！
* 新增了分数不足时自动进行"四人赛"和"双人对战"，但是随机选择，不求获胜，只求保底
* 简单重构了代码，主流程函数化，主要参数都列在了开头，修改起来方便一点
* 主要函数都移除了坐标依赖，采用基于控件的模拟操作
* 由于移除了坐标依赖，因此支持了调试 console，便于修改的时候输出日志
* 删除文章的收藏、分享功能（当前版本不再需要收藏、分享）
* 支持"专项答题"重新计算题目数 [#7](https://github.com/JackZxj/xue-xi-qiang-guo/issues/7)

**2022/05/24**

* 删除每周答题以及相关的配置
* 添加 `skipAnswer` 参数用于跳过答题和订阅的部分， 添加 `skipWatch` 参数用于跳过视频、文章、本地的部分
* 添加取消新版本更新的弹窗
* 添加答题时如果不小心点到推送，返回答题的检查
* 答题从最旧做到最新
* 修改了一点点订阅功能，但目前订阅功能基本没什么用。后续再改吧

**2021/07/02**

* 热烈庆祝我党成立100周年！祝愿我党万岁！中华民族万岁！
* 在参数列表中添加了两个检查的开关【`isCheckWeeklyQuestionsOnce` 和 `isCheckSpecialQuestionsOnce`】，解决 [#5](https://github.com/JackZxj/xue-xi-qiang-guo/issues/5)。运行前请自行修改是否开启
* 添加了如果分数不足40则尝试获取订阅分数的功能

**2021/06/28**

* 修复本地学习可能卡住的问题 [#4](https://github.com/JackZxj/xue-xi-qiang-guo/issues/4)

**2021/04/08**

* 上一次修复“我的积分”概率阻塞的问题还会复现，因为判断条件错了，本次更新了判断条件
* 修复可能出现的每周答题失败，原因是月初还没更新本周答题的时候，没有出现“本月”两个词

**2021/03/18**

* 修复了概率由于网络原因，进入“我的积分”长时间阻塞，导致后续无法答题
* 新增完成后自动锁屏

**2021/02/25**

* 增加了一些 comment 便于修改适配其他机型，给朋友(EMUI)测试了，除了解锁屏部分，其他部分做一些分辨率的修改后就能运行了。朋友的学习强国版本为 2.21.0，似乎可以正常运行
* 在 README 中更新了 [使用说明](#使用说明)

v3.0.1 - **2021/02/01**

* 由于专项答题与每周答题开放之前的题目，更新了一下列表结束判断

v3

* 新增一个小 label 用于展示当前学习进度
* 文章阅读如果为图片或者视频的话，不会更新文章阅读的篇数 (大概率保证文章阅读数能拿满)
* 新增每日答题、每周答题、专项答题 (**根据官方公告，后续专项答题会开放去年未完成的题目，届时需要更新脚本里的流程**)
* 每日分数不足震动 10s 提醒
* 更新学习强国版本，适配 `2.19.0` 版本，其余版本未做适配

## 使用说明

以下为零基础 (almost) 使用说明，熟悉开发或者熟悉 autojs 的请自由操作。

0. **[手机]** 在手机上下载并安装 Autojs 4.1.1Alpha2 版本 (或以上)
1. **[手机]** 进入手机`设置`-`应用设置`，在里头找到 autojs，点开应用详情，在权限中将`读取应用列表`,    `锁屏显示`,    `后台弹出界面`,    `显示悬浮窗` 等权限开启
2. **[电脑]** 在电脑上将脚本 [v4.js](https://raw.githubusercontent.com/JackZxj/xue-xi-qiang-guo/master/v4/v4.js) 下载到某一个文件夹中，打开 `记事本` 应用，将文件 `v4.js` 拖到记事本中进行编辑
3. **[电脑]** 使用 `ctrl + F` 组合键，搜索 `修改这里`，依次根据代码中的提示，修改为自己设备的实际情况 (涉及到需要精准位置的部分，建议在 `开发者选项` 中暂时打开 `指针位置` 以显示触摸的实际位置)
4. **[手机]** 将修改好的脚本移动至手机根目录中的名为 `/脚本` 的文件夹中。若不存在可自行创建该文件夹
5. **[手机]** 打开 `autojs`，点击左上角的三条杠杠弹出侧边栏，开启侧边栏中的 `无障碍服务`，此时进入手机的无障碍服务设置 (如果没有的话，手动进入系统的设置，搜索“无障碍”进入)，在该界面中寻找 `autojs`(可能在`下载服务`之类的菜单中)，打开 `autojs` 的无障碍权限。回到 autojs 应用，在点击侧边栏左下方的设置，开启`音量上键停止所有脚本`, `保护模式` 两个选项
6. **[手机]** ~~在手机设置中将自动锁屏时间调整为 **10分钟** 及以上，然后~~确保手机在连接 wifi 的情况下，点击autojs中 `v4.js` 条目右侧的三角形运行脚本。第一次运行 **务必** 要看着脚本运行，若脚本运行错误或者出现预料之外的操作时，使用 `音量上键` 及时停止脚本，修改错误后再运行。 (注: 第一次运行测试可以把脚本最前面的参数改为以下参数快速运行一次，若没有问题的话再改回默认值)

    ``` JS
    var videoNum = 3; // 至少观看几个视频
    var videoTimeInMinute = 1; // 视频至少观看几分钟
    var articleNum = 3; // 一共阅读几篇文章
    var articleCommentNum = 1; // 一共需要评论几篇文章
    var articleTimeInMinute = 1; // 文章至少阅读几分钟
    ```

7. 一般性而言，该脚本运行多次不会有问题（潜在问题：可能会浪费 `专项答题` 数量），完整运行一次脚本大约花费25分钟左右，每天运行时最好偶尔瞟一眼，万一出错了就手动停止再运行一次。另外，设置 `skipWatch` 为 `true`, 单独保存为一份 `只有答题` 的脚本，这样可以在后面答题出错误时，避免再刷一次视频和文章，减少时间。同理也可以设置 `skipAnswer` 为 `true`，单独保存为一份 `只有视频文章` 的脚本。


> **高级操作:** 每日定时任务自动学习
> * 需要 autojs 自启动，给后台上锁允许一直后台运行，解除系统运行设置(避免因省电而杀后台)
> * 摸索手头设备的自动解锁的方式并修改到[unlock](https://github.com/JackZxj/xue-xi-qiang-guo/blob/master/v4/v4.js#L21) [lock](https://github.com/JackZxj/xue-xi-qiang-guo/blob/master/v4/v4.js#L38) (可参考[testWeakup.js](../v3/testWeakup.js))，在 autojs 中配置自动运行脚本任务 
> * 据本人手头的设备发现，在自动运行之前，必须解除手机省电模式或者处于充电状态，否则将解锁失败 (未知其他设备是否也会如此)


## 实测

### 设备

* MI Mix2 (1080*2160) 
* MIUI 12 (20.6.18)
* Autojs ~~4.0.1Beta~~ (由于此版本定时任务有[bug](https://github.com/hyb1996/Auto.js/issues/336)，升级至 [4.1.1Alpha2](https://github.com/Ericwyn/Auto.js/releases)，感谢做包的老哥~ )
* 学习强国 2.19.0

### 效果

* 自动解锁屏幕
* 杀掉在后台运行的学习强国
* 进行视频学习 6 分钟以上，刷 6 个以上视频 (相关参数: `videoNum` `videoTimeInMinute`)
* 进行文章学习 6 分钟以上，并完成评论任务 (相关参数: `articleNum` `articleCommentNum` `articleTimeInMinute`)
* 完成本地学习, **需要在脚本开头设置本地城市** (相关参数: `city`)
* 完成每日答题，直到满分
* 完成若干次挑战答题，获得5分 (相关参数: `maxTryChallenge`)
* 完成 1 次专项答题，获得0~10分
* 如果分数不足 40, 则完成 2 次四人赛，获得 2-5 分
* 如果分数不足 40, 则完成 1 次双人对战，获得 1-2 分
* 如果分数不足 40, 则尝试进行订阅，获得 0-2 分
* 如果分数到达 40, 则震动 10s 提醒, 否则震动一下表示完成

## 自动答题原理

**选择题：** 抓取提示的内容，判断选项是否出现在提示中，若出现则加入候选。若候选为空，则无论单选还是多选，默认选A

**填空题：** 抓取提示的内容，找到填空位置的前4个字和后4个字。找出提示中前4字和后4字的位置，根据这两个位置截取提示内容作为填空题答案，若截取出来的答案比填空长度要短，则填 111111111111111 (超出长度也没关系，填空限制了长度，多余的会忽略)

选择题大概率都能正确，填空题比较容易翻车，因为提示的内容不一定和题目的内容一致，并且有可能出现视频题，以本人目前的水平与能力，并没有好的解决办法。由于填空题数量一般不会太多，以目前填空题的正确率来说，感觉还是可以接受的。

## 后续可能的优化

* 检查网络环境 (指 wifi) 是否可用
* 检查是否有没完成的视频/文章分数
* ~~获取订阅分数~~ (update on 2021/07/02)
* ~~凑够每日40分~~ (update on 2022/06/13, almost)
* 支持移动网络下的自动操作
* ~~提升通用性，降低适配难度~~ (update on 2022/06/13, almost)

## 使用须知

0. autojs开启了锁定后台，电源管理中解除了后台运行限制
1. 测试机为MIUI，需要打开 auto.js 从后台打开应用的权限 (应用信息-权限管理-后台弹出界面) 才能支持解锁屏幕自动学习；测试机解锁方式为图案，在其他机器上测试时需要更改代码匹配实际解锁方式
2. 测试机为我的备用机，因此常年充电并连接wifi使用，打开了屏幕充电时常亮 (由于视频/文章阅读有很长一段时间没有操作，因此需要保持屏幕常亮。不开屏幕常亮可以用10分钟息屏代替)
3. 如果网络不佳或者手机反应较慢，相应延长操作间隔
4. 开发者模式中打开操作可见性来针对不同的设备修改位置信息
