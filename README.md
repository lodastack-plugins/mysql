### MySQL Plugin


You need add a account in your DB, use sql:

```
 grant select,replication client on *.* to loda@'127.0.0.1' identified by 'yourpass';

```

default the plugin will monitor localhost:3306, use loda account.

### flag

`-servers loda:yourpass@tcp(10.21.8.13:3306)/`

`-servers loda:yourpass@tcp(127.0.0.1:3306)/,loda:yourpass@tcp(127.0.0.1:3307)/`


### DSN (Data Source Name)

The Data Source Name has a common format, like e.g. [PEAR DB](http://pear.php.net/manual/en/package.database.db.intro-dsn.php) uses it, but without type-prefix (optional parts marked by squared brackets):
```
[username[:password]@][protocol[(address)]]/dbname[?param1=value1&...&paramN=valueN]
```

A DSN in its fullest form:
```
username:password@protocol(address)/dbname?param=value
```

Except for the databasename, all values are optional. So the minimal DSN is:
```
/dbname
```

If you do not want to preselect a database, leave `dbname` empty:
```
/
```
This has the same effect as an empty DSN string:
```

```

Alternatively, [Config.FormatDSN](https://godoc.org/github.com/go-sql-driver/mysql#Config.FormatDSN) can be used to create a DSN string by filling a struct.
