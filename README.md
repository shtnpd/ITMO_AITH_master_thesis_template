# ITMO AITH Master Thesis Template

Этот репозиторий содержит LaTeX-шаблон для магистерской диссертации AI Talent Hub. Шаблон упрощает форматирование, обеспечивает соответствие требованиям и включает готовые настройки для таблиц, изображений, ссылок и библиографии.

Кому удобнее работать в OverLeaf, можете забрать шаблон [тут](https://www.overleaf.com/read/mgqyggdgbknt#906037).

## 📂 Структура проекта

```
ITMO_AITH_master_thesis_template/
├── main.tex               % Основной файл диссертации
├── preamble.tex           % Преамбула с настройками LaTeX
├── abbreviations.tex      % Список сокращений
├── terms.tex              % Список терминов
├── bibliography.bib       % Файл библиографии
│
├── configs/               % Конфигурационные файлы
│   ├── config-tables.tex  % Настройки таблиц
│   ├── config-images.tex  % Настройки изображений
│   ├── config-lists.tex   % Настройки списков
│   ├── config-formulas.tex % Настройки формул
│
├── chapters/              % Главы диссертации
│   ├── intro.tex          % Введение
│   ├── chapter1.tex       % Глава 1
│   ├── chapter2.tex       % Глава 2
│   ├── conclusion.tex     % Заключение
│
├── appendix/              % Приложения
│   ├── appA.tex           % Пример приложения
│
├── images/                % Каталог изображений
│   ├── example.jpg        % Пример изображения
```

## 🚀 Установка и использование

### Требования
Для работы с шаблоном требуется:
- **TeX Live** (рекомендуется) или **MikTeX**
- **Editor**: [TeXstudio](https://www.texstudio.org/) / Overleaf / VS Code с плагином LaTeX Workshop

### Компиляция
1. Откройте `main.tex` в вашем LaTeX-редакторе.
2. Компилируйте через **XeLaTeX** или **pdflatex** (рекомендуется несколько прогонов, чтобы корректно отобразились ссылки и библиография):
   ```bash
   pdflatex main.tex
   bibtex main
   pdflatex main.tex
   pdflatex main.tex
   ```
   или **latexmk**
   ```bash
   latexmk -xelatex -f -interaction=nonstopmode main.tex
   ```

## ✍️ Как редактировать

### Добавление глав
Для добавления новой главы:
1. Создайте файл `chapters/chapterN.tex`
2. Вставьте в `main.tex` строку:
   ```latex
   \include{chapters/chapterN}
   ```

### Добавление изображений
Поместите файлы в папку `images/`, затем вставьте в текст:
```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\textwidth]{images/example.jpg}
    \caption{Описание изображения}
    \label{fig:example}
\end{figure}
```

### Работа с таблицами
Шаблон поддерживает многостраничные таблицы с динамическим выравниванием заголовков:
```latex
\begin{longtable}{|p{4cm}|p{4cm}|p{4cm}|}
    \LeftCaption
    \caption{Название таблицы} \\
    \hline
    Столбец 1 & Столбец 2 & Столбец 3 \\
    \hline
    \endfirsthead

    \RightCaption
    \caption[]{Продолжение таблицы} \\
    \hline
    \endhead

    Данные 1 & Данные 2 & Данные 3 \\
    \hline
\end{longtable}
```

### Настройка библиографии
Используйте `bibliography.bib` для добавления источников. Пример ссылки в тексте:
```latex
\cite{some_reference}
```

