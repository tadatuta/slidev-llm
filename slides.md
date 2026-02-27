---
theme: default
title: Как работают LLM
author: grinenko.pro
transition: slide-left
colorSchema: dark
canvasWidth: 980
aspectRatio: 16/9
fonts:
  sans: Manrope
  serif: Inter
  mono: JetBrains Mono
  provider: google
defaults:
  transition: slide-left
htmlAttrs:
  lang: ru
---

<div style="text-align: center;">

<div style="margin-bottom: 1.5em;">
  <span style="font-size: 5rem;">🧠</span>
</div>

# Как работают большие языковые модели

<p style="font-size: 1.3rem; color: #A0A3B5; font-family: 'Inter', sans-serif; max-width: 600px; margin: 1em auto;">
Простым языком о технологии, которая меняет мир
</p>

<div style="margin-top: 2em; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; color: rgba(230, 232, 240, 0.35);">
grinenko.pro — 2026
</div>

</div>

---
layout: center
---

## Что такое LLM?

<div style="margin-top: 1.5em; max-width: 700px;">

<div v-click class="accent-block" style="margin-bottom: 1.5em;">

**LLM** — Large Language Model — это программа, которая научилась **понимать и генерировать текст**, прочитав огромное количество написанного людьми.

</div>

<div v-click style="text-align: center; margin: 2em 0;">
<span style="font-size: 3.5rem;">📚</span>  →  <span style="font-size: 3.5rem;">🤖</span>  →  <span style="font-size: 3.5rem;">💬</span>
</div>

<p v-click style="text-align: center; color: #A0A3B5; font-size: 1.05rem;">
Представьте себе <strong>очень начитанного собеседника</strong>, который прочёл<br/>
миллиарды страниц текста и уловил в них закономерности
</p>

</div>

---

## Откуда берутся данные

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 0.8em; margin-top: 0.8em;">

<div v-click class="card" style="padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.2em;">📖</span>
<h3 style="font-size: 0.95rem; margin: 0.2em 0;">Книги и статьи</h3>
<p style="font-size: 0.85rem; margin: 0;">Научная, художественная литература, энциклопедии — миллионы текстов</p>
</div>

<div v-click class="card" style="padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.2em;">🌐</span>
<h3 style="font-size: 0.95rem; margin: 0.2em 0;">Веб-страницы</h3>
<p style="font-size: 0.85rem; margin: 0;">Миллиарды страниц из интернета: форумы, блоги, документация</p>
</div>

<div v-click class="card" style="padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.2em;">💻</span>
<h3 style="font-size: 0.95rem; margin: 0.2em 0;">Исходный код</h3>
<p style="font-size: 0.85rem; margin: 0;">Миллионы репозиториев с программным кодом на разных языках</p>
</div>

<div v-click class="card" style="padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.2em;">🗣️</span>
<h3 style="font-size: 0.95rem; margin: 0.2em 0;">Диалоги</h3>
<p style="font-size: 0.85rem; margin: 0;">Субтитры, переписки, интервью — живая речь людей</p>
</div>

</div>

<p v-click style="text-align: center; margin-top: 0.8em; color: #A0A3B5; font-size: 0.9rem;">
Объём данных: <span class="stat" style="font-size: 1.3rem;">триллионы</span> слов — больше, чем человек прочтёт за тысячу жизней
</p>

---

## Как модель учится

<div style="max-width: 800px; margin-top: 1em;">

<v-clicks>

- 🔍 Модель читает текст и **ищет закономерности** — какие слова чаще стоят рядом, как строятся фразы

- 🧩 Она не **запоминает** тексты дословно — она извлекает **паттерны и правила**

- ⚖️ За каждую верную «догадку» модель получает «очки», за ошибку — «штраф». Так настраиваются миллиарды внутренних параметров

- 🔄 Этот процесс повторяется **миллионы раз** на огромных вычислительных кластерах

</v-clicks>

<div v-click class="accent-block" style="margin-top: 1.5em;">

**Аналогия:** Как ребёнок учит язык — не зубрит словарь, а слышит тысячи фраз и начинает чувствовать, «как правильно»

</div>

</div>

---

## Токенизация: как модель «видит» текст

<p style="color: #A0A3B5; margin-bottom: 1.5em;">
Модель не читает буквы — она разбивает текст на <strong>токены</strong>: кусочки слов
</p>

<div v-click style="text-align: center; margin: 1.5em 0;">

<span class="token token-1">Искус</span><span class="token token-2">ственный</span>
<span class="token token-3">интел</span><span class="token token-4">лект</span>
<span class="token token-1">помо</span><span class="token token-2">гает</span>
<span class="token token-3">людям</span>

</div>

<div v-click style="text-align: center; margin: 0.5em 0 1.5em;">
<span style="font-size: 2rem;">↓</span>
</div>

<div v-click style="display: flex; justify-content: center; gap: 0.5em; flex-wrap: wrap;">
<span class="token token-1">15482</span>
<span class="token token-2">7291</span>
<span class="token token-3">4830</span>
<span class="token token-4">9215</span>
<span class="token token-1">3847</span>
<span class="token token-2">6102</span>
<span class="token token-3">2956</span>
</div>

<p v-click style="text-align: center; color: #A0A3B5; margin-top: 1.5em; font-size: 0.95rem;">
Каждый токен — это число. Модель работает <strong>только с числами</strong>, не с текстом
</p>

---
layout: center
---

## Предсказание следующего слова

<div style="max-width: 700px; margin-top: 1em;">

<p v-click style="font-size: 1.15rem;">
Главный принцип LLM удивительно прост:
</p>

<div v-click style="text-align: center; margin: 1.5em 0;">
<div class="accent-block" style="font-size: 1.4rem; text-align: center;">
Прочитай всё, что написано до этого, и <strong>угадай следующее слово</strong>
</div>
</div>

<div v-click style="text-align: center; margin: 1.5em 0;">
<span style="font-family: 'JetBrains Mono', monospace; font-size: 1.3rem;">
«Солнце встаёт на&nbsp;
<span style="color: #00FA9A; border-bottom: 2px solid #00FA9A;">___</span>
»
</span>
</div>

<div v-click style="display: flex; justify-content: center; gap: 1.5em; margin-top: 1em;">
<span class="card" style="padding: 0.5em 1em; text-align: center;"><strong>востоке</strong><br/><span style="color: #00FA9A; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem;">94%</span></span>
<span class="card" style="padding: 0.5em 1em; text-align: center;">западе<br/><span style="color: #D68C45; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem;">3%</span></span>
<span class="card" style="padding: 0.5em 1em; text-align: center;">горизонте<br/><span style="color: #A0A3B5; font-family: 'JetBrains Mono', monospace; font-size: 0.85rem;">2%</span></span>
</div>

<p v-click style="text-align: center; color: #A0A3B5; margin-top: 1.5em; font-size: 0.95rem;">
По сути, это <strong>автодополнение на стероидах</strong> — как T9, но в миллиарды раз умнее
</p>

</div>

---

## Механизм внимания (Attention)

<div style="max-width: 800px; margin-top: 1em;">

<p v-click>
Когда вы пишете «<em>Она подошла к окну и открыла <strong>его</strong></em>» — нам понятно, что «его» — это окно. А как это понимает модель?
</p>

<div v-click class="accent-block" style="margin: 1.5em 0;">

**Механизм внимания** позволяет модели «смотреть» на все предыдущие слова одновременно и определять, какие из них **самые важные** для понимания текущего

</div>

<div v-click style="text-align: center; margin: 1.5em 0; font-family: 'JetBrains Mono', monospace; font-size: 1.05rem; line-height: 2.5;">
<span style="opacity: 0.3;">Она</span>
<span style="opacity: 0.3;">подошла</span>
<span style="opacity: 0.3;">к</span>
<span style="color: #00FA9A; text-decoration: underline; text-underline-offset: 4px;">окну</span>
<span style="opacity: 0.3;">и</span>
<span style="opacity: 0.5;">открыла</span>
<span style="color: #D68C45; font-weight: 700;">его</span>
<span style="display: block; font-size: 0.75rem; color: #A0A3B5; margin-top: 0.3em;">← «его» обращает внимание на «окну» →</span>
</div>

<p v-click style="color: #A0A3B5; font-size: 0.95rem;">
Именно эта идея, описанная в статье <strong>«Attention Is All You Need»</strong> (2017), стала революцией в AI
</p>

</div>

---

## Промпт и контекстное окно

<div style="max-width: 800px; margin-top: 1em;">

<div v-click>

**Промпт** (prompt) — это ваш запрос к модели. Всё, что вы пишете в чат — это промпт.

</div>

<div v-click style="margin: 1.5em 0;">

**Контекстное окно** — это «рабочая память» модели. Она видит только то, что помещается в это окно.

</div>

<div v-click style="display: flex; align-items: center; gap: 1em; margin: 1.5em 0;">
<div class="card" style="flex: 1; text-align: center;">
<div style="font-family: 'JetBrains Mono', monospace; color: #00FA9A; font-size: 0.9rem; margin-bottom: 0.5em;">GPT-3 (2020)</div>
<div class="stat" style="font-size: 2rem;">4K</div>
<div style="color: #A0A3B5; font-size: 0.85rem;">токенов</div>
</div>
<div style="font-size: 1.5rem; color: #A0A3B5;">→</div>
<div class="card" style="flex: 1; text-align: center;">
<div style="font-family: 'JetBrains Mono', monospace; color: #D68C45; font-size: 0.9rem; margin-bottom: 0.5em;">GPT-4 (2023)</div>
<div class="stat" style="font-size: 2rem;">128K</div>
<div style="color: #A0A3B5; font-size: 0.85rem;">токенов</div>
</div>
<div style="font-size: 1.5rem; color: #A0A3B5;">→</div>
<div class="card" style="flex: 1; text-align: center;">
<div style="font-family: 'JetBrains Mono', monospace; color: #5D2E8C; font-size: 0.9rem; margin-bottom: 0.5em;">Gemini (2025)</div>
<div class="stat" style="font-size: 2rem;">1M+</div>
<div style="color: #A0A3B5; font-size: 0.85rem;">токенов</div>
</div>
</div>

<p v-click style="color: #A0A3B5; font-size: 0.95rem;">
Чем больше окно — тем больше контекста модель может учитывать при ответе
</p>

</div>

---
layout: center
---

## Галлюцинации: главное ограничение

<div style="max-width: 700px; margin-top: 1em;">

<div v-click style="text-align: center; margin-bottom: 1.5em;">
<span style="font-size: 4rem;">⚠️</span>
</div>

<div v-click class="accent-block" style="border-left-color: #D68C45; margin-bottom: 1.5em;">

Модель **не знает**, что правда, а что нет. Она генерирует текст, который **выглядит** правдоподобным, на основе паттернов.

</div>

<v-clicks>

- 🎭 **Галлюцинация** — это уверенный, но неверный ответ модели

- 📊 Модель не обращается к базе данных фактов — она **достраивает текст** по вероятности

- ✅ Поэтому важно всегда **проверять** критически важную информацию

</v-clicks>

<p v-click style="text-align: center; color: #A0A3B5; margin-top: 1.5em; font-size: 0.95rem;">
LLM — это мощный <strong>инструмент</strong>, а не источник абсолютной истины
</p>

</div>

---

## Где LLM уже применяются

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 0.7em; margin-top: 0.8em;">

<div v-click class="card" style="text-align: center; padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.3em;">✍️</span>
<h3 style="font-size: 0.95rem; margin: 0.3em 0;">Тексты</h3>
<p style="font-size: 0.8rem; margin: 0;">Копирайтинг, рассылки, перевод, рерайт</p>
</div>

<div v-click class="card" style="text-align: center; padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.3em;">🔎</span>
<h3 style="font-size: 0.95rem; margin: 0.3em 0;">Поиск и анализ</h3>
<p style="font-size: 0.8rem; margin: 0;">Извлечение данных из документов, саммаризация</p>
</div>

<div v-click class="card" style="text-align: center; padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.3em;">🤝</span>
<h3 style="font-size: 0.95rem; margin: 0.3em 0;">Поддержка</h3>
<p style="font-size: 0.8rem; margin: 0;">Чат-боты, FAQ, автоответчики</p>
</div>

<div v-click class="card" style="text-align: center; padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.3em;">💻</span>
<h3 style="font-size: 0.95rem; margin: 0.3em 0;">Код</h3>
<p style="font-size: 0.8rem; margin: 0;">Помощь в разработке, отладка, рефакторинг</p>
</div>

<div v-click class="card" style="text-align: center; padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.3em;">🎓</span>
<h3 style="font-size: 0.95rem; margin: 0.3em 0;">Обучение</h3>
<p style="font-size: 0.8rem; margin: 0;">Персональные ассистенты, квизы, адаптивное обучение</p>
</div>

<div v-click class="card" style="text-align: center; padding: 0.8em;">
<span style="font-size: 2rem; display: block; margin-bottom: 0.3em;">📊</span>
<h3 style="font-size: 0.95rem; margin: 0.3em 0;">Бизнес</h3>
<p style="font-size: 0.8rem; margin: 0;">Отчёты, прогнозы, автоматизация рутины</p>
</div>

</div>

---
layout: center
---

<div style="text-align: center;">

<div style="margin-bottom: 1em;">
<span style="font-size: 4rem;">🚀</span>
</div>

## Ключевые тейкавеи

<div style="max-width: 600px; margin: 1.5em auto 0; text-align: left;">

<v-clicks>

- LLM — это **модель языка**, не база знаний и не разум

- Она **предсказывает** следующее слово на основе статистики

- Механизм **внимания** позволяет учитывать контекст

- Галлюцинации — не баг, а **свойство** технологии

- LLM — мощный **усилитель** ваших возможностей

</v-clicks>

</div>

<div v-click style="margin-top: 2.5em;">
<p style="color: #A0A3B5; font-size: 1.1rem; font-family: 'Inter', sans-serif;">
Спасибо за внимание!
</p>
<p style="font-family: 'JetBrains Mono', monospace; font-size: 0.85rem; color: rgba(230, 232, 240, 0.35); margin-top: 0.5em;">
grinenko.pro
</p>
</div>

</div>
