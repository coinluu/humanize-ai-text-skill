# Protected Facts 保真示例

## 场景

原文包含价格、日期、产品名、公司名等事实。改写后必须完全一致，并展示 Protected Facts 抽取和核对。

## 输入信息

```yaml
mode: platform_humanize
platform: private_domain
content_type: private_message
rewrite_intensity: Level 1
output_mode: full
allow_hypothetical_scenarios: false
```

## 改写前

```text
星河科技将在 2026 年 7 月 1 日至 7 月 7 日推出 FlowPilot Pro 限时体验活动，体验价为 199 元。活动仅面向已完成企业认证的新用户，每家公司限购 1 次。具体服务内容以合同条款为准。
```

## Protected Facts 抽取

```yaml
company_name:
  - 星河科技
product_name:
  - FlowPilot Pro
date:
  - 2026 年 7 月 1 日至 7 月 7 日
price:
  - 199 元
conditions:
  - 仅面向已完成企业认证的新用户
  - 每家公司限购 1 次
contract_terms:
  - 具体服务内容以合同条款为准
```

## AI 感诊断

- 原文信息准确，但语气偏公告，私域沟通中略显生硬。
- 句子信息密度较高，用户需要多读一遍才能抓住重点。
- 活动条件和合同限定需要保留，不能为了自然化删掉。

## 改写策略

- 保留所有价格、日期、产品名、公司名和限制条件。
- 改成更适合私域通知的自然语气。
- 不新增优惠、名额、效果或服务承诺。
- 把关键信息拆开，方便阅读。

## 改写后

```text
给你同步一个 FlowPilot Pro 的限时体验活动。

星河科技将在 2026 年 7 月 1 日至 7 月 7 日开放体验，体验价为 199 元。

这次活动仅面向已完成企业认证的新用户，每家公司限购 1 次。具体服务内容仍以合同条款为准。
```

## Protected Facts 核对

```yaml
company_name:
  source: 星河科技
  after: 星河科技
  status: unchanged
product_name:
  source: FlowPilot Pro
  after: FlowPilot Pro
  status: unchanged
date:
  source: 2026 年 7 月 1 日至 7 月 7 日
  after: 2026 年 7 月 1 日至 7 月 7 日
  status: unchanged
price:
  source: 199 元
  after: 199 元
  status: unchanged
conditions:
  source:
    - 仅面向已完成企业认证的新用户
    - 每家公司限购 1 次
  after:
    - 仅面向已完成企业认证的新用户
    - 每家公司限购 1 次
  status: unchanged
contract_terms:
  source: 具体服务内容以合同条款为准
  after: 具体服务内容仍以合同条款为准
  status: meaning_preserved
```

## 修改说明

- 将公告式长句拆成私域通知式短段。
- 保留活动时间、价格、产品名、公司名和限制条件。
- 没有加入额外优惠、名额、承诺或客户案例。
- "仍以合同条款为准"保留了原有限定含义。

## 风险提示

该内容涉及价格、活动时间和合同条款，属于需要保护的事实信息。改写时必须逐项核对，不得模糊化或强化承诺。

