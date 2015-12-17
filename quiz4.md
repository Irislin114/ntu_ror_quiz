1. 請說明 ```rails g scaffold xxx``` 功能的壞處為何？
	Ans:
		會產生出一些不必要的檔案，如.coffee檔

2. 若今天需要為 ```Project``` 和 ```Issue``` 這兩個 Model 建立一對多的關係，請寫出實作上所需要的 migratiion 和 model 檔案 
	Ans:
		```ruby
			class Project < ActiveRecord::Base
				has_many :issues
			end
			
			class Issue < ActiveRecord::Base
				belongs_to :project
			end
			
			class ProjectIssuesJoinTable < ActiveRecord::Migration
				def change
					create_table :project do |t|
						t.string :project_name
							
						t.timestamps
					end
					
					create_table :issues do |t|
						t.integer :issue_id
						t.integer :project_id
						
						t.timestamps
					end
				end
			end
		```
		

3. 若今天我有以下 model 檔：

  ```ruby
  class User < ActiveRecord::Base
    has_many :groups_users
    has_many :groups, through: :groups_users 
  end
  ```

  請寫出和這個 model 檔相關連的 model 檔，以及這些 model 檔所需要的資料庫欄位
	Ans:
	```ruby
		class Group <ActiveRecord::Base
			has_many :groups_users
			has_many :users, through: :groups_users
		end
		
		class GroupsUser < ActiveRecord::Base
			belongs_to :group
			belongs_to :user
		end
	```

4. 延續第3題，如果需要讓一個叫 "Bob" 的使用者產生一個名字叫做 "Rails is Fun" 的社團，應該如何在 rails console 裡實作出來？
	Ans:
		```ruby
			bob = User.create(name: "Bob")
			group = Group.create(title: "Rails is Fun")
			bob.groups << group
		```
5. 延續第4題，請寫一段程式碼確保使用者在建立新社團時社團名字不可以是空白，而且不能超過50個字
	Ans:
		```ruby
			class Group <ActiveRecord::Base
				has_many :groups_users
				has_many :users, through: :groups_users
				
				validates :title, presence: true, length: {maximum :50}
			end
		```
		
	
6. 請列出兩種方法檢查在 routes.rb 裡面設定的路由
	Ans:
		1. 在瀏覽器網址列輸入localhost:3000/rails/info/routes
		2. 在terminal輸入rake routes

7. 請列出在一個 rails 專案裡使用 bootstrap 套件的步驟
	Ans:
		1.在gemfile裡輸入 ```gem 'bootstrap-sass'```
		2.在terminal執行```bundle install```
		3.在app/assets/javascripts/application.js輸入 ```//=require bootstrap```
		4.在app/assets/stylesheets/application.css輸入 ```@import "bootstrap";``` ，並將副檔名改為scss 

8. 請說明在 .erb 檔案裡 ```<%= %>``` 與 ```<% %>``` 這兩種 tag 的差別
	Ans:
		```<%= %>``` => 顯示Ruby程式執行結果，如```ruby <%= post.content%>```
		```<% %>```  => 只執行Ruby程式但不會顯示結果，通常用在迴圈條件中，如```ruby <% @post.comments.each do |t| %>```
		