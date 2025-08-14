# 🎲 数制编码魔方 (Number System & Coding Cube)

**Language / 语言**: [English](README-EN.md) | 中文

一个基于 Astro 构建的计算机组成原理可视化学习工具，专为理解数制转换和机器码编码而设计。

## ✨ 功能特性

### 🔄 实时多进制转换器 (Real-time Multi-Base Converter)
- **实时转换**: 无需点击按钮，输入即时转换
- **多进制支持**: 二进制、八进制、十进制、十六进制
- **智能验证**: 自动验证输入是否符合选定进制
- **错误处理**: 友好的错误提示和状态显示

### 🔧 机器码编码解析器 (Machine Code Encoder/Decoder)
- **带符号整数表示**: 支持正数和负数的编码
- **三种编码方式**:
  - 原码 (Sign-Magnitude)
  - 反码 (One's Complement) 
  - 补码 (Two's Complement)
- **多位宽支持**: 8位、16位、32位
- **详细解释**: 每种编码方式的计算过程说明
- **范围检查**: 自动检查数值是否在指定位宽范围内

## 🚀 技术栈

- **框架**: [Astro](https://astro.build/) - 现代静态站点生成器
- **包管理器**: [pnpm](https://pnpm.io/) - 快速、节省磁盘空间的包管理器
- **样式**: 原生 CSS，响应式设计
- **脚本**: 原生 JavaScript，面向对象设计

## 📁 项目结构

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   └── Welcome.astro
│   ├── layouts/
│   │   └── Layout.astro          # 主布局文件
│   └── pages/
│       └── index.astro           # 主页面，包含两个核心功能
├── astro.config.mjs              # Astro 配置文件
├── package.json                  # 项目依赖和脚本
├── pnpm-lock.yaml               # pnpm 锁定文件
└── README.md                    # 项目说明文档
```

## 🛠️ 开发指南

### 环境要求
- Node.js 18+ 
- pnpm 8+

### 安装依赖
```bash
pnpm install
```

### 启动开发服务器
```bash
pnpm dev
```
访问 `http://localhost:4321` 查看应用

### 构建生产版本
```bash
pnpm build
```

### 预览生产构建
```bash
pnpm preview
```

## 🎯 使用说明

### 多进制转换器使用方法
1. 在输入框中输入数值
2. 选择输入数值的进制（二进制、八进制、十进制、十六进制）
3. 系统会实时显示该数值在其他三种进制下的表示

**示例**:
- 输入 `255`，选择十进制 → 自动显示二进制 `11111111`、八进制 `377`、十六进制 `FF`
- 输入 `FF`，选择十六进制 → 自动显示二进制 `11111111`、八进制 `377`、十进制 `255`

### 机器码编码解析器使用方法
1. 输入一个十进制整数（可以是正数或负数）
2. 选择数据位宽（8位、16位、32位）
3. 系统会显示该数的原码、反码、补码表示，并提供详细解释

**示例**:
- 输入 `-5`，选择8位 → 显示：
  - 原码: `1000 0101`
  - 反码: `1111 1010` 
  - 补码: `1111 1011`

## 🎓 教育价值

这个工具特别适合：
- **计算机组成原理课程**: 理解数制转换和机器码编码
- **数字逻辑课程**: 学习不同进制之间的关系
- **程序设计基础**: 理解计算机内部数据表示
- **自学编程**: 可视化学习计算机基础概念

## 🔧 核心算法

### 多进制转换算法
```javascript
// 验证输入是否符合指定进制
isValidForBase(input, base) {
    const validChars = '0123456789ABCDEF'.slice(0, base);
    return input.toUpperCase().split('').every(char => validChars.includes(char));
}

// 转换为目标进制
const decimal = parseInt(input, sourceBase);
const result = decimal.toString(targetBase);
```

### 机器码编码算法
```javascript
// 原码：符号位 + 数值的二进制表示
signMagnitude = (isNegative ? '1' : '0') + absValue.toString(2).padStart(bits-1, '0');

// 反码：负数时数值位取反
onesComplement = isNegative ? 
    '1' + absValue.toString(2).padStart(bits-1, '0').split('').map(bit => bit === '0' ? '1' : '0').join('') :
    signMagnitude;

// 补码：反码 + 1
twosComplement = isNegative ? addOne(onesComplement) : signMagnitude;
```

## 🎨 设计特色

- **响应式设计**: 支持桌面和移动设备
- **实时反馈**: 输入即时转换，无需等待
- **错误处理**: 智能验证和友好的错误提示
- **可视化**: 清晰的二进制格式化显示（每4位分组）
- **教育导向**: 详细的计算过程解释

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情

## 🙏 致谢

- [Astro](https://astro.build/) - 优秀的静态站点生成器
- [pnpm](https://pnpm.io/) - 高效的包管理器
- 所有为计算机教育做出贡献的开发者们

---

**🎯 让学习计算机组成原理变得更加直观和有趣！**