```ps1
Get-ChildItem "./" -File | Rename-Item -NewName { $_.Name -replace ' - コピー','' }
```
