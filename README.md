## uma_info

这是一个适用hoshinobot的赛马娘功能插件，数据来自马娘官网和bwiki

这里包含了之前开源了的功能以及新开发的功能，其他功能仍在锐意开发中

### ★ 如果你喜欢的话，请给仓库点一个star支持一下23333 ★

<details>
<summary>点我查看主要的几个功能模块</summary>

（具体命令请看下方功能命令和描述）

+ [马娘新闻播报](https://github.com/azmiao/umamusume_news) 

+ [马娘模拟抽卡](https://github.com/azmiao/uma_gacha)

+ 马娘基础数据库

+ 支援卡节奏榜

+ 相性计算器

+ 马娘黄历

+ 马娘耐力计算器

</details>

<details>
<summary>点我查看独立版和整合版的区别</summary>

+ 独立版的 [马娘模拟抽卡](https://github.com/azmiao/uma_gacha) 可以完全单独运行，内容也完全一致，可以从本整合版里直接复制出来用，但记得要装依赖哦！

+ 独立版的 [马娘新闻播报](https://github.com/azmiao/umamusume_news) 也可以完全单独运行，但和整合版的代码稍有不同，因此不可以从本整合版里直接复制出来用！

+ 另外后续关于 [马娘新闻播报](https://github.com/azmiao/umamusume_news) [马娘模拟抽卡](https://github.com/azmiao/uma_gacha) 的代码更新将会在原仓库和本仓库同步更新

</details>

## 本项目地址：
https://github.com/azmiao/uma_plugin/

## 更新日志

22-03-19    v1.3.2  新增了更新数据时自动下载语音文件，更新到此版本后需要手动更新一下数据，当然等半夜的自动更新也行

22-03-18    v1.3.1  调整了自动更新策略，将在更新时生成一个缓存文件，更新完再复制过去，以防止更新期间部分功能不能用，顺便新增手动更新相性信息功能

22-03-09    v1.3    新增了“马娘耐力计算器”功能，但数据为 根性与下坡 改版前的数据，且为非常理想的数值

22-03-09    v1.2    一些调整，以及修改部分文件使之规范化github储存库，方便 git pull, [pull #4](https://github.com/azmiao/uma_plugin/pull/4)

22-03-06    v1.1    新增了“马娘签到”功能

22-03-04    v1.0    first commit

## 注意事项

### 如何更新

> 若是从 v1.2 版本之前(不包括 v1.2)的版本更新到最新版，如果您嫌麻烦建议直接把 `uma_plugin` 文件夹删了，再按照下面的安装教程重新安装一遍

    并且建议删除前，把文件 `/uma_info/config.json` 备份出来，这样就不用再 手动更新马娘数据 了, 否则重装后需要重新使用群命令："手动更新马娘数据" 更新基础数据

> 若是从 v1.2 版本之后(包括 v1.2)的版本更新到最新版，就非常方便，可以直接在你的 `hoshino/modules/uma_plugin文件夹里，以管理员方式打开powershell，然后输入下方命令，运行完重启hoshinobot即可：

```
git pull
```

<details>
<summary>点我看看一些常规更新的内容</summary>

大多数数据均可自动更新，但是：

位于 `uma_info` 文件夹下的 `replace_dict.json` (角色别称) 

需要我手动更新，当然如果你有觉得可以添加的别称，可以fork后pull requests

因此一旦有更新我会以 commit 的形式上传至本仓库，如果您可以直接 watch 本仓库，如果会使用RSS的话可以添加本仓库，再者嫌麻烦的话可以使用我之前的插件 [github_reminder](https://github.com/azmiao/github_reminder) 添加[本仓库链接](https://github.com/azmiao/uma_plugin/)即可，一旦有任何commit更新您的bot都会提醒您

</details>

### 使用本插件需要的东西

一个OCR_SPACE的免费API（需要一个非QQ的邮箱即可）：[点我前往官网申请](http://ocr.space/ocrapi/freekey)，网站发邮件偶尔会非常慢，~~绝了~~慢慢等吧

<details>
<summary>点我查看需要 OCR 的原因</summary>

+ 由于部分数据来自官网，因此数据非常全，但这~~垃圾~~官网不少数据是整合进一张图里面了，不得不用一个OCR来识别出来，而gocq自带的OCR接口只能识别接收到的图片，虽然已经有思路如何绕过这个门槛，利用QQ的image缓存机制来识别，但这样依然非常不方便，而且为了部分功能实现的资源占用更低，还是选择了第三方的接口，ocr_space的接口速度也比较快，而且免费版每天有500次，而本插件每天只需要进行88次即可，但是网站比较不稳定，偶尔会500~~免费的还要什么自行车~~

</details>

## 功能命令和描述

### 注：群内查看功能帮助可以发送：“马娘帮助”

<details>
<summary><font size = 4>维护组的所有命令</font></summary>

马娘数据库的：

 - 手动更新马娘数据

马娘相性的：

 - 手动更新相性信息

马娘抽卡的：

 - 更新马娘信息

 - 重载赛马娘卡池

</details>

<details>
<summary><font size = 4>马娘基础数据库模块</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 查今天生日马娘 | 看看今天哪只马娘生日(仅限马娘) |
| 查马娘生日 xx | xx为马娘名字，查询这只马娘是哪天生日(仅限马娘) |
| 查生日马娘 m-d | m-d就是 m月d日 ，查询这天有哪些马娘生日(仅限马娘) |
| 查角色id xx | xx为角色名字 |
| 查角色日文名 xx | xx为角色名字 |
| 查角色中文名 xx | xx为角色名字 |
| 查角色英文名 xx | xx为角色名字 |
| 查角色分类 xx | xx为角色名字 |
| 查角色语音 xx | xx为角色名字 |
| 查角色头像 xx | xx为角色名字 |
| 查角色cv xx | xx为角色名字 |
| 查角色身高 xx | xx为角色名字 |
| 查角色体重 xx | xx为角色名字 |
| 查角色三围 xx | xx为角色名字 |
| 查角色制服 xx | xx为角色名字 |
| 查角色决胜服 xx | xx为角色名字 |
| 查角色原案 xx | xx为角色名字 |
| 查角色适应性 xx | xx为角色名字 |
| 查角色详细信息 xx | xx为角色名字(显示全部信息) |
| 手动更新马娘数据 | 功能限维护组 |
| (每天1:31自动更新马娘数据) | 该功能没有命令 |
| (每天9:31自动推送该日生日的马娘) | 该功能没有命令，且本功能需额外开启 |

</details>

<details>
<summary><font size = 4>相性计算器</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘相性帮助 | 看看详细帮助内容 |
| 查相性 本体 父母1 祖父母1 祖父母2 父母2 祖父母3 祖父母4 胜鞍数 | 1.直接按照下面的指令写马名即可，请按顺序写，注意空格别漏<br>2.胜鞍数为胜鞍+金牌的总个数，类型为整数，且可写可不写<br>3.判断胜鞍：(父母1和祖父母1相同的重赏胜场数)+(父母1和祖父母2相同的重赏胜场数)+(父母2和祖父母3相同的重赏胜场数)+(父母2和祖父母4相同的重赏胜场数) |
| 查相性 本体 父母1 祖父母1 祖父母2 父母2 祖父母3 祖父母4 | 同上，表示可以不加胜鞍 |
| 查相性 马娘1 马娘2 | 查两只马娘之间的相性，这里不可以加胜鞍 |
| 相性榜 马娘 | 相性榜是指生成对这只马娘相性最好的马娘排行榜 |

</details>

<details>
<summary><font size = 4>支援卡节奏榜</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 速卡节奏榜 | 对应速度卡 |
| 耐卡节奏榜 | 对应耐力卡 |
| 力卡节奏榜 | 对应力量卡 |
| 根卡节奏榜 | 对应根性卡 |
| 智卡节奏榜 | 对应智力卡 |

</details>

<details>
<summary><font size = 4>马娘新闻播报</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘新闻 | 查看最近五条新闻 |
| 新闻翻译 | 查看翻译命令和新闻编号（限近5条） |
| 新闻翻译 1 | 翻译第1条新闻，编号可选值(1/2/3/4/5) |
| (马娘新闻推送) | 该功能没有命令，且本功能需额外开启 |

</details>

<details>
<summary><font size = 4>马娘模拟抽卡</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 查看马娘卡池 | 看马娘当前的池子 |
| @bot马娘单抽 | 马娘池子单抽 |
| @bot马娘十连 | 马娘池子十连 |
| @bot马之井 | 马娘池子抽一井 |
| @bot育成卡单抽 | 育成卡池子单抽 |
| @bot育成卡十连 | 育成卡池子十连 |
| @bot育成卡井 | 育成卡池子抽一井 |
| 更新马娘信息 | 更新图片数据等并自动重载赛马娘卡池，功能限维护组 |
| 重载赛马娘卡池 | 仅刷新马娘当前UP卡池的信息（不含图片数据），功能限维护组 |
| (每天4点自动更新马娘信息) | 该功能没有命令 |

</details>

<details>
<summary><font size = 4>马娘黄历</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘签到 | 看看今日的黄历？ |

</details>

<details>
<summary><font size = 4>马娘耐力计算器</font></summary>

| 功能命令 | 介绍 |
| :---- | :---- |
| 马娘耐力帮助 | 看看详细帮助内容 |
| 举个例子： |  |
| 算耐力<br>属性:1200 600 1200 600 700<br>适应性:逃马-A 芝-A 1600-A<br>干劲:绝好调 状况:良<br>固回:0 普回:0 金回:1 | 计算最低耐力需求 |

</details>

## 食用教程：

<details>
<summary>点我展开</summary>

0. 申请OCR_SPACE的免费API，（需要一个非QQ的邮箱即可）：[点我前往官网申请](http://ocr.space/ocrapi/freekey)，网站发邮件偶尔会非常慢，~~绝了~~慢慢等吧，哦，对了，记得翻翻垃圾邮件

    第一封邮件是确认注册
    
    第二封邮件才是给你发APIKEY

1. 下载或git clone本插件：

    在 HoshinoBot\hoshino\modules 目录下使用以下命令拉取本项目
    ```
    git clone https://github.com/azmiao/uma_plugin
    ```

2. 如果之前装过 [马娘新闻播报](https://github.com/azmiao/umamusume_news) 和 [马娘模拟抽卡](https://github.com/azmiao/uma_gacha) 的，请先删除那两个文件夹，没有就跳过这一步

3. 填写APIKEY：

    打开 uma_plugin 文件夹下的 `APIKEY.txt` 文件

    在里面粘贴上你申请的APIKEY即可

4. 安装依赖：

    到HoshinoBot\hoshino\modules\uma_plugin目录下，管理员方式打开powershell
    ```
    pip install -r requirements.txt -i http://mirrors.aliyun.com/pypi/simple
    ```

5. 在 HoshinoBot\hoshino\config\ `__bot__.py` 文件的 MODULES_ON 加入 'uma_plugin'

    然后重启 HoshinoBot

    等待装完插件后首次启动的自动更新马娘抽卡数据和图片，预计用时1分钟？

    更新完后请维护组 __再发送群消息__  “手动更新马娘数据” 来更新马娘数据库的数据，预计用时8分钟

    更新期间您可以看着QQ消息，或者看着Hoshino日志以防意外情况

6. 额外功能：（自动提醒）

    在某个群里发消息输入下文以开启马娘生日提醒
    ```
    开启 uma_bir_push
    ```

    在某个群里发消息输入下文以开启马娘新闻播报
    ```
    开启 umamusume-news-poller
    ```

    可以通过发消息输入"lssv"查看这个功能前面是不是⚪来确认是否开启成功

</details>

## 另有图片预览，请看：

https://www.594594.xyz/2022/03/04/uma_plugin/