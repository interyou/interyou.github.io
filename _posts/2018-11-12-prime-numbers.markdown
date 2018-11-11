---
layout: post
title: Задача о представлении числа в виде суммы двух простых чисел
date: 2018-11-07 12:00:00 +0300
categories: jekyll update
---
### Условие
Необходимо реализовать функцию, которая принимает на вход целое положительное число, и возвращает   `true`  или   `false`  в зависимости от того, может ли число быть представлено суммой двух простых чисел. При этом, функция, определяющая является ли число простым, уже реализована:

<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
fun isPrime(n: Int): Boolean 
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
func isPrime(_ n: Int) -> Bool
{% endhighlight %}
</div>

### Решение
Сходу в голову приходит идея перебрать все возможные суммы и проверить слагаемые на простоту:


<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
fun test(n: Int): Boolean {
    (1..n).forEach { number ->
            if (isPrime(number) && isPrime(n - number)) {
                return true
            }
        }
        return false
}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
funс test(_ n: Int) -> Bool {
    for number in 1...n {
        if isPrime(number) && isPrime(n - number) {
            return true
        }
    }
    return false
}
{% endhighlight %}
</div>

Если подумать, зачем перебирать все числа подряд, если числа кратные двум не являются простыми:

<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
fun test(n: Int): Boolean {
    for (i in 1..n step 2) {
        if (isPrime(i) && isPrime(n - i)) {
            return true
        }
    }
    return false
}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
funс test(_ n: Int) -> Bool {
    for number in stride(from: 1, through: n, by: 2) {
        if isPrime(number) && isPrime(n - number) {
            return true
        }
    }
    return false
}
{% endhighlight %}
</div>


Уже близко! Если мы дошли до середины диапазона, то после этого мы уже будем получать числа вида n - i и i, которые мы уже проверили, значит можно сократить диапазон проверяемых чисел в два раза. Получим следующее решение:

<div class="tab">
    <button class="tablinks Kotlin active" style="margin-left: -1px;" onclick="openTab(event, 'Kotlin')">Kotlin</button>
    <button class="tablinks Swift" onclick="openTab(event, 'Swift')">Swift</button>
</div>

<div class="tabcontent Kotlin" style="display: block;">
{% highlight kotlin %}
fun test(n: Int): Boolean {
    val last = n / 2 
    for (i in 1..last step 2) {
        if (isPrime(i) && isPrime(n - i)) {
            return true
        }
    }
return false
}
{% endhighlight %}
</div>

<div class="tabcontent Swift">
{% highlight swift %}
funс test(_ n: Int) -> Bool {
    var last = n / 2
    for number in stride(from: 1, through: last, by: 2) {
        if isPrime(number) && isPrime(n - number) {
            return true
        }
    }
return false
}
{% endhighlight %}
</div>

### Что дальше?
Оптимизаций еще много, а что сможете придумать вы? Задачка хорошо показывает интервьюеру то, как вы думаете и можете ли придумать оптимизацию решения предложенной вам задачи. Всегда не забывайте оценить адекватность решения, которое вы предлагаете!

### P.S.
Для практики можете также построить алгоритм, который будет принимать на вход 2 целых положительных числа: число, которое нужно разложить на простые слагаемые, и число простых слагаемых, и возвращать   `true`  или   `false`  в зависимости от того, может ли число быть представлено суммой треубемого количества простых чисел. При этом, функция, определяющая является ли число простым, также реализована.
