# SYTCraft Frp Panel
# 演示网站/官方网站:https://govfrp.com/
# 公告
---
### 注意：此项目需要与项目“SYTCraft Frp”搭配！
### 本项目仍在开发，现阶段请勿使用
---
### V2.0.1 版本内容更新
1. 新增功能    开放流量购买渠道，免去申请流程以便于必要时刻。
2. 新增功能    开放赞助渠道
3. 体验优化    加载方式优化
# 开始
### 安装 nginx Web服务程序
#### 安装依赖
    yum install -y gcc-c++ pcre pcre-devel zlib zlib-devel openssl openssl-devel
#### 安装 nginx Web服务程序
    wget https://nginx.org/download/nginx-1.24.0.tar.gz      //下载 nginx Web服务程序
    tar -zxf nginx-1.24.0.tar.gz                             //解压 nginx Web服务程序
    cd nginx-1.24.0                                          //转入 nginx Web服务程序所在文件夹
    ls                                                       //出现 nginx-1.24.0 表示解压成功
    ./configure                                              //配置 nginx Web服务程序
    make&&make install                                       //编译安装 nginx Web服务程序
    cd /usr/local/nginx/sbin                                 //转入 sbin 文件夹
    ./nginx                                                  //运行 nginx Web服务程序

    访问 127.0.0.1:80 验证服务是否运行                         //将 127.0.0.1 更为服务器公网IPv4
### 安装面板
#### 安装 Git
    sudo apt-get install git
#### 获取面板
    git clone https://github.com/SYTCraft/SYTCraftFrp-Panel/archive/refs/heads/Master.zip
### 配置数据库
#### 安装 MySQL 5.6 数据库服务程序
    不提供安装命令，请自行查找安装方式
#### 检查是否已有 MySQL 数据库服务程序
    rpm -qa | grep mysql
#### 如已有非 MySQL 5.6 的 MySQL 数据库服务程序，请卸载（为避免系统崩溃，请谨慎操作）
    rpm -e mysql                                             //将mysql替换为上一步返回的文件名
#### 导入数据库
    mysql -uroot -ppassword sqlname < /home/mysql/panel.sql; //将 root 更为你的数据库管理员用户名
                                                             //将 password 更为你的数据库管理员密码
                                                             //将 sqlname 更为你的数据库名
                                                             //将 /home/mysql/ 更为要导入的数据库文件实际路径
