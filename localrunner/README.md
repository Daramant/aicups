## Как это всё устроено

`localrunner` является просто `tcp`-сервером, написанным на `python2.7`+`tornado`. При запуске он ждет соединения от двух `tcp-клиентов` со стратегией, после чего отсылаем им команду "начали!" и делает всё, что надо. В конце он отсылаем обоим команду "закончили" и завершается, сбрасывая в `visualizer/game.js` лог игры.  
И сервер, и оба клиента при этом завершают свою работу.

## Как это запустить

### Подготовка

Для успешной работы сервера нужно поставить необходимые пакеты из `world/requirements.txt`. Проще всего сделать это с помощью команды `pip install -r world/requirements.txt`

### Запуск сервера

После этого можно сразу переходить в папку world и запускать `python run.py`. Сервер запустится и будет терпеливо ожидать коннекта от двух стратегий

### Запуск стратегий

Работающая стратегия состоит из `обвязки` и `стратегии`. Стратегия занимается логикой, обвязка же просто запускает стратегию как tcp-клиент.  
Обвязку можно взять из [списка доступных клиентов](../clients/) - берем нужный нам, подкладываем ему внутрь в папку `core` саму стратегию (для начала можно взять baseline [отсюда](../baseline/)).  
Всё, tcp-клиент стратегии готов, можно запускать!  
Таким образом нужно запустить любые две стратегии, они автоматом подконнектятся к tcp-серверу мира и начнут играть. Через некоторое время игра закончится и все три программы (два клиента и один сервер) завершатся, и можно будет посмотреть визуализацию игры.

### Просмотр игры

Реализован просто и топорно - сервер в конце игры пишет все нужные данные в `visualizer/game.js`. Чтобы посмотреть игру, достаточно открыть в браузере `visualizer/index.html`  

## Подробная инструкция для разных клиентов

Крайне приветствуются `pull-request`-ы

### C++ QT


### C#


### Python2


### Python3


### Node.js


### PHP7


### Java1.8
