# README

## 画可 — 轻量级 AI 智能记账应用

**画可**是一款面向个人、家庭及小团队的轻量级智能记账应用。  
产品强调简洁与专注，融入侘寂美学设计，并结合本地规则 AI 提供自动分类、预算建议、消费分析等功能。  
所有数据安全地存储在您的设备本地，无需联网即可使用。

---

## 功能概览

- **记账管理**：快速记录收支，支持多分类选择与自定义分类（emoji 图标）。
- **预算规划**：AI 根据历史数据自动生成月度预算建议，支持一键采纳与手动调整。
- **储蓄目标**：设定储蓄计划，实时追踪进度，记账时显示对目标的影响。
- **财务仪表盘**：通过日/月/季图表、分类占比饼图和收支趋势，直观呈现财务状况。
- **数据管理器**：统一管理银行卡、电话卡、会员卡及实物资产，计算日均成本，支持生命周期状态切换（服役/退役/注销/卖出）。
- **数据导出**：支持导出交易记录为 CSV 文件。
- **跨平台支持**：一套代码运行于 Android、iOS（需 macOS 构建）和 Web。

---

## 快速体验

**Web 在线版**（浏览器直接打开）：  
[https://tsing-debug.github.io/expense-tracker/](https://tsing-debug.github.io/expense-tracker/)

**Android 安装包**：  
请从 [Releases 页面](https://github.com/Tsing-debug/expense-tracker/releases) 下载最新的 APK 文件。

> iOS 版本可通过源码在 macOS 环境下自行编译，或查看 GitHub Actions 中的构建产物。

---

## 项目源码

本项目托管于 GitHub：  
[https://github.com/Tsing-debug/expense-tracker](https://github.com/Tsing-debug/expense-tracker)

---

## 本地运行

若您希望在本地运行该项目，请确保已安装 [Flutter](https://flutter.dev) SDK（版本 3.0 以上）。

1. 克隆仓库
   ```bash
   git clone https://github.com/Tsing-debug/expense-tracker.git
   cd expense-tracker
   ```

2. 获取依赖
   ```bash
   flutter pub get
   ```

3. 生成 Hive 适配器
   ```bash
   flutter packages pub run build_runner build --delete-conflicting-outputs
   ```

4. 运行应用
   ```bash
   # Web 端
   flutter run -d chrome

   # Android 端（需连接设备或模拟器）
   flutter run
   ```

---

## 技术栈

- **框架**：Flutter（Dart）
- **状态管理**：Provider
- **本地存储**：Hive
- **图表**：fl_chart
- **平台支持**：Android / iOS / Web

项目使用纯本地规则实现自动分类、预算建议与财务分析，未依赖任何外部 API。

---

## 项目结构

```
lib/
├── main.dart                     # 应用入口
├── models/                       # 数据模型
│   ├── transaction.dart          # 交易记录
│   ├── category.dart             # 收支分类
│   ├── account.dart              # 账户
│   ├── budget.dart               # 预算
│   ├── goal.dart                 # 储蓄目标
│   └── asset.dart                # 资产（银行卡/电话卡/实物）
├── providers/                    # 状态管理
├── screens/                      # 页面
│   ├── main_shell.dart           # 底部导航壳
│   ├── home_screen.dart          # 首页（流水）
│   ├── add_transaction_screen.dart
│   ├── dashboard_screen.dart     # 仪表盘（统计）
│   ├── data_manager_screen.dart  # 数据管理器
│   ├── budget_screen.dart
│   ├── goal_screen.dart
│   └── settings_screen.dart
├── services/                     # 业务逻辑
│   ├── database_service.dart
│   ├── dashboard_service.dart
│   ├── budget_service.dart
│   ├── goal_service.dart
│   ├── asset_service.dart
│   ├── cabinet_score_service.dart
│   └── export_service.dart
└── widgets/                      # 可复用组件
    └── transaction_tile.dart
```

---

## 设计理念

画可尝试在财务管理工具中融入一点侘寂（wabi-sabi）美学：  
不追求繁复的装饰，而是通过大面积留白、老纸色背景、墨黑文字与朱红点缀，营造安静、克制的视觉氛围。  
字体选用了霞鹜文楷，希望传递一份手写本般的私密与温度。

---

## 关于项目

本项目主要面向技术验证与学习交流，不以商业盈利为目的。  
如果您是老师或有任何建议，欢迎通过 GitHub Issues 与我联系。
