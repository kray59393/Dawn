# Dawn Extension Bot [1.5]

<div align="center">
  <img src="./console/images/console.png" alt="Dawn Extension Bot Console" width="600"/>
</div>


**我的推特: [@Hy78516012)**


---

## 🚀 功能

- ✅ 自动账户注册和登录
- 📧 自动账户重新验证
- 🌾 自动完成所有任务
- 💰 自动获取积分
- 📊 导出账户统计数据
- 🔄 保持会话功能
- 🧩 高级跳码

---

## 💻 环境及需要的

- Python >= 3.11
- 互联网连接
- 用于注册的有效电子邮件账户
- 有效的代理（可选）

---

## 🛠️ 设置

1. 克隆仓库：
   ```bash
   git clone [repository URL]
   ```
2. 创建并激活虚拟环境：
   ```bash
   python -m venv venv
   cd venv/Scripts
   activate
   cd ../..
   ```
3. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

---

## ⚙️ 配置

### settings.yaml

该文件包含机器人的常规设置：

```yaml
threads: 5 # 同时进行账户操作的线程数
keepalive_interval: 120 # 保持会话请求之间的延迟（秒）
referral_code: "YOUR_REFERRAL_CODE" # 注册推荐码
captcha_service: "2captcha" # 验证码解决服务（2captcha或anticaptcha）
two_captcha_api_key: "YOUR_2CAPTCHA_API_KEY"
anti_captcha_api_key: "YOUR_ANTICAPTCHA_API_KEY"

imap_settings: # 电子邮件提供商的IMAP设置
  gmail.com: imap.gmail.com
  outlook.com: imap-mail.outlook.com
  # 根据需要添加更多电子邮件提供商
```

### 其他配置文件

#### 📁 register.txt
包含注册账户信息。
```
格式：
email:password
email:password
...
```

#### 📁 farm.txt
包含用于获取积分和完成任务的账户信息。
```
格式：
email:password
email:password
...
```

#### 📁 proxies.txt
包含代理信息。
```
格式：
http://user:pass@ip:port
http://ip:port:user:pass
http://ip:port@user:pass
http://user:pass:ip:port
...
```

---

## 🚀 使用

1. 确保所有配置文件已正确设置。
2. 运行机器人：
   ```bash
   python run.py
   ```

---

## ⚠️ 重要提示

- 建议的保持会话请求之间的延迟为120秒。
- 如果有未验证的账户，可以再次使用`register`模块重新验证。
- 由于验证码复杂性的变化，现在使用外部服务（2captcha，anti-captcha）来解决验证码。
- 使用数据库来优化登录过程，通过存储授权令牌。
- 对于像Gmail这样的电子邮件服务，可能需要使用应用程序专用密码而不是常规电子邮件密码。

---

## 🔧 故障排除

- **电子邮件验证问题**：检查`settings.yaml`中的电子邮件提供商IMAP设置。
- **验证码问题**：验证您的验证码服务API密钥和账户余额。
- **代理问题**：确保您的代理格式正确且代理功能正常。

---