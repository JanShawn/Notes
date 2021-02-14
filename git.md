### window指令
* 移動路徑: cd 資料夾(也可以直接滑鼠點著檔案直接拉進去)
* 回上一層: cd ..
* 查看內容: ls 
* 查看內容(包含隱藏資料夾): ls -a
* 建新資料夾: mkdir 資料夾名稱
* 建新檔案: touch 檔案名稱

### 基礎設定
==針對本機==
1. git config --global --list
2. git config --global --user.name janshawn
3. git config --global --user.email janshawns@gamil.com

==針對某一個專案==(不用設定global)
1. git init(如果此專案尚未使用git，先進行初始化)
2. cd 到專案名稱資料夾
3. git config user.name
4. git config user.email

### 新增本地/遠端數據庫
本地
- git init 初始化此資料夾由git開始追蹤版控

遠端
- git clone gitHub網址

### 要做版本備份時
* git add 檔案名稱 [增加檔案進入索引]
  - git add . [增加全部檔案進入索引] 
  - git reset HEAD [全部檔案取消索引]
  - git reset HEAD 檔案名稱 [單一檔案取消索引]
* git commit -m '更新訊息' [將索引提交到數據庫]
* git status [查詢狀態]
* git log [顯示歷史紀錄]

### 還原指令
* git checkout 檔案名稱 [恢復單一檔案到最新commit狀態]
  - git checkout 版本ID [回到指定版本]
  - git checkout master [回到最新版]
* git reset --hard [還原工作目錄和索引，會跟最後一次commit保持依樣]
* git reset HEAD^ [刪除最近一次commit]
* git reset --hard ORIG_HEAD[上面語法如果刪除錯可用此語法還原]
* git reset --soft HEAD^ [刪除最近一次commit，但保留異動內容]
* git commit --amend[commit之後發現有檔案忘記加入，補內容進去]

* git reset --mixed　取消索引修改
* git reset --hard　　強制回復到HEAD指定的版本
* git reset --soft　　工作區和暫停區修改不變
* git diff　　　　　　　working area 比較 staging area
* git diff head　　　　working area 比較 git repo
* git diff --cached　　staging area 比較 git repo

### 分支概念
* git branch [顯示所有本地分支]
* git branch -r [顯示遠端所有分支]
* git branch 分支名稱 [新增分支]
* git branch -d [刪除分支]　　　　　
* git checkout 分支名稱 [切換分支]　　
* git checkout-b 分支名稱 [建立並切換分支]　
* git merge 分支名稱 [合併指定分支到目前的分支]==要待在需被合併的主幹上==
* git merge --no-ff 分支名稱 [合併但避免快轉合併]

### 如何推送分支到遠端數據庫
* git remote [查詢遠端數據庫]
* git remote rename 原名稱 修改名稱
* git push origin branch 
  - origin(預設遠端主機名稱)
  - branch(分支名稱)

### 遠端數據庫操作(Git push&pull&fetch)
* git clone 遠端數據庫網址 [複製遠端數據庫]
* git remote [查詢遠端數據庫]
* git push 遠端數據庫名稱 遠端分支名稱 [將本地分支推送到遠端分支]
* git pull [將遠端分支拉下來與本地分支進行合併]
* git remote add origin [repo URL]
* git push origin master
* git push --delete origin master
* git pull origin master  (會直接和本地端做合併)
* git fetch origin master (可以先做查看不會被合併)

### 暫存概念
* git stash [暫時儲存當前目錄]
* git stash -u [暫存所有檔案狀態]
* git stash list [瀏覽stash列表]
* git stash pop [還原暫存]
* git stash drop [清除最新暫存]
* git stash clear [清除全部暫存]

### 標籤
* git tag [查詢標籤]
* git tag -n [查詢詳細標籤]
* git tag -d 標籤名稱 [刪除標籤]
* git tag 標籤名稱 [新增輕量標籤]
* git tag -am "備註名稱" 標籤名稱 [新增標示標籤]
* git checkout 標籤名稱 [切換到標籤commit]

### gitignore 忽略不想管控的檔案
* *.html 忽略所有HTML檔案
* css/ 忽略css整個資料夾
* https://github.com/github/gitignore 可參考

### 其他小筆記
* git pull = git fetch + git merge 
  - 指令:git fetch origin (遠端數據庫) branch1 (遠端分支)
* commit -> esc :q
* commit -> i進入編輯模式 -> esc -> :w
* git reset HEAD^ 回到前一版本
* git reset HEAD~? 回到某幾版之前
* git reset id(約六七碼)==--hard==? 回到某「特定」版本
* cat 檔案 可以看檔案內容
