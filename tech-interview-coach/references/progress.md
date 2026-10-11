# 面试进度

恢复面试、记录回答、完成评价或验证、跳题和查询进度时使用本文件。同一数据目录只维护一场进行中的面试。

## 记录与恢复

`interview-state.json` 使用 `schema_version: 1`、`target_role`、`tech_stack`、`stage`、`current_question`、`history`、`weak_topics`。当前题目保存题目及技术栈/方面/目标深度、有效回答与追问摘要、`initial_assessment`、`current_assessment`、`assessment_revisions`（补充内容摘要、讲解前/后阶段、变化依据）、验证记录、`post_teach_mastery` 和完成状态。回答与反馈只留脱敏摘要，复用已有公司和项目代称；偏题答复不作为有效回答。

阶段使用 `SETUP`、`WAIT_ANSWER`、`WAIT_FOLLOW_UP`、`WAIT_QUESTIONS`、`WAIT_VERIFICATION`、`WAIT_NEXT`。每次有效回答或阶段变化后保存，恢复时接续已记录阶段。在 `WAIT_NEXT` 保留当前题，收到下一题指令后归档为 `COMPLETED`；中途跳题归档为 `SKIPPED` 并记录跳过阶段，未作出的评价和验证保持空值。

## 知识进度

评价、复核或验证后，同步更新 `profile/stacks/` 中核心主题的覆盖、掌握情况和岗位差距，以及 `weak_topics`。首次评价、基于用户补充的复核、讲解后验证分别记录；自评不当作已验证能力，跳过本身不算薄弱点。旧数字评分只保留可核实的文字依据，不直接换算掌握程度。

查询“面试进度”或“薄弱点”时展示现有记录，之后返回原阶段。新提供的项目技术细节需要保存原文时，再按 [简历与背景资料](profile-setup.md) 处理。
