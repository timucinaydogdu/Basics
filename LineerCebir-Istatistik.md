### Vektörler ve Matrisler

#### Vektör:
Bir vektör, sayılar dizisidir. Bu sayılar "eleman" olarak adlandırılır. Örneğin, \([2, 3, 5]\) bir vektördür. Vektörler genellikle bir çizgi üzerinde bir noktayı temsil eder.



#### Matris:
Bir matris, sayılarla dolu bir tablodur. Satırlar ve sütunlar halinde düzenlenmiştir. Örneğin:
\[ A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \]
Bu, iki satır ve iki sütundan oluşan bir matrisi gösterir.

### Matris İşlemleri:

#### Toplama ve Çıkarma:
İki matrisin aynı boyutlarda olması gerekir. Elemanlar aynı konumda toplanır veya çıkarılır. Örneğin:
\[ \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} + \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 6 & 8 \\ 10 & 12 \end{bmatrix} \]

#### Çarpma:
- **Skaler Çarpma:** Matrisin her elemanı bir sayı (skaler) ile çarpılır. Örneğin, 2 ile çarpma:
\[ 2 \cdot \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 2 & 4 \\ 6 & 8 \end{bmatrix} \]

- **Matris Çarpma:** Biraz daha karmaşıktır. İki matris çarpılırken, bir matrisin satırları ile diğer matrisin sütunları çarpılır ve toplanır. Örneğin:
\[ \begin{bmatrix} a & b \\ c & d \end{bmatrix} \cdot \begin{bmatrix} d & e \\ f & g \end{bmatrix} = \begin{bmatrix} (a*d + b*f) & (a*e + b*g) \\ (3*2 + 4*1) & (3*0 + 4*3) \end{bmatrix} = \begin{bmatrix} 4 & 6 \\ 10 & 12 \end{bmatrix} \]

### Determinant ve Ters Matris:

#### Determinant:
Bir kare matrisin determinantı, matrisi bir skaler sayıya indirger. 2x2 matris için:
\[ A = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \]
Determinantı:
\[ det(A) = ad - bc \]

#### Ters Matris:
Bir matrisin tersi, onu birim matrise (identity matrix) çarptığında birim matrisi (identity matrix) veren matristir. 2x2 matrisin tersi için:
\[ A^{-1} = \frac{1}{det(A)} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix} \]
Ancak, determinantı sıfır olan matrislerin tersi yoktur.

### Özel Matrisler:

#### Birim Matris (Identity Matrix):
Köşegen elemanları bir, diğer tüm elemanları sıfır olan matris:
\[ I = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \]

#### Sıfır Matris:
Tüm elemanları sıfır olan matris:
\[ 0 = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix} \]
# Vektörler ve Matrisler

## Vektörler

Bir vektör, sayılar dizisidir. Bu sayılar "eleman" olarak adlandırılır. Örneğin, \([v_1, v_2, v_3]\) bir vektördür. Vektörler genellikle bir çizgi üzerinde bir noktayı temsil eder.

**Python Kodu:**
```python
import numpy as np

# Vektör örneği
vektor = np.array([2, 3, 5])
print("Vektör:", vektor)
