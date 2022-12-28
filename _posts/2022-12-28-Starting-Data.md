---
title: "Starting 66 Days of Data"
layout: post
---

In this past year I have been completing my Masters in Sport and Exercise and during this time I have been re-evaluating what sort of work I would like to be a part of. My initial goal (and still my main goal) was to be involved in sport research, but who's to say I can't be involved in action research, live research like professional sport as well?

My thoughts on this matter expanded with a paper I completed in the second semester which focused on sport analytics and data analysis. This experience really reinspired my interest in being part of professional sport. 

Naturally, I took to scouring youtube and I came across Ken Jee, a data scientist who has a big interest in sport analytics https://www.youtube.com/@KenJee_ds. Ken has this amazing idea of doing "66 days of data" to get starting into programming and data science. Thus, I decided to take the plunge, and my first project is to convert the code below into a 1RM (one repetition max) calculator. I will then expand to automatically create programs based off these calculations.

The sample of code which I retrieved from the "data professor" - https://www.youtube.com/watch?v=n6I58WJiKGU&ab_channel=DataProfessor

{% highlight python %}
import pywebio
from pywebio.input import input, FLOAT
from pywebio.output import put_text, put_html, put_markdown, put_table

def bmi():
    height = input("Input your height(cm)：", type=FLOAT)
    weight = input("Input your weight(kg)：", type=FLOAT)

    BMI = weight / (height / 100) ** 2

    top_status = [(16, 'Severely underweight'), (18.5, 'Underweight'),
                  (25, 'Normal'), (30, 'Overweight'),
                  (35, 'Moderately obese'), (float('inf'), 'Severely obese')]

    for top, status in top_status:
        if BMI <= top:
            put_markdown('# **Results**')
            put_text('Your BMI: %.1f. Category: %s' % (BMI, status))
            put_html('<br><br>')
            put_markdown('Your BMI: `%.1f`. Category: `%s`' % (BMI, status))
            put_html('<hr>')
            put_table([
                ['Your BMI', 'Category'],
                [BMI, status],
            ])

            break

if __name__ == '__main__':
    pywebio.start_server(bmi, port=55)
{% endhighlight %}

Anyway, this is my first documented day 1/66.
