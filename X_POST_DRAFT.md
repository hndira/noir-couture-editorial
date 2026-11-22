# X（Twitter）长贴文草稿

> 适用场景：X 长文（X Articles）或长贴（Premium Long Post）。按下方 `[配图 1]` ~ `[配图 5]` 位置直接拖入对应样图即可。

---

## 推荐标题（用于 X Article 封面标题）

**我把一组暗调高定时尚大片，逆向拆成了一个开源 Agent Skill：以后每次 AI 出图，都像同一个摄影团队拍的**

---

## 正文（可直接复制发布）

用 AI 做视觉内容，大家最头疼的往往不是「单张不好看」，而是**风格不可复用**——

上一张还是质感爆棚的暗调杂志封面，下一张换个主题、换个模特性别，构图、色温、字体和光影就全飘了。

这次我干脆做了一件更彻底的事：
拿了一组我很喜欢的**暗调高定杂志风（Noir Couture Editorial）**参考图，把背后的摄影、色彩和排版规则全部逆向工程，打包成了一个标准的开源 **`noir-couture-editorial` Agent Skill**。

装进 Antigravity / Claude Code / Codex 之后，Agent 可以按服装选模板、配字体。接入生图工具时可以直接出图并核字，也可以只要一份完整提示词。

先看同一套 Skill 实测跑出来的几组不同主题效果（建筑感高定、新中式、男装/女装杂志封面、暗黑蕾丝吊带丝袜 × AI 定制艺术字）👇

[配图 1：assets/showcase/01-architectural-ivory-poster.jpg — Mode A 建筑感象牙白高定海报]

[配图 2：assets/showcase/02-neo-chinese-ink-poster.jpg — Mode A 新中式「墨韵新衣」丝绸水墨海报]

---

### 我是怎么把“高级感”拆解成可执行 Skill 的？

好看的画风不能靠玄学形容词（比如“高级”“奢华”“大片感”），必须写成 Agent 能严格执行的硬规则。我在这套 Skill 里锁定了 4 条视觉 DNA：

**1️⃣ 双模态版式系统（不让构图乱飞）**
- **Mode A · 全身海报模式（`poster`）**：3:4 竖版全身 T 台站姿，磨砂黑曜石水泥质感背景（`#121315`–`#25272A`），左右保留干净的文字安全区，左上放高对比宋体或狂草中文大标题，右下配四行工艺参数。
- **Mode B · 杂志封面模式（`cover`）**：改用暖深灰褐无缝棚拍背景（`#3E3A37`–`#58524D`）配坐姿七分身特写，顶部通栏高对比衬线刊头（`ATELIER` / `COUTURE` 等原创刊名）**必须压在模特发丝与发簪后方**，做出真实印刷封面的前后景深。

[配图 3：assets/showcase/03-menswear-atelier-cover.jpg — Mode B 男装「黑曜绅士」ATELIER 杂志封面]

**2️⃣ 极度克制的色彩预算：暗调背景 + 少量朱砂红**
全画面以黑曜石、暖灰褐、象牙白、墨灰和液态银打底。服装保留自己的颜色，**`#B81D24` 朱砂红的平面点缀通常控制在画面约 5% 以内**，
只以「大标题下的一道飞白红划痕」「中英文之间的 2px 短红杠」「朱红小印章」或「背景暗处的一笔赤墨弧线」出现。克制，恰恰是高定感的核心来源。

**3️⃣ 服装驱动的定制字体系统 + 汉字防崩机制**
以前做海报最怕满屏死板电脑宋体、标题永远只会写「高定时装」。这次在 Skill 里直接建了一套**服装→字体映射矩阵**，拒绝死板固定字体：
- **暗黑蕾丝 / 薄纱吊带礼服** 👉 AI 定制瘦金丝带书法（如「夜纱 / 织影」）+ *Cormorant Garamond* 浪漫斜体英文；
- **新中式暗纹提花** 👉 飞白行草（*江西拙楷* / *马善政* 气质）+ 铭刻感衬线英文；
- **液态金属 / 建筑廓形** 👉 AI 原创液态铬金刀锋体或断笔几何无衬线体（*Syne* / *Space Grotesk* 气质）；
- 自己拟的标题通常只用 2–4 个字，整张图的中文尽量控制在约 30 字。用户给定的标题逐字保留，出图后再核对字形和拼写。

[配图 4：assets/showcase/06-obsidian-suspender-bespoke-type.jpg — Mode A 黑曜暗花薄纱 × 吊带丝袜 + AI 原创瘦金丝带体「夜纱织影」]

**4️⃣ 中画幅棚拍光学锚点 + 出图自检**
每张图都会自动注入 85mm–100mm 中画幅棚拍光影、35° 高位轮廓柔光、发丝边缘光和织物经纬肌理，同时内置「禁用霓虹赛博、禁用塑料 CG 皮肤、禁用僵硬电脑默认宋体、禁用商标 Logo」的防跑偏护栏。

[配图 5：assets/showcase/04-womenswear-couture-cover.jpg — Mode B 女装「东方美学」COUTURE 杂志封面]

---

### 以后怎么用？

装好 Skill 后，不用再自己拼几百字英文提示词，直接用自然语言跟 Agent 说一句就行：

> 「用 `noir-couture-editorial` 风格，生成一张新中式墨绿暗纹丝绸长裙海报，主标《松烟入画》。」
> 「用 `noir-couture-editorial` 的封面模式，画一张冬季男装炭灰羊绒风衣封面，刊头用 `MAISON`。」

无论是做小红书视觉系列、品牌 Lookbook、电商主图还是自媒体封面，整组图的调性都会稳稳锁在一条视觉线上。

---

### 开源地址 & 安装方式

整套 Skill（含 `SKILL.md`、完整色彩/打光规范 `style-dna.md`、4 套即插即用 Prompt 模板与全部实测样图）已经整理打包完毕，全部开源免费拿走：

🔗 **GitHub 仓库**：<https://github.com/hndira/noir-couture-editorial>

一行命令安装到你的 Agent 环境（支持 Antigravity / Claude Code / Codex 等兼容 `SKILL.md` 的工具）：
```bash
npx skills add hndira/noir-couture-editorial
```

或者直接克隆仓库，把 `skills/noir-couture-editorial/` 复制到你的本地 `~/.gemini/config/skills/` 或项目 `.agents/skills/` 目录即可开用。

如果你也想把某套自己喜欢的视觉风格「固化」成 Agent Skill，欢迎 Star / Fork 这个仓库当模板改造 ✨

#AISkill #AgentSkills #AIGC #AI绘画 #PromptEngineering #高定视觉 #设计自动化
