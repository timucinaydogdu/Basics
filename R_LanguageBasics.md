## R Temelleri

R, istatistiksel analiz ve veri görselleştirme için güçlü bir programlama dilidir. Veri bilimciler ve araştırmacılar tarafından yaygın olarak kullanılır. İşte R'nin temel konuları ve örnekleriyle birlikte açıklamaları:

### 1. Değişkenler ve Veri Türleri

R'de değişkenler, veri tutmak için kullanılır. Değişkenlere değer atamak için `<-` operatörü kullanılır.

**Örnek:**
```r
# Değişken atama
x <- 10        # Numeric (sayısal değer)
y <- 3.14      # Numeric (ondalıklı sayı)
name <- "Tim"  # Character (metin)
is_active <- TRUE  # Logical (mantıksal değer)

# Değişkenleri yazdırma
print(x)
print(y)
print(name)
print(is_active)
```

### 2. Vektörler

Vektörler, aynı türdeki verilerin bir arada tutulduğu yapılardır. `c()` fonksiyonu ile oluşturulur.

**Örnek:**
```r
# Vektör oluşturma
numbers <- c(1, 2, 3, 4, 5)
names <- c("Tim", "Tom", "Jim")

# Vektör elemanlarına erişim
print(numbers[1])
print(names[2])
```

### 3. Matrisler

Matrisler, iki boyutlu veri yapılarıdır ve `matrix()` fonksiyonu ile oluşturulur.

**Örnek:**
```r
# Matris oluşturma
matrix_data <- matrix(1:9, nrow=3, ncol=3)

# Matris elemanlarına erişim
print(matrix_data[1, 1])
print(matrix_data[3, 3])
```

### 4. Veri Çerçeveleri (Data Frames)

Veri çerçeveleri, farklı türdeki verilerin bir arada tutulduğu yapılardır. `data.frame()` fonksiyonu ile oluşturulur.

**Örnek:**
```r
# Veri çerçevesi oluşturma
data <- data.frame(
  name = c("Tim", "Tom", "Jim"),
  age = c(35, 30, 40),
  city = c("Adana", "Istanbul", "Ankara")
)

# Veri çerçevesi elemanlarına erişim
print(data$name)
print(data$age[2])
```

### 5. Fonksiyonlar

Fonksiyonlar, belirli bir görevi yerine getiren kod bloklarıdır. Fonksiyonlar, kodun tekrar kullanılabilirliğini sağlar.

**Örnek: Basit Fonksiyon**
```r
# Fonksiyon tanımlama
greet <- function(name) {
  print(paste("Merhaba,", name))
}

# Fonksiyonu çağırma
greet("Tim")
```

### 6. Koşul Yapıları

Koşul yapıları, programın akışını kontrol etmek için kullanılır. `if-else` yapıları R'de yaygındır.

**Örnek: If-Else**
```r
# If-Else örneği
age <- 18
if (age >= 18) {
  print("Yetişkinsiniz.")
} else {
  print("Yetişkin değilsiniz.")
}
```

### 7. Döngüler

Döngüler, belirli bir kod bloğunu tekrar tekrar çalıştırmak için kullanılır. `for` ve `while` döngüleri R'de yaygındır.

**Örnek: For Döngüsü**
```r
# For döngüsü örneği
for (i in 1:5) {
  print(i)
}
```

**Örnek: While Döngüsü**
```r
# While döngüsü örneği
count <- 0
while (count < 5) {
  print(count)
  count <- count + 1
}
```

### 8. Paketler ve Kütüphaneler

R'de paketler ve kütüphaneler, ek fonksiyonlar ve veri setleri sağlar. Paketler `install.packages()` ile yüklenir ve `library()` ile kullanılır.

**Örnek: ggplot2 Paketini Kullanma**
```r
# ggplot2 paketini yükleme ve kullanma
install.packages("ggplot2")
library(ggplot2)

# Örnek veri seti ile basit bir grafik çizme
data <- data.frame(
  x = c(1, 2, 3, 4, 5),
  y = c(3, 7, 6, 8, 9)
)

ggplot(data, aes(x=x, y=y)) + geom_point()
```

### 9. Dosya İşlemleri

R, dosya okuma ve yazma işlemlerini kolayca yapmanızı sağlar.

**Örnek: CSV Dosyası Okuma**
```r
# CSV dosyasını okuma
data <- read.csv("example.csv")

# Veriyi görüntüleme
print(data)
```

**Örnek: CSV Dosyasına Yazma**
```r
# Veri çerçevesi oluşturma
data <- data.frame(
  name = c("Tim", "Tom", "Jim"),
  age = c(35, 30, 40),
  city = c("Adana", "Istanbul", "Ankara")
)

# CSV dosyasına yazma
write.csv(data, "output.csv")
```
## R Veri Analizi Yapıları

R için Gereken Kütüphaneler
```r
Kodu kopyala
install.packages("dplyr")
install.packages("ggplot2")
```
### dplyr ile Veri Analizi
```r
library(dplyr)

# Veri çerçevesi oluşturma
data <- data.frame(
  name = c("Tim", "Tom", "Jim"),
  age = c(35, 30, 40),
  city = c("Adana", "Istanbul", "Ankara")
)

# Temel veri manipülasyonu
data <- data %>%
  filter(age > 30) %>%
  arrange(desc(age))
print(data)
```
### ggplot2 ile Veri Görselleştirme
```r
Kodu kopyala
library(ggplot2)

# Örnek veri seti ile basit bir grafik çizme
data <- data.frame(
  x = 1:10,
  y = c(3, 7, 6, 8, 9, 12, 15, 14, 18, 20)
)

ggplot(data, aes(x=x, y=y)) +
  geom_point() +
  ggtitle("Basit Dağılım Grafiği") +
  xlab("X Ekseni") +
  ylab("Y Ekseni")
```