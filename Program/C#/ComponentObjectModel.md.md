# tutorial
## 入門
### COM(Component Object Model)についてふわっと学習していく その１ 導入編
- https://qiita.com/mintcandy/items/979a4a2669c8fc1f4f2f
- 
```C#
class TaskTest1
    {
        public bool bLoop = true;
        async Task<string> getMessageAsync(string message)
        {
            Console.WriteLine("getMessageAsync s");
            await Task.Delay(3000);
            Console.WriteLine("getMessageAsync e");
            return "msg:" + message;
        }

        public async void executeAsync()
        {
            Console.WriteLine("executeAsync s");
            while (bLoop)
            {
                var result = await getMessageAsync("Hello");
                Console.WriteLine(result);

            }
            Console.WriteLine("executeAsync e");

        }
    }
```


#  既に開いているエクセルについて
https://shozo-gson.com/editing-open-excel/

System.Runtime.InteropServices.Marshal.GetActiveObject
で行ける
