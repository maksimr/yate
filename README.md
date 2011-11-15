Yet Another Template Engine
============================

Бла-бла-бла
-----------

  * Хочется заменить шаблонизатор в Я.Почте.
    Сейчас это xslt, исполняющийся на клиенте.

  * Как минимум новые шаблоны должны уметь компилироваться в javascript и
    работать с даннымми в формате json, превращая их в html.

  * Не исключается также компиляция и в другие языки. Например, в perl.

  * Шаблонизатор должен быть быстрым.
    Поэтому синтаксис и набор фич ограничивается в первую очередь
    возможностью компиляции в быстро работающий javascript.

  * Шаблонизатор не должен никаким образом модифицировать входящие данные.

  * Синтаксис не должен быть xml'ным,
    но общие принципы xslt (pattern matching шаблонов, xpath) должны сохраниться.


Building and Installing
-----------------------

  * Установить [node.js](https://github.com/joyent/node/wiki/Installation).

  * Запустить в корне проекта скрипт `make.sh`. Эта команда сгенерит в корне же файл yatelib.js.
    Необходимо так же запускать этот скрипт после любых изменений в `src/*`.

  * Компиляция шаблона запускается так:

        ./yate test.yate > test.js

  * Компиляция и исполнения шаблона:

        ./yate test.yate test.json > test.html

  * В папке examples/mailbox есть довольно развесистый пример:

        cd examples/mailbox
        ./make.sh

    Файл `mailbox.js.html` — это результат наложения шаблона "на сервере", а `mailbox.html` — на клиенте.

