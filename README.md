# iOSAuthKit

# 1. corecrypt 部分
    这部分代码来自于苹果官方开源项目corecrypto 或者iOS/macos 的libcommoncrypto。 https://github.com/samdmarshall/apple-corecrypto 
# 2. srp 部分
    这主要来自于对Authkit iOS10 和windows itunes 12.6.x 版本逆向分析。 苹果的srp 是非常标准的srp-6a版本。 hash函数为sha256. aes为aes_cbc_mode。
    aes的密钥计算采用pbkdf2算法。 在gsa登陆最后一步。 通过解密spd字段，得到所有的二级token授权。 拿这个token就能访问苹果的服务了。
# 3. 数据部分
    来自于对iOS 10 登陆过程抓包
# 4. ollvm
     苹果的本地代码，大量使用了某混淆算法加强版。 http://www.freebuf.com/articles/terminal/130142.html 还原苹果自家的代码将让你体会到精疲力尽。
# 4. iOS 系统抓包
### 1.安装证书
  filder: 访问代理地址192.168.1.xxx:8888 点击那个证书，i设备上选择信任该证书。
  charles：设置代理后，访问chls.pro/ssl
### 2. 宿主机安装证书
  filder: 需要将该证书到处到本机，并信任该证书。windows/macos 都需要这一步。 mac的filder非常难用
  charles: 10.12的macos 需要以root的权限运行charles。 按照同样的办法，将该证书设置为信任的
### 3. 越狱和非越狱的区别
  如果客户端要校验服务器证书， 没越狱的环境很多数据你会看不到明文。
### 4. sslkillswitch
  这个工具的是开源的，就几行代码，让证书校验总是通过。 该工具默认是抓了itunesstored, UIKit. 将plist文件设置为foundation后
  SpringBoard 会拉不起来。 如果你要抓的进程是黑框程序。 直接在executeable中增加该进程名。这样能够抓到所有iOS数据包。
  
 
