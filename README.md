                                         PYTHON CODING STYLE

# GİRİNTİLEME

Girinti seviyesinin başına 4 boşluk bırakmalıyız. Argümanları yazarken satır atlarsak kodun anlaşılabilir olması açısından
argümanları aynı hizada yazmalıyız.

# Doğru kullanım, açılış sınırlayıcı ile aynı hizada olmasıdır.

    foo = long_function_name(var_one, var_two,

                             var_three, var_four)


print fonksiyonunu ayırt edebilmek için daha fazla girinti kullanmalıyız.


    def long_function_name(

          var_one, var_two, var_three,

          var_four):

       print(var_one)
  

Girinti seviyemiz her satırda aynı olmalıdır.


    foo = long_function_name(

        var_one, var_two,

        var_three, var_four)
        

# Yanlış kullanım:

Dikey hizalama kullanmadığımızda argümanlar ilk satırda yasaklanır.


    foo = long_function_name(var_one, var_two,

         var_three, var_four)


Girinti olarak gerekli olan girintiyi ayırt edemediğimiz durumlar.


    def long_function_name(

        var_one, var_two, var_three,
    
        var_four):
    
        print(var_one)
       

# İsteğe bağlı 4-boşluk kuralı:


4 boşluk yerine daha az boşlukta bırakabiliriz.


    foo = long_function_name(

     var_one, var_two,
  
     var_three, var_four)
  

if kullanırken ekstra boşluk kullanmayabiliriz.


    if (this_is_one_thing and

        that_is_another_thing):

        do_something()


Yorum satırı eklerken kullanmayabiliriz.


    if (this_is_one_thing and

        that_is_another_thing):
        
        #......

        do_something()
     

Koşullu devamlarda girinti eklemeliyiz.


    if (this_is_one_thing

           and that_is_another_thing):
      
        do_something()


Parantez kullanım şekli aşağıdaki gibi olabilir.


    my_list = [

        1, 2, 3,

        4, 5, 6,

        ]
    
    result = some_function_that_takes_arguments(

        'a', 'b', 'c',
    
        'd', 'e', 'f',
    
         )


Ya da aşağıdaki şekilde:


    my_list = [

        1, 2, 3,
    
        4, 5, 6,
    
    ]

    result = some_function_that_takes_arguments(

        'a', 'b', 'c',
    
        'd', 'e', 'f',
    
    )


# Operatörleri kullanırken


# Doğru kullanım şekli:

    income = (gross_wages

             + taxable_interest
          
             + (dividends - qualified_dividends)
          
             - ira_deduction
          
             - student_loan_interest)


# Yanlış kullanım şekli:

    income = (gross_wages +

             taxable_interest +
          
             (dividends - qualified_dividends) -
          
             ira_deduction -
          
             student_loan_interest)
          

# IMPORT İŞLEMİ


Modülleri aynı satırda değilde farklı satırlarda import etmeliyiz.


# Doğru kullanım:

    import os

    import sys


# Yanlış kullanım:

    import sys, os

from .. import .. yapısında aynı satırda yazabiliriz.

    from subprocess import Popen, PIPE


import ederken aşağıdaki sıralamayı kullanmalıyız.


1.standard library imports

2.related third party imports

3.local application/library specific imports


Bu şekilde kodlarınız daha okunabilir olacaktır.


# Örnek olarak:

    import mypkg.sibling

    from mypkg import sibling

    from mypkg.sibling import example


# Pet Peeves

Aşağıdaki durumlarda gereksiz boşlukardan kaçınmalıyız...


  1) Parantez içinde parantez varsa:


# Doğru kullanım:

    spam(ham[1], {eggs: 2})


# Yanlış kullanım:

    spam( ham[ 1 ], { eggs: 2 } )


  2) Virgül, noktalı virgül ya da iki noktadan önce:


# Doğru kullanım:

    if x == 4: print x, y; x, y = y, x


# Yanlış kullnaım:

    if x == 4 : print x , y ; x , y = y , x


  3) Operatör kullanılırken:

# Doğru kullanım:

    ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]

    ham[lower:upper], ham[lower:upper:], ham[lower::step]

    ham[lower+offset : upper+offset]

    ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]

    ham[lower + offset : upper + offset]


# Yanlış kullanım:

    ham[lower + offset:upper + offset]

    ham[1: 9], ham[1 :9], ham[1:9 :3]

    ham[lower : : upper]

    ham[ : upper]


  4) Fonksiyon çağırırken kullanılan parantezlerde:

# Doğru kullanım:

    spam(1)


# Yanlış kullanım:

    spam (1)


  5) Slicing ya da indexleme başlamadan açılan parantezlerden önce:

# Doğru kullanım:

    dct['key'] = lst[index]


# Yanlış kullanım:

    dct ['key'] = lst [index]


  6) Atama operatörlerini hizalamak için:

# Doğru kullnaım:

    x = 1

    y = 2

    long_variable = 3


# Yanlış kullanım:

    x             = 1

    y             = 2

    long_variable = 3


# Diğer Öneriler

Farklı operatörleri bir arada kullanırken düşük önceliğe sahip operatörler arasında birer boşluk bırakmalıyız.


# Doğru kullanım:

    i = i + 1

    submitted += 1

    x = x*2 - 1

    hypot2 = x*x + y*y

    c = (a+b) * (a-b)


# Yanlış kullanım:

    i=i+1

    submitted +=1

    x = x * 2 - 1

    hypot2 = x * x + y * y

    c = (a + b) * (a - b)


Varsayılan bir parametre değerini belirtirken kullanılan '=' operatöründe boşluk kullanmamalıyız.


# Doğru kullanım:

    def complex(real, imag=0.0):

    return magic(r=real, i=imag)


# Yanlış kullanım:

    def complex(real, imag = 0.0):

    return magic(r = real, i = imag)


'->' ifadesini kullanırken her zaman boşluk kullanmalıyız.


# Doğru kullanım:

    def munge(input: AnyStr): ...

    def munge() -> AnyStr: ...


# Yanlış kullanım:

    def munge(input:AnyStr): ...

    def munge()->PosInt: ...


Default değer atanırken boşluk kullanmalıyız.


# Doğru kullanım:

    def munge(sep: AnyStr = None): ...

    def munge(input: AnyStr, sep: AnyStr = None, limit=1000): ...


# Yanlış kullanım:

    def munge(input: AnyStr=None): ...

    def munge(input: AnyStr, limit = 1000): ...


Birleşik ifadeler genellikle tavsiye edilmez.


# Doğru kullanım:

    if foo == 'blah':

    do_blah_thing()

    do_one()

    do_two()

    do_three()


# Tercihen:

    if foo == 'blah': do_blah_thing()

    do_one(); do_two(); do_three()


if/for/while kullanılırken dikkat etmemiz gereken noktalar:


# Tercihen:

    if foo == 'blah': do_blah_thing()

    for x in lst: total += x

    while t < 10: t = delay()


# Kesinlikle kullanmamamız gereken yapı:

    if foo == 'blah': do_blah_thing()

    else: do_non_blah_thing()


    try: something()

    finally: cleanup()


    do_one(); do_two(); do_three(long, argument,

    list, like, this)


    if foo == 'blah': one(); two(); three()


Block comment-ler '#' ifadesi ile başlamalıdır.

Inline comment-larda


# Doğru kullanım:

    x = x + 1                 # Compensate for border


# Yanlış kullanım:

    x = x + 1                 # Increment x


Tüm public modüller, fonksiyonlar, sınıflar ve metodlar için Docstring-ler yazmalıyız.

Docstring-ler """ ile başlar """ ile biter.

"""Return a foobang


Optional plotz says to frobnicate the bizbaz first.

"""


Type değişkenlerinde PEP 484'e göre kısa isimler kullanmalıyız. Type değişkenlerine genellikle _ ile başlayan son ekler eklenir.


# Örnek olarak:

    from typing import TypeVar


    VT_co = TypeVar('VT_co', covariant=True)

    KT_contra = TypeVar('KT_contra', contravariant=True)


is not operatörü not ... is den daha kullanışlıdır.


# Doğru kullanım:

    if foo is not None:


# Tercihen:

    if not foo is None:


Tanımlama işlemlerinde lambda yerine def fonksiyonunu kullanmalıyız.


# Doğru kullanım:

    def f(x): return 2*x


# Yanlış kullanım:

    f = lambda x: 2*x


Fonksiyon isinmleri küçük harfli _ ile ayrılmış sözcüklerden oluşmalıdır. Örneğin; long_function_name

Instance metodların ilk argümanı genellikle 'self' olarak kullanılır.

Class metodların ilk argümanı genellikle 'cls' olarak kullanılır.

Class isimleri kesinlikle büyük harfle başlamalı ve tekil olmalıdır.

Sabitler genellikle büyük hafrle yazılırlar. Örneğin; MAX_OVERFLOW ve TOTAL.

