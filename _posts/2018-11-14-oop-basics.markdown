---
layout: post
title: Основы ООП
date: 2018-11-14 15:00:00 +0300
categories: jekyll update
---
Сегодня речь пойдет об одном из базовых приниципов в программировании - ООП. Swift и Kotlin принадлежат семейству ООП языков. Поэтому крайне важно хорошо знать базовые понятия, чтобы писать легко поддерживаемый и расширяемый код.

### Что такое ООП?
ООП - (Объектно Ориентированное Программирование) методология программирования, основанная на представлении программы в виде совокупности объектов, каждый из которых является экземпляром определённого класса, а классы образуют иерархию наследования.

### Основные понятия

#### Класс
Класс - это способ описания сущности, определяющий состояние и поведение, зависящее от этого состояния, а также правила для взаимодействия с данной сущностью (контракт).
<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
// Объявление класса ExampleClass
class ExampleClass {
	
	var myProperty: Int = 0

}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Объявление класса ExampleClass
class ExampleClass {
	
	var myProperty: Int = 0

}
{% endhighlight %}
</div>

#### Объект
Объект (экземпляр) – это отдельный представитель класса, имеющий конкретное состояние и поведение, полностью определяемое классом.
<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
// Создаем экземпляр класса 
val exampleObject = ExampleClass()
// Напечатаем переменную myProperty опредленную в классе ExampleClass
println(exampleObject.myProperty)
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Создаем экземпляр класса 
let object = ExampleClass()
// Напечатаем переменную myProperty опредленную в классе ExampleClass
print(object.myProperty)
{% endhighlight %}
</div>

#### Интерфейс
Интерфейс – это набор методов класса, доступных для использования другими классами. 
<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
interface MyInterface {

	fun doSomething()

}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Объявление интерфейся MyInterface
protocol MyInterface {

	func doSomething()

}
{% endhighlight %}
</div>

### Основные принципы

#### Инкапсуляция
Инкапсуляция – это свойство системы, позволяющее объединить данные и методы, работающие с ними, в классе и скрыть детали реализации от пользователя.
<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
class ExampleClass {
	
	var myProperty: Int = 0

	fun doSomething() {
		println("This function do something")
	}

}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Объявление класса ExampleClass. 
// Переменная myProperty и функция doSomething инкапсулированы в классе ExampleClass.
class ExampleClass {
	
	var myProperty: Int = 0

	func doSomething() {
		print("This function do something")
	}

}
{% endhighlight %}
</div>

#### Абстрагирование
Абстрагирование – это способ выделить набор значимых характеристик объекта, исключая из рассмотрения незначимые. Соответственно, абстракция – это набор всех таких характеристик.
<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
// Объявление класса Dog. 
// Пусть, значимые переменные собаки это имя, хозяин, а функция лаять. 
// Мы понимамаем, что у собаки также есть порода, рост, вес и прочее, но мы опускаем данные характеристики
class Dog(val name: String, val owner: String) {

	fun bark() {
		print("WOOF-WOOF-WOOF")
	}

}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Объявление класса Dog. 
// Пусть, значимые переменные собаки это имя, хозяин, а функция лаять. 
// Мы понимамаем, что у собаки также есть порода, рост, вес и прочее, но мы опускаем данные характеристики
class Dog {
	
	let name: String
	var owner: String

	init(name: String, owner: String) {
		self.name = name
		self.owner = owner
	}

	func bark() {
		print("WOOF-WOOF-WOOF")
	}

}
{% endhighlight %}
</div>

#### Полиморфизм
Полиморфизм – это свойство системы использовать объекты с одинаковым интерфейсом без информации о типе и внутренней структуре объекта.
<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
// Объявление интерфейся MyInterface
interface MyInterface {

	fun doSomething()

}

// Первая реализация интерфейся MyInterface
class Implementation1: MyInterface {
	
	override fun doSomething() {
		print("Doing something")
	}

}

// Вторая реализация интерфейся MyInterface
class Implementation2: MyInterface {
	
	override fun doSomething() {
		print("Doing nothing")
	}

}

// Объявим перменную, которая будет иметь тип MyInterface
val exampleObject: MyInterface

// Тогда мы можем присвоить данной переменной как объект класс Implementation1, так и класс Implementation2.
// Причем обращаемся мы к ним через интерфейс MyInterface.
exampleObject = Implementation1()
exampleObject.doSomething() // Doing something

exampleObject = Implementation2()
exampleObject.doSomething() // Doing nothing
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Объявление интерфейса MyInterface
protocol MyInterface {

	func doSomething()

}

// Первая реализация интерфейся MyInterface
class Implementation1: MyInterface {
	
	func doSomething() {
		print("Doing something")
	}

}

// Вторая реализация интерфейся MyInterface
class Implementation2: MyInterface {
	
	func doSomething() {
		print("Doing nothing")
	}

}

// Объявим перменную, которая будет иметь тип MyInterface
var object: MyInterface

// Тогда мы можем присвоить данной переменной как объект класс Implementation1, так и класс Implementation2.
// Причем обращаемся мы к ним через интерфейс MyInterface.
object = Implementation1()
object.doSomething() // Doing something

object = Implementation2()
object.doSomething() // Doing nothing
{% endhighlight %}
</div>

#### Наследование
Наследование – это свойство системы, позволяющее описать новый класс на основе уже существующего с частично или полностью заимствующейся функциональностью. Класс, от которого производится наследование, называется базовым или родительским. Новый класс – потомком, наследником или производным классом.

<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
// Объявление класса ExampleClass
class ParentClass {
	
	var myProperty: Int = 0

}

// Создаем класс ChildClass потомка ParentClass
class ChildClass: ParentClass {
	
	var anotherProperty: Int = 1

}

val child = ChildClass()
// Нам доступны параметры класс предка
println(child.myProperty) // 0
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
// Объявление класса ExampleClass
class ParentClass {
	
	var myProperty: Int = 0

}

// Создаем класс ChildClass потомка ParentClass
class ChildClass: ParentClass {
	
	var anotherProperty: Int = 1

}

let child = ChildClass()
// Нам доступны параметры класс предка
print(child.myProperty) // 0
{% endhighlight %}
</div>

На этом все. До пятницы!
