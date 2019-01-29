# 小结

- tostring
 每个对象都会有默认的tostring 方法
 每个对象都有一个toString()方法，当该对象被表示为一个文本值时，或者一个对象以预期的字符串方式引用时自动调用。默认情况下，toString()方法被每个Object对象继承。如果此方法在自定义对象中未被覆盖，toString() 返回(去api查看)，其中type是对象(类)的类型。

 
 - this 调用属性或方法时，会先从本类查找是否存在指定的属性或方法，如果没有，则会去父类查找是否存在

- 所有的类钧继承Object 类，一个完整的简单的java类 理论上应该覆写Object 类中的   toString(), eqauls(),hashcode() 

 



