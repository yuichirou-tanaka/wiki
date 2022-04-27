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
# TIps
## 同じファイル名を開く対応
- 名前を付けて保存する
- https://forum.ozgrid.com/forum/index.php?thread/4503-solved-vba-different-directories-same-name-for-workbooks/
### Workbook
- https://docs.microsoft.com/en-us/office/vba/api/excel.workbook

## 色変更

# ファイル削除
- https://excelchamps.com/vba/delete-file/

```vba
KILL
```

```vba
    Dim FSO
    Set FSO = CreateObject("Scripting.FileSystemObject")
    If FSO.FileExists(path) Then
        FSO.DeleteFile path
    End If
```
# workbook
## close
https://docs.microsoft.com/en-us/office/vba/api/excel.workbook.close

# debug test 用コード
- https://www.excel-chunchun.com/entry/stop-debug-assert-difference#DebugAssert

# dropdown
- https://www.get-digital-help.com/run-a-macro-from-a-drop-down-list-vba/#google_vignette
- https://valmore.work/vba-create-dropdown-list/

# worksheet event
##  Activate
- https://docs.microsoft.com/en-us/office/vba/api/excel.worksheet.activate(even)
- 各シートに書く
```vba
Private Sub Worksheet_change(ByVal Target As Range)
End Sub

Private Sub Worksheet_Activate()
End Sub
```
# Enum
```vba
Enum DatasType
    ID1 = 0
    ID2 = 1
End Enum

Sub TestEnumDataType()
    
    Debug.Print (DatasType.ID1)
    Debug.Print (DatasType.ID2)
    
    Dim dt As DatasType
    dt = ID1
    Debug.Print (dt)
    dt = ID2
    Debug.Print (dt)
    
End Sub
```
- https://docs.microsoft.com/en-us/office/vba/language/reference/user-interface-help/enum-statement

### 数値判定
```vba


Sub Test_FindNumberRegExp_t()
    Dim stringOne As String
    Dim regexOne As Object
    Dim theMatches As Object
    Dim Match As Object
    Set regexOne = New RegExp
     
    regexOne.Pattern = "(AB|文字列)(.*)_(.*).txt"
    regexOne.Global = False
    stringOne = "AB12345_XXXX_FFFF.txt"
     
    Set theMatches = regexOne.Execute(stringOne)
     
    For Each Match In theMatches
      Debug.Print Match.Value
    Next
End Sub

```
# 入力規則 ○×
https://github.com/yuichirou-tanaka/wiki

# Redim
Preserve(配列要素を保持する)
- https://www.isa-school.net/blog/?p=78
```vba

Sub Test_RedimPreserve()
    Dim msOffice() As String, i As Integer
    ReDim msOffice(2)
    msOffice(0) = "Excel"
    msOffice(1) = "Word"
    msOffice(2) = "PowerPoint"
    
    For i = 0 To UBound(msOffice)
        Debug.Print msOffice(i)
    Next i
    
    ReDim Preserve msOffice(3)
    msOffice(3) = "Access"
    
    For i = 0 To UBound(msOffice)
        Debug.Print msOffice(i)
    Next i
        
    ReDim msOffice(3)
    msOffice(3) = "ABSD"
    
    For i = 0 To UBound(msOffice)
        Debug.Print msOffice(i)
    Next i
End Sub
```

# Find, FindPrevious
- https://www.sejuku.net/blog/31055
- https://docs.microsoft.com/en-us/office/vba/api/excel.range.find

xlWholeで完全一致
## sample code
```vba
Sub Test_FindNextPrev()
    Dim c As Range
    Dim c2 As Range
    
    ' 次の位置に行ってから、前の位置に行くので 12行目から範囲的に次の周期になるので30行目になる
    Set c = Range("A5:A44").Find("XXXX", LookIn:=xlValues, LookAt:=xlWhole)
    If c Is Nothing Then
        Exit Sub
    End If
    Debug.Print (c.Address & " : " & c.Row & " " & c.Column)
    
    Set c2 = Range("A5:A44").FindPrevious(c)
    If c2 Is Nothing Then
        Exit Sub
    End If
    Debug.Print (c2.Address & " : " & c2.Row & " " & c2.Column)
    
    ' 次の位置に行ってから、前の位置に行くので 12行目から4行目になる
    Set c = Range("A4:A65").Find("XXXX", LookIn:=xlValues, LookAt:=xlWhole)
    If c Is Nothing Then
        Exit Sub
    End If
    Debug.Print (c.Address & " : " & c.Row & " " & c.Column)
    
    Set c2 = Range("A4:A65").FindPrevious(c)
    If c2 Is Nothing Then
        Exit Sub
    End If
    Debug.Print (c2.Address & " : " & c2.Row & " " & c2.Column)
End Sub

```
