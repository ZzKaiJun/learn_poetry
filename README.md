# 使用 Poetry 來管理Python套件

相較於Pip , Poetry 有更方便的功能

## 安裝 poetry

避免安裝 Poetry 至專案虛擬環境，
安裝 Poetry 的時候，一定將它安裝在一個「專用」的虛擬環境。

### official installer

Bash:
Windows:
- Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -

macOS:
- curl -sSL https://install.python-poetry.org | python3 -

### 設定PATH環境變數

使用 macOS 或 Linux，設定 PATH 的步驟相對簡單，
只要在.zshrc或.bashrc或.bash_profile新增：

Bash:
- export PATH=$PATH:$HOME/.local/bin

存檔後重啟 shell 即可使用。直接在命令列打上poetry指令測試。


## 初始化 Poetry

初次使用需要初始化poetry，建立pyproject.toml:

Bash:
- poetry init

## 建立專案虛擬環境並使用:

Bash:
- poetry env use python      #建立虛擬環境所使用的 Python 版本

### 將虛擬環境建在專案目錄下:

使用 poetry config 指令來查看 Poetry 的設定
將 virtualenvs.in-project = false 修改為 true

Bash:
- poetry config virtualenvs.in-project true

## 啟動虛擬環境

Bash:
- poetry shell

## 安裝python套件:

Bash:
- poetry add pyautogui  #安裝pyautogui套件
- poetry add flask      #安裝flask套件

### 更新lock:
如果手動更改 pyproject.toml 內容，需要更新 poetry.lock

Bash:
- poetry lock

## 新增套件至 dev-dependencies:
用來新增只會在開發環境中使用，產品的部署環境並不需要的套件。

Bash:
- poetry add black --group dev  (Poetry >= 1.2.0)

## 其他指令:

- poetry update         #更新套件
- poetry show           #列出所有套件
- poetry show --tree    #列出所有套件樹狀圖
- poetry remove flask   #移除套件


## 在別台主機上重現專案的 Poetry 虛擬環境
- 安裝、設定好 Poetry
- 移至專案目錄底下，依序執行指令

Bash:
poetry shell
poetry install        #因為是舊專案，不需要init


## 參考文件

docs/Git基本教學.png       (截圖來源:https://youtu.be/mCzptNYsE30?t=23)
[再見了 pip！最佳 Python 套件管理器——Poetry 完全入門指南](https://blog.kyomind.tw/python-poetry/)。  

