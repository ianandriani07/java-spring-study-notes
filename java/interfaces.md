# Interfaces em Java

Interfaces são contratos que definem um conjunto de métodos que uma classe deve implementar. Elas são muito utilizadas para garantir que diferentes classes possam ser tratadas da mesma forma, mesmo que tenham implementações diferentes.

---

## ✅ O que é uma interface?

Uma interface é um tipo de classe especial que contém apenas assinaturas de métodos (sem implementação), constantes e métodos `default` ou `static`. Ela serve como um contrato para as classes que a implementam.

```java
public interface Animal {
    void fazerSom();
}

public class Cachorro implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("Au Au!");
    }
}
```

---

## 🧐 Quando usar interfaces?
- Quando você quer garantir que várias classes sigam o mesmo contrato.
- Quando quiser aplicar o princípio da inversão de dependência (muito usado no Spring).
- Quando quiser permitir a flexibilidade de múltiplas implementações.

---

## 💡 Dicas
- A partir do Java 8, interfaces podem ter métodos com implementação usando `default`.
- Uma classe pode implementar **várias interfaces**, o que é uma forma de "herança múltipla" no Java.
- Interfaces são essenciais para trabalhar com **injeção de dependência** em frameworks como o Spring.

---

## ✨ Exemplo com `default`

```java
public interface Saudacao {
    default void dizerOi() {
        System.out.println("Oi!");
    }
}

public class Pessoa implements Saudacao {
    // Herda o comportamento default
}
```

---
