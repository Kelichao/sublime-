# 插件配置流程
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

