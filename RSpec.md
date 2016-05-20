# RSpec

## 资料

- [Code School RSpec](https://www.codeschool.com/courses/testing-with-rspec)


## 测试

```
# 添加 RSpec
group :development, :test do
  gem 'sqlite3', '1.3.7'
  gem 'rspec-rails', '2.13.1'
end

# 用于界面交互测试
group :test do
  gem 'selenium-webdriver', '2.0.0'
  gem 'capybara', '2.1.0'
end
```

## 概念
BDD：行为驱动开发。
TDD：测试优先。
失败--实现--通过；遇红，变绿，重构；
DSL：Domain-specific Language，领域专属语言。

## 运行
```
# bundle exec 保证 RSpec 运行在 Gemfil 指定的环境
bundle exec rspec spec/requests/static_pages_spec.rb
```

- 自动化测试
```
# guard-rspec

# Spork 加速测试

```

## 重构
代码经常会『变味』丑陋、啰嗦、重复。经常重构很重要，一个好的测试就显出其价值了，可降低引入BUG风险。

## 测试用例
```
require 'spec_helper'

describe "Static pages" do
  # 测试主页是否包含某内容
  describe "Home page" do
    it "should have the content 'Sample App'" do
      visit '/static_pages/home'
      expect(page).to have_content('Sample App')
    end
  end

  # 测试 Titile
    it "should have the title 'About Us'" do
          visit '/static_pages/about'
          expect(page).to have_title("Ruby on Rails Tutorial Sample App | About Us")
    end
end
```

## 测试代码重构
```
describe "Home page" do
before { visit root_path }  # 使用before 代替重复的代码
it "should have the content 'Sample App'" do
expect(page).to have_content('Sample App')
end
it "should have the base title" do
expect(page).to have_title("Ruby on Rails Tutorial Sample App")
end
it "should not have a custom page title" do
expect(page).not_to have_title('| Home')
end
end
```

let 方法，只要指定就会创建一个局部变量，visit/click_link 函数（177页）

- [RSpec, Capybara, FactoryGirl的使用方法介绍](https://danielzhangqinglong.github.io/2015/03/03/rspec-capybara/)
