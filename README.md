<div align="center">

<h1>kimi-k3-in-c</h1>

<h3>Модель на 2,78 триллиона параметров. Один CPU. 8 ГБ ОЗУ.</h3>

<p>Инференс Kimi K3 на портативном C99.<br>Без BLAS. Без фреймворков. Без GPU.</p>

<p>
<a href="https://github.com/FareedKhan-dev/kimi-k3-in-c/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/FareedKhan-dev/kimi-k3-in-c/ci.yml?branch=main&style=flat-square&label=CI" alt="CI"></a>
<a href="LICENSE"><img src="https://img.shields.io/badge/license-Apache--2.0-blue?style=flat-square" alt="Лицензия"></a>
<a href="Makefile"><img src="https://img.shields.io/badge/C99-portable-lightgrey?style=flat-square" alt="C99"></a>
<a href="#requirements"><img src="https://img.shields.io/badge/platform-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey?style=flat-square" alt="Платформа"></a>
<a href="CHANGELOG.md"><img src="https://img.shields.io/badge/version-1.1.0-brightgreen?style=flat-square" alt="Версия"></a>
</p>

<table>
<tr>
<td align="center"><b>2.78T</b><br><sub>параметров</sub></td>
<td align="center"><b>1.56 TB</b><br><sub>чекпоинт на диске</sub></td>
<td align="center"><b>8.24 GB</b><br><sub>пиковый RSS, измерено</sub></td>
<td align="center"><b>176 KB</b><br><sub>весь движок</sub></td>
<td align="center"><b>0</b><br><sub>GPU</sub></td>
</tr>
</table>

<p><b>Та же модель на 2,78 триллиона параметров, тот же ответ — на любой вашей машине.</b><br>Больше памяти — только выше скорость:</p>

<table>
<tr>
<th align="left">ваша машина</th>
<th align="right">ОЗУ</th>
<th align="right">время на токен</th>
<th align="left">что происходит</th>
</tr>
<tr>
<td align="left">обычный ноутбук</td>
<td align="right">8 GB</td>
<td align="right"><b>26.5 s</b></td>
<td>вся модель подгружается с диска на каждом шаге</td>
</tr>
<tr>
<td align="left">топовый ноутбук</td>
<td align="right">32 GB</td>
<td align="right"><b>24.2 s</b></td>
<td>часть модели уже находится в памяти</td>
</tr>
<tr>
<td align="left">настольный ПК</td>
<td align="right">64 GB</td>
<td align="right"><b>19.8 s</b></td>
<td>ещё больше модели в памяти</td>
</tr>
<tr>
<td align="left">мощная рабочая станция</td>
<td align="right">128 GB+</td>
<td align="right"><b>5.6 s</b></td>
<td>модель полностью помещается в память, ожидания диска больше нет</td>
</tr>
</table>

<sub>Тот же короткий промпт при любом объёме памяти, и вывод <b>побайтово идентичен</b> от самой маленькой машины до самой большой — меняется только время. Одна машина, 124 ядра, быстрый NVMe-накопитель: первые три строки всё ещё читают модель с диска на каждом шаге, поэтому на более медленном диске там будет медленнее, тогда как строка 128 GB+ держит всё в памяти и больше не ждёт диск. На той же машине v1.0.0 сделала вычисления на токен примерно в <b>8&times;</b> легче, повторный вопрос в чате — в <b>3.9&times;</b> быстрее, а длинные промпты — примерно в <b>половину</b> дешевле. (Токен — это примерно короткий фрагмент слова; два запускаемых демо ниже — это оригинальные записи на более медленном диске, поэтому время там чуть выше.) Полные данные — в <a href="docs/data/">docs/data/</a>.</sub>

<hr>

<p>
  <img src="docs/images/patrick_pray.png" height="44" align="middle" alt="">
  <i>Открыт к позициям в области AI-исследований и к PhD-программам. <a href="https://drive.google.com/file/d/1yW5xHDS6Mr9ByrkCgVve85OqF4UOPv9K/view?usp=sharing">Резюме</a>.</i>
</p>

<hr>

<sub>Порты под macOS, Windows и NEON, режим чата, пресет <code>ultra</code>, более быстрые ядра MXFP4 и длинный список исправлений парсера — всё это сделали люди, указанные ниже. <a href="CONTRIBUTORS.md">Кто что сделал</a>.</sub>

<p>
<a href="https://github.com/douglasmun"><img src="https://avatars.githubusercontent.com/u/12515041?v=4&s=96" width="48" height="48" alt="douglasmun" title="douglasmun"></a>
<a href="https://github.com/cwwjacobs"><img src="https://avatars.githubusercontent.com/u/251295277?v=4&s=96" width="48" height="48" alt="cwwjacobs" title="cwwjacobs"></a>
<a href="https://github.com/mahavak"><img src="https://avatars.githubusercontent.com/u/38126162?v=4&s=96" width="48" height="48" alt="mahavak" title="mahavak"></a>
<a href="https://github.com/sulfierry"><img src="https://avatars.githubusercontent.com/u/22729945?v=4&s=96" width="48" height="48" alt="sulfierry" title="sulfierry"></a>
<a href="https://github.com/Barba2k2"><img src="https://avatars.githubusercontent.com/u/67913962?v=4&s=96" width="48" height="48" alt="Barba2k2" title="Barba2k2"></a>
<a href="https://github.com/ShaalanMarwan"><img src="https://avatars.githubusercontent.com/u/26276966?v=4&s=96" width="48" height="48" alt="ShaalanMarwan" title="ShaalanMarwan"></a>
<a href="https://github.com/TROY665"><img src="https://avatars.githubusercontent.com/u/84645104?v=4&s=96" width="48" height="48" alt="TROY665" title="TROY665"></a>
<a href="https://github.com/ysgao"><img src="https://avatars.githubusercontent.com/u/1692765?v=4&s=96" width="48" height="48" alt="ysgao" title="ysgao"></a>
<a href="https://github.com/openchat-ai"><img src="https://avatars.githubusercontent.com/u/274358245?v=4&s=96" width="48" height="48" alt="openchat-ai" title="openchat-ai"></a>
<a href="https://github.com/arafatsolok"><img src="https://avatars.githubusercontent.com/u/58647359?v=4&s=96" width="48" height="48" alt="arafatsolok" title="arafatsolok"></a>
<br>
<a href="https://github.com/genesisrevelationinc-debug"><img src="https://avatars.githubusercontent.com/u/243808510?v=4&s=96" width="48" height="48" alt="genesisrevelationinc-debug" title="genesisrevelationinc-debug"></a>
<a href="https://github.com/AuricTW"><img src="https://avatars.githubusercontent.com/u/108772778?v=4&s=96" width="48" height="48" alt="AuricTW" title="AuricTW"></a>
<a href="https://github.com/biokraft"><img src="https://avatars.githubusercontent.com/u/35855749?v=4&s=96" width="48" height="48" alt="biokraft" title="biokraft"></a>
<a href="https://github.com/cablepull"><img src="https://avatars.githubusercontent.com/u/135179737?v=4&s=96" width="48" height="48" alt="cablepull" title="cablepull"></a>
<a href="https://github.com/Avicennasis"><img src="https://avatars.githubusercontent.com/u/913872?v=4&s=96" width="48" height="48" alt="Avicennasis" title="Avicennasis"></a>
<a href="https://github.com/Deobot2"><img src="https://avatars.githubusercontent.com/u/131834087?v=4&s=96" width="48" height="48" alt="Deobot2" title="Deobot2"></a>
<a href="https://github.com/BlakeEvans22"><img src="https://avatars.githubusercontent.com/u/32441662?v=4&s=96" width="48" height="48" alt="BlakeEvans22" title="BlakeEvans22"></a>
<a href="https://github.com/FermiHart"><img src="https://avatars.githubusercontent.com/u/100219585?v=4&s=96" width="48" height="48" alt="FermiHart" title="FermiHart"></a>
<a href="https://github.com/santhoshsathish94"><img src="https://avatars.githubusercontent.com/u/11693712?v=4&s=96" width="48" height="48" alt="santhoshsathish94" title="santhoshsathish94"></a>
<a href="https://github.com/Irfanwani"><img src="https://avatars.githubusercontent.com/u/62456735?v=4&s=96" width="48" height="48" alt="Irfanwani" title="Irfanwani"></a>
</p>

</div>

<br>```console
$ ./bin/k3 ~/k3model --trunk ~/k3trunk --preset laptop \
           --tok ~/k3model --prompt "The capital of France is" --gen 8 --incremental

--- generated text ---
 Paris.",
+            "The Eiffel
----------------------
8 tokens in 261.5 s, 32.69 s/token average
PEAK RSS for the whole run: 8.24 GB
```Медленно и отвечая правильно, в 8.24 GB, из чекпоинта размером 1.56 TB. Данная batch-команда намеренно запрашивает сырое продолжение. Официальный чекпоинт Kimi K3 также поддерживает чат; используйте XTML REPL ниже, когда вам нужны ответы и история многошагового диалога. Выделите тому же batch-запросу больше памяти — ответ не изменится, изменится только время:```console
$ ./bin/k3 ~/k3model --trunk ~/k3trunk --preset server \
           --tok ~/k3model --prompt "def fibonacci(n):" --gen 28 --incremental

--- generated text ---
    if n <= 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci
----------------------
28 tokens in 299.3 s, 10.69 s/token average
PEAK RSS for the whole run: 127.92 GB
```Каждая иллюстрация в этом документе взята из результатов измерений в
[`docs/data/`](docs/data/).

![Небольшой резидентный рабочий набор наверху, сама модель на NVMe внизу и несколько подписанных каналов между ними](docs/images/main_architecture_with_spongbob.png)

Плотный ствол остаётся в памяти на выбранную вами глубину, а остальное подгружается потоково; 1,45 ТБ маршрутизируемых экспертов никогда не находятся в памяти постоянно и умножаются прямо из их упакованной 4-битной формы. Следствие — **одна и та же модель работает и в 8 ГБ, и в 224 ГБ и выдаёт побайтово идентичный результат при любом бюджете между ними.**

Четыре решения о том, где живут байты, переносят её с кластера на ноутбук, и ответ внизу тот же, что и ответ наверху:

![Четыре шага от серверного кластера до обычного ноутбука, с одинаковым выводом на обоих концах](docs/images/fit_cascade.png)

[Часть II](#part-ii-how-it-works) собирает каждый блок на обеих диаграммах с нуля, по одному компоненту за раз.

---

## Содержание

**[Часть I: Начало работы](#part-i-getting-started)**

- [Требования](#requirements)
- [Быстрый старт](#quick-start): клонирование, сборка и проверка примерно за минуту, без модели
- [Полная настройка](#full-setup): весь путь до генерации текста
- [Использование](#usage)
  - [Синопсис](#synopsis)
  - [Опции промпта](#prompt-options)
  - [Опции памяти](#memory-options)
  - [Опции генерации](#generation-options)
  - [Диагностические опции](#diagnostic-options)
  - [Коды выхода](#exit-codes)
  - [Переменные окружения](#environment-variables)
  - [Разобранные примеры](#worked-examples)
- [Выбор пресета](#choosing-a-preset)
- [Чтение отчёта о запуске](#reading-the-run-report)
- [Частые вопросы](#common-questions)

**[Часть II: Как это работает](#part-ii-how-it-works)**

- [Проблема: модель, которая не помещается](#the-problem-a-model-that-does-not-fit)
- [Четыре сокращения](#the-four-reductions)
- [Машина и её допущения](#the-machine-and-what-it-assumes)
- [Кодовая база](#the-codebase)
- [Три инварианта](#three-invariants)
- [1. Чтение чекпоинта 1,56 ТБ по его заголовкам](#1-reading-a-156-tb-checkpoint-from-its-headers)
- [2. Ридер конфига, который отказывается гадать](#2-the-config-reader-that-refuses-to-guess)
- [3. Токенизатор, байт в байт](#3-the-tokenizer-byte-for-byte)
- [4. Сокращение первое: эксперты уже поставляются по полбайта](#4-reduction-one-the-experts-already-ship-at-half-a-byte)
- [5. Ядра с контрактом на плавающую точку](#5-kernels-with-a-floating-point-contract)
- [6. Сокращение второе: KDA, attention с памятью, которая никогда не растёт](#6-reduction-two-kda-attention-with-a-memory-that-never-grows)
- [7. Сокращение третье: MLA, один латент вместо девяноста шести голов](#7-reduction-three-mla-one-latent-instead-of-ninety-six-heads)
- [8. Остаточные связи attention: слои, которые оглядываются назад](#8-attention-residuals-layers-that-look-back)
- [9. Выбор 16 экспертов из 896](#9-picking-16-experts-of-896)
- [10. Упаковка ствола: 93 слоя, по одному чтению на каждый](#10-packing-the-trunk-93-layers-one-read-each)
- [11. Сокращение четвёртое: потоковая передача ствола превращает порог в регулятор](#11-reduction-four-streaming-the-trunk-turns-a-floor-into-a-dial)
- [12. LRU-кэш для экспертов](#12-an-lru-cache-for-the-experts)
- [13. Каким должен быть этот кэш? Спросите у трейса](#13-how-big-should-that-cache-be-ask-the-trace)

**[Часть III: Валидация](#part-iii-validation)**

- [Лестница гейтов](#the-gate-ladder)
- [Сначала крошечный оракул](#a-tiny-oracle-first)
- [Доказательство на полном чекпоинте](#proving-it-on-the-full-checkpoint)
- [Первые токены](#the-first-tokens)
- [Устойчивая генерация: текст на входе, текст на выходе](#sustained-generation-text-in-text-out)

**[Часть IV: Измерения](#part-iv-measurements)**

- [Лестница памяти: от 8 ГБ до 224 ГБ](#the-memory-ladder-8-gb-to-224-gb)
- [Кэш, который не участвовал](#the-cache-that-was-not-participating)
- [Распределение важнее объёма](#allocation-beats-capacity)
- [Измерение измерения](#measuring-the-measurement)
- [Хранилище — это вся игра](#storage-is-the-whole-game)
- [Почему ствол не квантуется](#why-the-trunk-is-not-quantised)

**[Часть V: Справочник](#part-v-reference)**

- [Область применения](#scope)
- [Закрытие реестра](#closing-the-ledger)
- [Документация](#documentation)
- [Разработка](#development)
- [История звёзд](#star-history)
- [Лицензия](#license)

---

# Часть I: Начало работы

## Требования

Узкое место — хранилище: **чекпоинт — 1,56 ТБ.** Всё остальное — обычно.

| | | |
|---|---|---|
| **ОС** | Linux, x86-64 (эталон); macOS/arm64 и Windows/x86-64 также собираются и проходят все гейты | uses `O_DIRECT`, `posix_memalign`, `getrusage` -- портировано для Windows через MSYS2 MinGW-w64 (см. `src/io/k3_portable_io.h`) |
| **ЦП** | AVX2 + FMA на x86-64, NEON на arm64 | AVX-512 не требуется. `make portable` нацелена на generic AVX2 на x86-64 |
| **ОЗУ** | от 8 ГБ и выше | каждый пресет работает; больше памяти — быстрее, но результат тот же |
| **Хранилище** | ~1,7 ТБ свободно | чекпоинт 1,56 ТБ + 109 ГБ упакованного ствола, желательно на быстром локальном диске |
| **Тулчейн** | GCC ≥ 9 или Clang ≥ 10 | GNU make или CMake |
| **Python** | 3.9+ | для инструментов загрузки, упаковки и анализа; не требуется для `make test` |

Токенизатор и ридер конфига — переносимый C99 и собираются где угодно. Без чекпоинта вы всё равно можете сделать всё из раздела [Быстрый старт](#quick-start).

## Быстрый старт

Клонируйте, соберите и запустите весь набор тестов. **Без чекпоинта, без сети, без Python**. Всё это занимает около минуты.```bash
git clone https://github.com/FareedKhan-dev/kimi-k3-in-c.git
cd kimi-k3-in-c

make -j            # seconds. Seven C files, a compiler and OpenMP
make test          # under a minute
```Заканчивается так, либо произошла ошибка:```
GATE 1  teacher forcing : 32/32 positions match tf_pred
        generated span  : 20/20  <- must be exact
GATE 2  greedy decode   : 20/20 generated tokens match full_ids
GATE 3  incremental    : 20/20 generated tokens match full_ids  <- KV cache + carried KDA state

VERDICT: ENGINE MATCHES THE REFERENCE EXACTLY

ALL WEIGHTLESS TESTS PASSED
```Это и есть весь движок: каждое ядро, потоковый кэш, ридер safetensors, ридер конфига, токенизатор и сквозной оракул на 13-слойной модели, собранной с тем же графом тензоров, что и релизная, сверенный с PyTorch-референсом из фикстур, закоммиченных в репозиторий.

Одно из опубликованных измерений также воспроизводится на месте, по трейсу, записанному во время полного прогона на 93 слоях (для этого нужен Python 3.9+ и numpy):```bash
python3 tools/sim_cache.py tests/fixtures/expert_trace.bin
```100 096 запросов к экспертам, с повторной печатью таблицы ёмкости из
[`expert-cache-capacity.txt`](docs/data/expert-cache-capacity.txt).

## Полная настройка

Шесть шагов от пустой директории до сгенерированного текста. Медленный только шаг 4.

Скрипт `./scripts/k3-doctor.sh` можно запускать в любой момент. Он проверяет тулчейн, подбирает пресет под объём вашей RAM, замеряет диск и выводит точную команду для следующего шага.

### Шаг 0. Клонирование```bash
git clone https://github.com/FareedKhan-dev/kimi-k3-in-c.git
cd kimi-k3-in-c
```Около 45 МБ, в основном диаграммы и тестовые фикстуры.

### Шаг 1. Проверка машины```bash
./scripts/k3-doctor.sh
```Займёт около минуты — измеряет диск тем же способом, каким движок его читает. Завершается с ненулевым кодом, если машина вообще не способна запустить модель.

### Шаг 2. Сборка```bash
make -j
```Секунды. Единственные зависимости — компилятор C99, libm и OpenMP. CMake тоже подойдёт:```bash
cmake -B build && cmake --build build -j && ctest --test-dir build
```### Шаг 3. Проверка перед скачиванием```bash
make test
```Стоит сделать до того, как качать 1,56 ТБ: это доказывает, что движок совпадает с референсом на модели с тем же графом тензоров, и для этого не нужно ничего, кроме репозитория.

### Шаг 4. Скачивание чекпоинта

**1,56 ТБ — значит часы, а не минуты.** Получите токен на
[huggingface.co/settings/tokens](https://huggingface.co/settings/tokens):```bash
export HF_TOKEN=hf_your_token_here          # read from the environment, never echoed
./scripts/download-model.sh ~/k3model       # resumable, re-run to continue
```Скрипт завершается проверкой количества шардов, точного суммарного объёма и затем каждого шарда по отдельности — сверяет размеры с опубликованными значениями:```text
verifying…
  shards : 96 (expect 96)
  bytes  : 1560936091448 (expect 1560936091448)
  shards : all 96 match their published sizes individually
  RESULT : byte-exact match
```Частичное скачивание не падает громко — оно выдаёт неверные токены. Считайте `FAIL` здесь остановкой. Проверка пошардно ещё и превращает «перекачать 1,56 терабайта» в «перекачать вот этот один файл на 17 гигабайт», и ловит единственный случай, который не ловит сумма: два шарда ошиблись в противоположные стороны на одну и ту же величину.

### Шаг 5. Упаковка ствола (trunk)```bash
./scripts/pack-trunk.sh ~/k3model ~/k3trunk
```Около четырёх минут, один раз. Переписывает 93 плотных слоя в один файл на 109 ГБ, где слой *L* лежит по известному смещению и читается за один вызов. **Именно это превращает требование к памяти в регулятор.** Кладите результат на самый быстрый диск, который у вас есть.

### Шаг 6. Запуск```bash
./bin/k3 ~/k3model --trunk ~/k3trunk --preset workstation \
         --tok ~/k3model --prompt "The capital of France is" --gen 8 --incremental
```Токенизатор поставляется вместе с чекпоинтом — именно поэтому `--tok` указывает на директорию модели.

### Куда всё попадает```
kimi-k3-in-c/    ~45 MB   source, docs, images, and bin/k3
~/k3model/      1.56 TB   96 shards · config.json · tiktoken.model · tokenizer_config.json
~/k3trunk/       109 GB   trunk.bin · trunk.json, on the fastest disk you have
```Первый токен любого запуска загружает с диска каждый закреплённый (pinned) слой — около 108 ГБ на пресете `server`, поэтому он занимает куда больше времени, чем установившийся темп. Эта цена платится один раз за запуск, а не за каждый токен.

## Использование

### Краткая сводка (Synopsis)```
k3 <model_dir> [prompt] [memory] [generation] [diagnostics]
````<model_dir>` — директория с шардами `.safetensors`. Она обязательна для любого запуска, но `--help`, `--version` и `--list-presets` работают и без неё:```bash
./bin/k3 --help
./bin/k3 --version
./bin/k3 --list-presets
```### Опции промпта

Вне `--chat` ровно один из этих вариантов обязателен. Отсутствие любого или указание более одного — ошибка использования (код выхода 2).

| флаг | аргумент | |
|---|---|---|
| `--prompt` | `TEXT` | токенизировать TEXT и запустить. **Требует `--tok`.** |
| `--prompt-file` | `PATH` | токенизировать байты файла. **Требует `--tok`.** Предпочтителен для всего не-ASCII: шелл перекодирует `argv`, а файл читается побайтово без изменений |
| `--ids` | `1,2,3` | токены напрямую по id. Токенизатор вообще не загружается, поэтому работает даже на машине без файлов токенизатора. Воспроизводимый канал, который используют тесты |```bash
# text in
./bin/k3 ~/k3model --tok ~/k3model --prompt "The capital of France is" ...

# text in, from a file. Use this for CJK, emoji, accents
printf 'La capitale de la France est' > /tmp/p.txt
./bin/k3 ~/k3model --tok ~/k3model --prompt-file /tmp/p.txt ...

# ids in, ids out, no tokenizer needed
./bin/k3 ~/k3model --ids 1008,10484,318,15383,387 ...
```### Опции памяти

| флаг | аргумент | по умолчанию | |
|---|---|---|---|
| `--preset` | `ИМЯ` | нет | `laptop` · `desktop` · `workstation` · `server` · `max`. Задаёт оба бюджета ниже |
| `--trunk` | `ДИРЕКТОРИЯ` | выкл | директория с упакованным стволом из шага 5. **Именно это включает потоковую загрузку.** Без неё ствол загружается полностью резидентно, около 113.5 ГБ |
| `--trunk-gb` | `X` | 16 | бюджет под закреплённые слои плюс кольцо потоковой загрузки |
| `--cache-gb` | `X` | 64 | бюджет под LRU-кэш маршрутизируемых экспертов |
| `--trunk-ring` | `N` | 2 | слоты кольца потоковой загрузки: один слой считается, остальные читаются параллельно. Каждый дополнительный слот стоит один слот RAM, и бюджет всё равно побеждает, если не помещается |
| `--threads` | `N` | число физ. ядер | потоки OpenMP. На Linux по умолчанию — число физических ядер, а не «один поток на логическое ядро» как у OpenMP, что здесь на SMT-процессорах медленнее. `OMP_NUM_THREADS`, если задана, соблюдается |
| `--ultra-low-memory` | нет | выкл | потоково читать точные строки эмбеддингов и куски lm_head; полный рекомпьют также переиспользует один слот рекуррентного состояния. Требует `--trunk` |

Пресет `ultra` выбирает `--ultra-low-memory` с кольцом ствола 2.5 ГБ и кэшем экспертов 0.31 ГБ. Это путь «хоть как-то запустилось» для машин класса 8 ГБ, а не пресет для интерактивной скорости; точность модели, маршрутизация Top-K и все 93 слоя остаются без изменений.

`--preset` и два флага `-gb` задают одни и те же два числа, так что пресет — просто сокращение. Порядок имеет значение, если вы их смешиваете: более поздний флаг побеждает, поэтому
`--preset server --cache-gb 40` даёт бюджет ствола от сервера с кэшем 40 ГБ.

> **`--preset` без `--trunk` не даёт ничего полезного.** Каждый пресет предполагает, что ствол потоковый. Опустите `--trunk` — и движок загрузит все 113.5 ГБ резидентно, какой бы бюджет вы ни запросили.```bash
./bin/k3 ~/k3model --trunk ~/k3trunk --preset desktop --tok ~/k3model \
  --chat --system "You are a helpful assistant." \
  --history my-session.jsonl --incremental
```REPL принимает обычный текст плюс `/help`, `/reset` и `/exit`. Он выводит полную каноническую запись, включая `<think>…</think>` и `<response>…</response>`. Когда указан `--history`, он пишет переносимый, человеко-читаемый JSONL-файл вроде:```json
{"role":"system","content":"You are a helpful assistant."}
{"role":"user","content":"Explain cache locality."}
{"role":"assistant","content":"…","reasoning_content":"…"}
```Считайте этот файл чувствительным: он может содержать каждое сообщение пользователя и полную запись рассуждений ассистента, которая нужна K3 для честного продолжения диалога. При перезапуске движок валидирует, повторно рендерит и повторно делает префилл транскрипта; он сознательно не сериализует непрозрачное состояние KV, MLA или KDA. Внутри одной сессии под `--incremental` состояние, построенное ходом, сохраняется, и следующий ход делает префилл только своего нового хвоста, когда отрендеренный транскрипт начинается ровно с тех id, которыми кормили состояние (REPL печатает, сколько позиций было переиспользовано); `/reset` или любое иное расхождение начинает заново. Переданный `--system` должен точь-в-точь совпадать с существующей начальной системной записью. Буквальный текст контрольных маркеров в сообщениях пользователя кодируется как обычный текст, но никогда — как управляющий токен XTML.

Чат по умолчанию — `--gen 4096` и, как и пакетная генерация, жадный декодинг. Передача любого из `--temperature`, `--top-p` или `--seed` включает сэмплирование (температура `1.0`, top-p `0.95` если не указано); `--greedy` форсирует argmax даже в этом случае. Сэмплирование использует
PCG32; `--seed N` детерминированно выводит один поток на каждый ход ассистента, так что повтор того же транскрипта с тем же seed воспроизводим. Лимиты 32K промпта / 4096 генерации — это существующие лимиты движка, а не новые лимиты чата; чат чётко падает и сохраняет историю, когда достигнут либо контекст, либо безопасное размещение KV.

Размышление (thinking) включено по умолчанию с `thinking_effort=max` — ровно то, что делает собственный токенизатор чекпоинта, когда `apply_chat_template` ничего не получает; `--thinking-effort low` или `high` меняет только эту настройку. `--no-think` — это `thinking=False` у энкодера: нет системного сообщения о thinking_effort, предыдущие ходы ассистента рендерятся без канала размышлений, а промпт генерации сразу открывает канал ответа, так что модель отвечает мгновенно и REPL не печатает блок `<think>`. На потоковом стволе это самый большой рычаг скорости: в прогоне на реальном чекпоинте 119 из 150 токенов ответа из пяти слов были блоком размышлений. Рассуждения, уже сохранённые в транскрипте, остаются на месте и рендерятся снова при следующем запуске диалога с включённым thinking. Оба флага побайтово и по id точны относительно официального токенизатора в `tests/unit/test_chat.c`.

Чат использует тот же потоковый ствол на CPU и тот же кэш маршрутизируемых экспертов, что и пакетный режим. `--preset`, `--trunk-gb` и `--cache-gb` сохраняют ровно прежний смысл: эксперты не предзагружаются, а ствол остаётся потоковым с диска, если только существующие флаги памяти не просят иного.```bash
# Full-model, one-token proof of life on an 8 GB-class ARM64 machine.
./bin/k3 ~/k3model --trunk ~/k3trunk --preset ultra \
         --tok ~/k3model --prompt "The capital of France is" --gen 1

# Smallest possible run, the 8 GB floor.
./bin/k3 ~/k3model --trunk ~/k3trunk --preset laptop \
         --tok ~/k3model --prompt "Hello! My name is" --gen 16 --incremental

# Fastest per gigabyte. Pins 90 of 93 trunk layers.
./bin/k3 ~/k3model --trunk ~/k3trunk --preset server \
         --tok ~/k3model --prompt "def fibonacci(n):" --gen 28 --incremental

# Hand-tuned split instead of a preset: everything to the trunk.
./bin/k3 ~/k3model --trunk ~/k3trunk --trunk-gb 110 --cache-gb 13 \
         --tok ~/k3model --prompt-file prompt.txt --gen 32 --incremental

# Reproducible: ids in, ids out, no tokenizer, JSON results.
./bin/k3 ~/k3model --trunk ~/k3trunk --preset desktop \
         --ids 1008,10484,318,15383,387 --gen 8 --incremental --out run.json

# Capture a cache trace, then replay it offline at any capacity.
./bin/k3 ~/k3model --trunk ~/k3trunk --preset workstation \
         --ids 1008,10484,318,15383,387 --gen 8 --incremental \
         --dump-cache-trace /tmp/trace
python3 tools/sim_cache.py /tmp/trace/expert_trace.bin

# Elementwise logit comparison against the PyTorch reference.
./bin/k3 ~/k3model --trunk ~/k3trunk --preset server \
         --ids 3,4,5,6,7 --gen 1 --dump-logits /tmp/c_logits.bin
python3 tools/cmp_logits.py /tmp/c_logits.bin ref_logits.json

# Partial shard set: bind only the first 8 layers.
./bin/k3 ~/k3model --trunk ~/k3trunk --layers 8 \
         --ids 1,2,3 --gen 1

# Under a hard memory ceiling, which is how the ladder was measured.
systemd-run --scope --user -q -p MemoryMax=8G -p MemorySwapMax=0 \
  ./bin/k3 ~/k3model --trunk ~/k3trunk --trunk-gb 2.5 --cache-gb 0.5 \
           --ids 1008,10484,318,15383,387 --gen 8 --incremental
```## Выбор пресета```console
$ ./bin/k3 --list-presets
presets (trunk / expert-cache, in GB):
  ultra          2.50 / 0.31    ~3 GB planned: streamed model tables, one state slot. Slow.
  laptop         3.00 / 1.00    8.2 GB peak RSS. The ordinary-path floor.
  desktop       16.00 / 10.00   31.9 GB peak RSS.
  workstation   60.00 / 30.00   95.5 GB peak RSS; the expert cache starts to matter here.
  server       110.00 / 13.00   ~128 GB peak RSS; 90 of 93 trunk layers pinned. Fastest.
  max          110.00 / 109.00  ~224 GB peak RSS; trunk pinned and a large expert cache.

All presets stream the trunk, so they need --trunk <packed_dir>.
Run scripts/k3-doctor.sh to see which one this machine fits.
```![Что каждый пресет реально стоит в памяти](docs/images/preset_ladder.png)

Границы взяты из измеренной лесенки, а doctor ориентируется на `MemAvailable`, а не на `MemTotal`:```bash
if   [ "$AVAIL_GB" -ge 192 ]; then PRESET=server;      EXPECT="~6 s/token"
elif [ "$AVAIL_GB" -ge  96 ]; then PRESET=workstation; EXPECT="~6-20 s/token"
elif [ "$AVAIL_GB" -ge  32 ]; then PRESET=desktop;     EXPECT="~24 s/token"
elif [ "$AVAIL_GB" -ge  10 ]; then PRESET=laptop;      EXPECT="~27 s/token"
else PRESET=""; fi
```Две вещи, которые стоит знать перед выбором:

- **`max` в этих замерах не быстрее `server`**. Дополнительные 96 ГБ ничего не дают вне шумового порога.
- **Пресету нужно чуть больше свободной памяти, чем его пик RSS.** Движок отказывается от любого плана выше 95% доступной памяти, чтобы оставить место всему вне плана, так что `server` с примерно 128 ГБ требует около 135 ГБ доступно, а не 128.
- **Отдавайте память сначала стволу, а не кэшу экспертов.** При фиксированном бюджете 128 ГБ это дало выигрыш 1.69×. Данные — в [Allocation beats capacity](#allocation-beats-capacity).```
cache [final step]
  requests     : 1472  hits 1472 (100.00%)  misses 0  evictions 729
                 TRUE resident hit rate 50.48%
I/O share of wall clock: 71.1%  (trunk 62.4 s + experts 34.2 s of 135.8 s)
trunk [final]
  pinned 48/93 layers, ring 1 slots
  read 368.65 GB in 62.40 s (5908 MB/s)
PEAK RSS for the whole run: 94.74 GB   <- quote this, not the plan
```Три числа несут смысл:

- **`TRUE resident hit rate`**: эксперты, отданные из RAM. Сырой счётчик `hits` считает также экспертов, которых префетчер только что подтянул с диска, поэтому он показывает 100% при любом размере кэша; резидентный показатель печатается строкой ниже.
- **`I/O share of wall clock`**: доля дискового времени в общем времени, измерено от 41% до 61% по всей лесенке.
- **`PEAK RSS`**: из `getrusage`, после прогона. Это и есть показатель памяти; предварительный план чуть выше него.

## Частые вопросы

**Память висит около 113 ГБ даже на маленьком пресете.** Опущен `--trunk`. Без директории с упакованным стволом весь ствол грузится резидентно; каждый пресет предполагает потоковую загрузку.

**Не-ASCII промпт токенизируется странно.** Шелл перекодирует `argv`, так что движок получает другие байты, чем вы набрали. Положите промпт в файл и используйте `--prompt-file` — он читается побайтово без изменений.

**`--prompt/--prompt-file` требуют `--tok DIR`.** Токенизатор поставляется с чекпоинтом, поэтому добавьте `--tok ~/k3model`. Движок завершается, а не гадает, где лежит словарь. Чтобы вообще пропустить токенизатор, передайте id токенов через `--ids`.

**Пропускная способность сильно ниже таблицы.** Почти всегда — хранилище. `python3 tools/devbw.py <файл-на-этом-диске>` меряет диск тем же способом, каким его читает движок — большими случайными чтениями `O_DIRECT` с глубиной очереди 1 и 16, чего `dd` не делает. Сетевые тома в несколько раз медленнее локального NVMe; держите `~/k3trunk` локально.

**Прогон отказался стартовать из-за KV-кэша.** Контекст стоит около 2.37 МБ на позицию независимо от бюджета, и движок считает это заранее, а не обнаруживает через час. Укоротите запрос или уберите `--incremental` — он вообще не несёт KV-кэша.

**Нужны ли все 1,56 ТБ?** Для генерации — да. Для разработки — нет: `make test` не нужно вообще ничего, а `--layers N` работает на частичных наборах шардов. `scripts/download-model.sh <dest> --layers N` качает только шарды, нужные этим слоям — около 7 ГБ для `N=1` и 125 ГБ для `N=8`. Это для прогона пайплайна на маленьком диске; префикс слоёв — не модель и не даёт её вывода.

**Почему без BLAS?** Потому что каждый matmul здесь должен давать те же биты на каждой машине. Тесты сверяют движок с PyTorch-референсом точно, а не «с допуском» — и это работает лишь если порядок суммирования каждого скалярного произведения фиксирован и известен. Библиотека BLAS сама выбирает разбиение на блоки и порядок редукции, который может различаться между версиями, между вендорами (OpenBLAS, MKL, Accelerate) и между числами потоков на одной машине. Каждый из этих ответов численно корректен, и ни один не совпадает с другими побитово. Ядра в `src/core/k3_ops.c` существуют, чтобы зафиксировать этот порядок: пути AVX2 и NEON воспроизводят скалярную редукцию точно, и `test_ops` это проверяет. Это ещё и избавляет сборку от зависимости, которая ставится по-разному на каждой платформе, — ради ядер, которые всё равно не являются узким местом. Прогон ограничен скоростью, с которой ствол и эксперты сходят с диска, а не арифметикой.

**macOS, Windows, WSL?** Linux — референсная платформа. macOS/arm64 собирается обычным `make` (см. платформенный блок в Makefile). Windows тоже собирается нативно через MSYS2 MinGW-w64 GCC (`pacman -S mingw-w64-x86_64-gcc`, затем откройте именно шелл «MSYS2 MinGW x64» — `make`, `make test` и `make test-all` проходят все гейты без изменений, включая полно-модельный оракул и паритет токенизатора на реальных весах Kimi K3. Четыре вызова, специфичных для Linux — `O_DIRECT`, `pread`, `posix_memalign` и `getrusage` — портированы, см. `src/io/k3_portable_io.h`. Один реальный баг всплыл при портировании и стоит знать, если вы расширяете код под Windows: `_aligned_malloc`, лежащий в основе шима `posix_memalign`, должен освобождаться через `_aligned_free`, а не обычным `free`; у POSIX-ового `posix_memalign` такого ограничения нет, так что ошибиться легко и тихо — компилируется, а Windows завершает процесс с `STATUS_HEAP_CORRUPTION` лишь когда повреждённые метаданные аллокатора реально используются. `make asan`/`make ubsan` переключаются на Clang под Windows (`pacman -S mingw-w64-clang-x86_64-clang mingw-w64-clang-x86_64-compiler-rt`): пакет MinGW-w64 GCC вообще не поставляет рантайм санитайзеров, проверено напрямую, а не «предположено». WSL тоже работает без изменений — это просто Linux; токенизатор и ридер конфига — портативный C99 в любом случае и собирается везде, включая CI.

---

# Часть II: Как это работает

## Проблема: модель, которая не помещается

[Kimi K3](https://huggingface.co/moonshotai/Kimi-K3) имеет **2,78 триллиона параметров** и весит **1,56 терабайта** в поставке. Ни одна потребительская машина не вмещает её, и ожидание более мощного железа не помогает — потому что стена не в скорости, а в ёмкости.

Но это [смесь экспертов](https://huggingface.co/blog/moe) (mixture of experts), так что лишь 16 из 896 экспертов на слой срабатывают на каждый токен, а остальные спят на диске. Держите всегда-активную часть в памяти, подгружайте спящих экспертов потоково — и она помещается в **8,24 гигабайта** на одном CPU без GPU.

Наивная потребность — та, что подразумевает каждый подсчёт параметров.

![Наивная потребность: каждый параметр резидентно в bf16](docs/images/eq_naive_memory.png)

Так что 5,56 терабайта — число, которое нужно побить.

![Один токен будит 16 экспертов и оставляет 880 спящими](docs/images/moe-sparsity.png)

Kimi K3 имеет 93 слоя. Слой 0 — обычный плотный feed-forward слой, так что остальные 92 слоя маршрутизируют, и каждый из них выбирает top-16 экспертов из 896.

![Лишь 16 из 896 экспертов срабатывают на слой, так что большая часть модели спит](docs/images/eq_sparsity_ratio.png)

Около 104 миллиардов параметров активны на любой токен из 2,78 триллиона — это 3.7 процента. Остальные 96.3 процента всё ещё должны где-то существовать в досягаемости, но не обязаны быть в RAM.

Подсчёт реальных байтов на диске, а не гадание:```text
=== shard census: what the 1.56 TB actually is ===
shards            : 96
total bytes       : 1560936091448  (1.56 TB)

--- routed experts (the part that is streamed, never resident) ---
  experts total     : 82,432   (896 routed x 92 MoE layers)
  bytes per expert  : 17,547,264  exactly
                      = 33,030,144 params x 0.53125 bytes
                      = 0.5 bytes/nibble + 1/32 byte for the shared E8M0 scale
  routed expert set : 82,432 x 17,547,264 = 1.447 TB
```Существует **82 432 маршрутизируемых эксперта**, каждый занимает ровно **17 547 264 байта**. Вместе они — **1,447 терабайта**, то есть 93 процента всего чекпоинта. Всё остальное (проекции внимания, роутеры, нормы, эмбеддинги) — оставшиеся 7 процентов.

![Где живут 1,56 ТБ: 93% — это эксперты, которые никогда не загружаются](docs/images/bytes_census.png)

Эта перепись — вся стратегия в одной картинке. Если эти 1,447 терабайта могут быть доступными, но никогда не резидентными, проблема памяти схлопывается более чем на порядок до написания хотя бы одного ядра.

![Всегда активное множество: 113.49 ГБ в bf16, всё остальное — потоковое](docs/images/eq_resident_set.png)

Остаётся **56 743 648 000 параметров**, или 113.49 гигабайта в bfloat16. Из них 108.81 ГБ — послойный плотный ствол и 4.70 ГБ — таблица эмбеддингов плюс выходная голова.

## Четыре редукции

- **5 560 ГБ**: каждый параметр в bfloat16 — откуда стартуем.
- **1 560 ГБ**: чекпоинт как поставляется, потому что эксперты уже приходят по полбайта на вес.
- **113.49 ГБ**: то, что должно быть резидентно, когда маршрутизация означает, что эксперты никогда не грузятся.
- **8.24 ГБ**: то, что измерено, когда ствол вместо удержания — потоковый.

![Четыре редукции, и вывод идентичен на обоих концах](docs/images/eq_fit_ledger.png)

От начала до конца это **675× редукция** от модели bfloat16 и **189×** от поставляемого чекпоинта. Ничего не аппроксимируется и ни один вес не отбрасывается: вывод внизу этой лесенки побайтово совпадает с выводом наверху. График вверху документа — это та же ведомость, нарисованная в масштабе.

## Машина и что она предполагает

Каждое измерение здесь — с одной рабочей станции: двухсокетный AMD EPYC 7763 на 124 ядра без SMT, 228 ГБ RAM и 3.2 ТБ NVMe. На ней также стоят четыре NVIDIA L40, которые простаивали всю кампанию — потому что у этого движка нет GPU-пути.```text
--- ISA (note: AVX2 present, AVX-512 ABSENT) ---
avx avx2 fma sse4_2

--- memory ---
Mem:           228Gi       5.1Gi       207Gi       3.1Mi        18Gi       223Gi
MemTotal:       239308464 kB
MemAvailable:   233961008 kB
Hugepagesize:       2048 kB
```Здесь **нет AVX-512**. Движку нужны AVX2 и FMA — и ничего больше, набор инструкций любого десктопного CPU последнего десятилетия.```text
--- storage bandwidth, measured ---
O_DIRECT cold : 3.2 GB/s     (dd bs=4M iflag=direct after drop_caches)
buffered warm : 2.3 GB/s
engine, trunk : 5373-6064 MB/s sustained during runs
NOTE O_DIRECT is FASTER than buffered here. That is the opposite of the usual
expectation, and it is why the engine opens the trunk O_DIRECT.
```Чтение с `O_DIRECT`, полностью в обход page cache, здесь **быстрее**, чем через него. Одно это измерение определило весь дизайн ввода-вывода — именно поэтому движок открывает ствол с `O_DIRECT`.

![Один бинарь, четыре вида машин — и один идентичный ответ](docs/images/machine-model.png)

Один элемент гигиены — потому что на загруженной машине легко измерить криво:```text
--- measurement hygiene ---
unattended-upgrades: STOPPED and DISABLED before measurement (was using ~63% of a
  core during the smoke run).
apt-daily.timer and apt-daily-upgrade.timer: DISABLED
```Один элемент гигиены — потому что на загруженной машине легко измерить криво. Фоновый апдейтер пакетов, съедающий почти ядро, сдвигает тайминги сильнее, чем большинство оптимизаций, поэтому перед замерами он отключается.```python
# Streamable only if ROUTED. The 2 SHARED experts sit in the same namespace and
# are NOT streamable, which is where hand arithmetic goes wrong.
def classify(name: str) -> str:
    if ".block_sparse_moe.experts." in name:
        return "routed_expert"          # streamable: only 16 of 896 per token
    if ".block_sparse_moe.shared_expert" in name:
        return "shared_expert"          # RESIDENT: runs on every token
    if ".self_attn." in name:
        return "attention"              # resident
    if "embed_tokens" in name or "lm_head" in name:
        return "embedding"              # resident
    return "other"                      # norms, router gates, biases: resident
```Два общих (shared) эксперта работают на каждом токене, поэтому они принадлежат резидентному множеству, хотя их тензоры лежат рядом с маршрутизируемыми экспертами. Ошибиться здесь — значит занизить нижнюю границу, а это худшее направление для ошибки.```
include/k3/
  k3.h              # the public header: config, weights, every kernel prototype
  k3_cfg.h          # config reader, header-only, refuses to substitute defaults
src/
  core/k3_ops.c     # every numeric kernel: RMSNorm, KDA, MLA, MoE, MXFP4 matmul
  io/k3_st.c        # safetensors reader, hand-written JSON scan, O_DIRECT reads
  io/k3_load.c      # locating one expert's bytes inside a shard
  io/k3_trunk.c     # streaming the dense trunk, pinned prefix plus a ring slot
  cache/k3_cache.c  # the routed-expert LRU cache and its batch prefetch
  model/k3_bind.c   # binding checkpoint tensor names to kernel arguments
  tokenizer/k3_tok.h# byte-level BPE loaded from tiktoken.model
  cli/k3_run.c      # the k3 binary: memory plan, decode loop, reporting
tools/              # python: pack the trunk, replay the cache, verify against torch
benchmarks/         # the cgroup memory ladder and the split sweep
tests/              # fixtures, the tiny oracle, the 93-layer conformance run
```

```bash
CFLAGS = -O3 -std=gnu99 -Wall -Wextra -Wpointer-arith -Wshadow -Wvla \
         -march=native -fopenmp -ffp-contract=off
LDFLAGS = -lm -fopenmp
```Флаг, который выглядит необычно — `-ffp-contract=off`. По умолчанию компилятор может слить умножение и сложение в один FMA, что меняет округление. Обычно это хорошо. Здесь — проблема, потому что скалярный путь, путь OpenMP и путь AVX2 должны давать **побитово идентичные** результаты, чтобы изменение производительности никогда тихо не стало изменением точности.

![Один файл C плюс маленькие заголовки превращается в крошечный статический бинарь](docs/images/build-flow.png)```text
1. build, warnings are failures
  -> clean build, no diagnostics
  test_ops          97784 bytes
  k3_model          89392 bytes
  k3_run           179736 bytes
```Весь инференс-движок — **179 736 байт**, бинарь 176 килобайт, чья работа — запустить модель на 1,56 терабайта.

![Бинарь 176 КБ, который запускает модель 1,56 ТБ](docs/images/binary_sizes.png)```text
=== cross-platform tokenizer determinism ===
  Linux   gcc 13.3.0  x86_64
  Windows gcc 16.1.0  x86_64
  input   src/k3.h (24,499 bytes) -> 6,862 ids
  result  IDENTICAL id streams

  (a naive md5 of stdout DIFFERS by one byte: Windows text-mode stdout writes the
   trailing newline as CRLF. That is the pipe, not the tokenizer.)
```Два компилятора на двух операционных системах дают одинаковые 6 862 id токенов из тех же 24 499 байт. Суммы md5 различаются ровно на один байт, и причина — перевод строки, добавленный шеллом, а не что-то, что сделал токенизатор.

## Три инварианта

Публичный заголовок открывается тремя инвариантами, которые обязаны выполняться. Каждый — место, где правдоподобная с виду реализация даёт модель, которая запускается, выдаёт беглый текст и неверна, без падения и без NaN, которые бы предупредили.

1. **`A_log` индексируется по головам, а не по каналам.** Чекпоинт поставляет `head_dim` чисел float, но осмысленны лишь первые `num_heads`; остальное — паддинг.
2. **MLA использует NoPE, но 64 rope-измерения всё равно существуют и всё равно кэшируются.** Отсутствует лишь вращение; удаление слотов меняет ширину головы.
3. **Биас маршрутизации MoE управляет только выбором.** Веса комбинирования берутся из несмещённых сигмоидных оценок.

Каждый отмечается ниже по мере появления соответствующего компонента, и каждый закрыт фикстурой, выбранной так, чтобы ошибка меняла вывод: `A_log` — linspace-ом, который при поканальной ошибке индекса перемешивается, NoPE — проверкой, что масштаб softmax берётся по полной ширине головы, а биас роутинга — фикстурой, где биас меняет порядок top-k в пяти из шести строк.

Раньше в этом списке было пять пунктов. Два других — что обратная UT-трансформация есть `(I + Akk)^-1` и что `Aqk` сохраняет диагональ, а `Akk` — нет, — описывают чанкованную параллельную форму дельта-правила. Этот движок её не использует. `k3_kda_step` выполняет наивную последовательную рекуррентность по одной позиции, и PyTorch-референс, с которым он сверяется, тоже, так что ни одна из матриц никогда не формируется. Это были утверждения об алгоритме, а не об этом коде, ничто их не реализовывало и никакой тест не мог бы поймать ошибку в них. Теперь они живут в [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) вместе с остальным описанием алгоритма. Восстановление чанкованного пути KDA означает восстановление и их, вместе с закрывающими их фикстурами.

## 1. Чтение чекпоинта 1,56 ТБ по его заголовкам

Чекпоинт — это 96 файлов safetensors. Формат намеренно прост — именно это позволяет обращаться с 1,56 терабайта как с индексом, а не как с данными.

![safetensors: одна длина, один заголовок, затем сырые байты по известным смещениям](docs/images/eq_st_layout.png)

Каждый файл начинается с 8-байтной little-endian длины, затем столько же байт JSON, описывающего каждый тензор, затем сырые байты тензоров подряд. Ничего не сжато и ничего не перемешано.

![Проиндексируй шард, прочитай точные байты по требованию, затем сбрось страницы](docs/images/st-load.png)

Никакая JSON-библиотека не используется. Заголовок может быть десятки мегабайт, а нужны лишь четыре поля на тензор — так что ридер сканирует его напрямую.```c
/* Walk the header once, copy nothing we do not need. `p` sits just past the
 * opening quote of the tensor name. */
static const char *st_scan_entry(const char *p, const char *end, K3Tensor *t)
{
    const char *q = memchr(p, '"', (size_t)(end - p));
    if (!q || (size_t)(q - p) >= sizeof t->name) return NULL;
    memcpy(t->name, p, (size_t)(q - p));
    t->name[q - p] = '\0';

    const char *d = st_find_key(q, end, "dtype");
    if (!d) return NULL;
    t->dtype = st_dtype_code(d);

    const char *s = st_find_key(q, end, "shape");
    if (!s) return NULL;
    t->rank = 0;
    t->nelem = 1;
    for (const char *c = s; c < end && *c != ']'; c++) {
        if (*c >= '0' && *c <= '9') {
            long v = strtol(c, (char **)&c, 10);
            if (t->rank >= K3_ST_MAXRANK) return NULL;
            t->shape[t->rank++] = v;
            t->nelem *= (size_t)v;
        }
    }

    /* offsets are RELATIVE to the start of the data section */
    const char *o = st_find_key(q, end, "data_offsets");
    if (!o) return NULL;
    t->off  = (size_t)strtoull(o, (char **)&o, 10);
    while (o < end && (*o < '0' || *o > '9')) o++;
    t->nbytes = (size_t)strtoull(o, (char **)&o, 10) - t->off;
    return o;
}
```Каждый тензор попадает в хеш-таблицу по хешу своего имени. Выбор хеша не произволен.```c
/* Names are long and share deep prefixes
 * ("language_model.model.layers.N.block_sparse_moe.experts.M...."), so the hash must
 * mix every byte; a prefix-only or length-only hash would pile every expert of a
 * layer into one bucket. */
static uint64_t fnv1a(const char *s)
{
    uint64_t h = 1469598103934665603ull;
    while (*s) { h ^= (unsigned char)*s++; h *= 1099511628211ull; }
    return h;
}
```Полмиллиона имён тензоров, начинающихся с одних и тех же сорока символов — по-настоящему недружелюбный вход для хеш-функции. FNV-1a перемешивает каждый байт, так что индекс эксперта в конце имени всё ещё сдвигает результат.```c
int64_t k3_st_read_aligned(const K3St *s, int shard, int64_t off, int64_t nbytes,
                           void *buf, int64_t bufcap, int64_t *payload_off)
{
    /* widen outward to the enclosing aligned window */
    const int64_t lo  = off & ~(int64_t)(K3_ST_ALIGN - 1);
    const int64_t hi  = (off + nbytes + K3_ST_ALIGN - 1) & ~(int64_t)(K3_ST_ALIGN - 1);
    const int64_t len = hi - lo;
    const int64_t pad = off - lo;
    if (len > bufcap) return 0;
    if (payload_off) *payload_off = pad;

    int64_t got = 0;
    while (got < len) {
        ssize_t r = pread(dfd, (char *)buf + got, (size_t)(len - got), (off_t)(lo + got));
        if (r <= 0) break;      /* the last window may run past EOF */
        got += r;
    }
    return got >= pad + nbytes ? nbytes : (got > pad ? got - pad : 0);
}
```Обратите внимание на `break` вместо падения при коротком чтении: последнее выровненное окно шарда выходит за конец файла — это ожидаемо, поэтому возвращаемое значение проверяет, что полезная нагрузка покрыта, а не что всё окно прочитано.```text
indexed 497220 tensors from 96 shards in 0.27 s
```**Полмиллиона тензоров проиндексировано примерно за четверть секунды.** Именно это делает возможным всё последующее: движок никогда не читает шард, который ему не нужен, так что 1,56 терабайта на диске — это каталог, а не рабочий набор.```python
# Bit patterns, not tolerances: widening bf16 to f32 is lossless.
c_bits = np.asarray(c_values[name], dtype=np.float32).view(np.uint32)
p_bits = ref.astype(np.float32).view(np.uint32)
if not np.array_equal(c_bits, p_bits):
    bad = int(np.count_nonzero(c_bits != p_bits))
    fail(f"{name}: {bad} of {c_bits.size} float32 bit patterns differ")
```

```text
=== shard verification ===
shards: 96
bytes:  1560936091448
expected: 1560936091448
RESULT: EXACT MATCH
```![96 шардов, 1 560 936 091 448 байт, проверенных по одному файлу за раз](docs/images/shard_sizes.png)

## 2. Ридер конфига, который отказывается гадать

Размеры модели берутся из собственного `config.json` чекпоинта, и это первое место, где **инвариант четыре** может тихо укусить.

![Индексы слоёв с единицы, и 92 и 93 оба — MLA по дизайну](docs/images/eq_layer_map.png)

Kimi K3 чередует два механизма внимания. Большинство слоёв используют один, каждый четвёртый — другой, и последние два — оба второго вида, так что финальный слой всегда делает глобальное внимание. Конфиг перечисляет эти слои явно, и список — **с единицы** (one-based).```text
--- every value below is READ from the checkpoint, not assumed ---
config: config.json (nested shape) | hidden=7168 layers=93 vocab=163840
        | 24 MLA + 69 KDA | experts 896 top16 shared2 | latent=3584

--- KDA/MLA layer map (ONE-based, from full_attn_layers) ---
full_attn_layers (24, all MLA): 4,8,12,16,20,24,28,32,36,40,44,48,52,56,60,64,68,72,76,80,84,88,92,93
  note 92 AND 93 are both MLA - the report (2.1) places an extra Gated MLA layer
  at the end of the backbone so the final layer always does global attention.
kda_layers (69): every other layer.
```Каждое из этих чисел прочитано из файла; ни одно не зашито в бинарь. Они ложатся```c
typedef struct {
    int hidden;            /* 7168  */
    int n_layers;          /* 93    */
    int vocab;             /* 163840 */
    float rms_eps;         /* 1e-5  */

    /* Kimi Delta Attention. 69 of the 93 layers. */
    int kda_heads;         /* 96    */
    int kda_head_dim;      /* 128, and d_k == d_v */
    int conv_k;            /* 4, depthwise, causal, SiLU fused */
    float gate_lb;         /* -5.0, the decay lower bound */

    /* Gated MLA. 24 of the 93 layers. */
    int n_heads;           /* 96    */
    int q_lora;            /* 1536  */
    int kv_lora;           /* 512   */
    int qk_nope;           /* 128   */
    int qk_rope;           /* 64, PRESENT BUT NEVER ROTATED */
    int v_head;            /* 128   */
    int mla_out_gate;      /* 1     */

    /* Stable LatentMoE. 92 of the 93 layers. */
    int n_experts;         /* 896   */
    int topk;              /* 16    */
    int n_shared;          /* 2, full width, added UNWEIGHTED */
    int latent;            /* 3584, the routed-expert width */
    int moe_inter;         /* 3072  */
    float routed_scale;    /* 1.0   */
    int moe_renorm;        /* 1     */
    int latent_norm;       /* 1, RMSNorm on the AGGREGATE, not per expert */

    /* the single dense layer, layer 0 */
    int first_dense;       /* 1     */
    int dense_inter;       /* 33792 */

    int attn_res_block;    /* 12. Boundaries fire when layer_idx % this == 0. */
    float situ_b1;         /* 4.0   */
    float situ_b2;         /* 25.0  */

    int  n_full_attn;      /* 24 */
    int *full_attn;        /* ONE-BASED layer indices */
} K3Cfg;
```Эта структура — контракт между чекпоинтом и каждым ядром. Если она верна, модель — это Kimi K3. Если хоть одно поле неверно, модель — это что-то иное, что всё ещё говорит по-английски.

![Отказ вместо догадок — потому что угаданное поле даёт другую модель](docs/images/config-guard.png)

Рассмотрим, что сделал бы снисходительный ридер. Релизный конфиг вкладывает поля на один уровень глубже, чем фикстура, так что ридер, знающий только плоскую форму, не находит ничего знакомого. Если он затем подставит значения по умолчанию, произойдут две вещи: беты SiTU получат 4.0 и 25.0, которые являются **правильными** значениями для релизной модели, но ридер не знает, что угадал — он просто повезло. Вторая вещь хуже: любое поле, которое действительно отсутствует, тихо получит ноль.```c
/* An absent field is an ERROR, never a default. Missing names are accumulated so
 * the message lists all of them at once. */
static int cfg_req_int(jval root, const char *key, int *out,
                       const char **missing, int *nmissing)
{
    jval v = json_get(root, key);
    if (v.type != JSON_NUM) {                 /* absent OR the wrong type */
        if (*nmissing < K3_CFG_MAXMISS) missing[(*nmissing)++] = key;
        return 0;
    }
    *out = (int)v.num;
    return 1;
}
```

```text
  [no_layermap]
    k3_cfg: no_layermap.json is missing 1 required field(s):
        full_attn_layers
      refusing to substitute defaults: a config this reader cannot
      fully understand would silently produce a DIFFERENT model.
      ok    correctly rejected no_layermap.json

  [bad_layer_index]
    k3_cfg: bad_layer_index.json full_attn_layers[2] = 999 is outside 1..93
        (the list is ONE-based)
      ok    correctly rejected bad_layer_index.json
```Ридер конфига — это около полутора сотен строк самого скучного кода в проекте, и это одно из ровно двух мест, где вам могут подсунуть другую модель, не предупредив.

## 3. Токенизатор, побайтово

Второе — токенизатор. Kimi K3 использует байтовый BPE на 163 584 ранга плюс 256 специальных токенов, поставляемый как файл `tiktoken.model`.

![Каждый кейс проходит через файл, а не через argv](docs/images/tok-flow.png)

Загрузчик читает этот файл напрямую в вендоризованные структуры BPE. Он опирается на три допущения, каждое из которых даёт токенизатор, прекрасно работающий, но не тот, что в чекпоинте:```text
oracle   : tiktoken 0.13.0
method   : token-for-token comparison; every case passed through a FILE, never argv
           (argv is re-encoded to the active code page on Windows and would compare
            different bytes on every non-ASCII case)

  PASS  han only                 2 ids
  PASS  japanese                 6 ids
  PASS  korean                   5 ids
  PASS  cyrillic                 4 ids
  PASS  arabic                   7 ids
  PASS  emoji zwj                5 ids
  PASS  code python             11 ids
  PASS  json                    19 ids

tokenizer parity: 45/45 cases match
```Затем целые файлы прогоняются насквозь и декодируются обратно:```text
roundtrip: 48353 bytes -> 14797 ids -> 48353 bytes : PASS   <- k3_ops.c
roundtrip: 24499 bytes -> 6862 ids -> 24499 bytes : PASS   <- k3.h
roundtrip: 201775 bytes -> 52671 ids -> 201775 bytes : PASS   <- REPORT.md
roundtrip: 53444 bytes -> 12145 ids -> 53444 bytes : PASS   <- modeling_kimi_k3.py
```![Четыре файла на входе, побайтово идентичные файлы на выходе](docs/images/roundtrip_sizes.png)

Двести килобайт маркдауна превращаются в 52 671 id токенов и возвращаются в точности теми же двумястами килобайтами. Каждое последующее утверждение об идентичном выводе опирается на детерминированность токенизатора.```c
/* Greedily merge the lowest-rank adjacent pair. Everything here is BYTES. */
static int tok_encode_piece(const Tok *t, const unsigned char *p, int n, int *out)
{
    int parts[K3_TOK_MAXPIECE + 1], np = n + 1;
    for (int i = 0; i <= n; i++) parts[i] = i;          /* byte boundaries */

    for (;;) {
        int best = -1, bestrank = INT_MAX;
        for (int i = 0; i + 2 < np; i++) {
            const int r = tok_rank(t, p + parts[i], parts[i + 2] - parts[i]);
            if (r >= 0 && r < bestrank) { bestrank = r; best = i; }
        }
        if (best < 0) break;                            /* no mergeable pair left */
        memmove(&parts[best + 1], &parts[best + 2],
                (size_t)(np - best - 2) * sizeof(int));
        np--;
    }

    for (int i = 0; i + 1 < np; i++)
        out[i] = tok_rank(t, p + parts[i], parts[i + 1] - parts[i]);
    return np - 1;
}
```Цикл хранит список границ слайсов и многократно склеивает ту соседнюю пару, у которой наименьший ранг — именно это делает результат независимым от порядка разрешения ничьих.

## 4. Первая редукция: эксперты уже поставляются по полбайта

Первая из четырёх редукций — и самая крупная в отдельности.

Маршрутизируемые эксперты поставляются не в bfloat16. Они поставляются в **MXFP4** — микроскейлинговом 4-битном формате float. Каждый вес — это 4-битный ниббл, индексирующий таблицу из 16 значений, и каждая группа из 32 последовательных весов делит один 8-битный экспонент.

![MXFP4: 4-битный ниббл, масштабируемый одним 8-битным экспонентом на 32 веса](docs/images/eq_mxfp4.png)

![Один байт несёт два веса, и младший ниббл — чётный](docs/images/mxfp4-decode.png)

![Полбайта на вес плюс общий масштаб дают одному эксперту ровно 17 547 264 байта](docs/images/eq_bytes_per_weight.png)```json
{
  "note": "Kimi K3 MXFP4 bytes from the released checkpoint. w = E2M1[nibble] * 2^(scale - 127), one scale per 32 elements.",
  "source": "language_model.model.layers.1.block_sparse_moe.experts.0.w1",
  "rows": 64, "packed_cols": 1792, "scale_cols": 112,
  "logical_width": 3584, "group_size": 32,
  "e2m1_lut": [0.0, 0.5, 1.0, 1.5, 2.0, 3.0, 4.0, 6.0,
              -0.0, -0.5, -1.0, -1.5, -2.0, -3.0, -4.0, -6.0]
}
```Обе половины декодирования — таблицы поиска (lookup tables), и их построение — единственная настройка, которая нужна формату.```c
/* E2M1: sign, two exponent bits, one mantissa bit. Sixteen values in total. */
static const float K3_E2M1[16] = {
    0.0f,  0.5f,  1.0f,  1.5f,  2.0f,  3.0f,  4.0f,  6.0f,
   -0.0f, -0.5f, -1.0f, -1.5f, -2.0f, -3.0f, -4.0f, -6.0f
};

/* Byte -> its two weights, so the inner loop does one lookup, not two shifts. */
static void k3_pair_init(void)
{
    for (int b = 0; b < 256; b++) {
        K3_E2M1_PAIR[b][0] = K3_E2M1[b & 0x0F];   /* low nibble  = EVEN element */
        K3_E2M1_PAIR[b][1] = K3_E2M1[b >> 4];     /* high nibble = ODD  element */
    }
}

/* Scale byte -> power of two. 255 is NaN by spec, mapped to 0 to contain damage. */
static void k3_e8m0_init(void)
{
    for (int b = 0; b < 256; b++)
        K3_E8M0[b] = (b == 255) ? 0.0f : ldexpf(1.0f, b - 127);
}
```Теперь порядок нибблов — конвенция, которую никакая статистика не проверит.

![Младший ниббл — ЧЁТНЫЙ элемент, и перестановка даёт тихую ошибку](docs/images/eq_nibble_pack.png)```text
"expected_swapped_nibbles": {
  "note": "what you get if the low nibble is treated as the ODD element.
           Statistics are identical; positions are wrong."
}
```Каждое среднее, каждое стандартное отклонение, каждая гистограмма переставленной версии идентична правильной — потому что это то же мультимножество чисел. Различаются только позиции. Проверка, которая смотрит на распределения, пропустила бы матрицу с транспонированной каждой соседней парой весов.

Очевидный способ использовать эти веса — декодировать их во float и затем делать обычное матричное умножение. Цена такого подхода:

![Что стоила бы деквантизация — поэтому мы умножаем прямо из нибблов](docs/images/eq_dequant_cost.png)

Один эксперт 17.55 МБ становится 132 МБ после раскрытия во float32. Каждый токен трогает 16 экспертов на слой на 92 слоях — это означало бы выписать **194 гигабайта на токен** чистого преобразования формата до единого multiply-accumulate.

![Полбайта на вес экономит 4 ТБ, а отсутствие деквантизации экономит 194 ГБ на токен](docs/images/mxfp4_savings.png)

Так что ничто никогда не деквантизуется. Матричное умножение читает упакованные нибблы и масштабы напрямую.```c
/* y[rows] = x[in] . W[rows][in], W stored as MXFP4. Nothing is dequantized. */
void k3_matmul_mxfp4(float *y, const float *x, const unsigned char *packed,
                     const unsigned char *scales, int in, int rows, int group)
{
    const int ngroup = (in + group - 1) / group;
    const int rowbytes = (in + 1) / 2;              /* two nibbles per byte */

#pragma omp parallel for schedule(static)
    for (int o = 0; o < rows; o++) {
        const unsigned char *pb = packed + (size_t)o * rowbytes;
        const unsigned char *sb = scales + (size_t)o * ngroup;
        double acc = 0.0;                            /* double, always */

        for (int g = 0; g < ngroup; g++) {
            const float s = K3_E8M0[sb[g]];
            if (s == 0.0f) continue;                 /* a NaN scale zeroes the group */

            const int i0 = g * group;
            const int n = (i0 + group <= in) ? group : (in - i0);
            float wf[64];

            /* low nibble is the EVEN weight, high nibble the ODD one */
            const int half = n / 2;
            for (int k = 0; k < half; k++) {
                const unsigned char b = pb[(i0 / 2) + k];
                wf[2 * k]     = K3_E2M1_PAIR[b][0];  /* low  nibble -> even index */
                wf[2 * k + 1] = K3_E2M1_PAIR[b][1];  /* high nibble -> odd index  */
            }
            if (n & 1) wf[n - 1] = K3_E2M1_PAIR[pb[(i0 / 2) + half]][0];

            double part = 0.0;
            for (int k = 0; k < n; k++) part += (double)x[i0 + k] * (double)wf[k];
            acc += part * (double)s;
        }
        y[o] = (float)acc;
    }
}
```Две детали стоят паузы. `if (s == 0.0f) continue` обрабатывает байт масштаба 255, который спецификация MXFP4 отводит под NaN/Inf — редкое, но легальное значение, означающее «пропусти эту группу». А `0.53125` байт на параметр — это ровно полбайта на вес плюс один байт масштаба на 32 веса.```text
  PASS  mxfp4          64 rows x 3584 elems, EXACT on released checkpoint bytes
```Не «в пределах допуска», а **точно**. Обе стороны читают идентичные байты с идентичных весов, так что сравнивать нечего — биты совпадают. Точность здесь — не про «близко», а про «те же байты».

## 5. Ядра с контрактом на floating point

Каждый путь кода должен давать одинаковые биты. RMSNorm — самое используемое ядро в модели.

![RMSNorm с эпсилон внутри квадратного корня, аккумулируется в double](docs/images/eq_rmsnorm.png)```c
void k3_rmsnorm(float *out, const float *x, const float *w, int n, float eps)
{
    double ss = 0.0;                                   /* double, not float */
    for (int i = 0; i < n; i++) ss += (double)x[i] * (double)x[i];
    const float inv = (float)(1.0 / sqrt(ss / (double)n + (double)eps));
    for (int i = 0; i < n; i++) out[i] = x[i] * inv * (w ? w[i] : 1.0f);
}
```Две детали критичны: аккумулятор — **double**, хотя каждый вход и выход — `float`, и эпсилон идёт **внутрь** квадратного корня, а не наружу.

![Фиксированный порядок редукции, так что скаляр и AVX2 совпадают побитово](docs/images/eq_accum_order.png)```c
/* Four accumulators partitioned by i % 4. This pins the summation order, so a
 * 4-wide vector loop adds the same numbers in the same sequence. */
static float k3_dot4(const float *x, const float *w, int n)
{
    double a0 = 0.0, a1 = 0.0, a2 = 0.0, a3 = 0.0;
    int i = 0;
    for (; i + 3 < n; i += 4) {
        a0 += (double)x[i]     * (double)w[i];
        a1 += (double)x[i + 1] * (double)w[i + 1];
        a2 += (double)x[i + 2] * (double)w[i + 2];
        a3 += (double)x[i + 3] * (double)w[i + 3];
    }
    for (; i < n; i++) a0 += (double)x[i] * (double)w[i];
    return (float)((a0 + a1) + (a2 + a3));       /* the parentheses are the contract */
}
```![bf16 в fp32 — это сдвиг, а не конверсия, так что расширение без потерь](docs/images/eq_bf16_widen.png)

Значение bfloat16 расширяется во float32 сдвигом мантиссы, без округления и без потери. Обратное — не так.```c
void k3_matmul_bf16(float *y, const float *x, const uint16_t *W, int in, int out)
{
#pragma omp parallel for schedule(static) if (out > 64)
    for (int o = 0; o < out; o++) {
        const uint16_t *row = W + (size_t)o * in;
        int i = 0;
        double acc;
#if defined(__AVX2__)
        {
            __m256d v = _mm256_setzero_pd();
            for (; i + 3 < in; i += 4) {
                /* bf16 -> f32 is a 16-bit shift: no table, no rounding */
                const __m128i h   = _mm_loadl_epi64((const __m128i *)(row + i));
                const __m128i b32 = _mm_slli_epi32(_mm_cvtepu16_epi32(h), 16);
                const __m256d wd  = _mm256_cvtps_pd(_mm_castsi128_ps(b32));
                const __m256d xd  = _mm256_cvtps_pd(_mm_loadu_ps(x + i));
                v = _mm256_add_pd(v, _mm256_mul_pd(wd, xd));   /* NOT fmadd */
            }
            double a[4];
            _mm256_storeu_pd(a, v);
            acc = (a[0] + a[1]) + (a[2] + a[3]);
        }
#else
        {
            double a0 = 0.0, a1 = 0.0, a2 = 0.0, a3 = 0.0;
            for (; i + 3 < in; i += 4) {
                a0 += (double)k3_bf16f(row[i    ]) * (double)x[i    ];
                a1 += (double)k3_bf16f(row[i + 1]) * (double)x[i + 1];
                a2 += (double)k3_bf16f(row[i + 2]) * (double)x[i + 2];
                a3 += (double)k3_bf16f(row[i + 3]) * (double)x[i + 3];
            }
            acc = (a0 + a1) + (a2 + a3);
        }
#endif
        for (; i < in; i++) acc += (double)k3_bf16f(row[i]) * (double)x[i];
        y[o] = (float)acc;
    }
}
```Обе ветки аккумулируют в четыре double, обе разбивают по `i % 4` и обе сворачивают как `(a0 + a1) + (a2 + a3)`. Порядок суммирования идентичен — поэтому биты совпадают, независимо от того, идёт ли путь через скаляр, OpenMP или AVX2.

![Одинаковые веса, три пути кода — один хеш](docs/images/kernel-contract.png)

Доказать, что пути AVX2 и скаляр совпадают, нельзя допуском.```text
tolerance: atol=1.0e-05 rtol=1.0e-04  (from MANIFEST.json)
  PASS  rmsnorm        n=384    worst=0.01x tol
  PASS  situ_glu       n=48     worst=0.00x tol
        bound check |out|=100.000 must be <= b1*b2=100.0 : ok
  PASS  kda_decay      H=4 D=16 tok=4  max|dg|=4.768e-07 max|dalpha|=1.788e-07
  PASS  mla            n=768    worst=0.08x tol
        H=4 qh=32 (nope 24 + rope 8) v=16 kv_lora=32 scale=0.176777
  PASS  mxfp4          64 rows x 3584 elems, EXACT on released checkpoint bytes
  PASS  matmul_bf16   n=129    bit-identical to k3_matmul
22 passed, 0 failed, 0 skipped
```Худший случай среди всех 22 ядер — 8 процентов от допустимого допуска, а два ядра — точные, а не просто близкие.

![Куда уходит время одного токена на конфигурации «пол» (floor): 80% — ожидание диска](docs/images/token_time_split.png)

Замерено на собственных размерах модели на наименьшей конфигурации: примерно 36 секунд чтения ствола, 11 секунд чтения экспертов и 10 секунд арифметики. **Восемьдесят процентов токена — ожидание диска**, поэтому вторая половина этого документа — про ввод-вывод, а не про ядра.

## 6. Вторая редукция: KDA — внимание с памятью, которая никогда не растёт

Шестьдесят девять из 93 слоёв используют Kimi Delta Attention, и важное здесь свойство формулируется просто: его память не растёт с длиной контекста.

Стандартный слой внимания хранит ключ и значение на каждый виденный токен, так что его кэш линейно растёт вечно. KDA вместо этого держит одну фиксированную матрицу на голову и обновляет её на месте по мере поступления токенов.

![Рекуррентное состояние одинаково при 10 токенах и при 100 000](docs/images/eq_kda_state.png)

Девяносто шесть голов × матрица 128×128 на голову — это вся память слоя KDA при любой длине последовательности. На все 93 слоя это **626.25 мегабайта**, скармливаете ли вы десять токенов или миллион.

![Каждый токен сворачивается в одно и то же фиксированное состояние](docs/images/kda-state.png)

![Почему 69 слоёв — это KDA: его состояние не растёт с контекстом](docs/images/context_scaling.png)

Этот график — аргумент за весь дизайн. Плоская линия — KDA. Растущая — то, сколько стоят остальные 24 слоя, и она пересекает память этой машины где-то около 100 000 токенов. Если бы все 93 слоя вели себя так, модель не поместилась бы ни при какой осмысленной длине контекста.

![Затухание состояния, чтение из него, запись дельты, затем чтение обновлённого состояния](docs/images/kda-flow.png)

Сначала проекции проходят через короткую depthwise causal свёртку шириной четыре с вплавленной SiLU.

![Depthwise causal свёртка шириной 4 с вплавленной активацией](docs/images/eq_shortconv.png)```c
/* Causal depthwise conv with SiLU fused. State is carried across calls. */
void k3_shortconv(float *y, const float *x, const float *w, float *state,
                  int channels, int k, int T)
{
    const int hist = k - 1;                  /* guard on hist, not on buf */
    float *buf = hist ? (float *)malloc((size_t)hist * sizeof(float)) : NULL;
    if (hist && !buf) k3_fatal_oom("ShortConv history", (size_t)hist * sizeof(float));

    for (int c = 0; c < channels; c++) {
        if (hist) {
            if (state) memcpy(buf, state + (size_t)c * hist, (size_t)hist * sizeof(float));
            else       memset(buf, 0, (size_t)hist * sizeof(float));
        }

        for (int t = 0; t < T; t++) {
            const float cur = x[(size_t)t * channels + c];
            float acc = w[(size_t)c * k + hist] * cur;   /* taps run oldest to newest */
            for (int j = 0; j < hist; j++)
                acc += w[(size_t)c * k + j] * buf[j];

            for (int j = 0; j + 1 < hist; j++) buf[j] = buf[j + 1];
            if (hist > 0) buf[hist - 1] = cur;

            y[(size_t)t * channels + c] = acc * sigmoidf_(acc);   /* SiLU, fused */
        }
        if (state && hist) memcpy(state + (size_t)c * hist, buf, (size_t)hist * sizeof(float));
    }
    free(buf);
}
```Обратите внимание на проверку `hist`, а не `buf`: при ширине ядра равной единице истории нет вовсе, `malloc(0)` вправе вернуть NULL, и проверка указателя тихо пропустила бы всю свёртку, оставив выход нетронутым.

Затем запросы (queries) и ключи (keys) L2-нормируются — сумма квадратов, а не среднее квадратов, что выглядит почти идентично в коде, но является другой функцией.

![Сумма квадратов, а не среднее, и применяется только к q и k](docs/images/eq_l2norm.png)

Затем — гейт затухания (decay gate), это **инвариант один**.

![Гейт затухания, где A индексируется по головам, а не по каналам](docs/images/eq_kda_decay.png)```c
void k3_kda_decay(float *g, float *alpha, const float *z, const float *A_log,
                  const float *dt_bias, int H, int D, float lb)
{
    for (int h = 0; h < H; h++) {
        const float a = expf(A_log[h]);      /* PER HEAD, not per channel */
        for (int d = 0; d < D; d++) {
            const int i = h * D + d;
            const float u  = a * (z[i] + dt_bias[i]);
            const float gi = lb * sigmoidf_(u);   /* in (lb, 0] */
            g[i] = gi;
            alpha[i] = expf(gi);                  /* in (e^lb, 1] */
        }
    }
}
```Нижняя граница гейта — −5, так что `alpha` попадает между `e^-5` и 1. Близко к единице — этот канал ключа сохраняет почти всю историю; близко к `e^-5` — забывает почти всё, поканально и по-токенно.

![Дельта-правило: затухание, чтение, запись разницы, затем снова чтение](docs/images/eq_kda_recurrence.png)```c
void k3_kda_step(float *S, float *o, const float *q, const float *k,
                 const float *v, const float *alpha, float beta, int dk, int dv)
{
    /* 1. decay: scale ROW i of S by alpha[i], per key channel */
    for (int i = 0; i < dk; i++) {
        float *row = S + (size_t)i * dv;
        const float a = alpha[i];
        for (int j = 0; j < dv; j++) row[j] *= a;
    }

    /* 2. read the state along k: u = S^T k */
    float *u = (float *)calloc((size_t)dv, sizeof(float));
    if (!u) k3_fatal_oom("KDA recurrence temporary", (size_t)dv * sizeof(float));
    for (int i = 0; i < dk; i++) {
        const float ki = k[i];
        if (ki == 0.0f) continue;
        const float *row = S + (size_t)i * dv;
        for (int j = 0; j < dv; j++) u[j] += ki * row[j];
    }

    /* 3. rank-one delta write: (v - u) is the prediction error */
    for (int i = 0; i < dk; i++) {
        const float ki = k[i];
        if (ki == 0.0f) continue;
        float *row = S + (size_t)i * dv;
        for (int j = 0; j < dv; j++) row[j] += ki * beta * (v[j] - u[j]);
    }

    /* 4. output from the ALREADY UPDATED state: o = S^T q */
    for (int j = 0; j < dv; j++) o[j] = 0.0f;
    for (int i = 0; i < dk; i++) {
        const float qi = q[i];
        if (qi == 0.0f) continue;
        const float *row = S + (size_t)i * dv;
        for (int j = 0; j < dv; j++) o[j] += qi * row[j];
    }
    free(u);
}
```Этот `calloc` происходит **после** того, как шаг один уже отмасштабировал состояние, так что ранний возврат при ошибке выделения оставил бы рекуррентную матрицу необратимо затухшей, но никогда не обновлённой. Каждый последующий токен считался бы из состояния, которое тихо неверно, без каких-либо признаков. Именно поэтому путь ошибки делает abort, а не return.

![Девять упорядоченных шагов, и нумерация — не украшение](docs/images/kda-nine-steps.png)```c
void k3_kda_layer(float *out, const float *x, const K3KdaW *w, const K3Cfg *c,
                  int T, float *state, float *scratch)
{
    const int E = c->hidden, H = c->kda_heads, D = c->kda_head_dim;
    const int P = H * D, K = c->conv_k, hist = K - 1;

    float *q  = scratch;                 float *k  = q + (size_t)T * P;
    float *v  = k + (size_t)T * P;       float *z  = v + (size_t)T * P;
    float *al = z + (size_t)T * P;       float *bt = al + (size_t)T * P;
    float *o  = bt + (size_t)T * H;      float *gb = o + (size_t)T * P;
    float *wr = gb + P;                  float *fa = wr + P;

    /* 1. projections */
    for (int t = 0; t < T; t++) {
        const float *xt = x + (size_t)t * E;
        k3_mmw(q + (size_t)t * P, xt, w->q, w->wdt, E, P);
        k3_mmw(k + (size_t)t * P, xt, w->k, w->wdt, E, P);
        k3_mmw(v + (size_t)t * P, xt, w->v, w->wdt, E, P);
        k3_mmw(bt + (size_t)t * H, xt, w->b, w->wdt, E, H);
        k3_mmw(fa, xt, w->f_a, w->wdt, E, D);        /* one low-rank pair, all heads */
        k3_mmw(z + (size_t)t * P, fa, w->f_b, w->wdt, D, P);
    }

    /* 2. ShortConv with fused SiLU, carrying state across calls */
    float *cs = state ? state + (size_t)H * D * D : NULL;
    k3_shortconv(q, q, w->q_conv, cs ? cs : NULL, P, K, T);
    k3_shortconv(k, k, w->k_conv, cs ? cs + (size_t)P * hist : NULL, P, K, T);
    k3_shortconv(v, v, w->v_conv, cs ? cs + (size_t)2 * P * hist : NULL, P, K, T);

    /* 3. L2Norm on q and k ONLY, per head. v is deliberately left alone. */
    for (int t = 0; t < T; t++)
        for (int h = 0; h < H; h++) {
            l2norm_(q + (size_t)t * P + (size_t)h * D, D, 1e-6f);
            l2norm_(k + (size_t)t * P + (size_t)h * D, D, 1e-6f);
        }

    /* 4/5. beta and the decay chain */
    for (int t = 0; t < T; t++) {
        for (int h = 0; h < H; h++) bt[(size_t)t * H + h] = sigmoidf_(bt[(size_t)t * H + h]);
        k3_kda_decay(z + (size_t)t * P, al + (size_t)t * P, z + (size_t)t * P,
                     w->A_log, w->dt_bias, H, D, c->gate_lb);
    }

    /* 6. recurrence, per head, with q pre-scaled by d_k^-0.5 */
    float *S = state;
    float *Sown = NULL;
    if (!S) {
        Sown = (float *)calloc((size_t)H * D * D, sizeof(float));
        if (!Sown) k3_fatal_oom("KDA recurrent state", (size_t)H * D * D * sizeof(float));
        S = Sown;
    }
    const float qscale = 1.0f / sqrtf((float)D);
    for (int t = 0; t < T; t++)
        for (int h = 0; h < H; h++) {
            const size_t off = (size_t)t * P + (size_t)h * D;
            for (int i = 0; i < D; i++) wr[i] = q[off + i] * qscale;
            k3_kda_step(S + (size_t)h * D * D, o + off, wr, k + off, v + off,
                        al + off, bt[(size_t)t * H + h], D, D);
        }

    /* 7/8/9. head-wise RMSNorm, THEN the gate, THEN the output projection */
    for (int t = 0; t < T; t++) {
        const float *xt = x + (size_t)t * E;
        float *ot = o + (size_t)t * P;
        for (int h = 0; h < H; h++)
            k3_rmsnorm(ot + (size_t)h * D, ot + (size_t)h * D, w->o_norm, D, c->rms_eps);
        k3_mmw(gb, xt, w->g, w->wdt, E, P);
        for (int i = 0; i < P; i++) ot[i] *= sigmoidf_(gb[i]);
        k3_mmw(out + (size_t)t * E, ot, w->o, w->wdt, P, E);
    }
    free(Sown);
}
```Девять пронумерованных шагов, и нумерация — не украшение. Шаг 3 нормирует `q` и `k` и намеренно оставляет `v` в покое. Шаг 6 предварительно масштабирует запрос на единицу, делённую на корень из размерности головы, **до** рекуррентности, а не после.

![Сначала норма, затем гейт, затем проекция — и этот порядок не взаимозаменяем](docs/images/eq_kda_gate.png)

Шаги 7, 8 и 9 несут своё собственное ограничение порядка. Релизная модель заканчивает слой слитым (fused) ядром из библиотеки `fla` под названием `FusedRMSNormGated`, которое принимает сырой гейт и применяет сигмоиду внутри. Референсная реализация вместо этого делает явный RMSNorm с последующим умножением на гейт —```text
one KDA layer  : 443740384 params  (887.48 MB at bf16)
69 KDA layers  : 61.24 GB at bf16   (KDA attention ONLY, not the whole trunk)
full trunk     : 113.49 GB at bf16, 56,743,648,000 always-active params
one expert     : 33030144 params  (17.55 MB at MXFP4)
all 82432 experts: 1.45 TB at MXFP4  <- streamed from NVMe

per-sequence state, FIXED regardless of context:
  KDA recurrent : 217.06 MB at bf16
  ShortConv     : 15.26 MB at bf16
  MLA KV        : 2.37 MB per position (24 MLA layers, EXPANDED k and v, fp32)
                  19.38 GB at 8192 context
                  310.04 GB at 131072 context

allocating and running ONE full-width KDA layer (fp32)...
  weights: 1.77 GB
  ran 4 tokens in 0.17 s (44 ms/token)
  output all finite: YES, max |y| = 0.000003
  state non-zero   : yes
```Две строки под «FIXED независимо от контекста» — это и есть выигрыш. Состояние KDA — 217 МБ, история свёртки — 15 МБ, и ни одно число не сдвигается, как бы ни росла последовательность, против 310 ГБ у другого механизма внимания на 131 072 позициях.

Это и есть вторая редукция: у 69 из 93 слоёв стоимость памяти полностью не зависит от того, сколько текста вы подаёте.

## 7. Третья редукция: MLA — один латент вместо девяноста шести голов

Остальные 24 слоя делают глобальное внимание, потому что чисто рекуррентный стек не может с полной точностью оглянуться на произвольный более ранний токен. Они используют Gated Multi-head Latent Attention — и именно они стоят памяти. Но они кэшируют не то, что вы ожидаете.

Кэш хранит не развёрнутые головы. Он хранит сжатый латент, из которого головы восстанавливаются при использовании.

![Один латент на позицию кэшируется, а k и v пересоздаются при использовании](docs/images/eq_mla_latent.png)

![Запрос и токен оба проходят через маленький общий латент](docs/images/mla-latent.png)

Латент — 512 измерений для контентной части ключа и значения плюс ещё 64 для RoPE. Остальные размерности получаются проекцией на лету, а не хранением.```c
/* NoPE: the 64 rope dimensions are projected and cached, but never rotated. */
static void k3_mla_project(float *q, float *kv, const float *x, const K3MlaW *w,
                           const K3Cfg *c)
{
    float qa[K3_MAX_QLORA];                  /* down to 1536, norm, back up */
    k3_mmw(qa, x, &w->q_a_proj, c->q_lora, c->hidden);
    k3_rmsnorm(qa, qa, w->q_a_norm, c->q_lora, c->rms_eps);
    k3_mmw(q, qa, &w->q_b_proj, c->n_heads * (c->qk_nope + c->qk_rope), c->q_lora);

    /* one 576-wide projection: the entire per-position cache for this layer */
    k3_mmw(kv, x, &w->kv_a_proj, c->kv_lora + c->qk_rope, c->hidden);
    k3_rmsnorm(kv, kv, w->kv_a_norm, c->kv_lora, c->rms_eps);
    /* the trailing qk_rope floats are left unnormalised and unrotated */
}
```Ширина головы — 192 (128 контентных измерений плюс 64 переносимых-но-невращаемых), так что масштаб softmax — обратный корень из 192, а не из 128. Ошибка здесь — это примерно 22 процента в каждой оценке внимания, и при этом получается вполне читаемый вывод.```c
    for (int t = 0; t < T; t++) {
        const int p = cached + t;
        for (int h = 0; h < H; h++) {
            const float *qt = q + ((size_t)t * H + h) * qh;
            float m = -INFINITY;
            for (int s = 0; s <= p; s++) {                 /* causal: s <= p */
                const float *ks = K3_KV_AT(s) + (size_t)h * kvd;
                const float *kr = K3_ROPE_AT(s);           /* shared slot */
                double d = 0.0;
                for (int i = 0; i < qn; i++) d += (double)qt[i] * (double)ks[i];
                /* the rope slot is UNROTATED but still scored, and the SAME 64
                 * values serve every head */
                for (int i = 0; i < qr; i++) d += (double)qt[qn + i] * (double)kr[i];
                sc[s] = (float)d * scale;
                if (sc[s] > m) m = sc[s];
            }
            double z = 0.0;
            for (int s = 0; s <= p; s++) { sc[s] = expf(sc[s] - m); z += sc[s]; }
```Оценка — это два скалярных произведения, сложенных вместе. Первое идёт по 128 контентным измерениям, которые индивидуальны для каждой головы. Второе — по 64 rope-измерениям, которые **общие**: `K3_ROPE_AT(s)` не принимает индекс головы, так что все 96 голов оцениваются против одних и тех же 64 чисел. Именно это делает кэш шириной 576 вместо 96 × 320, и пропуск второго слагаемого — тихий способ получить модель, которая всё ещё говорит.

![Двадцать четыре MLA-слоя, развёрнутые k и v во fp32, на позицию](docs/images/eq_mla_kv.png)

![Что MLA кэширует на позицию, на слой](docs/images/kv_layout.png)

![Релизный код кэширует развёрнутые головы, латент в 53 раза меньше](docs/images/eq_kv_compression.png)```c
/* The context limit is the MLA KV cache, not any array size. */
if (incremental) {
    const double kv_need = (double)(np + gen + 1) * K3_KV_BYTES_PER_POS;
    const double avail   = mem_available_bytes();
    if (avail > 0.0 && kv_need > avail * 0.9) {
        fprintf(stderr,
            "\nREFUSING: the KV cache for %d positions needs %s but only %s is\n"
            "available. This is a MEMORY limit, not an engine ceiling: MLA caches\n"
            "expanded k and v in fp32 across 24 layers, so context costs ~2.37 MB per\n"
            "position regardless of budget. Shorten the request, or use full\n"
            "recompute (drop --incremental), which carries no KV cache at all.\n",
            np + gen + 1, kb, ab);
        return 2;
    }
}
```"Это лимит ПАМЯТИ, а не потолок движка" — экономит кому-то полдня поисков несуществующей захардкоженной константы.

Это и есть третья редукция. Контекст стоит 2.37 МБ на позицию вместо 125.

## 8. Остаточные связи внимания: слои, которые оглядываются назад

Ещё один структурный кусок, достаточно необычный, чтобы заслужить раздел, хотя памяти он не стоит.

В обычном трансформере каждый слой добавляет свой выход к текущему остаточному потоку (residual stream). Kimi K3 делает иначе: каждый слой осуществляет внимание (attends) поверх выходов каждого предшествующего **блока**, где блок — это двенадцать слоёв, и обучается, сколько каждого подмешивать.

![Каждый слой осуществляет внимание поверх выходов каждого предшествующего блока](docs/images/eq_attn_res.png)

![Блоков по двенадцать, так что стек остатков никогда не превышает девять источников](docs/images/eq_block_count.png)

![Каждые двенадцать слоёв текущий префикс снапшотится и очищается](docs/images/attn-res.png)```c
void k3_attn_res(float *out, const float *src, const float *fold,
                 int nsrc, int n, float eps)
{
    float *score = (float *)malloc((size_t)nsrc * sizeof(float));
    if (!score) k3_fatal_oom("AttnRes scores", (size_t)nsrc * sizeof(float));

    for (int s = 0; s < nsrc; s++) {
        const float *v = src + (size_t)s * n;
        double ss = 0.0;
        for (int i = 0; i < n; i++) ss += (double)v[i] * (double)v[i];
        const float inv = (float)(1.0 / sqrt(ss / (double)n + (double)eps));
        double acc = 0.0;                            /* key: the NORMALISED source */
        for (int i = 0; i < n; i++) acc += (double)(v[i] * inv) * (double)fold[i];
        score[s] = (float)acc;
    }

    float m = score[0];
    for (int s = 1; s < nsrc; s++) if (score[s] > m) m = score[s];
    double z = 0.0;
    for (int s = 0; s < nsrc; s++) { score[s] = expf(score[s] - m); z += score[s]; }

    for (int i = 0; i < n; i++) out[i] = 0.0f;
    for (int s = 0; s < nsrc; s++) {
        const float p = (float)(score[s] / z);
        const float *v = src + (size_t)s * n;   /* the RAW source, not the key */
        for (int i = 0; i < n; i++) out[i] += p * v[i];
    }
    free(score);
}
```Ключи нормируются перед оценкой, а значения (values) — это **сырые** источники. Нормировать заодно и values — очевидная на вид ошибка, которая тихо перемасштабирует остаточный поток.

![Один слой: агрегация, внимание, снова агрегация, затем маршрутизация](docs/images/decoder-layer.png)```c
void k3_decoder_layer_inc(float *h, float *block_residual, int *n_blocks,
                          const K3LayerW *w, const K3Cfg *c, int layer_idx,
                          int T, float *state, float *scratch,
                          float *kvc, float *ropec, int cached, int cap)
{
    const int E = c->hidden;
    const int maxb = c->n_layers / c->attn_res_block + 2;

    float *pref   = scratch;                    /* [T][E] the running residual   */
    float *tmp    = pref + (size_t)T * E;       /* [T][E] module output          */
    float *hin    = tmp  + (size_t)T * E;       /* [T][E] normalised layer input */
    float *foldA  = hin  + (size_t)T * E;       /* [E] attention aggregator      */
    float *foldM  = foldA + E;                  /* [E] mlp aggregator            */
    float *src    = foldM + E;                  /* [maxb+1][E] source stack      */
    float *dgu    = src + (size_t)(maxb) * E;   /* [2*dense_inter]               */
    float *sub    = dgu + (size_t)2 * c->dense_inter;   /* scratch for the module */

    /* norm gain and scoring projection collapse into one vector */
    for (int i = 0; i < E; i++) {
        foldA[i] = w->attn_res_norm[i] * w->attn_res_proj[i];
        foldM[i] = w->mlp_res_norm[i]  * w->mlp_res_proj[i];
    }

    memcpy(pref, h, (size_t)T * E * sizeof(float));
    int have_prefix = 1;                        /* mirrors "prefix_sum is not None" */

    /* aggregation before attention, only when snapshots already exist */
    if (*n_blocks > 0) {
        for (int t = 0; t < T; t++) {
            for (int b = 0; b < *n_blocks; b++)
                memcpy(src + (size_t)b * E,
                       block_residual + ((size_t)t * maxb + b) * E,
                       (size_t)E * sizeof(float));
            memcpy(src + (size_t)(*n_blocks) * E, pref + (size_t)t * E,
                   (size_t)E * sizeof(float));
            k3_attn_res(h + (size_t)t * E, src, foldA, *n_blocks + 1, E, c->rms_eps);
        }
    }

    /* block boundary: snapshot the running residual, then CLEAR it */
    if (layer_idx % c->attn_res_block == 0) {
        for (int t = 0; t < T; t++)
            memcpy(block_residual + ((size_t)t * maxb + *n_blocks) * E,
                   pref + (size_t)t * E, (size_t)E * sizeof(float));
        (*n_blocks)++;
        have_prefix = 0;
    }

    /* whichever attention was bound for this layer */
    for (int t = 0; t < T; t++)
        k3_rmsnorm(hin + (size_t)t * E, h + (size_t)t * E, w->in_norm, E, c->rms_eps);
    if (w->kda) k3_kda_layer(tmp, hin, w->kda, c, T, state, sub);
    else        k3_mla_cached(tmp, hin, w->mla, c, T, sub, kvc, ropec, cached, cap);

    if (have_prefix) for (size_t i = 0; i < (size_t)T * E; i++) pref[i] += tmp[i];
    else             { memcpy(pref, tmp, (size_t)T * E * sizeof(float)); have_prefix = 1; }

    /* aggregation before the MLP, with no emptiness guard */
    for (int t = 0; t < T; t++) {
        for (int b = 0; b < *n_blocks; b++)
            memcpy(src + (size_t)b * E,
                   block_residual + ((size_t)t * maxb + b) * E,
                   (size_t)E * sizeof(float));
        memcpy(src + (size_t)(*n_blocks) * E, pref + (size_t)t * E,
               (size_t)E * sizeof(float));
        k3_attn_res(h + (size_t)t * E, src, foldM, *n_blocks + 1, E, c->rms_eps);
    }

    for (int t = 0; t < T; t++)
        k3_rmsnorm(hin + (size_t)t * E, h + (size_t)t * E, w->post_norm, E, c->rms_eps);

    if (w->moe) {
        int   idx[K3_MAX_TOPK]; float wt[K3_MAX_TOPK];
        k3_moe(tmp, hin, w->moe, c, T, idx, wt, sub);
    }
}
```Слой никогда не спрашивает, какого он типа; он проверяет, привязан ли `w->kda`, так что карта слоёв из `config.json` — единственное, что решает. Две агрегации несимметричны: та, что перед вниманием, пропускается, когда снапшотов ещё нет, а та, что перед MLP, такого гарда не имеет — потому что и у референса его нет.

Делает ли это что-то наблюдаемое? Референсный прямой проход показывает. Печать максимального абсолютного значения активации после каждого слоя:```text
  L45  KDA MoE      41.2 s   |h| max 47.714829
  L46  KDA MoE      38.9 s   |h| max 62.183392
  L47  MLA MoE      44.3 s   |h| max 76.281532
  L48  KDA MoE      36.1 s   |h| max 2.902113
  L49  KDA MoE      39.5 s   |h| max 4.353188
```Слой 47 к слою 48: магнитуда активации падает с **76.28 до 2.90** — в 26 раз за один слой. Это граница блока: текущий префикс был снапшотнут и очищен, так что следующий слой стартует со свежего малого остатка.

![Остаточные связи внимания, нарисованные данными: активации растут, затем коллапсируют каждые 12 слоёв](docs/images/activation_spikes.png)

Семь зубьев пилы — по одному на блок, каждый растёт двенадцать слоёв, а затем обваливается. Никто эту форму не рисовал — её нарисовала модель. Самый большой пик — 136.7 на слое 59, падение до 1.78 на слое 60. Когда у измеренной кривой ровно тот период, который обещает код, — это неплохой знак, что код совпадает с моделью.

## 9. Выбор 16 экспертов из 896

Роутер оценивает каждого из 896 экспертов и выбирает шестнадцать. Это **инвариант пять** — самый тонкий из всех.

![Биас управляет только выбором, веса — из несмещённых оценок](docs/images/eq_router.png)```c
/* Score all n_experts, pick the top-k, weight them. The bias steers SELECTION only. */
void k3_router(int *idx, float *w, const float *x, const float *W, const float *bias,
               int hidden, int n_experts, int topk, int renorm, float routed_scale)
{
    float sc[K3_MAX_EXPERTS], ch[K3_MAX_EXPERTS];

#pragma omp parallel for schedule(static)
    for (int e = 0; e < n_experts; e++) {
        double acc = 0.0;
        for (int i = 0; i < hidden; i++)
            acc += (double)x[i] * (double)W[(size_t)e * hidden + i];
        sc[e] = 1.0f / (1.0f + expf(-(float)acc));      /* the UNBIASED score */
        ch[e] = sc[e] + (bias ? bias[e] : 0.0f);        /* the SELECTION score */
    }

    char taken[K3_MAX_EXPERTS] = {0};        /* top-k by repeated max */
    for (int j = 0; j < topk; j++) {
        int best = -1;
        for (int e = 0; e < n_experts; e++)
            if (!taken[e] && (best < 0 || ch[e] > ch[best])) best = e;
        taken[best] = 1;
        idx[j] = best;
        w[j] = sc[best];                                 /* the UNBIASED score again */
    }

    if (renorm) {
        float s = 0.0f;
        for (int j = 0; j < topk; j++) s += w[j];
        if (s > 0.0f) for (int j = 0; j < topk; j++) w[j] /= s;
    }
    for (int j = 0; j < topk; j++) w[j] *= routed_scale;
}
````sc[e]` и `ch[e]` оба вычисляются и используются для разного. Биас управляет **выбором**, а `ch[e]` — **взвешиванием**. Перепутать их — значит получить модель, где роутинг выглядит правильно, но веса комбинации неверны. Правка, меняющая модель, — это одна строка.

![Эксперты работают в узком латенте, а норма — на агрегате](docs/images/eq_moe_latent.png)

![Маршрутизация, прогон 16 экспертов в латенте шириной 3584, затем проекция обратно](docs/images/moe-dispatch.png)```c
/* Stable LatentMoE for one token.
 *
 * Six steps, and step 4 is the one people get wrong: the RMSNorm is applied to the
 * AGGREGATE of the weighted expert outputs, not to each expert individually. Norming
 * per expert and then summing is a different function.
 *
 * The two shared experts run on the ORIGINAL full-width input, not the latent, and
 * their output is added UNWEIGHTED. They are not part of the top-k sum. */
void k3_moe(float *out, const float *x, const K3MoeW *w, const K3Cfg *c,
            int T, int *idx, float *wt, float *scratch)
{
    const int E = c->hidden, L = c->latent, I = c->moe_inter;
    float *z = scratch, *accL = z + L, *gu = accL + L, *act = gu + 2 * I;
    float *edn = act + I;

    for (int t = 0; t < T; t++) {
        const float *xt = x + (size_t)t * E;

        /* 1. route on the FULL width, not the latent */
        k3_router(idx, wt, xt, w->gate, w->gate_bias, E,
                  c->n_experts, c->topk, c->moe_renorm, c->routed_scale);

        /* 2. down-project into the expert latent */
        k3_mmw(z, xt, w->down, w->wdt, E, L);

        /* 3. run the chosen experts, accumulating in the latent */
        for (int i = 0; i < L; i++) accL[i] = 0.0f;
        if (w->src && w->src->getmany) w->src->getmany(w->src, w->layer, idx, c->topk);

        for (int j = 0; j < c->topk; j++) {
            K3ExpertQ q;
            if (w->src->get(w->src, w->layer, idx[j], &q) != 0) {
                k3_expert_drops++;          /* counted, never silent */
                continue;
            }
            k3_matmul_mxfp4(gu,     z, q.p1, q.s1, L, I, K3_MXFP4_GROUP);
            k3_matmul_mxfp4(gu + I, z, q.p3, q.s3, L, I, K3_MXFP4_GROUP);
            k3_situ_glu(act, gu, I, c->situ_b1, c->situ_b2);
            k3_matmul_mxfp4(edn, act, q.p2, q.s2, I, L, K3_MXFP4_GROUP);
            for (int i = 0; i < L; i++) accL[i] += wt[j] * edn[i];
        }

        /* 4. norm the AGGREGATE, not each expert */
        if (c->latent_norm) k3_rmsnorm(accL, accL, w->latent_norm, L, c->rms_eps);

        /* 5. back up to full width */
        float *ot = out + (size_t)t * E;
        k3_mmw(ot, accL, w->up, w->wdt, L, E);

        /* 6. shared experts, on the ORIGINAL input, added UNWEIGHTED */
        const int SI = I * c->n_shared;
        k3_mmw(gu,      xt, w->sh1, w->wdt, E, SI);
        k3_mmw(gu + SI, xt, w->sh3, w->wdt, E, SI);
        k3_situ_glu(act, gu, SI, c->situ_b1, c->situ_b2);
        k3_mmw(edn, act, w->sh2, w->wdt, SI, E);
        for (int i = 0; i < E; i++) ot[i] += edn[i];
    }
}
```Активация внутри каждого эксперта — SiTU-GLU, гейтированный блок, где обе половины проходят через сигмоиду с разными бетами.

![SiTU-GLU: две сигмоиды, две беты, один гейт](docs/images/eq_situ_glu.png)```c
void k3_situ_glu(float *y, const float *x, int n, float b1, float b2)
{
    const float *gate = x;
    const float *up   = x + n;
    for (int i = 0; i < n; i++) {
        const float g = gate[i];
        /* the sigmoid takes the UNCAPPED gate */
        const float a = b1 * tanhf(g / b1) * sigmoidf_(g);
        const float u = b2 * tanhf(up[i] / b2);
        y[i] = a * u;
    }
}
```Сигмоида читает **неограниченный** гейт `g`, а не ограниченный `b1 * tanh(g / b1)`. Подача ограниченного значения даёт плавную, но неверную кривую — модель всё ещё говорит, но веса комбинации смещены.```text
  PASS  situ_glu       n=48     worst=0.00x tol
        bound check |out|=100.000 must be <= b1*b2=100.0 : ok
```Фикстура, тестировавшая бы только около-линейную область, пропустила бы реализацию с опущенными caps — потому что при малых `g` ограничение почти не влияет. При больших `g` расхождение огромно, и именно туда целится фикстура. Проверяется не «примерно верно», а точное совпадение в хвостах.

![Квантильное балансирование: ни одна горстка экспертов не доминирует](docs/images/hosts-confound.png)

Это называется **Quantile Balancing**, чья единственная цель — выровнять использование экспертов по пулу, чтобы никакая малая группа не доминировала.

![Самые горячие эксперты из 10 010 различных затронутых](docs/images/expert_reuse.png)

Это хорошо для модели — и это будет очень плохо для кэша.```c
/* Silent numerical corruption that exits 0 is indistinguishable from a good run. */
if (k3_expert_drops) {
    fprintf(stderr,
            "\nRUN INVALID: %ld routed expert load(s) failed and were dropped from\n"
            "the MoE sum. The token ids above are CORRUPT. Re-run; if this repeats,\n"
            "the shard set or the storage is at fault.\n", k3_expert_drops);
    return 4;
}
return 0;
```Обратите внимание, где это находится: после всех отчётов и всех освобождений. Повреждённый прогон всё равно печатает полную диагностику и сохраняет артефакты — чтобы харнес, проверяющий только код выхода, не пропустил тихую порчу чисел.

## 10. Упаковка ствола: 93 слоя, по одному чтению каждый

Ствол — это 93 слоя плотных проекций, рассыпанных по 96 шардам. Чтение слоя означало бы пробраться через 17-ГБ файл. Так что перед запуском чего-либо он один раз переписывается в раскладку, подходящую под то, как его реально читают.

![Отказ, если байты не непрерывны — потому что разрыв означает копирование экспертов](docs/images/pack-trunk.png)

Ключевой факт, делающий это дешёвым: тензоры ствола каждого слоя непрерывны в шардах — эксперты, которые их прерывали бы, уже отделены.```python
# 93 sequential range copies, one per layer, each verified contiguous first.
for L in range(n_layers):
    names = [n for n in index if n.startswith(f"model.layers.{L}.") and not is_expert(n)]
    shards = {index[n] for n in names}
    if len(shards) != 1:
        die(f"layer {L} spans {len(shards)} shards; refusing")

    runs = sorted((offsets[n][0], offsets[n][1]) for n in names)
    lo, hi = runs[0][0], runs[-1][1]
    covered = sum(b - a for a, b in runs)
    if covered != hi - lo:
        # a gap would drag expert bytes along with it
        die(f"layer {L} is not contiguous: {hi - lo - covered} bytes of gap")

    out_off = align_up(out_off, ALIGN)      # head aligned for O_DIRECT
    copy_range(shard_path(shards.pop()), lo, hi, out_fh, CHUNK)
    out_off += align_up(hi - lo, ALIGN)     # and the tail, so reads never overrun
```![O_DIRECT требует выравнивания обоих концов, что стоит 4 КБ на слой](docs/images/eq_align.png)

Если тензоры слоя были бы не выровнены, каждый слой стоил бы дополнительного чтения. На релизном чекпоинте они выровнены.```text
  packed 10/93 layers, 12.90 GB, 25 s (521 MB/s)
  packed 20/93 layers, 24.31 GB, 47 s (520 MB/s)
  packed 30/93 layers, 36.14 GB, 74 s (488 MB/s)
  packed 40/93 layers, 47.55 GB, 99 s (480 MB/s)
  packed 50/93 layers, 59.38 GB, 127 s (466 MB/s)
  packed 60/93 layers, 70.79 GB, 153 s (462 MB/s)
  packed 70/93 layers, 82.62 GB, 181 s (457 MB/s)
  packed 80/93 layers, 94.02 GB, 208 s (451 MB/s)
  packed 90/93 layers, 105.86 GB, 236 s (448 MB/s)
  packed 93/93 layers, 108.81 GB, 244 s (447 MB/s)

wrote trunk.bin: 108.81 GB across 93 layers
largest layer run: 2.341 GB  <- the streaming slot size
```![Упаковка 93 последовательных прогонов слоёв в один файл на 108.81 ГБ](docs/images/pack_progress.png)

Четыре минуты, один раз — и слой L живёт по известному смещению и читается за один вызов. Последняя строка задаёт размеры всему, что ниже: **самый большой прогон слоёв — 2.341 ГБ**, так что любой буфер, должный вместить один произвольный слой, должен быть не меньше этого.

## 11. Четвёртая редукция: потоковая загрузка ствола превращает порог в регулятор

Ствол — 108.81 ГБ, и каждый его слой используется на каждом токене. Разреженности нет, пропускать нечего. Так что вопрос не в том, как избежать чтения, а в том, где его держать.

![Путь одного токена — от холодного NVMe до следующего слова](docs/images/big-picture.png)

![Закреплённые слои ничего не стоят при чтении, всё остальное идёт через один кольцевой слот](docs/images/trunk-stream.png)

Дизайн — закреплённый префикс плюс один вращающийся слот. Что помещается в бюджет — закрепляется навсегда, остальное циклично проходит через один кольцевой буфер. Критично, что это именно **префикс**, а не кэш.

Движок обходит слои 0–92 в одном и том же порядке на каждом токене. Это циклический скан, а циклический скан — патологический случай для вытеснения least-recently-used: к моменту, когда слой 0 снова подходит, он оказывается наименее недавно использованным элементом в кэше, так что он всегда только что вытеснен.

LRU на 90 слотов при цикле 93 слоя даёт частоту попаданий **ровно ноль**. Закрепление первых N слоёв вместо этого даёт детерминированную частоту N/93, что при N=90 составляет 96.8 процента. Очевидная структура данных здесь не просто неоптимальна — она неверна в худшую возможную сторону, возвращая ноль там, где тривиальный подход возвращает почти единицу.```c
/* Pinned count and slot size are mutually dependent, so iterate to a fixed point. */
size_t slot = tr->max_run;                 /* start assuming nothing is pinned */
int npin = 0;
for (int pass = 0; pass < 4; pass++) {
    size_t avail = budget > slot * (size_t)nring ? budget - slot * (size_t)nring : 0;
    int n = 0;
    size_t used = 0;
    while (n < tr->n_layers && used + tr->lay[n].nbytes <= avail) {
        used += tr->lay[n].nbytes;
        n++;
    }
    size_t need = 0;                       /* largest run still not pinned */
    for (int L = n; L < tr->n_layers; L++)
        if (tr->lay[L].nbytes > need) need = tr->lay[L].nbytes;
    if (need == 0) need = 4096;            /* everything pinned: degenerate but valid */
    if (n == npin && need == slot) break;  /* converged */
    npin = n;
    slot = k3_align_up(need, K3_TRUNK_ALIGN);
}
```Есть деталь памяти, которая сильно влияет. Чтения `O_DIRECT` закрепляют (pin) страницы назначения, и слот 2.37 ГБ на 4-КБ страницах стоит дороже, чем на 2-МБ huge pages — из-за накладных расходов на структуры страниц. Всего около 54 миллионов операций со страницами на токен чисто на бухгалтерию. Так что арены аллоцируются на 2-МБ huge pages.

![Всё суммируется до того, как что-либо аллоцируется, затем сравнивается со свободной RAM](docs/images/eq_ram_budget.png)```c
/* Add up EVERYTHING before allocating anything. */
const double need_b = w_trunk + w_model + w_cache + w_state + w_buf + w_kv;
const double have = mem_available_bytes();      /* MemAvailable, not MemFree */

if (need_b > have * 0.95) {
    fprintf(stderr,
            "\nREFUSING TO START: this needs %s and the machine has %s "
            "available, a shortfall of %s.\n"
            "Options: a larger box, a smaller --cache-gb, or fewer --layers.\n",
            b6, b1, b2);
    return 1;
}
```Этот план — явно прогноз, а не результат. Он не учитывает индекс safetensors (около 78 МБ в полном масштабе), отчёты и накладные расходы аллокатора. Пиковый RSS оказывается чуть ниже плана — и это нормально.

![Один токен: встройка, проход 93 слоёв, агрегация, проекция в словарь](docs/images/forward-pass.png)```c
/* One full forward over T tokens, writing logits for the LAST position only. */
static int forward(Weights *w, const K3Cfg *c, K3Cache *cache, const int *ids, int T,
                   float *logits_last, float *scratch, float *h, float *br, float *kstate)
{
    const int E = c->hidden;
    const int maxb = c->n_layers / c->attn_res_block + 2;
    const int P = c->kda_heads * c->kda_head_dim;
    const size_t kper = (size_t)P * c->kda_head_dim + (size_t)3 * P * (c->conv_k - 1);

    for (int t = 0; t < T; t++)
        k3_embed_row(h + (size_t)t * E, w->mb.embed, w->mb.wdt, ids[t], E);

    memset(br, 0, (size_t)T * maxb * E * sizeof(float));
    /* incremental decode carries the KDA state forward; full recompute rebuilds it */
    if (!w->kvc) memset(kstate, 0, kper * (size_t)w->n_bound * sizeof(float));

    int nb = 0;
    for (int L = 0; L < w->n_bound; L++) {
        /* bring this layer in, and hint the next one so its read overlaps */
        if (w->trunk) {
            if (k3_trunk_bind(w->trunk, c, L, &w->lay[L]) != 0) {
                fprintf(stderr, "trunk bind failed at layer %d\n", L);
                return -1;
            }
            k3_trunk_prefetch(w->trunk, L + 1);
        }
        if (w->lay[L].lay.moe) {
            w->lay[L].moe.src = &cache->src;
            w->lay[L].moe.layer = L;
        }
        if (w->kvc && w->mla_slot[L] >= 0) {
            const size_t kvper = (size_t)w->kv_cap * c->n_heads * (c->qk_nope + c->v_head);
            const size_t rpper = (size_t)w->kv_cap * c->qk_rope;
            const int mi = w->mla_slot[L];
            k3_decoder_layer_inc(h, br, &nb, &w->lay[L].lay, c, L, T,
                                 kstate + kper * (size_t)L, scratch,
                                 w->kvc + kvper * (size_t)mi,
                                 w->ropec + rpper * (size_t)mi,
                                 w->cached, w->kv_cap);
        } else {
            k3_decoder_layer_inc(h, br, &nb, &w->lay[L].lay, c, L, T,
                                 kstate + kper * (size_t)L, scratch,
                                 NULL, NULL, 0, 0);
        }
    }

    /* one model-level aggregator, beyond the two in every layer */
    if (w->mb.out_res_norm && w->mb.out_res_proj) {
        float *fold = scratch;
        float *src  = fold + E;
        for (int i = 0; i < E; i++) fold[i] = w->mb.out_res_norm[i] * w->mb.out_res_proj[i];
        for (int t = 0; t < T; t++) {
            for (int b = 0; b < nb; b++)
                memcpy(src + (size_t)b * E, br + ((size_t)t * maxb + b) * E,
                       (size_t)E * sizeof(float));
            memcpy(src + (size_t)nb * E, h + (size_t)t * E, (size_t)E * sizeof(float));
            k3_attn_res(h + (size_t)t * E, src, fold, nb + 1, E, c->rms_eps);
        }
    }

    float *nrm = scratch;
    k3_rmsnorm(nrm, h + (size_t)(T - 1) * E, w->mb.norm, E, c->rms_eps);
    k3_mmw(logits_last, nrm, w->mb.lm_head, w->mb.wdt, E, c->vocab);
    return 0;
}
```Это и есть вся модель в семидесяти строках. Встроить токены, пройти 93 слоя, привязывая каждый по мере поступления, применить финальный агрегатор по всем снапшотам блоков, нормализовать последнюю позицию и спроецировать в 163 840 логитов.

Строка `if (!w->kvc)` — это всё различие между инкрементальным декодированием и полным рекомпьютом в одном условии.

![Фиксированный порядок обхода означает, что следующее чтение может начаться до завершения этого слоя](docs/images/eq_prefetch.png)

При первом прохождении```text
Kimi K3, pure C, released checkpoint
  model    : /home/k3/k3model
  prompt   : 5 tokens, generating 2

indexed 497220 tensors from 96 shards in 0.70 s

memory plan
  trunk (STREAMED) 16.00 GB
  embed + lm_head  4.70 GB
  expert cache     6.00 GB
  recurrent state  626.25 MB
  buffers          6.68 MB
  KV cache         0.00 B
  TOTAL            27.33 GB
  available        65.91 GB

trunk stream: 108.81 GB packed, 10/93 layers PINNED (13.16 GB), ring 1 x 2.37 GB
              reads use O_DIRECT (page cache bypassed)
              deterministic hit rate 10.8% (a cyclic scan defeats LRU, so a pinned
              prefix is used instead)

peak RSS after loading weights: 4.78 GB  (the plan above is a forecast, this is measured)
expert cache: 341 slots x 17.56 MB = 5.99 GB (0.41% of the 1.45 TB expert pool)

STEP   TOKEN      SECONDS      CACHE HIT  READ GB    TOK/S
--------------------------------------------------------------------
0      2494       167.84       35.0       83.91      0.006
1      9          171.65       39.3       94.05      0.006
--------------------------------------------------------------------
2 tokens in 339.5 s, 169.75 s/token average
PEAK RSS for the whole run: 25.83 GB   <- quote this, not the plan
```Это работает — и это **169.75 секунд на токен**, что непригодно. Почти всё в [части IV](#part-iv-measurements) — о том, как сбить это число до 10.66, и то, что это исправляет, — не очевидное.

Толкая в другую сторону, когда вообще ничего не закреплено и кэш экспертов меньше двух гигабайт:```text
trunk stream: 108.81 GB packed, 0/93 layers PINNED (0.00 GB), ring 2 x 2.37 GB
              deterministic hit rate 0.0%
expert cache: 113 slots x 17.56 MB = 1.98 GB (0.14% of the 1.45 TB expert pool)

STEP   TOKEN      SECONDS      CACHE HIT  READ GB    TOK/S
--------------------------------------------------------------------
0      17374      57.08        22.8       99.70      0.018
1      20829      27.72        0.0        25.83      0.036
2      10         26.95        0.0        25.83      0.037
3      427        27.25        0.0        25.83      0.037
--------------------------------------------------------------------

cache [final step]
  requests     : 1472  hits 0 (0.00%)  misses 1472  evictions 1472
```Ноль закреплённых слоёв. Кэш экспертов, держащий **0.14 процента** пула. Частота попаданий кэша ровно **ноль**, все 1 472 запроса — промахи и все 1 472 — вытеснения. И всё равно выдаёт `17374, 20829, 10, 427` — тот же правильный ответ, что и любая другая конфигурация.

![Потоковая загрузка превращает порог 315 ГБ в регулятор 11 ГБ](docs/images/resident_vs_streamed.png)

Держать ствол резидентно вместо этого тратит **150 секунд только на загрузку весов** до первого токена, требует 315 ГБ```c
/* Offset and length are both 4096-aligned, so this is a plain pread with no fixup. */
static int load_run(K3Trunk *tr, int L, unsigned char *dst)
{
    const K3Run *r = &tr->lay[L];
    size_t got = 0;
    while (got < r->nbytes) {
        const ssize_t n = pread(tr->fd, dst + got, r->nbytes - got,
                                (off_t)(r->off + got));
        if (n <= 0) return -1;      /* a short read is a corrupt layer */
        got += (size_t)n;
    }
    tr->bytes_read += got;
    return 0;
}
```## 12. LRU-кэш для экспертов

Теперь другая сторона пути чтения: 1 472 выборки экспертов на токен, каждая по 17.56 МБ, из пула 1.45 ТБ.

![Слот бывает пустым, зарезервированным, но ещё не читаемым, или хранящим эксперта](docs/images/cache-slot-states.png)

![Кэш экспертов хранит целых экспертов, так что бюджет делится нацело](docs/images/eq_slot_count.png)```c
/* Three slot states, not two: a key, EMPTY, or INFLIGHT. */
static int pick_victim(K3Cache *c)
{
    int best = -1;
    uint64_t oldest = (uint64_t)-1;
    for (int i = 0; i < c->nslot; i++) {
        if (c->key_of[i] == K3_SLOT_INFLIGHT) continue;   /* being read into RIGHT NOW */
        if (c->key_of[i] == K3_SLOT_EMPTY) return i;      /* free, take it */
        if (c->pinned[i]) continue;
        if (c->used_at[i] < oldest) { oldest = c->used_at[i]; best = i; }
    }
    return best;
}
```Три детали в двенадцати строках. Слоты `INFLIGHT` полностью пропускаются, а не рассматриваются как кандидаты, так что слот нельзя захватить дважды. `EMPTY` возвращается немедленно — свободный слот всегда лучше вытеснения живого. А закреплённые слоты пропускаются *после* теста на пустоту, так что закрепление никогда не блокирует дешёвый путь.

![Резервируй последовательно, читай параллельно, затем публикуй только то, что пришло](docs/images/cache-3phase.png)

![Пакетные pread держат устройство занятым, последовательные — оставляют его простаивать](docs/images/eq_queue_depth.png)```c
static int cache_getmany(K3ExpertSrc *self, int layer, const int *experts, int n)
{
    K3Cache *c = (K3Cache *)self->ctx;
    int slots[K3_MAX_TOPK];

    /* phase 1: reserve serially, so no two experts take the same slot */
    int nres = 0;
    for (int j = 0; j < n; j++) {
        int s = cache_lookup(c, layer, experts[j]);
        if (s >= 0) { slots[j] = -1; continue; }        /* already resident */
        s = cache_pick_victim(c);
        if (s < 0) { slots[j] = -1; continue; }
        c->slot_id[s] = K3_SLOT_INFLIGHT;
        slots[j] = s;
        nres++;
    }

    /* phase 2: read in parallel, in disk-offset order */
    int order[K3_MAX_TOPK];
    cache_sort_by_offset(c, layer, experts, slots, n, order);
#pragma omp parallel for schedule(dynamic)
    for (int k = 0; k < n; k++) {
        const int j = order[k];
        if (slots[j] < 0) continue;
        if (!k3_expert_load_direct(c->st, layer, experts[j], c->arena + slot_off(c, slots[j])))
            slots[j] = -2;
    }

    /* phase 3: publish only what arrived */
    for (int j = 0; j < n; j++) {
        if (slots[j] >= 0) c->slot_id[j] = expert_key(layer, experts[j]);
        else if (slots[j] == -2) c->slot_id[j] = K3_SLOT_EMPTY;
    }
    return nres;
}
```Размер слота несёт похожую защиту. Эксперт — 17 547 264 байта, что случайно равно ровно 4 284 × 4 096, так что требуемое для чтений выравнивание на релизном чекпоинте выполняется **по совпадению**. Код, который бы полагался на выравнивание, а не обеспечивал его, работал бы на каждом отгруженном весе — именно поэтому фикстура кэша намеренно использует несоответствующий размер эксперта. Релизные веса не могут прогнать этот путь, так что тестовые данные были сделаны специально.```c
int64_t k3_expert_load(const K3St *s, const K3ExpertRef *r, unsigned char *buf)
{
    if (r->contiguous) {                     /* one coalesced 17.55 MB read */
        K3Tensor t;
        memset(&t, 0, sizeof t);
        t.name = (char *)"expert";
        t.shard = r->shard;
        t.off = r->off;
        t.nbytes = r->nbytes;
        t.dtype = K3_DT_U8;
        t.ndim = 1;
        t.shape[0] = r->nbytes;
        return k3_st_read(s, &t, buf);
    }

    /* fallback: six separate reads, one per tensor */
    static const char *W[3] = { "w1", "w2", "w3" };
    char name[256];
    int64_t got = 0;
    for (int i = 0; i < 3; i++) {
        snprintf(name, sizeof name, EXPERT_FMT, r->layer, r->expert, W[i], "weight_packed");
        const K3Tensor *p = k3_st_find(s, name);
        snprintf(name, sizeof name, EXPERT_FMT, r->layer, r->expert, W[i], "weight_scale");
        const K3Tensor *c = k3_st_find(s, name);
        if (!p || !c) return got;
        got += k3_st_read(s, p, buf + (p->off - r->off));
        got += k3_st_read(s, c, buf + (c->off - r->off));
    }
    return got;
}
```Тот синтетический `K3Tensor` под именем `"expert"` не соответствует ничему в шарде; это удобный универсальный тип, чтобы путь экспертов шёл через тот же выровненный ридер.```text
4. streaming expert cache
  PASS  prefetch_reads <= hits             requests 24, hits 24, prefetch 24
  PASS  mixed batch and serial             0 of 24 wrong
CACHE TESTS PASSED
```![Восьмикратный разброс скорости носителя — и движок упирается в ввод-вывод](docs/images/storage_regimes.png)

Случайное холодное чтение — паттерн, который имеет значение, потому что роутер выбирает экспертов по релевантности, а файл раскладывает их по индексу, и эти два порядка никак не связаны.

![Один прогон, один трейс — затем проигрывай его при любой ёмкости](docs/images/trace-replay.png)

Кэш работает, так что один прогон может записать каждый запрос `(слой, эксперт)`, и этот единственный трейс можно проиграть при любой ёмкости и любой политике.```python
def belady(trace, cap):
    """Evict whatever is needed furthest in the future. A ceiling, not a policy."""
    nxt = defaultdict(deque)
    for i, k in enumerate(trace):
        nxt[k].append(i)
    resident, hits = set(), 0
    for k in trace:
        nxt[k].popleft()
        if k in resident:
            hits += 1
            continue
        if len(resident) >= cap:
            victim = max(resident, key=lambda r: nxt[r][0] if nxt[r] else 1 << 60)
            resident.discard(victim)
        resident.add(k)
    return hits / len(trace)
```

```text
trace: 100096 requests, 10010 distinct experts, about 68 token(s)
distinct experts touched: 10010 of 82432 (12.14% of the pool)
if nothing were cached: 25.83 GB per token
total reuse: 90086 of 100096 requests are repeats (90.0%)

CACHE        SLOTS       LRU    BELADY   PIN+LRU  GB READ/TOK     SEC/TOK
----------------------------------------------------------------------------
8 GB           455    36.24%    39.42%    37.82%        16.47       13.35
16 GB          911    36.24%    42.61%    39.42%        16.47       13.35
32 GB         1823    36.24%    48.99%    42.57%        16.47       13.35
64 GB         3647    36.24%    61.74%    48.66%        16.47       13.35
128 GB        7294    49.19%    84.59%    62.86%        13.12       10.64
192 GB       10941    90.00%    90.00%    90.00%         2.58        2.09
1450 GB      82633    90.00%    90.00%    90.00%         2.58        2.09

compulsory misses: 10010 (every expert must be read at least once), a ceiling of
90.00% hit rate for ANY policy at ANY size on this trace.
```![Каждый отдельный эксперт должен быть прочитан хотя бы раз, так что ни одна политика не побьёт это](docs/images/eq_compulsory.png)

![Эксперты, которых этот трейс вообще затронул, на фоне пула 1.45 ТБ](docs/images/eq_working_set.png)

Шестьдесят восемь токенов затронули 10 010 различных экспертов — лишь 12.14 процента пула. Удерживать каждый эксперт, которого трейс хоть раз коснулся, стоило бы 176 ГБ — больше, чем весь резидентный набор. LRU с 13 ГБ удерживает 740 из них одновременно, и ни одна политика не может избежать обязательного промаха при первом касании.

![Сколько экспертов затронуто на каждом бюджете кэша](docs/images/cache-miss-rate.png)

Тот же диапазон растёт с 39 до 62 процентов, а значит плоскость принадлежит политике, а не нагрузке.

![Рычаг — политика, а не размер: LRU плоский там, где Belady растёт](docs/images/belady_vs_lru.png)

При 64 ГБ есть **разрыв 25.5 пункта** между тем, что достигает LRU, и тем, что мог бы.```text
CAVEAT, and it matters
This trace was recorded during a run that re-prefills the whole prefix every step, so
the same experts are legitimately touched ~68 times. Steady-state incremental decode
has far less reuse, and its hit rates will be LOWER than this curve suggests. Treat
these numbers as an upper bound on what caching can do, not a forecast.
```Держите эту таблицу в уме. [Часть IV](#part-iv-measurements) измеряет её напрямую — и два не сходятся.

---

# Часть III: Валидация

## Лесенка гейтов (gate ladder)

![Четыре уровня доказательств — и лишь последние два касаются релизного чекпоинта](docs/images/gate_ladder.png)

![Бюджет округления на 93 слоя при скрытом размере 7168](docs/images/eq_tolerance.png)

![Фикстуры операций, игрушечный оракул, затем релизный чекпоинт](docs/images/oracle-ladder.png)

## Сначала — маленький оракул

Средний уровень — крошечная модель с тем же графом тензоров: тринадцать слоёв, скрытый размер 128, словарь 256.

Почему тринадцать, а не пять? Потому что остаточные связи внимания работают блоками по двенадцать, и их режимы отказа не проявляются, пока не завершены два блока и не начат третий. Пятислойная модель вообще не затронула бы граничную логику.```text
3. full-model oracle gates on the 13-layer reference
checkpoint: 628 tensors loaded
layer map (0-based): KKKMKKKMKKKMM   (M=MLA, K=KDA; dense layer = 0)
attn_res boundaries at: 0 3 6 9 12
prompt_ids 12, full_ids 32, tf_pred 32
all layer weights bound

GATE 1  teacher forcing : 32/32 positions match tf_pred
        generated span  : 20/20  <- must be exact
GATE 2  greedy decode   : 20/20 generated tokens match full_ids
GATE 3  incremental    : 20/20 generated tokens match full_ids  <- KV cache + carried KDA state

VERDICT: ENGINE MATCHES THE REFERENCE EXACTLY
```Три разных пути исполнения дают идентичные id токенов. Все три — точные.```text
The strongest-sounding line in gates.txt is about a toy model. "VERDICT: ENGINE
MATCHES THE REFERENCE EXACTLY" refers to the 13-layer, hidden-128, vocab-256 oracle
- NOT the 2.8T checkpoint.
```Каждая фикстура была спроектирована так, чтобы сломать конкретную правдоподобную неверную реализацию. Промахи не «в пределах допуска» — они огромны.```python
# A wrong binding does not miss by 1e-6, it misses by ~1.
tol = 1.2e-7 * math.sqrt(width) * 50
```

```text
L87  KDA  PASS   3 stages  worst 0.00x budget   44s
L88  KDA  PASS   3 stages  worst 0.00x budget   46s
L89  KDA  PASS   3 stages  worst 0.00x budget   43s
L90  KDA  PASS   3 stages  worst 0.00x budget   45s
L91  MLA  PASS   3 stages  worst 0.00x budget   46s
L92  MLA  PASS   3 stages  worst 0.00x budget   49s

==============================================================================
LAYERS 0..92   93 passed, 0 failed   (69 KDA, 24 MLA)   5639 s total
worst stage across all passing layers: 0.00x of its rounding budget
==============================================================================
VERDICT: ALL LAYERS CONFORM
```![Все 93 слоя сверены с torch: 93 пройдено, 0 провалено, 5639 секунд](docs/images/layer_conformance.png)

Примечание: время — это стоимость побитовой точности. Каждый слой сверяется отдельно, а не только финальные логиты. 5639 секунд — это цена за доказательство, что каждый слой совпадает.```text
reference forward: 93 layers, 5 prompt ids, hidden 7168, vocab 163840
embedded 5 ids (BF16)
  L0   KDA dense    20.7 s   |h| max 0.145457
  L1   KDA MoE      44.7 s   |h| max 0.187096
  L2   KDA MoE      41.8 s   |h| max 0.463652
  L3   MLA MoE      39.2 s   |h| max 1.284419
  ...
  L92  MLA MoE      36.7 s   |h| max 31.064180

final position: argmax token 2494, logit 15.021948, mean -0.462536, max 15.021948
total 3608.5 s
```**Три тысячи шестьсот секунд.** Один час на один прямой проход по пяти токенам промпта с скрытым размером 7168 и словарём 163 840. Это цена побитовой точности: каждый слой сравнивается по отдельности, а не только финальные логиты. C-движок сделал тот же проход за 169.73 секунды.

![Сравни все 163 840 логитов, а не только победителя](docs/images/parity-flow.png)```text
===== ELEMENTWISE LOGIT COMPARISON =====
prompt cross-check     : both sides ran [3, 4, 5, 6, 7]
vocab                 : 163840
C argmax              : 2494  (logit 15.021946)
reference argmax      : 2494  (logit 15.021948)
top-10 overlap        : 10/10
max |diff|            : 7.867813e-06
relative to max|ref|  : 5.237545e-07   (budget 5.1e-04)
mean |diff|           : 1.231738e-06
correlation           : 1.000000000

VERIFIED: the C engine's logits match the torch reference over the FULL 93-layer
stack on the released checkpoint, elementwise, and the argmax token agrees.
```Наибольшее расхождение где бы то ни было среди 163 840 значений — **7.87 × 10⁻⁶**, примерно половина младшего бита bfloat16. Это шум округления, а не ошибка.```text
The logit parity run used prompt ids 3,4,5,6,7, which decode to: $%&'(
That is synthetic junk, not text.

That same run reports `KV cache 0.00 B`, so the KV path is not exercised by the
parity check at all.
```Это согласие на одной позиции бессмысленного промпта: сильное свидетельство о математике, слабое — о языке. Следующий раздел проверяет язык.

## Первые токены

![Промпт на входе, 93 слоя, один argmax, одно слово на выходе](docs/images/first-token.png)```text
  prompt    ids : 1008,10484,318,15383,387
  prompt    txt : The capital of France is
  generated ids : 17374,20829,10,427,414,1008,606,142957
  generated txt :  Paris.",~+            "The Eiffel~
                  (~ marks a newline)

  The first two tokens are 17374 = ' Paris' and 20829 = '.",' - the model answers
  the question CORRECTLY.
```**Paris.** Первый токен из модели на 2.78 триллиона параметров, работающей на одном CPU. Проверка строкой выше сверяла логиты на бессмысленных байтах; эта проверяет, что модель всё ещё говорит по-английски (и по-французски).```text
  cap    trunk  cache  s/token    token ids          decoded
96G    48G    40G    72.3430    17374,20829,10  Paris.",~+~
64G    32G    24G    67.8921    17374,20829,10  Paris.",~+~
48G    24G    16G    63.1822    17374,20829,10  Paris.",~+~
32G    12G    12G    63.4072    17374,20829,10  Paris.",~+~
24G    10G    7G     60.8162    17374,20829,10  Paris.",~+~
16G    6G     4G     68.4805    17374,20829,10  Paris.",~+~
12G    4G     2G     61.0702    17374,20829,10  Paris.",~+~

Every row that ran must show the SAME tokens. A differing row is a bug.
```![Семь потолков памяти, семь разных скоростей, один идентичный ответ](docs/images/same_answer.png)

От 96 ГБ до 12 ГБ — те же три токена. Не просто те же id при каждом бюджете, а тот же правильный ответ.

## Устойчивая генерация: текст на входе, текст на выходе

Четыре полные генерации, простой текст на входе и простой текст на выходе, с токенизатором на C на обоих концах и без Python где-либо на пути.

![Одна стена префилла, затем ровная полка — на каждом промпте](docs/images/gen-loop.png)

Все четыре прогона — с `--trunk-gb 110 --cache-gb 13 --incremental`. Это разбиение отдаёт почти всё стволу.```c
for (int g = 0; g < gen; g++) {
    k3_cache_reset_stats(&cache);
    const double ts = now_s();
    int frc;
    if (incremental) {
        /* step 0 feeds the whole prompt; later steps feed only the new token */
        const int base = w.cached;
        const int nT   = (g == 0) ? np : 1;
        frc = forward(&w, &c, &cache, seq + base, nT, lg, sc, h, br, ks);
        w.cached = base + nT;
    } else {
        frc = forward(&w, &c, &cache, seq, T, lg, sc, h, br, ks);
    }
    /* Abort the run rather than argmax a buffer the forward never wrote. */
    if (frc != 0) {
        fprintf(stderr, "forward pass failed at generation step %d; aborting.\n", g);
        return 1;
    }
    const int nxt = argmax_(lg, c.vocab);
    ...
}
```Сэмплер — одна строка, и это единственная, которая есть:```c
static int argmax_(const float *v, int n)
{ int b = 0; for (int i = 1; i < n; i++) if (v[i] > v[b]) b = i; return b; }
```Жадный (greedy), без температуры и без top-p. Это сделано намеренно, а не «пока не доделано» — именно жадный декодинг делает вывод идентичным при любом бюджете памяти, и на этом свойстве держится большая часть тестирования.```text
trunk stream: 108.81 GB packed, 90/93 layers PINNED (108.19 GB), ring 1 x 1.29 GB
              deterministic hit rate 96.8%
expert cache: 740 slots x 17.56 MB = 12.99 GB (0.90% of the 1.45 TB expert pool)
incremental decode: KV cache 70.96 MB for 24 MLA layers at 30 positions

STEP   TOKEN      SECONDS      CACHE HIT  READ GB    TOK/S
--------------------------------------------------------------------
0      1040       53.04        100.0      89.21      0.019
1      149803     8.92         100.0      25.83      0.112
2      316        8.92         100.0      25.83      0.112
3      374        8.74         100.0      25.83      0.114
4      1491       8.85         100.0      25.83      0.113
5      261        8.91         100.0      25.83      0.112
--------------------------------------------------------------------
24 tokens in 255.8 s, 10.66 s/token average

--- generated text ---
 Kelsey and I am a certified teacher. I have experience tutoring after school at the
middle school level. I have taught
----------------------

PEAK RSS for the whole run: 127.89 GB   <- quote this, not the plan
```Промпт был **"Hello! My name is"**. Это беглый, грамматичный текст, который держит персону на всём отрезке: придумал имя и оставался ему верен двадцать четыре токена.

Посмотрите на колонку времени — эта форма повторяется в каждом прогоне. Шаг 0 занимает **53.04 секунды** и читает 89.21 ГБ. Каждый шаг после него — около **8.9 секунд** и читает ровно **25.83 ГБ**.

![Префилл масштабируется с промптом, и ничего после него — нет](docs/images/eq_prefill.png)

![Одна стена префилла, затем ровная полка — на всех четырёх промптах](docs/images/step_trace.png)

Учитывая```text
--- generated text ---

    if n <= 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci
----------------------

28 tokens in 299.3 s, 10.69 s/token average
```Корректная рекурсивная Фибоначчи. Базовый случай `if n <= 1: return n` верен, отступы верны, и рекуррентность верна — обрезана лишь потому, что бюджет токенов закончился посреди выражения.

А на промпт «Kimi K3 is a mixture-of-experts language model. It works by»:```text
--- generated text ---
 routing each token through a small subset of its total parameters, which keeps
inference fast and cheap relative to its size. The model is trained on a large corpus of
----------------------

32 tokens in 361.6 s, 11.30 s/token average
```**«маршрутизируя каждый токен через небольшое подмножество всех своих параметров»** — ровно то, что реализует [часть II](#part-ii-how-it-works). Этот прогон также показывает масштабирование стоимости префилла: промпт здесь — 17 токенов вместо 5, и шаг 0 занял **97.98 секунд и прочитал 200.67 ГБ**, примерно вдвое больше пятитокенных промптов, тогда как каждый последующий шаг всё так же читал ровно 25.83 ГБ.

![Префилл масштабируется с промптом, и ничего после него — нет](docs/images/prefill_cost.png)

Четыре промпта — это демонстрация, а не бенчмарк. Но форма стабильна: примерно от 10.7 до 11.8 секунд на токен при том же разбиении trunk/cache. И всякий раз, когда память ограничивается cgroup, ответ остаётся тем же.

![Ограничь память через cgroup — затем проверь, что id идентичны](docs/images/ladder-harness.png)```bash
# MemorySwapMax=0 matters as much as MemoryMax: without it an over-budget rung
# swaps instead of dying, and its s/token measures swap bandwidth.
systemd-run --scope --user -q \
    -p MemoryMax=${TOT}G -p MemorySwapMax=0 \
    ./bin/k3 "$MODEL" --ids "$IDS" --gen "$GEN" \
    --trunk "$TRUNK" --trunk-gb "$TR" --cache-gb "$CA" --incremental \
    --out "$OUT/$tag.json" > "$OUT/$tag.log" 2>&1
```

```text
=== LADDER COMPLETE ===
total_gb  pin_layers  cache_gb  s_per_tok  trunk_hit  gb_read  peak_rss_gb
8         0           0.49      32.69      0.0        25.83    8.24
12        0           2.79      31.41      0.0        25.83    10.53
16        3           4.39      32.21      2.8        25.83    16.00
24        7           7.58      31.85      6.6        25.83    23.95
32        11          10.80     31.44      10.3       25.83    31.90
48        19          17.19     29.76      17.9       25.83    47.80
64        27          23.59     28.60      25.4       25.83    63.71
96        43          36.39     24.40      40.5       18.11    95.51
128       60          49.19     29.40      56.5       17.51    128.18
160       76          61.99     26.31      71.5       17.28    159.98
192       90          77.00     21.32      84.7       16.65    191.83
224       90          108.98    19.21      84.7       14.53    223.82

ids, every row: 17374,20829,10,427,414,1008,606,142957
```Читайте последнюю строку первой. **Каждая ступень дала побайтово идентичный вывод.** Двенадцать бюджетов с разбросом в 28 раз — и id токенов везде одинаковые.

Сырые данные: [`docs/data/memory-ladder.tsv`](docs/data/memory-ladder.tsv).

![В 28 раз больше памяти даёт в 1.70 раза больше скорости, и большинство шагов — внутри шума](docs/images/memory_ladder.png)

Переход от 8 ГБ к 224 ГБ снижает время с 32.69 с/токен до 19.21. Это **в 28 раз больше памяти за в 1.70 раза больше скорости.** Если вы выбираете железо, прыжок с 8 ГБ до 64 ГБ даёт 14 процентов. Память — не там, где скорость.

![План памяти не врёт: каждая ступень попадает в свой бюджет](docs/images/rss_fidelity.png)

Попросите 8 ГБ — использует 8.24. Попросите 224 — использует 223.82. Каждая ступень попадает в свой бюджет. План памяти не врёт.

![Токен ноль оплачивает стоимость закрепления — так что короткие прогоны занижают частоту попаданий](docs/images/eq_trunk_hit.png)

На верхних ступенях закреплены 90 из 93 слоёв, так что установившаяся частота попаданий ствола — 96.8 процента. Таблица показывает 84.7 — потому что токен ноль оплатил закрепление.```text
8    GB budget  ->  25.83 GB read per token
12   GB budget  ->  25.83 GB read per token
16   GB budget  ->  25.83 GB read per token
24   GB budget  ->  25.83 GB read per token
32   GB budget  ->  25.83 GB read per token
48   GB budget  ->  25.83 GB read per token
64   GB budget  ->  25.83 GB read per token
```Семь бюджетов подряд прочитали **ровно** одинаковое количество байт. На этом отрезке кэш экспертов растёт с 28 слотов до 1 344 — в 48 раз, а перемещённые байты не меняются ни на один знак после запятой.

![Кэш экспертов вообще ничего не делает примерно до 36 ГБ арены](docs/images/gb_read_shelf.png)

Кэш, который растёт в 48 раз и меняет перемещённые байты на ноль, работает не неэффективно. Он **вообще не участвует**.

![Симуляция ошибалась в обе стороны](docs/images/sim_vs_measured.png)

Симуляция предсказывала плоские 36.24 процента с изломом на 128 ГБ.```text
cache [final step]
  slots        : 740 of 17.56 MB = 12.99 GB arena (740 resident, 0 pinned)
  requests     : 1472  hits 1472 (100.00%)  misses 0  evictions 1032
  of those hits : 38940 came from the batch prefetch, i.e. read from disk
                  this token; TRUE resident hit rate 0.00%
  read from disk: 25.83 GB in 5.06 s (5104 MB/s while loading)
```Частота попаданий 100.00 процента двумя строками выше резидентной частоты 0.00 процента — на тех же 1 472 запросах.

![Один счётчик, три ответа — и лишь один означает избегнутый ввод-вывод](docs/images/metric-bug.png)

![Три определения одного числа — и лишь третье согласуется с байтами](docs/images/hit_metrics.png)

Первый считает запрос, удовлетворённый из арены, но пакетный префетч положил эксперта туда микросекундами ранее, прочитав его с диска, так что он показывает около 100 процентов при любом размере кэша и ничего не говорит об избегнутом вводе-выводе. Второй считает только экспертов, уже резидентных до начала шага — величину, которая нас интересует, но она меряется по окну, сбрасывающемуся каждый шаг.

![Единственная метрика кэша экспертов, согласующаяся с реально прочитанными байтами](docs/images/eq_retention.png)

Эксперт, которого пришлось вытеснить, — это эксперт, который не удержался. На ступени 36.39 ГБ это даёт `1 - 1032/1472 = 29.89%` удержано, против `18.11/25.83 = 70.1%` всё ещё читаемых байт. Эти два числа совпадают до знака после запятой, посчитанные по совершенно разным счётчикам.

![Как выглядит работающий кэш экспертов — шаг за шагом](docs/images/cache_wakeup.png)

При бюджете 8 ГБ каждый шаг читает 25.83 ГБ — ровно и навсегда. При 96 ГБ чтения падают с 99.70 до 23.58 до 19.90 до 14.07 за первые четыре шага, по мере того как арена наполняется экспертами, которые используются повторно. Эта спадающая кривая — то, как выглядит работающий кэш, и она не появляется нигде ниже примерно 36 ГБ арены.

## Распределение важнее ёмкости

Если кэш экспертов ничего не даёт ниже 36 ГБ, куда вместо этого отдать память?

Арифметика не близка. Ствол — это 108.81 ГБ, перечитываемые полностью на каждом токене. Эксперты — 25.83 ГБ на токен. Это **в 4.2 раза больше байт и в 2.9 раза больше времени**.

![Ствол перечитывается полностью каждый токен, эксперты — лишь выборочно](docs/images/eq_traffic.png)

![Что один закреплённый слой убирает из гарантированного трафика](docs/images/eq_gb_per_layer.png)

Гигабайт, отданный стволу, закрепляет примерно ещё один слой и убирает около 1.17 ГБ трафика на токен, который иначе случился бы гарантированно. Гигабайт, отданный кэшу экспертов, убирает — ниже колена — ничего измеримого.

![Отдайте стволу всё, пока он не закреплён полностью, затем кормите кэш](docs/images/split-rule.png)

Так что это проверили напрямую. Зафиксировали суммарную память и варьировали только разбиение:```bash
# Fractions of the budget given to the trunk, cache-heavy first so the sweep runs
# AGAINST the hypothesis rather than with it.
FRACS="0.10 0.25 0.60 0.86"
```

```text
total_gb  trunk_gb  cache_gb  s_per_tok  hit_pct  gb_read  peak_rss
128       12.3      110.7     28.38      44.02    14.46    127.89
128       30.8      92.2      25.20      42.93    14.74    127.53
128       49.2      73.8      25.69      33.97    17.06    128.14
128       73.8      49.2      18.37      32.20    17.51    128.19
128       98.4      24.6      19.46      0.0      25.83    127.36
128       110.0     13.0      16.80      0.0      25.83    127.85
```![При фиксированном бюджете отдать больше стволу — в 1.69 раза быстрее](docs/images/trunk_cache_split.png)

С 28.38 с/токен до 16.80 — при **идентичной суммарной памяти**: в 1.69 раза быстрее только за счёт распределения.

А теперь посмотрите ещё раз, потому что в этой таблице есть результат, идущий в обратную сторону. **Самая быстрая** конфигурация читает 25.83 ГБ на токен при 0.0 процента попаданий кэша. **Самая медленная** читает лишь 14.46 ГБ при 44.02 процента попаданий.

![Победитель читает на 79% больше байтов экспертов и всё равно выигрывает](docs/images/bytes_paradox.png)

Победитель перемещает на 79 процентов больше байтов экспертов, чем проигравший — и всё равно выигрывает, потому что держит больше слоёв ствола закреплёнными.

Сырые данные: [`docs/data/trunk-cache-split.tsv`](docs/data/trunk-cache-split.tsv).```text
[09:36:39] --- replicate 1/3 (trunk 110 / cache 13, gen 8, identical every time) ---
  8 tokens in 118.2 s, 14.78 s/token average
[09:39:14] --- replicate 2/3 ---
  8 tokens in 117.3 s, 14.67 s/token average
[09:41:22] --- replicate 3/3 ---
  8 tokens in 161.1 s, 20.14 s/token average
```![Один и тот же бинарь, один и тот же промпт, одни и те же флаги, одна и та же машина, одна и та же минута](docs/images/replication_noise.png)

![Три идентичных прогона — так что меньшая разница не является эффектом](docs/images/eq_spread.png)

Среднее 16.53 с/токен, стандартное отклонение 3.13, разброс **33.1 процента**. Треть измерения — шум.

Это планка, которую должен преодолеть любой заявляемый выигрыш по времени, и она перечёркивает несколько меньших ступеней лесенки. Ступень 12 ГБ, оказавшаяся на четыре процента ниже 8 ГБ, — не эффект. Улучшение 11 процентов от приоритета стволу при суммарных 32 ГБ — не эффект. Провал на 12 ГБ — тоже.

![Лишь два эффекта по времени проходят планку](docs/images/noise-floor.png)

Два результата уверенно проходят планку: лесенка охватывает **70 процентов** разброса.```text
run A  (from the ladder)        run B  (from the split sweep)
  trunk (STREAMED) 73.80 GB       trunk (STREAMED) 73.80 GB
  expert cache     49.20 GB       expert cache     49.20 GB
  60/93 layers PINNED (72.34 GB)  60/93 layers PINNED (72.34 GB)
  2802 slots                      2802 slots
  requests 1472  evictions 998    requests 1472  evictions 998
  binds 744, hits 420 (56.5%)     binds 744, hits 420 (56.5%)
  read 374.99 GB in 138.40 s      read 374.99 GB in 63.84 s
       (2709 MB/s)                     (5874 MB/s)
  29.40 s/token                   18.37 s/token
```Они закрепили одни и те же слои, выделили одинаковое число слотов, сделали одинаковое число запросов, вытеснили одинаковое число экспертов и прочитали **ровно те же 374.99 ГБ**. Каждый счётчик совпадает. Единственная разница — один получил с диска 2 709 МБ/с, а другой — 5 874, разница в 2.17 раза при идентичной работе.

![Одна и та же конфигурация, измеренная дважды, с идентичной работой](docs/images/duplicate_config.png)

Разброс — не джиттер планировщика и не размещение NUMA. Это устройство.

Сырые данные: [`docs/data/replication.tsv`](docs/data/replication.tsv).

## Хранилище — это вся игра

![Это задача ввода-вывода при любом бюджете, от 8 ГБ до 224 ГБ](docs/images/io_share.png)

![Оба слагаемых — итоги за весь прогон, и это задача ввода-вывода при любом бюджете](docs/images/eq_io_share.png)```python
# dd is one sequential stream at queue depth 1. The expert path is random
# 17.55 MB O_DIRECT reads, up to 16 outstanding. On network storage they diverge.
SZ = 17547264   # one Kimi K3 routed expert, to the byte
N  = 40         # reads per measurement
for qd in (1, 4, 16):
    measure(path, qd)
```Один результат оптимизации. Переключение арен с 4-КБ страниц на 2-МБ huge pages, измеренное как чистое A/B на одном бинаре через переменную окружения, а не на двух сборках:```text
########## A: 4 KB pages (previous behaviour)
4 tokens in 45.5 s, 11.37 s/token average
  read 153.02 GB in 24.36 s (6282 MB/s)

########## B: 2 MB hugepages (new)
4 tokens in 43.0 s, 10.76 s/token average
  read 153.02 GB in 22.64 s (6758 MB/s)

=== output equality (a speedup that changes tokens is worthless) ===
A: [161427, 11294, 58776, 123595]
B: [161427, 11294, 58776, 123595]
IDENTICAL
```Токены идентичны — первое, что нужно проверить у любой оптимизации. Время улучшилось на 5.4 процента, что уверенно **внутри 33-процентного шумового порога**, так что выигрышем это не заявляется. Механизм работоспособен, а измерение не устанавливает размер эффекта.```c
/* An A/B between two builds compares two binaries. An A/B on one binary
 * compares one decision. */
```## Почему ствол не квантуется

Ствол — это 108.81 ГБ bfloat16. Квантование в int8 уменьшило бы это вдвое, а в int4 — вчетверо. Любой другой движок такой формы предлагает ручку битности. У этого — ровно два типа весов и вообще никакой ручки:```c
enum { K3_WF32 = 0, K3_WBF16 = 1 };
```Причина в том, что цена была измерена. Исследование сэмплировало 31 тензор внимания из релизного чекпоинта через HTTP range-запросы, по 384 строки каждый, квантовало с симметричным построчным масштабированием.

![Симметричное построчное квантование — метод, лежащий в основе исследования int8 и int4](docs/images/eq_absmax.png)```text
  type   tensor                      int8 mean  int4 mean    ratio
  ------------------------------------------------------------------
  KDA    L13.o_proj                    0.01188    0.21122    17.8x
  MLA    L3.kv_b_proj                  0.00736    0.13355    18.2x
  MLA    L11.o_proj                    0.01399    0.24612    17.6x
  ------------------------------------------------------------------
  MEAN over KDA-layer tensors          0.01046    0.18746    17.9x  (n=2)
  MEAN over MLA-layer tensors          0.00948    0.17154    18.1x  (n=18)
  MEAN over ALL sampled tensors        0.00961    0.17383    18.1x  (n=31)
```![Ни один тип слоя не переносит 4 бита сколь-нибудь лучше других](docs/images/quant_by_layer_type.png)

Int8 стоит около одного процента, а int4 — около семнадцати, соотношение 18, которое держится по каждому сэмплированному тензору. И среднее занижает ущерб, потому что хвост куда хуже.

![int8 стоит около 1%, int4 — около 17%, а его худшие строки стоят 65%](docs/images/quant_error.png)

Худшие отдельные строки при int4 достигают 45, 56 и **65 процентов** относительной ошибки. Это не артефакты округления.

Есть и сильный намёк от авторов модели. Технический отчёт говорит, что эксперты — это MXFP4 с quantisation-aware обучением, «пока все не-экспертные компоненты остаются в более высокой точности». Этот список не-экспертных компонентов — ровно этот ствол. Он сознательно не квантовался и никогда не обучался терпеть четыре бита.

![Секунды выкупаются RAM-ом, а ошибка округления — нет, ни при каком бюджете](docs/images/eq_stream_vs_quantize.png)

Безпотерьный поток (lossless stream) стоит секунд на токен, и эти секунды возмещаются, дав движку больше RAM — ровно то, что показала лесенка памяти. Точность, потерянная из-за округления до четырёх бит, не возмещается ни при каком бюджете.

Четыре оговорки, каждая из которых исследование заявляет о себе само: это ошибка реконструкции весов, а не качество вывода; сэмплировалось 384 строки на тензор, а не целые тензоры; покрыты только проекции внимания, без MoE, без эмбеддингов и без выходной головы; и никакого сравнения логитов/токенов на int4 не прогонялось, так что цена качества ограничена, а не измерена.

Сырые данные: [`docs/data/trunk-quantisation.txt`](docs/data/trunk-quantisation.txt).

---

# Часть V: Справочник

## Область применения (Scope)

- **Только текст, чат XTML.** Диалоги K3 система/пользователь/ассистент и их история рассуждений поддерживаются. Инструменты, зрение/изображения, HTTP-сервер и сжатие контекста пока не поддерживаются.
- **Пакетный режим остаётся жадным.** Его выводы остаются идентичными на любых бюджетах памяти. Только чат добавляет опциональные temperature/top-p и `--greedy`.
- **Без чанкованного префилла.** Потолок — 32 768 токенов, но промпт на 21 000 токенов — это один квадратичный проход.
- **Контекст ограничен памятью, а не движком.**

![Заявленный контекст на миллион токенов — факт памяти, а не лимит движка](docs/images/eq_context_ceiling.png)

- **Без зрения.** MoonViT-V2 полностью специфицирован в `config.json` на 27 слоёв, но кода здесь ноль. Отсутствующий энкодер — это 0.057 процента чекпоинта и качается отдельно, что делает его реализацию задачей на 0.9 ГБ, а не на 1.56 ТБ.
- **Без SIMD в рекуррентности KDA.** У matmul есть пути AVX2; рекуррентность — всё ещё скалярный C.
- **Без бенчмарка качества.** Ни перплексии, ни оценок задач. При 11 секундах на токен это дни вычислений, и измерялась бы Kimi K3, а не этот движок.

![Что этот движок не реализует — в масштабе](docs/images/whats_missing.png)

Что дальше, в порядке приоритета: [`ROADMAP.md`](docs/ROADMAP.md).

## Подведение итогов

![От чекпоинта 1.56 ТБ до правильного ответа — на одной машине](docs/images/recap.png)

Каждый параметр в bfloat16 — это 5.56 ТБ. Эксперты уже поставляются по 0.53125 байта на вес, что даёт 1.56 ТБ на диске. Маршрутизация означает, что лишь 16 из 896 экспертов срабатывают на слой, так что 1.45 ТБ из них вообще не обязаны быть в памяти, остаётся 113.49 ГБ. Потоковая подача ствола послойно превращает этот последний порог в регулятор, и регулятор опускается до измеренных **8.24 ГБ**.

Суть была не в скорости. На 8 ГБ токен занимает около полуминуты, и притворяться иначе было бы глупо. Суть в том, что модель помещается, что она выдаёт те же токены на 8 ГБ, что и на 224, и что разрыв между «нужен дата-центр» и «хватит десктопа» — это четыре решения о том, где живут байты, а не какое-либо изменение самой модели.

## Документация

| | |
|---|---|
| [`QUICKSTART.md`](docs/QUICKSTART.md) | настройка выше, сжатая до команд |
| [`ARCHITECTURE.md`](docs/ARCHITECTURE.md) | как модель ложится на код |
| [`PERFORMANCE.md`](docs/PERFORMANCE.md) | лесенка памяти, измеренная, с её шумовым порогом |
| [`TUNING.md`](docs/TUNING.md) | выбор бюджета и разбиения |
| [`BENCHMARKING.md`](docs/BENCHMARKING.md) | как измерять, не обманывая себя |
| [`TESTING.md`](docs/TESTING.md) | что устанавливает каждый гейт |
| [`API.md`](docs/API.md) | C-интерфейс для встраивания движка |
| [`ROADMAP.md`](docs/ROADMAP.md) | область применения и что дальше |
| [`docs/data/`](docs/data/) | вывод измерений; каждая цифра выше транскрибирована оттуда |
| [`docs/images/`](docs/images/) | каждая диаграмма и уравнение, с исходниками mermaid и Python, которые их генерируют |
| [`kimi-k3-tech-report.pdf`](docs/kimi-k3-tech-report.pdf) | технический отчёт модели |

## Разработка

```bash
make test        # the gate that stays green, no weights, no network, no Python
make help        # the documented targets
make asan        # AddressSanitizer and UBSan
make portable    # generic AVX2, without -march=native
```CI прогоняет те же гейты: матрицу GCC и Clang под `-Werror`, санитайзеры поверх парсеров и кэша, полный безвесовой набор и ruff со shellcheck как блокирующие проверки. Фикстуры генерируются из PyTorch-референса и коммитятся; [`tests/fixtures/README.md`](tests/fixtures/README.md) документирует, что делает каждую фикстуру «злой» и как её пересоздать. [`CONTRIBUTING.md`](CONTRIBUTING.md) — место, с которого стоит начать.

## История звёзд

<p align="center">
<a href="https://www.star-history.com/#FareedKhan-dev/kimi-k3-in-c&Date">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=FareedKhan-dev/kimi-k3-in-c&type=Date&theme=dark" />
  <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=FareedKhan-dev/kimi-k3-in-c&type=Date" />
  <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=FareedKhan-dev/kimi-k3-in-c&type=Date" />
</picture>
</a>
</p>

## Лицензия

Apache 2.0 — см. [LICENSE](LICENSE).