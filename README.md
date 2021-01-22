opencart-ocmod-hack

A hack for Opencart 2.x that adds the functionality of applying modifications according to the Opencart version to OCMOD.

For example, in Opencart 2.1.x in the system library language.php there is such a wonderful method all () that returns all the values ​​of the language file, but this method is not in Opencart 2.0.x. This is where this module can help us, which introduces two new attributes for the operation XML tag:

    min-version - minimum Opencart version for which this modification applies
    max-version - maximum version of Opencart for which this modification applies
---
An example of your install.xml file, which makes changes to the system library language.php so that the all () method is available on Opencart 2.0.x
---
#<?xml version="1.0" encoding="utf-8"?>
#<modification>
#    <name>Add language method all() for Opencart 2.0.x</name>
#    <version>1.0</version>
#    <author>Sergey Pechenyuk (http://oc-store.com)</author>
#	  <code>ocstore_test_version</code>
#	  <file path="system/library/language.php">	
#		  <operation min-version="2.0.0" max-version="2.0.3.1">
#			  <search trim="true"><![CDATA[public function load($filename) {]]></search>
#			  <add position="before" trim="true"><![CDATA[
#				  public function all() {
#					  return $this->data;
#				  }
#			  ]]></add>
#		  </operation>
#	  </file>
#</modification>
---
