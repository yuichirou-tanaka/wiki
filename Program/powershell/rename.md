# 一括置換
ファイル名から コピーを消す
```ps1
Get-ChildItem "./" -File | Rename-Item -NewName { $_.Name -replace ' - コピー','' }
```
