# 运行环境

## Gemfile

```
# 强制安装到开发环境，防止冲突
group :development do
  gem 'sqlite3', '1.3.7'
end

# 仅安装到生产环境
group :production do
  gem 'pg', '0.15.1'
end

# 安装1.30以上最新版本（跨版本升级）
gem 'uglifier', '>=1.3.0'

# 安装补丁版升级
gem 'coffee-rails', '~> 4.0.0'

# 不会在生产环境中部署
$ bundle install --without production

#结论，最好都指定固定版本，减少环境问题
```

## Git
```
# 强制回滚到上个未提交版本
git checkout -f

# -a 将所有改动，包括重命名都添加进来
git commit -a -m "Improve the README file"
```
