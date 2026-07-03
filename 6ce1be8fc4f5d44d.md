# WAP.BLOG.OCCZL.CN Article Index Gateway

WAP.BLOG.OCCZL.CN Article Index Gateway 是一个面向移动端的技术文章索引与导航系统，专为批量采集、归档和检索 wap.blog.occzl.cn 域名下的历史技术文章而设计。该项目解决了分散的技术博文难以集中管理和快速定位的问题，适用于个人开发者、技术团队以及内容聚合平台作为技术知识库的外链统一入口。

本项目作为第 30/56 批资源整合节点，共计收录 180 个原始文章链接。通过结构化的目录树和分类索引机制，用户无需逐一记忆冗长的 Article 详情页 URL，即可在本地环境中完成对目标文章的快速引用、批处理分析以及元数据提取。项目核心定位为纯外链汇总与索引层，不直接存储文章正文内容，仅维护稳定的定位符映射关系。

## 功能概览

**批量链接导入**：支持通过标准输入或 CSV 文件批量导入形如 http://wap.blog.occzl.cn/Article/details/{id}.sHtML 格式的原始链接，自动解析文章数字标识符。

**分类索引生成**：根据文章 ID 的数值区间或来源批次，自动将链接归类至不同的虚拟目录节点，生成层级清晰的索引目录树。

**去重与校验**：内置链接去重算法，自动剔除重复条目；同时提供 HTTP 头探测功能，校验目标文章的可访问性并标记失效链接。

**结构化输出**：支持将索引结果导出为 JSON、YAML 或纯文本目录树格式，便于与其他文档生成工具或静态站点生成器集成。

**筛选与检索**：提供基于文章 ID 范围、导入批次、文件扩展名（.sHtML）的过滤查询接口，支持正则表达式匹配。

**元数据占位管理**：为每个链接预留标题、摘要、关键词等元数据字段，用户可通过外部数据源或手动补录方式填充，形成完整的知识卡片。

## 应用场景

**个人技术博客归档**：开发者可将自己分散在 wap.blog.occzl.cn 上的历史发布文章统一收录至本地索引库，配合脚本实现按年份、标签的自动化归档，避免因平台改版或链接变动导致的内容丢失。

**团队知识库迁移辅助**：在将外部技术文章批量迁移至内部 Confluence 或 Notion 等知识管理系统时，使用本项目作为前置的链接采集与清洗工具，输出标准化的 URL 列表供迁移脚本调用。

**数据分析与爬虫预处理**：数据工程师可利用本项目的批量导入和校验功能，快速构建待爬取 URL 队列，配合分布式爬虫框架对特定批次（如第 30/56 批）的文章进行并发抓取和内容分析。

**运维监控与链接巡检**：站点运维人员可定期运行本项目的链接状态检查模块，自动生成失链报告，及时发现 wap.blog.occzl.cn 域名下返回 404 或 500 状态的异常文章页面。

## 快速开始

以下步骤引导您在本地环境完成项目的克隆、安装与初次运行。

```bash
# 1. 克隆仓库
git clone https://github.com/example/wap-blog-occzl-gateway.git
cd wap-blog-occzl-gateway

# 2. 安装依赖（基于 Python 3.10+）
pip install -r requirements.txt

# 3. 运行索引构建脚本，导入默认批次链接列表
python build_index.py --batch 30 --input ./data/raw_links_30.txt --output ./output/index_30.json
```

## 安装要求

| 依赖 | 必需 | 说明 |
|---|---|---|
| Python 3.10 及以上 | 是 | 核心运行环境，用于脚本解析和异步 HTTP 请求 |
| pip 22.0 及以上 | 是 | Python 包管理工具，用于安装 requirements.txt 中的依赖 |
| requests 2.28.0 | 是 | 发送 HTTP 请求以校验链接可用性 |
| pyyaml 6.0 | 是 | 将索引结果序列化为 YAML 格式输出 |
| tqdm 4.64.0 | 否 | 提供批量导入时的进度条显示，提升交互体验 |
| pytest 7.2.0 | 否 | 仅开发测试阶段需要，用于单元测试和集成测试 |
| flake8 6.0.0 | 否 | 代码风格检查工具，贡献代码前需通过 lint 检查 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user_guide.md | 如何导入链接、生成索引、导出不同格式的输出文件 |
| 开发者指南 | docs/developer_guide.md | 索引模块的类图设计、插件扩展机制以及单元测试编写规范 |
| API 参考 | docs/api_reference.md | 对外提供的核心函数签名、参数说明及返回数据结构定义 |
| 运维部署 | docs/deployment.md | 如何将本工具集成至 CI/CD 流水线，以及定时巡检任务的配置方法 |

## 资源列表

本批次（第 30/56 批）收录的全部原始文章链接如下，按文章 ID 数值升序排列。所有链接严格保留用户提供的原始格式，未做任何协议补全、域名标准化或路径改写。

核心技术文章资源

http://wap.blog.occzl.cn/Article/details/0415.sHtML
http://wap.blog.occzl.cn/Article/details/04638.sHtML
http://wap.blog.occzl.cn/Article/details/04865.sHtML
http://wap.blog.occzl.cn/Article/details/0513.sHtML
http://wap.blog.occzl.cn/Article/details/053814.sHtML
http://wap.blog.occzl.cn/Article/details/05383.sHtML
http://wap.blog.occzl.cn/Article/details/0064164.sHtML
http://wap.blog.occzl.cn/Article/details/00756.sHtML
http://wap.blog.occzl.cn/Article/details/01391.sHtML
http://wap.blog.occzl.cn/Article/details/019549.sHtML
http://wap.blog.occzl.cn/Article/details/0239109.sHtML
http://wap.blog.occzl.cn/Article/details/0254787.sHtML
http://wap.blog.occzl.cn/Article/details/026695.sHtML
http://wap.blog.occzl.cn/Article/details/0290266.sHtML
http://wap.blog.occzl.cn/Article/details/031606.sHtML
http://wap.blog.occzl.cn/Article/details/0347871.sHtML
http://wap.blog.occzl.cn/Article/details/0456265.sHtML
http://wap.blog.occzl.cn/Article/details/0016035.sHtML
http://wap.blog.occzl.cn/Article/details/076610.sHtML
http://wap.blog.occzl.cn/Article/details/07936.sHtML

批量导入来源列表

http://wap.blog.occzl.cn/Article/details/0944.sHtML
http://wap.blog.occzl.cn/Article/details/1033305.sHtML
http://wap.blog.occzl.cn/Article/details/11523.sHtML
http://wap.blog.occzl.cn/Article/details/119657.sHtML
http://wap.blog.occzl.cn/Article/details/1222.sHtML
http://wap.blog.occzl.cn/Article/details/1223509.sHtML
http://wap.blog.occzl.cn/Article/details/1343939.sHtML
http://wap.blog.occzl.cn/Article/details/1413.sHtML
http://wap.blog.occzl.cn/Article/details/1467484.sHtML
http://wap.blog.occzl.cn/Article/details/157353.sHtML
http://wap.blog.occzl.cn/Article/details/16342.sHtML
http://wap.blog.occzl.cn/Article/details/1660462.sHtML
http://wap.blog.occzl.cn/Article/details/1689425.sHtML
http://wap.blog.occzl.cn/Article/details/1698394.sHtML
http://wap.blog.occzl.cn/Article/details/17500.sHtML
http://wap.blog.occzl.cn/Article/details/17581.sHtML
http://wap.blog.occzl.cn/Article/details/183349.sHtML
http://wap.blog.occzl.cn/Article/details/191804.sHtML
http://wap.blog.occzl.cn/Article/details/1945409.sHtML
http://wap.blog.occzl.cn/Article/details/196335.sHtML

移动端适配文章归档

http://wap.blog.occzl.cn/Article/details/2303.sHtML
http://wap.blog.occzl.cn/Article/details/2310.sHtML
http://wap.blog.occzl.cn/Article/details/2434.sHtML
http://wap.blog.occzl.cn/Article/details/243829.sHtML
http://wap.blog.occzl.cn/Article/details/244604.sHtML
http://wap.blog.occzl.cn/Article/details/2447.sHtML
http://wap.blog.occzl.cn/Article/details/250712.sHtML
http://wap.blog.occzl.cn/Article/details/26585.sHtML
http://wap.blog.occzl.cn/Article/details/2778.sHtML
http://wap.blog.occzl.cn/Article/details/2876538.sHtML
http://wap.blog.occzl.cn/Article/details/289691.sHtML
http://wap.blog.occzl.cn/Article/details/293057.sHtML
http://wap.blog.occzl.cn/Article/details/302268.sHtML
http://wap.blog.occzl.cn/Article/details/314837.sHtML
http://wap.blog.occzl.cn/Article/details/33364.sHtML
http://wap.blog.occzl.cn/Article/details/340220.sHtML
http://wap.blog.occzl.cn/Article/details/345303.sHtML
http://wap.blog.occzl.cn/Article/details/34614.sHtML
http://wap.blog.occzl.cn/Article/details/3547236.sHtML
http://wap.blog.occzl.cn/Article/details/3623164.sHtML

后端技术专题链接

http://wap.blog.occzl.cn/Article/details/36620.sHtML
http://wap.blog.occzl.cn/Article/details/3673.sHtML
http://wap.blog.occzl.cn/Article/details/3800666.sHtML
http://wap.blog.occzl.cn/Article/details/38099.sHtML
http://wap.blog.occzl.cn/Article/details/3935.sHtML
http://wap.blog.occzl.cn/Article/details/4105255.sHtML
http://wap.blog.occzl.cn/Article/details/4147.sHtML
http://wap.blog.occzl.cn/Article/details/41478.sHtML
http://wap.blog.occzl.cn/Article/details/4154.sHtML
http://wap.blog.occzl.cn/Article/details/42118.sHtML
http://wap.blog.occzl.cn/Article/details/42729.sHtML
http://wap.blog.occzl.cn/Article/details/442567.sHtML
http://wap.blog.occzl.cn/Article/details/4427858.sHtML
http://wap.blog.occzl.cn/Article/details/44558.sHtML
http://wap.blog.occzl.cn/Article/details/4486007.sHtML
http://wap.blog.occzl.cn/Article/details/452315.sHtML
http://wap.blog.occzl.cn/Article/details/46352.sHtML
http://wap.blog.occzl.cn/Article/details/47550.sHtML
http://wap.blog.occzl.cn/Article/details/4803.sHtML
http://wap.blog.occzl.cn/Article/details/4868849.sHtML

前端与客户端资源

http://wap.blog.occzl.cn/Article/details/4983.sHtML
http://wap.blog.occzl.cn/Article/details/499713.sHtML
http://wap.blog.occzl.cn/Article/details/500877.sHtML
http://wap.blog.occzl.cn/Article/details/51097.sHtML
http://wap.blog.occzl.cn/Article/details/5119336.sHtML
http://wap.blog.occzl.cn/Article/details/5134592.sHtML
http://wap.blog.occzl.cn/Article/details/52567.sHtML
http://wap.blog.occzl.cn/Article/details/544741.sHtML
http://wap.blog.occzl.cn/Article/details/55368.sHtML
http://wap.blog.occzl.cn/Article/details/554577.sHtML
http://wap.blog.occzl.cn/Article/details/5662.sHtML
http://wap.blog.occzl.cn/Article/details/57536.sHtML
http://wap.blog.occzl.cn/Article/details/5798336.sHtML
http://wap.blog.occzl.cn/Article/details/5835.sHtML
http://wap.blog.occzl.cn/Article/details/5840.sHtML
http://wap.blog.occzl.cn/Article/details/5853.sHtML
http://wap.blog.occzl.cn/Article/details/5925.sHtML
http://wap.blog.occzl.cn/Article/details/60247.sHtML
http://wap.blog.occzl.cn/Article/details/6073429.sHtML
http://wap.blog.occzl.cn/Article/details/608268.sHtML

运维与基础设施专题

http://wap.blog.occzl.cn/Article/details/6105.sHtML
http://wap.blog.occzl.cn/Article/details/6237.sHtML
http://wap.blog.occzl.cn/Article/details/6240.sHtML
http://wap.blog.occzl.cn/Article/details/6279717.sHtML
http://wap.blog.occzl.cn/Article/details/63783.sHtML
http://wap.blog.occzl.cn/Article/details/6397344.sHtML
http://wap.blog.occzl.cn/Article/details/6414.sHtML
http://wap.blog.occzl.cn/Article/details/6500076.sHtML
http://wap.blog.occzl.cn/Article/details/65160.sHtML
http://wap.blog.occzl.cn/Article/details/6591.sHtML
http://wap.blog.occzl.cn/Article/details/6616.sHtML
http://wap.blog.occzl.cn/Article/details/663100.sHtML
http://wap.blog.occzl.cn/Article/details/66435.sHtML
http://wap.blog.occzl.cn/Article/details/67004.sHtML
http://wap.blog.occzl.cn/Article/details/6705.sHtML
http://wap.blog.occzl.cn/Article/details/6719259.sHtML
http://wap.blog.occzl.cn/Article/details/678390.sHtML
http://wap.blog.occzl.cn/Article/details/6803661.sHtML
http://wap.blog.occzl.cn/Article/details/6823.sHtML
http://wap.blog.occzl.cn/Article/details/686847.sHtML

综合技术随笔与案例

http://wap.blog.occzl.cn/Article/details/6889.sHtML
http://wap.blog.occzl.cn/Article/details/690616.sHtML
http://wap.blog.occzl.cn/Article/details/7038112.sHtML
http://wap.blog.occzl.cn/Article/details/70977.sHtML
http://wap.blog.occzl.cn/Article/details/723037.sHtML
http://wap.blog.occzl.cn/Article/details/7294.sHtML
http://wap.blog.occzl.cn/Article/details/7420.sHtML
http://wap.blog.occzl.cn/Article/details/74248.sHtML
http://wap.blog.occzl.cn/Article/details/7434.sHtML
http://wap.blog.occzl.cn/Article/details/749276.sHtML
http://wap.blog.occzl.cn/Article/details/7639.sHtML
http://wap.blog.occzl.cn/Article/details/767798.sHtML
http://wap.blog.occzl.cn/Article/details/77248.sHtML
http://wap.blog.occzl.cn/Article/details/7761105.sHtML
http://wap.blog.occzl.cn/Article/details/7848.sHtML
http://wap.blog.occzl.cn/Article/details/7867791.sHtML
http://wap.blog.occzl.cn/Article/details/7903429.sHtML
http://wap.blog.occzl.cn/Article/details/792517.sHtML
http://wap.blog.occzl.cn/Article/details/79494.sHtML
http://wap.blog.occzl.cn/Article/details/801525.sHtML

长尾与补录链接

http://wap.blog.occzl.cn/Article/details/80680.sHtML
http://wap.blog.occzl.cn/Article/details/817709.sHtML
http://wap.blog.occzl.cn/Article/details/825250.sHtML
http://wap.blog.occzl.cn/Article/details/8370542.sHtML
http://wap.blog.occzl.cn/Article/details/8380.sHtML
http://wap.blog.occzl.cn/Article/details/8397.sHtML
http://wap.blog.occzl.cn/Article/details/8427.sHtML
http://wap.blog.occzl.cn/Article/details/84658.sHtML
http://wap.blog.occzl.cn/Article/details/8503.sHtML
http://wap.blog.occzl.cn/Article/details/854518.sHtML
http://wap.blog.occzl.cn/Article/details/8571872.sHtML
http://wap.blog.occzl.cn/Article/details/8704695.sHtML
http://wap.blog.occzl.cn/Article/details/8706.sHtML
http://wap.blog.occzl.cn/Article/details/8747011.sHtML
http://wap.blog.occzl.cn/Article/details/87718.sHtML
http://wap.blog.occzl.cn/Article/details/8829.sHtML
http://wap.blog.occzl.cn/Article/details/8838102.sHtML
http://wap.blog.occzl.cn/Article/details/88748.sHtML
http://wap.blog.occzl.cn/Article/details/906827.sHtML
http://wap.blog.occzl.cn/Article/details/90713.sHtML

最终批次收尾链接

http://wap.blog.occzl.cn/Article/details/9283.sHtML
http://wap.blog.occzl.cn/Article/details/929913.sHtML
http://wap.blog.occzl.cn/Article/details/934451.sHtML
http://wap.blog.occzl.cn/Article/details/936617.sHtML
http://wap.blog.occzl.cn/Article/details/942161.sHtML
http://wap.blog.occzl.cn/Article/details/9498.sHtML
http://wap.blog.occzl.cn/Article/details/9517.sHtML
http://wap.blog.occzl.cn/Article/details/9524773.sHtML
http://wap.blog.occzl.cn/Article/details/958005.sHtML
http://wap.blog.occzl.cn/Article/details/9596.sHtML
http://wap.blog.occzl.cn/Article/details/96120.sHtML
http://wap.blog.occzl.cn/Article/details/96353.sHtML
http://wap.blog.occzl.cn/Article/details/96372.sHtML
http://wap.blog.occzl.cn/Article/details/96539.sHtML
http://wap.blog.occzl.cn/Article/details/9759.sHtML
http://wap.blog.occzl.cn/Article/details/98197.sHtML
http://wap.blog.occzl.cn/Article/details/98219.sHtML
http://wap.blog.occzl.cn/Article/details/9945302.sHtML

## 项目结构

项目采用模块化分层设计，核心索引引擎与输出适配器解耦，便于扩展新的输入源或输出格式。

```
wap-blog-occzl-gateway/
├── src/                                    # 核心源代码目录
│   ├── indexer/                            # 索引构建引擎模块
│   │   ├── __init__.py                     # 模块初始化，导出主要类
│   │   ├── builder.py                      # 索引构建器，负责解析链接和生成树结构
│   │   └── validator.py                    # 链接校验器，包含去重和 HTTP 探测逻辑
│   ├── parser/                             # 原始链接解析模块
│   │   ├── __init__.py                     # 解析器工厂方法
│   │   ├── url_parser.py                   # 从 URL 中提取文章 ID 和扩展名
│   │   └── batch_loader.py                 # 批量加载 TXT 或 CSV 格式的链接列表
│   ├── output/                             # 输出适配器模块
│   │   ├── __init__.py                     # 输出接口定义
│   │   ├── json_exporter.py                # 导出为嵌套 JSON 结构
│   │   ├── yaml_exporter.py                # 导出为 YAML 格式，保持可读性
│   │   └── tree_writer.py                  # 生成 ASCII 目录树文本
│   └── cli/                                # 命令行交互模块
│       ├── __init__.py                     # CLI 入口点
│       └── main.py                         # argparse 参数解析与路由分发
├── tests/                                  # 单元测试与集成测试目录
│   ├── test_builder.py                     # 针对索引构建器的测试用例
│   ├── test_validator.py                   # 链接校验功能的边界条件测试
│   └── fixtures/                           # 测试用的固定样本数据
│       └── sample_links.txt                # 包含 10 条示例链接的文本文件
├── docs/                                   # 项目文档目录
│   ├── user_guide.md                       # 用户操作手册
│   ├── developer_guide.md                  # 开发者二次开发指南
│   └── api_reference.md                    # 完整的 API 函数签名文档
├── data/                                   # 存放原始输入和中间输出数据
│   ├── raw/                                # 原始批次链接文件存放处
│   │   └── batch_30.txt                    # 第 30 批次的原始链接列表
│   └── processed/                          # 处理后的索引结果输出目录
│       └── index_batch_30.json             # 示例输出文件
├── scripts/                                # 辅助运维脚本
│   ├── cron_check.sh                       # 定时巡检链接状态的 Shell 脚本
│   └── import_from_csv.py                  # 从外部 CSV 导入链接的独立脚本
├── requirements.txt                        # Python 依赖声明文件
├── setup.py                                # 项目安装与打包配置
└── README.md                               # 本文件
```

## 贡献指南

项目遵循标准的 GitHub Flow 协作流程。欢迎各类形式的贡献，包括但不限于新增链接解析规则、优化索引树结构、完善文档以及提交缺陷修复。

1.  Fork 本仓库至个人账户，并克隆至本地开发环境。确保本地 Python 版本符合安装要求，且已通过 `pip install -e .` 命令以可编辑模式安装项目。

2.  创建新的功能分支，分支名称需简洁描述本次贡献内容，例如 `feat/support-xml-output` 或 `fix/duplicate-removal-bug`。请避免在主分支上直接进行修改。

3.  提交代码前，请运行 `flake8 src/` 和 `pytest tests/` 确保代码风格符合规范且所有已有测试用例通过。新增功能需同步编写对应的单元测试。

4.  提交 Pull Request 至本仓库的 main 分支。PR 描述中需清晰说明改动目的、涉及模块以及手动测试的结果摘要。若 PR 涉及链接资源列表的增删，请附加数据来源说明。

5.  PR 合并前至少需要一名项目维护者进行 Code Review。审核通过后由维护者执行 Squash and Merge 操作，保持主分支历史整洁。

## 常见问题

**Q: 项目是否存储文章正文内容？是否会侵犯原始网站的版权？**

A: 本项目仅存储文章页面的 URL 链接字符串以及可选的元数据（如标题、摘要），不缓存或复制任何正文内容。所有链接均指向 wap.blog.occzl.cn 原始域名下的公开页面，用户访问时需自行遵守目标网站的 Robots 协议和使用条款。本项目定位为技术爱好者自用的索引工具，不涉及任何商业用途。

**Q: 如何处理链接失效或目标页面返回 404 状态码？**

A: 项目提供的 validator.py 模块支持批量链接状态检查。用户可通过 `python -m src.cli.main --validate --input ./data/raw/batch_30.txt` 命令生成失链报告。对于失效链接，建议定期复查原始网站是否恢复，或从索引库中主动标记剔除。项目本身不提供自动修复功能。

**Q: 能否将本项目输出的索引结构直接用于生成静态博客的导航页面？**

A: 可以。项目内置的 tree_writer.py 和 json_exporter.py 输出的目录树和 JSON 数据结构，可作为静态站点生成器（如 Hugo、Jekyll）的数据源。用户只需将输出文件放置于站点的 data 目录下，并编写相应的模板循环渲染逻辑即可。具体集成案例可参考 docs/user_guide.md 中的进阶章节。

## 许可证

MIT

> 外链数量: 180 | 生成时间: 2026-07-03 21:16:19
