1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異
	Ans:
		```
		Fixnum => 沒有小數點
		Float => 有小數點
		```

2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```
	Ans:
		```
		puts str1 + str2 => 會先將str1、str2放置暫存空間再印出，會消耗記憶體
		puts "#{str1}#{str2}" => 以內插的方式印出
		```

3. 請解釋 array 和 hash 的不同處
	Ans:
		```
		array => 有排序限制，以索引號碼(index number)提取內容
		hash  => 以鍵(key)提取內容
		```

4. 請寫一段 code 從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值
	Ans:
		```
		arr = [1,"a string", 3.14, [1,2,3,4]]
		arr.select{|x| x.class != string}
		```
		
5. 請列出兩種產出亂數的方法
	Ans:
		```
		(1..9).shuffle
		rand(1..9)
		```

6. 請把 lesson1 程式碼裡的 calculator.rb 裡面的使用者輸入兩個數字的方式改寫成 method，並要有防止使用者亂輸入值的功能
	Ans:
		```ruby
			def check_num1
				begin
					puts "Please enter the first number"
					num1 = gets.chomp.to_i
				end while !(num1.class == Fixnum)
				num1
			end
		```

7. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
  會執行出什麼結果？ 請試試不用 irb 算出結果
  	Ans:
  		```
		true
		```

8. 請問 binding.pry 是什麼？ 要如何使用它？
	Ans:
		```
		debug用;在程式最上方輸入```ruby require 'pry'```，在程式中加入```ruby binding pry```作為斷點debug
		```

9. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

  ```ruby
  var = 5

  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```
 	Ans:
 		```
		var == 5 ? "var is greater than or equal to 5" : "var is less than 5"
		```

