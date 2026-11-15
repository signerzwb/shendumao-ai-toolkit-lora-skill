# 训练 LoRA 其实很简单：让 AI 智能体帮你操作

这个 Skill 将本地部署和训练图像 LoRA 的经验整理为智能体可以参考的流程：用户用自然语言描述目标，具备本机工具权限的 Agent 根据实际系统检查环境、准备 AI-Toolkit、核对模型和数据、试训及验证。

**Skill 是说明书，不是训练程序，也不包含模型或训练素材。** 训练由 [Ostris AI-Toolkit](https://github.com/ostris/ai-toolkit) 等软件在用户选择的计算设备上完成；是否能运行取决于模型架构、显存、内存、磁盘、依赖、数据和权限。

## 获取与使用

完整技能目录：[skills/ai-toolkit-local-training](skills/ai-toolkit-local-training)。

1. 下载本仓库，将该完整目录添加或复制到所用 Agent 支持的技能位置，或请 Agent 先阅读其中的 [SKILL.md](skills/ai-toolkit-local-training/SKILL.md)。Codex、WorkBuddy 等产品的导入方式、工具权限与格式支持随版本而异，请参考各自文档；未对所有产品逐一验证兼容性。
2. 准备授权使用的数据，向 Agent 描述目标模型、训练类型、图片目录与操作范围。例如：“请先检查我的电脑能否使用 AI-Toolkit 训练一份人物风格 LoRA，原图不要改动，先用少量样本做小测，完成后报告。”
3. 核对它报告的硬件、模型来源、数据、预计磁盘开销和计划。实际允许的文件操作、命令和联网能力由所用产品及用户授权决定。
4. 小测通过后再明确正式训练目标。将不同 checkpoint 与未加载 LoRA 的底模，用留出样本和相同测试参数对照；由人判断效果。

## 它能协助什么？

检查显卡、驱动与已有环境；查 AI-Toolkit 是否支持目标模型训练；准备模型组件及训练数据；校验文件、隔离实验、检查日志和续训状态；整理结果和实验记录。工具不能保证任何指定显卡、模型或数据一定训练成功，智能体也可能出错。

## 已验证范围与限制

本技能根据实际工作记录重新编写为可迁移版本。历史记录中，MOSS-Image-Base 的单图编辑 LoRA 在 Windows 和 RTX 4090 D 48GB 上完成过训练及断点恢复；这不代表其他显卡或数据能复现相同结果。H3 Image 当时完成了依赖准备与离线组件加载检查，但 GPU 训练小测尚未完成，**不能宣称已训练成功**。本仓库的通用改写尚未在所有机器或 Agent 上进行端到端实测。

本地训练不等于所有信息都不出本机：Agent 可能调用云端模型或下载依赖，是否上传内容取决于产品设置、工具和用户操作。请按需保护数据，使用有权处理的素材。

## 来源

- [AI-Toolkit 项目](https://github.com/ostris/ai-toolkit)
- [OpenAI：Skills 的结构与工作方式](https://developers.openai.com/plugins/concepts/skills)
- [WorkBuddy 企业版：技能说明](https://cloud.tencent.com/document/product/1831/134432)
- [MiniMax H3-Image](https://huggingface.co/MiniMaxAI/MiniMax-H3-Image)｜[MOSS-Image-Base](https://modelscope.cn/models/openmoss/MOSS-Image-Base)

神都猫整理。仓库只分发原创说明文件，不包含第三方代码、模型权重、数据、账户信息或密钥；上游软件、模型和素材各自遵循原有许可。
