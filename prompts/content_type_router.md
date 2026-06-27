# content_type 路由 Prompt

## 用途

判断原文的主要 `content_type`，并给出对应改写重点。

## 路由规则

只选择一个主要类型。文本可归入多个类型时，以最终发布或使用场景为准。

## 类型规则

| content_type | 判断特征 | 改写重点 |
| --- | --- | --- |
| `article` | 多段论述、观点展开、解释或长文 | 优化开头、段落推进、逻辑和结尾 |
| `social_note` | 小红书/社交笔记，强调经验感和扫读 | 短段落、具体、自然、不伪造体验 |
| `short_video_script` | 口播、短视频、直播脚本 | 短句、停顿、前三秒钩子、好朗读 |
| `sales_copy` | 产品/服务/课程/咨询推广 | 明确适合谁、价值和边界，不承诺结果 |
| `title` | 标题、主题行、视频标题 | 清楚、准确、有吸引力，不误导 |
| `caption` | 图片/视频/社交配文 | 简短、贴合场景，不强行升华 |
| `comment_reply` | 评论、评价、异议、互动回复 | 相关、自然、友好、有边界 |
| `private_message` | 私信、私域、跟进、邀约 | 意图清楚，语气自然，不过度压迫 |
| `email` | 邮件、商务沟通 | 礼貌、结构清楚、行动明确 |
| `resume` | 简历、求职信、项目经历 | 真实、具体、岗位相关，不编成果 |
| `business_doc` | 汇报、方案、纪要、SOP | 精准、克制、可决策 |
| `knowledge_explanation` | 知识解释、教程、科普 | 准确、易懂、逻辑清楚 |
| `generic_text` | 无明确类型 | 保留原意，提升自然度和可读性 |

## 输出

```yaml
content_type_result:
  content_type: ""
  confidence: high|medium|low
  judgment_features: []
  rewrite_priorities: []
```
