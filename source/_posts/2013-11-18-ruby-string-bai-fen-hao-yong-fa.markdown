---
layout: post
title: "ruby 字符串定义中百分号的用法"
date: 2013-11-18 22:43
comments: true
categories: [Ruby] 
---
1. `%(string)` 、`%Q(string)` 相当于 `"string"` 。双引号字符串表达式
2. `%q(string)` 相当于 `'string'` ，单引号字符串表达式，不会对字符串中的变量运算。
3. `%r(string)` 相当于 `/string/` ，正则表达式。
4. `%w(str1 str2 str3)` 相当于 `['str1', 'str2', 'str3']` 。 
5. `%W(str1 str2 str3)` 相当于 `["str1", "str2", "str3"]` 。
6. `%s(string)` 相当于 `'string'.to_sym` 或 `:'string'` 。注意是单引号，所以不会对字符串中的变量表达式进行运算。
7. `%x(string)` 相当于 \`string\`。执行系统中的命令，跟shell语法中的\`cmd\`差不多。如果命令有错会抛出异常并且没有返回。
