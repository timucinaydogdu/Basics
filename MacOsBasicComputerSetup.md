
# Temel Bilim Ve Teknoloji Notları
## MacOs Temiz Kurulum Rehberi
<img src="https://developer.apple.com/macos/images/lockup-hero-large_2x.png" >

### Adım : Mac Ayarları 

#### Dock Hızını Artırma 

```sh
defaults write com.apple.dock autohide-delay -float 0
killall Dock
```

- Ayarı Geri Varsayılana döndürme
```sh
defaults delete com.apple.dock autohide-delay
killall Dock
```

### Adım 1: Homebrew Kurulumu
<img src="https://brew.sh/assets/img/homebrew.svg" align="left" height="120" width="120">


Öncelikle Homebrew'u kurmanız gerekiyor. Terminal'i açın ve aşağıdaki komutu girin:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
<br>

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

<img src="https://avatars.githubusercontent.com/u/18133?s=200&v=4" align="left" height="120" width="120">
<br>

```sh
brew install git
```
<br>

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

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/121px-Python-logo-notext.svg.png" align="left" height="120" width="120">

<br>

```sh
brew install python
```
<br><br>

**2.1. Python Kurulumu:**
	•	Python ve pip’in yüklü olduğunu doğrulamak için aşağıdaki komutları çalıştırın:
```sh
python3 --version
pip3 --version
```
•	Proje dizinine gidin ve aşağıdaki komutu çalıştırarak sanal bir ortam oluşturun:
```sh
python3 -m venv venv
```
•	Sanal ortamı etkinleştirin
•	Sanal ortam etkinleştirildiğinde, komut satırında (venv) etiketi görünecektir.

```sh
source venv/bin/activate
```
•	Sanal ortam etkin durumdayken Flask ve diğer gerekli paketleri yükleyin:
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Flask_logo.svg/2560px-Flask_logo.svg.png" align="left" height="120" width="240">

```sh
pip install Flask
```
<br><br>

•	Projenize bağlı olarak, SQLAlchemy, Flask-WTF gibi diğer Flask eklentilerini de yükleyebilirsiniz. Örneğin:
```sh
pip install Flask-SQLAlchemy
pip install Flask-WTF
```

**3. Node.js ve npm Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png" align="left" height="120" width="200">

```sh
brew install node
```
<br><br>

**4. Visual Studio Code Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Visual_Studio_Code_1.35_icon.svg/1200px-Visual_Studio_Code_1.35_icon.svg.png" align="left" height="120" width="120">

```sh
brew install --cask visual-studio-code
```
<br><br>

**5. Java Kurulumu:**
<img src="https://res.cloudinary.com/lwgatsby/f_auto/www/uploads/2020/08/openjdklogo.082620.png" align="left" height="120" width="120">

```sh
brew install openjdk
```
<br><br>

**6. Brave Tarayıcısı Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/Brave_lion.png/220px-Brave_lion.png" align="left" height="120" width="120">

```sh
brew install --cask brave-browser
```
<br><br>

**7. Raycast Kurulumu:** : Spotligth Muadili.
<img src="https://upload.wikimedia.org/wikipedia/en/thumb/f/f4/Raycast_App_Icon.png/120px-Raycast_App_Icon.png" align="left" height="120" width="120">

```sh
brew install --cask raycast
```
<br><br>

**7.1. Raycast Kurulumu:** : Masa Üstü İçin Pencere Yöneticisi
- Extensions > Window Management > Add Hotkeys 

**9. WhatsApp Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/WhatsApp.svg/120px-WhatsApp.svg.png" align="left" height="120" width="120">

```sh
brew install --cask whatsapp
```
<br><br>

**10. Zoom Kurulumu:**
<img src="https://logowik.com/content/uploads/images/zoom-icon8997.jpg" align="left" height="120" width="150">

```sh
brew install --cask zoom
```
<br><br>

**11. Slack Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Slack_icon_2019.svg/2048px-Slack_icon_2019.svg.png" align="left" height="120" width="120">

```sh
brew install --cask slack
```
<br><br>

**12. Discord Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/tr/5/57/Discord_logo_old.png" align="left" height="120" width="120">

```sh
brew install --cask discord
```
<br><br>

**13. Xcode Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/en/5/56/Xcode_14_icon.png" align="left" height="120" width="120">

```sh
brew install --cask xcode
```
<br><br>

**14. FreeDownload Manager Kurulumu:**
<img src="https://www.wintotal.de/media/2009/04/Free-Download-Manager-01-120x120.png" align="left" height="120" width="120">

```sh
brew install --cask free-download-manager
```
<br><br>

**15. Monitor Control Kurulumu:**
<img src="https://github.com/MonitorControl/MonitorControl/raw/main/.github/Icon-cropped.png" align="left" height="120" width="120">

```sh
brew install --cask monitorcontrol
```
<br><br>

**16. Alt-Tab Kurulumu:**
<img src="https://alt-tab-macos.netlify.app/public/android-chrome-256x256.png" align="left" height="120" width="120">

```sh
brew install --cask alt-tab
```
<br><br>

**17. Al Dente Kurulumu:**
<img src="https://apphousekitchen.com/wp-content/uploads/2021/03/aldenteproicon-300x300.png" align="left" height="120" width="120">

```sh
brew install --cask aldente
```
<br><br>

**18. Chat Gpt Kurulumu:**
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/04/ChatGPT_logo.svg/130px-ChatGPT_logo.svg.png" align="left" height="120" width="120">

```sh
https://persistent.oaistatic.com/sidekick/public/ChatGPT_Desktop_public_latest.dmg
```
<br><br>

**19. Hand Mirror Kurulumu:**
<img src="https://is1-ssl.mzstatic.com/image/thumb/Purple221/v4/08/fd/64/08fd645b-bfd1-7a83-2ea9-038231f11ad5/AppIcon-0-0-85-220-0-0-4-0-2x-P3.png/230x0w.webp" align="left" height="120" width="120">

```sh
https://apps.apple.com/us/app/hand-mirror/id1502839586?mt=12
```
<br><br>

**20. KDE Live Kurulumu:**
<img src="https://kdenlive.org/wp-content/uploads/2024/05/2405.png" align="left" height="120" width="120">

```sh
brew install --cask kdenlive
```
<br><br>

**21. Audacity Kurulumu:**
<img src="https://www.audacityteam.org/_astro/Audacity_Logo.63b57726.svg" align="left" height="120" width="120">

```sh
brew install --cask audacity
```
<br><br>

### Adım 1: iTerm2 Kurulumu
<img src="https://upload.wikimedia.org/wikipedia/commons/3/31/ITerm2_v3.4_icon.png" align="left" height="120" width="120">
<br>

```sh
brew install --cask iterm2
```
<br>

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
<img src="https://upload.wikimedia.org/wikipedia/commons/1/1e/Oh_My_Zsh_logo.png" align="left" height="120" width="200">
Oh My Zsh'ı kurmak için aşağıdaki komutu çalıştırın:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
<br>

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
