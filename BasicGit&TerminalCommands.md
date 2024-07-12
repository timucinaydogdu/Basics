<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/121px-Python-logo-notext.svg.png" align="left" >

### Temel Git Komutları
<br><br>

1. **git init**: Yeni bir Git deposu oluşturur.
   ```sh
   git init
   ```

2. **git clone**: Var olan bir depoyu klonlar.
   ```sh
   git clone https://github.com/username/repository.git
   ```

3. **git add**: Değişiklikleri ekler.
   ```sh
   git add .
   ```

4. **git commit**: Değişiklikleri commit eder.
   ```sh
   git commit -m "Commit mesajı"
   ```

5. **git status**: Depo durumunu kontrol eder.
   
   ```sh
   git status
   ```
   
6. **git push**: Değişiklikleri uzak depoya gönderir.
   
   ```sh
   git push origin main
   ```
   
7. **git pull**: Uzak depodan değişiklikleri alır.
   ```sh
   git pull origin main
   ```

### İleri Seviye Git Komutları

#### Dallar (Branches) ve Çatallaşma (Branching)

1. **git branch**: Yeni bir dal oluşturur veya dalları listeler.
   ```sh
   git branch # Mevcut dalları listeler
   git branch feature-branch # Yeni bir dal oluşturur
   ```

2. **git checkout**: Dalları değiştirir veya dalları oluşturup değiştirir.
   ```sh
   git checkout feature-branch # Mevcut bir dala geçer
   git checkout -b new-feature-branch # Yeni bir dal oluşturur ve ona geçer
   ```

3. **git merge**: Bir dalı başka bir dal ile birleştirir.
   ```sh
   git checkout main # Hedef dala geçer
   git merge feature-branch # Feature dalını main ile birleştirir
   ```

4. **git rebase**: Bir dalın tabanını başka bir dalın sonuna taşıyarak yeniden uygulama yapar.
   ```sh
   git checkout feature-branch
   git rebase main # main dalındaki değişiklikleri feature-branch'a uygular
   ```

#### İptal Etme ve Geri Alma (Undoing)

1. **git reset**: Commit geçmişini değiştirir ve değişiklikleri geri alır.
   ```sh
   git reset --soft HEAD~1 # Son commit'i geri alır, değişiklikler saklanır
   git reset --hard HEAD~1 # Son commit'i geri alır ve değişiklikleri kaybeder
   ```

2. **git revert**: Belirli bir commit'i geri alır, yeni bir commit olarak kaydeder.
   ```sh
   git revert <commit_hash> # Belirtilen commit'i geri alır
   ```

#### İnteraktif Rebase (Interactive Rebase)

1. **git rebase -i**: Commit geçmişini düzenlemek için interaktif rebase yapar.
   ```sh
   git rebase -i HEAD~3 # Son üç commit'i düzenler
   ```

#### Etiketler (Tags)

1. **git tag**: Belirli bir commit'e etiket ekler.
   ```sh
   git tag v1.0 # HEAD commit'e v1.0 etiketi ekler
   git tag v1.0 <commit_hash> # Belirtilen commit'e etiket ekler
   ```

2. **git push --tags**: Etiketleri uzak depoya gönderir.
   ```sh
   git push --tags
   ```

#### Git Stash

1. **git stash**: Geçici olarak değişiklikleri saklar.
   ```sh
   git stash # Geçerli değişiklikleri saklar
   git stash pop # Saklanan değişiklikleri geri getirir
   ```

#### Git Log

1. **git log**: Commit geçmişini görüntüler.
   ```sh
   git log # Tüm commit geçmişini gösterir
   git log --oneline # Her commit'i tek satırda gösterir
   ```

2. **git log --graph --decorate --oneline**: Dal geçmişini ve commit'leri grafik olarak gösterir.
   ```sh
   git log --graph --decorate --oneline
   ```

### Çakışmalar ve Çözümleme (Conflicts and Resolution)

1. **git merge-conflict**: Çakışmalar olduğunda, dosyalar çakışma işaretleri içerir. Çakışmaları manuel olarak çözmeniz gerekir.

2. **git add ve git commit**: Çakışmalar çözüldüğünde değişiklikleri ekleyin ve commit edin.
   ```sh
   git add .
   git commit -m "Çakışma çözüldü"
   ```

### Uzak Depolar (Remote Repositories)

1. **git remote**: Uzak depoları yönetir.
   ```sh
   git remote -v # Uzak depoları listeler
   git remote add origin https://github.com/username/repository.git # Uzak depo ekler
   ```

2. **git fetch**: Uzak depodan değişiklikleri alır (ancak çalışma dizinine uygulamaz).
   ```sh
   git fetch origin
   ```

### Fork ve Pull Request

1. **Fork**: GitHub'da bir projeyi fork edin (klonlayın).
2. **Pull Request**: Değişikliklerinizi orijinal depo sahibine geri gönderin. GitHub arayüzü üzerinden yapılır.

<img src="https://upload.wikimedia.org/wikipedia/commons/b/b3/Terminalicon2.png"  height="120" width="120" align="left" >


## Temel Terminal Komutları 

<br><br>

### 1. `ls`
**Açıklama:** Klasör içeriğini listelemek için kullanılır.

**Kullanım:**
```sh
ls            # Mevcut dizindeki dosyaları ve klasörleri listeler
ls -l         # Ayrıntılı listeleme
ls -a         # Gizli dosyaları da listeler
ls -la        # Ayrıntılı ve gizli dosyaları listeleme
```

### 2. `cd`
**Açıklama:** Dizin değiştirmek için kullanılır.

**Kullanım:**
```sh
cd /path/to/directory  # Belirtilen dizine gider
cd ~                   # Ana dizine gider
cd ..                  # Üst dizine gider
cd -                   # Önceki dizine gider
```

### 3. `pwd`
**Açıklama:** Geçerli çalışma dizinini yazdırır.

**Kullanım:**
```sh
pwd  # Mevcut çalışma dizinini gösterir
```

### 4. `mkdir`
**Açıklama:** Yeni bir dizin oluşturur.

**Kullanım:**
```sh
mkdir new_directory  # "new_directory" adında yeni bir dizin oluşturur
```

### 5. `rmdir`
**Açıklama:** Boş bir dizini siler.

**Kullanım:**
```sh
rmdir directory_name  # "directory_name" adlı boş dizini siler
```

### 6. `rm`
**Açıklama:** Dosyaları veya dizinleri siler.

**Kullanım:**
```sh
rm file_name         # "file_name" adlı dosyayı siler
rm -r directory_name # "directory_name" adlı dizini ve içeriğini siler
```

### 7. `cp`
**Açıklama:** Dosya veya dizinleri kopyalar.

**Kullanım:**
```sh
cp source_file destination_file             # "source_file" adlı dosyayı "destination_file" olarak kopyalar
cp -r source_directory destination_directory # "source_directory" adlı dizini "destination_directory" olarak kopyalar
```

### 8. `mv`
**Açıklama:** Dosya veya dizinleri taşır veya yeniden adlandırır.

**Kullanım:**
```sh
mv old_name new_name          # "old_name" adlı dosya/dizini "new_name" olarak yeniden adlandırır
mv file_name /path/to/directory # "file_name" adlı dosyayı belirtilen dizine taşır
```

### 9. `touch`
**Açıklama:** Yeni boş bir dosya oluşturur veya mevcut bir dosyanın zaman damgasını günceller.

**Kullanım:**
```sh
touch file_name  # "file_name" adlı yeni boş bir dosya oluşturur
```

### 10. `cat`
**Açıklama:** Dosyanın içeriğini terminalde görüntüler.

**Kullanım:**
```sh
cat file_name  # "file_name" adlı dosyanın içeriğini gösterir
```

### 11. `nano`
**Açıklama:** Basit bir metin editörüdür.

**Kullanım:**
```sh
nano file_name  # "file_name" adlı dosyayı nano ile düzenlemek için açar
```

### 12. `vi` veya `vim`
**Açıklama:** Gelişmiş bir metin editörüdür.

**Kullanım:**
```sh
vi file_name   # "file_name" adlı dosyayı vi ile düzenlemek için açar
vim file_name  # "file_name" adlı dosyayı vim ile düzenlemek için açar
```

### 13. `grep`
**Açıklama:** Dosya içeriğinde belirli bir metin dizisini arar.

**Kullanım:**
```sh
grep "search_term" file_name  # "file_name" adlı dosyada "search_term" metnini arar
grep -r "search_term" directory_name # "directory_name" adlı dizinde "search_term" metnini arar
```

### 14. `find`
**Açıklama:** Dosya ve dizinleri arar.

**Kullanım:**
```sh
find /path/to/search -name "file_name"  # Belirtilen dizinde "file_name" adlı dosyayı arar
```

### 15. `chmod`
**Açıklama:** Dosya veya dizin izinlerini değiştirir.

**Kullanım:**
```sh
chmod 755 file_name  # "file_name" adlı dosyanın izinlerini değiştirir
```

### 16. `chown`
**Açıklama:** Dosya veya dizin sahibini değiştirir.

**Kullanım:**
```sh
chown user:group file_name  # "file_name" adlı dosyanın sahibi ve grubunu değiştirir
```

### 17. `echo`
**Açıklama:** Terminalde bir metni veya değişkenin değerini yazdırır.

**Kullanım:**
```sh
echo "Hello, World!"  # Terminalde "Hello, World!" yazdırır
echo $PATH            # PATH çevresel değişkeninin değerini yazdırır
```

### 18. `sudo`
**Açıklama:** Yönetici (root) yetkileriyle bir komutu çalıştırır.

**Kullanım:**
```sh
sudo command  # Belirtilen komutu yönetici yetkileriyle çalıştırır
```

### 19. `df`
**Açıklama:** Disk alanı kullanımını gösterir.

**Kullanım:**
```sh
df -h  # İnsan tarafından okunabilir biçimde disk kullanımını gösterir
```

### 20. `du`
**Açıklama:** Dosya ve dizinlerin disk kullanımını gösterir.

**Kullanım:**
```sh
du -h /path/to/directory  # Belirtilen dizinin disk kullanımını insan tarafından okunabilir biçimde gösterir
```

