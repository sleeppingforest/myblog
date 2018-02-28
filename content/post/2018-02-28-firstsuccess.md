---
title: 终于成功了
author: 赵青山
date: '2018-02-28'
slug: firstsuccess
categories: []
tags: []
---
经过实验。终于把个人主页配置成功了。
在Netlify网站配置HUGO时需要提供HUGO的版本号。
还需要添加如下的备注。

[build]
publish = "public"
command = "hugo"

[context.production.environment]
HUGO_VERSION = "0.36.1"
HUGO_ENV = "production"
HUGO_ENABLEGITINFO = "true"

[context.split1]
command = "hugo --enableGitInfo"

[context.split1.environment]
HUGO_VERSION = "0.36.1"
HUGO_ENV = "production"

[context.deploy-preview]
command = "hugo -b $DEPLOY_PRIME_URL"

[context.deploy-preview.environment]
HUGO_VERSION = "0.36.1"

[context.branch-deploy]
command = "hugo -b $DEPLOY_PRIME_URL"

[context.branch-deploy.environment]
HUGO_VERSION = "0.36.1"

[context.next.environment]
HUGO_ENABLEGITINFO = "true"


