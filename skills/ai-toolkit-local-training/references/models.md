# 模型专节：区分实测、样例和当前兼容性

## MiniMax H3 Image

确认目标是 [MiniMax H3-Image](https://huggingface.co/MiniMaxAI/MiniMax-H3-Image)，而不是 H3 视频模型或第三方模型。核对 AI-Toolkit 当前实现 `minimax_h3_image`、UI 配置、加载器和训练文档。

在 2026-11-15 的一次环境记录中，训练器使用 Comfy-Org 的对应重打包图像主模型、Qwen3-VL 视觉文本编码器、VAE 和 [Ostris 训练辅助 adapter](https://huggingface.co/ostris/minimax_h3_training_adapter)。这些是历史版本线索，不是所有未来版本的固定要求；以目标提交的实际加载器和许可为准，核对文件哈希和架构。

当时离线 tokenizer/processor 配置已验证加载，文生图小测试配置已准备，但实际 GPU 小测尚未完成；不要宣称该记录证明 H3 Image LoRA 已训练成功。文生图与参考图编辑的数据接口不同。训练 adapter 和最终产出的用户 LoRA 是不同文件。

## MOSS-Image 编辑

[MOSS-Image-Base](https://modelscope.cn/models/openmoss/MOSS-Image-Base) 的编辑训练需要与当前训练器兼容的视觉编码器、参考图、目标图和指令配对；纯文本编码器不一定可替代视觉分支。依据当前 loader 准备完整配置、预处理组件与离线缓存。

历史本机记录显示，Windows / RTX 4090 D 48GB 环境曾完成 MOSS Base 单图编辑训练及断点恢复，样本数据、分辨率、优化器和训练步数仅对应当时实验。不同显卡、版本、数据集和目标不保证复现，运行前重新校验。
