# Часто задаваемые вопросы (FAQ)

[TOC]

## Основные вопросы

##### **Что такое NEO？**

NEO - это распределенная сеть, которая использует технологию blockchain и цифровую идентификацию для оцифровки активов и автоматизации управления цифровыми активами с использованием смарт-контрактов. Сеть NEO имеет два токена, NEO представляет право на управление NEO blockchain и GAS представляет право на использование NEO Blockchain.

##### **Какие сообщества разработчиков есть у NEO?**

NEO имеет большое количество распределённых по миру сообществ разработчиков, которые в течение длительного времени вносят свой вклад в развитие NEO. Ниже приведены некоторые репрезентативные сообщества:

- **CoZ**，самое раннее сообщество разработчиков в экосистеме NEO: https://github.com/CityOfZion
- **NEL**，первое китайское сообщество разработчиков в экосистеме NEO: https://github.com/NewEconoLab
- **NeoResearch**，южноамериканское сообщество разработчиков：https://github.com/NeoResearch
- **NSPCC**，Российское сообщество разработчиков, г. Санкт-Петербург：https://www.nspcc.ru/en/
- **KeyMakers**，японское сообщество разработчиков：https://github.com/keymakers

##### **Что такое GAS？Как приобрести GAS？**

GAS представляет собой право на использование блокчейна Neo. Сеть NEO взимает GAS за выдачу новых активов, а также за выполнение и хранение смарт-контрактов. В блоке генезиса (genesis block) GAS равен 0 и генерируется по мере генерации новых блоков. Как только NEO приобретен, GAS создаётся в системе согласно алгоритмам. GAS имеет два статуса, доступен и недоступен. Как только NEO израсходован (т. е. переведен) со счета, соответствующий GAS становится доступным. Держатели NEO могут в любое время инициировать запрос на получение доступного GAS'а на адрес NEO.

##### **Могу ли я перевести газ на свой счет, чтобы сделать его востребованным?** 

Да. Вы можете сделать это, даже если в вашем кошельке есть только один адрес.

##### **Какие алгоритмы консенсуса использует NEO?**

NEO использует делегированный византийский алгоритм отказоустойчивости (dBFT), который обеспечивает 𝑓 = ⌊ (𝑛−1) / 3 ⌋ отказоустойчивость к консенсусной системе, состоящей из n узлов. 

Существует два типа узлов в этом механизме, обычный узел и узел консенсуса. Обычные узлы голосуют за консенсусные узлы на основе доли принадлежащих им NEO. Когда необходимо принять консенсус, лидер выбирается случайным образом, чтобы принять решение по предложению, а затем другие узлы консенсуса голосуют в соответствии с алгоритмом dBFT. Если более 2/3 узлов согласны с предложением, в таком случае достигается консенсус; в противном случае лидер переизбирается и процесс голосования повторяется.

##### **Как стать узлом консенсуса NEO? Есть ли какие-то поощрения?**

Узлы консенсуса NEO избираются держателями NEO. Для получения дополнительной информации см. https://neo-ngd.github.io/reference/How-To-Become-NEO-Consensus-Node.html

**Какие браузеры доступны для блокчейна NEO?**

Вы можете перейти на http://ndapp.org/ и найти все браузеры, перечисленные во вкладке Explorer.

**В чем разница между обычными активами и активами NEP-5?**

NEO имеет два типа активов. Один из них-глобальные активы, которые управляют активами с помощью модели UTXO. Другой актив - это NEP-5, который управляет активами с использованием балансовой модели. Как NEO, так и GAS являются активами UTXO, которые можно торговать напрямую. NEP-5 является активом контракта, который торгуется путем вызова смарт-контракта. Вы можете использовать NEO-GUI для регистрации и выпуска нового ресурса UTXO. Создать новый NEP-5 актив можно путём написания смарт-контракта.

##### **Как просмотреть активы NEP-5 в NEO-CLI?**

В NEO-CLI вы можете просмореть список UTXO активов используя `list asset`. Для просмотра NEP-5 активов необходимо вызвать API-метод `getbalance`.

**В чём разница между NEP-5 и NEP-6？**

NEP-5 это стандарт токенов которые создаются с использованием NEO смарт контрактов. NEP-6 - это стандарт кошелька, который определяет формат кошелька, его параметров, а так же правила создания адреса кошелька и т.д. NEP-6 применим к нескольким текущим версиям клиента NEO, начиная с 2.7.6. Клиент NEO поддерживает кошельки в двух форматах, кошелёк SQLite (в формате .db3) и кошелёк NEP-6 (в формате .json). Учитывая скорость обработки, кошелек sqlite настоятельно рекомендуется для использования.

## Клиенты

##### **Почему я не увидел никаких изменений в учетной записи после того, как я перевел активы на нее с помощью NEO-GUI?**

Для начала, проверьте список транзакций в NEO-GUI, чтобы убедиться, была ли подтверждена ваша транзакция. Если подтверждение получено, то проверьте, что ваш клиент был синхронизирован до последнего блока и перестроен индекс кошелька, в случае, если проблема все еще существует.

##### **Why doesn't the downloaded offline package work?**

Read the instructions at http://docs.neo.org/ru-ru/network/syncblocks.html and make sure the following:

- You have downloaded the proper package
- You have directly placed the downloaded file (chain.0.acc.zip or chain.xxx.acc.zip) under the root directory of NEO-CLI or NEO-GUI without modifying the file name
- You have installed the [ImportBlocks](https://github.com/neo-project/neo-plugins/releases/download/v2.9.0/ImportBlocks.zip) plugin.

##### **Как узнать, что мой клиент полностью синхронизирован?**

Используйте blockchain браузер, чтобы проверить номер последнего блока, а затем посмотрите номер последнего блока в вашем клиенте кошелька. Если номера блоков одинаковы, значит клиент полностью синхронизирован.

##### **How to make a watch-only wallet？**

In NEO-CLI create a new address, then right-click to import the watch-only address and enter the address you want to monitor. Then you can see each transaction information in the transaction record. You need to rebuild the wallet index after importing the address.

##### **Можно ли перевести активы на несколько адресов за одну транзакцию?**

Да. См. раздел [транзакции](node/gui/transc.md).

##### **Каковы требования к аппаратному обеспечению компьютера, на котором работает NEO node в основной сети?**

A dual-core CPU, 8G memory, and a solid state drive with a minimum of 100G or more are required. The hard disk needs to be expanded on demand to prevent the inode from overflowing.

##### **Можно ли запустить NEO-CLI в фоне?**

Вы можете написать скрипт с помощью Nodepad в Windows, со следующим содержимым `dotnet neo-cli.dll /rpc` и сохранить его с расширением .cmd или используя утилиту `screen` в ОС Linux.

## Разработка

##### **Как получить токены в testnet?**

Перейдите по ссылке https://neo.org/testcoin/apply и сделайте запрос. После того как запрос будет одобрен, вы будете уведомлены в течении пяти рабочих дней.

##### **Как настроить приватную сеть?**

Чтобы настроить приватную сеть, вы можете воспользоваться следующими инструкциями:

- используя виртуальную машину для создания приватной сети в вашем облаке, см. [здесь](network/private-chain/private-chain.md).
- быстрая настройка приватной сети на Windows сервере, см. [здесь](network/private-chain/private-chain2.md).
- быстрая настройка приватной сети с помощью neo-local, см. [здесь](network/neolocal.md).

Вы также сможете следовать [инструкции сообщества](http://docs.neo.org/communitydoc.html) чтобы узнать больше подробностей.

##### **Какие языки можно использовать для разработки смарт-контрактов?**

NEO поддерживает множество основных языков программирования и может быть разработан с использованием C#, Python, Go, JS и Java. В настоящее время в экосистеме NEO инфраструктура для C# и Python чрезвычайно хорошо развита, и разработчикам предоставляются различные компиляторы.

**Как я могу получить TXID активов NEP-5?**

В настоящий момент мы рекомендуем использовать браузер блокчейна https://scan.nel.group , который позволяет просматривать TXID активов NEP-5.

1. В браузере щелкните кнопкой мыши по Assets в верхней панели навигации.
2. В выпадающем списке Assets выберите NEP-5.
3. Щелкните кнопкой мыши по необходимому активу, чтобы увидеть его TXID на появившейся странице с подробной информацией.

**Почему при выводе активов из контракта с многопользовательской подписью, для которого требуется как минимум 3 подписи, появляется сообщение о том, что в кошельке нет закрытого ключа объекта?**

После настройки частной цепи необходимо также произвести одинаковую настройку всех четырех кошельков, то есть добавить адреса с многосторонней подписью, а затем обновить индекс кошелька.

## Смарт-контракт

**Почему при попытке опубликовать neon появляется сообщение о том, что пакет NuGet не может быть восстановлен? Проблема возникает даже тогда, когда я использую Visual Studio 2017.**

Для решения данной проблемы:

1. Загрузите nuget.exe [отсюда](https://www.nuget.org/downloads) и разместите его в корневом каталоге проекта neo-compiler.
2. Запустите Power Shell или командную строку (CMD)
3. Перейдите в корневой каталог neo-compiler и запустите `nuget restore` .

**Почему neon.dll не может быть скопирован при публикации проекта neon?**

Данная проблема может быть вызвана ошибкой VS 2017. В некоторых версиях VS 2017 (например, 15.4, 15.5) возможно появление следующей ошибки:

Невозможно скопировать "obj\Release\netcoreapp1.0\win10-x64\neon.dll", поскольку файл не может быть найден.

Чтобы решить данную проблему, вы можете вручную скопировать файл `\obj\Release\netcoreapp1.0\neon.dll` в каталог `\obj\Release\netcoreapp1.0\win10-x64\`, а затем опубликовать его повторно.

**Почему пространства имен NEO нет в только что созданном проекте NeoContract?**

После создания проекта NeoContract в коде появляется много красных подчеркиваний, указывающих на то, что пространство имен NEO не найдено, при этом в ссылке на данный проект можно увидеть восклицательный знак.

Чтобы решить данную проблему, щелкните правой кнопкой мыши по файлу решения в Visual Studio, а затем щелкните по `restore NuGet package`. Если после успешного восстановления всех пакетов ситуация не изменилась, а в References в правой панели все еще можно увидеть восклицательный знак, щелкните по нему дважды, чтобы понять, в чем проблема, и решить ее.

Если вы все-таки не смогли решить данную проблему, попробуйте воспользоваться следующими вариантами:

1. Скачайте nuget.exe [отсюда](https://www.nuget.org/downloads) и разместите его в корневом каталоге проекта NeoContract.
2. Запустите Power Shell или командную строку (CMD) 
3. Перейдите в корневой каталог NeoContract и запустите `nuget restore`.

**Почему, когда я запускаю neon, опубликовав его в Windows 7 и установив переменную среды, появляется сообщение о том, что api-ms-win-core-console-l2-1-0.dll отсутствует?**

Это объясняется настройкой системы публикации. Поскольку win 10-x64 по умолчанию является системой публикации для проекта neon, то, когда вы публикуете neon в Windows 7, появляется сообщение об отсутствующем файле .dll.

Чтобы решить данную проблему, отредактируйте файл neon.csproj и замените `<RuntimeIdentifiers>win10-x64</RuntimeIdentifiers>` на `<RuntimeIdentifiers>win7-64</RuntimeIdentifiers>`. Затем повторно опубликуйте проект в Visual Studio (или с помощью команды `dotnet publish -r win7-x64 -c debug`).

Дополнительную информацию по RID см. в [.NET Core Runtime IDentifier (RID) catalog](https://docs.microsoft.com/en-us/dotnet/core/rid-catalog) .

Вы также можете скачать этот файл и скопировать его в каталог neon.exe (однако мы не рекомендуем данный способ по причине возможных проблем с безопасностью).

**Почему я не могу найти neon в CMD после того, как задал переменную среды?**

Это объясняется тем, что вы не перезапустили CMD после того, как изменили переменную среды. CMD продолжает считывать параметры, измененные до этого момента. Чтобы решить данную проблему, перезапустите CMD.

**Почему после публикации neon и добавления каталога neon.exe в путь компилирование NeoContract зависает на шаге «Start NeoContract converter»**

Это вызвано тем, что вы не перезапустили Visual Studio после изменения переменной среды. Visual Studio продолжает считывать переменную среды, измененную до этого момента.

Чтобы решить данную проблему, перезапустите Visual Studio. Если проблема не исчезла, перезагрузите вашу систему. 

**Почему смарт-контракт, согласующийся со старой версией neon, не работает в тестовой и главной сетях?**

Смарт-контракты NEO требуют того, чтобы фреймворк разработки, компилятор и версии NEOVM были совместимы друг с другом. Код, скомпилированный со старым фреймворком и компилятором, может не работать в новой версии NEOVM. Однако все это не влияет на смарт-контракты, уже опубликованные в блокчейне. Поэтому, прежде чем приступить к разработке смарт-контракта, убедитесь в том, что вы используете последние версии фреймворка (например, NeoContractPlugin) и компилятора (например, neon).

Некоторые части данной статьи взяты из  [NEO Contract Development - Common Pitfalls using Windows 7](https://steemit.com/neo/@cybourgeoisie/neo-contract-development-common-pitfalls-using-windows-7). Спасибо за вклад **cybourgeoisie**.

Если у вас по-прежнему возникают проблемы, или вы не можете найти актуальный для вас вопрос, то вы можете открыть Issues или Pull requests на [GitHub NEO Doc project](https://github.com/neo-project/docs).