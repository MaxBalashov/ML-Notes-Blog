Перенес все в ноутбук '../_notebooks/2020-05-26-DS-fastpages-blog.ipynb'

# Data Science блог с помощью Fastpages

В конце февраля 2020 года ребята из `fast.ai` представили миру `fastpages` - платформу для ведения блога.

Сразу скажу, что `fastpages` основан на `Jekyll`, о котором на Хабре есть множество постов.

Главное отличительная черта и приемущество `fastpages` состоит в поддерживаемых из коробки форматах постов:
- Jupyter ноутбуки (расширение `.ipynb`);
- Markdown файлы (расширение `.md`);
- Word файлы (расширение `.docx`)

Таким образом, автору блога необходимо сохранить пост в любом из перечисланных выше форматах в соответствующей директории:
- './_notebooks/' для `.ipynb`;
- './_posts/' для `.md`;
- './_word/' для `.docx`.

А все остальное сделает `fastpages`, как утверждают его авторы.
`fastpages` использует Github Pages для хостинга и Github Actions для автоматизации публикации постов.

Таким образом `fastpages` является доработкой связки Github Pages + `Jekyll`, где можно сразу же из Jupyter ноутбука получить опубликованный пост.


## Первичная настройка `fastpages`
Если хотите самостоятельно разобраться, то вот [официальная инструкция](https://github.com/fastai/fastpages#setup-instructions) по настройке в репозитории `fastpages`.

Процесс настройки `fastpages`:
1. Создать собственную копию репозитория из шаблона `fastpages` по [ссылке](https://github.com/fastai/fastpages/generate)
![](../images/ds-blog-fastpages/new-repo-fastpages.png)
2. Далее автоматически откроется pull request (через ~ 30 секунд), который отвечает за настройку вашего блога, чтобы он мог начать работать.
![](../images/ds-blog-fastpages/init-setup.png)
3. Вам нужно выполнить иструкции из полученного pull request'a и вы получите свою собственную уже работающую платформу для блога.

Также есть [видео туториал](https://youtu.be/L0boq3zqazI) с пошаговой настройкой.


## fast_template - младший брат fastpages
Стоит упомянуть, что ранее `fast.ai` выпустили аналогичный проект под названием `fast_template`, который еще проще в настройке, но не поддерживает автоматическое создание постов из Word и Jupyter файлов, а также многие другие функции перечисленные выше. Поскольку `fastpages` более гибок и расширяем, его авторы рекомендуют использовать его там, где это возможно.

Авторы предполагают, что `fast_template` может быть лучшим вариантом для тех, кто ведет не технические блоги. В этом случае посты можно создавать только с помощью встроенного онлайн-редактора Github, не заморачиваясь с использованием `git`.

## Jupyter Notebooks & Fastpages
`fastpages` из коробки поддерживает различные удобства.

### Options via FrontMatter
Первая ячейка в вашем Jupyter ноутбуке (а также первые строки в Markdown файлах) содержит метаданные, которые могут включать/выключать опции связанные с постом.

```
# Title
> Awesome summary

- toc:true- branch: master
- badges: true
- comments: true
- author: Hamel Husain & Jeremy Howard
- categories: [fastpages, jupyter]
```

- `toc` - при значении `true` автоматически будет сгенерировано оглавление поста;
- `badges` - при значении `true` отображаются ссылки `Google Colab` и `GitHub`;
- `comments` - при значении `true` будут включены комментарии ([больше деталей](https://github.com/fastai/fastpages#enabling-comments));
- `author` - при значении `true` отображаются имена авторов;
- `categories` - позволяют группировать посты по тегам (на странице "Tags").

Для указания таких в Markdown файлах необходимо в начале файла задать опции как и в ноутбуке, только поместив эти метаданные между строк содержащих по три минуса, т.е. `---`.

Выглядит это так:

```
---
toc: true
layout: post
description: Awesome description.
categories: [markdown]
title: Title
---
```

### Сворачивание/скрытие кода
TODO: выяснить все про `#collapse`

Приятной функциональностью этого движка для блога является возможность скрывать код и/или результаты его выполнения. Это позволяет не нагружать посты отображением простыни кода или огромного количество принтов (что бывает при обучении нейросетей по эпохам), скрывая эти большие по размеру элементы, но не выкидывая их из поста на совсем.

Поместив флаг `#collapse-hide`, в первую строку любой ячейки, вы скроете код этой ячейки внутри поста. Но в замен появится кнопка, позволяющая показать эту ячейку.

Флаг `#collapse-show` позволяет показать ячейку по умолчанию, но дает читателю возможность скрыть ее.

Чтобы полностью скрыть ячейки (а не просто свернуть их), смотрите [сюда](https://github.com/fastai/fastpages#hide-inputoutput-cells).


### Интерактивные графики с помощью `Altair`
TODO: только в ноутбуке

### Отображение таблиц
TODO: только в ноутбуке


## Другие возможности ``


## Pros&Cons
Плюсы:
- отсутствие сторонней рекламы;
- 
Минусы:
- непонятно, как сделать структуру
- латиница в git : "_posts/2020-05-26-DS \320\221\320\273\320\276\320\263 \321\201 \320\277\320\276\320\274\320\276\321\210\321\214\321\216 Fastpages.md"


## DS/ML блоги
- [Анализ малых данных](https://dyakonov.org/) блог Александра Дьяконова;
- Andrej Karpathy [github.io](http://karpathy.github.io/), [medium](https://medium.com/@karpathy);
- [Machine Learning Mastery](https://machinelearningmastery.com/blog/) by Jason Brownlee;


### Блоги компаний
- [Fast.ai](https://www.fast.ai/) + [fastpages blog](https://fastpages.fast.ai/);
- [Airbnb](https://medium.com/airbnb-engineering/ai/home);
- [Uber](https://eng.uber.com/category/articles/ai/);
- [OpenAI](https://openai.com/blog/);
- [DeepMind](https://deepmind.com/blog);
- [Nvidia](https://blogs.nvidia.com/blog/category/deep-learning/) + [AI podcast](https://blogs.nvidia.com/ai-podcast/);
- Microsoft [AI blog](https://blogs.microsoft.com/ai/) + [ML devblogs](https://devblogs.microsoft.com/cse/tag/,machine-learning-ml/)


## Полезные ссылки:
- [Репозиторий](https://github.com/fastai/fastpages#setup-instructions) проекта `fastpages`;
- [Introducing fastpages](https://fastpages.fast.ai/fastpages/jupyter/2020/02/21/introducing-fastpages.html);