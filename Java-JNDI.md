# JNDI
是一种Java漏洞
## JNDI注入攻击

### 定义及原理
JNDI（Java Naming and Directory Interface）注入攻击是一种利用Java应用程序中的JNDI功能的漏洞进行攻击的技术。JNDI是Java中用于访问命名和目录服务的API，允许应用程序通过名称来查找和访问对象。JNDI注入攻击利用了应用程序对外部数据的信任，通过构造恶意的JNDI名称来执行恶意操作。

### 漏洞

1. **远程代码执行漏洞**： 如果应用程序存在远程代码执行漏洞，攻击者可以在攻击过程中构造恶意的JNDI名称，并在应用程序中执行恶意代码。
2. **未经验证的用户输入**： 如果应用程序未正确验证或过滤用户提供的输入，攻击者可以在输入中插入恶意的JNDI名称，从而执行恶意操作。
3. **Web容器配置不当**： 如果Web容器（如Tomcat）的JNDI资源配置不当，可能会导致JNDI注入漏洞，攻击者可以利用此漏洞执行恶意代码。


### 攻击后果
1. **远程代码执行（RCE）**： 攻击者可以通过JNDI注入执行恶意代码，例如在目标系统上执行系统命令、上传后门等。
2. **服务拒绝（DoS）攻击**： 攻击者可以通过JNDI注入导致目标系统资源耗尽，从而导致服务拒绝攻击。

### 防御方式

1. **验证和过滤输入**： 应用程序应该对所有用户输入进行严格的验证和过滤，确保输入的安全性和完整性。
2. **安全配置JNDI资源**： 确保Web容器的JNDI资源配置安全可靠，限制对JNDI资源的访问权限，避免出现JNDI注入漏洞。
3. **使用安全的编程实践**： 开发人员应该遵循安全的编程实践，尽量避免在应用程序中执行动态构造的JNDI名称。
4. **更新和修补**： 及时更新和修补应用程序和相关组件，以修复已知的JNDI注入漏洞。