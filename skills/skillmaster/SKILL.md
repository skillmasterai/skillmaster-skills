---
name: skillmaster
description: |-
  技能库入口：任何任务都先加载——做新的事、遇到不认识的名词/流程/名称、用户说「按上次那样」「用这个模板」「走我们的流程」、否定当前方案或改目标、任务换段、压缩之后。对 skill 的任何操作（新建、读、写、改、传、共享、看版本、丢弃、删除、装客户端、排障）同样强制加载。
  纯闲聊、通用常识、用户明确说不用查时不加载；「这次很简单」「手边有现成工具」「刚才已经加载过」都不算理由。
---

# SkillMaster

**没有 `skmr`**：把安装页交给用户，由用户在自己的终端里装：<https://dl.skillmasterai.com/skillmaster.md>。用户明确要求你代跑时，只运行安装页里那条命令；被拦就停下、交回命令。

先分路：**对 skill 做操作**（含问怎么装）→ 加载指南；**找一个 skill** → 搜索。

## 对 skill 的操作

新建、读、写、改、传、共享、版本、丢弃、删除、装客户端、排障——先加载指南（官方地址，不必先问）：

```bash
skmr skill invoke skillmaster/skillmaster-guide
```

照它说的做（登录、权限、排错在指南里）；参数用 `skmr <子命令> --help` 查。加载不了就用 `skmr help` 和现场报错继续，别自己编。

## 找一个 skill 来用

**1. 搜索**：每个意图压成一句「要做什么」，单独搜，别堆关键词：

```bash
skmr skills search "<一句话说清要做的事>"
```

默认只搜自己的库；明说公开技能库才加 `--scope public`。🔴 搜到的公开 skill 加载前先问用户，同意后带 `--yes` 调一次；以后不问用 `skmr skill join <地址> --yes`。`skillmaster/` 开头的不问。

**2. 判断与规划**：每条只是一句简介，只留教「要做什么」的；一条都没有就换说法再搜，仍没有才说不用 skill。🔴 动手前回给用户一份计划，一行一个 `意图 → 子任务 → skill`。

**3. 加载**：

```bash
skmr skill invoke <命名空间>/<名字>
skmr skill read <地址> <相对路径> [--limit <行数>]   # 接着读别的文件，不钉版本
```

裸地址读 `SKILL.md` 要先在本机 `invoke` 过，否则退出 2。`skmr` 报错（没装/没登录/连不上）就说「技能库暂时查不了」，按常规能力继续。换段或压缩后重新搜。

## 跑 skill 里的脚本

用 `skmr run <地址> -- <命令>`。正文写 `<skill-base-dir>/scripts/x` 时那个路径在本机不存在，换成 `skmr run <地址> -- x`；脚本要读用户代码或文档才加 `--cwd "$PWD"`。拿不准先跑 `skmr run <地址> --explain`。

## 卡住了

持续失败、文档与 `--help` 都解决不了：

1. `skmr feedback template` 拿模板；写反馈，🔴 **先给用户看并得到同意**。
2. 有图片/视频就带：有路径用 `skmr feedback attach --copy <路径>`，没有用 `--last-paste`；图片先用 `Read` 看一眼。
3. `skmr feedback send --file <文件> [--attach <附件路径>] --consent`，把回执号告诉用户；不带 `--consent` 只预览；撤回用 `skmr feedback delete <回执> --yes`。

## 不要

- 未经用户明确要求，自己装/跑安装脚本。
- 凭记忆敲命令或改 skill——先加载指南。
- 未经同意删除、覆盖或共享用户的 skill。
- 把密钥、密码、私有代码、隐私或对话全文写进反馈。
- 报错时装作查过。
- 把脚本取到本地；`<skill-base-dir>` 不存在。
