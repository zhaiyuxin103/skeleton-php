# Skeleton PHP

[![Latest Version on Packagist](https://img.shields.io/packagist/v/zhaiyuxin/skeleton-php?style=for-the-badge)](https://packagist.org/packages/zhaiyuxin/skeleton-php)
[![Total Downloads on Packagist](https://img.shields.io/packagist/dt/zhaiyuxin/skeleton-php?style=for-the-badge)](https://packagist.org/packages/zhaiyuxin/skeleton-php)
[![Build Status](https://img.shields.io/github/actions/workflow/status/zhaiyuxin103/skeleton-php/tests.yml?style=for-the-badge)](https://github.com/zhaiyuxin103/skeleton-php/actions)
[![Code Coverage](https://img.shields.io/codecov/c/github/zhaiyuxin103/skeleton-php?style=for-the-badge)](https://codecov.io/gh/zhaiyuxin103/skeleton-php)
[![Laravel](https://img.shields.io/badge/Laravel-12.x-red.svg?style=for-the-badge)](https://laravel.com)
[![PHP](https://img.shields.io/badge/PHP-8.4+-blue.svg?style=for-the-badge)](https://php.net)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=for-the-badge)](LICENSE)

一个用于快速创建 PHP 包的骨架模板项目。该项目提供了完整的开发工具链，包括代码风格检查、静态分析、测试框架等。

## 特性

- 🚀 基于现代 PHP 开发标准
- 🧪 集成 Pest 测试框架
- 🎨 Laravel Pint 代码风格检查
- 📊 PHPStan 静态代码分析
- 🔧 Orchestra Testbench 测试环境
- 📦 完整的 Composer 配置
- 🎯 Git hooks 集成
- 💻 开发环境快速搭建

## 系统要求

- PHP >= 8.4
- Composer
- Node.js & pnpm（用于前端工具链）

## 安装

### 1. 克隆项目

```bash
git clone https://github.com/zhaiyuxin/skeleton-php.git
cd skeleton-php
```

### 2. 安装 PHP 依赖

```bash
composer install
```

### 3. 安装 Node.js 依赖

```bash
pnpm install
```

## 使用方法

### 开发服务器

启动开发服务器：

```bash
composer serve
```

### 代码风格检查

运行代码风格检查和静态分析：

```bash
composer lint
```

这个命令会执行：

- Laravel Pint 代码风格修复
- PHPStan 静态代码分析

### 运行测试

```bash
composer test
```

### 构建项目

```bash
composer build
```

## 项目结构

```
skeleton-php/
├── src/                    # 源代码目录
│   └── helpers.php        # 辅助函数
├── tests/                 # 测试目录
│   ├── Feature/          # 功能测试
│   ├── Unit/            # 单元测试
│   ├── Pest.php         # Pest配置
│   └── TestCase.php     # 测试基类
├── workbench/            # 开发工作台
│   ├── app/             # 示例应用
│   ├── database/        # 数据库文件
│   ├── resources/       # 资源文件
│   └── routes/          # 路由文件
├── config/               # 配置文件
├── database/            # 数据库迁移
├── composer.json        # Composer配置
├── phpunit.xml         # PHPUnit配置
├── phpstan.neon.dist   # PHPStan配置
├── pint.json          # Laravel Pint配置
└── testbench.yaml     # Testbench配置
```

## 配置说明

### Composer脚本

项目提供了以下Composer脚本：

- `composer serve` - 启动开发服务器
- `composer lint` - 代码风格检查和静态分析
- `composer test` - 运行测试套件
- `composer build` - 构建工作台
- `composer clear` - 清理缓存
- `composer prepare` - 准备开发环境

### 代码风格

项目使用 Laravel Pint 进行代码风格检查，配置文件为 `pint.json`。主要规则包括：

- Laravel预设
- 严格类型声明
- 有序的类元素
- 严格比较
- 全限定类型导入

### 静态分析

使用 PHPStan 进行静态代码分析，配置文件为 `phpstan.neon.dist`。

### 测试框架

使用 Pest 作为测试框架，提供了简洁的测试语法和丰富的断言方法。

## 开发工作流

1. **创建新功能**：在 `src/` 目录下添加你的代码
2. **编写测试**：在 `tests/` 目录下添加相应的测试
3. **运行测试**：使用 `composer test` 确保功能正常
4. **代码检查**：使用 `composer lint` 检查代码风格和质量
5. **提交代码**：Git hooks 会自动运行代码检查

## Git Hooks

项目集成了Husky和lint-staged，在提交代码时会自动：

- 运行代码风格检查
- 执行静态分析
- 格式化代码

## 自定义配置

### 修改命名空间

在`composer.json`中修改PSR-4自动加载配置：

```json
{
  "autoload": {
    "psr-4": {
      "YourNamespace\\YourPackage\\": "src/"
    }
  }
}
```

## 贡献

欢迎提交 [Issue](https://github.com/zhaiyuxin103/skeleton-php/issues) 和 [Pull Request](https://github.com/zhaiyuxin103/skeleton-php/pulls) 来改进这个项目。

## 许可证

本项目基于MIT许可证开源。详情请查看 [LICENSE](LICENSE) 文件。

## 作者

**YuXin Zhai**

- Email: [zhaiyuxin103@hotmail.com](mailto:zhaiyuxin103@hotmail.com)
- GitHub: [@zhaiyuxin](https://github.com/zhaiyuxin)

## 致谢

- [Laravel](https://laravel.com/) - 提供了优秀的 PHP 开发工具
- [Pest](https://pestphp.com/) - 现代化的 PHP 测试框架
- [Orchestra Testbench](https://github.com/orchestral/testbench) - Laravel 包测试环境
