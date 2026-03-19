---
title: Discord/Twitch/Snapchat age verification bypass
topics: Web Security, JavaScript, Browser DevTools
date: 2026-03-19T11:25:29+08:00
Link: https://age-verifier.kibty.town/
Source: Hacker News
---

背景/问题：主流社交平台（如Discord、Twitch、Snapchat）为遵守法规（如COPPA、GDPR），普遍实施了前端年龄验证机制，通常要求用户输入出生日期或上传身份证件。然而，这些机制大多依赖客户端（浏览器）执行验证逻辑，存在被绕过的固有风险。

核心方案/技术细节：该技术演示站点（https://age-verifier.kibty.town/）揭示了一种通用的前端年龄验证绕过方法。其核心在于利用浏览器开发者工具（DevTools）直接修改前端JavaScript代码或操作DOM元素。具体技术路径通常包括：1）拦截并修改向验证API发送的请求载荷（例如，将出生日期字段篡改为符合要求的日期）；2）直接覆写负责验证的JavaScript函数，使其始终返回“验证通过”状态；3）操作本地存储（如LocalStorage）或Cookie，伪造已验证的会话状态。示例代码可能涉及使用DevTools控制台执行类似 `document.getElementById('birthYear').value = 1990;` 的指令，或通过重写 `fetch` / `XMLHttpRequest` 来篡改提交数据。

价值/影响：此漏洞暴露了仅依赖客户端进行关键安全验证（如年龄门控）的严重设计缺陷。对于平台方，这意味着可能违反数据保护法规，面临法律风险与罚款，并可能导致未成年用户接触不当内容。对于技术社区，此案例强调了任何客户端执行的安全检查都极易被绕过，敏感逻辑（如年龄计算、权限判定）必须由服务端进行不可篡改的最终验证。该演示也促使相关平台重新评估其年龄验证架构，推动向更安全的服务端验证或第三方可信认证服务迁移。