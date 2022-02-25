---
# Front matter
lang: ru-RU
title: "Лабораторная работа №3"
subtitle: "Модель боевых действий"
author: "Смирнов Артем Александрович"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

- Рассмотреть простейшую модель боевых действий – модель Ланчестера:
- Научиться составлять системы дифференциальных уравнений изменения численностей армий;
- Научиться строить графики для моделей боевых действий.



# Задание №51

Между страной *Х* и страной *У* идет война. Численность состава войск исчисляется от начала войны, и являются временными функциями *x(t)* и *y(t)*. В начальный момент времени страна *Х* имеет армию численностью 25000 человек, а в распоряжении страны *У* армия численностью в *39000* человек. Для упрощения модели считаем, что коэффициенты  *a, b, c, h*  постоянны. Также считаем *P(t)* и *Q(t)* непрерывные функции. 

Постройте графики изменения численности войск армии *Х* и армии *У* для следующих случаев:

					1.Модель боевых действий между регулярными войсками
$$
\frac{\partial x}{\partial t} = -0.441x(t) - 0.773y(t) + sin(2t)+1
$$

$$
\frac{\partial y}{\partial t} = -0.55x(t) - 0.664y(t) +cos(2t) + 1
$$

					2.Модель ведение боевых действий с участием регулярных войск и партизанских отрядов 


​										
$$
\frac{\partial x}{\partial t} = -0.399x(t) - 0.688y(t) + sin(2t) + 2
$$

$$
\frac{\partial y}{\partial t} = -0.299x(t)y(t) - 0.811y(t) +cos(3t) + 1
$$

# Краткая теоретическая справка

Рассмотрим некоторые простейшие модели боевых действий – модели Ланчестера. В противоборстве могут принимать участие как регулярные войска, так и партизанские отряды. В общем случае главной характеристикой соперников являются численности сторон. Если в какой-то момент времени одна из численностей обращается в нуль, то данная сторона считается проигравшей (при условии, что численность другой стороны в данный момент положительна).

Рассмотри три случая ведения боевых действий: 

1. Боевые действия между регулярными войсками. 

2.  Боевые действия с участием регулярных войск и партизанских отрядов. 

3.  Боевые действия между партизанскими отрядами. 

   - В первом случае численность регулярных войск определяется тремя факторами: 

     скорость уменьшения численности войск из-за причин, не связанных с боевыми действиями (болезни, травмы, дезертирство); 

   - Скорость потерь, обусловленных боевыми действиями противоборствующих сторон (что связанно с качеством стратегии, уровнем вооружения, профессионализмом солдат и т.п.);  

   - Скорость поступления подкрепления (задаётся некоторой функцией от времени). В этом случае модель боевых действий между регулярными войсками описывается следующим образом.

     

В этом случае модель боевых действий между регулярными войсками описывается следующим образом
$$
\frac{\partial x}{\partial t} = -a(t)x(t) - b(t)y(t) + P(t)
$$

$$
\frac{\partial y}{\partial t} = -c(t)x(t) - h(t)y(t) + Q(t)
$$

Потери, не связанные с боевыми действиями, описывают члены *-a(t)x(t)* и *-h(t)y(t)* , члены *-b(t)y(t)* и *-c(t)x(t)* отражают потери на поле боя. Коэффициенты *b(t)* и *c(t)* указывают на эффективность боевых действий со стороны *у* и *х* соответственно, *a(t), h(t)* - величины, характеризующие степень влияния различных факторов на потери. Функции  *P(t), Q(t)* учитывают  возможность подхода подкрепления к войскам *Х* и *У* в течение одного дня.



	Во втором случае в борьбу добавляются партизанские отряды. Нерегулярные войска в отличии от постоянной армии менее уязвимы, так как действуют скрытно, в этом случае сопернику приходится действовать неизбирательно, по площадям, занимаемым партизанами. Поэтому считается, что тем потерь партизан, проводящих свои операции в разных местах на некоторой известной территории, пропорционален не только численности армейских соединений, но и численности самих партизан. В результате модель принимает вид:
$$
\frac{\partial x}{\partial t} = -a(t)x(t) - b(t)y(t) + P(t)
$$

$$
\frac{\partial y}{\partial t} = -c(t)x(t)y(t) - h(t)y(t) + Q(t)
$$

 В этой системе все величины имеют тот же смысл, описанный выше.

# Выполнение лабораторной работы

**Случай 1: Модель боевых действий между регулярными войсками**

model lab03

parameter Real t; 

constant Real a=0.441; 
constant Real b=0.89; 
constant Real c=0.299; 
constant Real h=0.811;  

Real p;
Real q;
Real x;
Real y;

initial equation
x=25000; 
y=39000; 
t=0;

equation
p= sin(2*t) + 2;  
q= cos(3*t) + 1;
der(x)=-a*x-b*y+p;
der(y)=-c*x-h*y+q;

end lab03;



График первого случая (рис.01).

<figure>
    <img src = image\1.PNG alt = "График первого случая">
    <figcaption>рис.01</figcaption>
</figure>
*Победила страна Y.*



**Случай 2: Модель боевых действий между регулярными войсками и партизанами**

model lab03

parameter Real t; 

constant Real a=0.399; 
constant Real b=0.688; 
constant Real c=0.299; 
constant Real h=0.811;  

Real p;
Real q;
Real x;
Real y;

initial equation
x=25000; 
y=39000; 
t=0;

equation
p= sin(2*t) + 2;  
q= cos(3*t) + 1;
der(x)=-a*x-b*y+p;
der(y)=-c*x*y-h*y+q;

end lab03;

График второго случая (рис.02).

<figure>
    <img src = image\2.PNG alt = "График второго случая">
    <figcaption>рис.02</figcaption>
</figure>
*Победила страна X.*



# Вывод

- Научился строить простые модели
- Научился строить графики моделей военных действий (численность армии)
- Рассмотрел модель боевых действий - модель Ланчествера



# Список литературы

Кулябов Д.С "Лабораторная работа №3": https://esystem.rudn.ru/pluginfile.php/1343805/mod_resource/content/2/Лабораторная%20работа%20№%202.pdf



<figure>