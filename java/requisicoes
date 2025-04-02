# Requisições HTTP com Java (HttpClient)

Desde o Java 11, o pacote `java.net.http` trouxe uma forma moderna e nativa de realizar requisições HTTP. Essa abordagem facilita a comunicação com APIs REST, algo muito comum no backend com Java e Spring.

---

## ✅ Objetivo

Fazer uma requisição HTTP GET para uma API, usando `HttpClient`, e retornar o corpo da resposta (normalmente em JSON).

---

## 🔧 Exemplo prático

```java
import java.io.IOException;
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;

public class ConsumoApi {
    public String obterDados(String endereco) {
        HttpClient client = HttpClient.newHttpClient();

        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create(endereco))
                .build();

        HttpResponse<String> response = null;
        try {
            response = client.send(request, HttpResponse.BodyHandlers.ofString());
        } catch (IOException | InterruptedException e) {
            throw new RuntimeException(e);
        }

        return response.body();
    }
}
```

---

## ✍️ Explicação passo a passo

### 1. Criar o cliente HTTP
```java
HttpClient client = HttpClient.newHttpClient();
```
- Cria um cliente HTTP reutilizável para enviar requisições.

### 2. Construir a requisição
```java
HttpRequest request = HttpRequest.newBuilder()
        .uri(URI.create(endereco))
        .build();
```
- `newBuilder()` inicia a construção da requisição.
- `.uri()` define o destino da requisição.
- `.build()` finaliza e retorna a requisição.

> Por padrão, o método HTTP é GET.

### 3. Enviar a requisição e obter resposta
```java
response = client.send(request, HttpResponse.BodyHandlers.ofString());
```
- Envia a requisição e espera pela resposta.
- O corpo da resposta será retornado como `String`.

### 4. Tratar exceções
- IOException: problemas de rede.
- InterruptedException: se a thread for interrompida.

### 5. Retornar a resposta
```java
return response.body();
```
- Retorna apenas o corpo da resposta HTTP (ex: JSON).

---

## 🔄 Fluxo resumido

1. Cria o `HttpClient`
2. Constrói o `HttpRequest`
3. Envia a requisição e recebe o `HttpResponse`
4. Extrai o `body()` e retorna

---

## 🖊️ Exemplo de uso

```java
ConsumoApi consumo = new ConsumoApi();
String json = consumo.obterDados("https://api.exemplo.com/dados");
System.out.println(json);
```

---

## 📅 Próximos passos
- Adicionar cabeçalhos personalizados (Authorization, Content-Type)
- Enviar dados via POST
- Fazer requisições assíncronas com `.sendAsync()`
- Usar bibliotecas como Gson ou Jackson para converter o JSON em objetos Java

---
