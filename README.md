# Waveforms 波形

![Convergence Demo](demo.gif)

This interactive guide introduces and explores waveforms. It covers how to read waveform graphs, goes over the fundamental physics of sound, teaches how it relates to music and harmony, and demonstrates how to build complex tones from simple ones.

这个交互式指南介绍并探索波形。它涵盖如何阅读波形图，讲解声音的基本物理原理，教授其与音乐和和声的关系，并演示如何从简单音调构建复杂音调。

This guide is aimed at a general audience–no prior knowledge is required.

本指南面向一般受众——无需任何预备知识。

[**Check it out!**](https://waveforms.surge.sh)
[**立即体验！**](https://waveforms.surge.sh)

---

### Future plans 未来计划

I'm toying with the idea of making this a series. There are other interesting audio concepts to explore. Off the top of my head:

我在考虑将其制作成系列内容。还有其他有趣的音频概念值得探索。我能想到的有：

- FFT (Fast Fourier Transform 快速傅里叶变换)
- Human perception of sound 人类声音感知
- Phase offset effects like phasers, flangers, delays, and reverb 相位偏移效果，如移相器、镶边器、延迟和混响
- Distortion (clip distortion, bit reduction) 失真（削波失真、位深缩减）
- FM/AM synthesis FM/AM 合成
- Envelope generators and filters 包络生成器和滤波器

It's likely I won't get to this anytime soon, but do let me know if you think there's a need for interactive explanations of these concepts!

我可能短期内无法实现这些内容，但如果您认为有必要对这些概念进行交互式解释，请告诉我！

### How It's Made 制作方式

This tutorial-thingy is purely front-end, built with React. No state management library was needed. Styled with `styled-components`.

这个教程完全是前端项目，使用 React 构建。无需状态管理库。样式采用`styled-components`。

The waveforms are rendered with SVG (although they can also render to Canvas with the change of a prop), and the air molecule grids render to Canvas. I used the fancy new IntersectionObserver to handle the scroll-based logic, with a fallback to a simple scroll listener.

波形通过 SVG 渲染（也可通过更改属性渲染到 Canvas 上），而空气分子网格渲染到 Canvas 上。我使用新颖的 IntersectionObserver 处理基于滚动的逻辑，并提供简单滚动监听器作为备选方案。

> NOTE: This was a very interesting project from a technical perspective! I needed to draw Waveforms in lots of different configurations and states. Waveforms can be one of a series of predefined shapes, or arbitrary shapes (as is the case when converging multiple waveforms together). Waveforms can be "playing", and any state change that can happen (even changing the waveform shape) needs to work whether it's staying still or playing. Also, every transition should use spring physics. Also, it should be performant while doing all of this.
>
> 注意：从技术角度看，这是一个非常有趣的项目！我需要绘制各种不同配置和状态的波形。波形可以是一系列预定义形状之一，也可以是任意形状（如合并多个波形时的情况）。波形可以处于"播放"状态，任何状态变化（甚至改变波形形状）都需要在静止或播放状态下正常工作。此外，每个过渡都应使用弹簧物理效果。同时，在实现所有这些功能的同时还要保持良好的性能。
>
> I started writing up how it works, but I realized that it is super non-trivial, and it deserves a proper blog post. I would like to write that blog post at some point. If this interests you, feel free to [poke me on Twitter](https://twitter.com/JoshWComeau) and remind me.
>
> 我开始写下它的工作原理，但我发现这非常复杂，值得写一篇专门的博客文章。我希望在某个时候写这篇博客文章。如果您对此感兴趣，欢迎在[Twitter 上联系我](https://twitter.com/JoshWComeau)并提醒我。
>
> You can also poke around yourself! Check out all the components that start with `Waveform`, like `WaveformPlayer` or `WaveformTween`.
>
> 您也可以自己探索！查看所有以`Waveform`开头的组件，比如`WaveformPlayer`或`WaveformTween`。

### Running locally 本地运行

Want to run this on your machine? it _should_ be as simple as `git clone`, `yarn install`, and `yarn:start`. Let me know if that fails.

想在您的机器上运行吗？它*应该*只需简单执行`git clone`，`yarn install`和`yarn start`。如果失败请告诉我。

### 详细安装与运行指南 Detailed Installation and Running Guide

#### 系统要求 System Requirements

- Node.js 14.0+
- npm 6.0+ 或 yarn 1.22+
- 现代浏览器（支持 ES6 和 Canvas/SVG）

#### 安装步骤 Installation Steps

1. **克隆仓库 Clone the repository**

   ```bash
   git clone https://github.com/username/waveforms.git
   cd waveforms
   ```

2. **安装依赖 Install dependencies**

   ```bash
   # 使用yarn
   yarn install

   # 或使用npm
   npm install
   ```

3. **启动开发服务器 Start development server**

   ```bash
   # 使用yarn
   yarn start

   # 或使用npm
   npm start
   ```

   开发服务器将在 http://localhost:3000 启动

#### 构建生产版本 Build for Production

```bash
# 使用yarn
yarn build

# 或使用npm
npm run build
```

#### 常见问题排查 Troubleshooting

- **依赖安装失败 Dependency installation fails**

  - 尝试删除 node_modules 文件夹并重新安装
  - 确保您使用的 Node.js 版本兼容

- **开发服务器启动失败 Development server fails to start**

  - 检查端口 3000 是否已被占用
  - 查看控制台错误信息，确认所有依赖都已正确安装

- **渲染问题 Rendering issues**
  - 确保您的浏览器支持现代 Canvas 和 SVG API
  - 尝试禁用浏览器扩展，特别是与内容或脚本相关的扩展

#### 环境变量 Environment Variables

创建`.env`文件自定义以下变量（可选）:

```
REACT_APP_AUDIO_ENABLED=true
REACT_APP_DEFAULT_WAVEFORM=sine
```

### Contributing 贡献

Please open issues describing changes you'd like to contribute before spending any time working on them; this is a personal side-project, and I open-sourced it primarily as an educational thing, for those curious how it was built. I'm not actively seeking external contributions, and there would be a bit of friction (this repo is no longer the "source of truth" for the project, as it lives on The Pudding).

在花时间进行任何工作之前，请先开设议题描述您想贡献的更改；这是个人的副项目，我将其开源主要是作为教育资源，供那些好奇它如何构建的人参考。我并不积极寻求外部贡献，且可能会有一些摩擦（这个仓库不再是项目的"真实来源"，因为它现在存在于 The Pudding 上）。

### 项目模块功能详细说明 Project Module Details

#### 核心组件 Core Components

1. **WaveformPlayer**

   - 管理波形的播放状态和控制
   - 处理播放/暂停逻辑
   - 控制波形动画速度和方向

2. **WaveformTween**

   - 实现波形之间的平滑过渡动画
   - 使用弹簧物理效果处理状态变化
   - 确保形状变化时的连续性和流畅性

3. **WaveformAxis**

   - 渲染波形图的 X 和 Y 轴
   - 提供刻度和标签
   - 支持自定义调整和主题定制

4. **WaveformGenerator**
   - 生成各种预定义波形（正弦、方形、锯齿、三角形等）
   - 提供数学计算功能来生成波形数据点
   - 支持自定义波形参数

#### 交互式功能 Interactive Features

1. **波形合成器 Waveform Combiner**

   - 允许用户组合多个波形创建复杂音调
   - 实时计算和显示合成波形
   - 提供交互式控件调整每个组件波形的振幅

2. **谐波展示器 Harmonic Visualizer**

   - 展示基频和各次谐波的关系
   - 可视化演示傅里叶级数概念
   - 通过动画展示不同谐波如何形成复杂波形

3. **参数控制器 Parameter Controllers**
   - 提供交互式滑块控制频率、振幅和相位
   - 实时更新波形显示
   - 具有数值输入和预设功能

#### 渲染系统 Rendering System

1. **SVG 渲染器 SVG Renderer**

   - 高精度矢量波形绘制
   - 适用于静态和低频率波形动画
   - 支持高级样式和滤镜效果

2. **Canvas 渲染器 Canvas Renderer**

   - 优化的高性能波形绘制
   - 适用于复杂动画和高帧率要求
   - 包含缓存机制提高性能

3. **分子模拟器 Molecule Simulator**
   - 使用 Canvas 绘制空气分子模拟
   - 可视化声波如何通过介质传播
   - 支持不同密度和波长的模拟

#### 辅助工具 Utility Functions

1. **波形数学库 Waveform Math Library**

   - 实现各种波形生成算法
   - 提供波形操作和变换函数
   - 包含傅里叶变换和频谱分析工具

2. **动画控制器 Animation Controller**
   - 管理基于时间的动画循环
   - 处理动画帧率和同步
   - 提供暂停、恢复和速度控制功能
