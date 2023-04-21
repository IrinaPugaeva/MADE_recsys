# Рекомендательные Системы в Продакшене

## Лекции

Слайды лекций лежат в папке [slides](slides).

## Практика

Практическая часть курса построена вокруг музыкального рекомендера **botify**. 
На семинарах и в домашке мы будем развивать и анализировать этот рекомендер.

### Prerequisites

- Установить docker
- Сделать virtualenv c python (я использую версию 3.7)
- Вспомнить как пользоваться вашей любимой средой разработки (я использую PyCharm)

### Общее описание задачи

Пользователи приходят в музыкальный сервис **botify**, чтобы послушать музыку.
Сперва пользователь сам выбирает начальный трек.
Когда пользователь прослушал этот трек, сервис рекомендует следующий.
Пользователь может послушать рекомендованный трек или скипнуть его и перейти к следующему.
Либо пользователю может надоесть и он уйдет.
Как поступит пользователь зависит от качества рекомендаций: если они плохие - пользователь быстро уйдет; если хорошие – "залипнет".
Последовательность прослушанных пользователем треков мы будем называть "сессией".
На диаграмме ниже показан процесс одной сессии.  

![Взаимодействие пользователя с рекомендером botify](user-flow.png)

Цель сервиса **botify** – максимально долго удерживать пользователя.
Возможно, мы зарабатываем на рекламе или просто хотим набрать аудиторию.
Сервис меряет процент прослушки каждого трека из сессии и суммирует эти проценты, чтобы получить общую длину сессии (пренебрегаем тем, что треки могут длиться разное время – обычно песни длятся около 3 минут).
Качество рекомендаций напрямую влияет на то, сколько треков послушают пользователи и какой будет процент их прослушки.
Следовательно качество рекомендаций влияет на длину сессии и на успех всего сервиса в целом.

### Что есть в репозитории

#### botify

В этом модуле лежит заготовка сервиса рекомендера. 
В рамках заданий работать нужно будет над кодом из этого модуля.

[Описание и инструкции](botify/README.md)

#### sim

Так как наш рекомендер учебный, он не развернут для реальных пользователей. 
Но мы хотим экспериментировать с рекомендером как с настоящим.
Для этого в модуле sim реализован симулятор пользователя.
Запуская симулятор, мы генерируем трафик, похожий на трафик, который генерируют реальные пользователи.

[Описание и инструкции](sim/README.md)

#### jupyter

Ноутбуки с подготовкой данных для симулятора, визуализацией и всем таким.


