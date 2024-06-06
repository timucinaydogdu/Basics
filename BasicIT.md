# MacOs Temiz Kurulum Rehberi

Adım 3: Python ve pip Yükleme
Öncelikle, sisteminizde Python ve pip yüklü olduğundan emin olun. MacOS'ta aşağıdaki komutları kullanarak yükleme yapabilirsiniz:

Python ve pip Kontrolü
sh
Kodu kopyala
python3 --version
pip3 --version
Eğer yüklü değilse, Homebrew kullanarak yükleyebilirsiniz:

Homebrew Kurulumu
sh
Kodu kopyala
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
Python ve pip Yükleme
sh
Kodu kopyala
brew install python
Adım 4: Virtual Environment Oluşturma
Proje bağımlılıklarını izole etmek için bir sanal ortam (virtual environment) oluşturun.

sh
Kodu kopyala
python3 -m venv venv
Adım 5: Virtual Environment'ı Aktifleştirme
Sanal ortamı aktifleştirin.

sh
Kodu kopyala
source venv/bin/activate
Adım 6: Flask Kurulumu
Sanal ortam aktifleştirildikten sonra Flask'ı yükleyin.

sh
Kodu kopyala
pip install Flask
