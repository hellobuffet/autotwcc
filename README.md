# 更新日誌  

### 20211213
修正功能：將登入計畫代碼與金鑰功能改成手動設定
說明文件：修改執行流程

### 20211028  
修正功能：自動登入API並且不需要手動下載VCS KEY  
說明文件：修改執行流程  


### 20211019  
修正功能：自動更新twccli版本  
說明文件：加入pip3 install ansible  

### 20211018  
新增功能：修改key權限  
修正功能：允許金鑰更新後自動允許更新  

### 20211014  
更新結尾資訊：可更快設定wordpress  
更新lampp軟連結語法：從command改成file (line 136)  
修正vars/default.yml：刪除無用變數

# autotwcc 說明文件

### 1.安裝ansible
```
sudo apt update -y
sudo apt install ansible -y
pip3 install ansible  
pip3 install -U TWCC-CLI

```
### 2. 下載ansible腳本檔
```
git clone https://github.com/hellobuffet/autotwcc.git
cd autotwcc  

```
### 3. 修改vars/default.yml
```
vim vars/default.yml
```

```
1. twcc_key: tempkey1213  
    建立主機時所要指定的金鑰
2. twcc_webserver_name: bfblogweb1213  
    建立webserver的名稱
3. twcc_dbserver_name: bfblogdb1213  
    建立dbserver的名稱
4. twcc_lb_name: bfbloglb1213  
    建立附載平衡的名稱
5. twcc_dbroot_pw: 1qaz2wsx  
    db的root密碼
6. twcc_db_wordpress_id: wordpress  
    wordpress系統所要使用的資料庫id
7. twcc_db_wordpress_pw: wordpresspw  
    wordpress系統所要使用的資料庫密碼
    
```
### 4. 登入計畫代碼與api金鑰


```
twccli config init
```

```
Do you agree we use the collection of the information by GA to improve user experience?  [Y/n]: 
(詢問是否同意收集用戶訊息改善用戶使用狀況)
Please enter TWCC Project Code:       (輸入計畫代碼)
Please enter TWCC APIKEY:             (輸入API金鑰)

```
### 5. 確認是否成功登入金鑰
```
twccli ls vcs
```


### 6. 執行ansible
```
ansible-playbook autogowordpress.yml  

```
