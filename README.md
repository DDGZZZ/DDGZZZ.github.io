# 政务管理系统

基于MCP（Model Context Protocol）的智能政务管理系统，提供便捷的政务服务体验。

## 功能特性

### 🔐 双重登录模式
- **普通用户登录**：面向普通市民的政务服务
- **政务人员登录**：面向政府工作人员的专用模式

### 🏠 首页功能
- **智能搜索**：快速查找要办理的事务
- **搜索历史**：记录用户搜索历史，提升使用体验
- **常见事务**：提供常用事务的快速入口
- **快速入口**：办事指南、附近网点、在线咨询、进度查询

### 📋 事务管理
- **事务列表**：显示用户正在办理的所有事务
- **进度跟踪**：实时显示办理进度和状态
- **详细信息**：点击查看办理步骤、时间节点、位置等信息
- **状态管理**：支持待处理、办理中、已完成、已拒绝等状态

### 📖 政策解读
- **政策列表**：根据用户地理位置推送相关政策
- **分类筛选**：按政策类型进行筛选
- **详细内容**：点击查看政策完整内容和解读
- **标签系统**：政策标签便于分类和搜索

### 👤 个人中心
- **用户信息**：显示用户基本信息和登录状态
- **设置选项**：账户设置、隐私安全、帮助中心
- **模式切换**：普通用户可切换为政务人员模式
- **退出登录**：安全退出当前账户

## 技术栈

- **前端框架**：Next.js 14 + React 18
- **样式框架**：Tailwind CSS
- **状态管理**：Zustand
- **图标库**：Lucide React
- **类型安全**：TypeScript
- **表单处理**：React Hook Form

## 项目结构

```
├── app/                    # Next.js App Router
│   ├── globals.css        # 全局样式
│   ├── layout.tsx         # 根布局
│   ├── page.tsx           # 主页面
│   └── login/             # 登录页面
├── components/            # React组件
│   ├── BottomNavigation.tsx
│   ├── HomePage.tsx
│   ├── TransactionsPage.tsx
│   ├── PoliciesPage.tsx
│   └── ProfilePage.tsx
├── store/                # 状态管理
│   └── index.ts
├── types/                # TypeScript类型定义
│   └── index.ts
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── README.md
```

## 快速开始

### 安装依赖

```bash
npm install
```

### 开发模式

```bash
npm run dev
```

### 构建生产版本

```bash
npm run build
```

### 启动生产服务器

```bash
npm start
```

## 主要功能模块

### 1. 用户认证系统
- 支持普通用户和政务人员两种登录模式
- 用户信息持久化存储
- 安全的登录状态管理

### 2. 事务管理系统
- 事务创建和跟踪
- 多步骤办理流程
- 实时进度更新
- 详细的状态管理

### 3. 政策解读系统
- 基于地理位置的政策推送
- 政策分类和标签
- 完整的政策内容展示
- 政策搜索和筛选

### 4. 个人中心
- 用户信息管理
- 设置和偏好配置
- 模式切换功能
- 安全退出机制

## 数据模型

### 用户模型 (User)
```typescript
interface User {
  id: string;
  name: string;
  phone: string;
  idCard: string;
  userType: 'normal' | 'government';
  location: {
    province: string;
    city: string;
    district: string;
  };
}
```

### 事务模型 (Transaction)
```typescript
interface Transaction {
  id: string;
  title: string;
  description: string;
  status: 'pending' | 'processing' | 'completed' | 'rejected';
  type: string;
  createdAt: string;
  updatedAt: string;
  steps: TransactionStep[];
  location: string;
  estimatedTime: string;
  requiredDocuments: string[];
}
```

### 政策模型 (Policy)
```typescript
interface Policy {
  id: string;
  title: string;
  summary: string;
  content: string;
  category: string;
  publishDate: string;
  effectiveDate: string;
  location: string;
  tags: string[];
  author: string;
  isNew: boolean;
}
```

## 界面设计

### 设计原则
- **简洁明了**：界面简洁，信息层次清晰
- **响应式设计**：适配不同屏幕尺寸
- **用户友好**：操作简单，反馈及时
- **政务风格**：符合政务系统的专业性和权威性

### 色彩方案
- **主色调**：蓝色系 (#3B82F6)
- **辅助色**：灰色系 (#6B7280)
- **状态色**：绿色(成功)、黄色(警告)、红色(错误)

## 未来规划

### 短期目标
- [ ] 添加更多事务类型
- [ ] 完善政策搜索功能
- [ ] 增加用户反馈系统
- [ ] 优化移动端体验

### 长期目标
- [ ] 集成真实的后端API
- [ ] 添加数据可视化功能
- [ ] 实现智能推荐系统
- [ ] 支持多语言国际化

## 贡献指南

1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开 Pull Request

## 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 联系方式

如有问题或建议，请通过以下方式联系：

- 项目 Issues：[GitHub Issues](https://github.com/your-repo/issues)
- 邮箱：your-email@example.com

---

**注意**：这是一个演示项目，实际部署时需要配置真实的后端服务和数据库。 