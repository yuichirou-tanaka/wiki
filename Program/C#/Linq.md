# link
- [Enumerable.OrderBy メソッド](https://docs.microsoft.com/ja-jp/dotnet/api/system.linq.enumerable.orderby?view=net-6.0)
- [C# リストで複数キーを指定したソート方法](http://www.3s-sys.co.jp/blog/2017/03/15/1195/)

# dictionary
 https://www.modis.co.jp/candidate/insight/column_136


# 重複した要素を削除する
- [Listから重複した要素を削除するには？［C#／VB］](https://atmarkit.itmedia.co.jp/ait/articles/1703/29/news027.html)

```c#
        enum ITEM_TYPE
        {
            FREE_MONEY,
            PAY_MONEY,
            RECOVERY, 
            EQUIPMENT, 
            OTHER,
        }

        class ItemData
        {
            public int m_id;
            public ITEM_TYPE m_type;
            public int m_count;
        }


        public static void OrderByThenByEx2_testexamp()
        {

            // アイテム情報を管理するリスト
            List<ItemData> m_itemList = new List<ItemData>() {
                 new ItemData() { m_id = 1, m_type = ITEM_TYPE.FREE_MONEY, m_count = 10 }
                ,new ItemData() { m_id = 2, m_type = ITEM_TYPE.OTHER, m_count = 20 }
                ,new ItemData() { m_id = 1, m_type = ITEM_TYPE.RECOVERY, m_count = 50 }
                ,new ItemData() { m_id = 3, m_type = ITEM_TYPE.EQUIPMENT, m_count = 40 }
                ,new ItemData() { m_id = 1, m_type = ITEM_TYPE.RECOVERY, m_count = 11 }
                ,new ItemData() { m_id = 1, m_type = ITEM_TYPE.PAY_MONEY, m_count = 12 }
                ,new ItemData() { m_id = 1, m_type = ITEM_TYPE.OTHER, m_count = 13 }
            };
            var q2 = m_itemList
                .GroupBy(c => new { c.m_id, c.m_type });

            foreach (var pq in q2)
            {
                Console.WriteLine("key:"+pq.Key);
                foreach (var p in pq)
                {
                    Console.WriteLine("id,type,count:{0} {1} {2}", p.m_id, p.m_type, p.m_count);
                }
            }

            var q3 = m_itemList
                .GroupBy(c => c.m_id)
                .Select(x => x.Where(y => y.m_id == y.m_id).FirstOrDefault()
                );
            foreach (var p in q3)
            {
                Console.WriteLine("3 id,type,count:{0} {1} {2}", p.m_id, p.m_type, p.m_count);
            }

            var q4 = m_itemList
                .GroupBy(c => c.m_id)
                .Select(x => x.FirstOrDefault(y => y.m_id == y.m_id));
            foreach (var p in q4)
            {
                Console.WriteLine("4 id,type,count:{0} {1} {2}", p.m_id, p.m_type, p.m_count);
            }
        }
```

# where 複数条件
- [C#でのLINQの条件指定Whereの使い方について詳しく解説します](https://www.fenet.jp/dotnet/column/language/8203/)
