## Julia Temelleri

Julia, yüksek performanslı hesaplamalar ve veri analizi için optimize edilmiş modern bir programlama dilidir. Kullanımı kolay ve esnek bir sözdizimine sahiptir. İşte Julia'nın temel konuları ve örnekleriyle birlikte açıklamaları:

### 1. Değişkenler ve Veri Türleri

Julia'da değişkenler, veri tutmak için kullanılır. Değişkenlere değer atamak için `=` operatörü kullanılır.

**Örnek:**
```julia
# Değişken atama
x = 10        # Integer (tam sayı)
y = 3.14      # Float (ondalıklı sayı)
name = "Tim"  # String (metin)
is_active = true  # Boolean (doğru/yanlış)

# Değişkenleri yazdırma
println(x)
println(y)
println(name)
println(is_active)
```

### 2. Vektörler ve Matrisler

Julia'da vektörler ve matrisler, sayısal hesaplamalar için önemli veri yapılarıdır.

**Örnek: Vektör**
```julia
# Vektör oluşturma
numbers = [1, 2, 3, 4, 5]

# Vektör elemanlarına erişim
println(numbers[1])
println(numbers[end])
```

**Örnek: Matris**
```julia
# Matris oluşturma
matrix_data = [1 2 3; 4 5 6; 7 8 9]

# Matris elemanlarına erişim
println(matrix_data[1, 1])
println(matrix_data[3, 3])
```

### 3. Fonksiyonlar

Fonksiyonlar, belirli bir görevi yerine getiren kod bloklarıdır. Fonksiyonlar, kodun tekrar kullanılabilirliğini sağlar.

**Örnek: Basit Fonksiyon**
```julia
# Fonksiyon tanımlama
function greet(name)
    println("Merhaba, $name!")
end

# Fonksiyonu çağırma
greet("Tim")
```

### 4. Koşul Yapıları

Koşul yapıları, programın akışını kontrol etmek için kullanılır. `if-else` yapıları Julia'da yaygındır.

**Örnek: If-Else**
```julia
# If-Else örneği
age = 18
if age >= 18
    println("Yetişkinsiniz.")
else
    println("Yetişkin değilsiniz.")
end
```

### 5. Döngüler

Döngüler, belirli bir kod bloğunu tekrar tekrar çalıştırmak için kullanılır. `for` ve `while` döngüleri Julia'da yaygındır.

**Örnek: For Döngüsü**
```julia
# For döngüsü örneği
for i in 1:5
    println(i)
end
```

**Örnek: While Döngüsü**
```julia
# While döngüsü örneği
count = 0
while count < 5
    println(count)
    count += 1
end
```

### 6. Paketler ve Kütüphaneler

Julia'da paketler ve kütüphaneler, ek fonksiyonlar ve veri setleri sağlar. Paketler `Pkg.add()` ile yüklenir ve `using` ile kullanılır.

**Örnek: Plots Paketini Kullanma**
```julia
# Plots paketini yükleme ve kullanma
using Pkg
Pkg.add("Plots")
using Plots

# Örnek veri seti ile basit bir grafik çizme
x = 1:10
y = rand(10)
plot(x, y, title="Basit Grafik", xlabel="X Ekseni", ylabel="Y Ekseni")
```

### 7. Veri Çerçeveleri (DataFrames)

Veri çerçeveleri, farklı türdeki verilerin bir arada tutulduğu yapılardır. `DataFrames.jl` paketi ile kullanılır.

**Örnek: Veri Çerçevesi Oluşturma ve Kullanma**
```julia
# DataFrames paketini yükleme ve kullanma
using Pkg
Pkg.add("DataFrames")
using DataFrames

# Veri çerçevesi oluşturma
data = DataFrame(name = ["Tim", "Tom", "Jim"], age = [35, 30, 40], city = ["Adana", "Istanbul", "Ankara"])

# Veri çerçevesi elemanlarına erişim
println(data[!, :name])
println(data[2, :age])
```

### 8. Dosya İşlemleri

Julia, dosya okuma ve yazma işlemlerini kolayca yapmanızı sağlar.

**Örnek: Dosya Okuma**
```julia
# Dosya okuma
content = read("example.txt", String)
println(content)
```

**Örnek: Dosya Yazma**
```julia
# Dosyaya yazma
open("example.txt", "w") do file
    write(file, "Bu, bir örnek yazıdır.")
end
```

## R Veri Analizi Yapıları

### Julia için Gereken Kütüphaneler
```julia
using Pkg
Pkg.add("DataFrames")
Pkg.add("Plots")
```
### DataFrames.jl ile Veri Analizi
```julia
using DataFrames

# Veri çerçevesi oluşturma
data = DataFrame(name = ["Tim", "Tom", "Jim"], age = [35, 30, 40], city = ["Adana", "Istanbul", "Ankara"])

# Temel veri manipülasyonu
filtered_data = filter(row -> row.age > 30, data)
println(filtered_data)
```
### Plots.jl ile Veri Görselleştirme
```julia
using Plots

# Örnek veri seti ile basit bir grafik çizme
x = 1:10
y = rand(10)

plot(x, y, title="Basit Grafik", xlabel="X Ekseni", ylabel="Y Ekseni")
```