# 一括置換
ファイル名から コピーを消す
```ps1
Get-ChildItem "./" -File | Rename-Item -NewName { $_.Name -replace ' - コピー','' }
```

-https://4thsight.xyz/16468#:~:text=REN%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89,%E4%B8%80%E6%8B%AC%E5%A4%89%E6%9B%B4%E3%81%97%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%80%82
