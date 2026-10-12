# Диаграммы

## Диаграмма последовательности

```mermaid
sequenceDiagram
    actor User as Сотрудник
    participant App as RAG-система
    participant KB as База знаний
    participant LLM as LLM-модель

    User->>App: Задать вопрос
    App->>KB: Найти подходящие документы
    KB-->>App: Фрагменты документов
    App->>LLM: Передать вопрос и найденный контекст
    LLM-->>App: Сгенерированный ответ
    App-->>User: Показать ответ со ссылками на источники
```

## Диаграмма классов
```mermaid
classDiagram
    class User {
        +int id
        +string name
    }

    class Question {
        +int id
        +string text
    }

    class Answer {
        +int id
        +string text
    }

    class Document {
        +int id
        +string title
    }

    User "1" --> "*" Question
    Question "1" --> "1" Answer
    Answer "*" --> "*" Document
```