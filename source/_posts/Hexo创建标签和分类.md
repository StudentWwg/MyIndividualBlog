---
title: Hexo创建标签和分类
tags:
  - hexo
  - blog
categories:
  - [生活经历, blog, hexo]
abbrlink: 1718164033
date: 2023-10-04 15:36:08
---

## 创建分类页(categories)和标签页(tags)

1. 生成两个文件夹: categories和tags
   通过终端进入博客目录，分别执行以下两条命令。在"/source"目录下(和"_post"同级)生成两个文件夹: categories和tags。

   ```shell
   hexo new page categories
   ```

   ```shell
   hexo new page tags
   ```

2. 修改index.md文件
   每个文件夹内都有一个名为**index.md**的文件。分别添加两条语句[type: categories]{.red}和**type: tags**，如下所示。
   source/categories/index.md

   > ```shell
   > ---
   > title: categories
   > date: 2023-10-04 15:03:43
   > type: categories
   > ---
   > ```

   source/tags/index.md
   
   > ```shell
   > ---
   > title: categories
   > date: 2023-10-04 15:03:43
   > type: categories
   > ---
   > ```
   
3. 在文章内添加分类和标签

   在文章的 **Front Matter** 设置 **categories: xxx**和**tags: xxx** ，则该文章将被标记为相应的分类和标签。_post/test.md

   > ```shell
   > ---
   > title: Hexo创建标签和分类
   > date: 2023-10-04 15:36:08
   > tags: hexo
   > categories: 个人博客
   > ---
   > ```
   
   

## 设置多级分类、并列分类、标签

1. 分类的层次
   在hexo中分类上具有顺序和层次。简而言之，一个分类可以包含几个子分类。而标签并不具有层级关系。

   - 定义父子分类

     ```shell
     categories:
       - computer-science
       - data-structure
     ```

     这里使用的定义方法将data-structure分类定义为computer-science的子分类。

   - 定义并列分类和子分类

     ```shell
     categories:
       - [computer-science, data-structure]
       - [computer-science, operating-system]
       - [mathematics]
     ```

     这里将data-structure和operating-system定义为computer-science的子分类，而mathematics是data-structure和operating-system的共同下一级子分类。设置的方式不止这一种。

2. 标签
   因为hexo中标签并不具备层次关系，因为无论如何定义都是累加在一起的。

   ```shell
   tags:
     - life
     - death
   ```

   这里给一篇文章设置life和death两个标签。
