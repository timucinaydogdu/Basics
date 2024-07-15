<img src="https://upload.wikimedia.org/wikipedia/en/thumb/5/56/Xcode_14_icon.png/120px-Xcode_14_icon.png" align="left" >
<br>

## Xcode Ayarları Ve Kullanım Notları
**Açıklama:** Xcode da bilinmesi gereken ayarlar ve notlar. 

#### Panel Arayüzü

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


### Kısayollar Ve Uygulama Notları ;
// -> Tek satır yorum için kullanılır. 

/* -> Çoklu yorum satırında kullanılır. <- */ 

Command + ? -> Seçilen satırları toplu olarak yorum satırı olarak kapatır açar.

​Command + Sol Click -> Jump To Definition Location (Tanımlama noktasına gider)

​Command + Shift + L -> Kütüphaneyi (Library Views) açar.

​Command + Shift + K -> Derleme klasörünü temizler.

​Command + B -> Projeyi build eder. 

- Show Build Times Command: Terminal Code

```sh
defaults write com.apple.dt.Xcode ShowBuildOperationDuration -bool YES
```

​Command + N -> SwiftUI View  // Arayüz eklenmesi.

​Command + Control + E -> Aynı isimlendirmeleri toplu şekilde değiştirmek için kullanılır.

​Control + Shift + Click -> Çoklu satıra yazı ekleme.

​Control + I -> Kodun girinti boşluklarını düzenler. 

​Hold - Option + Drag Mouse -> Dikey çoklu satır seçimi ve düzenleme.



## Yığın Yapısı

-  VStack -> Bileşenleri dikey olarak alt alta yada üst üste gelecek şekilde yığın olarak kullanılır. 
- HStack -> Bileşenleri yatay olarak yan yana  gelecek şekilde yığın olarak kullanılır.
- ZStack -> Bileşenleri üst üste ekleyenecek şekilde yığın olarak kullanılır. 

Bileşenleri dikey olarak alt alta yada üst üste yığılmasını sağlayan yapıdır. 


```swift
// Text Kullanımı
    Text("Merhaba Dünya !")      // . text'e ait özellikleri listeler

        .font(.headline)         // Font değişliği yapar. Özellik yerine fonsiyona benzer.
        .foreground(.red)        // Font rengini değiştirir.
        .bold()                  // Yazıyı kalınlaştırır.
        .italic()                // Yazıyı italic yapar. 
        .multilineTextAlignment(.center)    // Çok satırlı yazıyı ortalar.
        .kerning(10)             // Yazı karakterleri arasında 10 piksel oluşturur.
        .frame(width:250, height:150, aligment:Aligment.center)
                                 // Yazıyı bir çerçeveye alır ve yazıyı ortalar. 
    Text("^[/(variable)Person](inflect: true)") // Otomatik Gramer Düzenleme
        .foregroundStyle(self.yapildi ? .green : .red) // Koşula bağlı renk değişimi yapar.

// Image Kullanımı
		Image("istanbul")						 // Resmin en boy oranını korumak için kullanılan yapı.
				.resizable()
				.aspectRatio(contentMode:.fit)
				.frame(width: UIScreen.main.bounds.width * 0.8, heigth: UIScreen.main.bounds.heigth * 0.3, aligment:.center)					 // Farklı cihazlarda ekranlarda uyum sağlamak için ayarlama.
				.clipShape(Circle())		 // Resimin şekle göre kırpma işlemini yapar.
				.overlay(Circle()				 // Şekil üzerine katman yada yazı eklemesi yapar. 
                .stroke(Color.purple,lineWidth:4))

        .minimimScaleFactor(1.0) // Yazıyı ölçeklendirme için kullanılır. 
        .capitalized             // Metnin arkasına özellik olarak eklenir. 
				.edgesIgnoringSafeArea(.all) 	// Tüm erkan ilgili görselle kaplanır.
// Gradient Bileşenleri Ve Özellikleri
        RoundedRectangle(cornerRadius: 10)
            .fill(LinearGradient(gradient: Gradient(colors: [Color.red, Color.blue]), startPoint: .bottomLeading, endPoint: .topTrailing))
            .fill(RadialGradient(colors: [.red,.blue], center: .center, startRadius: 10, endRadius: 100))
            .fill(AngularGradient(colors: [.red,.yellow,.green], center: .bottom, angle: .zero))
            .frame(width: 300.0,height: 200.0)

```

## Butonlar Ve Kullanımları
- SwiftUI'da buton kullanımı oldukça esnektir ve çeşitli şekillerde özelleştirilebilir. Temel kullanımdan başlayarak, butonları durumlarla ilişkilendirebilir ve özel stiller uygulayabilirsiniz.
```swift
//Temel Buton Kullanımı
VStack { 
            // Basit bir buton oluşturuyoruz
            Button(action: {
                // Butona tıklandığında yapılacak işlemler buraya yazılır
                print("Butona tıklandı!")
            }) {
                // Butonun içeriği buraya yazılır
                Text("Butona Tıkla")
                    .padding() // Butona dolgu ekler
                    .background(Color.blue) // Butonun arka plan rengini belirler
                    .foregroundColor(.white) // Butonun metin rengini belirler
                    .cornerRadius(10) // Butona köşe yuvarlaması ekler
            }
        }
// Butonla Durum Değiştirme
struct ContentView: View {
    // Butona tıklanınca değişecek bir durum oluşturuyoruz
    @State private var buttonText = "Butona Tıkla"
    // @State özelliğini kullanarak butona tıklanıldığında butonun metnini değiştirdik. @State, SwiftUI'da durumun otomatik olarak güncellenmesini sağlar.

    var body: some View {
        VStack {
            Button(action: {
                // Butona tıklandığında durum değişir
                buttonText = "Butona Tıklandı!"
            }) {
                Text(buttonText)
                    .padding()
                    .background(Color.green)
                    .foregroundColor(.white)
                    .cornerRadius(10)
            }
        }
        .padding() // VStack'e dolgu ekler
    }
}
// Buton Stilleri
struct CustomButtonStyle: ButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        configuration.label
            .padding()
            .background(configuration.isPressed ? Color.gray : Color.blue)
            .foregroundColor(.white)
            .cornerRadius(10)
            .scaleEffect(configuration.isPressed ? 0.95 : 1.0) // Butona basıldığında küçülme efekti
            .animation(.spring(), value: configuration.isPressed) // Animasyon ekler
    }
}
        VStack {
            Button(action: {
                print("Özel butona tıklandı!")
            }) {
                Text("Özel Buton")
            }
            .buttonStyle(CustomButtonStyle()) // Özel buton stilini uygular
        }
// CustomButtonStyle adlı özel bir buton stili oluşturduk. Butona basıldığında arka plan rengini ve boyutunu değiştirerek bir animasyon ekledik.


```

## NavigationView Kullanımı
- SwiftUI'da navigasyon, NavigationView ve NavigationLink kullanılarak oldukça kolay bir şekilde gerçekleştirilebilir. NavigationView genel çerçeveyi sağlarken, NavigationLink geçişleri kontrol eder. Durum yönetimi ve veri geçişi de bu yapı içinde rahatlıkla yapılabilir. 
```swift
// Temel NavigationView ve NavigationLink Kullanımı
import SwiftUI

struct ContentView: View {
    var body: some View {
        NavigationView {
            VStack {
                // NavigationLink ile başka bir görünüme geçiş yapar
                NavigationLink(destination: DetailView()) {
                    Text("Detay Sayfasına Git")
                        .padding()
                        .background(Color.blue)
                        .foregroundColor(.white)
                        .cornerRadius(10)
                }
            }
            .navigationTitle("Ana Sayfa") // Navigasyon çubuğunun başlığını ayarlar
        }
    }
}

struct DetailView: View {
    var body: some View {
        Text("Bu, detay sayfası.")
            .navigationTitle("Detay Sayfası") // Detay sayfasının başlığını ayarlar
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// Duruma Bağlı Navigasyon
import SwiftUI

struct ContentView: View {
    @State private var isActive = false

    var body: some View {
        NavigationView {
            VStack {
                Button(action: {
                    // Butona tıklandığında isActive durumunu değiştirir
                    isActive = true
                }) {
                    Text("Detay Sayfasına Git")
                        .padding()
                        .background(Color.green)
                        .foregroundColor(.white)
                        .cornerRadius(10)
                }
                // isActive durumuna bağlı olarak navigasyonu kontrol eder
                NavigationLink(destination: DetailView(), isActive: $isActive) {
                    EmptyView()
                }
            }
            .navigationTitle("Ana Sayfa")
        }
    }
}

struct DetailView: View {
    var body: some View {
        Text("Bu, detay sayfası.")
            .navigationTitle("Detay Sayfası")
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// Geri Dönüş ve Veriyi Geri Gönderme
import SwiftUI

struct ContentView: View {
    @State private var message = ""

    var body: some View {
        NavigationView {
            VStack {
                NavigationLink(destination: DetailView(message: $message)) {
                    Text("Detay Sayfasına Git")
                        .padding()
                        .background(Color.blue)
                        .foregroundColor(.white)
                        .cornerRadius(10)
                }
                Text("Mesaj: \(message)")
            }
            .navigationTitle("Ana Sayfa")
        }
    }
}

struct DetailView: View {
    @Binding var message: String

    var body: some View {
        VStack {
            TextField("Mesajı buraya girin", text: $message)
                .textFieldStyle(RoundedBorderTextFieldStyle())
                .padding()
        }
        .navigationTitle("Detay Sayfası")
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

// Liste ve NavigationLink Kullanımı
import SwiftUI

struct ContentView: View {
    var items = ["Item 1", "Item 2", "Item 3"]

    var body: some View {
        NavigationView {
            List(items, id: \.self) { item in
                NavigationLink(destination: DetailView(item: item)) {
                    Text(item)
                }
            }
            .navigationTitle("Item Listesi")
        }
    }
}

struct DetailView: View {
    var item: String

    var body: some View {
        Text("Seçilen item: \(item)")
            .navigationTitle("Detay Sayfası")
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}


```

## Temel List Kullanımı
- SwiftUI'da List bileşeni, dinamik veri görüntülemek ve kullanıcı etkileşimlerini yönetmek için güçlü bir araçtır. Temel kullanımdan başlayarak, NavigationLink, dinamik veriler ve kullanıcı etkileşimleriyle daha karmaşık yapılar oluşturabilirsiniz. 
```swift
import SwiftUI

struct ContentView: View {
    // Gösterilecek öğelerin dizisi
    let items = ["Item 1", "Item 2", "Item 3"]

    var body: some View {
        NavigationView {
            // List, diziyi görüntülemek için kullanılır
            List(items, id: \.self) { item in
                Text(item) // Her öğe için bir metin bileşeni oluşturur
            }
            .navigationTitle("Liste") // Navigasyon çubuğunun başlığını ayarlar
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

// Liste İçinde NavigationLink Kullanımı : Kullanıcı bir öğeye tıkladığında, DetailView görünümüne yönlendirilir ve seçilen öğe hakkında bilgi görüntülenir.
import SwiftUI

struct ContentView: View {
    let items = ["Item 1", "Item 2", "Item 3"]

    var body: some View {
        NavigationView {
            List(items, id: \.self) { item in
                NavigationLink(destination: DetailView(item: item)) {
                    Text(item)
                }
            }
            .navigationTitle("Liste")
        }
    }
}

struct DetailView: View {
    var item: String

    var body: some View {
        Text("Seçilen öğe: \(item)")
            .navigationTitle("Detay Sayfası")
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

// Liste İçinde Dinamik Verilerle Çalışma
import SwiftUI

struct ContentView: View {
    // @State ile dinamik verileri tanımlıyoruz
    @State private var items = ["Item 1", "Item 2", "Item 3"]
    @State private var newItem = ""

    var body: some View {
        NavigationView {
            VStack {
                HStack {
                    TextField("Yeni öğe", text: $newItem)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .padding()

                    Button(action: addItem) {
                        Text("Ekle")
                            .padding()
                            .background(Color.blue)
                            .foregroundColor(.white)
                            .cornerRadius(10)
                    }
                    .padding(.trailing)
                }

                List {
                    ForEach(items, id: \.self) { item in
                        Text(item)
                    }
                    .onDelete(perform: deleteItems) // Öğeleri silmek için
                    .onMove(perform: moveItems)     // Öğeleri taşımak için
                }
                .navigationTitle("Listeye Ekle")
                .navigationBarItems(trailing: EditButton())// Düzenleme modu için buton
            }
        }
    }
    // Öğeleri ekleme işlemi
    func addItem() {
        if !newItem.isEmpty {
            items.append(newItem)
            newItem = "" // Metin girişini temizle
        }
    }
    // Öğeleri silme işlemi
    func deleteItems(at offsets: IndexSet) {
        items.remove(atOffsets: offsets)
    }
    // Öğeleri taşıma işlemi
    func moveItems(from source: IndexSet, to destination: Int) {
        items.move(fromOffsets: source, toOffset: destination)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}


```

## Temel Identifiable Kullanımı
- SwiftUI'da Identifiable protokolü, verilerin benzersiz şekilde tanımlanmasını sağlayarak listeleme ve veri yönetimi işlemlerini kolaylaştırır. 

```swift
import SwiftUI

// Identifiable protokolünü uygulayan basit bir model
struct Item: Identifiable {
    var id = UUID() // Benzersiz bir id için UUID kullanılır
    var name: String
}

struct ContentView: View {
    // Item modelinden bir dizi oluşturuyoruz. Her öğe için benzersiz bir id oluşturduk.
    let items = [
        Item(name: "Item 1"),
        Item(name: "Item 2"),
        Item(name: "Item 3")
    ]

    var body: some View {
        NavigationView {
            // Identifiable olan öğeleri listelemek için List kullanılır
            List(items) { item in
                Text(item.name) // Her öğenin adını gösterir
            }
            .navigationTitle("Identifiable Liste")
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

// Identifiable ve Dinamik Veriler

import SwiftUI
    // Item modeli Identifiable olarak tanımlandı
struct Item: Identifiable {
    var id = UUID()
    var name: String
}
struct ContentView: View {
    // @State kullanarak dinamik bir öğe listesi
    @State private var items = [
        Item(name: "Item 1"),
        Item(name: "Item 2"),
        Item(name: "Item 3")
    ]
    @State private var newItemName = ""

    var body: some View {
        NavigationView {
            VStack {
                HStack {
                    TextField("Yeni öğe", text: $newItemName)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .padding()

                    Button(action: addItem) {
                        Text("Ekle")
                            .padding()
                            .background(Color.blue)
                            .foregroundColor(.white)
                            .cornerRadius(10)
                    }
                    .padding(.trailing)
                }

                List {
                    // Identifiable olan öğeleri ForEach ile listelemek
                    ForEach(items) { item in
                        Text(item.name)
                    }
                    .onDelete(perform: deleteItems)
                    .onMove(perform: moveItems)
                }
                .navigationTitle("Dinamik Identifiable Liste")
                .navigationBarItems(trailing: EditButton())
            }
        }
    }

    // Yeni bir öğe ekleme işlevi
    func addItem() {
        if !newItemName.isEmpty {
            items.append(Item(name: newItemName))
            newItemName = "" // Metin girişini temizle
        }
    }

    // Öğeleri silme işlevi
    func deleteItems(at offsets: IndexSet) {
        items.remove(atOffsets: offsets)
    }

    // Öğeleri taşıma işlevi
    func moveItems(from source: IndexSet, to destination: Int) {
        items.move(fromOffsets: source, toOffset: destination)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}


```
## Temel Identifiable Kullanımı
-  SwiftUI'da Section, liste öğelerini gruplandırmak ve düzenlemek için güçlü bir araçtır. Section bileşeni, başlık ve alt bilgi eklemeyi, dinamik olarak bölümler oluşturmayı ve her bölüm için özel görünümler tanımlamayı sağlar. 

```swift
import SwiftUI

struct ContentView: View {
    let fruits = ["Apple", "Orange", "Banana"]
    let vegetables = ["Carrot", "Broccoli", "Cucumber"]

    var body: some View {
        NavigationView {
            List {
                // Meyve bölümünü tanımlıyoruz
                Section(header: Text("Fruits")) {
                    ForEach(fruits, id: \.self) { fruit in
                        Text(fruit)
                    }
                }
                
                // Sebze bölümünü tanımlıyoruz
                Section(header: Text("Vegetables")) {
                    ForEach(vegetables, id: \.self) { vegetable in
                        Text(vegetable)
                    }
                }
            }
            .navigationTitle("Grocery List") // Navigasyon çubuğunun başlığını ayarlar
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// Dynamic Sections
import SwiftUI

struct ContentView: View {
    @State private var sections = [
        SectionData(title: "Fruits", items: ["Apple", "Orange", "Banana"]),
        SectionData(title: "Vegetables", items: ["Carrot", "Broccoli", "Cucumber"])
    ]
    @State private var newSectionTitle = ""
    @State private var newItem = ""

    var body: some View {
        NavigationView {
            VStack {
                HStack {
                    TextField("New Section", text: $newSectionTitle)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .padding()
                    
                    Button(action: addSection) {
                        Text("Add Section")
                            .padding()
                            .background(Color.blue)
                            .foregroundColor(.white)
                            .cornerRadius(10)
                    }
                    .padding(.trailing)
                }

                HStack {
                    TextField("New Item", text: $newItem)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .padding()
                    
                    Button(action: addItem) {
                        Text("Add Item")
                            .padding()
                            .background(Color.green)
                            .foregroundColor(.white)
                            .cornerRadius(10)
                    }
                    .padding(.trailing)
                }

                List {
                    ForEach(sections) { section in
                        Section(header: Text(section.title)) {
                            ForEach(section.items, id: \.self) { item in
                                Text(item)
                            }
                        }
                    }
                }
                .navigationTitle("Dynamic Sections")
            }
        }
    }

    func addSection() {
        if !newSectionTitle.isEmpty {
            sections.append(SectionData(title: newSectionTitle, items: []))
            newSectionTitle = ""
        }
    }

    func addItem() {
        if !newItem.isEmpty, !sections.isEmpty {
            sections[0].items.append(newItem)
            newItem = ""
        }
    }
}

struct SectionData: Identifiable {
    var id = UUID()
    var title: String
    var items: [String]
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// Section ile Görünüm Özelleştirme
import SwiftUI

struct ContentView: View {
    let items = [
        Item(category: "Fruits", name: "Apple"),
        Item(category: "Fruits", name: "Orange"),
        Item(category: "Vegetables", name: "Carrot"),
        Item(category: "Vegetables", name: "Broccoli")
    ]

    var body: some View {
        NavigationView {
            List {
                ForEach(Dictionary(grouping: items, by: { $0.category }).sorted(by: { $0.key < $1.key }), id: \.key) { category, items in
                    Section(header: Text(category)) {
                        ForEach(items) { item in
                            HStack {
                                Text(item.name)
                                Spacer()
                                Image(systemName: "star")
                            }
                        }
                    }
                }
            }
            .navigationTitle("Custom Section")
        }
    }
}

struct Item: Identifiable {
    var id = UUID()
    var category: String
    var name: String
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```

## @State Kullanımı
-  SwiftUI'da @State, kullanıcı arayüzünde etkileşimli ve dinamik içerikler oluşturmak için kullanılır. @State ile tanımlanan durum değişkenleri, değerleri değiştiğinde kullanıcı arayüzünü otomatik olarak günceller. Bu özellik, formlar, listeler, anahtarlar, kaydırıcılar ve daha pek çok etkileşimli bileşenle kullanılabilir.

```swift
// Basit @State Örneği

import SwiftUI

struct ContentView: View {
    // @State ile bir durumu tanımlıyoruz
    @State private var name: String = ""
    // @State ve name ile binding şekilde bağlıdır. 

    var body: some View {
        VStack {
            // TextField ile kullanıcıdan metin girişi alıyoruz
            TextField("Enter your name", text: $name)
                .padding()
                .textFieldStyle(RoundedBorderTextFieldStyle())

            // Butona tıklandığında name değişkenini güncelliyoruz
            Button(action: {
                print("Hello, \(name)!")
            }) {
                Text("Say Hello")
                    .padding()
                    .background(Color.blue)
                    .foregroundColor(.white)
                    .cornerRadius(10)
            }
        }
        .padding()
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// @State ile Dinamik Liste

import SwiftUI

struct ContentView: View {
    // @State ile dinamik bir öğe listesi tanımlıyoruz
    @State private var items: [String] = ["Item 1", "Item 2", "Item 3"]
    @State private var newItem: String = ""

    var body: some View {
        NavigationView {
            VStack {
                HStack {
                    // Yeni öğe için metin girişi
                    TextField("New item", text: $newItem)
                        .textFieldStyle(RoundedBorderTextFieldStyle())
                        .padding()

                    // Yeni öğe ekleme butonu
                    Button(action: {
                        addItem()
                    }) {
                        Text("Add")
                            .padding()
                            .background(Color.green)
                            .foregroundColor(.white)
                            .cornerRadius(10)
                    }
                    .padding(.trailing)
                }

                // Dinamik öğe listesi
                List {
                    ForEach(items, id: \.self) { item in
                        Text(item)
                    }
                    .onDelete(perform: deleteItems) // Öğeleri silme işlevi
                }
                .navigationTitle("Dynamic List")
                .navigationBarItems(trailing: EditButton()) // Düzenleme modu butonu
            }
        }
    }

    // Yeni öğe ekleme işlevi
    func addItem() {
        if !newItem.isEmpty {
            items.append(newItem)
            newItem = "" // Metin girişini temizle
        }
    }

    // Öğeleri silme işlevi
    func deleteItems(at offsets: IndexSet) {
        items.remove(atOffsets: offsets)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// @State ile Toggle ve Slider Kullanımı
import SwiftUI

struct ContentView: View {
    // @State ile bir anahtar ve bir kaydırıcı durumu tanımlıyoruz
    @State private var isOn: Bool = false
    @State private var sliderValue: Double = 0.5

    var body: some View {
        VStack {
            // Toggle bileşeni, boolean durumunu değiştirir
            Toggle(isOn: $isOn) {
                Text("Switch")
            }
            .padding()

            // Slider bileşeni, double bir değeri değiştirir
            Slider(value: $sliderValue, in: 0...1)
                .padding()

            // Durumları metin olarak gösteriyoruz
            Text("Switch is \(isOn ? "ON" : "OFF")")
            Text("Slider value is \(sliderValue, specifier: "%.2f")")
        }
        .padding()
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```
## Temel Sheet Kullanımı

-  SwiftUI'da sheet, geçici olarak bir alt görünümü (modal) sunmak için kullanılır. @State ve @Binding kullanarak sheet'in gösterilip gösterilmeyeceğini ve sheet içindeki verileri kontrol edebiliriz. Bu özellik, kullanıcıya ek bilgiler göstermek veya ek eylemler yaptırmak için oldukça kullanışlıdır.

```swift
// Basit Bir Sheet
import SwiftUI

struct ContentView: View {
    // @State ile sheet'in gösterilip gösterilmeyeceğini kontrol ediyoruz
    @State private var isShowingSheet = false

    var body: some View {
        VStack {
            // Butona tıklandığında sheet'i göster
            Button("Show Sheet") {
                isShowingSheet = true
            }
            .padding()
            .sheet(isPresented: $isShowingSheet) {
                // Sheet'in içeriği
                SheetView()
            }
        }
    }
}

struct SheetView: View {
    var body: some View {
        VStack {
            Text("This is a sheet")
                .font(.largeTitle)
                .padding()
            
            // Sheet'i kapatmak için bir buton
            Button("Dismiss") {
                // Sheet'i kapatmak için sunan görünümde isPresented durumunu false yapmalıyız
                // Bunu gerçekleştirmek için Binding kullanmalıyız, bu yüzden burada kapatma işlevi yok
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// Sheet İçinde Veri Paylaşımı
import SwiftUI

struct ContentView: View {
    @State private var isShowingSheet = false
    @State private var message = "Hello from ContentView"

    var body: some View {
        VStack {
            // Sheet'e veri geçmek için message değişkenini kullanıyoruz
            Button("Show Sheet") {
                isShowingSheet = true
            }
            .padding()
            .sheet(isPresented: $isShowingSheet) {
                SheetView(message: message)
            }
        }
    }
}

struct SheetView: View {
    var message: String // Ana görünümden gelen veri

    var body: some View {
        VStack {
            Text(message) // Geçilen mesajı göster
                .font(.largeTitle)
                .padding()
            
            Button("Dismiss") {
                // Sheet'i kapatmak için bir buton
                // Sheet'i sunan görünümde isPresented durumunu false yapmalıyız
                // Bu örnekte kapatma işlevi yok, çünkü binding ile yönetilmiyor
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
// Sheet'i Dismiss Etme (Kapatma)
import SwiftUI

struct ContentView: View {
    @State private var isShowingSheet = false

    var body: some View {
        VStack {
            Button("Show Sheet") {
                isShowingSheet = true
            }
            .padding()
            .sheet(isPresented: $isShowingSheet) {
                // Sheet'i kapatma işlevi olan bir görünüm
                SheetView(isPresented: $isShowingSheet)
            }
        }
    }
}

struct SheetView: View {
    // Sheet'in gösterilip gösterilmeyeceğini kontrol eden binding
    @Binding var isPresented: Bool

    var body: some View {
        VStack {
            Text("This is a sheet")
                .font(.largeTitle)
                .padding()
            
            Button("Dismiss") {
                // Sheet'i kapatmak için binding değerini false yapıyoruz
                isPresented = false
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

// Sheet ile Form Kullanımı
import SwiftUI

struct ContentView: View {
    @State private var isShowingSheet = false

    var body: some View {
        VStack {
            Button("Show Sheet") {
                isShowingSheet.toggle()
            }
            .padding()
            .sheet(isPresented: $isShowingSheet) {
                // Sheet içinde form içeren bir görünüm
                FormSheetView(isPresented: $isShowingSheet)
            }
        }
    }
}

struct FormSheetView: View {
    @Binding var isPresented: Bool
    @State private var name: String = ""
    @State private var email: String = ""

    var body: some View {
        NavigationView {
            Form {
                Section(header: Text("User Information")) {
                    TextField("Name", text: $name)
                    TextField("Email", text: $email)
                }
                
                Section {
                    Button("Submit") {
                        // Formu göndermek için işlemler yapılabilir
                        print("Name: \(name), Email: \(email)")
                        isPresented = false // Form gönderildikten sonra sheet'i kapat
                    }
                    Button("Cancel") {
                        isPresented.toggle() // False yapmak için
                        // isPresented = false // İptal butonuna tıklandığında sheet'i kapat
                    }
                }
            }
            .navigationTitle("Form")
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```