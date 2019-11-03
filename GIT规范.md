##  Git Commit & branchs 规范

#### 1、分支

- master 分支为主分支（保护分支）不能直接在master分支上进行修改代码和提交；且master分支为线上版本分支，代码只能从develop分支merge，且每次merge需要加上Tag 版本号；
- develop 分支为开发分支，是各功能分支的合并总分支，各功能分支统一merge到develop；
- feature 分支为功能性分支，根据不同需求创建独立的功能分支，开发完成后merge到develop分支；
- hotfix 分支为bug修复分支，即测试分支

Tag 采用三段式，v版本.里程碑.序号；如：v1.2.1
- 架构升级或架构重大调整，修改第2位
- 新功能上线或者模块大的调整，修改第2位
- bug修复上线，修改第3位

#### 2、Git commit中使用 emoji

**配合webstorm插件**：[gitmoji](http://gitmoji.carloscuesta.me/)使用

emoji | emoji 代码 | commit说明 
---|---|---
tada（庆祝）| :tada:| 初次提交
sparkles（火花）| :sparkles:| 引入新功能
bug（bug）| :bug:| 修复bug
bookmark（书签）| :bookmark:| 发行/版本标签
ambulance（急救车）| :ambulance:| 重要补丁
lipstick（口红）| :lipstick:| 更新 UI 和样式文件
wrench（扳手）| :wrench:| 修改配置文件
heavy_plus_sign（加号）| :heavy_plus_sign:| 增加一个依赖/代码/文件
heavy_minus_sign（减号）| :heavy_minus_sign:| 减少一个依赖/代码/文件
arrow_up（上升箭头）| :arrow_up:| 升级依赖
arrow_down（下降箭头）| :arrow_down:| 降级依赖
zap（闪电）| :zap:| 提升性能
rocket（火箭）| :rocket:| 部署功能
memo（备忘录）| :memo:| 撰写文档
hammer（锤子）| :hammer:| 重大重构
art（调色板）| :art:| 改进代码结构/代码格式
construction（施工）| :construction:| 工作进行中
apple（苹果）| :apple:| 修复 macOS 下的问题
penguin（企鹅）| :penguin:| 修复 Linux 下的问题
checkered_flag（旗帜）| :checkered_flag:| 修复 Windows 下的问题

 优点：
- 统一团队Git Commit标准，便于后续代码review、版本发布、自动化生成change log
- 可以提供更多有效的历史消息，方便快速预览合并代码
- 团队其他成员进行类 git blame 时可以快速明白代码用意


使用 emoji 形式应该遵循以下格式
```
:emoji: 不超过 50 个字的摘要，首字母大写，使用祈使语气，句末不要加句号

提交信息主体

引用相关 issue 或 PR 编号 <#110>
```

例如：
```
git commit -m ":tada: 初次提交代码"
```

另外：
- 如果不需要记录在更新日志的内容，则不要打标记。比如："添加企业内部人员信息"这种只适合开发内部告知的
- 每一条更新只占用一行，另外一行视为另一条更新描述

#### 3、禁止提交的文件

Git项目中禁止提交包含以下内容的文件
- 包含账号密码的文件
- 包含token信息的文件
- .idea、日志文件、包文件