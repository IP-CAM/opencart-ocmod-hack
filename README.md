# opencart-ocmod-hack

Хак для Opencart 2.x, который добавляет функционал применения модификаций по версии Opencart в OCMOD.

Для примера, в Opencart 2.1.x в системной библиотеке language.php есть такой замечательный метод all(), который отдает все значения языкового файла, но данного метода нет в Opencart 2.0.x. Вот тут нам и может помочь этот модуль, который вводит для XML-тега "operation" два новых аттрибута:
* min-version - минимальная версия Opencart, для которой применяется данная модификация
* max-version - максимальная версия Opencart, для которой применяется данная модификация

Пример Вашего файла install.xml, который вносит изменения в системную библиотеку language.php, чтобы был доступен метод all() на Opencart 2.0.x
```
<?xml version="1.0" encoding="utf-8"?>
<modification>
    <name>Add language method all() for Opencart 2.0.x</name>
    <version>1.0</version>
    <author>Sergey Pechenyuk (http://oc-store.com)</author>
	  <code>ocstore_test_version</code>
	  <file path="system/library/language.php">	
		  <operation min-version="2.0.0" max-version="2.0.3.1">
			  <search trim="true"><![CDATA[public function load($filename) {]]></search>
			  <add position="before" trim="true"><![CDATA[
				  public function all() {
					  return $this->data;
				  }
			  ]]></add>
		  </operation>
	  </file>
</modification>
```
