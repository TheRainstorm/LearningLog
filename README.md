## 简介

本库为《python编程-从入门到实践》（美）(Eric Matthes)第18，19，20三个章节的实例代码，是用**Django**框架写的一个Web应用程序。
实现了一个在线笔记本，用于在线记录某一主题学习的心得。实现了主题(Topic)的添加，条目(Entry)的添加与修改，并实现了账户注册，
登录功能。每个账户只能登录查看自己记录的内容。

## 说明

本项目已经成功部署到pythonanywhere网站上。[链接](https://therainstorm.pythonanywhere.com)

## 部署简略过程
1. 上传代码到github上
2. 注册并登录[pythonanywhere](https://www.pythonanywhere.com/), 注：beginner版有限制但免费的
![pythonanywhere](https://www.pythonanywhere.com/static/anywhere/images/PA-logo.svg)
3. 打开bash终端输入`git clone https:/github.com/user_name/your_repo_name`
4. 使用mkvirtualenv新建一个虚拟环境(具体看pythonanywhere的官方教程),代码：
```
  mkvirtualenv env_name --python=/usr/bin/python3
  #/usr/bin/python3意思是指定使用该文件夹下的python interpreter
    
  pip install django==x.x.x
  ... #安装其它必要的包
```
5. 在pythonanywhere上新建一个web app, 因为我们是已经有写好了的Django程序的，所以选择manual configuration.
6. 配置Source code路径为Django应用程序manage.py所在的文件夹,Virtualenv为自己配置的路径(只需输env_name,网站会自动补全).
7. 配置WSGI文件,按照自动生成的的WSGI文件里的提示改,只需改两处。
```
  #+++++++++++ DJANGO +++++++++++
  #To use your own django app use code like this:
  import os
  import sys

  # assuming your django settings file is at '/home/UserName/ProjectName/ProjectName/settings.py'
  # and your manage.py is is at '/home/UserName/ProjectName/manage.py'
  path = '/home/UserName/ProjectName' #直到manage.py所在文件夹
  if path not in sys.path:
      sys.path.append(path)

  os.environ['DJANGO_SETTINGS_MODULE'] = 'ProjectName.settings' #ProjectName

  # then:
  from django.core.wsgi import get_wsgi_application
  application = get_wsgi_application()
```
8. 完毕，reload,然后点击网址运行。


