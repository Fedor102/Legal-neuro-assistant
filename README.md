# Юридический нейро-ассистент для анализа вопросов, связанных с Трудовым кодексом РФ
Этот проект представляет собой нейросетевого ассистента, специализирующегося на анализе вопросов трудового законодательства Российской Федерации. Основой работы ассистента является Трудовой кодекс РФ (ТК РФ), структурированный для быстрого поиска ответов по статьям и главам. Модель ориентирована на точное и объективное предоставление информации на основе положений законодательства, без субъективных интерпретаций и гипотез.

# Основные функции
- Поиск информации по ТК РФ: Ассистент отвечает на вопросы, ссылаясь на конкретные статьи и главы Трудового кодекса.
- Векторизация и индексация данных: ТК РФ был преобразован в векторное представление для эффективного поиска и точных ответов.
- Устранение ошибок: Включены инструменты постобработки для снижения количества "галлюцинаций" (некорректных ответов) модели.
- Оптимизация данных: Выполнена предварительная очистка PDF-файлов с помощью сервиса Unstructured для повышения качества текстов.
- Реранжирование результатов поиска: Интеграция Cohere ReRank позволяет выбирать документы с наиболее релевантной информацией для более точных ответов.
# Структура проекта
Импорт и настройка необходимых библиотек:

- Установка библиотек transformers, llama-index, peft, и phoenix.
- Подключение к API OpenAI и Hugging Face для доступа к языковым моделям.
- Скачивание и подготовка Трудового кодекса РФ:

Автоматическое скачивание PDF-файла ТК РФ и извлечение текста с помощью PDFReader.
Создание векторного индекса на основе текста для быстрого поиска.
Обработка данных с использованием сервиса Unstructured:

Очистка и структурирование данных для исключения шумов и нерелевантной информации.
Настройка и обучение модели LLaMA с использованием LoRA (PEFT):

Использование техники LoRA для настройки языковой модели на юриспруденцию.
Применение квантования для экономии памяти.
Системный промпт:

Промпт, ориентированный на точные ответы, без субъективных интерпретаций.
Трассировка модели с помощью Phoenix:

Встроенные инструменты трассировки позволяют выявлять и устранять ошибки и галлюцинации модели в реальном времени.
Улучшение точности с помощью реранжирования (Cohere ReRank):

Реранжирование позволяет выбрать наиболее релевантные документы для ответа на вопросы пользователя, улучшая точность и снижая вероятность ошибок.

# Запустите скрипт, чтобы задать вопрос, и получите точный ответ с указанием статьи и главы ТК РФ.

 Пример запроса
query = "В какой статье говорится про отпуск?"

response = query_engine.query(query)
print(response)
Заметки по улучшению
Рерангирование и очистка данных заметно повысили качество ответов.
Дополнительные настройки промпта позволили снизить субъективность ответов.
