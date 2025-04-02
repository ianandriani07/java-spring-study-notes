# Annotations em Java

Anotações (ou *annotations*) são usadas para adicionar **metadados** ao código Java. Elas são muito usadas por frameworks como o Spring para definir comportamentos sem precisar escrever muita lógica manualmente.

---

## ✅ O que é uma annotation?

Uma annotation é uma "marca" que você coloca no seu código para dizer algo a mais sobre ele. Por exemplo:

```java
@Override
public String toString() {
    return "Texto";
}
```

`@Override` diz ao compilador que você está sobrescrevendo um método da superclasse.

---

## 🧐 Exemplos comuns

- `@Override`: informa que um método está sendo sobrescrito.
- `@Deprecated`: indica que algo não deve mais ser usado.
- `@SuppressWarnings`: suprime avisos do compilador.

```java
@Deprecated
public void metodoAntigo() {
    // ...
}
```

---

## 🌟 Annotations personalizadas

Você também pode criar suas próprias annotations:

```java
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface Logavel {
}
```

Essa annotation pode ser usada para marcar métodos que devem ser logados, por exemplo.

---

## 💡 Dicas
- As annotations são muito usadas com **reflection**, principalmente por frameworks.
- No Spring, annotations como `@Component`, `@Service`, `@Autowired` etc. são essenciais.
- O `@Retention` define **quando** a annotation está disponível (em tempo de compilação ou execução).
- O `@Target` define **onde** ela pode ser usada (método, classe, atributo, etc).

---

## ✨ Exemplo com Spring

```java
@RestController
@RequestMapping("/usuarios")
public class UsuarioController {

    @GetMapping
    public List<Usuario> listar() {
        return service.todos();
    }
}
```

Nesse exemplo, `@RestController`, `@RequestMapping` e `@GetMapping` são todas annotations fornecidas pelo Spring para configurar uma API REST.

---
