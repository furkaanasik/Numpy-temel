## **Numpy**

### **Numpy nedir?**
Numpy dizilerle çalışmak için kullanılan python kütüphanesidir. Ayrıca **Num**erical **Py**thon kısaltılmasıdır.

### **Neden Numpy?**
Listeler her bir veri için bir veri tipi tuttuğundan çok yavaştır. Buna kıyasla Numpy dizileri listelerden çok daha hızlıdır.

### **Nasıl kurulur?**
```
pip install numpy
```


### **Projeye entegre edilmesi.**


```python
# Artık np adı ile çağırılabilir.
import numpy as np
```

### **Numpy sürümünü kontrol etmek.**


```python
print(np.__version__)
```

    1.22.3
    

## **Numpy dizisi oluşturma**

Numpy dizi nesnesine ndarray denir. Dizi oluşturmak için np.array() fonksyionun kullanılabilir.

Numpy ile dizi yaratırken np.array fonksiyonuna parametre olarak gönderilecek parametre tuple içinde ya da liste içinde gönderilmesi gerkiyor.


```python
# np.array() fonksiyonu ile array tanımlanması.
arr = np.array([1, 2, 3])

# arrayi ekrana basmak.
print(arr)

# arrayin tipini ekrana basmak.
print(type(arr))
```

    [1 2 3]
    <class 'numpy.ndarray'>
    

### **1 boyutlu diziler**


```python
arr = np.array([1, 2, 3])

print(arr)
```

    [1 2 3]
    

### **2 boyutlu diziler**




```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(arr)
```

    [[1 2 3]
     [4 5 6]]
    

### **3 boyutlu diziler**


```python
arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print(arr)
```

    [[1 2 3]
     [4 5 6]
     [7 8 9]]
    

### **Bir dizinin boyutunu nasıl kontrol edebiliriz?**

Bir dizinin boyutunu konrol etmek için 'ndim' kulllanılır.


```python
# 0 boyutlu dizi.
arr = np.array(1)
print(arr.ndim)

# 1 boyutlu dizi.
arr = np.array([1,2,3])
print(arr.ndim)

# 2 boyutlu dizi.
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.ndim)
```

    0
    1
    2
    

### **Bir dizinin elemanlarına nasıl erişirim?**

Listelerdeki sistem gibi kullanılabilir.

1 boyutlu dizinin elemanlarına erişmek;





```python
# örnek listenin tanımlanması
sample_list = [10, 1, 2, 3]
# örnek listesinin ilk elemanını ekrana bastırmak
print(sample_list[0])


# np.array() fonksiyonu ile dizi oluşturma
arr = np.array([4,1,2])
# dizinin ilk elemanını ekrana bastırmak
print(arr[0])
```

    10
    4
    

2 boyutlu dizinin elemanlarına erişmek;


```python
# iki boyutlu bir dizi tanımlanması
arr = np.array([[10, 9, 8], [7, 6, 5]])

# ikinci boyuttaki ilk eleman
print(arr[1, 0])
```

    7
    

### **Dizi dilimleme (Slicing)**

Tek boyutlu dizileri dilimlemek;


```python
# Bir boyutlu bir dizi tanımlanması.
arr = np.array([1, 2, 3, 4, 5])

# Diziyi başlangıçtan sona kadar şekliyle istediğimiz parçayı dilimledik.
print(arr[1:3])

# Belirlenen başlangıçtan diziyi sona kadar dilimlemek.
print(arr[2:])

# Baştan diziyi belirlenen sona kadar bölmek.
print(arr[:4])
```

    [2 3]
    [3 4 5]
    [1 2 3 4]
    

Çok boyutlu dizileri dilimlemek;


```python
# Boyutlu dizinin tanımlanması.
arr = np.array([[0, 1, 2, 3], [10, 20, 30, 40]])

print(arr[1, [2, 3]])
```

    [30 40]
    

### **Dizi kopyalama (Copy)**

Kopyalama işlemi bir dizideki elemanın değeri değiştirildiğinde asıl dizide değişmemesini sağlar.


```python
# Dizinin tanımlanması.
arr = np.array([10, 20, 30, 40])

# Kopyalanma işlemi.
clone = arr.copy()

print(arr)
print(clone)
```

    [10 20 30 40]
    [10 20 30 40]
    

Diziyi bir değişkene atadığımızda asıl dizimiz değişiyor örnek;


```python
# Dizinin tanımlanması
arr = np.array([10, 20,30, 40])

# Dizi kopyalanmaz referans olarak atanır.
second_arr = arr

# Atanan değişkenin değerini değiştiririz.
second_arr[0] = 50

# ve asıl dizimiz olan arr dizisinde bu değişiklik görünür
print(arr)
```

    [50 20 30 40]
    

### **Dizi şeklini alma (Shape)**

Bir dizinin şeklini almak için shape kullanılır.


```python
# Dizinin tanımlanması
arr = np.array([[10, 20, 30, 40], [50, 60, 70, 80]])

print(arr.shape) #(2,4)


```

    (2, 4)
    

*Bu dizinin boyutunun 2 olduğu ve 4 öğeye sahip olduğu görülmektedir.*

### **Dizi yeniden şekillendirme (Reshaping)**

Dizimizi yeniden şekillendirmek istersek reshape methodu kullanılır.


```python
# Bir boyutlu dizi tanımlanması
arr = np.array([10, 20, 30, 40, 50, 60])

# Reshape kullanılarak elde edilen yeni dizinin tanımlanması
arr2 = arr.reshape(2,3)

print(arr2)
```

    [[10 20 30]
     [40 50 60]]
    


```python
arr2 = arr.reshape(3,2)

print(arr2)
```

    [[10 20]
     [30 40]
     [50 60]]
    

### **Bir numpy dizisini ekrana basmak**

Bir numpy dizisini ekrana basmak istersek döngüleri kullanabilir.

Bir boyutlu dizinin ekrana basılması;


```python
# Dizimizin tanımlanması
arr = np.array([10, 20, 30, 40, 50])

for i in arr:
  print(i)
```

    10
    20
    30
    40
    50
    

Çok boyutlu dizinin ekrana basılması;


```python
# Dizimizin tanımlanması
arr = np.array([[10, 20], [30, 40], [50, 60]])

for i in arr:
  print(i)
```

    [10 20]
    [30 40]
    [50 60]
    

Çok boyutlu dizinin her elemanını ayrı bir şekilde ekrana basmak için;


```python
# Dizimizin tanımlanması
arr = np.array([[10, 20], [30, 40], [50, 60]])

for i in arr:
  for value in i:
    print(value)
```

    10
    20
    30
    40
    50
    60
    

Döngülerin dışında bir diziyi ekrana basmak için np.nditer methodunu kullanabiliriz.


```python
# Dizimizin tanımlanması
arr = np.array([[10, 20], [30, 40], [50, 60]])

for i in np.nditer(arr):
  print(i)
```

    10
    20
    30
    40
    50
    60
    

### **Dizileri birleştirme (concatenate)**

İki tane bir boyutlu dizinin birleştirilme işlemi;


```python
# Birinci dizinin tanımlanması.
arr1 = np.array([1,2,3,4,5])

# İkinci dizinin tanımlanması
arr2 = np.array([10, 20, 30, 40, 50])

# Birleştirilen dizilerin yeni bir değişkene atanması
concat_arr = np.concatenate((arr1, arr2))

print(concat_arr)
```

    [ 1  2  3  4  5 10 20 30 40 50]
    

İki tane iki boyutlu dizinin birleştirilme işlemi (axis=1);


```python
# Birinci dizinin tanımlanması
arr1 = np.array([[1, 2], [3, 4]])

# İkinci dizinin tanımlanması
arr2 = np.array([[10, 20], [30, 40]])

# Birleştirilen dizilerin yeni bir değişkene atanması
concat_arr = np.concatenate((arr1, arr2), axis = 1)

print(concat_arr)
```

    [[ 1  2 10 20]
     [ 3  4 30 40]]
    

### **Dizileri bölmek (Split)**

Bir diziyi bölmek istediğimizde array_split methodunu kullanabiliriz.

Bir boyutlu diziyi bölmek;


```python
# Dizinin tanımlanması
arr = np.array([10, 20, 30, 40, 50, 60])

# Diziyi parçalara bölüp değişkene atanma işlemi
split_arr = np.array_split(arr, 2)

print(split_arr)
```

    [array([10, 20, 30]), array([40, 50, 60])]
    


```python
# Dizinin tanımlanması
arr = np.array([10, 20, 30, 40, 50, 60])

# Diziyi parçalara bölüp değişkene atanma işlemi
split_arr = np.array_split(arr, 3)

print(split_arr)
```

    [array([10, 20]), array([30, 40]), array([50, 60])]
    

İki boyutlu diziyi bölmek;


```python
# iki boyutlu dizinin tanımlanması
arr = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], [11, 12]])

# Diziyi parçalara bölüp değişkene atanma işlemi
split_arr = np.array_split(arr, 2)

print(split_arr)
```

    [array([[1, 2],
           [3, 4],
           [5, 6]]), array([[ 7,  8],
           [ 9, 10],
           [11, 12]])]
    


```python
# iki boyutlu dizinin tanımlanması
arr = np.array([[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], [11, 12]])

# Diziyi parçalara bölüp değişkene atanma işlemi
split_arr = np.array_split(arr, 3)

print(split_arr)
```

    [array([[1, 2],
           [3, 4]]), array([[5, 6],
           [7, 8]]), array([[ 9, 10],
           [11, 12]])]
    

### **Dizileri sıralama (Sorting)**

Dizimizi sıralamak istersek sort methodu kullanabiliriz

Bir boyutlu diziyi sıralamak;


```python
# Dizinin tanımlanması
arr = np.array([300, 20, 500, 1, 100])

# Sıralanan dizinin değişkene atanma işlemi
sorted_array = np.sort(arr)

print(sorted_array)
```

    [  1  20 100 300 500]
    

İki boyutlu diziyi sıralamak;


```python
# Dizinin tanımlanması
arr = np.array([[30, 10, 20], [60, 40, 50]])

# Sıralanan dizinin değişkene atanma işlemi
sorted_array = np.sort(arr)

print(sorted_array)
```

    [[10 20 30]
     [40 50 60]]
    

### Fancy indexing

Dizi öğelerimizi kolayca filtrelememize yarar. 


```python
# Dizinin tanımlanması
arr = np.array([10, 20, 30, 40, 50])

# Filtreleme ile dizinin bazı elemanlarını değişkene atma
filtered_arr = arr[arr > 30]

print(filtered_arr)
```

    [40 50]
    

*fancy indexing ile dizimize şunu dedik 30 değerinden büyük değerleri bizlere getir*


```python
# Dizinin tanımlanması
arr = np.array([10, 11, 12, 13, 14, 15])

# Sadece çift sayıları aldığımız değişkenin tanımlanması
even_arr = arr[arr % 2 == 0]

print(even_arr)
```

    [10 12 14]
    

*fancy indexing ile dizimizdeki çift sayıları alma işlemi*

### Rastgele dizi oluşturma

*   Rastgele tam sayılardan oluşan bir dizi oluşturmak istersek np.random.randint methodunu kullanabiliriz.
*   Rastgele rasyonel sayılar (float) oluşturmak istersek np.random.rand methodunu kullanabiliriz.


Bir boyutlu rastgele tam sayı dizisi oluşturmak;


```python
# Dizimizin tanımlanması
arr = np.random.randint(20, size=(5))

print(arr)
```

    [15 18 14  7  4]
    

*Oluşturduğumuz rastgele dizimizde np.random.randint methodunun ilk parametresi 0'dan 20'ye kadar olan sayılar arasından rastgele seçmeyi, ikinci parametresi ile dizimizin büyüklüğünü belirtir.*

İki boyutlu rastgele tam sayı dizisi oluşturmak;


```python
# Dizimizin tanımlanması
arr = np.random.randint(100, size=(2,5))

print(arr)
```

    [[66 65 93 86 53]
     [23 93 49 35 37]]
    

*Oluşturmuş olduğumuz dizimizde np.random.randint methodunun ilk parametresi 0'dan 100'e kadar rastgele değerler seçer, ikinci parametresinde ilk değer boyutunu ikinci değer ise eleman sayısını belirtir.*

### Aritmetik işlemler

*   Toplama işlemi için **add** methodunu kullanabiliriz.
*   Çıkarma işlemi için **subract** methodunu kullanabiliriz.
*   Çarpma işlemi için **multiply** methodunu kullanabiliriz.
*   Bölme işlemi için **divide** methodunu kullanabiliriz.
*   Üs alma işlemi için **power** methodunu kullanabiliriz.
*   Kalan alma işlemi için **remainder** methodunu kullanabiliriz.
*   Mod alma işlemi için **mod** methodunu kullanabiliriz.
*   Mutlak değer işlemi için **absolute** methodunu kullanabiliriz.

#### Toplama (add)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([10, 20, 30, 40, 50])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

add_arr = np.add(arr1, arr2)

print(add_arr)
```

    [11 22 33 44 55]
    

*Birinci dizimiz ile ikinci dizimizin elemanları sıralı bir şekilde toplama işlemini yaptık.*

#### Çıkarma (subtract)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([10, 20, 30, 40, 50])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

sub_arr = np.subtract(arr1, arr2)

print(sub_arr)
```

    [ 9 18 27 36 45]
    

*Birinci dizimizden ikinci dizimizi çıkartma işlemini sıralı bir şekilde uyguladık.*

#### Çarpma (multiply)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([10, 20, 30, 40, 50])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

multiply_arr = np.multiply(arr1, arr2)

print(multiply_arr)
```

    [ 10  40  90 160 250]
    

*Birinci dizimiz ile ikinci dizimizi sıralı olarak çarpma işlemini uyguladık.*

#### Bölme (divide)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([11, 21, 31, 41, 51])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

divide_arr = np.divide(arr1, arr2)

print(divide_arr)
```

    [11.         10.5        10.33333333 10.25       10.2       ]
    

*Birinci dizimizi ikinci dizimize böldük ve elde ettiğimiz dizi rasyonel sayılardan (float) oluşan bir dizi oldu.*

#### Üs alma (power)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([11, 21, 31, 41, 51])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

power_arr = np.power(arr1, arr2)

print(power_arr)
```

    [       11       441     29791   2825761 345025251]
    

*Birinci dizimize ikinci dizimizde bulunan değerleri sırayla üs olarak aldık.*

#### Kalan (remainder)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([11, 21, 34, 45, 57])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

remainder_arr = np.remainder(arr1, arr2)

print(remainder_arr)
```

    [0 1 1 1 2]
    

*Birinci dizimizin ikinci dizimize bölünmesinden kalanları alma işlemi yaptık.*

#### Mod (mod)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([11, 21, 34, 45, 57])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

mod_arr = np.mod(arr1, arr2)

print(mod_arr)
```

    [0 1 1 1 2]
    

*Birinci dizimizin ikinci dizimize bölünmesinden kalanları alma işlemi yaptık.*

#### Mutlak değer (absolute)


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([-11, 21, -34, 45, -57])

absolute_arr = np.absolute(arr1)

print(absolute_arr)
```

    [11 21 34 45 57]
    

*Dizimize mutlak değer işlemi uyguladık.*

### Dizi içerisinde aritmetik işlemler

*   Toplama
*   Fark
*   Çarpım

#### Toplama (Summations)


```python
# Dizimizin tanımlanması
arr = np.array([10, 20, 30, 40, 50])

# Dizimizin elemanlarının toplanıp yeni değişkene atılması
summation_arr = np.sum(arr)

print(summation_arr)
```

    150
    

Axis ile toplama;


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([10, 20, 30, 40, 50])

# İkinci dizimizin tanımlanması
arr2 = np.array([1, 2, 3, 4, 5])

# Toplanan değerleri yeni değişkene atılma işlemi
summation_arr = np.sum([arr1, arr2], axis = 1)

print(summation_arr)
```

    [150  15]
    

*Birinci dizimizin elemanlarını topladık ve ikinci dizimizin elemanlarını topladık böylece ayrı ayrı toplama işlemi yapmış olduk. Eğer axis değerine 0 atasaydık arr1 ile arr2 nin elemanlarının hepsini toplayacaktı yani çıktı 165 olacaktı.*

#### Fark (Differences)


```python
# Dizimizin tanımlanması
arr = np.array([10, 22, 35, 49, 5])

# Çıkarılan değerleri yeni değişkene atılma işlemi
diff_arr = np.diff(arr)

print(diff_arr)
```

    [ 12  13  14 -44]
    

*Burada dizimizin elamanlarının bir önceki elemanlanla çıkarılma işlemini yapıyoruz yani şu şekilde:*
22-10 = 12,
35-22 = 13,
49-35 = 14,
5-49 = -44 

#### Çarpım (products)


```python
# Dizimizin tanımlanması
arr = np.array([1, 2, 3, 4])

# Dizimizin elemanlarının çarpılıp değişkene atılma işlemi
mult_arr = np.prod(arr)

print(mult_arr)
```

    24
    

*Dizimizdeki elemanların birbirleriyle çarpılma işlemini yaptık.*

Axis ile çarpma;


```python
# Birinci dizimizin tanımlanması
arr1 = np.array([1, 2, 3])

# İkinci dizimizin tanımlanması
arr2 = np.array([3, 4, 5])

# Çarpılan değerlerin değişkene atılma işlemi
mult_arr = np.prod([arr1, arr2], axis=1)

print(mult_arr)
```

    [ 6 60]
