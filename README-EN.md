# 🎲 Number System & Coding Cube

**Language / 语言**: English | [中文](README.md)

A computer architecture visualization learning tool built with Astro, designed for understanding number system conversion and machine code encoding.

## ✨ Features

### 🔄 Real-time Multi-Base Converter
- **Real-time conversion**: Instant conversion without clicking buttons
- **Multi-base support**: Binary, octal, decimal, hexadecimal
- **Smart validation**: Automatic validation of input for selected base
- **Error handling**: Friendly error messages and status display

### 🔧 Machine Code Encoder/Decoder
- **Signed integer representation**: Support for positive and negative number encoding
- **Three encoding methods**:
  - Sign-Magnitude
  - One's Complement
  - Two's Complement
- **Multiple bit-width support**: 8-bit, 16-bit, 32-bit
- **Detailed explanations**: Step-by-step calculation process for each encoding method
- **Range checking**: Automatic validation of values within specified bit-width range

## 🚀 Tech Stack

- **Framework**: [Astro](https://astro.build/) - Modern static site generator
- **Package Manager**: [pnpm](https://pnpm.io/) - Fast, disk space efficient package manager
- **Styling**: Native CSS with responsive design
- **Scripting**: Native JavaScript with object-oriented design

## 📁 Project Structure

```text
/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   └── Welcome.astro
│   ├── layouts/
│   │   └── Layout.astro          # Main layout file
│   └── pages/
│       └── index.astro           # Main page with two core features
├── astro.config.mjs              # Astro configuration file
├── package.json                  # Project dependencies and scripts
├── pnpm-lock.yaml               # pnpm lock file
└── README.md                    # Project documentation
```

## 🛠️ Development Guide

### Requirements
- Node.js 18+ 
- pnpm 8+

### Install Dependencies
```bash
pnpm install
```

### Start Development Server
```bash
pnpm dev
```
Visit `http://localhost:4321` to view the application

### Build for Production
```bash
pnpm build
```

### Preview Production Build
```bash
pnpm preview
```

## 🎯 Usage Instructions

### Multi-Base Converter Usage
1. Enter a number in the input field
2. Select the base of the input number (binary, octal, decimal, hexadecimal)
3. The system will display the number in the other three bases in real-time

**Examples**:
- Input `255`, select decimal → Automatically displays binary `11111111`, octal `377`, hexadecimal `FF`
- Input `FF`, select hexadecimal → Automatically displays binary `11111111`, octal `377`, decimal `255`

### Machine Code Encoder/Decoder Usage
1. Enter a decimal integer (can be positive or negative)
2. Select the bit width (8-bit, 16-bit, 32-bit)
3. The system will display the sign-magnitude, one's complement, and two's complement representations with detailed explanations

**Example**:
- Input `-5`, select 8-bit → Displays:
  - Sign-Magnitude: `1000 0101`
  - One's Complement: `1111 1010` 
  - Two's Complement: `1111 1011`

## 🎓 Educational Value

This tool is particularly suitable for:
- **Computer Architecture courses**: Understanding number system conversion and machine code encoding
- **Digital Logic courses**: Learning relationships between different number systems
- **Programming Fundamentals**: Understanding internal data representation in computers
- **Self-learning programming**: Visual learning of fundamental computer concepts

## 🔧 Core Algorithms

### Multi-Base Conversion Algorithm
```javascript
// Validate input for specified base
isValidForBase(input, base) {
    const validChars = '0123456789ABCDEF'.slice(0, base);
    return input.toUpperCase().split('').every(char => validChars.includes(char));
}

// Convert to target base
const decimal = parseInt(input, sourceBase);
const result = decimal.toString(targetBase);
```

### Machine Code Encoding Algorithm
```javascript
// Sign-Magnitude: Sign bit + binary representation of absolute value
signMagnitude = (isNegative ? '1' : '0') + absValue.toString(2).padStart(bits-1, '0');

// One's Complement: Invert value bits for negative numbers
onesComplement = isNegative ? 
    '1' + absValue.toString(2).padStart(bits-1, '0').split('').map(bit => bit === '0' ? '1' : '0').join('') :
    signMagnitude;

// Two's Complement: One's complement + 1
twosComplement = isNegative ? addOne(onesComplement) : signMagnitude;
```

## 🎨 Design Features

- **Responsive design**: Support for desktop and mobile devices
- **Real-time feedback**: Instant conversion on input, no waiting required
- **Error handling**: Smart validation and friendly error messages
- **Visualization**: Clear binary formatting display (grouped by 4 bits)
- **Educational focus**: Detailed calculation process explanations

## 🤝 Contributing

Issues and Pull Requests are welcome!

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## 🙏 Acknowledgments

- [Astro](https://astro.build/) - Excellent static site generator
- [pnpm](https://pnpm.io/) - Efficient package manager
- All developers contributing to computer science education

---

**🎯 Making computer architecture learning more intuitive and engaging!**