# Домашнее задание к занятию «Базы данных, их типы»

### Инструкция по выполнению домашнего задания


---

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

- реляционная 

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? 

- redis

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

- NoSQL, зависит от масштабности проекта. вероятнее Clickhouse, Verica...

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать?

- NoSQL иерархоческую/доуентно-ориентированную

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.
1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов?

- NoSQL графовую. лучше свою, т.к. для закупок скорее иерархоческая/докуентно-ориентированная

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?
*Приведите ответ в свободной форме.*

- из-за деталей скорости проблематично, но на небольших данных можно использовать правильно структурированную и настроенную реляциюнную

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

acid(атомарность, согласованность, изоляция,долговечность):  
 
 0) *крон таймер
 1) запросе на списание
 2) проверка достаточности средств
 3) списание средств
 4) проверка возможности о передаче средств цели
 5) передача средств

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.


высокая надежность, постгрес - кластеризация, широкая поддержка большинством приложений, поддержка транзакций, относительная кнификация друг с другом (язык запросов), четкие требования к данным

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

База данных способная горизонтально масштабироваться, обеспечивающая надежность, администрирование пользователей, гибкую настройку, надежную работу, логирование и сохранность данных, репликацию, стабильная (долго на рынке).
Подойдет реляционная бд

---

Задания,помеченные звёздочкой, — дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже разобраться в материале.
