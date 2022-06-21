# ドラッグアンドドロップのパス
- https://zero0nine.com/archives/3110
- [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](https://docs.microsoft.com/en-us/dotnet/desktop/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms?view=netframeworkdesktop-4.8)
- [Windowsフォームフォームにドラッグされたファイルのパスを取得します](https://stackoverflow.com/questions/4364437/get-the-path-of-a-file-dragged-into-a-windows-forms-form)

```c#
        private void Form1_DragDrop(object sender, DragEventArgs e)
        {
            string[] fileList = (string[])e.Data.GetData(DataFormats.FileDrop);
            textBox1.Text = fileList[0];
        }

        private void textBox1_DragEnter(object sender, DragEventArgs e)
        {
            if (e.Data.GetDataPresent(DataFormats.FileDrop))
            {
                e.Effect = DragDropEffects.Copy;
            }
            else
            {
                e.Effect = DragDropEffects.None;
            }
        }
```
