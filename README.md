# Втора лабораториска вежба по софтверско инженерство
## Marija Vasilevska 223159
## 2. Control Flow Graph
![Cfg_lab2](https://github.com/marijavasilevska06/SI_2024_lab2_223159/assets/163039204/bdc24212-2f13-476b-a296-941e5fab43ec)

## 3. Цикломатска комплексност
Цикломатската комплексност на дадениот код е 10. Ја добив според формулата Р+1, односно Р е број на предикатни јазли, обоените на графот кои се 9+1=10.

## 4.Тест случаи според Every Branch критериумот
Тест случај 1: allItems = null, payment = 100

резултат: Фрлање на RuntimeException со порака "allItems list can't be null!"
Ова го тестира првиот if услов кој проверува дали листата allItems е null.
Тест случај 2: allItems = [], payment = 100

резултат:true
Ова го тестира случајот каде што листата allItems е празна и нема предмети за обработка.
Тест случај 3: allItems = [new Item("item1", "123", 100, 0)], payment = 100

резултат: true
Ова го тестира случајот каде што предметот има валидно име и баркод и нема попуст.
Тест случај 4:allItems = [new Item("", "123", 100, 0)], payment = 100

резултат:true
Ова го тестира случајот каде што предметот има празно име и се поставува на "unknown".
Тест случај 5: allItems = [new Item("item1", "12a3", 100, 0)], payment = 100

резултат: Фрлање на RuntimeException со порака "Invalid character in item barcode!"
Ова го тестира случајот каде што баркодот на предметот содржи невалиден карактер.
Тест случај 6:allItems = [new Item("item1", null, 100, 0)], payment = 100

резултат: Фрлање на RuntimeException со порака "No barcode!"
Ова го тестира случајот каде што предметот нема баркод.
Тест случај 7: allItems = [new Item("item1", "123", 100, 0.1f)], payment = 90

резултат:true
Ова го тестира случајот каде што предметот има попуст.
Тест случај 8: allItems = [new Item("item1", "0123", 350, 0.1f)], payment = 31.5

резултат:false
Ова го тестира случајот каде што предметот исполнува сите три услови и цената се намалува за 30.
![tabela excel](https://github.com/marijavasilevska06/SI_2024_lab2_223159/assets/163039204/2be28d20-17c1-42a4-85d3-5153cfa10e5e)

## 5. Тест случаи според Multiple Condition критериумот за условот
if (item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0') Тест случај 1 - Сите услови се исполнети: Влез: item.getPrice() = 400, item.getDiscount() = 0.1, item.getBarcode() = "01234" излез: true

Тест случај 2 - Цената е помала од 300:

Влез: item.getPrice() = 200, item.getDiscount() = 0.1, item.getBarcode() = "01234" излез: false

Тест случај 3 - Нема попуст:

Влез: item.getPrice() = 400, item.getDiscount() = 0, item.getBarcode() = "01234" излез: false

Тест случај 4 - Баркодот не почнува со '0':

Влез: item.getPrice() = 400, item.getDiscount() = 0.1, item.getBarcode() = "12345" излез: false

Тест случај 5 - Цената е поголема од 300 и баркодот почнува со 0, но нема попуст: Влез: item.getPrice() = 400, item.getDiscount() = 0, item.getBarcode() = "01234" излез: false

## Објаснување за unit тестовите
Unit тестовите ги направив врз база на дадените тест случаи кои се напишани со помош на добиениот граф користејки ја табелата прикачена погоре.
