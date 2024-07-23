# Hello World API

## Descrição

Este projeto é uma API simples construída em Go utilizando o framework Gin. A API responde com "Hello World" na rota `/hello`.

## Pré-requisitos

- Go instalado: [Instruções de instalação](https://golang.org/dl/)
- Gin instalado: Execute `go get -u github.com/gin-gonic/gin`

## Estrutura do Projeto

hello-world-api/
├── go.mod
└── main.go

## Configuração

1. Clone o repositório (se necessário):
    ```sh
    git clone https://github.com/seu-usuario/hello-world-api.git
    cd hello-world-api
    ```

2. Inicie um novo módulo Go (se não estiver clonado):
    ```sh
    go mod init hello-world-api
    ```

3. Instale as dependências:
    ```sh
    go get -u github.com/gin-gonic/gin
    ```

## Execução

1. Execute o servidor:
    ```sh
    go run main.go
    ```

2. O servidor estará rodando em `http://localhost:8080`.

## Teste

1. Abra seu navegador ou use um cliente HTTP (como curl ou Postman) e vá para `http://localhost:8080/hello`.
2. Você deve ver a seguinte resposta:
    ```json
    {
        "message": "Hello World"
    }
    ```

## Código Principal

```go
package main

import (
    "github.com/gin-gonic/gin"
)

func main() {
    r := gin.Default()
    
    // Define a rota
    r.GET("/hello", func(c *gin.Context) {
        c.JSON(200, gin.H{
            "message": "Hello World",
        })
    })
    
    // Inicia o servidor na porta 8080
    r.Run(":8080")
}
