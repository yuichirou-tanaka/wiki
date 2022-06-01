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
