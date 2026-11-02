# 大脑研究图谱 · Brain Research Atlas

一个单页、可交互的 3D 脑图谱网站：把 **脑区图鉴（科普）**、**FUSI 功能超声脑区**、**tFUS 经颅超声靶点** 三套标注叠在同一个 Z-Anatomy 脑模型上，并附两套文献库。

🌐 **在线访问**：<https://yingjiefeng0632-gif.github.io/brain-atlas/>

## 功能

- **三档视图**：脑区图鉴（20 个脑区）/ FUSI（12 个人脑与灵长类脑区）/ tFUS（13 个刺激靶点）
- **3D 交互**：拖动旋转、滚轮缩放、点击图例定位脑区、`Ctrl+点击` 多选、深部结构「透视」滑杆
- **连线与图例**：每个脑区一条引线指向模型对应位置，右侧图例支持高亮联动
- **配图与出处**：人脑/灵长类脑区卡片内嵌论文配图，附图注来源（作者 · 期刊 · DOI）
- **文献库**：tFUS 23 篇、fUS 8 篇，支持按类别与关键词筛选

## 本地运行

```bash
# 需要 Node.js（仅用于起一个静态服务器）
node serve.mjs 8080
# 打开 http://127.0.0.1:8080
```

> 不要直接双击 `index.html`：ES module 不支持 `file://` 协议。也不要用 `python -m http.server`（Windows 上会把 `.js` 当 `text/plain` 返回，模块加载失败）。

## 目录结构

```
index.html          单页应用（HTML + CSS + JS 全内联，含 base64 配图）
assets/brain.glb    Z-Anatomy 脑模型（4.5 MB）
vendor/three/       three.js r160 + OrbitControls / GLTFLoader / DRACOLoader + Draco 解码器
serve.mjs           本地预览服务器（零依赖）
```

## 数据与配图来源

论文配图版权归原作者与期刊所有，此处仅用于学术说明（非商业）。DOI 均经 Crossref 核对：

| 脑区 | 文献 | DOI |
|---|---|---|
| 中央前回·口区、中央后回·体感口区 | Soloukey S et al., *Science Advances* 2025 | [10.1126/sciadv.adu9133](https://doi.org/10.1126/sciadv.adu9133) |
| 中央前回·手区 | Rabut C et al., *Science Translational Medicine* 2024 | [10.1126/scitranslmed.adj3143](https://doi.org/10.1126/scitranslmed.adj3143) |
| Wernicke 区、视觉皮层 V1 | Soloukey S et al., *NeuroImage* 2023 | [10.1016/j.neuroimage.2023.120435](https://doi.org/10.1016/j.neuroimage.2023.120435) |
| SEF、ACC | Dizeux A et al., *Nature Communications* 2019 | [10.1038/s41467-019-09349-w](https://doi.org/10.1038/s41467-019-09349-w) |
| LIP、PRR | Norman SL et al., *Neuron* 2021 | [10.1016/j.neuron.2021.03.003](https://doi.org/10.1016/j.neuron.2021.03.003) |

tFUS / fUS 文献库中的条目来自各自论文，卡片「文献出处」一栏保留原始编号（H1–H5、M1–M3、F1–F8）。

## 致谢

- 脑模型：[Z-Anatomy / BodyParts3D](https://github.com/itayinbarr/brainproject)（CC BY-SA 4.0）
- 3D 引擎：[three.js](https://threejs.org/)（MIT）
- 论文配图：见上表，版权归原作者与期刊

## 许可

本站代码以 MIT 许可发布；`assets/` 中的脑模型遵循 CC BY-SA 4.0；论文配图版权归原作者与期刊，不在 MIT 许可范围内。
