# テスト関連のメモ
## MSTest
- https://needtec.sakura.ne.jp/wod07672/2020/03/29/mstest%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%8B%E3%83%83%E3%83%88%E3%83%86%E3%82%B9%E3%83%88%E3%81%AE%E8%A7%A3%E8%AA%AC/

1. MSTest テストプロジェクトで作成
![image](https://user-images.githubusercontent.com/80798265/171137865-664b6666-f9f2-4864-bd87-8e7598b3cf87.png)


```c#
    [TestClass]
    public class TestV1
    {
        [TestMethod]
        public void TestMethod1()
        {
            int exp = 10;
            int act = 5 + 5;
            Assert.AreEqual(exp, act);
        }


    }
```
