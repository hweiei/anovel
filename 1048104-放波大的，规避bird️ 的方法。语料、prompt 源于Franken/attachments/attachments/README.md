# frankentexts_prompt_package_BRIEF_PRO

本包为 **“生成语料的提示词模板”**，与《筑心师·Frankentexts 2.2（BRIEF-PRO版）》**完全匹配**。

## 目录结构
- `prompts/main_prompt.txt`：主提示词（2.2 总纲）。
- `prompts/modules/compression_BRIEF_PRO.txt`：BRIEF-PRO 式“压缩片段机制”。
- `prompts/modules/generation_blocks.txt`：块级生成与输出字段模板（与 2.2 对齐）。
- `prompts/modules/roles_and_noise.txt`：oracle/distractor 混合策略。
- `prompts/modules/commands.txt`：交互命令与参数说明。
- `schemas/fragment_schema.json`：片段池（语料）推荐字段。
- `schemas/output_block_schema.json`：生成块输出字段规范。
- `examples/driver_config.yaml`：调用示例（如何设置模式/句数K等）。

## 与 2.2 的一致性要点
- 支持 `/压缩片段 模式=[高|中|低|自动]` 与 **K 句数控制**。
- 支持 **短到长合成（S2L）**。
- 支持 **oracle/distractor** 混入（≤10%）。
- 保留 **复制率≥0.90**、**最小编辑**、**连接词白名单**等硬约束。
- 输出字段（片段清单/复制率自估/一致性自检/是否混入distractor等）完全对齐。

## 使用建议
- 语料推荐包含：`id/source/text/topic/sent_count/role` 字段。
- 若输出复制率 < T：先换片段重拼，再降压缩等级；避免大段自写。
