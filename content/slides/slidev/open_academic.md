---
theme: academic
layout: cover
class: text-white
coverAuthor: 王思远
coverAuthorUrl: wsy0227@stu.xjtu.edu.cn
coverBackgroundUrl: images/cover.jfif
coverBackgroundSource: unsplash
coverBackgroundSourceUrl: https://images.unsplash.com/photo-1594122230689-45899d9e6f69?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80
fonts:
  local: Montserrat, Roboto Mono, Roboto Slab # local fonts are used for legal reasons for deployment to https://slidev-theme-academic.alexeble.de and only set up for the example project, remove this line for your project to automatically have fonts imported from Google
themeConfig:
  paginationX: r
  paginationY: b
  paginationPagesDisabled: [1]
title: slidev-theme-academic
info: |
  # slidev-theme-academic

  Created and maintained by [Alexander Eble](https://www.alexeble.de).

  - [GitHub](https://github.com/alexanderdavide/slidev-theme-academic)
  - [npm](https://www.npmjs.com/package/slidev-theme-academic)

  slidev-theme-academic is licensed under [MIT](https://github.com/alexanderdavide/slidev-theme-academic/blob/master/LICENSE).

  <ul>
    <li>
      <a href="https://www.alexeble.de/impressum/" target="_blank">Legal information of this website</a>
    </li>
    <li>
      <a href="https://www.alexeble.de/datenschutz/" target="_blank">Privacy policy of this website</a>
    </li>
  </ul>
hideInToc: true
---

# 2023届毕设开题报告
# 基于可控磁场触控感知技术研究

**指导老师**：陈东尧 张玥

---
layout: table-of-contents
hideInToc: true
---

# 目录

---
layout:
---
# 任务简述

## 触觉感知
一种执行设备，能够产生多种模式的触觉刺激
* 力
* 振动
* 热刺激
* 形状

> 这种类型的设备能够支持人的双手进行<text style="color:teal">精细的操作</text>，并同时刺激人的触觉通道的多个感受器（包括<text style="color:teal">皮肤</text>和动觉感受器）。为了确保真实的感觉，刺激不同感受器的触觉刺激应该以一致的<text style="color:teal">空间</text>和<text style="color:teal">时间</text>方式显示，也就是说，这些多维刺激之间的空间搭配误差和时间延迟需要小于人类的分辨阈值。通过多模态触觉设备，用户能够在虚拟现实应用中感知到虚拟物体的多种属性<sup>1</sup>。

<style>
.container-two {
  word-break: break-all;
  width: 20%;
  height: 20%;
  border: 2px solid black;
}
</style>

<Footnotes separator>
  <Footnote :number=1><a href="https://ieeexplore.ieee.org/document/8733996" class="whitespace-normal" rel="noreferrer" target="_blank" >D. Wang, K. Ohnishi and W. Xu, "Multimodal Haptic Display for Virtual Reality: A Survey", in IEEE Transactions on Industrial Electronics, vol. 67, no. 1, pp. 610-623, Jan. 2020, doi: 10.1109/TIE.2019.2920602.</a></Footnote>
</Footnotes>

---
layout: center
class: "text-center"
hideInToc: false
---

# 研究前沿

---
layout: figure
figureCaption: TacTiles
figureFootnoteNumber: 2
figureUrl: images/opening/TacTile.png
hideInToc: true
---

# 研究前沿：压力触觉

<Footnotes separator>
  <Footnote :number=2><a href="https://ieeexplore.ieee.org/abstract/document/8797921/" class="whitespace-normal" rel="noreferrer" target="_blank" >Velko Vechev et al. 2019. Tactiles: Dual-mode low-power electromagnetic actuators for rendering continuous contact and spatial haptic patterns in VR. In 2019 IEEE Conference on Virtual Reality and 3D User Interfaces (VR), IEEE, 312–320.</a></Footnote>
</Footnotes>

---
layout: figure
figureCaption: Haptic Gloves
figureFootnoteNumber: 3
figureUrl: images/opening/Haptic_Glove_1.webp
hideInToc: true
---

# 研究前沿：气囊触觉

<Footnotes separator>
  <Footnote :number=3><a href="https://www.wired.com/story/facebook-haptic-gloves-vr/" class="whitespace-normal" rel="noreferrer" target="_blank" >Lauren Goode. 2021. Facebook Reaches for More Realistic VR With Haptic Gloves. Retrieved January 13, 2023 from https://www.wired.com/story/facebook-haptic-gloves-vr/</a></Footnote>
</Footnotes>

---
layout: figure
figureCaption: WeTac
figureFootnoteNumber: 4
figureUrl: images/opening/ElectroTactile.png
hideInToc: true
---

# 研究前沿：电触觉

<Footnotes separator>
  <Footnote :number=4><a href="https://www.nature.com/articles/s42256-022-00543-y" class="whitespace-normal" rel="noreferrer" target="_blank" >Kuanming Yao et al. 2022. Encoding of tactile information in hand via skin-integrated wireless haptic interface. Nature Machine Intelligence 4, 10 (October 2022), 893–903. DOI:https://doi.org/10.1038/s42256-022-00543-y</a></Footnote>
</Footnotes>


---
layout: figure
figureCaption: Epidermal VR System
figureFootnoteNumber: 5
figureUrl: images/opening/Epidermal.png
hideInToc: true
---

# 研究前沿：振动触觉

<Footnotes separator>
  <Footnote :number=5><a href="https://www.nature.com/articles/s41586-019-1687-0?ref=mainstreem-dotcom" class="whitespace-normal" rel="noreferrer" target="_blank" >Xinge Yu et al. 2019. Skin-integrated wireless haptic interfaces for virtual and augmented reality. Nature 575, 7783 (November 2019), 473–479. DOI:https://doi.org/10.1038/s41586-019-1687-0</a></Footnote>
</Footnotes>


---
layout: figure
figureCaption: Haptic Revolver
figureFootnoteNumber: 6
figureUrl: images/opening/HapticRevolver.png
hideInToc: true
---

# 研究前沿：手柄触觉

<Footnotes separator>
  <Footnote :number=6><a href="https://www.microsoft.com/en-us/research/publication/haptic-revolver-reconfigurable-virtual-reality-controller/" class="whitespace-normal" rel="noreferrer" target="_blank" >Eric Whitmire et al. 2018. Haptic Revolver: Touch, Shear, Texture, and Shape Rendering on a Reconfigurable Virtual Reality Controller. In Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems, ACM, Montreal QC Canada, 1–12. DOI:https://doi.org/10.1145/3173574.3173660</a></Footnote>
</Footnotes>


---
layout: figure
figureCaption: $60 Homemade VR Gloves
figureFootnoteNumber: 7
figureUrl: images/opening/HomemadeVRGloves.png
hideInToc: true
---

# 研究前沿：外骨骼

<Footnotes separator x="l">
  <Footnote :number=7><a href="https://www.youtube.com/watch?v=ZTzn37Usa-U" class="whitespace-normal text-left right-auto" rel="noreferrer" target="_blank" >Lucas VRTech. 2022. I built $60 VR Haptic Gloves to feel Virtual Reality. Retrieved January 13, 2023 from https://www.youtube.com/watch?v=ZTzn37Usa-U</a></Footnote>
</Footnotes>

---
layout:
---

<style> table th:first-of-type { width: 100px; } </style>
<style>
td,th {
  font-size: 20px
}
</style>

|          | TacTile | Haptic Glove | WeTac | Epidermal VR Systems | Haptic Revolver |
|----------|---------|--------------|-------|----------------------|-----------------|
| 类型     | 压力    | 气囊         | 电    | 振动                 | 手柄            |
| 灵活     | ✅       | ❌            | ✅     | ✅                    | ✅               |
| 紧凑     | ❌       | ❌            | ✅     | ✅                    | ✅               |
| 容易佩戴 | ✅       | ✅            | ❌     | ✅                    | ✅               |
| 定量压力 | ❌       | ❌            | ❌     | ❌                    | ❌               |
| 细粒度   | ❌       | ✅            | ✅     | ✅                    | ❌               |
| 关节限位 | ❌       | ✅            | ❌     | ❌                    | ❌               |
| 低成本   | ✅       | ❌            | ❔     | ❔                    | ✅               |




---
layout: figure-side
figureCaption: 3D 草图
figureUrl: images/opening/ModelImages/model_b_word_hd.png
---

# 研究方向

## 动机

* 灵活
* 紧凑
* 定量压力
* 细粒度


## 方案草图

一种可以佩戴在手上的压力产生装置

* 使用弹性磁材料包裹皮肤
* 电磁铁驱动
* 通过调整不同电磁铁的电流控制压力和触点


---
layout: figure
figureUrl: images/opening/FundamentalA.png
figureFootnoteNumber: 8
figureCaption: MagX：使用磁力计与永磁铁的姿态追踪系统 
---

## 研究基础



<Footnotes separator x="l">
  <Footnote :number=8><a href="https://dl.acm.org/doi/abs/10.1145/3447993.3483260" class="whitespace-normal text-left right-auto" rel="noreferrer" target="_blank" >Dongyao Chen, Mingke Wang, Chenxi He, Qing Luo, Yasha Iravantchi, Alanson Sample, Kang G Shin, and Xinbing Wang. 2021. MagX: Wearable, untethered hands tracking with passive magnets. In Proceedings of the 27th Annual International Conference on Mobile Computing and Networking, 269–282.</a></Footnote>
</Footnotes>

---
layout: figure
figureUrl: images/opening/FundamentalB.png
figureFootnoteNumber: 9
figureCaption: MAGIC：全自动罗盘校准技术
hideInToc: true
---

## 研究基础



<Footnotes separator x="l">
  <Footnote :number=9><a href="https://dl.acm.org/doi/abs/10.1145/3495243.3558760" class="whitespace-normal text-left right-auto" rel="noreferrer" target="_blank" >Mingke Wang, Qing Luo, Yasha Iravantchi, Xiaomeng Chen, Alanson Sample, Kang G Shin, Xiaohua Tian, Xinbing Wang, and Dongyao Chen. 2022. Automatic calibration of magnetic tracking. In Proceedings of the 28th Annual International Conference on Mobile Computing And Networking, 391–404.</a></Footnote>
</Footnotes>
---
layout:
---

## 文献翻译

ReSkin: versatile, replaceable, lasting tactile skins<sup>10</sup>
> 在这篇文章中，作者使用了磁塑胶材质制成的贴片进行压力检测。通过贴片外的磁力计记录磁场变化，使用机器学习方法训练模型计算触点位置和压力大小


<div class="my-10 grid grid-cols-3 gap-2 w-max items-center">
<img src="images/opening/ReSkin1.png" alt="Paddy Power Betfair" class="w-350px h-250px" />
<img src="images/opening/ReSkin2.png" alt="Petapilot" class="w-350px h-250px" />
</div>

<Footnotes separator x="l">
  <Footnote :number=10><a href="reskin.dev" class="whitespace-normal text-left right-auto" rel="noreferrer" target="_blank">Raunaq Bhirangi, Tess Hellebrekers, Carmel Majidi, and Abhinav Gupta. 2021. ReSkin: versatile, replaceable, lasting tactile skins. In 5th Annual Conference on Robot Learning.</a></Footnote>
</Footnotes>

---
layout:
---

# 毕设进度
| 时间  | 进度         | 备注                                   |
|-------|------------|----------------------------------------|
| 01-31 | 文献翻译     |                                        |
| 02-20 | 基本模型测试 | 测试电磁铁模型产生压力能否满足使用要求 |
| 03-20 | 文献调研     |                                        |
| 03-31 | 动态模型改进 | 测试通过控制电磁铁电流改变压力大小     |
| 04-15 | 数据收集     | 收集实验数据，评估模型表现              |
| 05-15 | 撰写报告     |                                        |