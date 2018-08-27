---
title: 关于Glide的圆角等效果的使用注意
tags:github
---

#### 使用Glide版本3.7达到圆角图片的效果

圆角效果的代码使用的是 开源库[glide-transformations](https://github.com/wasabeef/glide-transformations) 

在使用该库时，注意Glide的版本是否与使用的版本一致，如果不一致，需要该开源库的分支，确定某分支的Glide版本号与使用的相同，然后才进行相关的圆角代码使用及查看。

如果是想在Glide的3.7.0版本使用圆角，如果发现圆角无效，可以采用如下代码：

`Glide.with(context)    .load(url)    .transform(new CenterCrop(context), new GlideRoundTransform(context))    .diskCacheStrategy(DiskCacheStrategy.ALL)    .crossFade()    .into(view);`

参考的相关[BLog](https://github.com/wasabeef/glide-transformations/ )

