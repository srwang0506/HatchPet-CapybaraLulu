<p align="center">
  <img src="assets/teaser.png" alt="Capybara Lulu——灵动的噜噜桌宠" width="100%">
</p>

<p align="center">
  <img src="assets/readme-title.svg" alt="HatchPet: Capybara Lulu——一只温暖、灵动、会陪 Codex 一起工作的水豚噜噜" width="92%">
</p>

<p align="center">
  <a href="README.md">English</a> · <a href="README.zh-CN.md">简体中文</a>
</p>

<p align="center"><strong>一只温暖、灵动、会陪 Codex 一起工作的水豚噜噜。</strong></p>

<table>
  <tr>
    <td align="center" width="25%"><strong>16</strong><br><sub>灵动静止阶段</sub></td>
    <td align="center" width="25%"><strong>9</strong><br><sub>任务感知状态</sub></td>
    <td align="center" width="25%"><strong>16</strong><br><sub>注视方向</sub></td>
    <td align="center" width="25%"><strong>83</strong><br><sub>透明源帧</sub></td>
  </tr>
</table>

<p align="center"><sub>Codex 桌宠就绪 &nbsp;·&nbsp; Apache-2.0 &nbsp;·&nbsp; 完整源素材 &nbsp;·&nbsp; 确定性验证</sub></p>

<p align="center">
  <img src="assets/lulu-in-motion.png" alt="Lulu in Motion——噜噜跑步、跳跃、挥手、玩电脑、等待与检查成果" width="100%">
</p>

### 🧡 认识噜噜

Capybara Lulu 是为 ChatGPT 桌面端 Codex 体验制作的自定义桌宠。没有任务时，噜噜会呼吸、眨眼、张嘴并用一只小手自然挥动；拖动时会左右跑；鼠标移动时会转头注视；Codex 工作、等待输入、完成任务或出错时，也都有独立反应。

> [!TIP]
> **想马上见到噜噜？** 运行 `python3 scripts/install.py`，重启 ChatGPT 桌面端，然后在 **设置 → Pets** 中选择 **水豚噜噜**。

实际安装的 `pet/spritesheet.webp` 是一张带时间轴的 8 × 11 动态图集。16 帧静止循环共 2.13 秒，用 WebP 自身的图像时钟解决桌面渲染器切换图集列较慢造成的长时间停顿。仓库同时保留静态图集，供质量检查、二次编辑和减少动态效果时使用。

| 能力 | 仓库内容 |
| --- | --- |
| 灵动静止状态 | 16 个阶段：休息、呼吸、眨眼、张嘴/闭嘴、单手挥动、自然回正 |
| 任务感知 | 工作中、等待输入、完成待查看、失败/阻塞都有独立动作 |
| 桌面互动 | 鼠标悬停会跳跃，水平拖动会交替腿跑动 |
| 方向注视 | 每 22.5° 一帧，共 16 个顺时针方向 |
| 完整开源素材 | 83 张透明 PNG、10 个 GIF、可复现画廊脚本、验证工具和升级后的 `hatch-pet` 工作流 |

### 🎬 动作与触发表

下表对应当前 Codex 桌面端的实际状态映射。具体停留时长与状态切换由客户端控制，未来版本可能微调。

| 动作 | 预览 | 什么时候触发 | 帧数 |
| --- | --- | --- | ---: |
| **灵动静止**（`idle`） | <img src="assets/gifs/idle.gif" alt="噜噜灵动静止循环" width="116"> | 没有活动状态，且鼠标位于中性死区时。WebP 时间轴会自动播放呼吸、眨眼、张嘴和单手挥动。 | [16 · 2.13 秒](assets/frames/idle/) |
| **向右跑**（`running-right`） | <img src="assets/gifs/running-right.gif" alt="噜噜向右跑" width="116"> | 向屏幕右侧拖动悬浮桌宠。 | [8 · 1.06 秒](assets/frames/running-right/) |
| **向左跑**（`running-left`） | <img src="assets/gifs/running-left.gif" alt="噜噜向左跑" width="116"> | 向屏幕左侧拖动悬浮桌宠。 | [8 · 1.06 秒](assets/frames/running-left/) |
| **打招呼**（`waving`） | <img src="assets/gifs/waving.gif" alt="噜噜打招呼" width="116"> | 唤醒桌宠后的首次问候。 | [4 · 0.70 秒](assets/frames/waving/) |
| **跳跃**（`jumping`） | <img src="assets/gifs/jumping.gif" alt="噜噜跳跃" width="116"> | 鼠标进入或悬停在噜噜上方。 | [5 · 0.84 秒](assets/frames/jumping/) |
| **失败/阻塞**（`failed`） | <img src="assets/gifs/failed.gif" alt="噜噜失败反应" width="116"> | 对话失败、被阻塞或遇到系统错误。 | [8 · 1.22 秒](assets/frames/failed/) |
| **等待输入**（`waiting`） | <img src="assets/gifs/waiting.gif" alt="噜噜等待输入" width="116"> | Codex 需要审批、回答或其他用户决定。 | [6 · 1.01 秒](assets/frames/waiting/) |
| **工作中**（`running`） | <img src="assets/gifs/running.gif" alt="噜噜拿电脑工作" width="116"> | 对话正在工作。噜噜会拿电脑处理任务，而不是原地跑步。 | [6 · 0.82 秒](assets/frames/running/) |
| **完成/检查成果**（`review`） | <img src="assets/gifs/review.gif" alt="噜噜检查成果" width="116"> | 对话已经完成，并且有尚未查看的活动。 | [6 · 1.03 秒](assets/frames/review/) |
| **四处看**（第 9–10 行） | <img src="assets/gifs/look-directions.gif" alt="噜噜 16 向注视" width="116"> | 噜噜处于静止、工作或问候状态时，根据鼠标方向切换；正面中性位置回到静止动作。 | [16 个方向](assets/frames/look-directions/) |

多个对话同时有活动时，官方优先级为：**等待输入 → 阻塞 → 完成待查看 → 工作中**。点击噜噜会返回 ChatGPT；点击活动托盘中的项目会打开对应对话。详见 OpenAI 官方[桌宠文档](https://learn.chatgpt.com/docs/pets?surface=app)。

README 中的 GIF 均保留透明背景，在 GitHub 的浅色与深色主题下都能自然显示；动作总览图继续使用纯白编辑画布，83 张独立源帧与实际安装图集也都保留原始透明通道。

### 🖼️ 所有动作的每一帧

83 张实际发布帧均以透明 PNG 形式保存在 [`assets/frames`](assets/frames/)；[`assets/frames/manifest.json`](assets/frames/manifest.json) 记录了帧序、时长与注视角度。

<p align="center">
  <img src="assets/all-frames.png" alt="水豚噜噜全部动作帧" width="100%">
</p>

#### 🌿 16 帧静止时间线

挥手不是两张图上下跳变，而是完整的抬手、三个相邻顶点角度、回程、落手与中性回归。画面右侧的小手负责挥动，另一只手始终自然垂在身体侧面。

<p align="center">
  <img src="assets/idle-frames.png" alt="噜噜 16 帧灵动静止时间线" width="100%">
</p>

#### 👀 完整图集与注视质量检查

<details>
<summary>🧩 展开 8 × 11 完整图集接触表</summary>

<p align="center">
  <img src="assets/sprite-atlas.png" alt="噜噜完整精灵图集" width="100%">
</p>

</details>

<details>
<summary>🧭 展开正面与 16 向注视检查图</summary>

<p align="center">
  <img src="assets/look-directions.png" alt="噜噜 16 向注视检查图" width="100%">
</p>

</details>

### 🐾 在 Codex 中安装

#### ⚡ 一条命令安装

下载或克隆仓库后，在项目根目录运行：

```bash
python3 scripts/install.py
```

安装脚本会：

1. 将 `pet/pet.json` 和 `pet/spritesheet.webp` 复制到 `~/.codex/pets/capybara-lulu/`；
2. 把已有安装备份到 `~/.codex/backups/capybara-lulu/`；
3. 在 `~/.codex/config.toml` 中把 `[desktop].selected-avatar-id` 设置为 `custom:capybara-lulu`。

只想写入文件、不自动选中时可运行 `python3 scripts/install.py --no-select`。安装后必须完全退出并重新打开 ChatGPT 桌面端，因为自定义宠物列表存在进程级缓存。

#### 🧰 手动安装

macOS 与 Linux：

```bash
mkdir -p ~/.codex/pets/capybara-lulu
cp pet/pet.json pet/spritesheet.webp ~/.codex/pets/capybara-lulu/
```

Windows PowerShell：

```powershell
$target = Join-Path $HOME ".codex/pets/capybara-lulu"
New-Item -ItemType Directory -Force -Path $target | Out-Null
Copy-Item pet/pet.json, pet/spritesheet.webp -Destination $target -Force
```

随后打开 **设置 → Pets**，点击 **Refresh**，选择 **水豚噜噜**。使用 `/pet`、**Wake Pet** 或 **Tuck Away Pet** 显示或收起桌面悬浮层。宠物选择与位置会在重启后保留。

如果当前客户端没有通过界面选中噜噜，可在 `~/.codex/config.toml` 中加入以下内容并重启：

```toml
[desktop]
selected-avatar-id = "custom:capybara-lulu"
```

#### 🔁 让任务动作保持原速循环（macOS，可选）

桌面渲染器默认只把非静止动作播放三轮，随后即使 Codex 仍在工作或等待，也会回到静止画面。这个可选补丁会让当前动作在对应真实状态存在期间持续重复。它**不会**把单帧放慢、拖延状态切换，也不会在任务已经完成后强行保留“工作中”。

补丁写入前后都会验证 ASAR 完整性，并自动建立带时间戳的备份：

```bash
node hatch-pet/scripts/patch_codex_pet_playback.mjs --check /Applications/ChatGPT.app
node hatch-pet/scripts/patch_codex_pet_playback.mjs --apply /Applications/ChatGPT.app
```

执行后必须完全退出并重新打开 ChatGPT。应用更新可能覆盖补丁，更新后应重新运行 `--check`。命令输出中的 `backupDir` 可用于精确恢复。

#### ⌨️ Codex CLI

在交互式 Codex CLI 中输入 `/pets` 或 `/pet`，然后选择 **水豚噜噜**。终端宠物需要 iTerm2 3.6+、Kitty 图形协议或 Sixel 支持，在 tmux 和 Zellij 内不可用。Codex IDE 扩展目前不提供宠物选择器或悬浮桌宠。

#### 🔗 HTTPS 安装链接

Codex 支持通过 HTTPS 图集地址打开宠物安装流程。本仓库可直接分享的链接如下：

```text
codex://pets/install?name=%E6%B0%B4%E8%B1%9A%E5%99%9C%E5%99%9C&description=Capybara%20Lulu%20desktop%20pet&imageUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fsrwang0506%2FHatchPet-CapybaraLulu%2Fmain%2Fpet%2Fspritesheet.webp&spriteVersionNumber=2
```

安装链接只接受 `name`、`description`、`imageUrl` 与 `spriteVersionNumber`。`imageUrl` 必须是绝对 HTTPS 地址。`spriteVersionNumber=2` 是 Codex 8 × 11 图集协议字段，不是本项目的发布版本号。

### ⚙️ Codex 与 Claude Code 配置说明

| 环境 | 能否原生显示噜噜 | 推荐配置 |
| --- | --- | --- |
| ChatGPT 桌面端 · Codex | **可以** | 运行 `python3 scripts/install.py`，重启应用，然后在 **设置 → Pets** 中选择噜噜。 |
| Codex CLI | **支持的终端中可以** | 安装相同的本地宠物包，再通过 `/pets` 选择。 |
| Codex IDE 扩展 | **不可以** | 需要桌宠时使用桌面端或 Codex CLI。 |
| Claude Code | **没有 Codex 宠物原生渲染器** | 可用于维护仓库、查看素材和参与开发；把 `pet/` 复制到 `~/.claude` 不会出现桌宠。 |

Claude Code 仍然可以完整参与项目维护：

```bash
git clone https://github.com/srwang0506/HatchPet-CapybaraLulu.git
cd HatchPet-CapybaraLulu
claude
```

仓库中的 [`CLAUDE.md`](CLAUDE.md) 与 [`AGENTS.md`](AGENTS.md) 会约束噜噜的角色特征与验证流程。Claude Code 会读取项目级 `CLAUDE.md`；其可复用 Skill 位于 `~/.claude/skills/` 或 `.claude/skills/`，详见 Anthropic 官方 [Skills 文档](https://code.claude.com/docs/en/skills)。

随仓库提供的 [`hatch-pet`](hatch-pet/) 是构建本项目时使用的 Codex 生成与质量检查工具。它依赖 Codex 的图像生成能力并输出 Codex 宠物协议，因此复制到 Claude Code **不等于**获得桌宠渲染器，也不保证图像生成步骤可用。若要让 Claude Code 真正驱动桌面宠物，需要独立渲染器和 Hook 状态桥；本仓库不会把尚不存在的原生支持写成已支持。

### 🧩 可选：在 Codex 中安装创作 Skill

仓库包含升级后的 `hatch-pet` Skill，支持 WebP 图像时钟流畅静止循环、灵动阶段清单、9 状态质量检查与 16 向注视验证。

```bash
mkdir -p ~/.codex/skills/hatch-pet
rsync -a hatch-pet/ ~/.codex/skills/hatch-pet/
```

重启 Codex 或重新加载 Skills，之后可通过 `$hatch-pet` 创建或修复宠物。只使用现成噜噜不需要安装 Skill；可直接安装 [`pet/`](pet/) 中的宠物包。

### ♿ 减少动态效果

官方宠物会尊重操作系统的“减少动态效果”设置。本项目的丝滑静止状态使用动态 WebP 自身的图像时钟，在 JavaScript 精灵定时器被减少时仍可能继续播放。如果持续动画不适合你的使用场景，可将已安装运行图集替换为静态质量检查图集：

```bash
cp assets/spritesheet-static.webp ~/.codex/pets/capybara-lulu/spritesheet.webp
```

替换后重启应用。任务状态和 16 向注视仍然保留，只移除了额外的动态 WebP 静止包装。

### 🧪 开发与验证

创建环境并重建公开素材：

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python scripts/build_gallery.py
```

验证静态源图集和完整动态运行图集：

```bash
python hatch-pet/scripts/validate_atlas.py \
  assets/spritesheet-static.webp \
  --chroma-key '#FF00FF' \
  --require-v2

python hatch-pet/scripts/validate_atlas.py \
  pet/spritesheet.webp \
  --chroma-key '#FF00FF' \
  --require-v2 \
  --allow-animated \
  --allow-transparent-rgb-residue

python hatch-pet/scripts/validate_smooth_idle_webp.py \
  pet/spritesheet.webp \
  --source-atlas assets/spritesheet-static.webp \
  --phase-manifest assets/idle-phases.json

python -m unittest discover -s hatch-pet/tests -v
```

验收目标：

- 静态与动态运行图集均为 1536 × 2288 RGBA；
- `spriteVersionNumber` 必须保持为 `2`；
- 动态运行图集共 16 帧、2130 ms、无限循环；
- 所有可被桌面渲染器选择的静止列保持同相；
- 每个运行帧的第 1–10 行与静态源图集渲染完全一致；
- 不得出现眉毛、尾巴、多余肢体、换手、步态倒退或基线跳动。

### 🗂️ 仓库结构

```text
capybara-lulu/
├── assets/                 # teaser、头像、GIF、83 张 PNG 与质量检查图
├── hatch-pet/              # 创作 Skill、确定性脚本、参考规范与测试
├── pet/                    # 可直接安装的 Codex 宠物包
├── scripts/                # 安装器与素材画廊生成器
├── AGENTS.md               # Codex 贡献约束
├── CLAUDE.md               # Claude Code 项目上下文
├── README.md               # 英文文档
└── README.zh-CN.md         # 简体中文文档
```

### 🤝 参与贡献

修改画面或时序前请阅读 [`CONTRIBUTING.md`](CONTRIBUTING.md)。视觉改动必须同步重建 GIF 与总览图，并通过确定性验证。安全问题请按 [`SECURITY.md`](SECURITY.md) 提交。

### 📜 许可证与名称

代码、文档及仓库素材按 [Apache License 2.0](LICENSE) 提供，但仍受 [`NOTICE`](NOTICE) 中所述权利边界约束。本项目为独立项目，与 OpenAI、Anthropic 无隶属关系。Codex、ChatGPT、Claude 与 Claude Code 等名称归各自权利人所有。
