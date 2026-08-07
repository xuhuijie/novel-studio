# 英文残留扫描指南

## 为什么需要

AI 生成中文小说时，常将英文单词混入对话或叙述中（如 `recent`、`single-handedly`、`yours`、`design`、`risky` 等），破坏阅读体验。

## 扫描方法

在 chapters/ 目录下用 search_files 搜索常见英文残留：

```
pattern: recent|single-handedly|yours|design|risky|agent|system|plot|scene
path: /home/agent/.hermes/novels/{小说名}/chapters/
output_mode: content
```

注意排除检验报告段落中的英文（检验报告本身可能用英文术语如 `[因果链]`、`[人物一致性]`，这些不需要修改）。

## 常见混入场景

| 英文词 | 正确中文 | 出现位置 |
|--------|----------|----------|
| recent | 最近 | 对话/叙述 |
| single-handedly | 一个人/独自 | 对话 |
| yours | 你这 | 对话 |
| design | 设计 | 叙述/检验报告 |
| risky | risky/冒险 | 对话 |
| agent | 代理人/角色 | 对话 |

## 修复原则

1. 只替换英文单词，保留上下文标点
2. 对话中的英文替换后检查对话流畅度
3. 检验报告中的英文术语（如 `[因果链]`）不需要修改
4. 修复后更新检验报告的"状态"字段
