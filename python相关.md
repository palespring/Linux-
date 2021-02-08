# 虚拟环境

安装Python，目前使用pyenv来进行包版本的管理

## pyenv

1. 安装pyenv

    `curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash`
    
2. 配置环境

    安装完成后，将有环境配置方法输出，类似如下
    ```
    export PATH="/home/jeremy/.pyenv/bin:$PATH"
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"
    ```
    将上述语句复制粘贴到 ~/.bashrc 文件中，保存
    
  3. 重新运行保存后的配置文件
  
      `exec $SHELL`
      
  4. 查看pyenv是否安装成功
  
      `pyenv -v `
      
      若有版本输出，则表面已经安装和配置成功
      
  5. 安装python
  
      首先需要安装一些python的依赖包
      
      `sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev`
      
      `pyenv install 3.6.1` 
      
      (若下载过慢，可去 https://www.python.org/downloads/source/ 下载‘XZ compressed source tarball’类型的，然后将下载后的.tar.xz 放置 ~/.pyenv/cache/ 的文件夹中)
      
  6. 查看已有的python
      
      `pyenv versions`
      
 7. 查看当前系统运用的python版本
 
     `pyenv version`
     
 8. 设置全局版本python
 
     `pyenv global 3.6.1`
     
9. pip 全局换源

    将 ~/.pip/pip.conf (若没有则新建该文件) 中的内容改成如下：
    
    ```
    [global]
    timeout = 6000
    index-url = https://pypi.douban.com/simple/
    [install]
    trusted-host = pypi.douban.com
    ```
## pyenv-virtualenv (虚拟环境)
  1. 下载
  
     `brew install pyenv-virtualenv` 或者 `sudo apt-get install`
    
  2. 配置全局
  
     `if which pyenv-virtualenv >/dev/null; then eval "$(pyenv virtualenv-init -)";fi`
    
  3. 新建虚拟环境
  
     `pyenv virtualenv [version] <virtualenv-name>`
    
     如 `pyenv virtualenv 3.6.1 spiders-3.6.1`
    
  4. 使用虚拟环境
  
     `pyenv local <virtualenv-name>` 即可
    
  5. 删除虚拟环境
  
     `pyenv virtualenv-delete <virtualenv-name>`

## virtualenv windows下的python虚拟环境
1. 安装

    `pip install virtualenv`

2. 安装virtualenv虚拟环境管理包

    `Windows 环境安装使用 pip install  virtualenvwrapper-win`

3. 修改默认的创建目录
    
    编辑系统变量
    
    变量名：WORKON_HOME
    
    变量值：路径
    
4. 新建虚拟环境目录

    `mkvirtualenv <venvName>`
    
5. 查看/启用

    `workon <venvName>`
