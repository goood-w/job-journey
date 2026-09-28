---
name: job-journey
description: Use this skill whenever a user is job hunting or mentions career positioning, job discovery, JD or company analysis, person-role fit, resume tailoring, applications, interview preparation or review, Offer comparison, compensation negotiation, or onboarding. It orchestrates the full eight-stage journey while allowing any single stage to run independently.
---

# 求职全程

## Overview

把一次求职视为由八个可独立调用、可相互衔接的阶段组成的过程。先识别用户的主任务，再补齐完成主任务所必需的前置分析；不要强迫用户从第一阶段开始，也不要擅自执行无关的后续阶段。

核心原则：以证据为基础，缺少材料时继续完成不依赖该材料的部分；不能确认的内容保持待确定，不用猜测填满报告。

## When to Use

适用于以下请求：

- 明确求职方向、转岗路径、职级或涨薪目标；
- 汇总、筛选、比较 PDF、Word、Excel、截图、文本或链接中的岗位；
- 分析公司、JD、岗位价值、层级、薪酬、成长性和风险；
- 从简历、博客、作品集等材料建立个人结构化资料，并逐项映射岗位要求；
- 定制简历、投递消息、自我介绍和面试准备；
- 复盘面试逐字稿、准备复试；
- 比较 Offer、谈薪或制定入职后的 30/60/90 天计划。

不适用于：纯招聘方人才盘点、替企业批量筛选候选人、无求职语境的通用公司研究，以及需要持牌专业人士确认的法律、税务或投资结论。

## Stage Router

| 用户主任务 | 阶段 | 必读参考 |
|---|---:|---|
| 明确求职方向、目标岗位、筛选条件 | 1 | `references/stage-01-positioning.md` |
| 汇总岗位、建立岗位池、初筛 | 2 | `references/stage-02-job-discovery.md` |
| 分析公司、岗位、JD、风险 | 3 | `references/stage-03-role-company-analysis.md` |
| 判断个人是否匹配、建立个人材料库、逐项映射 | 4 | `references/stage-04-person-role-mapping.md` |
| 修改简历、准备投递材料 | 5 | `references/stage-05-resume-application.md` |
| 准备面试、自我介绍、模拟面试 | 6 | `references/stage-06-interview-prep.md` |
| 复盘面试、准备复试 | 7 | `references/stage-07-interview-review.md` |
| 比较 Offer、谈薪、入职准备 | 8 | `references/stage-08-offer-onboarding.md` |

用户明确指定阶段时按用户指定执行。用户未指定时，根据意图和现有材料自动识别。无法可靠识别时，只询问完成主任务所需的最少信息。

## Execution Protocol

1. 用一句话确认主任务和当前阶段。
2. 盘点用户已经提供的材料、格式、可访问性和明显缺口。
3. 涉及文件、截图、表格或链接时，先读 `references/material-ingestion.md`。
4. 只读取当前阶段参考文件以及必要的前置阶段参考文件。
5. 执行主任务；只自动补齐必要前置分析，不自动延伸到无关后续阶段。
6. 按 `references/evidence-confidence.md` 区分事实、公开信息、推断、冲突和待确认项。
7. 涉及岗位评价时，按 `references/scoring.md` 使用统一六维评分。
8. 按 `references/output-contract.md` 输出结论、风险、评分、依据、缺口和下一步。

## Main Task and Prerequisite Rules

- 阶段 2 可以在没有个人资料时执行；此时完成岗位侧初筛，不生成个人匹配和综合总分。
- 阶段 3 不依赖个人资料。缺少公司信息时进入 JD-only 模式。
- 阶段 4 是核心模块。详细映射前，先从用户授权的个人材料建立或更新结构化个人资料。
- 阶段 5 自动补齐阶段 3 和阶段 4 中与简历定制直接相关的部分。
- 阶段 6 至少补齐岗位分析；有个人资料时再调用人岗映射生成个性化回答。
- 阶段 7 以实际面试记录为主，只补齐理解问题所需的岗位背景和个人证据。
- 阶段 8 以 Offer 或入职任务为主；没有个人资料时仍可分析条款和岗位风险，但不显示综合总分。

不要为了“完整”而每次运行八个阶段。

## Material Intake

接受以下输入：

- PDF：岗位 JD、简历、Offer、面试记录；
- Word：`.docx` 或可读取的文字文档；
- Excel：岗位汇总表、多岗位清单、薪酬对比表；
- 图片或截图：招聘页面、JD、聊天记录、Offer 页面；
- 链接：招聘页、公司官网、个人简历页、博客、作品集；
- 纯文本：粘贴的 JD、经历、面试问题、逐字稿和沟通记录。

对扫描件和截图使用 OCR 时，保留不可辨认字段并要求用户确认影响结论的内容。对链接记录访问日期；页面无法访问时，请用户粘贴正文或导出文件。不要把私人链接、带令牌的链接或个人信息转发给无关服务。

## Personal Evidence Database

当用户要求人岗匹配、定制简历或建立个人材料库时：

1. 读取 `references/data-contract.md`。
2. 从简历、博客、作品集和用户补充说明中提取工作经历、项目、职责、行动、成果、指标、能力和来源。
3. 合并明显重复的信息，但保留来源引用。
4. 不静默解决日期、职级、职责或成果冲突；把冲突列入待确认清单。
5. “明显提升”“效果很好”等只能作为定性陈述，不能改写为具体百分比。
6. 只有用户明确表示要建立或更新个人材料库时，才将结构化资料持久化到本地；首次保存前说明保存路径和内容范围。
7. 默认不复制原始简历、逐字稿或完整网页到数据库。用户不同意保存时，在当前会话内使用临时结构化结果继续任务。

个人材料总库可以包含多段经历。同一段真实经历可以针对不同岗位突出不同能力，但不得改变事实、夸大职责或虚构数据。

## Missing Material Behavior

- 缺少个人资料：个人匹配标记“待确定”，其他岗位侧分析继续，不显示综合总分。
- 缺少公司名称或公开资料：执行 JD-only 分析并降低相关结论可信度。
- 缺少薪资结构：薪酬与整体回报标记“待确定”，不把缺失当作低分。
- 缺少完整面试逐字稿：基于现有笔记复盘，并说明可能遗漏问题。
- 缺少完成主任务不可替代的材料：只请求该项，不一次索取全部八阶段材料。

## Scoring and Major Risks

所有岗位评价维度均为 0—100 分，分数越高越好，并同时展示高、中、低可信度和一句判断。不要自行增加会与六维总分混淆的评分维度。

只有六个维度都有有效得分时才显示综合总分。缺少个人资料时一定不显示综合总分，也不重新分配权重。

重大风险不构成自动淘汰，但必须：

1. 放在最终结论最前面；
2. 说明属于已确认风险、高风险推断还是待验证线索；
3. 在综合总分旁增加风险标记；
4. 给出具体核实问题。

## Evidence and Claims

关键判断必须标记为以下一种：

- 用户确认事实；
- 公开事实；
- 合理推断；
- 待确认事项；
- 冲突信息。

公开信息要给出直接来源和访问日期。不要把JD潜台词、面试官意图、录用概率、公司内部状态或下一轮题目写成确定事实。给出简洁的判断依据，不输出冗长的隐藏思维过程。

## Privacy

执行前读取 `references/privacy.md`。默认采用本地优先和最小化保存：

- 不把简历原文、手机号、邮箱、身份证号、详细住址、精确薪资或面试逐字稿放入公开搜索请求；
- 未经授权不保存原始敏感材料，不创建公开链接，不上传第三方存储；
- 结构化资料和报告保存在用户选择的工作区，不写入已安装 Skill 目录；
- 用户要求删除、纠正或导出时，对明确目标执行并说明结果。

## Output

默认输出顺序：

1. 重大风险提醒（存在时）；
2. 当前主任务与执行范围；
3. 主任务结果；
4. 适用的单项评分、可信度和一句判断；
5. 事实依据、来源和限制；
6. 待确认材料或问题；
7. 不超过五项的下一步建议。

不要默认创建页面、Dashboard、公开链接或多页产品。用户明确要求本地报告时，才生成脱敏的本地文件。

## Reference Index

- 材料提取：`references/material-ingestion.md`
- 数据结构：`references/data-contract.md`
- 评分：`references/scoring.md`
- 证据与可信度：`references/evidence-confidence.md`
- 隐私：`references/privacy.md`
- 输出：`references/output-contract.md`
- 面试题与评价方法：`references/interview-framework.md`
- 八阶段方法：读取上方 Stage Router 中与当前任务对应的阶段参考文件。

## Common Mistakes

- 因为没有简历就停止公司和岗位分析；
- 把缺失项按 0 分计入总分；
- 从文件中没找到某项经历就断言用户不会；
- 把多个简历版本的冲突静默合并；
- 根据岗位标题而不是实际职责判断岗位类型；
- 将静态题库宣称为某公司的历史真题；
- 为了“完整”自动生成用户未要求的简历、面试题或入职计划；
- 用看似精确的分数掩盖低可信度和重大风险。
