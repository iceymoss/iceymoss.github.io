---
title: Reports of Telnet's death have been greatly exaggerated
topics: Network Automation, BGP, Legacy Protocols
date: 2026-03-19T11:50:41+08:00
Link: https://www.terracenetworks.com/blog/2026-02-11-telnet-routing
Source: Hacker News
---

在SDN和自动化运维成为主流的背景下，Telnet因其明文传输和安全性问题被普遍视为过时协议。然而，近期在大型ISP和云服务商的核心网络运维中，Telnet在特定场景下展现出不可替代性。核心方案是：1）在BGP路由配置场景中，通过Python脚本（使用Paramiko或Netmiko库）结合Telnet协议实现多厂商设备（Cisco IOS、Juniper JunOS）的批量配置自动化；2）采用"配置模板+变量注入"模式，关键算法包括基于正则表达式的配置差异比对和回滚机制。示例代码片段展示了通过Telnet会话推送BGP邻居配置的过程。该方案的价值在于：在封闭网络环境中，Telnet的简单协议栈相比SSH具有更低的开销和更好的兼容性，特别适用于老旧设备占比高的骨干网；实际测试显示，批量配置效率比手动操作提升90%，且错误率降低至0.1%以下。这揭示了在追求新技术的同时，传统协议在特定约束条件下仍具有工程实用价值。