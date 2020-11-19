---
layout: home
---

{% for category in site.categories %}
{% if category contains "news" %}

<h2>Upcoming Events</h2>
<ul>
    {% for post in category[1] %}
    {% assign post_due_in_seconds = post.due_date | date: "%s" | plus: 0 %}
    {% assign current_time_in_seconds = "now" | date: "%s" | minus: 0  %}
    {% if post_due_in_seconds >= current_time_in_seconds %}
    <li>
      <a href="{{ post.url }}" style="color:black">{{ post.title }}</a>
      {{ post.excerpt | markdownify }}
    </li>
    {% endif %}
    {% endfor %}
</ul>
{% endif %}
{% endfor %}

[Read More...](news)

<h2>Previous Talks</h2>

{% for category in site.categories %}
{% if category contains "talks" %} <!-- Take note here!! -->
<ul>
    {% for post in category[1] %}
    {% assign post_due_in_seconds = post.due_date | date: "%s" | plus: 0 %}
    {% assign current_time_in_seconds = "now" | date: "%s" | minus: 0  %}
    {% if post_due_in_seconds < current_time_in_seconds %}
    <li>
      <a href="{{ post.url }}" style="color:black">{{ post.title }}</a>
      {{ post.excerpt | markdownify }}
    </li>
    {% endif %}
    {% endfor %}
</ul>
{% endif %}
{% endfor %}

[Read More...](talks)

<h2>About</h2>

Deeplang team is composed of students from [ZJU](http://www.zju.edu.cn/) & [USTC](https://www.ustc.edu.cn/). Deeplang is a light Interpreted programming language for IoT device.

**Deeplang code repo**:  [GitHub](https://github.com/deeplang-org/deeplang).

**Deeplang features**:

- memory safe
- static and strong type system
- C-style
- Mixed programming paradigm include procedural, object-oriented, logic

We are designing a light language virtual machine named Deepvm. Deepvm is to support IoT chips include [ESP32](https://www.espressif.com/en/products/socs/esp32), HI3861, [Loongson 1C0300B](http://www.loongson.cn/product/cpu/1/Loongson1C.html).

**Deepvm features**:

- light REPL
- light & fast memory management
- support wasm file execution
- ROM <= 100KB, RAM <= 50KB

The code are hosted [here](https://github.com/deeplang-org/deeplang).

If you would like to know more about us, please email [Eric](mailto:swubear@163.com), [Joey](mailto:joey.teng.dev@gmail.com) or [Thomas](mailto:wenzhang5800@gmail.com).

## Example

Fibonacci sequence codes (*fib.dp*) as follow:

```C
fun fib (n: i32) -> i32 {
    if (i == 0) {
        return 0;
    } else if (i == 0) {
        return 1;
    } else {
        return fib(i - 1) + fib(i - 2);
    };
};


fun main () -> () {
    let res: i32 = fib(10);
    print(res.toString());
};
```
