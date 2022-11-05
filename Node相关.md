## NVM （github: https://github.com/nvm-sh/nvm）
1. 在终端执行以下命令，将自动进行nvm的安装:

    `wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash` （安装完成后将自动配入环境变量中）

2. 安装完成后，执行以下命令查看是否安装完成（重启terminal）:

    `nvm --version`

## Node  
1. 查看可以安装的node版本:

    `nvm ls-remote`

2. 下载需要的node版本:

    `nvm install v10.15.3`

3. 查看本地已安装的node:

    `nvm ls`
    
- 查看当前node版本:

    `node -v`
    
- 使用指定node:

    `nvm use v10.15.3`
    
- 修改默认node版本
    
    `nvm alias default 0.12.7 #设置默认 node 版本为 0.12.7`

- 配置npm为国内源（taobao）:

    `npm install -g cnpm --registry=https://registry.npm.taobao.org`
    
## NPM
- 换成国内源：

    `npm config set registry https://registry.npm.taobao.org`
    
- 查看当前npm地址源：

    `npm config get registry`
    
- 还原成初始源：

    `npm config set registry https://registry.npmjs.org/`
