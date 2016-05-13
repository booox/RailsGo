# 运行环境

- Gemfile

```
# 强制安装到开发环境，防止冲突
group :development do
  gem 'sqlite3', '1.3.7'
end

# 安装1.30以上最新版本（跨版本升级）
gem 'uglifier', '>=1.3.0'

# 安装补丁版升级
gem 'coffee-rails', '~> 4.0.0'

#结论，最好都指定固定版本，减少环境问题
```