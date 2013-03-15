С чего начать
=============

Установка
---------

    npm install yate


Пишем шаблон
------------

Файл `hello.yate`:

    module "hello"

    match / {
        "Hello, { .username }"
    }

Строчка `module "hello"` должна быть первой строчкой в файле.

Компилируем шаблон
------------------

    yate hello.yate > hello.js

Выполняем шаблон
----------------

### В браузере

    <!-- Подключаем рантайм. -->
    <script src="node_modules/yate/lib/runtime.js"></script>

    <!-- Подключаем шаблон. -->
    <script src="hello.js"></script>

    <script>
    //  Данные для наложения шаблона.
    var data = { username: 'nop' };

    //  Запускаем шаблонизатор:
    var result = yr.run('hello', data);

    console.log(result); // 'Hello, nop'
    </script>

Что такое 'hello' тут --- это название модуля.
Если в шаблоне не указать явно название модуля, то будет использоваться дефолтное: 'main'.


### В node.js

    //  Подгружаем рантайм.
    var yr = require('yate/lib/runtime.js');

    //  Подгружаем шаблон.
    require('./hello.js');

    var data = { username: 'nop' };
    var result = yr.run('hello', data);

    console.log(result); // 'Hello, nop'

