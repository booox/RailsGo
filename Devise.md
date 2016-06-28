---
title: Divise
date: 2016-05-25
categories: Rails
tags: Rails

---

## Controller 中设置权限

```
# 只有用户自己才友权限更改自己的文章

@group = Group.new(group_params)
@group = current_user.groups.new(group_params)
```

