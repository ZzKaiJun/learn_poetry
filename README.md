# poetry 檔案建立

安裝poetry  (可使用:pip install poetry)
在你要的檔案路徑開啟終端機，
輸入: poetry new + package名稱     (ex: poetry new energy_system)
會在當前路徑創建energy_system文件，並會產生初始的檔案

# git 建立本地數據庫

到要管理的檔案路徑內，
git init 進行初始化，即可建立本地工作目錄
git add . 將檔案加到索引(staging area)
git commit -m "要輸入的訊息"  ，即可將檔案上傳到本地數據庫

# git 建立遠端數據庫

再連到github 建立repository，
git remote add origin https://github.com/ZzKaiJun/learn_poetry.git  (origin為數據庫名稱)
git branch -M main
git push -u origin main     (-u 是將git push預設值設為此數據庫)
即可將本地數據庫檔案上傳到遠端數據庫。

# git 參考文件

docs/Git基本教學.png       (截圖來源:https://youtu.be/mCzptNYsE30?t=23)

