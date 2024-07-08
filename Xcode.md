<img src="https://upload.wikimedia.org/wikipedia/en/thumb/5/56/Xcode_14_icon.png/120px-Xcode_14_icon.png" align="left" >


## Xcode Ayarları Ve Kullanım Notları
<br>
**Açıklama:** Xcode da bilinmesi gereken ayarlar ve notlar. 
<br><br><br>

#### Proje Oluşturma
* Create New Project 
    - MultiPlatform
    - İOS
    - MacOS
    - TvOs
        * Next
        - ProjectName
        - Team
        - OrganizationIdentifier
        - Interface
        - Language 
            * Next
            - Save Location
            - File Name
            - Github Repository
                * Create
                    * Hello New Project Screen

#### Xcode Arayüzü

###### Sol Panel
Run Project Button
- Project Navigator (Proje Dosyaları)
    * ProjeckName (Ana Klasör - Proje Ayarları)
        - General
            * Supported Destinations (Desteklenen Aygıtlar)
            * Minimum Deployment (En düşük sürüm belirleme)
            * Identity (Uygulama Bilgisi)
                - App Category  (Uygulama Kategorisi)
                - Display Name  (Uyguluma Görünen Adı)  
                - Version Number
                - Build
            * Deployment Info
                - Iphone Orientation
                - İpad Orientation
                - Status Bar Style
            * App Icons and Launch Screen
                - AppIcon (Asset Dosyasından Icon Eklenir)
        - Signin & Capablities
        - Resource Tags
        - Info
        - Build Settings
        - Build Phases
        - Build Rules
    * projectName.swift - Başlangıç dosyası @main'e bakılır.
    * ContentView.swift - Uygulama Arayüzü.
- Source Control Navigator
- BookMark Navigator
- Show to Find Navigator
- Issuie Navigator
- Test Navigator
- Debug Navigator
- BreeakPoint Navigator
- Report Navigator

###### Merkez Editor Panel
- Show Library (Ek Araçlar)
- Tab Panel
- Editor Panel
- Similasyon Panel

###### Sağ Panel
- File Inspector Panel
- History Panel
- Quick Help Panel
- Accessibility Panel
- Attributes Panel (Özellik Paneli)

##  Kullanım Notları

### Text Bileşenleri Ve Özellikleri ;
<p>
//          -> Yorum satırı için kullanılır. <br>
Commend + ? -> Seçilen satırları toplu olarak yorum satırı yapar.<br>
Color.primary ve secondry -> İki yada dafa fazla renk şemalı yapılarda renk yapılandırmasını kolay şekilde değiştirmeye yarar. 
<br></p>



```sh
    text("Merhaba Dünya !")                 # . text'e ait özellikleri listeler

        .font(.headline)                    # Font değişliği yapar. Özellik yerine fonsiyona benzer.
        .foreground(.red)                   # Font rengini değiştirir.
        .bold()                             # Yazıyı kalınlaştırır.
        .italic()                           # Yazıyı italic yapar. 
        .multilineTextAlignment(.center)    # Çok satırlı yazıyı ortalar.
        .kerning(10)                        # Yazı karakterleri arasında 10 piksel oluşturur.
        .frame(width:250, height:150, aligment:Aligment.center)
                                            # Yazıyı bir çerçeveye alır ve yazıyı ortalar. 
        .minimimScaleFactor(1.0)            # Yazıyı ölçeklendirme için kullanılır. 
        .capitalized                        # Metnin arkasına özellik olarak eklenir. 
```

### Shape Bileşenleri Ve Özellikleri ;
- Library -> circle()
- Library -> Ellipse()
- Library -> Capsule()
- Library -> Rectangle()
- Library -> RoundedRectangle()

<br>


Özel renk tanımlamada :

- Asset 
    - ekle ->  Color Set -> Attribulet Panel -> 8 bit Hex

```sh

    .foregroundColor(Color("CustomColor"))
    .shadow(color:Color.red, radius:10.0,x:0, y:0)

```

```sh
    circle().fill(color.red)                # Çember oluştur ve rengini kırmızı yap. 
    .foregroundColor(.green)                # Rengini yeşil yap. 
    .stroke(Color.blue, lineWidth:10.0)     # Çemberin çevre kalınlığını mavi yapar ve kalınlığını ayarlar.. 
    .stroke(style:StrokeStyle(lineWidth:10, lineCap: .butt,dash: [10]))         
    .trim(from:0.0, to 1.0)                 # Çizimden parça koparmak için kullanılır. 
    .frame(width:200, height :100)          # Çerçeveye göre şekli ayarlamaya yarar. 
    
```
- UI Color Değeriyle Renk Atama

```sh

    var uiColor = UIColor(red:1.0, green:1.0, blue:1.0, alpha:1.0)

    circle()
        .foreground(uiColor)
        .fill(Color.init(uiColor: uicolor))
```