# link
- [SSHを介してファイル転送を行うには？ sftpコマンド](https://atmarkit.itmedia.co.jp/ait/articles/1505/20/news004.html#:~:text=%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%EF%BC%9F-,sftp%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%81%AE%E6%A6%82%E8%A6%81,%E6%80%A7%E3%81%8C%E7%A2%BA%E4%BF%9D%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%80%82)

# commmand 文字コード変更
https://aprico-media.com/posts/3928

## shift_jis
 chcp 932
## utf-8
 chcp 65001

## sftp 例
```python
import paramiko
# SFTP接続先の設定
HOST = 'ホスト名'
PORT = 22
SFTP_USER = 'ユーザー名'
SFTP_PASSWORD = 'パスワード'
WORK_FOLDER='フォルダ'

client = paramiko.SSHClient()
client.set_missing_host_key_policy(paramiko.AutoAddPolicy)
client.connect(HOST, PORT, SFTP_USER,SFTP_PASSWORD)

sftpcon = client.open_sftp()
sftpcon.chdir(WORK_FOLDER)

files = sftpcon.listdir()
for rf in files:
    print(rf)

```


# version 3だと文字化けするかも
- https://titanftp.add-soft.jp/support/?p=946
