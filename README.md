# DSL for HTML

Написан язык гипертекстовой разметки на языке Kotlin.

Пример использования:

```
fun main() {
  html {
    head {
      title { + "Example page" }
    }
    body {
      p { + "Text" }
    }
  }.toHtml().apply { println(it) }
}
```

Метод `toHtml` возвращает строку, являющуюся аналогом на языке HTML. Из внешнего контекста доступен вызов только функции `html`, остальные функции-теги доступны внутри лямбда-функции, передаваемой в функцию html. Запрещенное вложение тегов в HTML равносильно запрещенному вложению контекстов в данном DSL.
