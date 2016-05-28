# 用Helper瘦身

## 可以看做是一个外联的JS文件

1. 在 `app/helpers` 中添加需要的文件，命令可与表名相关如：issues_helper.rb
2. 文件中结构如下，注意驼峰结构
 ```
 module IssuesHelper
  def test
    res = Issue.where(:id => 2)
    # res 为 Array
    res2 = res.as_json[0]
    # res2 为 Hash
    res["R"] = "Ruby"
    return res2 
  end
end
 ```
 
3. 引用时，在 `Controller` 中的 `Class` 上，引用 `include  IssuesHelper`
4. 可传参数