# Protected Facts

Protected Facts 是改写过程中必须保持稳定的信息。

## 包括什么

数字、日期、名称、公司名、产品名、地名、价格、合同条款、专业术语、引用语、用户明确给出的事实、高风险关键结论、限定词和免责声明。

## 为什么要保护

真人化改写可能造成价格漂移、日期漂移、产品名变化、条件丢失、结论强化，或把假设场景写成真实案例。Protected Facts 用来防止这些问题。

## 改写前抽取

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
```

## 改写后核对

```yaml
price:
  source: 199 元
  rewritten: 199 元
  status: unchanged
```

## 示例

安全改写：

```text
星河科技将在 2026 年 7 月 1 日至 7 月 7 日开放 FlowPilot Pro 限时体验，体验价为 199 元。
```

不安全改写：

```text
星河科技将在 7 月推出 FlowPilot Pro 优惠活动，价格不到 200 元。
```

不安全版本模糊了日期和价格，不符合保真要求。
