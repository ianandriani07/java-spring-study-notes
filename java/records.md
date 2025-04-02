# Records em Java

`record` é um tipo de classe introduzido no Java 14 (como preview) e oficialmente no Java 16. Ele é usado para declarar **classes imutáveis** com menos código, ideais para transportar dados (DTOs, por exemplo).

---

## ✅ O que é um record?

Um record é uma forma concisa de criar uma classe que:
- É imutável (os campos são `final` por padrão);
- Tem `equals()`, `hashCode()` e `toString()` gerados automaticamente;
- Foca em carregar dados, não lógica complexa.

```java
public record Pessoa(String nome, int idade) {}
```

Uso:
```java
Pessoa p = new Pessoa("Ian", 25);
System.out.println(p.nome()); // Ian
System.out.println(p.idade()); // 25
```

---

## 🧐 Quando usar records?
- Para criar classes simples de dados (como DTOs).
- Quando quiser garantir imutabilidade e ter menos código repetitivo.
- Quando a classe não precisa de herança (records não podem estender outras classes).

---

## 💡 Dicas
- Campos de um record são implicitamente `private final`.
- Os nomes dos campos viram automaticamente métodos públicos (getters).
- Pode ter métodos, construtores compactos e validadores:

```java
public record Produto(String nome, double preco) {
    public Produto {
        if (preco < 0) {
            throw new IllegalArgumentException("Preço não pode ser negativo");
        }
    }
}
```

---

## ⚠️ Limitações
- Não pode extender outra classe.
- Não pode ter campos mutáveis.
- É mais indicado para estruturas de dados simples.

---
