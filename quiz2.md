1. 請用簡單的方式敘述以下每一行程式碼：

  ```ruby 
  a = 1					#a變數的值為1
  @a = 2				#instance variable 
  @@a = 5				#class vairable 
  user = User.new		#用User這個class創造一個新object
  user.name				#user這個object的name的值
  user.name = "Joe"		#user.name的值為Joe
  ```
 			
2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?
	Ans:
		1.本身不是class，只能被include到class內使用，不能被new
		2.
		```
			module Knowledge
				def math
					puts "I love math"
				end
			end
			
			class Person
				include Knowledge
				
			end
		```	

3. 請說明 class 和 instance variable 之間的差別
	Ans:
		class variable    => 綁定class
		instance variable => 綁定物件本身

4. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是: 
  ```
  User.new("Bob", "male", "Engineer")
  ```
請寫出 User class 的 initialize method
	Ans:
		```
			class User
				def initialize(name, gender, job)
					@name = name
					@gender = gender
					@job = job
				end
			end
		```

5. self 在：
  a. class 裡，method 外面
  b. class 裡，instance method 裡
  分別是指向什麼?
  	Ans:
		a. 指class自己
		b. 指被創造出的object

6. attr_accessor 的功能是什麼
	Ans:
		自動產生getter和setter method

7. 請說明 public 和 private method 之間的不同
	Ans:
		publice method => 在程式任何地方都可以存取
		private method => 只能在class內存取，需透過其他instance method取用

8. Ruby 是如何確保一個 module 的 method 會被 include 它的 class 使用到？ (提示：method lookup)
	Ans:
		使用.ancestor找出祖先查看該module是否為該class祖先
		
		
