# dify-meeting-minutes-ai-agent
基于Dify低代码可视化编排搭建的多模态AI Agent，上传音频自动生成结构化会议纪要，支持同时返回文本预览 + Word/PDF文档下载链接。

## ✨ 工作链路
`用户上传音频 → SiliconFlow SenseVoiceSmall ASR语音转写 → DeepSeek LLM生成Markdown纪要 → Markdown Exporter插件导出文档 → 返回纪要文本 + 文件下载链接`

## 🧩 核心能力
1. 音频文件识别，自动转写录音文本
2. LLM输出标准化Markdown会议纪要，包含核心结论、待办事项、关键讨论点
3. 一次性返回文本预览，同时生成可下载Word/PDF文档
4. 模型解耦，ASR语音模型与LLM大模型可灵活切换API服务商

## 📦 一键导入复现
> 本项目DSL为YAML格式，旧版/新版Dify均可直接导入
1. Dify新建Chatflow应用，选择「导入DSL文件」
2. 上传仓库内 `meeting-minutes-ai-agent.yml`
3. 在模型供应商页面配置 **SiliconFlow API Key**
4. Dify插件市场手动安装 `Markdown Exporter` 插件
5. 预览页面上传音频，即可完整跑通全流程

> ⚠️ 注意：DSL仅保存编排逻辑，不会打包API密钥与插件本体，导入后需要自行配置。跨Dify大版本导入可能存在少量节点兼容问题。

## 🖼️ 工作流截图
![workflow](./workflow.png)

## 💡 项目亮点
低代码搭建端到端音频解析Agent，串联语音识别、大模型文本整理、文档渲染工具；
工具与大模型职责分离，LLM负责内容创作，独立插件负责二进制文档导出；
适用于项目例会、访谈录音自动化纪要，减少人工整理成本。

## 📄 项目文件说明
- `meeting-minutes-ai-agent.yml`：Dify Chatflow DSL编排文件
- `workflow.png`：工作流画布截图
- `README.md`：项目说明文档
