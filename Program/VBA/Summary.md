# merge
## セル 
```vba
' セルのマージ
Public Sub MergeCells(xs As Integer, ys As Integer, xe As Integer, ye As Integer, iwsht As Worksheet)
    iwsht.Range(iwsht.Cells(ys, xs), iwsht.Cells(ye, xe)).Merge
End Sub
```
### 左上に揃える。

- https://www.officepro.jp/excelvba/cell_align/index1.html
