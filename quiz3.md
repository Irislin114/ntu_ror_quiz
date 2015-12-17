1. 請解釋 ```database.yml```, ```routes.rb```, 和 ```Gemifle``` 分別是什麼？ 他們分別在一個 Rails 專案裡的什麼位置？ 他們為什麼對一個 Rails 專案如此重要？
	Ans:
		database.yml => 位於app\config下，為資料庫相關細節設定
		routes.rb => 位於app\config下，為路由設定
		Gemfile =>  位於app\下，用來設定Rails專案中會使用的gem

2. MVC 架構裡的 M, V, 和 C 分別代表什麼？ 
	Ans:
		M:Model
		V: View; 
		C:Controller

3. 請解釋 CRUD 是哪四個字的縮寫？  
	Ans:
		C: Create
	    R: Read 
	    U: Update;
		D: Destory

4. 請問在 routes.rb 裡面加入以下程式碼會產生出哪一些 url？ (提示：在 browser 輸入```http://localhost:3000/rails/info/routes```)
```ruby
	resources :users
```
	
	Ans:
		users_path
	    new_users_path
	    edit_users_path 
	
5. 請解釋 model 檔案和 migration 檔案的差別
	Ans:
		model => 對應資料庫內的資料表
		migration => 資料庫欄位的版本控制，更改資料庫欄位現有的狀態

6. 若今天發現一個 migration 檔寫錯，請問我應該用什麼指令回復到上一個版本的 migration? 
	Ans:
```ruby
		
		rake db:rollback
		
```
	
7. 假設今天
	* 我要在資料庫裡產出一個叫 group 的資料表
	* 裡面包括的欄位名稱和相對應的資料型別是： 
		**name (string)**,
		**description (text)**,
		**members (integer)**
    * 請寫出一個能產生出以上需求的 migration 檔

	Ans:
```ruby
			
		class Groups < ActiveRecord::Migration
			def change
					create_table :groups do |t|
					t.string :name
					t.text :description
					t.integer: members

					t.timestamps
			 end
		end

```
	
8. 請解釋什麼是 ActiveRecord? 
	Ans:
		Ruby 及 SQL 語言的翻譯器，讓程式開發人員不用寫SQL語法便可操作資料庫
