# TuxBuddy 品牌基建设计文档（Phase 0）

日期：2026-10-14 · 状态：待用户评审

## 1. 定位

TuxBuddy 是一个开源组织（github.com/TuxBuddy）与产品品牌，方向为 Cloud Native 运维工具生态。能力版图（按阶段交付）：

1. Kubernetes 自动运维
2. eBPF 可观测
3. 网络故障诊断
4. MCP（AI Agent 工具接口）
5. 跨集群管理

一句话口号：**A penguin buddy for your clusters. / 给集群配一只企鹅伙伴。**

本期（Phase 0）只做品牌基建：组织 profile README、品牌资产、官网落地页、LICENSE。不写产品代码。

对外语言：英文为主、中文并行（官网整站一键切换；README 英文段落 + 中文段落并列）。

## 2. 视觉识别

### 2.1 品牌图标（已定稿 · 纯净版）

App 图标风格：深色微渐变 squircle + 极简几何 Tux。**无任何配件**（光环/天线等方案已逐一否决，最终定稿为纯净版）。

- 底：圆角方形（rx ≈ 22.5%），垂直渐变 `#1A2332 → #0A0E16`
- 企鹅：几何极简——身体 `#10151E` 带极淡描边 `#2A3446`（深底可辨识），白肚 `#F5F7FA`，橙喙橙脚 `#FFAB2E`，白眼黑瞳
- 无光环、无内框描边、无其他标记

派生资产（已产出，位于 `assets/`）：

| 文件 | 用途 |
|---|---|
| `icon.svg` | 母版（512 viewBox） |
| `favicon.svg` | 小尺寸简化版（加粗五官、去细节），官网 favicon |
| `avatar-1024.png` | GitHub 组织头像上传用 |
| `tux-official.svg` | 官方 Tux 矢量（见 2.3） |

### 2.2 "Buddy" 的表达

视觉层不承载 AI 符号：Buddy 由品牌名、口号与产品体验表达（Tux + Buddy = 名字本身就是叙事）。标题文案中 "buddy" 一词的渐变色保留为唯一的 AI 视觉暗示（见 2.4），图标与吉祥物保持纯净。

### 2.3 官方 Tux 素材与授权（品牌资产层）

官方 Larry Ewing 原作 Tux 的矢量版（garrett/Tux 仓库，已补 viewBox 本地化）作为品牌资产保留在 `assets/tux-official.svg`，用于 README / 关于页等品牌叙事场景。授权链：Larry Ewing 原作（GIMP）→ Garrett LeSage 矢量化 → IFo Hancroft 清理，**CC0 公共领域**。

**官网 Hero 主视觉使用与图标同源的极简几何企鹅**（用户 2026-10-14 定稿：全站视觉统一为极简图标风格，不用写实版）。页脚保留礼貌致谢与独立性声明：

> Tux was created by Larry Ewing in GIMP, re-illustrated in vector by Garrett LeSage and IFo Hancroft (CC0). TuxBuddy is an independent open-source project, not affiliated with the Linux Foundation.

### 2.4 配色与字体

| Token | 值 | 用途 |
|---|---|---|
| 背景 | `#fbfbfd` | 页面底色 |
| 分区灰 | `#f5f5f7` | 能力区/页脚 |
| 主文字 | `#1d1d1f` | 标题正文 |
| 次文字 | `#6e6e73` / `#86868b` | 描述 |
| 链接/按钮 | `#0066cc` / `#0071e3` | 交互 |
| AI 渐变 | `#0090F7→#BA62FC→#F2416B→#F5A623` | "buddy" 词、光环、点睛 |

字体：系统栈 `-apple-system, "SF Pro Display", "PingFang SC", sans-serif`（苹果设备自动获得 SF Pro / 苹方），等宽 `SF Mono / ui-monospace`。

风格红线：不做深色发光、霓虹渐变背景、玻璃拟态卡片堆叠、行内图标轰炸；克制、留白、一屏一事（Apple HIG 取向）。

## 3. 官网落地页

纯静态 HTML/CSS/JS，无框架无构建。结构：

1. **导航**：毛玻璃白条，小图标 + TuxBuddy 字标，Capabilities / Roadmap / GitHub，右侧 EN/中文 切换
2. **Hero**（白）：eyebrow → 大标题（"buddy" 渐变词）→ 中文副题 → 描述 → 蓝色药丸按钮 + 文字链 → **极简几何企鹅大图（与图标同源，纯净版）+ 地面柔影**
3. **终端区**（黑）：One buddy. Every layer. + `tux status --all` 终端卡（绿光标闪烁）
4. **能力区**（灰）：5 张白卡（K8s 运维 / eBPF 可观测 / 网络诊断 / MCP 原生 / 跨集群），全部如实标注 Coming soon
5. **路线图**（白）：4 阶段点线（P0 Now / P1 Next / P2 / P3）
6. **页脚**：版权 + Apache-2.0 + Tux 致谢与独立性声明

双语实现：**每个语言模式整页纯一种语言，不做同屏混排**（默认英文，右上角一键切换中文）。技术为 `data-en` / `data-cn` 属性 + 按钮替换 textContent；专有名词（TuxBuddy / GitHub / MCP / eBPF / Apache-2.0 等）与终端卡内容不翻译。

## 4. 仓库与分发

| 仓库 | 内容 |
|---|---|
| `TuxBuddy/TuxBuddy` | 组织 profile 仓库：README（双语，展示于 org 主页）、`assets/`（icon/favicon/avatar/tux-official）、`docs/specs/`（本文档）、LICENSE |
| `TuxBuddy/tuxbuddy.github.io` | 官网静态站（index.html + favicon.svg + assets），GitHub Pages 从 main 自动发布，域名 `tuxbuddy.github.io` |

组织设置同步更新：描述、官网链接（tuxbuddy.github.io）、头像（avatar-1024.png）。

License：代码与内容仓库统一 **Apache-2.0**（Tux 素材依其自身 CC0 + 致谢条款）。贡献指南 / CoC 待第一个产品仓库（Phase 1）再补。

本地工作区：`/Users/zhangyi/my_project/tuxbuddy/` 下按 `tuxbuddy/`（profile clone）与 `tuxbuddy.github.io/`（站点 clone）双目录布局；`assets/` 与 `docs/` 为工作母版。

## 5. 验收标准

- [ ] github.com/TuxBuddy 组织页显示新头像、描述、带图标的 README
- [ ] tuxbuddy.github.io 可访问：苹果风落地页、双语切换可用、favicon 正确
- [ ] 两仓库均有 LICENSE；页脚含 Tux CC0 致谢
- [ ] `assets/` 四个品牌文件入库；icon.svg 在 32px 缩放下可辨识
- [ ] 全部页面无 console 错误（网络字体/图标零外链）

## 6. 实施步骤（评审通过后执行）

1. 本地组装 profile 仓库内容（README 双语 + assets + LICENSE）与站点仓库内容（从已定稿视觉稿转译为独立 index.html）
2. `gh repo create TuxBuddy/TuxBuddy --public` 与 `TuxBuddy/tuxbuddy.github.io --public`，推送
3. org 设置：`gh api -X PATCH orgs/TuxBuddy` 更新 description/website；上传头像
4. 启用 Pages（main 根目录），验证线上渲染与切换
5. 回收验收清单
