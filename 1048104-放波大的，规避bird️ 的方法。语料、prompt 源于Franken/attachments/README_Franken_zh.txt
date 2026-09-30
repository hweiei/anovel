Frankentexts 中文片段池（规范化版）README
=======================================
包含内容：
- normalized_<pool>_zh.jsonl  ：各来源清洗切分+去重后的片段
- normalized_all_pools_zh.jsonl：合并去重后的总库
- chapterpack_1500_zh.jsonl    ：单章候选池（约 1500 段）

字段说明：id｜pool_id｜file｜idx｜text｜char_len｜open12｜source｜hash
建议：把 chapterpack_1500_zh.jsonl 上传到 Gem“知识”，再用你配置的 Frankentexts 指令写章。

我默认禁用大量检索带来的“自写增多”问题；这些 JSONL 是纯片段库，非常适合你指令里的“随机/批量采样 + 规则初筛”。
个别超长句我做了“温和截断”，不影响“逐字拷贝”判定。
如果你想要按体裁/角色/题材再细分多个章节包，我也可以马上基于这份全量库再切一版（例如“都市职场包”“仙侠修真包”等）。