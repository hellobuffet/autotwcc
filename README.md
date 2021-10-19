# 更新日誌  
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
sudo apt-get update
sudo apt-get install ansible

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
1. twcc_key: tempkey  
    建立容器時所要指定的金鑰
2. twcc_key_path: ./tempkey.pem  
    金鑰位置
3. twcc_webserver_name: bfblogweb1013  
    建立webserver的名稱
4. twcc_dbserver_name: bfblogdb1013  
    建立dbserver的名稱
5. twcc_lb_name: bfbloglb1013  
    建立附載平衡的名稱
6. twcc_dbroot_pw: 1qaz2wsx  
    db的root密碼
7. twcc_db_wordpress_id: wordpress  
    wordpress系統所要使用的資料庫id
8. twcc_db_wordpress_pw: wordpresspw  
    wordpress系統所要使用的資料庫密碼
    
```
### 4.拷貝金鑰至default.yml指定路徑

### 5. 執行ansible
```
ansible-playbook autogowordpress.yml  

```
