# BybitSpot
Trading bot for exchange Bybit

Бот для спот торговли на криптобирже Bybit (аналог BinSpot-19).    
Бот работает только на стандартном торговом аккаунте (не на едином торговом аккаунте).     
Можно выбирать реальную или тестовую биржу (https://testnet.bybit.com/).   

Запуск бота на VPS с ubuntu
1. Подключаемся к серверу и по умолчанию находимся в корневом каталоге.
2. Создаем новую папку (например, с именем BybitSpot) командой:  
mkdir BybitSpot
3. Создаём новую screen-сессию (назовем, например, тоже BybitSpot) для  бота командой:  
screen -S BybitSpot
4. Заходим в папку BybitSpot командой:  
cd BybitSpot
5. Скачиваем бота в папку BybitSpot командой:  
wget https://github.com/ebot732/BybitSpot/releases/download/BybitSpot-19/BybitSpot-19
6. Даём права на запуск бота командой:  
chmod 755 BybitSpot-19
7. Запускаем  бота командой:  
./BybitSpot-19  
и следуем подсказкам.
8. Выходим из работающего screen, не прерывая его работу, командой:  
ctrl+a, d (при нажатой ctrl жмем а, отпускаем их, и затем жмем d)

Далее, чтобы зайти в screen работающего бота, введите команду:  
screen -x BybitSpot  
То есть, второй раз вводить  
screen -S BybitSpot   
не нужно, а то создастся еще одна screen-сессия.
