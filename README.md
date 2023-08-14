# Python-31-
Python学习笔记(31)
# P104 traceback模块的使用
print(10/0)
import traceback
try:
    print('----------------')
    print(1/0)
except:
    traceback.print_exe()



# p105 Pycharm的程序调试
i=1
while i<10:
    print(i)
    i+=1



# p106 编程的两大思想_面向过程_面向对象
#面向过程是自己做西红柿炒鸡蛋，每一步都要清楚，面向对象是选美团饿了吗点外卖，商家怎么做我不需要知道
#两者相辅相成，并不是相互对立
#解决问题，通过面向对象方式便于我们从宏观上把握事物的·关系，具体到微观，仍然要面向过程来解决



# p107 类与对象
#类是多个类似事物组成的群体的统称。能够帮助我们快速理解和判断事物的性质
#不同的数据类型属于不同的类，用内置函数查看数据类型print(type(100))
#Python中一切皆对象



# p108 定义Python中的类
class Student:  #Student为类的名称(类名)有一个或多个单词组成，每个单词的首字母大写，其余小写
    pass

#Python中一切皆对象Student是对象吗？内存有开空间吗？
print(id(Student))  #开辟1内存空间
print(type(tudent))
print(Student)  #这叫一个类


class Student
native_pace='吉林'  #直接写在类里的变量，称为类属性
def__init__(self,name,age):
    self.name=name  #self.name成为实体属性，进行了一个赋值操作，将局部变量的name的值赋给实体属性
    self.age=age

def eat(self):
    print('学生在吃饭')  #方法

#在类之外定义的称为函数，在类之外定义的称为方法
def drink()：
    print('喝水')  #这个在class之外定义叫函数

#静态方法
@staticmethod
def method():  #这里是不可以用self
    print('我使用了staticmethod进行了修饰，蓑衣我是静态方法')

#类方法
@classmethod
def cm(cls):  #这里要求cls
    print('我是类方法，因为我使用了classmethod进行修饰')



# p109 对象的创建
stu1=Student('张三',20)
print(id(stu1))
print(type(stu1))
print(stu1)
print('-----------------')
print(id(Student))  #Student是类的名称
print(type(Student))
print(Student)

#创建Student类的对象
stu1=Student('张三',20)
stu1.eat()  #输出为学生在吃饭  对象名.方法名()
print(stu1,name)
print(stu1,age)

print('----------------')
Student.eat(stu1)  #输出为学生在吃饭  33行与28行代码功能相同，都是在调用Student-中的eat方法
                   #类名.方法名(类的对象)-->实际上就是方法定义处的self



# p110 类属性_类方法_静态方法的使用方法
#类属性的使用方式
print(Student.native_pace)
stu1=Student('张三',20)
stu2=Student('李四',30)
print(stu1.native_pace)
print(stu2.native_pace)  #两个都输出吉林
Student.native_pace='天津'
print(stu1.native_pace)
print(stu2.native_pace)  #两个都是天津

#每个实例对象都有一个类指针指向类类别
#所以Student类别是有stu1和stu2共享的，把Student改成天津的时候，两个都为天津，因为Student的的值是共享的

#类方法传的是class，实例方法传的是自身实例对象
print('----------------类方法的使用方式----------------------')
Student.cm()  #调用类方法
print('----------------静态方法的使用方式----------------------')
Student.sm()



# p111 动态绑定属性和方法
class Student:
    def__init__(self,name,age):
        self.name=name
        self.age=age
    def eat(self):
        print(self.name+'在吃饭')

stu1=Student('张三',20)
stu2=Student('李四',30)
#Student类可以创建N个Student类的实例对象，每个实例对象的属性值不同
print('---------------为stu2动态绑定性别属性-----------------')
stu2.gender='女'
print(stu1,name,stu1.age)
print(stu2.name,stu2.age,stu2.gender)
#这个gender只隶属于stu2，其他调用无效

print('----------------------')
stu1.eat()
stu2.eat()

def show():
    print('定义在类之外的，称函数题')
stu1.show=show
stu1.show()

#stu2.show()  #报错，因为stu2没有绑定show方法
