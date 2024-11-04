# Go: json
## Маппинг полей с json
```go
type Item struct {
    Data ItemData `json:"data"`
}
```
 Если передавать эту структуру во внешнюю библиотеку (например, Unmarshall), то нужно атрибуты делать публичными, иначе будут недоступны этой бибилиотеки и json не распарсится.
## Десериализация из json
```go
err = json.Unmarshal(body, &item)
if err != nil {
	fmt.Fprint(w, "Error while parsing request body to json\n")
	break
}
```
