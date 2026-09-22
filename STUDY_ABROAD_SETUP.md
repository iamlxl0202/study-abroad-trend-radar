# 留学行业 TrendRadar 配置说明

本仓库基于 [sansan0/TrendRadar](https://github.com/sansan0/TrendRadar)，用于国内平台与公开 RSS 中的留学行业热点监测。

## 已配置范围

- 国内平台：今日头条、百度热搜、澎湃新闻、B站、微博、抖音、知乎。
- 重点地区：香港、澳门、新加坡、英国、美国、澳洲、加拿大及欧洲、亚洲其他目的地。
- 重点议题：申请与录取节点、签证政策、语言考试、国际课程、排名与专业、中外合作办学、就业费用与安全。
- RSS：6组 Bing News 中文检索源，文章新鲜度为7天。
- 筛选方式：关键词模式，不需要 AI 密钥。
- 报告模式：增量，只突出新出现的匹配信息。

## 自动运行

GitHub Actions 每天按北京时间运行4次：

- 08:17
- 12:17
- 16:17
- 20:17

每次成功运行会上传一个保留30天的 Actions Artifact，包含：

- `index.html`
- `output/`

路径：仓库顶部 **Actions** → **Get Hot News** → 选择运行记录 → **Artifacts**。

## 关键配置文件

- `config/frequency_words.txt`：行业关键词及排除词。
- `config/ai_interests.txt`：未来启用AI筛选时使用的兴趣描述与真实性要求。
- `config/config.yaml`：数据源、RSS、报告模式和展示设置。
- `.github/workflows/crawler.yml`：自动运行时间与报告归档。

## 当前无需配置的密钥

基础抓取、关键词筛选和Artifact归档不需要密钥。

如后续需要AI分析或消息推送，再在仓库 **Settings → Secrets and variables → Actions** 添加对应密钥。不要把密钥直接写入配置文件。

## 内容使用原则

热榜和搜索RSS只作为选题信号。签证、申请、录取、考试、排名与政策内容发布前，必须回到政府、法院、考试机构或院校原文核实发布日期、适用对象、生效时间与统计口径。
