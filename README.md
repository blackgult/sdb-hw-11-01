# Домашнее задание к занятию «Базы данных, их типы» - Михайлов Дмитрий

---

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? 

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

*Приведите ответ в свободной форме.*

### Решение 1

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных. - На мой взгляд лучше всего подойдёт из теоремы Блюера "СА" (Согласованность данных и Доступность) СУБД, к которым относятся
Реляционные системы управления базами данных, а именно, например: PostgreSQL, MySQL.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? - В этом случае подойдёт Redis. Redis - это база данных, размещаемая в памяти, которая используется,
в основном, в роли кеша, находящегося перед другой, «настоящей» базой данных, вроде MySQL или PostgreSQL. Кеш, основанный на Redis, помогает улучшить производительность приложений.
Он эффективно использует скорость работы с данными, характерную для памяти, и смягчает нагрузку центральной базы данных приложения, связанную с обработкой данных,
которые редко меняются, к которым часто обращается приложение и к данным, не относящимcя к критически важным, но которые часто меняются.

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми. - Для лендингов и CRM можно использовать реляционные СУБД, например: MySQL, PostgreSQL. Реляционые БД нужны для команды аналитиков и Data Science.
Но, для большей производительности, стоит присмотреться к использованию ещё и NoSQL СУБД, например: MongoDB.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией? - Да, можно закрыть задачу используя только одной из реляционных СУБД, например: MySQL, PostgreSQL. 

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру. - Опять же, например, MySQL или PostgreSQL (реляционные СУБД) подойдут.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать? - (У меня нет ответа, это задание со звёздочкой, необязательное.)

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями. - Подойдут NoSQL Графовые СУБД, так как в таком типе СУБД данные хранятся в виде узлов, ребер и свойств.


1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов? - Для них лучше сформировать свою СУБД в связке с СУБД логистов, используя реляционные базы данных (MySQL, PostgreSQL), так как для отдела закупок нужно чётко будет знать и понимать какие товары строительного магазина заказывают, какие клиенты делают заказ, какие грузчики и водители развозят закак, на каких складах хранятся необходимые товары и т.д..

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно? - Думаю что наверное да, можно решить все вышеперечисленные задачи используя только одну из реляционных СУБД, например: MySQL. Но при этом, стоит отметить, что чем больше база данных будет расти, тем в будущем она будет менее отзывчивой в использовании.    

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

*Приведите ответ в свободной форме.*

### Решение 2

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

1. Пользователь вводит номер телефона и сумму пополнения, например в своём банковском приложении на смартфоне.
2. Данные отправляются на сервер банка, где проверяется что такой номер есть и что у пользователя достаточно денег на своём банковском счёте, чтобы пополнить баланс телефона.
3. Если всё в порядке, такой номер телефона существует и денег на счёте достаточно, то сервер оператора сгенерирует уникальный идентификатор транзакции и отправит его обратно пользователю.
4. Пользователь подтверит транзакцию.
5. Банк переведёт деньги мобильному оператору. Деньги спишутся с банковского счёта, но они появятся на балансе счёта телефона.
6. Оператор отправит подтверждение, что баланс телефона пополнен и баланс обновится.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Наверное тут стоит опустить тот факт, что пользователь до этого уже подключил автоплатёж))) Пользователь уже на этапе настройки автоплатежа ввёл номер телефона и ежемесячную сумму пополнения.
Какой сегодня день? Если сегодня не день автоплатежа, то деньги не спишутся. Но, мы представим, что сегодня тот самый день, день "ИКС" - день автоплатежа. Что произойдёт дальше?

2. Данные уже сохранены и находятся на сервере банка, но опять проверяется что такой номер есть (мало ли, что могло поменяться за месяц) и что у пользователя достаточно денег на своём банковском счёте, чтобы пополнить баланс телефона.
3. Если всё в порядке, такой номер телефона существует и денег на счёте достаточно, то сервер оператора сгенерирует уникальный идентификатор транзакции и отправит его серверу банка.
4. Сервер банка скажет "ОК", пользователь дал согласие на то, что деньги будут списываться раз в месяц, так что бери деньги.
5. Банк переведёт деньги мобильному оператору. Деньги спишутся с банковского счёта, но они появятся на балансе счёта телефона.
6. Оператор отправит подтверждение, что баланс телефона пополнен и баланс обновится.

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

*Приведите ответ в свободной форме.*

### Решение 3

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 


Различия в языке
Одно из основных отличий между SQL и NoSQL - используемый язык. SQL язык структурированных запросов к структурированным данным. NoSQL - это новая система баз данных, которая не использует стандартный язык запросов, а использует документы JSON для хранения данных. 


Масштабируемость и производительность
Базы данных SQL используют горизонтальную масштабируемость, которая включает в себя сегментирование, при котором таблицы делятся на более мелкие разделы и распределяются по нескольким серверам. 
В конечном счете, эффективность используемых структур данных может существенно повлиять на масштабируемость больше, чем различия между базами данных SQL и NoSQL.

Структурные различия
Базы данных SQL и NoSQL имеют совершенно разные свойства и структуры. База данных SQL - это табличный формат, который чем-то похож на электронную таблицу Excel, где каждая строка представляет собой запись в базе данных, а каждый столбец -это поле данных. Связи между полями данных устанавливаются таблицами в базе данных. Базы данных NoSQL активно хранят данные в виде документов, представляющих собой записи, состоящие из наборов ключей или свойств со значениями. Они обладают более гибкой структурой, которая позволяет хранить связанные элементы вместе, не требуя создания таблиц, как это необходимо в базе данных SQL.
Базы данных SQL более строги в использовании предопределенных схема, что ускоряет их использование в транзакционных приложениях. Напротив, базы данных NoSQL не имеют предопределенной схемы. Их можно легко адаптировать к различным типам наборов данных, что делает их идеальными для больших наборов данных и аналитика в реальном времени.

Свойства базы данных
Каждый тип базы данных имеет свой собственный набор свойств, которые делают его подходящим для определенных случаев использования. Базы данных SQL соответствуют свойствам ACID (атомарность, согласованность, изоляция и долговечность), которые гарантируют точность и надежность обработки транзакций. Напротив, базы данных NoSQL следуют теореме CAP (согласованность, доступность и толерантность разделов), подчеркивая доступность и устойчивость разделов над согласованностью.

Поддержка и сообщества
Из-за своей популярности и того факта, что SQL существует с 1970-х годов, SQL имеет более широкую поддержку и большее сообщество. Следовательно, найти опытных специалистов, умеющих работать с SQL, может быть проще, чем найти тех, кто имеет опыт работы с базами данных NoSQL.
С другой стороны, многие базы данных NoSQL имеют открытый исходный код или являются проприетарными и содержат множество ценной документации.




3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.  - (У меня нет ответа, это задание со звёздочкой, необязательное.)

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

*Приведите ответ в свободной форме.*

### Решение 4

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?


---
