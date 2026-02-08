# Blog Images

Gaoxuefeng 个人博客的图片仓库 - 通过 jsDelivr CDN 加速

## 📌 用途

存储博客文章所用的图片，并通过 jsDelivr 全球 CDN 加速分发。

## 📁 结构

```
blog-images/
├── article-name-1/
│   ├── image1.png
│   ├── image2.jpg
│   └── ...
├── article-name-2/
│   └── images...
└── ...
```

每个文件夹对应一篇博客文章，使用 Hexo 的文章资源文件夹功能管理。

## 🔗 CDN 链接格式

所有图片通过 jsDelivr 提供加速访问：

```
https://cdn.jsdelivr.net/gh/GxFn/blog-images@main/{article-folder}/{image-name}
```

**示例**:
```
https://cdn.jsdelivr.net/gh/GxFn/blog-images@main/autosnippet-manual/20260205232116_66_167.png
```

## ⚡ CDN 特性

- ✅ **全球加速**: 支持国内外快速访问
- ✅ **免费服务**: 无需付费
- ✅ **自动同步**: 推送到 GitHub 后，jsDelivr 自动缓存（5-60分钟）
- ✅ **版本控制**: 支持通过 commit hash 引用特定版本的文件

## 🚀 如何使用

### 方式 1: 自动上传（推荐）

使用博客的自动发布脚本上传图片：

```bash
cd Pages-Hexo
./auto-publish.sh
```

脚本会自动：
1. 扫描文章中的新图片
2. 上传到此仓库
3. 替换文章中的图片链接为 CDN 地址

### 方式 2: 手动上传

```bash
# 克隆此仓库
git clone git@github.com:GxFn/blog-images.git
cd blog-images

# 添加或修改图片
cp your-image.png article-name/

# 提交并推送
git add .
git commit -m "Add images for article-name"
git push origin main
```

## 🗑️ 清理孤立图片

如果删除了文章中的图片引用，需要手动清理仓库中的对应文件：

```bash
# 删除图片文件
rm article-name/old-image.png

# 提交更改
git add .
git commit -m "Remove unused image"
git push origin main
```

> 注意：脚本不会自动删除仓库中的图片，防止多篇文章共用同一图片时误删。

## 📊 CDN 缓存说明

- 新推送的文件通常在 **5-60 分钟**内在 CDN 上可用
- 修改已有文件时，旧内容可能被缓存，需要等待过期或清除缓存
- 可以使用 jsDelivr 的[清除缓存](https://www.jsdelivr.com/tools/purge)工具手动清除

## 🔗 相关项目

- 📝 [Pages-Hexo](https://github.com/GxFn/Pages-Hexo) - 博客源代码
- 🌐 [GxFn.github.io](https://github.com/GxFn/GxFn.github.io) - 发布的博客
- 🔗 [My Blog](https://gaoxuefeng.com) - 博客主页

---

**维护者**: gaoxuefeng  
**最后更新**: 2026-02-09
