# Go: мапы
## Проверка наличия ключа
```go
if val, exists := cache[key]; !exists {
                fmt.Fprint(w, "No such key in cache\n")
                break
            } else {
                fmt.Fprintf(w, "%v\n", val) 
            }
```