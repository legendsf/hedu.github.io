# 

## 添加全局cdn变量

对于一些静态资源，比如图片、音乐文件、第三方库等，如果有自己的cdn或者图床等，可以在站点配置文件自定义一个cdn变量，如下：
```
[params]
  # cdn变量，末尾不需要加/
  cdnPrefix = "http://xxxx"
```

接下来就可以在你需要的地方使用该变量，大概有如下3种用法。

### 在md文件中使用

在md文件中可以用内置的shortcodes来使用该变量：
```
{{</* param cdnPrefix */>}}

![avatar.jpg]({{</* param cdnPrefix */>}}/images/avatar.jpg)
```

### 在模板文件中使用

在`layouts`目录下有很多html文件，这些是用来渲染站点的模板文件，可以用Hugo的语法来引入该变量：
```
{{ .Site.Params.cdnPrefix }}
```

如果在一个模板文件里有多个地方使用到该变量，可以定义一个局部变量来使用：
```
{{- $cdn := .Site.Params.cdnPrefix -}}

/* 使用局部变量 */
{{ $cdn }}
```
#### 测试

	```ajflafj
	```

1. Lorem ipsum dolor sit amet
1. Consectetur adipiscing elit
1. Integer molestie lorem at massa
1. Facilisis in pretium nisl aliquet
1. Nulla volutpat aliquam velit
1. Faucibus porta lacus fringilla vel
1. Aenean sit amet erat nunc
1. Eget porttitor lorem

* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem

