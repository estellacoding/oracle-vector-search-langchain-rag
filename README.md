# 使用 Oracle 向量資料庫的 RAG 應用

此專案展示了如何使用 Oracle 資料庫和 LangChain 建立一個 RAG 應用，參照 Oracle LiveLabs 這篇 [Oracle LiveLabs 的 AI Vector Search - 7 Easy Steps to Building a RAG Application](https://apexapps.oracle.com/pls/apex/f?p=133:180:108165763619849::::wid:3927) 教學。

主要會處理一份 PDF 文件，提取文本、向量化並存入 Oracle 資料庫，讓使用者能夠用問答的方式進行查詢並檢索 PDF 的資訊。PDF 文件是是使用 202402_2330_AI1_20241003_160741.pdf，這是台積電的 2024 Q2 財報，你可以使用其他文件，或是也可以用這份文件來測試 RAG 應用程式的功能。

# 功能
PDF 處理：將 PDF 文件轉換為文本區塊。
向量化：使用 HuggingFace 的嵌入模型將文本轉換為向量。
Oracle 資料庫整合：將向量化的文檔存入並從 Oracle 資料庫檢索。
問答功能：基於文檔內容生成用戶查詢的答案。

# 執行專案步驟
## 複製專案
```
git clone https://github.com/estellacoding/oracle-vector-search-langchain-rag.git
```
## 安裝套件
請先安裝檔案中的套件，也可以使用以下命令一次安裝所有套件。
```
pip install -r requirements.txt
```

## 設定環境變數
在專案目錄下建立 .env 檔案，並填寫以下內容。
```
username = 'HR' # Oracle 資料庫使用者名稱
password = 'oracle' # Oracle 資料庫密碼
dsn = 'localhost:1521/freepdb1'
COMPARTMENT_OCID =
OPENAI_API_KEY = '' # OpenAI API 金鑰
```

## 運行 Jupyter Notebook
進入專案資料夾。
```
cd <專案目錄>
```

啟動 Jupyter Notebook。
```
jupyter notebook
```

在瀏覽器中打開`oracle-vector-search-langchain-rag.ipynb`，並依照每個區塊逐步執行代碼。