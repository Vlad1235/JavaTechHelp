### Memory Java - память в Java.  

- - -  

##### Молодое поколение:  

место (память jvm/куча heap), где создаются все новые объекты.  
Когда памят заполнена, запускается сборка мусора. Minor GC - незначительный вывоз мусора.  

GC - Garbage Collection - вывоз/сборка мусора.  

Молодое поколение =  Eden  ->  Survivor_0  <->  Survivor_1  

Принципы:
     - Все новые объекты помещаются в область EDEN.  
     - Когда EDEN заполнено, производится Minor GC, и все уцелевшие переносятся в область Survivor 0 или 1.  
     (область EDEN, очевидно, очищается)  
     - Minor GC так же проверяет оставшуюся область Survivor, и переносит все уцелевшие объекты,  
     к только что добавленным из области EDEN.  
     - Поэтому одна из областей Survivor всегда остается пустой.  
     - Объекты, которые сохранились после многих циклов GC, переносятся в область Old generation.  
     (устанавливается пороговое значения для возраста объектов молодого поколения,  
     после которого они перемещаются в область старого поколения)  

- - -  

##### Старое поколение:

место (память jvm/ куча heap), где расположены объекты, которые  
уцелели после многогратных Minor GC. Когда память заполнена, запускается сборка мусора.  
Major GC - основной вывоз мусора.  

- - -  

### Stop the world event.  

Когда запускается GC останавливаются все потоки приложения.  
Minor GC - работает очень быстро и практически незаметно для приложения.  
Major GC - работает долго и может привести в тайм-аутам, поэтому важно отслеживать и  
настраивать GC.


[Heap & Stack java - from javadevblog](https://javadevblog.com/chto-takoe-heap-i-stack-pamyat-v-java.html)  
[Jvm inside - from Habr](https://habr.com/ru/post/84165/)  

- - -  

### Garbage collector - сборщик мусора.  
- - -  

[Garbage collector - from ibm](https://www.ibm.com/developerworks/ru/library/j-jtp11253/index.html)  