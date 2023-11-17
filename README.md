# BybitSpot
Trading bot for Bybit exchange.     
При регистрации на бирже по рефссылке использование бота бесплатное.    
( реф ссылка для регистрации: https://www.bybit.com/invite?ref=8E183W )

Бот для спот торговли на криптобирже Bybit (аналог BinSpot-21).    
Бот работает только на стандартном торговом аккаунте (не на едином торговом аккаунте).     
Можно выбирать реальную или тестовую биржу (https://testnet.bybit.com/).    
   Бот может работать в одном из 4-х режимов:
1.  Режим стандартный- перебор пар для выбора подходящей по всем заданным условиям: 
  - объем торгов за 24 часа в USDT больше указанного в настройках;
  - объем торгов последней свечи или предпоследней больше объема выбранной дальней свечи на %, указанный в настройках;
  - изменение текущей цены по отношению к цене открытия дальней свечи:
    с подрежимом delta_start1- при LONG рост цены больше, чем на указанный %,
                             - при SHORT падение цены еще больше, чем на указанный %,
    с подрежимом delta_start2- при LONG падение цены еще больше, чем на указанный %,
                             - при SHORT рост цены больше, чем на указанный %.
  
2. Режим super_asset: бот работает с парой без каких-либо условий до отключения.

3. Режим control_auto: выбор подходящей пары заданным условиям стандартного режима и работа с ней до истечения указанного таймера от старта позиции в этом режиме, или достижения стоп_цены (изменения на указанный % от цены старта).

4. Режим most_changed- перебор пар для выбора подходящей по следующим условиям: 
  - объем торгов за 24 часа в USDT больше указанного в настройках,
  - курс пары за последние 24 часа изменился в заданном коридоре (с выбором ближе к максимальному или минимальному значению коридора).
  
    Режимы super_asset и control_auto взаимоисключающие, т.е. при выборе одного другой режим отключаются. Если не выбран ни один из режимов, бот будет работать в стандартном режиме.
Подробнее смотри в описании BinSpot.
    
Запуск бота на VPS с ubuntu
1. Подключаемся к серверу и по умолчанию находимся в корневом каталоге.
2. Создаем новую папку (например, с именем BybitSpot) командой:  
mkdir BybitSpot
3. Создаём новую screen-сессию (назовем, например, тоже BybitSpot) для  бота командой:  
screen -S BybitSpot
4. Заходим в папку BybitSpot командой:  
cd BybitSpot
5. Скачиваем бота в папку BybitSpot командой:  
wget https://github.com/ebot732/BybitSpot/releases/download/BybitSpot-21/BybitSpot-21
6. Даём права на запуск бота командой:  
chmod 755 BybitSpot-21
7. Запускаем  бота командой:  
./BybitSpot-21  
и следуем подсказкам.
8. Выходим из работающего screen, не прерывая его работу, командой:  
ctrl+a, d (при нажатой ctrl жмем а, отпускаем их, и затем жмем d)

Далее, чтобы зайти в screen работающего бота, введите команду:  
screen -x BybitSpot  
То есть, второй раз вводить  
screen -S BybitSpot   
не нужно, а то создастся еще одна screen-сессия.
