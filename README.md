# RuLitBank

В данном репозитории представлены результаты курсовой работы по теме "Разработка датасета для распознавания именованных сущностей при помощи переноса разметки".

В файле code.ipynb представлен код с описанием алгоритма по переносу разметки именованных сущностей с корпуса англоязычных литературных произведений LitBank (https://github.com/dbamman/litbank) на русскоязычный корпус переводов этих произведений.  
Блок Hunalign посвящен выравниванию предложений (https://github.com/danielvarga/hunalign), в конце создается 2 таблицы: 1) с выровненными предложениями и их доверительным значением; 2) с выровненными предложениями и набором именованных сущностей, встречаемых в данном предложении на английском языке.  
Блок Fast_align работает с выравниванием слов (https://github.com/clab/fast_align), сначала создается таблица выравнивания слов, где английский язык является мишенью, а русский язык - источником, и берется разметка именованных сущностей для английского языка. Затем языки меняются местами, и создается таблица с перенесенной разметкой.  
После этого к русскому тексту применяются три NER модели ([Natasha-Slovnet](https://github.com/natasha/slovnet), [Stanza](https://stanfordnlp.github.io/stanza/ner.html), [DeepPavlov RuBERT](https://docs.deeppavlov.ai/en/master/features/models/bert.html)), и их разметка сравнивается с перенесенной разметкой.

В этом репозитории представлено 4 папки с результатами работы данного алгоритма для некоторых текстов:

- папка texts содержит используемые для переноса разметки части текстов на русском и английском языках по книгам
- папка hunalign содержит таблицы для каждого произведения с выровненными предложениями
- папка fastalign содержит таблицы для каждого произведения с выровненными словами
- папка tags содержит таблицы для каждого произведения с перенесенной разметкой и с разметкой трех NER моделей - Natasha-Slovnet, Stanza и DeepPavlov RuBERT

В файле book translations.xlsx хранятся ссылки на оригиналы используемых текстов на английском и русском языках.

Выполнено: Мария Сухарева, студентка 3 курса ОП "Фундаментальная и Компьютерная лингвистика", группа БКЛ-201  
Научный руководитель: Сериков Олег Алексеевич  
Консультант: Волошина Екатерина Юрьевна
