## MacOs Clean Setup
**Açıklama:** Yazılım geliştirme ilgilenmek ugraşmak ve hatalarla ugraşmak istemiyorsanız. İlk önce işletim sisteminizi ingilizce kurun. 
<img src="https://developer.apple.com/macos/images/lockup-hero-large_2x.png" >

### Route Steps : Mac Settings 

- [MacOs Clean Setup](#macos-clean-setup)
  - [Route Steps : Mac Settings](#route-steps--mac-settings)
- [OS Settings](#os-settings)
  - [Desktop](#desktop)
  - [Finder](#finder)
  - [Dock](#dock)
  - [Dock Speed Up Settings](#dock-speed-up-settings)
  - [Homebrew Setup](#homebrew-setup)
  - [Home Brew PATH Settings](#home-brew-path-settings)
  - [Homebrew Update](#homebrew-update)
  - [App List](#app-list)
    - [Git Setup](#git-setup)
      - [Github SSH Setup](#github-ssh-setup)
      - [Git Configuration](#git-configuration)
      - [SSH Key Creating](#ssh-key-creating)
      - [Adding SSH Key In GitHub Account](#adding-ssh-key-in-github-account)
      - [SSH Connetion Test](#ssh-connetion-test)
      - [System Repair And Clean](#system-repair-and-clean)
    - [Python Setup](#python-setup)
      - [Python Pip And Flask Setup Steps](#python-pip-and-flask-setup-steps)
    - [Node.js And Npm Setup](#nodejs-and-npm-setup)
    - [R Setup](#r-setup)
    - [Julia Setup](#julia-setup)
    - [Visual Studio Code Setup](#visual-studio-code-setup)
      - [VS Code Settings And Extensions](#vs-code-settings-and-extensions)
    - [Java Setup](#java-setup)
    - [Brave Browser Setup](#brave-browser-setup)
    - [Spotify Setup](#spotify-setup)
    - [Raycast Setup](#raycast-setup)
    - [WhatsApp Desktop Setup](#whatsapp-desktop-setup)
    - [Zoom Setup](#zoom-setup)
    - [Slack Setup](#slack-setup)
    - [Discord Setup](#discord-setup)
    - [Xcode Setup](#xcode-setup)
    - [FreeDownload Manager Setup](#freedownload-manager-setup)
    - [Monitor Control Setup](#monitor-control-setup)
    - [Alt Tab Setup](#alt-tab-setup)
    - [Al Dente Setup](#al-dente-setup)
    - [KDE Live Setup](#kde-live-setup)
    - [Audacity Setup](#audacity-setup)
    - [Libre Office Setup](#libre-office-setup)
    - [Android File Trasfer Setup](#android-file-trasfer-setup)
    - [Keeping You Awake Setup](#keeping-you-awake-setup)
    - [VLC Player Setup](#vlc-player-setup)
    - [Keka Setup](#keka-setup)
    - [Kap Screen Recorder Setup](#kap-screen-recorder-setup)
    - [Figma Setup](#figma-setup)
    - [Steam Setup](#steam-setup)
    - [EpicGames Setup](#epicgames-setup)
    - [Hand Mirror Webcam Helper Setup](#hand-mirror-webcam-helper-setup)
    - [Other command line tools I use](#other-command-line-tools-i-use)
    - [iTerm2 Terminal Setup](#iterm2-terminal-setup)
    - [Zsh Setup](#zsh-setup)
    - [Make ZSH Default Shell](#make-zsh-default-shell)
    - [Oh My Zsh Setup](#oh-my-zsh-setup)
    - [Powerlevel10k Theme Setup](#powerlevel10k-theme-setup)
    - [ZSH Eklentileri](#zsh-eklentileri)
  - [1. zsh-autosuggestions](#1-zsh-autosuggestions)
  - [2. zsh-syntax-highlighting](#2-zsh-syntax-highlighting)
  - [3. zsh-completions](#3-zsh-completions)
  - [4. z](#4-z)
  - [5. git](#5-git)
  - [6. zsh-history-substring-search](#6-zsh-history-substring-search)
  - [7. zsh-nvm](#7-zsh-nvm)
  - [8. zsh-interactive-cd](#8-zsh-interactive-cd)
  - [9. zsh-docker-aliases](#9-zsh-docker-aliases)
  - [10. autojump](#10-autojump)
  - [11. zsh-dirhistory](#11-zsh-dirhistory)
  - [12. zsh-extract](#12-zsh-extract)
  - [13. zsh-navigation-tools](#13-zsh-navigation-tools)
  - [14. zsh-vi-mode](#14-zsh-vi-mode)
  - [15. zsh-you-should-use](#15-zsh-you-should-use)
  - [16. zsh-prompt-benchmark](#16-zsh-prompt-benchmark)
  - [17. zsh-auto-notify](#17-zsh-auto-notify)
  - [18. zsh-apple-touchbar](#18-zsh-apple-touchbar)
  - [19. zsh-histdb](#19-zsh-histdb)
  - [20. zsh-peco](#20-zsh-peco)
    - [System Repair And Clean](#system-repair-and-clean-1)

## OS Settings

These are my preferred settings for `Desktop`, `Finder` and the `Dock`.

### Desktop

I don't like the new Desktop, Stage Manager or Widget features in Sonoma, so I disable them.

* System Preferences
  * Desktop & Dock
    * Desktop & Stage Manager
      * Show Items
        * On Desktop -> check
        * In Stage Manager -> check
      * Click wallpaper to reveal desktop -> Only in Stage Manager
      * Stage Manager -> uncheck
      * Widgets
        * On Desktop -> uncheck
        * In Stage Manager -> uncheck

### Finder

* Finder -> Preferences
  * General -> Show these on the desktop -> Select None
      * I try to keep my desktop completely clean.
  * General -> New Finder windows show -> Home Folder
      * I prefer to see my home folder in each new finder window instead of recent documents
  * Advanced -> Show all filename extensions -> Yes
  * Advanced -> Show warning before changing an extension -> No
  * Advanced -> When performing a search -> Search the current folder
* View
  * Show Status Bar
  * Show Path Bar
  * Show Tab Bar

### Dock

I don't use the Dock at all. It takes up screen space, and I can use RayCast to launch apps and AltTab to switch between apps. I make the dock as small as possible and auto hide it.

* System Preferences
  * Desktop & Dock
    * Size -> Small as possible
    * Position on screen -> Left
    * Automatically hide and show the Dock -> Yes
    * Animate opening applications -> No
    * Show suggested and recent apps in the Dock -> No

### Other Settings

* Accessibility
  * Display
    * Reduce Transparrency -> Yes
* Trackpad
  * Scrool & Zoom -> Natural Scrolling -> No 

### Dock Speed Up Settings

- Speed Up
```sh
defaults write com.apple.dock autohide-delay -float 0
killall Dock
```

- Revert Default Value
```sh
defaults delete com.apple.dock autohide-delay
killall Dock
```

### Homebrew Setup
<img src="https://brew.sh/assets/img/homebrew.svg" align="left" height="120" width="120">


Öncelikle Homebrew'u kurmanız gerekiyor. Terminal'i açın ve aşağıdaki komutu girin:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
<br>

### Home Brew PATH Settings
Homebrew kurulumundan sonra, PATH değişkeninizi güncellemeniz gerekebilir. Terminal ekrarınında da aynı kod bulunacaktır. Öncelik onu yazınız. 
Bulamazsanız eğer aşağıdaki komutu girin:

```sh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### Homebrew Update
Homebrew'u güncelleyin ve hazır hale getirin:

```sh
brew update
brew upgrade
```

### App List
Şimdi, kullandığınız uygulamalara göre gerekli olanları yükleyelim.

#### Git Setup

<img src="https://avatars.githubusercontent.com/u/18133?s=200&v=4" align="left" height="120" width="120">
<br>

```sh
brew install git
```
<br>

##### Github SSH Setup
* Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to setup an ssh key for github
* Follow [this guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to add the ssh key to your github account

##### Git Configuration
GitHub hesabınızla Git'i yapılandırmak için aşağıdaki komutları kullanın, `<your-name>` ve `<your-email>` alanlarını kendi bilgilerinizle değiştirin:

```sh
git config --global user.name "your-name"
git config --global user.email "your-email"
```

##### SSH Key Creating
Eğer GitHub hesabınızda SSH anahtarı kullanmak istiyorsanız, aşağıdaki komutu kullanarak yeni bir SSH anahtarı oluşturun:

```sh
ssh-keygen -t ed25519 -C "your-email"
```

Komut size birkaç soru soracaktır; hepsini varsayılan olarak bırakabilirsiniz.

##### Adding SSH Key In GitHub Account

Oluşturulan SSH anahtarını GitHub hesabınıza eklemek için aşağıdaki adımları izleyin:

- Terminal'de aşağıdaki komutu çalıştırarak SSH anahtarınızı kopyalayın:
  ```sh
  pbcopy < ~/.ssh/id_ed25519.pub
  ```
- GitHub'da [SSH ve GPG anahtarları](https://github.com/settings/keys) sayfasına gidin.
- "New SSH key" butonuna tıklayın.
- Anahtarınızı "Title" kutusuna yapıştırın ve ardından "Add SSH key" butonuna tıklayın.

##### SSH Connetion Test
SSH bağlantısının doğru yapılandırıldığını test etmek için aşağıdaki komutu çalıştırın:

```sh
ssh -T git@github.com
```

Eğer her şey doğru yapılandırılmışsa, bir hoş geldiniz mesajı alırsınız.
Eğer git push origin main kısmında hata alırsanız. 

- Github -> Settings -> Personel Token (Classic)-> Add name and Expiration Date -> Check All -> Generate Token
  Terminal in push folder. Write this code. 
  - git remote set-url origin https://Your-token-number-paste-it@github.com/username/reponame

##### System Repair And Clean
Son olarak, sistemdeki gereksiz dosyaları temizlemek için Homebrew'un temizlik komutunu çalıştırabilirsiniz:

```sh
brew cleanup
```
#### Source Tree Setup
**Açıklama:** Git arayüz kullanımı için ek program.

<img src="https://wac-cdn.atlassian.com/dam/jcr:2f7db492-c688-401b-93cf-70215edeade5/Sourcetree%20ios%20app%20icon%20beta%20shadow%20red.svg?cdnVersion=1881" align="left" height="120" width="120">

```sh
brew install --cask sourcetree
```
<br><br>

#### Python Setup
**Açıklama:** Python programa dilinin kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/121px-Python-logo-notext.svg.png" align="left" height="120" width="120">
<br>

```sh
brew install python
```
<br><br>

##### Python Pip And Flask Setup Steps
**Açıklama:** Python temelli flask çalışma ortamının kurulumu. 

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

#### Node.js And Npm Setup
**Açıklama:** Node js kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/1200px-Node.js_logo.svg.png" align="left" height="120" width="200">

```sh
brew install node
```
<br><br>

#### R Setup
**Açıklama:** R Programlama dilinin kurulumu. (Makine Öğrenmesi)

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/R_logo.svg/724px-R_logo.svg.png?20240131042527" align="left" height="120" width="120">

```sh
brew install r
```
<br><br>

#### Julia Setup
**Açıklama:** Julia Programlama dilinin kurulumu. (Makine Öğrenmesi)

<img src="https://www.svgrepo.com/show/376330/julia.svg" align="left" height="120" width="120">

```sh
brew install --cask julia
```
<br><br>

#### Visual Studio Code Setup
**Açıklama:** VSC IDE kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Visual_Studio_Code_1.35_icon.svg/1200px-Visual_Studio_Code_1.35_icon.svg.png" align="left" height="120" width="120">

```sh
brew install --cask visual-studio-code
```
<br><br>


##### VS Code Settings And Extensions 
**Açıklama:** VS üzerindeki terminalde ohmyzhs eklentilerini ve görsellerini çalıştırma.


- VS Code Terminal Font Fix -> Vs Code -> Settings -> Terminal.integrated.font -> 'Your Nerd  Font'

## MySQL Setup
**Açıklama:** Docker ve Azure Data studio Üzerinden Kurulum. İki uygulamayı kurduktan sonra ; <br><br>
Terminal üzerinden iki komut çalıştırılacak ; <br> 
- Dikkat edilecek nokta ikinci kodda sadece Test123456 şifresi değiştiriilebilir. 8 Karakter olmalıdır. 
```sh
docker pull mcr.microsoft.com/azure-sql-edge
```
<br>

```sh
docker run -e "ACCEPT_EULA=1" -e "MSSQL_SA_PASSWORD=Test123456" -e "MSSQL_PID=Developer" -e "MSSQL_USER=SA" -p 1433:1433 -d --name=sql mcr.microsoft.com/azure-sql-edge

```

#### Docker Setup
<img src="https://www.ibm.com/content/dam/adobe-cms/instana/media_logo/Docker.component.complex-narrative-xl.ts=1689294851916.png/content/adobe-cms/us/en/products/instana/supported-technologies/docker-monitoring/jcr:content/root/table_of_contents/body/content_section_styled/content-section-body/complex_narrative/logoimage" align="left" height="120" width="200">

```sh
brew install --cask docker
```
<br><br>
#### Azura Data Studio Setup
<img src="https://user-images.githubusercontent.com/10014944/136142919-9862b62f-3036-40fe-a380-b86fe005c27e.png" align="left" height="120" width="120">

```sh
brew install --cask azure-data-studio
```
<br><br>

#### Java Setup
**Açıklama:** Java kurulumu. Kurulum esnasında terminal kodları arasında 2 adet progman path yollarını eklememizi isteyen kod var. Atlanmamalı.
<img src="https://res.cloudinary.com/lwgatsby/f_auto/www/uploads/2020/08/openjdklogo.082620.png" align="left" height="120" width="120">

```sh
brew install openjdk
```
- Console add 2 difrent code for make program paths.
<br><br>

#### Brave Browser Setup
**Açıklama:** Brave Web Tarayıcı kurulumu. Block Chainle sync yapılırsa tüm ayarlarınız otomatik gelir. 

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/Brave_lion.png/220px-Brave_lion.png" align="left" height="120" width="120">

```sh
brew install --cask brave-browser
```
<br><br>

#### Rain Drop IO Setup
**Açıklama:** Bookmark ve not alma uygulaması.

<img src="https://raindrop.io/_next/static/images/logotype-60-73ba67bc4d66d42ef20d908a2e0c5322.png" align="left" height="120" width="120">

```sh
brew install --cask raindropio
```
<br><br>

#### Spotify Setup
**Açıklama:** Müzik çalar kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/Spotify_icon.svg/1024px-Spotify_icon.svg.png" align="left" height="120" width="120">

```sh
brew install --cask spotify
```
<br><br>


#### WhatsApp Desktop Setup
**Açıklama:** Telefonla masaüstü mesajlaşma yardımcısı kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/WhatsApp.svg/120px-WhatsApp.svg.png" align="left" height="120" width="120">

```sh
brew install --cask whatsapp
```
<br><br>

#### Zoom Setup
**Açıklama:** Zoom desktop kurulumu.

<img src="https://logowik.com/content/uploads/images/zoom-icon8997.jpg" align="left" height="120" width="150">

```sh
brew install --cask zoom
```
<br><br>

#### Slack Setup
**Açıklama:** Slack mesajlaşma uygulaması kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Slack_icon_2019.svg/2048px-Slack_icon_2019.svg.png" align="left" height="120" width="120">

```sh
brew install --cask slack
```
<br><br>

#### Discord Setup
**Açıklama:** Discord mesajlaşma uygulaması kurulumu.

<img src="https://upload.wikimedia.org/wikipedia/tr/5/57/Discord_logo_old.png" align="left" height="120" width="120">

```sh
brew install --cask discord
```
<br><br>

#### Xcode Setup
**Açıklama:** Xcode farklı versiyonları indirme aralarında geçiş yapmayı sağlayan program. 
<img src="https://upload.wikimedia.org/wikipedia/en/5/56/Xcode_14_icon.png" align="left" height="120" width="120">

```sh
brew install --cask xcodes
```
<br><br>

#### X Code SF-Symbols Setup
**Açıklama:** Xcode kullanılmak için kullanılan bir sembol kütüphanesi. 
<img src="https://developer.apple.com/assets/elements/icons/sf-symbols-beta/sf-symbols-beta-96x96_2x.png" align="left" height="120" width="120">

```sh
brew install --cask sf-symbols
```
<br><br>

#### FreeDownload Manager Setup
**Açıklama:** Dosya indirme yöneticisi, torrent dosyalarını da indirmeyi destekliyor. 

<img src="https://www.wintotal.de/media/2009/04/Free-Download-Manager-01-120x120.png" align="left" height="120" width="120">

```sh
brew install --cask free-download-manager
```
<br><br>

#### Alt Tab Setup
**Açıklama:** Windows tarzı uygulamalar arası geçisi destekleyen bir eklenti. 

<img src="https://alt-tab-macos.netlify.app/public/android-chrome-256x256.png" align="left" height="120" width="120">

```sh
brew install --cask alt-tab
```
<br><br>

#### Mac Mouse Fix
**Açıklama:** Mac Mause ayarlarını değiştirebildiğimiz eklenti yapabildiğimiz bir yardımcı program. 

<img src="https://macmousefix.com/_ipx/w_225&q_100/mmf-icon.png" align="left" height="120" width="120">

```sh
brew install --cask mac-mouse-fix
```
<br><br>

#### Al Dente Setup
**Açıklama:** Laptoplar için bir batarya yöneticisi programı. 

<img src="https://apphousekitchen.com/wp-content/uploads/2021/03/aldenteproicon-300x300.png" align="left" height="120" width="120">

```sh
brew install --cask aldente
```
<br><br>

#### Obs Setup
**Açıklama:** Canlı yayın veya kayıt yapılabilecek bir kayıt programı.
<img src="https://obsproject.com/assets/images/new_icon_small-r.png" align="left" height="120" width="120">

```sh
brew install --cask obs
```
<br><br>

#### KDE Live Setup
**Açıklama:** Video düzenleme programı. 

<img src="https://kdenlive.org/wp-content/uploads/2024/05/2405.png" align="left" height="120" width="120">

```sh
brew install --cask kdenlive
```
<br><br>

#### Audacity Setup
**Açıklama:** Ses düzenleme programı. 

<img src="https://www.audacityteam.org/_astro/Audacity_Logo.63b57726.svg" align="left" height="120" width="120">

```sh
brew install --cask audacity
```
<br><br>

#### Libre Office Setup
**Açıklama:** Ofis programları kurulumu. 

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/LibreOffice_6.1_Calc_Icon.svg/512px-LibreOffice_6.1_Calc_Icon.svg.png" align="left" height="120" width="120">

```sh
brew install --cask libreoffice
```
<br><br>

#### Android File Trasfer Setup
**Açıklama:** Android telefonlardan mac üzerine bağlamayı sağlayan bir eklenti programı. 

<img src="https://icons.iconarchive.com/icons/papirus-team/papirus-apps/256/android-file-transfer-icon.png" align="left" height="120" width="120">

```sh
brew install --cask android-file-transfer
```
<br><br>

#### Keeping You Awake Setup
**Açıklama:** Bilgisayarın uykuya geçmesini engelleyen bir eklenti. 

<img src="https://keepingyouawake.app/icon.png" align="left" height="120" width="120">

```sh
brew install --cask keepingyouawake
```
<br><br>

#### Rectangle Setup
**Açıklama:** Pencere yöneticisi. 

<img src="https://rectangleapp.com/assets/pro/images/mac512pts1x.png" align="left" height="120" width="120">

```sh
brew install --cask rectangle
```
<br><br>

#### VLC Player Setup
**Açıklama:** Video izleme programı ve video formatları arasında dönüştürme yapabilir.

<img src="https://cdn1.iconfinder.com/data/icons/metro-ui-dock-icon-set--icons-by-dakirby/512/VLC_Media_Player.png" align="left" height="120" width="120">

```sh
brew install --cask vlc
```
<br><br>

#### Keka Setup
**Açıklama:** Zip programı dosyaları sıkıştırabilir ve açabilir. 

<img src="https://www.keka.io/img/Keka-Square-512x512.png" align="left" height="120" width="120">

```sh
brew install --cask keka
```
<br><br>

#### Kap Screen Recorder Setup
**Açıklama:** Masa üstü ekran kayıt programı.

<img src="https://getkap.co/static/favicon/icon-256.png" align="left" height="120" width="120">

```sh
brew install --cask kap
```
<br><br>

#### VMwareFusion Setup
**Açıklama:** Sanal işletim sistemi arayüz programı. 

<img src="https://upload.wikimedia.org/wikipedia/commons/8/8e/VMware_Fusion_Logo.png?20150508091423" align="left" height="120" width="120">

```sh
brew install --cask vmware-fusion
```
<br><br>

#### Bitwarden Setup
**Açıklama:** Şifre yöneticisi. 

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Bitwarden_logo.svg/120px-Bitwarden_logo.svg.png" align="left" height="76" width="120">

```sh
brew install bitwarden
```
<br><br>

#### Figma Setup
**Açıklama:** Tasaramı ve protatip oluşturma aracı. 

<img src="https://banner2.cleanpng.com/20180614/tjk/kisspng-figma-designer-computer-icons-material-design-5b2244f198c236.1471924315289725296257.jpg" align="left" height="120" width="120">

```sh
brew install --cask figma
```
<br><br>

#### Steam Setup
**Açıklama:** Oyun kütüphanesi. 

<img src="https://upload.wikimedia.org/wikipedia/commons/8/83/Steam_icon_logo.svg" align="left" height="120" width="120">

```sh
brew install --cask steam
```
<br><br>

#### EpicGames Setup
**Açıklama:** Oyun kütüphanesi. 

<img src="https://logos-world.net/wp-content/uploads/2021/12/Epic-Games-Logo-700x394.png" align="left" height="120" width="200">

```sh
brew install --cask epic-games
```
<br><br>


#### Key Castr Setup
**Açıklama:** Klavyeden basılan tuşu gösteren program. 

<img src="https://github.com/keycastr/keycastr/raw/main/assets/KeyCastr_header.png" align="left" height="120" width="150">

```sh
brew install --cask keycastr
```
<br><br>

#### Bettir Display Setup
**Açıklama:** Harici ekranların kontrolü için program. 

<img src="https://private-user-images.githubusercontent.com/37590873/252763361-d0c7e3c2-07c4-45de-9fca-60441281a548.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjIzOTM3NzksIm5iZiI6MTcyMjM5MzQ3OSwicGF0aCI6Ii8zNzU5MDg3My8yNTI3NjMzNjEtZDBjN2UzYzItMDdjNC00NWRlLTlmY2EtNjA0NDEyODFhNTQ4LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA3MzElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNzMxVDAyMzc1OVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTFmZTY4N2FjZTUzNTJiNmViN2VjMTZlMzU5ZmM5MmI0ZTUzMmU2OTAyNjJiODEwZTA0OGJiNDFkMWQ5NDUzMDImWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.D9Gggx2t0ashsTs-nM2ihgctUjI4mBOT8EzUih3SvNM" align="left" height="120" width="120">

```sh
brew install --cask betterdisplay
```
<br><br>

#### Hand Mirror Webcam Helper Setup
**Açıklama:** Toplantı öncesi kamera görselini kontrol etme eklenti aracı. 

<img src="https://is1-ssl.mzstatic.com/image/thumb/Purple221/v4/08/fd/64/08fd645b-bfd1-7a83-2ea9-038231f11ad5/AppIcon-0-0-85-220-0-0-4-0-2x-P3.png/230x0w.webp" align="left" height="120" width="120">

```sh
https://apps.apple.com/us/app/hand-mirror/id1502839586?mt=12
```
<br><br>

#### One Thing
**Açıklama:** Hedef belirleme konsantirasyon eklentisi.

<img src="https://is1-ssl.mzstatic.com/image/thumb/Purple116/v4/df/e0/43/dfe043d3-ff4d-6edf-9912-f7859dc1db65/AppIcon-0-0-85-220-0-4-0-2x.png/230x0w.webp" align="left" height="120" width="120">

```sh
https://apps.apple.com/us/app/one-thing/id1604176982?mt=12
```
<br><br>

#### Expenses 
**Açıklama:** Harcama takip programı. 

<img src="https://is1-ssl.mzstatic.com/image/thumb/Purple221/v4/cd/fe/4f/cdfe4fb0-5d26-7ae6-c822-249a22ac3957/AppIcon-2x_U007euniversal-0-0-0-4-0-0-85-220-0.png/230x0w.webp" align="left" height="120" width="120">

```sh
https://apps.apple.com/us/app/expenses-spending-tracker/id1492055171?ign-itscg=30200&ign-itsct=apps_box_link
```
<br><br>

#### Other command line tools I use

* [ffmpeg](https://en.wikipedia.org/wiki/FFmpeg) - edit videos from the command line
* [imagemagick](https://en.wikipedia.org/wiki/ImageMagick) - edit images from the command line

```sh
brew install ffmpeg
brew install imagemagick
```

#### iTerm2 Terminal Setup
**Açıklama:** Mac terminale alternatif güclü bir kisileştirme yapısına sahip ve eklentiler ile güçlenebilmektedir. 

<img src="https://upload.wikimedia.org/wikipedia/commons/3/31/ITerm2_v3.4_icon.png" align="left" height="120" width="120">
<br>

```sh
brew install --cask iterm2
```
<br><br>

I prefer [iTerm2](https://iterm2.com/) because:
* Lots of customization options
* Clickable links
* Native OS notifications

Once installed, launch it and customize the settings / preferences to your liking. These are my preferred settings:


* [Fonts, What you wish.](https://www.nerdfonts.com/font-downloads)
* Appearance
  * Theme
    * Minimal
    * Tabbar Location -> Bottom
    * Status Bar Location -> Bottom
* Profiles
  * Default
      * General -> Working Directory -> Reuse previous session's directory
      * Color Presets -> High Contrast
      * Text -> Font -> Your Choise From NerdFonts for icons.
      * Keys -> Key Mappings -> Presets -> Natural Text Editing
      * Window -> Style -> Full Height Rigth of Screen
* Keys 
  * Hotkey
      * Show / Hide all windows hotkey -> Checked
      * Setup Hotkey


#### Oh My Zsh Setup
<img src="https://upload.wikimedia.org/wikipedia/commons/1/1e/Oh_My_Zsh_logo.png" align="left" height="120" width="200">

Oh My Zsh'ı kurmak için aşağıdaki komutu çalıştırın:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
<br>

- iTerm2 ile Zsh ve Oh My Zsh Kullanımı
iTerm2'yi açın ve Zsh'in varsayılan kabuk olarak kullanıldığını doğrulayın. Eğer doğru şekilde kurulduysa, Oh My Zsh temasını ve eklentilerini kullanmaya başlayabilirsiniz.

#### Powerlevel10k Theme Setup
**1. Powerlevel10k'yı Klonlayın:**

```sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

**2. Oh My Zsh Temasını Değiştirin:**

`~/.zshrc` dosyasını açın ve `ZSH_THEME` satırını aşağıdaki gibi değiştirin:

```sh
ZSH_THEME="powerlevel10k/powerlevel10k"
```

**3. Değişiklikleri Uygulama**

Zsh kabuğunu yeniden yükleyin:

```sh
source ~/.zshrc
```
- Powerlevel10k Yapılandırma Sihirbazını Çalıştırma : Terminalinizi yeniden başlattığınızda veya Zsh'ı yeniden yüklediğinizde, Powerlevel10k yapılandırma sihirbazı otomatik olarak başlayacaktır. Bu sihirbaz, temayı özelleştirmenize ve tercihlerinizi ayarlamanıza yardımcı olacaktır. Sihirbazı adım adım takip ederek kişisel tercihlerinizi belirleyin.

#### ZSH Eklentileri

- Eklenti Dizinine Göz Atma : Öncelikle, Oh My Zsh'ın varsayılan olarak hangi eklentileri sağladığını görmek için eklenti dizinine göz atabilirsiniz. Bu dizin genellikle `~/.oh-my-zsh/plugins` konumunda bulunur.

```sh
ls ~/.oh-my-zsh/plugins
```

- Eklenti Eklemek : Eklentileri etkinleştirmek için `~/.zshrc` dosyasını düzenlemeniz gerekiyor. Terminalde aşağıdaki komutu kullanarak `~/.zshrc` dosyasını açın:

Open VS code in ~/.zshrc location. 

or 

```sh
nano ~/.zshrc
```

Eklentileri etkinleştirmek için `plugins` dizisini bulun. Örneğin, `git` ve `z` eklentilerini etkinleştirmek için `plugins` dizisini aşağıdaki gibi düzenleyin:

```sh
plugins=(git z)
```

- Yeni Eklentiler Kurma : Varsayılan olarak sağlanmayan bir eklentiyi kurmak için, ilgili eklentiyi `~/.oh-my-zsh/custom/plugins` dizinine klonlamanız gerekir.

Örneğin, `zsh-syntax-highlighting` eklentisini kurmak için:

```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

Kurulumdan sonra, `~/.zshrc` dosyasını açın ve yeni eklentiyi `plugins` dizisine ekleyin:

```sh
plugins=(git zsh-syntax-highlighting)
```

- Değişiklikleri Uygulama : `~/.zshrc` dosyasındaki değişiklikleri uygulamak için Zsh kabuğunu yeniden yükleyin:

```sh
source ~/.zshrc
```

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

### 7. Colorls
**Açıklama:** Listeleri klasörlü simgelerle göstermeye yarar. 
**Kurulum:**
```sh
sudo gem install colorls
```
**~/.zshrc dosyasınnın sonuna ekleyin:**
```sh
alias ls='colorls'
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

#### System Repair And Clean
Son olarak, sistemdeki gereksiz dosyaları temizlemek için Homebrew'un temizlik komutunu çalıştırabilirsiniz:

```sh
brew cleanup
```