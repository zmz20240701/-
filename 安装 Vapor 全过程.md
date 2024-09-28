操作系统：阿里云 Ubuntu 20.04.6 LTS (GNU/Linux 5.4.0-182-generic x86_64)

# 安装 swift
1. 浏览器到 Vapor 中文文档，选择Linux安装：https://docs.vapor.codes/zh/install/linux/
2. 使用 Swiftly CLI 工具自动安装(推荐). 安装链接 `curl -L https://swiftlang.github.io/swiftly/swiftly-install.sh | bash`
3. 将安装连接复制到命令行窗口执行安装
4. 执行命令`export PATH="$HOME/.local/bin:$PATH"`
6. 执行命令`swiftly install latest`
7. 显示安装成功界面
   <img width="960" alt="image" src="https://github.com/user-attachments/assets/05d3d772-9e12-407c-890c-d7b2c555863c">
# 安装工具箱(Install Toolbox)
1. `git clone https://github.com/vapor/toolbox.git`
2. `cd toolbox`
3. `make install`
4. `vapor --help`验证安装是否成功, 成功的话会出现界面
   <img width="729" alt="image" src="https://github.com/user-attachments/assets/c5fc0482-597c-4e9b-abbc-c6dffbe42940">
   
