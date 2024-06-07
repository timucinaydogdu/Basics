
# Temel Bilim Ve Teknoloji Notları
## MacOs Temiz Kurulum Rehberi

### Adım 1: Homebrew Kurulumu
Öncelikle Homebrew'u kurmanız gerekiyor. Terminal'i açın ve aşağıdaki komutu girin:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Adım 2: PATH Ayarlarını Güncelleme
Homebrew kurulumundan sonra, PATH değişkeninizi güncellemeniz gerekebilir. Bunun için aşağıdaki komutu girin:

```sh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### Adım 3: Homebrew Güncelleme
Homebrew'u güncelleyin ve hazır hale getirin:

```sh
brew update
brew upgrade
```

### Adım 4: Gerekli Uygulamaların Kurulumu
Şimdi, kullandığınız uygulamalara göre gerekli olanları yükleyelim.

**1. Git Kurulumu:**
```sh
brew install git
```

#### Adım 1.1 : GitHub Hesap Bağlantısı İçin Ayarlar
GitHub hesabınızı Git ile bağlamak için aşağıdaki adımları izleyin:

**1. Git Konfigürasyonu:**
GitHub hesabınızla Git'i yapılandırmak için aşağıdaki komutları kullanın, `<your-name>` ve `<your-email>` alanlarını kendi bilgilerinizle değiştirin:

```sh
git config --global user.name "your-name"
git config --global user.email "your-email"
```

**2. SSH Anahtarı Oluşturma:**
Eğer GitHub hesabınızda SSH anahtarı kullanmak istiyorsanız, aşağıdaki komutu kullanarak yeni bir SSH anahtarı oluşturun:

```sh
ssh-keygen -t ed25519 -C "your-email"
```

Komut size birkaç soru soracaktır; hepsini varsayılan olarak bırakabilirsiniz.

**3. SSH Anahtarını GitHub Hesabınıza Ekleyin:**
Oluşturulan SSH anahtarını GitHub hesabınıza eklemek için aşağıdaki adımları izleyin:

- Terminal'de aşağıdaki komutu çalıştırarak SSH anahtarınızı kopyalayın:
  ```sh
  pbcopy < ~/.ssh/id_ed25519.pub
  ```
- GitHub'da [SSH ve GPG anahtarları](https://github.com/settings/keys) sayfasına gidin.
- "New SSH key" butonuna tıklayın.
- Anahtarınızı "Title" kutusuna yapıştırın ve ardından "Add SSH key" butonuna tıklayın.

**4. SSH Bağlantısını Test Etme:**
SSH bağlantısının doğru yapılandırıldığını test etmek için aşağıdaki komutu çalıştırın:

```sh
ssh -T git@github.com
```

Eğer her şey doğru yapılandırılmışsa, bir hoş geldiniz mesajı alırsınız.

### Adım 6: Sistem Temizleme ve Bakım
Son olarak, sistemdeki gereksiz dosyaları temizlemek için Homebrew'un temizlik komutunu çalıştırabilirsiniz:

```sh
brew cleanup
```

**2. Python Kurulumu:**
```sh
brew install python
```

**3. Node.js ve npm Kurulumu:**
```sh
brew install node
```

**4. Visual Studio Code Kurulumu:**
```sh
brew install --cask visual-studio-code
```

**5. Java Kurulumu:**
```sh
brew install openjdk
```

**6. Brave Tarayıcısı Kurulumu:**
```sh
brew install --cask brave-browser
```

**7. Raycast Kurulumu:** : Spotligth Muadili.
```sh
brew install --cask raycast
```
**7. Raycast Kurulumu:** : Masa Üstü İçin Pencere Yöneticisi
        Extensions > Window Management > Add Hotkeys 

**9. WhatsApp Kurulumu:**
```sh
brew install --cask whatsapp
```

**10. Zoom Kurulumu:**
```sh
brew install --cask zoom
```

**11. Slack Kurulumu:**
```sh
brew install --cask slack
```

**12. Discord Kurulumu:**
```sh
brew install --cask discord
```

**13. Xcode Kurulumu:**
```sh
brew install --cask xcode
```

### Adım 1: iTerm2 Kurulumu
Öncelikle iTerm2'nin yüklü olduğundan emin olun. Eğer iTerm2 yüklü değilse, Homebrew kullanarak yükleyebilirsiniz:

```sh
brew install --cask iterm2
```

### Adım 2: Zsh Kurulumu
Zsh, macOS ile birlikte gelir, ancak en son sürümü kullanmak için yine de Homebrew ile yükleyebilirsiniz:

```sh
brew install zsh
```

### Adım 3: Zsh'i Varsayılan Kabuk Olarak Ayarlama
Zsh'i varsayılan kabuk (shell) olarak ayarlayın:

```sh
chsh -s /bin/zsh
```

Bu komut çalışmazsa, aşağıdaki komutu deneyin:

```sh
chsh -s $(which zsh)
```

### Adım 4: Oh My Zsh Kurulumu
Oh My Zsh'ı kurmak için aşağıdaki komutu çalıştırın:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Adım 5: iTerm2 ile Zsh ve Oh My Zsh Kullanımı
iTerm2'yi açın ve Zsh'in varsayılan kabuk olarak kullanıldığını doğrulayın. Eğer doğru şekilde kurulduysa, Oh My Zsh temasını ve eklentilerini kullanmaya başlayabilirsiniz.

Tabii ki! Powerlevel10k, Zsh için oldukça popüler ve özelleştirilebilir bir tema. Hem performanslı hem de göz alıcı bir terminal deneyimi sunar. Aşağıda Powerlevel10k temasının nasıl kurulacağına dair adım adım rehberi bulabilirsiniz.

### Adım 6: Powerlevel10k Temasının Kurulumu

**1. Powerlevel10k'yı Klonlayın:**

```sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

**2. Oh My Zsh Temasını Değiştirin:**

`~/.zshrc` dosyasını açın ve `ZSH_THEME` satırını aşağıdaki gibi değiştirin:

```sh
ZSH_THEME="powerlevel10k/powerlevel10k"
```

### Adım 7: Değişiklikleri Uygulama

Zsh kabuğunu yeniden yükleyin:

```sh
source ~/.zshrc
```

### Adım 8: Powerlevel10k Yapılandırma Sihirbazını Çalıştırma

Terminalinizi yeniden başlattığınızda veya Zsh'ı yeniden yüklediğinizde, Powerlevel10k yapılandırma sihirbazı otomatik olarak başlayacaktır. Bu sihirbaz, temayı özelleştirmenize ve tercihlerinizi ayarlamanıza yardımcı olacaktır. Sihirbazı adım adım takip ederek kişisel tercihlerinizi belirleyin.

### Adım 9: Powerlevel10k Eklentileri ve Özellikleri

Powerlevel10k, birçok özelleştirme ve özellik sunar. İşte bazı örnekler:

**1. Renk Şemaları:**

```sh
p10k configure
```

## ZSH Eklentileri

### Adım 1: Eklenti Dizinine Göz Atma
Öncelikle, Oh My Zsh'ın varsayılan olarak hangi eklentileri sağladığını görmek için eklenti dizinine göz atabilirsiniz. Bu dizin genellikle `~/.oh-my-zsh/plugins` konumunda bulunur.

```sh
ls ~/.oh-my-zsh/plugins
```

### Adım 2: Eklenti Eklemek
Eklentileri etkinleştirmek için `~/.zshrc` dosyasını düzenlemeniz gerekiyor. Terminalde aşağıdaki komutu kullanarak `~/.zshrc` dosyasını açın:

```sh
nano ~/.zshrc
```

Eklentileri etkinleştirmek için `plugins` dizisini bulun. Örneğin, `git` ve `z` eklentilerini etkinleştirmek için `plugins` dizisini aşağıdaki gibi düzenleyin:

```sh
plugins=(git z)
```

### Adım 3: Yeni Eklentiler Kurma
Varsayılan olarak sağlanmayan bir eklentiyi kurmak için, ilgili eklentiyi `~/.oh-my-zsh/custom/plugins` dizinine klonlamanız gerekir.

Örneğin, `zsh-syntax-highlighting` eklentisini kurmak için:

```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

Kurulumdan sonra, `~/.zshrc` dosyasını açın ve yeni eklentiyi `plugins` dizisine ekleyin:

```sh
plugins=(git zsh-syntax-highlighting)
```

### Adım 4: Değişiklikleri Uygulama
`~/.zshrc` dosyasındaki değişiklikleri uygulamak için Zsh kabuğunu yeniden yükleyin:

```sh
source ~/.zshrc
```

### Popüler Oh My Zsh Eklentileri
İşte bazı popüler Oh My Zsh eklentileri ve kurulumları:

### 1. zsh-autosuggestions
**Açıklama:** Önceki komutlarınızdan otomatik tamamlama önerileri sunar.
**Kurulum:**
```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-autosuggestions)
```

### 2. zsh-syntax-highlighting
**Açıklama:** Komutları yazarken sözdizimi vurgulaması sağlar.
**Kurulum:**
```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-syntax-highlighting)
```

### 3. zsh-completions
**Açıklama:** Zsh için ek tamamlama komutları sağlar.
**Kurulum:**
```sh
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-completions
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-completions)
```

### 4. z
**Açıklama:** Sık kullanılan dizinlere hızlıca gitmeyi sağlar.
**Kurulum:**
```sh
brew install z
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(z)
```

### 5. git
**Açıklama:** Git komutları için yardımcı fonksiyonlar ve kısayollar sağlar.
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(git)
```

### 6. zsh-history-substring-search
**Açıklama:** Komut geçmişinde alt dize araması yapmanızı sağlar.
**Kurulum:**
```sh
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-history-substring-search)
```

### 7. zsh-nvm
**Açıklama:** Node.js versiyon yöneticisi nvm için Zsh desteği sağlar.
**Kurulum:**
```sh
git clone https://github.com/lukechilds/zsh-nvm ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-nvm
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-nvm)
```

### 8. zsh-interactive-cd
**Açıklama:** Etkileşimli dizin değiştirme işlemlerini kolaylaştırır.
**Kurulum:**
```sh
git clone https://github.com/changyuheng/zsh-interactive-cd ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-interactive-cd
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-interactive-cd)
```

### 9. zsh-docker-aliases
**Açıklama:** Docker komutları için kısayollar sağlar.
**Kurulum:**
```sh
git clone https://github.com/felixr/docker-zsh ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/docker
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(docker)
```

### 10. autojump
**Açıklama:** Sık kullanılan dizinlere hızlıca gitmeyi sağlar.
**Kurulum:**
```sh
brew install autojump
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(autojump)
```

### 11. zsh-dirhistory
**Açıklama:** Dizin geçmişini kaydeder ve geri dönmenizi sağlar.
**Kurulum:**
```sh
git clone https://github.com/tymm/zsh-directory-history ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-directory-history
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-directory-history)
```

### 12. zsh-extract
**Açıklama:** Dosya arşivlerini kolayca açmanızı sağlar.
**Kurulum:**
```sh
git clone https://github.com/specht/zsh-extract ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-extract
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-extract)
```

### 13. zsh-navigation-tools
**Açıklama:** Klasörlerde ve dosyalarda gezinmeyi kolaylaştırır.
**Kurulum:**
```sh
git clone https://github.com/psprint/zsh-navigation-tools ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-navigation-tools
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-navigation-tools)
```

### 14. zsh-vi-mode
**Açıklama:** Zsh için vi tarzı mod sağlar.
**Kurulum:**
```sh
git clone https://github.com/jeffreytse/zsh-vi-mode ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-vi-mode
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-vi-mode)
```

### 15. zsh-you-should-use
**Açıklama:** Daha önce kullandığınız komutları hatırlatır ve yeniden kullanmanızı önerir.
**Kurulum:**
```sh
git clone https://github.com/MichaelAquilina/zsh-you-should-use ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/you-should-use
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(you-should-use)
```

### 16. zsh-prompt-benchmark
**Açıklama:** Komut satırının performansını ölçer ve raporlar.
**Kurulum:**
```sh
git clone https://github.com/romkatv/zsh-prompt-benchmark ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-prompt-benchmark
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-prompt-benchmark)
```

### 17. zsh-auto-notify
**Açıklama:** Uzun süren komutlar tamamlandığında bildirim gönderir.
**Kurulum:**
```sh
git clone https://github.com/MichaelAquilina/zsh-auto-notify ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/auto-notify
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(auto-notify)
```

### 18. zsh-apple-touchbar
**Açıklama:** Apple Touch Bar üzerinde özel kısayollar ve komutlar oluşturur.
**Kurulum:**
```sh
git clone https://github.com/zsh-users/zsh-apple-touchbar ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-apple-touchbar
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-apple-touchbar)
```

### 19. zsh-histdb
**Açıklama:** Komut geçmişinizi SQLite veritabanına kaydeder ve sorgulamanızı sağlar.
**Kurulum:**
```sh
git clone https://github.com/larkery/zsh-histdb ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-histdb
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(zsh-histdb)
```

### 20. zsh-peco
**Açıklama:** Komut geçmişinizde arama yapmanızı sağlar ve seçim yapmanıza olanak tanır.
**Kurulum:**
```sh
git clone https://github.com/hchbaw/peco ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/peco
```
**~/.zshrc dosyasına ekleyin:**
```sh
plugins=(peco)
```

## Temel Terminal Komutları 

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

