# 结构化资料协议

## 定位

“个人结构化数据库”是可审阅、可纠正、可复用的本地结构化资料，不要求部署数据库服务。首次实现优先使用 JSON 或同等可移植格式。

运行时数据不得保存在已安装 Skill 目录中。用户授权持久化后，优先使用用户指定目录；没有指定时，建议在当前工作区使用 `job-journey-data/`，并在写入前说明路径。

## 个人资料结构

```json
{
  "schemaVersion": "0.1",
  "profile": {
    "currentPosition": "",
    "yearsOfExperience": null,
    "careerGoals": [],
    "preferences": [],
    "constraints": []
  },
  "sources": [],
  "experiences": [],
  "projects": [],
  "capabilities": [],
  "conflicts": [],
  "unknowns": []
}
```

### sources

每项包含：`sourceId`、`sourceType`、`label`、`accessDate`、`extractionStatus`、`notes`。除非用户明确允许，不保存私人链接令牌、完整原文或不必要的绝对路径。

### experiences

每段经历包含：

- `experienceId`
- 机构、岗位、时间范围
- 业务背景和主要对象
- 用户确认的职责
- 关联项目编号
- 来源引用
- 事实状态和可信度

### projects

每个项目包含：

- `projectId`
- 项目背景、目标和用户实际角色
- 具体行动和交付物
- 结果和指标
- 指标的对比基准、统计口径和归因依据
- 支持的能力标签
- 来源引用
- 待确认项

### conflicts and unknowns

冲突项保留各版本原文、来源和影响。未知项记录缺什么以及它会影响哪个判断。不要用推断覆盖冲突或未知。

## 岗位资料结构

岗位档案至少包含：

- `jobId`、公司、岗位、地点和来源；
- 原始JD引用；
- 岗位使命、职责模块和岗位层级；
- 逐项要求及重要性；
- 公司和业务公开事实；
- 风险、待确认项和六维评分。

## 人岗映射结构

每条映射包含：

- `requirementId`
- 岗位要求及重要性
- 关联的 `experienceId` 或 `projectId`
- 匹配状态：直接匹配、可迁移匹配、待补强、关键缺口、待确认
- 证据强度：强、中、弱、无
- 简短依据
- 待补材料或验证问题

## 更新原则

- 个人资料是事实来源，岗位映射只引用相关经历和项目。
- 用户纠正事实后，更新结构化资料；不要篡改原始来源。
- 用户未授权保存时，只在当前任务中维护临时结构。
- 导出报告时默认只包含完成任务所需的脱敏摘要。
