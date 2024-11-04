# Go: Web/HTTP

## GET-запрос
```go
httpResource, err := http.Get(url)
if err != nil {
		...
}

_, err := io.Copy(io.Stdout, httpResource.Body)
if err != nil {
		...
}

defer func() { httpResource.Body.Close() }()
```

## Запуск web-сервера
```go
func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
            fmt.Fprintf(w, "%v", r.Header)
    })
    log.Fatal(http.ListenAndServe("localhost:8000", nil))
}
```

## Получение тела ответа (r *http.Request)
```go
body, err := io.ReadAll(r.Body)
if err != nil {
	fmt.Fprint(w, "Error while parsing request body\n")
	break
}
defer func() {r.Body.Close()}()
```