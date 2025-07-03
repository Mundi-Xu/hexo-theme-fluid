# WebGL流体背景使用指南

## 功能概述

WebGL流体背景为您的Hexo博客提供了一个令人惊艳的动态背景效果。该功能基于GPU加速的流体模拟，创造出随用户交互而变化的流动色彩效果。

## 特性
- 🌊 **流体物理模拟** - 真实的流体动力学效果
- 🎨 **实时颜色变化** - 动态生成的彩色涡流
- 📱 **响应式设计** - 自动适配移动设备
- ⚡ **GPU加速** - 利用WebGL获得最佳性能
- 🌙 **暗色模式支持** - 自动适配主题模式
- 🔧 **高度可配置** - 丰富的参数调节选项

## 启用方式

### 1. 基础启用

在主题配置文件 `hexo-theme-fluid-mini/_config.yml` 中找到 `webgl_fluid_bg` 配置项：

```yaml
# WebGL流体背景配置
webgl_fluid_bg:
  enable: true  # 设置为 true 启用
```

### 2. 详细配置

```yaml
webgl_fluid_bg:
  enable: true
  
  # 流体模拟参数
  config:
    # 模拟分辨率 (64-256，越高越精细但性能消耗越大)
    sim_resolution: 128
    
    # 染料分辨率 (512-2048，影响视觉效果清晰度)
    dye_resolution: 1024
    
    # 密度消散率 (0.1-5.0，控制颜色消失速度)
    density_dissipation: 1
    
    # 速度消散率 (0.1-1.0，控制流动衰减)
    velocity_dissipation: 0.2
    
    # 压力 (0.1-2.0，影响流体行为)
    pressure: 0.8
    
    # 压力迭代次数 (10-50，影响计算精度)
    pressure_iterations: 20
    
    # 涡度 (0-50，控制旋涡强度)
    curl: 30
    
    # 颜色飞溅半径 (0.1-1.0)
    splat_radius: 0.25
    
    # 颜色飞溅力度 (1000-10000)
    splat_force: 6000
    
    # 是否启用着色 (增强视觉效果)
    shading: true
    
    # 是否启用彩色 (关闭后为单色效果)
    colorful: true
    
    # 颜色更新速度 (1-20)
    color_update_speed: 10
```

## 性能优化建议

### 桌面设备
```yaml
sim_resolution: 128
dye_resolution: 1024
pressure_iterations: 20
```

### 移动设备
```yaml
sim_resolution: 64
dye_resolution: 512
pressure_iterations: 15
```

### 高性能设备
```yaml
sim_resolution: 256
dye_resolution: 2048
pressure_iterations: 30
```

## 交互方式

- **鼠标悬停** - 产生颜色轨迹
- **点击拖拽** - 创建强烈的色彩飞溅
- **触摸滑动** (移动端) - 生成流动效果

## 兼容性

### 支持的浏览器
- ✅ Chrome 50+
- ✅ Firefox 45+
- ✅ Safari 10+
- ✅ Edge 12+
- ✅ iOS Safari 10+
- ✅ Chrome for Android 50+

### 系统要求
- 支持WebGL的GPU
- 2GB+ 显存 (推荐)
- 现代浏览器环境

## 故障排除

### WebGL不支持
如果浏览器不支持WebGL，会自动降级到渐变背景。

### 性能问题
- 降低 `sim_resolution` 和 `dye_resolution`
- 减少 `pressure_iterations`
- 关闭 `shading` 选项

### 移动端优化
系统会自动检测移动设备并降低相关参数。

## 技术实现

该功能基于以下技术：
- **WebGL 2.0/1.0** - GPU计算和渲染
- **GLSL着色器** - 流体物理模拟
- **双缓冲技术** - 平滑动画效果
- **帧缓冲对象** - 多步渲染流程

## 自定义开发

如需深度定制，可以修改：
- `source/js/fluid-background.js` - 核心逻辑
- `source/css/fluid-background.css` - 样式调整
- `layout/_partials/header/banner.ejs` - 模板集成

## 注意事项

1. **性能影响** - WebGL渲染会增加GPU使用率
2. **电池消耗** - 移动设备可能增加电池消耗  
3. **兼容性检查** - 建议保留传统背景作为降级方案
4. **SEO影响** - 动态背景不影响SEO表现

## 最佳实践

1. 根据目标用户群体选择合适的性能设置
2. 在不同设备上测试效果和性能
3. 保持文字内容的可读性
4. 定期检查浏览器兼容性更新

启用WebGL流体背景后，您的博客将拥有独特而吸引人的视觉体验！ 