# Makine Öğrenmesine Giriş: Adım Adım Rehber

## İçindekiler
1. [Temel Kavramları Anlamak](#temel-kavramları-anlamak)
2. [Programlama Dili Seçimi](#programlama-dili-seçimi)
3. [Python Temelleri](#python-temelleri)
4. [R Temelleri](#r-temelleri)
5. [Julia Temelleri](#julia-temelleri)
6. [Veri Analizi ve Görselleştirme](#veri-analizi-ve-görselleştirme)
7. [Makine Öğrenmesi Temelleri](#makine-öğrenmesi-temelleri)
8. [Makine Öğrenmesi Kütüphaneleri ile Çalışma](#makine-öğrenmesi-kütüphaneleri-ile-çalışma)
9. [İlk Projeyi Tamamlama](#ilk-projeyi-tamamlama)
10. [İleri Seviye Konulara Geçiş](#ileri-seviye-konulara-geçiş)
11. [Sürekli Öğrenme ve Projeler](#sürekli-öğrenme-ve-projeler)
12. [Kaynaklar ve Öneriler](#kaynaklar-ve-öneriler)

## Temel Kavramları Anlamak

Makine öğrenmesine başlamadan önce, bazı temel kavramları anlamak önemlidir. Bu kavramlar, makine öğrenmesi projelerinde sıkça karşılaşacağınız terimlerdir.

### Veri (Data)
Veri, makine öğrenmesi modellerinin eğitilmesi için kullanılan bilgidir. Veriler çeşitli biçimlerde olabilir: sayılar, metinler, resimler, vb. 

**Örnek:**
Bir ev fiyatı tahmini modeli için veri seti şu şekilde olabilir:
| Oda Sayısı | Banyo Sayısı | Alan (m²) | Fiyat (TL)  |
|------------|--------------|-----------|-------------|
| 3          | 2            | 120       | 500,000     |
| 2          | 1            | 80        | 300,000     |
| 4          | 3            | 200       | 750,000     |

### Model
Model, verileri analiz eden ve tahminlerde bulunan matematiksel yapıdır. Model, verilerden öğrenir ve yeni verilere dayanarak tahminler yapabilir.

**Örnek:**
Ev fiyatı tahmini modeli, oda sayısı, banyo sayısı ve alan gibi özellikleri kullanarak bir evin fiyatını tahmin eder.

### Algoritma
Algoritma, modeli oluşturmak ve eğitmek için kullanılan adımlar dizisidir. Algoritmalar, verilerden öğrenme sürecini tanımlar.

**Örnek:**
Ev fiyatı tahmini için kullanılan algoritma, doğrusal regresyon (linear regression) olabilir. Bu algoritma, bağımsız değişkenler (oda sayısı, banyo sayısı, alan) ile bağımlı değişken (fiyat) arasındaki ilişkiyi öğrenir.

### Eğitim (Training)
Eğitim, modeli verilerle besleyerek öğrenmesini sağlama sürecidir. Model, verilerden desenleri öğrenir ve bu desenlere dayanarak tahminlerde bulunmayı öğrenir.

**Örnek:**
Ev fiyatı tahmini modeli, eğitim verileri kullanılarak eğitilir:
| Oda Sayısı | Banyo Sayısı | Alan (m²) | Fiyat (TL)  |
|------------|--------------|-----------|-------------|
| 3          | 2            | 120       | 500,000     |
| 2          | 1            | 80        | 300,000     |
| 4          | 3            | 200       | 750,000     |

### Test (Testing)
Test, modelin performansını değerlendirmek için yeni veriler kullanma sürecidir. Test verileri, modelin daha önce görmediği verilerdir.

**Örnek:**
Model, test verileri kullanılarak değerlendirilir:
| Oda Sayısı | Banyo Sayısı | Alan (m²) | Gerçek Fiyat (TL) | Tahmin Edilen Fiyat (TL) |
|------------|--------------|-----------|-------------------|--------------------------|
| 3          | 2            | 110       | 480,000           | 470,000                  |
| 2          | 1            | 85        | 320,000           | 310,000                  |
| 4          | 3            | 210       | 780,000           | 760,000                  |

### Doğruluk (Accuracy)
Doğruluk, modelin ne kadar doğru tahminlerde bulunduğunu gösteren bir ölçüttür. Genellikle doğru tahminlerin toplam tahminlere oranı olarak hesaplanır.

**Örnek:**
Eğer model, 10 test verisinden 8'inde doğru tahmin yapmışsa, doğruluk oranı %80'dir.

Bu temel kavramlar, makine öğrenmesi sürecinde sıkça karşılaşacağınız terimlerdir. Her bir kavram, makine öğrenmesi projelerinizin başarılı olmasına katkı sağlayacaktır.


## Programlama Dili Seçimi

Makine öğrenmesi projeleri için hangi programlama dilini seçeceğinize karar vermek önemli bir adımdır. Her dilin kendi avantajları ve kullanım alanları vardır. İşte Python, R ve Julia'nın makine öğrenmesinde nasıl kullanıldığını ve örnekleri:

### Python
Python, makine öğrenmesi alanında en popüler dillerden biridir. Geniş kütüphane desteği, kullanıcı dostu sözdizimi ve büyük topluluğu ile bilinir.

**Örnek: Basit Lineer Regresyon (Scikit-Learn ile)**
```python
import numpy as np
from sklearn.linear_model import LinearRegression

# Veriyi oluşturma
X = np.array([[1, 1], [1, 2], [2, 2], [2, 3]])
y = np.dot(X, np.array([1, 2])) + 3

# Modeli oluşturma ve eğitme
model = LinearRegression().fit(X, y)

# Tahmin yapma
predictions = model.predict(np.array([[3, 5]]))
print(predictions)
```
### R
R, istatistiksel analiz ve veri görselleştirme için güçlü bir dildir. Özellikle veri bilimciler ve araştırmacılar arasında popülerdir.

**Örnek: Basit Lineer Regresyon (lm() ile)**

```R
# Veriyi oluşturma
X1 <- c(1, 1, 2, 2)
X2 <- c(1, 2, 2, 3)
y <- 1 * X1 + 2 * X2 + 3

# Veriyi veri çerçevesi olarak hazırlama
data <- data.frame(X1, X2, y)

# Modeli oluşturma ve eğitme
model <- lm(y ~ X1 + X2, data=data)

# Tahmin yapma
new_data <- data.frame(X1=3, X2=5)
predictions <- predict(model, new_data)
print(predictions)
```
### Julia
Julia, yüksek performanslı hesaplamalar için optimize edilmiştir ve kullanıcı dostu bir sözdizimine sahiptir. Bilimsel hesaplamalar ve veri analizi için uygundur.

**Örnek: Basit Lineer Regresyon (GLM.jl ile)**

```julia
using DataFrames
using GLM

# Veriyi oluşturma
X1 = [1, 1, 2, 2]
X2 = [1, 2, 2, 3]
y = 1 .* X1 .+ 2 .* X2 .+ 3

# Veriyi veri çerçevesi olarak hazırlama
data = DataFrame(X1=X1, X2=X2, y=y)

# Modeli oluşturma ve eğitme
model = lm(@formula(y ~ X1 + X2), data)

# Tahmin yapma
new_data = DataFrame(X1=[3], X2=[5])
predictions = predict(model, new_data)
println(predictions)
```
### Hangi Dili Seçmeliyim?
- Python: Genel amaçlı makine öğrenmesi ve derin öğrenme projeleri için idealdir. Geniş kütüphane desteği ve topluluk desteği ile bilinir.
- R: İstatistiksel analiz ve veri görselleştirme projeleri için güçlüdür. Veri bilimi ve araştırma alanlarında yaygın olarak kullanılır.
- Julia: Yüksek performans gerektiren projeler için uygundur. Bilimsel hesaplamalar ve büyük veri işlemleri için idealdir.

## Python Temelleri Ve Veri Analizi Yapıları

[Python Temel Yapıları Ve Örnekleri](PythonBasics.md)

## R Temelleri Ve Veri Analizi Yapıları

[R Temel Yapıları Ve Örnekleri](R_LanguageBasics.md)

## Julia Temelleri Ve Veri Analizi Yapıları

[Julia Temel Yapıları Ve Örnekleri](JuliaBasics.md)

## Makine Öğrenmesi Temelleri

Makine öğrenmesi, bilgisayarların verilerden öğrenmesini ve bu bilgileri kullanarak tahminlerde bulunmasını sağlayan bir yapay zeka dalıdır. Temel olarak üç ana kategoriye ayrılır: denetimli öğrenme, denetimsiz öğrenme ve pekiştirmeli öğrenme.

### 1. Denetimli Öğrenme (Supervised Learning)

Denetimli öğrenmede, modelin eğitilmesi için giriş ve çıkış verileri (etiketli veriler) kullanılır. Model, bu verilerden öğrenir ve yeni veriler için tahminlerde bulunur.

#### Örnek: Doğrusal Regresyon (Linear Regression)
Doğrusal regresyon, iki değişken arasındaki ilişkiyi modellemek için kullanılır. Hedef değişken (bağımlı değişken) ile açıklayıcı değişkenler (bağımsız değişkenler) arasındaki doğrusal ilişkiyi tanımlar.

```python
import numpy as np
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt

# Veri oluşturma
X = np.array([[1], [2], [3], [4], [5]])
y = np.array([1, 4, 9, 16, 25])

# Model oluşturma ve eğitme
model = LinearRegression()
model.fit(X, y)

# Tahmin yapma
predictions = model.predict(X)

# Sonuçları görselleştirme
plt.scatter(X, y, color='blue')
plt.plot(X, predictions, color='red')
plt.title('Doğrusal Regresyon')
plt.xlabel('X Değeri')
plt.ylabel('Y Değeri')
plt.show()
```

#### Örnek: Lojistik Regresyon (Logistic Regression)
Lojistik regresyon, ikili sınıflandırma problemleri için kullanılan bir algoritmadır. Hedef değişken ikili (binary) olduğunda kullanılır.

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

# Veri yükleme
iris = load_iris()
X = iris.data
y = (iris.target == 0).astype(int)  # Setosa türü mü? Evet=1, Hayır=0

# Veri bölme
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Model oluşturma ve eğitme
model = LogisticRegression()
model.fit(X_train, y_train)

# Tahmin yapma
y_pred = model.predict(X_test)

# Doğruluk skoru
accuracy = accuracy_score(y_test, y_pred)
print(f"Doğruluk Skoru: {accuracy}")
```

### 2. Denetimsiz Öğrenme (Unsupervised Learning)

Denetimsiz öğrenmede, modelin eğitilmesi için yalnızca giriş verileri kullanılır (etiketsiz veriler). Model, verilerdeki desenleri ve yapıları keşfetmeye çalışır.

#### Örnek: K-Means Kümeleme (K-Means Clustering)
K-means kümeleme, verileri K adet küme/grup olacak şekilde ayıran bir algoritmadır. Her veri noktası, en yakın merkeze (centroid) atanır.

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Veri oluşturma
X = np.array([[1, 2], [1, 4], [1, 0], [10, 2], [10, 4], [10, 0]])

# Model oluşturma ve eğitme
kmeans = KMeans(n_clusters=2, random_state=0)
kmeans.fit(X)

# Tahmin yapma
labels = kmeans.predict(X)

# Sonuçları görselleştirme
plt.scatter(X[:, 0], X[:, 1], c=labels, cmap='viridis')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1], s=300, c='red')
plt.title('K-Means Kümeleme')
plt.xlabel('X Değeri')
plt.ylabel('Y Değeri')
plt.show()
```

### 3. Pekiştirmeli Öğrenme (Reinforcement Learning)

Pekiştirmeli öğrenmede, bir ajan (agent) bir ortamda (environment) hareket eder ve her eylem (action) için bir ödül veya ceza alır. Ajan, ödülleri maksimize etmek için en iyi stratejiyi öğrenmeye çalışır.

#### Örnek: Basit Pekiştirmeli Öğrenme (Simple Reinforcement Learning)
Bu örnek, klasik bir pekiştirmeli öğrenme problemini basitçe göstermek içindir. Genellikle, bu tür problemler daha karmaşık ortamlarda ve daha sofistike algoritmalarla çözülür.

```python
import numpy as np

# Parametreler
n_states = 10  # Durum sayısı
actions = ['left', 'right']  # Eylemler
epsilon = 0.1  # Keşif oranı
alpha = 0.1  # Öğrenme oranı
gamma = 0.9  # İndirim faktörü
episodes = 1000  # Bölüm sayısı

# Q-Tablosu
Q = np.zeros((n_states, len(actions)))

# Eğitim
for _ in range(episodes):
    state = np.random.randint(0, n_states)
    while state != n_states - 1:
        if np.random.uniform(0, 1) < epsilon:
            action = np.random.choice(actions)
        else:
            action = actions[np.argmax(Q[state])]

        next_state = state + 1 if action == 'right' else state - 1
        reward = 1 if next_state == n_states - 1 else 0

        Q[state, actions.index(action)] = Q[state, actions.index(action)] + \
                                          alpha * (reward + gamma * np.max(Q[next_state]) - Q[state, actions.index(action)])
        state = next_state

print("Öğrenilen Q-Tablosu:")
print(Q)
```

### 4. Model Değerlendirme ve Doğrulama

Makine öğrenmesi modellerinin performansını değerlendirmek ve doğrulamak için çeşitli metrikler ve yöntemler kullanılır.

#### Örnek: Doğruluk Skoru (Accuracy Score)
Doğruluk skoru, doğru tahminlerin toplam tahminlere oranını ölçer.

```python
from sklearn.metrics import accuracy_score

# Gerçek ve tahmin edilen etiketler
y_true = [0, 1, 1, 0, 1, 0, 1, 1]
y_pred = [0, 1, 0, 0, 1, 1, 1, 1]

# Doğruluk skoru hesaplama
accuracy = accuracy_score(y_true, y_pred)
print(f"Doğruluk Skoru: {accuracy}")
```

#### Örnek: Karışıklık Matrisi (Confusion Matrix)
Karışıklık matrisi, sınıflandırma problemlerinde doğru ve yanlış tahminlerin dağılımını gösterir.

```python
from sklearn.metrics import confusion_matrix

# Gerçek ve tahmin edilen etiketler
y_true = [0, 1, 1, 0, 1, 0, 1, 1]
y_pred = [0, 1, 0, 0, 1, 1, 1, 1]

# Karışıklık matrisi hesaplama
cm = confusion_matrix(y_true, y_pred)
print("Karışıklık Matrisi:")
print(cm)
```

### 5. Hiperparametre Ayarı

Makine öğrenmesi modellerinin performansını iyileştirmek için hiperparametreler ayarlanabilir. Hiperparametre ayarı, modelin performansını optimize etmek için kullanılır.

#### Örnek: Grid Search ile Hiperparametre Ayarı
Grid Search, farklı hiperparametre kombinasyonlarını deneyerek en iyi performansı bulmayı sağlar.

```python
from sklearn.model_selection import GridSearchCV
from sklearn.svm import SVC

# Veri seti
X = [[1, 2], [2, 3], [3, 4], [4, 5], [5, 6], [6, 7]]
y = [0, 0, 1, 1, 0, 1]

# Model ve hiperparametreler
model = SVC()
parameters = {'kernel': ('linear', 'rbf'), 'C': [1, 10]}

# Grid Search
clf = GridSearchCV(model, parameters)
clf.fit(X, y)

print("En İyi Parametreler:")
print(clf.best_params_)
```
