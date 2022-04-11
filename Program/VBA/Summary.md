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
```vba

' collection
Sub Test_Collection()
    Dim col As New Collection
    Dim i As Integer
    For i = 0 To 5
        col.Add ("fruit" & i)
    Next i
    col.Add ("apple")
    col.Add ("banana")
    col.Add ("Pear")
    Debug.Print ("1all -------")
    For i = 1 To col.Count
        Debug.Print (col(i))
    Next i
    Debug.Print ("2 -------")
    col.Remove (2)
    col.Remove (5)
    Debug.Print ("all -------")
    For i = 1 To col.Count
        Debug.Print (col(i))
    Next i
    Debug.Print ("end -------")
End Sub
```

# Tips
## Range
- [セルがセル範囲内にあるかどうか](http://officetanaka.net/excel/vba/tips/tips118.htm)
