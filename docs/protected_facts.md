# Protected Facts

Protected Facts are facts that must remain stable during rewriting.

## What Counts as Protected Facts

- Numbers.
- Dates.
- Names.
- Company names.
- Product names.
- Places.
- Prices.
- Contract terms.
- Professional terms.
- Quotes.
- User-stated facts.
- Key claims in high-risk domains.
- Qualifiers and disclaimers.

## Why Protect Them

Humanized rewriting can accidentally change meaning. Protected facts prevent:

- Price drift.
- Date drift.
- Changed product names.
- Removed contract conditions.
- Stronger claims than the source supports.
- Hypothetical examples becoming real cases.

## Extract Before Rewriting

Before rewriting, list protected facts:

```yaml
protected_facts:
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
```

## Check After Rewriting

After rewriting, compare source and output:

```yaml
price:
  source: 199 元
  rewritten: 199 元
  status: unchanged
date:
  source: 2026 年 7 月 1 日至 7 月 7 日
  rewritten: 2026 年 7 月 1 日至 7 月 7 日
  status: unchanged
```

## Example

Source:

```text
星河科技将在 2026 年 7 月 1 日至 7 月 7 日推出 FlowPilot Pro 限时体验活动，体验价为 199 元。
```

Safe rewrite:

```text
星河科技将在 2026 年 7 月 1 日至 7 月 7 日开放 FlowPilot Pro 限时体验，体验价为 199 元。
```

Unsafe rewrite:

```text
星河科技将在 7 月推出 FlowPilot Pro 优惠活动，价格不到 200 元。
```

The unsafe version changes precision and weakens protected facts.

