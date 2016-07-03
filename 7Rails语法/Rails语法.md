# 七、Rails语法

## Time
```
# time TO 2016-06-04
Time.at(@romantic_order.consume_time + 1.day - Time.now).utc.strftime("%H:%M:%S")
```

## 循环语句
- if
    ```
    if true

    elsif

    end
    ```

- `case`
    ```
    case name
      when "John"
        puts "Howdy John!"
      when "Ryan"
        puts "Whatz up Ryan!"
      else
        puts "Hi #{name}!"
    end
    ```

- `真假`
    ```
    只有false和nil是假，其他都为真
    ```
