#  IQueryable 

Executes queries on the database, returning only the data you need. 

C# 
```
var books = context.Books.Where(b => b.Authorld == 1);
```

SQL
```
SELECT * FROM Books WHERE Authorld = 1;
```

# IEnumerable

Fetches all data into memory, then applies filters in your application.

C#
```
var books = context.Books.ToList().Where(b => b.Authorld == 1);
```

SQL 
```
SELECT * FROM Books;
```

