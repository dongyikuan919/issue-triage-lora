# issue-triage-lora · 故障分诊微调实验

验证用小型开源语言模型进行问题分类与字段提取，是否优于更简单的提示或规则方案。

> 状态：仓库已初始化，业务功能尚未实现。以下是目标范围，不能视为已经可用的能力。

## 使用场景

输入报错描述 → 输出类别，以及组件、版本、错误码等可从输入确认的字段 → 对比微调前后的结果。

## 首版计划

- 整理项目二积累的人工审核数据，保留来源及真实/合成标记。
- 按案例来源分组去重，分开训练、验证和冻结的独立测试集。
- 提供 LoRA 训练、保存、加载、推理和评测流程。
- 同条件比较规则、同一基础模型加提示、微调模型，报告 Macro-F1、字段匹配率和 JSON 合法率。
- 记录候选模型、环境、配置、延迟和成本；效果合格后再反馈接入项目二。

## 项目衔接

使用项目二的审核数据；同时提供可公开的小样例，支持独立复现实验。微调结果只有在评测合格时才作为项目二的可选组件。

- [devdocs-rag](https://github.com/dongyikuan919/devdocs-rag)：开发文档问答库。
- [issue-triage-agent](https://github.com/dongyikuan919/issue-triage-agent)：问题分诊助手。
- [issue-triage-lora](https://github.com/dongyikuan919/issue-triage-lora)：故障分诊微调实验。

## 开发路线

项目三 · 第 13～18 周；学习计划每周投入 8 小时：学习 2 小时、实现 4 小时、评测 1 小时、文档与提交 1 小时。

具体周计划见 [阶段路线图](docs/ROADMAP.md)。采用 Python 主线，实际依赖和运行命令在首个可运行版本中补充。

## 当前范围

只做有限类别的分类与字段提取；不从零预训练、不训练通用排障模型。训练硬件、预算和基础模型待进入该阶段时确定，微调不承诺提升。

## 数据与配置

仅提交自写或许可允许公开的样例。API 密钥、真实私人日志和未经授权的数据不入库；配置方案确定后提供 `.env.example`。

## 学习资料

[Hugging Face PEFT](https://huggingface.co/docs/peft/en/quicktour) · [TRL SFT Trainer](https://huggingface.co/docs/trl/en/sft_trainer)

## 许可证

自有代码采用 [MIT License](LICENSE)。第三方文档、数据、基础模型及权重分别遵循其原始许可，不能由本仓库的 MIT 许可证替代。
