Душко Стојанов 215042

2 .

Control Flow Graph

![215042 drawio (1)](https://github.com/dulestojanov/SI_2024_lab2_215042/assets/166952471/9fe733c6-5f9e-46d3-8427-126b13b09754)

3 .**Цикломатската комплексност**

Цикломатската комплексност на овој код е 10, резултатот го добив = (Број на региони) или (број на ребра - број на јазли + 2) или (број на предикатни јазли + 1)=40 - 32 + 2 = 10

4 .**Тест случаи според критериумот Every Branch**

Тест случај кога allItems листата е празна:

Влезни параметри: allItems = [], payment = 100
Очекуван резултат: false
Тест случај кога allItems листата има еден елемент со попуст и баркод започнува со '0':

Влезни параметри: allItems = [Item("Name", "0123", 200, 0.1)], payment = 300
Очекуван резултат: true
Тест случај кога allItems листата има еден елемент без попуст и без баркод:

Влезни параметри: allItems = [Item("Name", null, 200, 0)], payment = 100
Очекуван резултат: исклучок RuntimeException ("No barcode!")
Тест случај кога allItems листата има еден елемент со баркод што не е валиден:

Влезни параметри: allItems = [Item("Name", "abc123", 200, 0)], payment = 100
Очекуван резултат: исклучок RuntimeException ("Invalid character in item barcode!")
Тест случај кога allItems листата има еден елемент со попуст, ама со цена помала од 300 и баркод што не започнува со '0':

Влезни параметри: allItems = [Item("Name", "12345", 200, 0.1)], payment = 100
Очекуван резултат: false
Тест случај кога allItems листата има еден елемент со попуст, со цена поголема од 300 и баркод што не започнува со '0':

Влезни параметри: allItems = [Item("Name", "12345", 400, 0.1)], payment = 350
Очекуван резултат: true
Тест случај кога allItems листата има еден елемент со попуст, со цена поголема од 300 и баркод што започнува со '0':

Влезни параметри: allItems = [Item("Name", "012345", 400, 0.1)], payment = 350
Очекуван резултат: true

5 . 
**Тест случаи според Multiple Condition **

Тест случај каде сите се true Item item = new Item("Item1", "012345", 400, 0.1f); assertTrue(checkCondition(item));

Тест случај каде првиот услов е false другите се true Item item = new Item("Item1", "012345", 200, 0.2f); assertFalse(checkCondition(item));

Тест случај каде вториот услов е false другите се true Item item = new Item("Item1", "012345", 400, 0); assertFalse(checkCondition(item));

Тест случај каде третиот услов е false другите се true Item item = new Item("Item1", "123456", 400, 0.1f); assertFalse(checkCondition(item));

Тест случај каде првиот и вториот услов се false а другите true Item item = new Item("Item1", "012345", 200, 0); assertFalse(checkCondition(item));

Тест случај каде првиот и третиот услов се false а другите true Item item = new Item("Item1", "123456", 400, 0.2f); assertFalse(checkCondition(item));

Тест случај каде вториот и третиот услов се false а другите true Item item = new Item("Item1", "123456", 400, 0); assertFalse(checkCondition(item));

Тест случај каде сите се false Item item = new Item("Item1", "123456", 200, 0); assertFalse(checkCondition(item));
