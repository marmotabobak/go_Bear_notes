# Go: работу с командной строкой

## Считывание ввода из терминала
```go
input := bufio.NewSvanner(os.Stdin)
for input.Scan() {
	print(input.Text())
}
```

## Обработка аргументов командной строки
```go
args := os.Args
for _, arg := range args {
	fmt.Println(arg)
}
```

