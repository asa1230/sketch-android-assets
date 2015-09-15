# sketch快速切图插件

一键导出安卓所需的各种尺寸切图.

## 安装


* Sketch 2版本, 使用 `~/Library/Application Support/sketch/Plugins`
  路径.
* 如果是在APPstore购买的版本, 使用
  `~/Library/Containers/com.bohemiancoding.sketch3/Data/Library/Application Support/sketch/Plugins`
  路径
* 如果是从官网下载的sketch 3（ Bohemian Coding site）, 使用
  `~/Library/Application Support/com.bohemiancoding.sketch3/Plugins`
  路径

安装成功后，你可以在sketch的插件菜单中，找到相应文件。

## 基本分辨率 (实验中)
如果默认显示设置是一个像素等于1DP，你可以一次性导出不同的分辨率的切图，无论是单文档或是所有文档。

为了解决另外一个问题，增加图层命名为
`.android_assets` (注意：命名写在文件的前缀上)
在文档中

```
base_density:xxx
```

而 `xxx` 是切图使用的分辨率, 主要有以下几种:

* mdpi
* hdpi
* xhdpi
* xxhdpi
* xxxhdpi

举个例子，如果你想1像素显示在“MDPI”屏幕上，使用如下命名
`base_density:mdpi`.

如果不指定基密度，插件会问你使用哪一个分辨率
设置好默认分辨率后，就不会出现这个问题。甚至在下次使用的过程中，会默认使用先前设定好的分辨率。

自动生成的文件，可能会存放在一下两个目录:

* 如果你的文件已经保存有单独目录,文件会和保存SKETCH文件的目录一起。
* 如果你创建了一个保存所有sketch文档的目录,切片会保存到该路径 (`/Users/<yourusername>/`).

想把 `hdpi`分辨率作为sketch的默认分辨率，你需要在mac的命令窗口输入下命令 :

```shell
echo "base_density:hdpi" > ~/.android_assets
```
