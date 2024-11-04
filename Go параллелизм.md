# Go: параллелизм

## Блок через Mutex
```go
var cnt map[string]int
var mu sync.Mutex

func main() {
    cnt = make(map[string]int)
    http.HandleFunc("/", count)
    log.Fatal(http.ListenAndServe("localhost:8000", nil))
}

func count(w http.ResponseWriter, r *http.Request) {
    url := r.URL.Path
    mu.Lock()
    cnt[url]++
    mu.Unlock()
    fmt.Fprintf(w, "%s", SprintMapStringInt(cnt))
}
```