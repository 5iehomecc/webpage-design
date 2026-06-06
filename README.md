# 🌍 全球时区转换 Web 应用

一个优雅的苹果风格时区转换工具，支持多个城市之间的实时时间转换，自动识别夏令时（DST），并提供昼夜视觉区分。

## ✨ 功能特性

- **多城市支持** - 北京、马德里、赫尔辛基、苏黎世、密尔沃基 5 个城市
- **自动 DST 识别** - 根据输入日期自动识别夏令时/冬令时
- **双向时间转换** - 任一城市作为基准，实时转换其他城市时间
- **苹果风格 UI** - 现代化的卡片式设计，流畅的交互动画
- **昼夜视觉区分** - 白天（6:00-17:59）使用太阳图标，夜间（18:00-5:59）使用月亮图标
- **国旗色彩** - 采用 zhaoguoqi.com 官方颜色
- **内联 SVG Favicon** - 蓝色地球+时钟指针设计，零网络请求
- **性能优化** - 使用 `Intl.DateTimeFormat` 缓存和 `formatToParts()` 替代字符串解析

## 🚀 在线演示

访问应用：[时区转换](https://5iehome.cc/timezone-converter.html)

## 📱 使用方法

1. 打开应用页面
2. 选择日期和时间（默认使用当前北京时间）
3. 点击任意城市卡片，该城市将成为新的基准时间
4. 其他城市卡片会自动显示对应的时间
5. 点击"重置"按钮恢复初始状态

## 🛠 技术实现

### 核心技术

- **IANA 时区数据库** - 通过 `Intl.DateTimeFormat` API 实现准确的时区转换
- **UTC 中转** - 使用 UTC 作为中转时间，避免浏览器时区依赖
- **DST 检测** - 优先使用 `timeZoneName: 'long'` 读取关键词，回退方案比较 1 月和 7 月偏移量
- **性能优化** - DateTimeFormat 缓存池 + `formatToParts()` 直接计算

### 性能优化

1. **DateTimeFormat 缓存池** - 避免重复创建开销
2. **卡片预创建 DateTimeFormat** - render() 直接复用
3. **事件委托** - 减少事件监听器数量
4. **DocumentFragment** - 批量创建卡片
5. **内联 SVG favicon** - 零网络请求

### 浏览器兼容性

- Chrome 61+
- Firefox 58+
- Safari 11.1+
- Edge 79+

## 📂 项目结构

```
/workspace/
└── timezone-converter.html  # 唯一的应用文件（HTML + CSS + JS）
```

## 🎨 UI 设计

- **主题色**：苹果蓝 (#007aff)
- **昼夜切换**：白天使用太阳图标，夜间使用月亮图标
- **卡片高亮**：基准城市使用金黄色边框 (#FFD54F) 高亮
- **国旗色彩**：每个城市使用对应国旗的官方颜色

## 📄 许可证

© 2024 [E家分享](https://www.5iehome.cc). All rights reserved.

## 🔗 相关链接

- [E家分享](https://www.5iehome.cc)
- [GitHub 仓库](https://github.com/5iehomecc/webpage-design)
