<!-- verified: agorbachev 03.05.2022 -->

<!-- 17.6.1 -->
## Основные подходы к поиску и устранению неполадок

В предыдущих двух разделах вы узнали о некоторых утилитах и командах, которые можно использовать для определения проблемных областей в сети. Это важная часть устранения неполадок. Существует множество способов устранения неполадок в сети. В этом разделе подробно описывается структурированный процесс, который поможет вам стать лучшим сетевым администратором. Он также предоставляет несколько дополнительных команд, которые помогут вам решить проблемы.

Неполадки сетей бывают простыми и сложными. Они могут возникать из-за проблем с оборудованием, программным обеспечением и подключениями. Технические специалисты должны уметь проанализировать неполадку и определить причину ошибки, чтобы исправить ее. Этот процесс и называется **поиском и устранением неполадок**.

Общепринятая эффективная процедура поиска и устранения неполадок основана на научном подходе и состоит из шести этапов.

| Шаг | **Описание** |
| --- | --- |
| **Шаг 1. Определение неполадки** | <ul><li>Первый шаг в процессе поиска и устранения неполадок. </li><li>На этом этапе можно использовать различные методы, в том числе, расспросить пользователя, что может оказаться очень полезным.</li></ul> |
| **Шаг 2. Формирование предположений о возможных причинах неполадки** | <ul><li>После того, как проблема определена, попробуйте выстроить теорию о возможной причине. </li><li>Обычно на этом этапе выявляется несколько возможных причин проблемы.</li></ul> |
| **Шаг 3. Проверка предположений о причине неполадки** | <ul><li>Основываясь на вероятных причинах, проверьте свои теории, чтобы определить, какие из них могли быть верными. </li><li>Технический специалист может попытаться устранить неполадку, применив быструю процедуру, это решает проблему. </li><li>Если быстрая процедура не устранила проблему, может потребоваться дальнейшее ее изучение, чтобы установить точную причину.</li></ul> |
| **Шаг 4. Разработка плана действий для решения проблемы и его реализация** | После того, как вы определили точную причину проблемы, составьте план действий для ее решения и внедрите его. |
| **Шаг 5. Полная проверка функционального состояния сети и принятие профилактических мер** | <ul><li>После устранения неполадки выполните полную проверку функционального состояния системы.</li><li>При необходимости примите профилактические меры во избежание повторения проблемы в будущем.</li></ul> |
| **Шаг 6. Документирование полученных данных, принятых мер и результатов** | <ul><li>На последнем этапе процедуры поиска и устранения неполадок выполняется документирование полученных данных, совершенных действий и результатов. </li><li>Эта информация очень важна для использования в будущем.</li></ul> |

Для оценки неполадки необходимо определить количество устройств в сети, на которых она возникла. Если проблема выявлена только на одном устройстве в сети, начните процесс поиска и устранения неполадок на нем. Если проблема коснулась всей сети, начните поиск и устранение неполадок на устройстве, к которому подключены все остальные устройства. Вы должны разработать логичную и последовательную процедуру диагностики сетевых неполадок, устраняя каждую из них по очереди.

<!-- 17.6.2 -->
## Что следует сделать: решить проблему или эскалировать ее?

В некоторых случаях проблему невозможно устранить сразу. Если требуется решение руководителя, нужны особые знания или у технического специалиста нет нужного уровня доступа к сети, проблему необходимо эскалировать.

Например, осуществив поиск неполадок, технический специалист может прийти к выводу, что нужно заменить модуль роутера. Эту проблему необходимо эскалировать, чтобы руководитель утвердил решение. Он может передать проблему дальше, поскольку для покупки нового модуля может требоваться одобрение финансового отдела.

В политике компании должно быть четко указано, в каких случаях и каким образом технический специалист должен эскалировать проблемы.

<!-- 17.6.3 -->
## Команда debug

Процессы, протоколы, механизмы и события IOS генерируют сообщения для индикации их состояния. Эти сообщения могут оказаться ценным источником информации при поиске и устранении неполадок, а также при проверке работы системы. Команда **debug** в IOS позволяет администратору отобразить эти сообщения в реальном времени для анализа. Эта команда играет очень важную роль в мониторинге событий на устройстве Cisco IOS.

Все команды **debug** вводятся в привилегированном режиме EXEC. Cisco IOS позволяет ограничить выходные данные команды **debug** и включать в них только нужные функции или подфункции. Это очень важно, поскольку отладке присваивается высший приоритет среди процессов ЦП, и она способна привести к невозможности использования системы. Поэтому команду **debug** следует использовать только для устранения конкретной проблемы.

Для контроля состояния сообщений ICMP роутера Cisco используется команда **debug ip icmp**, как показано на рисунке.

```
R1# debug ip icmp
ICMP packet debugging is on
R1#
R1# ping 10.1.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R1#
*Aug 20 14:18:59.605: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.606: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.608: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.609: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
*Aug 20 14:18:59.611: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
R1#
```

Чтобы отобразить краткое описание всех параметров команды отладки, введите в командной строке команду  **debug ?** в привилегированном режиме EXEC.

Чтобы выключить определенную функцию отладки, добавьте перед командой **debug** ключевое слово **no**:

```
Router# no debug ip icmp
```

Кроме того, можно ввести команду **undebug** в привилегированном режиме EXEC:

```
Router# undebug ip icmp
```

Чтобы одновременно выключить все активные команды debug, используйте команду **undebug all**:

```
Router# undebug all
```

Будьте осторожны, используя какую-либо из команд **debug**. Некоторые команды отладки, например, **debug all** и **debug ip packet**, генерируют большое количество выходных данных и задействуют значительную часть системных ресурсов. Роутер может оказаться настолько занят отображением сообщений **debug**, что у него не останется вычислительной мощности для выполнения своих основных сетевых функций или даже для восприятия команд отключения отладки. По этой причине настоятельно не рекомендуется использовать эти параметры команды.

<!-- 17.6.4 -->
## Команда terminal monitor

Соединения для предоставления доступа к интерфейсу командной строки IOS могут устанавливаться двумя вариантами.

* **Локально** — для выполнения локального подключения требуется физический доступ к роутеру или коммутатору по кабельному соединению.
* **Удаленно** — удаленные подключения требуют использования Telnet или SSH для установки подключения к устройству, настроенному на IP.

Некоторые сообщения IOS автоматически отображаются на консольном соединении, но не на удаленном. Например, выходные данные **debug** отображаются по умолчанию на консольных соединениях, но не показываются автоматически на удаленных соединениях. Это связано с тем, что сообщения **debug** являются сообщениями системного журнала, которые не могут отображаться на vty-строках.

Например, в следующих выходных данных пользователь установил удаленное подключение с помощью Telnet от R2 до R1, а потом выдал команду **debug ip icmp**. Однако вывод команды **debug** не отобразился.

```
R2# telnet 209.165.200.225
Trying 209.165.200.225 ... Open
 Authorized access only!
User Access Verification
Password:
R1> enable
Password:
R1# debug ip icmp
ICMP packet debugging is on
R1# ping 10.1.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R1#
! No debug output displayed
```

Чтобы включить отображение сообщений журнала на терминале (виртуальной консоли), используйте команду **terminal monitor** в привилегированном режиме EXEC. Чтобы отключить его, используйте команду **terminal no monitor** в привилегированном режиме EXEC.

Например, обратите внимание, как теперь была введена команда **terminal monitor** и команда **ping** отображает вывод **debug**. 

```
R1#  terminal monitor
R1# ping 10.1.1.1
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms
R1#
*Aug 20 16:03:49.735: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
**Aug 20 16:03:49.737: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
**Aug 20 16:03:49.738: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
**Aug 20 16:03:49.740: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
**Aug 20 16:03:49.741: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0
R1# no debug ip icmp
ICMP packet debugging is off
R1#
```

**Примечание.** Цель команды **debug** состоит в том, чтобы захватить живой выход в течение короткого периода времени (т.е. от нескольких секунд до минуты или около того). Всегда необходимо отключать команды **debug**, когда они больше не требуются.

<!-- 17.6.5 -->
<!-- quiz -->

