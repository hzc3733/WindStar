---
title: "把B站视频转成本地AI知识库！新手也能3分钟上手"
url: "https://www.bilibili.com/video/BV1g1dLBPEHV/?spm_id_from=333.1007.tianma.15-4-58.click&vd_source=be52938c173d1c63babcec4f036a9ee0"
bvid: "BV1g1dLBPEHV"
cid: "37589944385"
author: "MIP耀"
upload_date: "2026-04-17"
subtitle_lang: "中文"
created: "2026-05-13"
tags: ["clippings", "bilibili"]
---

<iframe src="https://player.bilibili.com/player.html?aid=116420927166252&bvid=BV1g1dLBPEHV&cid=37589944385&page=1&autoplay=0" scrolling="no" border="0" frameborder="no" framespacing="0" allow="fullscreen; picture-in-picture" allowfullscreen="true" style="height:100%;width:100%; aspect-ratio: 16 / 9;"> </iframe>

## 简介

「把B站视频转成本地AI知识库！新手也能3分钟上手」
初投稿，感谢@杰森的效率工坊  与@小陈师傅c_z  的分享。
原知识库仓库Github地址：https://github.com/jason-effi-lab/karpathy-llm-wiki-vault
B站视频插件仓库地址：https://github.com/haixiong1997/Bilibili-Obsidian-Clipper

#Obsidian #知识库 #效率工具 #新手教程 #Karpathy

## 章节

- `00:00` 开场：理念与工具链介绍
- `02:22` Live Demo：B站视频一键入库实操

## 字幕

### 开场：理念与工具链介绍 `00:00`

`00:00` 把B站视频整理至本地LLM-Wiki
`00:03` 从视频收藏到AI可理解的知识库
`00:05` 油管能 B站也能
`00:07` 这一页
`00:08` 介绍Andre Karpathy提出的LLM-Wiki核心理念
`00:11` 他提出利用obsidian作为本地知识库
`00:13` 通过obsidian Web Clipper抓取视频
`00:15` 生成可被LLM理解的Markdown笔记
`00:18` 实现知识互联
`00:19` 核心思路是这样的
`00:20` 视频通过Web Clipper抓取
`00:22` 转化为Markdown格式
`00:24` 存入obsidian vault
`00:25` 让LLM能够理解
`00:27` 最终实现知识生长
`00:28` b站up主杰森的效率工坊
`00:30` 开源了一个obsidian知识库模板
`00:32` 叫karpathy llm wiki vault
`00:34` 它基于Karpathy的理念构建
`00:35` 支持YouTube视频自动抓取
`00:37` 但是有一个问题
`00:38` YouTube视频可以用obsidian Web Cipper
`00:41` 正常抓取
`00:42` 而b站视频不行
`00:43` 插件无法解析b站页面结构
`00:45` 需要专用解决方案
`00:46` b站用户面临三个主要困境
`00:48` 第一是平台差异
`00:50` b站采用不同的播放器与页面结构
`00:52` obsidian Web Clipper无法正确解析
`00:54` 第二是字幕格式
`00:55` b站字幕格式与YouTube不同
`00:57` 需专门解析才能提取
`00:59` 第三是特有数据
`01:01` b站特有的BVID等数据需单独处理
`01:03` 问题本质是
`01:04` b站聚集了大量优质学习资源
`01:06` 却无法像YouTube一样收入本地知识库
`01:08` 为了解决这个问题
`01:10` b站up主小陈师傅cz
`01:12` 开发了bilibili Web Clipper浏览器扩展
`01:14` 这是专为b站定制的工具
`01:16` 可以一键将视频转化为结
`01:17` 构化笔记目前支持Chromium内核
`01:20` 浏览器如Chrome和edge
`01:22` Firefox版本也由up主提供适配
`01:24` 接下来演示完整工作流程
`01:27` 共4步第一步
`01:28` 安装插件
`01:29` 通过浏览器扩展商店或Github
`01:31` 下载并安装bilibili Web Clipper
`01:33` 第2步打开任意b站视频页面
`01:36` 点击浏览器右上角的扩展图标
`01:38` 第3步
`01:39` 插件会自动提取标题up主字幕和简介
`01:42` 一键生成标准Markdown文件
`01:44` 第4步文件自动存入LLM wiki vault
`01:47` 配合模板的skills功能
`01:49` 自动完成双向链接与知识图谱
`01:51` 构建
`01:52` 完整工具链
`01:52` 包含四个核心组件
`01:54` 第一obsidian
`01:55` 作为本地知识库核心
`01:57` 支持双链笔记与图谱可视化
`01:59` 第二local rest API插件
`02:01` 它为外部工具提供读写笔记库的接口
`02:04` 第三Karpathy-LLM-Wiki-Vault模板
`02:06` 提供标准化的知识管理结构
`02:08` 第四bilibili Web Clipper
`02:10` 负责抓取b站视频原数据与字幕
`02:13` 打通最后一环
`02:14` 理论就绪
`02:15` 接下来进入实战演示
`02:17` 我会一步步操作
`02:18` 展示如何用bilibili Web Clipper
`02:20` 把b站视频无缝整理进LLM-Wiki

### Live Demo：B站视频一键入库实操 `02:22`

`02:23` 默认大家已装好CDN和插件
`02:25` 我们打开get和carp ZLL MVP four仓库
`02:29` 首先看项目结构
`02:31` 核心目录是raw目录下的03 transcripts
`02:33` 这里专门存放视频转录
`02:35` 文本和会议记录
`02:36` 我们稍后将把视频抓取到这个目录
`02:39` skills目录下的Ingest query
`02:41` 是我们编译检索与维护用到的技能
`02:44` 你需要克隆这个仓库到本地作为知
`02:46` 识库跟目录在subdirs中打开
`02:49` 我本地已经有一个克隆好的项目了
`02:51` 让我们进入下一步
`02:52` 在obsdian中打开仓库
`02:54` 点击设置
`02:55` 在第三方插件社区插件市场里
`02:57` 安装local list API
`02:59` 打开插件选项
`03:02` 复制这个APIT
`03:03` 稍后我们会把它填入bilibili的配置中
`03:06` 开启这个h t t p服务器选项
`03:09` 配置完成
`03:10` 我们切换到浏览器
`03:11` 打开任意b站学习视频
`03:13` 点击浏览器右上角的插件图标
`03:16` 首次使用需要配置一下
`03:18` 点击设置按钮
`03:19` 粘贴刚才复制的API key
`03:22` 笔记目录改为raw 0
`03:23` 三transcripts
`03:27` 点击测试连接
`03:29` 确保配置正确并保存设置
`03:32` 回到视频页面
`03:34` 点击保存至obsidian
`03:45` 找到刚刚保存的笔记文件
`03:47` 我已经安装了Claudian插件
`03:49` 当然你也可以使用终端
`03:50` 或者其他agent来调用skill
`03:52` 我们调用Ingest技能
`03:54` 由于API响应较慢
`03:56` 我们直接看编译后的结果
`04:01` 看
`04:02` 原文件已经被自动归档到092开文件夹
`04:07` 同时wiki目录下
`04:08` 生成了对应的概念实体和摘要
`04:12` 后续
`04:13` 我们可以通过query命令向知识库提问
`04:16` 也可以定期运行list命令
`04:18` 修复wiki目录中的错误
`04:20` 这样b站视频
`04:21` 就被转化成了AI可理解的知识库
`04:24` 从视频收藏到知识生长
`04:26` 油管能b站也能
`04:28` 如果你觉得这个工作流有帮助
`04:30` 欢迎点赞收藏
`04:31` 我们下期见