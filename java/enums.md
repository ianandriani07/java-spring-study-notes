# Enums em Java

Enums (ou tipos enumerados) são uma forma de representar um conjunto fixo de constantes em Java. Eles são muito úteis quando você precisa de um grupo de valores que não mudam, como dias da semana, status de pedidos, tipos de usuário, etc.

---

## ✅ O que é um Enum?

Um `enum` é um tipo especial de classe que representa um conjunto de constantes nomeadas.

```java
public enum DiaDaSemana {
    SEGUNDA, TERCA, QUARTA, QUINTA, SEXTA, SABADO, DOMINGO
}
```

Você pode usar essas constantes como qualquer outro valor:

```java
DiaDaSemana hoje = DiaDaSemana.SEGUNDA;
```

---

## 🧐 Quando usar enums?
- Quando você tem um conjunto fixo de valores relacionados.
- Para evitar o uso de strings ou números mágicos no código.
- Para facilitar comparações e validações.

---

## 💡 Dicas
- Enums podem ter construtores, métodos e atributos.
- São usados com frequência em switches:

```java
switch (hoje) {
    case SEGUNDA:
        System.out.println("Começo da semana!");
        break;
    case SEXTA:
        System.out.println("Quase fim de semana!");
        break;
    default:
        System.out.println("Dia comum.");
}
```

---

## ✨ Enum com atributos e métodos

```java
public enum StatusPedido {
    PENDENTE("Pendente"),
    PROCESSANDO("Processando"),
    ENVIADO("Enviado"),
    ENTREGUE("Entregue");

    private String descricao;

    StatusPedido(String descricao) {
        this.descricao = descricao;
    }

    public String getDescricao() {
        return descricao;
    }
}
```

```java
StatusPedido status = StatusPedido.ENVIADO;
System.out.println(status.getDescricao()); // Saída: Enviado
```

---

