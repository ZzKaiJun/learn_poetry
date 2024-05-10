# poetry 檔案建立

安裝poetry  (可使用:pip install poetry)
在你要的檔案路徑開啟終端機，
輸入: poetry new + package名稱     (ex: poetry new energy_system)
會在當前路徑創建energy_system文件，並會產生初始的檔案。

初次使用需要初始化poetry，建立pyproject.toml:
poetry init

建立專案虛擬環境並使用:
poetry env use python      #建立虛擬環境所使用的 Python 版本

將虛擬環境建在專案目錄下:
#使用 poetry config 指令來查看 Poetry 目前幾個主要的設定
#將 virtualenvs.in-project = false 修改為 true
poetry config virtualenvs.in-project true

進入專案但虛擬環境還未啟動，以這個指令啟動:
poetry shell

安裝套件:
poetry add pyautogui  #安裝pyautogui套件
poetry add flask      #安裝flask套件

更新lock:
如果手動更改 pyproject.toml 內容，需要更新 poetry.lock
poetry lock

新增套件至 dev-dependencies:
用來新增只會在開發環境中使用，產品的部署環境並不需要的套件。
poetry add black --group dev  (Poetry >= 1.2.0)

更新套件:
poetry update

列出所有套件:
poetry show
poetry show --tree    #樹狀圖

移除套件:
poetry remove flask

# 在別台主機上重現專案的 Poetry 虛擬環境
1.安裝、設定好 Poetry
2.移至專案目錄底下，依序執行指令
poetry shell
poetry install        #因為是舊專案，不需要init

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

# 參考文件

docs/Git基本教學.png       (截圖來源:https://youtu.be/mCzptNYsE30?t=23)
[再見了 pip！最佳 Python 套件管理器——Poetry 完全入門指南](https://blog.kyomind.tw/python-poetry/)。  

