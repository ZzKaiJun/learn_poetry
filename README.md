# 使用 Poetry 來管理Python套件

- 相較於Pip , Poetry 有更方便的功能

## 安裝 poetry

避免安裝 Poetry 至專案虛擬環境，
安裝 Poetry 的時候，一定將它安裝在一個「專用」的虛擬環境。


### official installer

Bash:
- Windows:
```
Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
```
- macOS:
```
curl -sSL https://install.python-poetry.org | python3 -
```
### 設定PATH環境變數

使用 macOS 或 Linux，設定 PATH 的步驟相對簡單，
只要在.zshrc或.bashrc或.bash_profile新增：

Bash:
```
export PATH=$PATH:$HOME/.local/bin
```

存檔後重啟 shell 即可使用。直接在命令列打上poetry指令測試。


## 初始化 Poetry

初次使用需要初始化poetry，建立pyproject.toml:

Bash:
```
poetry init
```

## 建立專案虛擬環境並使用:

Bash:
```
poetry env use python     
```

### 將虛擬環境建在專案目錄下:

使用 poetry config 指令來查看 Poetry 的設定
將 virtualenvs.in-project = false 修改為 true

Bash:
```
poetry config virtualenvs.in-project true
```

## 啟動虛擬環境

Bash:
```
poetry shell
```

## 安裝python套件:

Bash:

- 安裝django套件
```
poetry add django  
```
- 安裝django套件版本為 >=4.2.9 且 <5.0.0（允許 4.2.9 及以上版本，但不包括 5.0.0 )
```
poetry add django@^4.2.9      
```
- 安裝django套件版本只會接受 4.2.x 系列的更新
```
poetry add django@~4.2.9      
```
- 安裝django套件版本為 >=4.2.9（沒有上限）
```
poetry add "django>=4.2.9"      
```
- 安裝django套件版本為 4.2.9
```
poetry add django==4.2.9     
```

### 更新lock:

如果手動更改 pyproject.toml 內容，需要更新 poetry.lock

Bash:
```
poetry lock
```

## 新增套件至 dev-dependencies:

用來新增只會在開發環境中使用，產品的部署環境並不需要的套件。
ex:新增black套件到開發環境。 

Bash:
```
- poetry add black --group dev  
```

## 其他指令:

- 更新套件
```
poetry update         
```
- 列出所有套件
```
poetry show           
```
- 列出所有套件樹狀圖
```
poetry show --tree    
```
- 移除套件
```
poetry remove flask   
```

## 在別台主機上重現專案的 Poetry 虛擬環境
- 安裝、設定好 Poetry
- 移至專案目錄底下，依序執行指令

Bash:
```
poetry shell
```
```
poetry install        
```

## 參考文件

- [Git基本操作](https://youtu.be/mCzptNYsE30?t=23)
- [再見了 pip！最佳 Python 套件管理器——Poetry 完全入門指南](https://blog.kyomind.tw/python-poetry/)
