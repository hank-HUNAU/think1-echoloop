# think1-echoloop

TH!NK 1（THiNK 1 A2）听读训练站 · 数据底座与站点仓库。

> 移植自 nce2-echoloop 的四阶段听读体系：**盲听 → 跟读 → 精听 → 复述**（顺序定案 2026-10-22，依据见 `06 新概念英语/顺序变更论证_2026-10-22.md`）。

## 项目定位

- **教材**：THiNK 1 A2（第二版），Welcome Unit + Unit 1–12
- **资产空间**：`E:\04 少儿原版课程\04 综合课程 THINK_1_A2\`（在教项目，音频/PDF/测试卷正典在此空间，本仓库只放生成物）
- **数据底座工具**：`04 综合课程 THINK_1_A2\听读数据底座\_work\`（盘点/Audioscript 解析/归类脚本）

## 数据底座（第 0 期，2026-10-23 完成第一交付物）

| 文件 | 内容 |
|---|---|
| `data/tracks/曲目归类_全量.json` | 236 唯一曲目全量归类（分类/粒度/处理方法/正本路径/时长） |
| `data/tracks/曲目归类总表.md` | 人读版总表：盘点结论、分类规则、E1–E4 明细、验收对照 |
| `data/tracks/_曲目盘点_全量.json` | 509 文件盘点原始记录（副本鉴定/正本选取留痕） |
| `data/audioscript/_audioscript_parsed.json` | 教师用书 Audioscript 结构化（13 单元 / 27 曲目 / 506 话语） |
| `data/audioscript/_audioscript_raw.txt` | Audioscript 三栏版面重提取原文（p135–142） |

**分类概览**：E1 正课文有稿 27（句级）· E2 正课文无稿长音频 46（ASR 句级）· E3 文学有文本 16（句级）· E4 文学无文本 8（ASR 句级）· A_SB 短活动 39（曲目级）· A WB/测试 96（曲目级）· T 教师自制 4。句级队列合计 97 条。

**音频**：236 正本共约 509MB（含 24 个文学有声章节），暂不入库；第 1 期建站时按 echoloop 先例压缩（64k 单声道）后按需入 `audio/`。

## 路线图（0–3 期）

| 期 | 内容 | 状态 |
|---|---|---|
| 0 数据底座 | 曲目归类表 ✅ · Audioscript ✅ · 句级对齐（E1 27 条先行）· 词表挂接 | 进行中 |
| 1 盲听+精听 | 曲目级播放 · 模糊字幕 · 预测问题 · 句卡 | 未开始 |
| 2 跟读 | 循环×N · 录音 A/B · STT 降级自评 | 未开始 |
| 3 复述+听写 | 复述台 · 听写（dictation 文献补审后）· 7 轮复习 | 未开始 |

## 推送与版本基线

- **优先 `git push` 直连**（2026-10-23 实测可用；若代理拦截 github.com TLS 则回落 `node _push_one.js` 走 Git Data API）
- API 路径注意：提交日期规范为 UTC → **远端 sha 与本地不同（内容一致）**；对齐：`git fetch origin && git reset --hard origin/main`
- 基线查询：`gh api repos/hank-HUNAU/think1-echoloop/commits/main --jq .sha`；回滚=API PATCH `refs/heads/main`
- 已知坑：空仓库用 API 建 blob 会 409（Git Repository is empty）——首次提交必须用直连 git push 播种

## 版权

音频与教材内容仅限个人学习使用（同 echoloop 口径）。
