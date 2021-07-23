## property 和 属性名.setter 装饰器
- property装饰器将一个get方法转换为对象属性
- setter装饰器将一个set方法装换位对象属性
    ```
    class Person():
        def __init__(self, name):
            self._name = name

        @property
        def name(self):
            return self._name

        @name.setter
        def nam(self, value):
            self._name = value
    
    person = Person("Amy")
    print(person.name)      # Amy
    person.nam = "Panda"
    print(person.name)      # Panda
    ```


## python中下划线区别
```
    _foo：一种约定，用来指定变量私有。程序员用来指定私有变量的一种方式。
    __foo：这个有真正的意义：解析器用_classname__foo来代替这个名字，以区别和其他类相同的命名。
    __foo__：一种约定，Python内部的名字，用来区别其他用户自定义的命名，以防冲突。
```