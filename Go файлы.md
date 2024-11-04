# Go: файлы

## Проверка наличия и чтение файла целиком
```go
data, err := os.ReadFile(`nothing.txt`)
if err != nil {
    fmt.Println(err)
}
```

## Чтение файла построчно
```go
f, err := os.ReadFile("temp.txt")
if err != nil {}
for _, s := range strings.Split(string(f), "\n") {
	fmt.Printf("%s\n", s)
}


```

```go
f, err := os.Open(fileName)
if err != nil {
	fmt.Println("ERROR")
	os.Exit(1)
}
fileReader := bufio.NewScanner(f)
for fileReader.Scan() {
	fmt.Println(fileReader.Text())
}

```

## Запись в файл
```go
    file, err := os.Create("temp.txt")
    if err != nil {
        fmt.Println("ERR 1")
        return
    }

    defer file.Close()

    _, err = file.WriteString(outputText)
    if err != nil {
        fmt.Println("ERR 2")
        return
    }
```