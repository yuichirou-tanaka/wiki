# Range
- [Range object (Excel)](https://docs.microsoft.com/en-us/office/vba/api/excel.range(object))
## Cellsには、Long型を使う
Row,Columnの数は3万以上ある

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

* on error resume next エラーがあっても続行する
```vba
Sub SetCoordinateRow(isht As Worksheet, in_coordinate_row_str As String)
    On Error Resume Next ' エラーにせずに次の処理を実行する
    If (isht.Range(in_coordinate_row_str) Is Nothing) Then
        Exit Sub
    End If
    coordinate_row = isht.Range(in_coordinate_row_str).Column
End Sub
```
- https://stackoverflow.com/questions/12611900/test-if-range-exists-in-vba
- https://excel-ubara.com/excelvba1/EXCELVBA362.html
- https://docs.microsoft.com/en-us/office/vba/language/reference/user-interface-help/on-error-statement#:~:text=time%20error%20occurs.-,On%20Error%20Resume%20Next,Error%20GoTo%20when%20accessing%20objects.

## スペース除去
### 全角と半角含めて
```vba
Function DeleteSpace(istr As String) As String
    Dim s As String
    s = istr
    s = Replace(s, " ", "")
    s = Replace(s, "　", "")
    DeleteSpace = s
End Function
```

# Str関数の注意点
何故かスペースが先頭に入る
- https://excel-ubara.com/excelvba8/EXCELVBA813.html#:~:text=Str%E9%96%A2%E6%95%B0%E3%81%AE%E6%B3%A8%E6%84%8F%E7%82%B9,%E3%82%B9%E3%83%9A%E3%83%BC%E3%82%B9%E3%81%8C%E6%8C%BF%E5%85%A5%E3%81%95%E3%82%8C%E3%81%BE%E3%81%99%E3%80%82

# エラー
## 400について
### Range範囲
- https://excelchamps.com/vba/error-400/
RangeでAutoFillの時は範囲がおかしい場合も発生する
- 名前が未定義でも発生する。
### fileSaveAs
開いているファイルに対してWorkbook.SaveAsすると起きる

# 条件式の改行
[ ]+[_]
```VBA
    If Not worksheet.Cells(20, 1) = "" Or _
       Not worksheet.Cells(21, 1) = "" Then
    End If
```
- http://plus1excel.web.fc2.com/learning/l301/t810.html


# シートの非表示しているものを全表示するコマンド
 1. VBAを開く
 2. Ctrl+G
 3. for each s in sheets:s.visible=true:next を入力する

# 全シート名を表示する。
- https://nkmrdai.com/vba-get-sheetnames-of-all/
```vba
Sub sandbox_Show_excel_allsheet_name()
    Dim i As Long, cnt As Long
    cnt = ThisWorkbook.Sheets.Count
    For i = 1 To cnt
       Debug.Print Sheets(i).Name
    Next i
End Sub
```
## マクロパスワード付きの場合
いったん、マクロ無しのブックで保存する xlsx形式

# 高速化対応
```vba
Application.ScreenUpdate = False
```
- https://docs.microsoft.com/en-us/office/vba/api/excel.application.screenupdating
