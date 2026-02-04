# 🎬Sinema Otomasyonu

Bir sinema salonu yönetim sistemi. Windows Forms tabanlı masaüstü uygulaması.

## 📌 Genel Bakış

Sinema Otomasyonu, sinema salonlarının günlük operasyonlarını yönetmek için geliştirilmiş kapsamlı bir masaüstü uygulamasıdır. Bu sistem, sinema işletmelerinin film yönetiminden bilet satışına kadar tüm süreçlerini dijital ortamda yönetmesine olanak tanır. Uygulama, kullanıcı dostu arayüzü ve güçlü veritabanı yönetimi sayesinde sinema personelinin iş yükünü azaltır ve müşteri hizmetlerini iyileştirir.

Sistem, film bilgilerinin kaydedilmesi, seans planlaması, bilet satışı ve koltuk rezervasyonu gibi temel işlevleri tek bir platformda birleştirir. Windows Forms teknolojisi kullanılarak geliştirilmiş olan bu uygulama, masaüstü bilgisayarlarda hızlı ve verimli çalışır. Entity Framework ile SQL Server veritabanı entegrasyonu sayesinde, tüm veriler güvenli bir şekilde saklanır ve hızlı erişim sağlanır.

Uygulamadaki kullanıcı olarak belirtilen kullanıcılar bilet alan kişiler değil büfe görevlileri olarak düşünülmüştür.

## ✨ Özellikler

### 🔐 1. Kullanıcı Yönetimi

Uygulama, güvenli bir giriş sistemi ile başlar. Kullanıcılar, kullanıcı adı ve şifre bilgileri ile sisteme giriş yapabilirler. Giriş ekranında, kullanıcı bilgileri doğrulandıktan sonra ana sayfaya yönlendirme yapılır. Sistem, veritabanında kayıtlı kullanıcı bilgilerini kontrol eder ve geçerli kullanıcılar için erişim sağlar.

### 🎞️ 2. Film Yönetimi

Film yönetimi modülü, sinema salonunun film envanterini yönetmek için tasarlanmıştır. Bu modülde, yeni filmler eklenebilir, mevcut filmler listelenebilir ve gerektiğinde filmler silinebilir. Film ekleme işlemi sırasında, film adı, film türü, film süresi ve film görseli gibi bilgiler girilir. Film silme işlemi yapıldığında, sistem otomatik olarak ilgili seansları ve biletleri de siler, böylece veri tutarlılığı korunur.

### 📅 3. Seans Yönetimi

Seans yönetimi, sinema salonunun gösterim programını oluşturmak ve yönetmek için kritik bir modüldür. Bu modülde, yeni seanslar oluşturulabilir, mevcut seanslar listelenebilir, güncellenebilir ve silinebilir. Seans ekleme işlemi sırasında, kullanıcılar film, salon, tarih ve saat bilgilerini seçerler. Sistem, aynı salon, tarih ve saatte başka bir seans olup olmadığını kontrol eder ve çakışma durumunda uyarı verir.

Seans listeleme ekranında, tüm seanslar bir tablo formatında gösterilir. Kullanıcılar, bu tablodan seans seçerek güncelleme veya silme işlemleri yapabilirler. Seans güncelleme işlemi, ayrı bir form üzerinden gerçekleştirilir ve kullanıcılar seans bilgilerini değiştirebilirler.

Sistem, öğrenci ve tam bilet fiyatlarını ayrı ayrı yönetir. Varsayılan olarak, öğrenci bilet fiyatı 120 TL, tam bilet fiyatı ise 150 TL olarak ayarlanmıştır.

### 🎫 4. Bilet Satışı

Bilet satışı modülü, sistemin en kapsamlı ve kullanıcı dostu bölümlerinden biridir. Bu modülde, müşteriler için bilet satışı gerçekleştirilir. Bilet satış işlemi, film seçimi ile başlar. Kullanıcı, bir film seçtiğinde, o filme ait mevcut seans tarihleri otomatik olarak yüklenir. Tarih seçildiğinde, o tarihe ait seans saatleri gösterilir. Saat seçildiğinde ise, salon koltuk haritası güncellenir ve dolu koltuklar yeşil renkte gösterilir.

Koltuk seçimi, görsel bir harita üzerinden yapılır. Her koltuk, bir buton olarak temsil edilir ve koltuk durumuna göre renklendirilir. Boş koltuklar beyaz, dolu koltuklar yeşil, seçili koltuklar ise kırmızı renkte gösterilir. Kullanıcı, bilet sayısını belirledikten sonra, o sayı kadar koltuk seçebilir. Sistem, seçilen koltuk sayısının bilet sayısına eşit olmasını zorunlu kılar.

Bilet tipi seçimi, öğrenci ve tam bilet olmak üzere iki seçenek sunar. Kullanıcı, verilen bilgilere göre öğrenci ve tam sayısını girer. Toplam tutar, seçilen bilet tipleri ve sayılarına göre otomatik olarak hesaplanır ve ekranda gösterilir.

Müşteri bilgileri, ad ve soyad olarak kaydedilir. Bilet satış işlemi tamamlandığında, sistem tüm seçilen koltuklar için ayrı ayrı bilet kayıtları oluşturur ve veritabanına kaydeder. Bu sayede, her koltuk için ayrı bir bilet numarası oluşturulur ve müşteriler biletlerini takip edebilirler.

### 🔍 5. Bilet Bilgileri

Bilet bilgileri modülü, satılan biletlerin görüntülenmesi için kullanılır. Bilet bilgileri görüntüleme işlemi, bilet ID'si ile gerçekleştirilir. Kullanıcı, bilet ID'sini girdiğinde, sistem ilgili biletin tüm detaylarını gösterir. Bu detaylar arasında müşteri adı ve soyadı, film adı, seans tarihi ve saati, salon numarası, koltuk numarası, bilet tipi ve film görseli yer alır.

Bilet iptal işlemi, bilet satış ekranından yapılabilir. İptal işlemi sırasında, kullanıcı bilet ID'sini girer ve sistem biletin varlığını kontrol eder. Bilet bulunduğunda, kullanıcıya onay mesajı gösterilir ve onaylandığında bilet veritabanından silinir. Bilet silindiğinde, ilgili koltuk otomatik olarak boş duruma geçer ve başka bir müşteri tarafından rezerve edilebilir.

### 💺 6. Koltuk Yönetimi

Koltuk yönetimi, bilet satış sürecinin kritik bir parçasıdır. Sistem, salon koltuklarını görsel bir harita üzerinde gösterir ve her koltuk için gerçek zamanlı durum güncellemesi yapar. Koltuk durumları, renk kodları ile gösterilir: beyaz renk boş koltukları, yeşil renk dolu koltukları, kırmızı renk ise seçili koltukları temsil eder.

Sistem, koltuk seçimi sırasında çeşitli kontroller yapar. Örneğin, dolu bir koltuk seçilmeye çalışıldığında kullanıcıya uyarı mesajı gösterilir. Ayrıca, kullanıcı bilet sayısından fazla koltuk seçmeye çalıştığında sistem uyarı verir. Koltuk seçimi iptal edildiğinde, koltuk otomatik olarak boş duruma döner.

Koltuk haritası, seans bilgileri seçildiğinde otomatik olarak güncellenir. Sistem, seçilen seansa ait dolu koltukları veritabanından çeker ve harita üzerinde gösterir. Bu sayede, kullanıcılar her zaman güncel koltuk durumunu görürler.

## 🛠️ Teknolojiler

### ⚙️ Backend
- **.NET Framework 4.7.1**: Ana framework
- **C#**: Programlama dili
- **Entity Framework 6.5.1**: ORM (Object-Relational Mapping)
- **SQL Server**: Veritabanı yönetim sistemi

### 🎨 Frontend
- **Windows Forms**: UI framework
- **Guna.UI2.WinForms 2.0.4.7**: Modern UI bileşenleri
- **Bunifu.UI.WinForms 8.0.0**: Gelişmiş UI kontrolleri

### 📦Diğer Kütüphaneler
- **Newtonsoft.Json 13.0.3**: JSON işlemleri
- **System.Management**: Sistem yönetimi

### 📸 Uygulama Görselleri

1- Giriş ekranı 
<img width="734" height="484" alt="Ekran görüntüsü 2026-02-05 010450" src="https://github.com/user-attachments/assets/38a26b18-f58c-4f8e-a64a-7cb1a39882bb" />

2- Anasayfa
<img width="1085" height="640" alt="Ekran görüntüsü 2026-02-05 010506" src="https://github.com/user-attachments/assets/36b898f0-e7dc-48df-a413-f7c2655c5542" />

3- Seans Sayfası / Seans Güncelleme / Seans Silme
<img width="1209" height="675" alt="Ekran görüntüsü 2026-02-05 010519" src="https://github.com/user-attachments/assets/6ece10ec-bbc9-4b48-a245-a2be7169ad42" />
<img width="429" height="209" alt="Ekran görüntüsü 2026-02-05 010531" src="https://github.com/user-attachments/assets/53e57925-a944-48a3-bdbd-7103badb56bc" />
<img width="376" height="412" alt="Ekran görüntüsü 2026-02-05 010540" src="https://github.com/user-attachments/assets/845688df-4e3c-42d7-83cb-83c95dda8f81" />

 4- Film Ekleme Sayfası 
 <img width="1203" height="736" alt="Ekran görüntüsü 2026-02-05 010600" src="https://github.com/user-attachments/assets/03140f64-988f-4910-a433-5bf66e19d54d" />

5- Seans Ekleme Sayfası 
<img width="1218" height="687" alt="Ekran görüntüsü 2026-02-05 010617" src="https://github.com/user-attachments/assets/78fad153-33da-4a7e-8942-0cc2398555a5" />

6- Bilet Alma Sayfası 
<img width="1183" height="689" alt="Ekran görüntüsü 2026-02-05 010646" src="https://github.com/user-attachments/assets/f5c7a91d-c501-4414-a3c1-8420d0c0cdac" />

7- Bilet Bilgileri ve Ekran Çıktısı
<img width="376" height="206" alt="Ekran görüntüsü 2026-02-05 010655" src="https://github.com/user-attachments/assets/3839ed52-8235-4b4b-89df-b890a9ac93ee" />
<img width="1221" height="684" alt="Ekran görüntüsü 2026-02-05 010728" src="https://github.com/user-attachments/assets/2ad7b75a-1a94-456e-8a91-2343bfa7fd17" />

### Bu uygulama sınıf arkadaşım Ayşe İldem ÖZTÜRK ile birlikte yaptığımız bir uygulamadır. Kendisine teşekkür ederim. 
