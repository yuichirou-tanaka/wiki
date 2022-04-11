# Range
- [Range object (Excel)](https://docs.microsoft.com/en-us/office/vba/api/excel.range(object))

## boarder
- [Range.Borders property (Excel)](https://docs.microsoft.com/en-us/office/vba/api/excel.range.borders)

# merge
## セル 
### merge
```vba
' セルのマージ
Public Sub MergeCells(xs As Integer, ys As Integer, xe As Integer, ye As Integer, iwsht As Worksheet)
    iwsht.Range(iwsht.Cells(ys, xs), iwsht.Cells(ye, xe)).Merge
End Sub
```



### unmerge
- https://docs.microsoft.com/en-us/office/vba/api/excel.range.unmerge
### 左上に揃える。

- https://www.officepro.jp/excelvba/cell_align/index1.html

# vbacのコンパイルとデコンパイル
## コンパイル
```input.bat
cd %~dp0
copy /Y .\vba\src.xlsm .\bin\src.xlsm
cscript //noLogo vbac.wsf combine
copy /Y .\bin\src.xlsm ..\vba\src.xlsm 
pause
```

## デコンパイル 

```export.bat
cd %~dp0
copy /Y src.xlsm .\bin\src.xlsm
cscript //noLogo vbac.wsf decombine
```

# コピーセル
## AutoFill
- https://docs.microsoft.com/en-us/office/vba/api/excel.range.autofill
- https://www.moug.net/tech/exvba/0050146.html

# フォルダ作成
```vba
    If Dir(dir, vbDirectory) = "" Then
        MkDir dir
    End If
```
- https://www.moug.net/tech/exvba/0060035.html

# 配列関係
## Collection
- https://valmore.work/excel-vba-collection/
