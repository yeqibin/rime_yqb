# Rime 输入法说明
Rime是[佛振@git](https://gist.github.com/lotem)开发的适用于各个操作系统的一款输入法，[官网在这里](http://rime.im/)。Rime在Linux上叫中州韵，有ibus-rime和fcitx-rime两种版本，而在Windows上是小狼毫（Weasel），在Mac OS X下则变成了鼠须管（Squirrel），Android上叫同文输入法。

我主要用Ubuntu系统，同时用一个Windows 7虚拟机，喜欢Rime输入法的灵活配置和输入中文的流畅感。

# Rime输入法安装
在Ubuntu 16.04中可以直接用`apt-get install fcitx-rime` 安装，配置文件在`~/.config/fcitx/rime` 文件夹中。

# 安装扩充词库
* 从[这里](https://github.com/rime-aca/dictionaries)可以下载rime输入法的扩充词库，放入配置文件夹里。
  - 我用朙月拼音方案，所以`luna_pinyin.custom.yaml`名字不用改变。
  - 重新部署。
  - 验证：输入「一介书生」、「一丈红」、「疑是地上霜」。
* 配置符号
  - 在`luna_pinyin.custom.yaml' 加入：
```yaml
  punctuator:
    import_preset: symbols
  recognizer:
    patterns:
      punct: "^/[0-9]*[a-z]*$"
```
  因为luna_pinyin.yaml中没有`punct: "^/[0-9]*[a-z]*$"`这一条，导致`/fh`呼不出符号输入选项。
  
* 安装自己的词库

用QQ拼音词库生成冶金和材料专业两个词库`metall.dict.yaml`和`mater.dict.yaml`，加入`luna_pinyin.extended.dict.yaml`文件中，变成这样：
```yaml
import_tables:
  - luna_pinyin
  - luna_pinyin.hanyu
  - luna_pinyin.poetry
  - luna_pinyin.cn_en
  - metall
  - mater
```



# 同步

修改配置目录下的`installation.yaml`文件以下两行：

```yaml
installation_id: "xxxxx"
sync_dir: '/home/xxx/Nutstore/RimeSync'
```

第一行改成自己的id名，第二行将同步文件夹设立在Nutstore网盘同步文件夹里。

# 下一步
- [x] 配置符号输入
- [ ] 配置语句流
- [ ] 同步windows 7 下的个人词典
- [ ] 配置LaTeX专用个人词库，如`latex=LaTeX`等

