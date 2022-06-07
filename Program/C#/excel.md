# tutorial
## エクセルの色取得
### link
- [C# EXCEL操作 背景色変更](https://hironimo.com/prog/c-sharp/c-excel-color/)

# com オブジェクトがプロセスに残る現象を解決する。
- https://www.tetsuyanbo.net/tetsuyanblog/46913
- https://qiita.com/mima_ita/items/aa811423d8c4410eca71
- https://docs.microsoft.com/ja-jp/archive/blogs/office_client_development_support_blog/office-5

```cs
// アプリケーションの終了前にガベージ コレクトを強制します。
GC.Collect();GC.WaitForPendingFinalizers();GC.Collect();
// Application オブジェクトのガベージ コレクトを強制します。
GC.Collect();GC.WaitForPendingFinalizers();GC.Collect();

}
```
## 結論
　Worksheetを参照で渡さずに、クラス内で完結するように開放すれば残らない。
 値取得は文字列か数値で返す。

# range の位置を取得する
## cells
```cs
                Microsoft.Office.Interop.Excel.Range range;
                Microsoft.Office.Interop.Excel.Range range_cell1;
                Microsoft.Office.Interop.Excel.Range range_cell2;
                range_cell1 = wrksht.Cells[rowidx, colidx];
                range_cell2 = wrksht.Cells[rowidx, colidx];
                range = wrksht.get_Range(range_cell1, range_cell2) as Microsoft.Office.Interop.Excel.Range;
                ret = range.Value;
                System.Runtime.InteropServices.Marshal.ReleaseComObject(range_cell1);
                System.Runtime.InteropServices.Marshal.ReleaseComObject(range_cell2);
                System.Runtime.InteropServices.Marshal.ReleaseComObject(range);

```

# 
