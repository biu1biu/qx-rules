# 红果短剧 去广告 · Quantumult X 规则

一刀切屏蔽红果短剧（番茄系，走字节穿山甲 Pangle 广告 SDK）的插屏/激励视频广告。
**插屏 8 秒广告 + 看广告解锁会一起消失**（不保留奖励解锁）。

## 用法

QX → 「资源」→「分流(Filter)」→ 添加远程资源，填入本仓库 `hongguo-adblock.list` 的 raw 链接：

```
https://raw.githubusercontent.com/biu1biu/qx-rules/main/hongguo-adblock.list
```

`reject` 类规则走分流层拦截，**无需**加入 MITM 解密。

## 安全边界

- **不拦截**正片视频流：`vas-lf-x.snssdk.com` / `*.douyincdn.com` / `*.fqnovelpic.com`
- **不拦截**设备风控：`security.snssdk.com`（封了会登录报错/弹验证码）

## 说明

规则基于「番茄/红果系通用走穿山甲后端」这一已知架构编写。若装上后广告仍在弹，
请在广告弹出瞬间用 QX 抓一份 HAR（MITM hostname 先加 `*.pangolin-sdk-toutiao.com,
*.snssdk.com, *.pglstatp-toutiao.com`），据此补齐漏网广告子域。
