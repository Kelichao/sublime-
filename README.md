# submlie插件配置流程
![image](https://cloud.githubusercontent.com/assets/18028533/21637071/42cc6648-d2a0-11e6-8a68-3f7c7d4d010a.png)

- [sublime稳定版本](附件是sublime-text 2000+版本我一直在使用的比较稳定的版本。)

## 第一步：安装package control组件
> 按Ctrl+\` 调出console

![image](https://cloud.githubusercontent.com/assets/18028533/21636964/c04013aa-d29f-11e6-9cc3-070e04f6a5ef.png)

> 并输入以下代码sublime-text3

```
import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
```

> sublime-text2 package代码

```
import urllib2,os; pf='Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler( ))); open( os.path.join( ipp, pf), 'wb' ).write( urllib2.urlopen( 'http://sublime.wbond.net/' +pf.replace( ' ','%20' )).read()); print( 'Please restart Sublime Text to finish installation')
```

## 第二步：用Package Control安装插件

>  按下Ctrl+Shift+P调出命令面板
> 插件安装以JSLint为例

![image](https://cloud.githubusercontent.com/assets/18028533/21636896/755b5cc8-d29f-11e6-8121-2b3bbd323303.png)
> 稍等片刻就会出现安装包的输入框

![image](https://cloud.githubusercontent.com/assets/18028533/22095411/708c9d36-de4f-11e6-80d7-40764ec09b21.png)
- 第一步：首先需要安装的代码是SublimeLinter (可以在tools -> sublimeLinter -> open User Settings 中进行配置)
- 第二步：再安装SublimeLinter-jshint
- 第三步：全局安装jshint   `# $ npm install jshint -g`

> 至此，代码检查已经是可以使用了。

## 对语法检查个性化配置
- 配置方式一
```
可以在tools -> sublimeLinter -> open User Settings 中进行配置
```
- 配置方式二
```
可以在Preferences -> Package Settings -> SublimeLinter -> settings - User 中进行配置
(如果进去为空，可以在 settings - Default中拷贝,并将"default"键值名改为"user")
```
- 代码内容为 ["user配置"](https://github.com/Kelichao/sublime-Text3/blob/master/personal%E9%85%8D%E7%BD%AE)
- 需要注意的是jshint中args config的路径
> 例如可以修改为：

```js
        "linters": {
            "jshint": {
                "@disable": false,
                "args": [
                    "--config",
                    "D://文件安装包//sublime-text3-master//sublime-pojie//sublime-pojie//config.json"
                ],
                "excludes": []
            }
        },
```
# 对于无法安装全局jshint的环境
![image](https://cloud.githubusercontent.com/assets/18028533/22133970/adb1ce16-defe-11e6-8581-8433611e4b03.png)
- 先在c盘nodejs主目录下添加两个文件，jshint与jshint.cmd,然后再在node_modules中放入对应的包即可
