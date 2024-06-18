## Python Temelleri

Python, öğrenmesi kolay ve güçlü bir programlama dilidir. Makine öğrenmesi ve veri bilimi projelerinde yaygın olarak kullanılır. İşte Python'un temel konuları ve örnekleriyle birlikte açıklamaları:

### 1. Değişkenler ve Veri Türleri

Python'da değişkenler, veri tutmak için kullanılır. Değişkenlere değer atamak için `=` operatörü kullanılır.

**Örnek:**
```python
# Değişken atama
x = 10        # Integer (tam sayı)
y = 3.14      # Float (ondalıklı sayı)
name = "Tim"  # String (metin)
is_active = True  # Boolean (doğru/yanlış)

# Değişkenleri yazdırma
print(x)
print(y)
print(name)
print(is_active)
```

### 2. Kontrol Yapıları

Kontrol yapıları, programın akışını kontrol etmek için kullanılır. En yaygın kontrol yapıları `if-else` ve döngülerdir (`for` ve `while`).

**Örnek: If-Else**
```python
# If-Else örneği
age = 18
if age >= 18:
    print("Yetişkinsiniz.")
else:
    print("Yetişkin değilsiniz.")
```

**Örnek: For Döngüsü**
```python
# For döngüsü örneği
for i in range(5):
    print(i)
```

**Örnek: While Döngüsü**
```python
# While döngüsü örneği
count = 0
while count < 5:
    print(count)
    count += 1
```

### 3. Fonksiyonlar

Fonksiyonlar, belirli bir görevi yerine getiren kod bloklarıdır. Fonksiyonlar, kodun tekrar kullanılabilirliğini sağlar.

**Örnek: Basit Fonksiyon**
```python
# Fonksiyon tanımlama
def greet(name):
    print(f"Merhaba, {name}!")

# Fonksiyonu çağırma
greet("Tim")
```

### 4. Kütüphaneler ve Modüller

Python'da kütüphaneler ve modüller, kodu organize etmek ve yeniden kullanmak için kullanılır. Bir modül, diğer Python dosyalarından işlevleri ve değişkenleri içerebilir.

**Örnek: Matematik Kütüphanesini Kullanma**
```python
# Math kütüphanesini içe aktarma
import math

# Math kütüphanesini kullanma
print(math.sqrt(16))  # Karekök hesaplama
print(math.pi)        # Pi sayısı
```

### 5. Liste, Sözlük ve Demetler

Python'da veri yapılarını anlamak önemlidir. En yaygın kullanılan veri yapıları listeler, sözlükler ve demetlerdir.

**Örnek: Liste**
```python
# Liste oluşturma
numbers = [1, 2, 3, 4, 5]

# Listeye eleman ekleme
numbers.append(6)

# Listeden eleman çıkarma
numbers.remove(3)

# Liste elemanlarına erişim
print(numbers[0])
print(numbers[-1])
```

**Örnek: Sözlük**
```python
# Sözlük oluşturma
person = {
    "name": "Tim",
    "age": 38,
    "city": "Adana"
}

# Sözlükteki değerlere erişim
print(person["name"])
print(person.get("age"))

# Sözlüğe yeni anahtar-değer çifti ekleme
person["job"] = "Programcı"

# Sözlükten anahtar-değer çifti silme
del person["city"]
```

**Örnek: Demet**
```python
# Demet oluşturma
fruits = ("apple", "banana", "cherry")

# Demet elemanlarına erişim
print(fruits[0])
print(fruits[1:])
```

### 6. Dosya İşlemleri

Python, dosya okuma ve yazma işlemlerini kolayca yapmanızı sağlar.

**Örnek: Dosya Okuma**
```python
# Dosya açma ve okuma
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

**Örnek: Dosya Yazma**
```python
# Dosyaya yazma
with open("example.txt", "w") as file:
    file.write("Bu, bir örnek yazıdır.")
```
## Python Veri Analizi Yapıları

### Python için Gereken Kütüphaneler
```python
# Gerekli kütüphaneleri yükleme
!pip install numpy pandas matplotlib seaborn
```
NumPy ile Veri Analizi

```python
import numpy as np
```

### NumPy dizisi oluşturma
```python
data = np.array([1, 2, 3, 4, 5])

# Temel istatistiksel hesaplamalar
mean = np.mean(data)
std_dev = np.std(data)
print("Ortalama:", mean)
print("Standart Sapma:", std_dev)
```

### Pandas ile Veri Analizi
```python
import pandas as pd

# Veri çerçevesi oluşturma
data = pd.DataFrame({
    "name": ["Tim", "Tom", "Jim"],
    "age": [35, 30, 40],
    "city": ["Adana", "Istanbul", "Ankara"]
})

# Veri çerçevesini görüntüleme
print(data)

# Temel analizler
print(data.describe())
```

### Matplotlib ve Seaborn ile Veri Görselleştirme
```python
import matplotlib.pyplot as plt
import seaborn as sns

# Matplotlib ile Basit Grafik Çizme
x = [1, 2, 3, 4, 5]
y = [1, 4, 9, 16, 25]

plt.plot(x, y)
plt.title("Basit Çizgi Grafiği")
plt.xlabel("X Ekseni")
plt.ylabel("Y Ekseni")
plt.show()
```
### Seaborn ile Dağılım Grafiği
```python
data = sns.load_dataset("iris")

sns.scatterplot(x="sepal_length", y="sepal_width", data=data)
plt.title("Sepal Length vs Sepal Width")
plt.show()
```