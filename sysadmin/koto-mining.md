# CPU Майнинг KOTO через Docker

Ниже заметки, касательно KOTO и `yescrypt`, но используя `cpuminer-multi` майнятся и другие монеты

![yescrypt-cpu-mining](https://blog.amd-nick.me/content/images/2018/07/yescrypt-cpu-mining.png)

`docker run --rm defaced/cpuminer-multi --algo yescrypt --url stratum+tcp://koto.litepool.ru:3032 --user k1FQS7Q2XxaWWLjLdFXFJfG7cQq74mWsZph`\
Можно заменить адрес пула и кошелька

### Установка без Docker <a href="#docker" id="docker"></a>

Требуется Debian based OS\*

Установка зависимостей\
`sudo apt install git build-essential libcurl4-openssl-dev autotools-dev automake`

Скачиваем майнер\
`git clone https://github.com/KotoDevelopers/cpuminer-yescrypt.git koto-miner ; cd koto-miner`

Устанавливаем\
`./autogen.sh`\
`./configure`\
`make`

Запускаем (В -u кошелек)\
`./minerd -a yescrypt -o stratum+tcp://koto.litepool.ru:3032 -u k1FQS7Q2XxaWWLjLdFXFJfG7cQq74mWsZph`

### Статистика <a href="#undefined" id="undefined"></a>

Наблюдать за своими воркерами можно по ссылке:\
[http://koto.litepool.ru:8080/workers/k1FQS7Q2XxaWWLjLdFXFJfG7cQq74mWsZph](http://koto.litepool.ru:8080/workers/k1FQS7Q2XxaWWLjLdFXFJfG7cQq74mWsZph)\
Нужно только заменить адрес кошелька на свой.

![koto-litepool-stats](https://blog.amd-nick.me/content/images/2018/07/koto-litepool-stats.png)

Если есть несколько воркеров (aka rigs), то его имя можно указать через точку после адреса при запуске майнера: `--user ADDRESS.rigname`

#### Subscribe to Блог \_AMD\_

Get the latest posts delivered right to your inbox

**Great!** Check your inbox and click the link to confirm your subscription.

Please enter a valid email address!
