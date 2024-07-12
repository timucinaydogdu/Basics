<img src="https://upload.wikimedia.org/wikipedia/en/thumb/5/56/Xcode_14_icon.png/120px-Xcode_14_icon.png" align="left" >

## Xcode Ayarları Ve Kullanım Notları

## **Açıklama:** Xcode da bilinmesi gereken ayarlar ve notlar. 

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
  - View Library
  - Modifiers Library
  - Snippets Library
  - Media Library
  - Color Library

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

### Kısayollar Ve Uygulama Notları ;
//          -> Yorum satırı için kullanılır. 

/*
  -> Çoklu yorum satırında kullanılır. 
*/ 

 	Command + ? -> Seçilen satırları toplu olarak yorum satırı olarak kapatır açar.

​	Command + Sol Click -> Jump To Definition Location (Tanımlama noktasına gider)

​	Command + Shift + K -> Derleme klasörünü temizler.

​	Command + B -> Projeyi build eder. 

- Show Build Times Command: Termila Code

```sh
defaults write com.apple.dt.Xcode ShowBuildOperationDuration -bool YES
```

​	Command + N -> SwiftUI View  // Arayüz eklenmesi, tekrarlanan kodlardan sadeleştirmek için kullanılan yapı.

​	Command + Control + E -> Aynı isimlendirmeleri toplu şekilde değiştirmek için kullanılır.

​	Control + Shift + Click -> Çoklu satıra yazı ekleme.

​	Control + I -> Kodun girinti boşluklarını düzenler. 

​	Hold - Option -> Dikey çoklu satır seçimi ve düzenleme.



## Yığın Yapısı

-  VStack -> Bileşenleri dikey olarak alt alta yada üst üste gelecek şekilde yığın olarak kullanılır. 
- HStack -> Bileşenleri yatay olarak yan yana  gelecek şekilde yığın olarak kullanılır.
- ZStack -> Bileşenleri üst üste ekleyenecek şekilde yığın olarak kullanılır. 

Bileşenleri dikey olarak alt alta yada üst üste yığılmasını sağlayan yapıdır. 


```swift
    text("Merhaba Dünya !")      // . text'e ait özellikleri listeler

        .font(.headline)         // Font değişliği yapar. Özellik yerine fonsiyona benzer.
        .foreground(.red)        // Font rengini değiştirir.
        .bold()                  // Yazıyı kalınlaştırır.
        .italic()                // Yazıyı italic yapar. 
        .multilineTextAlignment(.center)    // Çok satırlı yazıyı ortalar.
        .kerning(10)             // Yazı karakterleri arasında 10 piksel oluşturur.
        .frame(width:250, height:150, aligment:Aligment.center)
                                 // Yazıyı bir çerçeveye alır ve yazıyı ortalar. 
		Image("istanbul")						 // Resmin en boy oranını korumak için kullanılan yapı.
				.resizable()
				.aspectRatio(contentMode:.fit)
				.frame(width: UIScreen.main.bounds.width * 0.8, heigth: UIScreen.main.bounds.heigth * 0.3, aligment:.center)					 // Farklı cihazlarda ekranlarda uyum sağlamak için ayarlama.
				.clipShape(Circle())		 // Resimin şekle göre kırpma işlemini yapar.
				.overlay(Circle()				 // Şekil üzerine katman yada yazı eklemesi yapar. 
                .stroke(Color.purple,lineWidth:4))

        .minimimScaleFactor(1.0) // Yazıyı ölçeklendirme için kullanılır. 
        .capitalized             // Metnin arkasına özellik olarak eklenir. 
		
		Button(action:{ print("Tıklandı")}, label:{ Text("Benim Buttonum")}) // Buton ekleme.
		
		NavigationView{							 // Viewler arası geçiş yapmaya yarar.
		NavigationLink( destination: <SwiftUI Görünüme Adı>(), label:{ Text("Başkabir görünüm.")})										 
    }.navigationTitle(Text("AnaGörüme Gider"))
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

```swift

    .foregroundColor(Color("CustomColor"))
    .shadow(color:Color.red, radius:10.0,x:0, y:0)

```

```swift

    circle().fill(color.red)                    // Çember oluştur ve rengini kırmızı yap. 
        .foregroundColor(.green)                //Rengini yeşil yap. 
        .stroke(Color.blue, lineWidth:10.0)     // Çemberin çevre kalınlığını mavi yapar ve kalınlığını ayarlar.. 
        .stroke(style:StrokeStyle(lineWidth:10, lineCap: .butt,dash: [10]))         
        .trim(from:0.0, to 1.0)                 // Çizimden parça koparmak için kullanılır. 
        .frame(width:200, height :100)          // Çerçeveye göre şekli ayarlamaya yarar. 
    
```
- UI Color Değeriyle Renk Atama

```swift

    var uiColor = UIColor(red:1.0, green:1.0, blue:1.0, alpha:1.0)

    circle()
        .foreground(uiColor)
        .fill(Color.init(uiColor: uicolor))
```

### Gradient Bileşenleri Ve Özellikleri ;

- Uygulanacak yapıya göre nesnelere renk doygunluğu verilebilir. 

```swift

    RoundedRectangle(cornerRadius: 10)
        .fill(LinearGradient(gradient: Gradient(colors: [Color.red, Color.blue]), startPoint: .bottomLeading, endPoint: .topTrailing))
        .fill(RadialGradient(colors: [.red,.blue], center: .center, startRadius: 10, endRadius: 100))
        .fill(AngularGradient(colors: [.red,.yellow,.green], center: .bottom, angle: .zero))
        .frame(width: 300.0,height: 200.0)

```

### Image Bileşeni Kullanarak Icon ve Resim Ekleme ve Özellikleri ;

- Uygulanacak uygulamaya göre SF Sembols den icon eklenebilir. Resimler ise assets içine eklenerek add ile çağırılır. 

```swift
// Icon yapısı ve özellikleri. 

    Image(systemName: "heart")
        .font(.system(size: 300))
        .resizable()
        .aspectRatio(contentMode: .fill)
        .foregroundColor(.red)
        .frame(width: 300,height: 300)
        .clipped()
        .background(.black)                

// Image yapısı ve özelikleri. 


    Image("123")
        .resizable()
        .cornerRadius(10)
        .clipShape(Circle())
    
    AsyncImage(url: URL(string: "https://picsum.photos/256")) { image in image
        .image?
        .resizable()
        .frame(width: 500,height: 200)
        .scaledToFit()
        .clipped()
    }


```

### Hizalama Bileşenleri ve Özellikleri ;

- Belli bir çerçeve üzerinde katmanlar oluşturma ve hizalama işlemleri. 

```swift
// Frame ve Aligment

    Text("Selam Dünya")
        .foregroundColor(.black)
        .background(.yellow)
        .frame(height: 100, alignment: .bottom) // Bir sonraki frame içinde hareket eder.
        .background(.green)
        .frame(height: 200, alignment: .top)
        .background(.teal)
        .frame(width: 300, alignment: .leading)
        .background(.brown)
        .frame(maxWidth: .infinity,maxHeight: .infinity,alignment: .topTrailing)
        .background(.blue)
```

### Background ve Overlay Bileşenleri ve Özellikleri ;

- Katmanlar üzerinde işlemler.

```swift
// Like göstergesi.

Image(systemName: "heart.fill")
    .font(.largeTitle)
    .foregroundColor(.white)
    .background(
        Circle()
            .fill (LinearGradient(colors: [.red,.pink], startPoint: .bottomTrailing, endPoint: .topLeading))
            .frame(width: 150,height: 150)
            .shadow(color: .pink, radius: 10,x: 0,y: 10)
            .overlay(
                Circle()
                    .fill(.purple)
                    .frame(width: 50,height: 50)
                    .overlay(
                        Text("10")
                            .foregroundColor(.white)
                                    
                    ),alignment: .topTrailing
            )
    )
// Kutu yerleşimi.

    Rectangle()
        .frame(width: 200,height: 200)
        .overlay(
            Rectangle()
                .fill(.red)
                .frame(width: 50,height: 50),alignment: .topLeading)
                .background(
                    Rectangle()
                        .fill(.orange)
                        .frame(width: 250,height: 250),alignment: .bottomTrailing
                )
    Rectangle()
        .frame(width: 200,height: 200)
        .overlay(
            Rectangle()
                .fill(.red)
                .frame(width: 50,height: 50),alignment: .bottomLeading)
                .background(
                    Rectangle()
                        .fill(.orange)
                        .frame(width: 250,height: 250),alignment: .topTrailing
                )       
```

### Stack Yapıları İle Bileşen Ekleme

- Dikey, yatay ve üst üste bileşenleri eklememize yarayan yapı. 

```swift
// Vertical-Horizontal-Z Stack

    ZStack(alignment: .top) {

        Rectangle()
            .fill(.red)
            .frame(width: 150,height: 150)
        VStack(alignment: .leading, spacing: 20) {
                    
            Rectangle()
                .fill(.pink)
                .frame(width: 30,height: 30)
            Rectangle()
                .fill(.blue)
                .frame(width: 30,height: 30)
            HStack{
                Rectangle()
                    .fill(.orange)
                    .frame(width: 30,height: 30)
                Rectangle()
                    .fill(.orange)
                    .frame(width: 30,height: 30)
            }
            .background(.cyan)
        }
        .background()
    }

```

### Padding Yapıları Ve Kullanımları

- Dinamik olarak farklı cihazlarda da düğru çalışmasını sağlayan boşluk ayarlaması yapan bileşen. Paddingler alt alta yazıldıklarında eklenme özelliği gösterir. 

```swift
// Padding Kullanımı.

    VStack (alignment : .leading){
        Text("Merhaba Dünya !")
            .font(.largeTitle)
            .fontWeight(.semibold)
            .padding(.bottom,20)
        Text("Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.")
    }
    .padding()
    .padding(.vertical,10)
    .background(
        Color.white
            .cornerRadius(10)
            .shadow(color: .black.opacity(0.3), radius: 10,x: 0,y: 10)
    )
    .padding(.horizontal,10)

```

### Spacer Yapıları Ve Kullanımları

- Spacer kullanımı ve yapıları.

```swift
// Spacer Kullanımı.

    HStack{
        Spacer()
            .frame(height: 10)
            .background(.yellow)
        Rectangle()
            .frame(width: 50,height: 50)
            .foregroundColor(.red)
            
        Spacer(minLength: 30) // En düşük uzunluk değeri.
            .frame(height: 10)
            .background(.black)
            
        Rectangle()
            .frame(width: 50,height: 50)
            .foregroundColor(.blue)
        Spacer()
            .frame(height: 10)
            .background(.green)
    }
    .background(.orange)
    .padding(200)

```