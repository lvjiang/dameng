# 例子

```go
package main

import (
	"database/sql"
	"fmt"
	_ "github.com/alexbrainman/odbc"
)

var (
	SqlHandler  *sql.DB
	SqlHandler2 *sql.DB
)

func InitDM(dsn string) {
	var err error
	//SqlHandler, err = sql.Open("odbc", "driver={DM7 ODBC DRIVER};server=192.168.1.165;tcp_port=5236;uid=SYSDBA;pwd=SYSDBA")
	SqlHandler, err = sql.Open("odbc", "dsn=DM7")
	if err != nil {
		fmt.Println(err)
	}
	SqlHandler.SetMaxOpenConns(5)
	SqlHandler.SetMaxIdleConns(10)
	SqlHandler.SetMaxOpenConns(100)
}

func main() {
	InitDM("")
	//rows, err := SqlHandler.Query("select * from all_users");
	query := fmt.Sprintf("select * from %s.%s", "V1_TINYEYE", "white_ip")
	rows, err := SqlHandler.Query(query)
	if err != nil {
		fmt.Println(err)
	}
	defer rows.Close()

	columns, err := rows.Columns()

	values := make([]sql.RawBytes, len(columns))
	scans := make([]interface{}, len(columns))

	for i := range values {
		scans[i] = &values[i]
	}

	var result []map[string]string

	for rows.Next() {
		_ = rows.Scan(scans...)
		each := make(map[string]string)

		for i, col := range values {
			each[columns[i]] = string(col)
		}

		result = append(result, each)
		fmt.Println(each)
	}

}

```

