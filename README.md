Clean Code Kitabı - 1. ve 2. Bölümün Detaylı İncelemesi
________________________________________
1. Bölüm: Introduction (Giriş)
Bu bölüm, temiz kodun ne olduğunu, neden önemli olduğunu ve bir yazılım geliştiricisi için ne anlama geldiğini açıklıyor.
Temiz Kod Nedir?
•	Tanımlar:
Temiz kodun ne olduğuna dair farklı bakış açıları sunulur. Örneğin:
o	Temiz kod, bir hikaye gibi okunabilir, anlaşılması kolaydır. (Grady Booch)
o	Temiz kod, basit ve doğrudan olan bir koddur. Gereksiz karmaşıklıktan arınmıştır. (Bjarne Stroustrup)
o	Temiz kod, bir geliştirici tarafından kolayca bakım yapılabilir ve genişletilebilir. (Dave Thomas)
•	Uncle Bob’un Tanımı:
Temiz kod, okuyanın kodun ne yaptığını hemen anlayabildiği ve sadece doğru çalışmakla kalmayıp mükemmel bir yapı ve tasarım barındıran koddur.
Neden Temiz Kod?
•	Kötü kod yazmak hızlı görünebilir ancak uzun vadede projeyi yavaşlatır.
•	Bakım ve geliştirme süreleri uzar; ekiplere maliyeti artar.
•	Temiz kod yazmak, bir yazılım projesinin uzun ömürlü olmasını sağlar.
•	Yazılım geliştiriciler, bir kodun hem yazarı hem de okuyucusudur. Kodun okunabilirliği, yazım süreci kadar önemlidir.
Kirli Kodun Etkileri
•	Teknik borç: Kirli kod, kısa vadeli çözümler nedeniyle yazılır ve bu da zamanla projeyi karmaşık hale getirir.
•	Motivasyon düşüklüğü: Kötü yazılmış kodlar üzerinde çalışmak zorunda kalmak geliştiricileri yorabilir ve hayal kırıklığı yaratabilir.
Temiz Kod Yazma Felsefesi
•	Kod, tasarım kadar sanat ve zanaat içerir. Yazılımcılar, kod yazarken disiplinli, düşünceli ve tutarlı olmalıdır.
•	"Kod çalışıyorsa yeterlidir" anlayışı terk edilmelidir. Kod sadece çalışmamalı, aynı zamanda anlamlı, sürdürülebilir ve etkili olmalıdır.
________________________________________
2. Bölüm: Meaningful Names (Anlamlı İsimler)
Bu bölümde, değişken, fonksiyon ve sınıflar için isimlendirme kuralları ve bunların temiz kod üzerindeki etkileri açıklanır.
Anlamlı İsimlerin Önemi
•	Kod, insanlar tarafından okunmak için yazılır. Anlamlı isimler, kodun kendini açıklamasını sağlar.
•	Bir isme bakarak, onun ne iş yaptığını anlamak mümkündür. Yani isimler, kodun kendisi kadar önemli bir dokümantasyon aracıdır.
İyi Bir İsimlendirme İçin İlkeler
1.	Amaçları Yansıtmalı:
o	İsimler, değişkenin veya fonksiyonun yaptığı işi açıkça ifade etmelidir.
o	Örneğin, getUserInfo() fonksiyonu, kullanıcının bilgilerini döndüreceğini açıkça belirtir.
2.	Yanıltıcı Olmamalı:
o	İsimler yanlış bir anlam çağrıştırmamalıdır.
o	Örneğin, accountList ismi bir liste gibi görünse de bir koleksiyon olabilir. Doğru isim: accounts veya accountCollection.
3.	Kısaltmalardan Kaçının:
o	Kısaltmalar genellikle anlaşılmaz olur. Örneğin, hp yerine healthPoints, ctrl yerine control gibi açık isimler tercih edilmelidir.
4.	Genel ve Bağlamdan Kopuk Olmamalı:
o	data, value gibi genel isimler kullanmaktan kaçınılmalıdır.
o	İsmin bağlama özel ve açıklayıcı olması gerekir. Örneğin, data yerine userData veya transactionData.
5.	İsimlendirme Deseni Tutarlı Olmalı:
o	Benzer işlevlere sahip değişken ve fonksiyonlar benzer şekilde adlandırılmalıdır.
o	Örneğin, getName(), setName() gibi mantıksal bir ilişki korunmalıdır.
Sınıf ve Fonksiyon İsimleri
•	Sınıflar:
o	İsimlendirme, sınıfın ne olduğunu açıkça anlatmalıdır.
o	Örneğin: OrderProcessor (Sipariş işleme sınıfı).
•	Fonksiyonlar:
o	İsimler bir eylem (fiil) ile başlamalıdır:
	calculateTotal(), fetchData() gibi.
Bağlamın Önemi
•	Bağlam, kodun anlaşılabilirliğini artırır.
•	Örneğin:
o	state ismi kendi başına bağlamsızdır. Ancak addressState bağlam sağlayarak, değişkenin bir adresle ilgili olduğunu belirtir.
Kötü İsim Örnekleri ve Çözüm
•	Kötü: int d;
o	Anlamlı hale getirin: int daysSinceLastUpdate;
•	Kötü: function process()
o	Açıklayıcı hale getirin: function processPayment();
İsimlendirme Özet Kuralları
•	Açık, kısa ve öz olun.
•	İsmi okuyan kişi, ne anlama geldiğini hemen anlamalı.
•	Bağlam sağlayın ve proje genelinde tutarlılığı koruyun.
Clean Code Kitabı - 3. ve 4. Bölümün Detaylı İncelemesi
________________________________________
3. Bölüm: Functions (Fonksiyonlar)
Bu bölümde, temiz kod yazmak için iyi fonksiyon tasarımı üzerine yoğunlaşılır. İyi bir fonksiyon, yalnızca bir işi doğru şekilde yapan, anlaşılır ve bakım dostu bir yapıdadır.
İyi Bir Fonksiyonun Özellikleri
1.	Küçük Olmalı:
o	Fonksiyonlar kısa olmalıdır. Bir fonksiyonun uzunluğu genellikle 20 satırı geçmemelidir.
o	Uzun fonksiyonlar kodun anlaşılmasını zorlaştırır ve karmaşıklığı artırır.
2.	Tek Bir İş Yapmalı (Single Responsibility):
o	Fonksiyonlar yalnızca bir işi yapmalıdır ve bu işi mükemmel şekilde gerçekleştirmelidir.
o	Eğer fonksiyonun ne yaptığını anlatmak için "ve" kelimesini kullanıyorsanız, o fonksiyon muhtemelen iki iş yapıyordur.
3.	Okunaklı ve Anlamlı Olmalı:
o	Kod okuyucusu, fonksiyonun adını ve içeriğini görerek ne yaptığını hemen anlayabilmelidir.
o	Karmaşık algoritmalar, açıklayıcı isimlerle daha anlaşılır hale gelir.
4.	İsimlendirme Doğru Yapılmalı:
o	Fonksiyon isimleri bir fiil veya fiil cümlesi içermelidir.
o	Örneğin: 
	İyi: calculateTotalPrice(), fetchUserData()
	Kötü: dataProcess(), priceCalc()
5.	Girinti Seviyeleri Az Olmalı:
o	Fonksiyon içindeki if-else blokları ve döngüler mümkün olduğunca azaltılmalıdır.
o	Derin iç içe yapılar yerine, küçük ve bağımsız fonksiyonlara ayırın.
Parametre Kullanımı
•	Az Sayıda Parametre:
o	Fonksiyonlar genellikle 0-2 parametre içermelidir. Üç veya daha fazla parametre gereksinimi varsa, parametreleri bir sınıf veya nesne içinde gruplayabilirsiniz.
o	Örneğin: 
o	calculatePrice(order, taxRate, discount); // Fazla parametre
o	calculatePrice(orderDetails); // Daha temiz
•	Boolean Parametrelerden Kaçının:
o	Bir fonksiyonun anlamını karmaşıklaştırır. Eğer bir parametre olarak true veya false gönderiliyorsa, bu iki farklı işi temsil ediyor olabilir.
Yan Etkilerden Kaçının
•	İdeal bir fonksiyon, yalnızca tanımlı işi yapar ve dış dünya üzerinde beklenmeyen etkiler yaratmaz.
•	Örneğin, bir "getUserData()" fonksiyonu yalnızca veri döndürmeli; aynı zamanda bir dosya yazmak gibi ek bir iş yapmamalıdır.
Void (Geri Döndürmeyen) Fonksiyonlardan Kaçının
•	Fonksiyonlar genellikle bir değer döndürmelidir. Eğer bir şey yapıyorsa, yaptığı işi sonuç olarak döndürmesi daha iyidir.
Kod Örnekleri
Kötü Örnek:
public void processAccount(Account account) {
    if (account.isActive()) {
        // İşlemler
    } else {
        // İşlemler
    }
}
İyi Örnek:
public void processActiveAccount(Account account) {
    // İşlemler
}

public void processInactiveAccount(Account account) {
    // İşlemler
}
________________________________________
4. Bölüm: Comments (Yorumlar)
Yorumların kodda yeri ve gerekliliği tartışılır. Temiz kod, kendini açıklayan bir yapıya sahip olmalıdır ve ideal olarak yorumlara fazla ihtiyaç duyulmamalıdır.
Yorumların Gerekliliği
•	Yorumlar Kodun Başarısızlığını Gösterebilir: 
o	Yorumlar, genellikle kodun yeterince açıklayıcı olmadığı durumlarda yazılır.
o	İyi yazılmış bir kodda yorumların yerini, anlamlı değişken ve fonksiyon isimleri alır.
Yorum Yazmanız Gereken Durumlar
1.	Amaç veya Niyet Açıklamaları:
o	Kodun neden yazıldığını açıklayan yorumlar bazen gereklidir.
o	Örneğin: 
o	// Veritabanı performansını artırmak için bu sorgu optimize edildi.
2.	Önemli Bilgiler:
o	Eğer kodda bir geçici çözüm (workaround) kullanılıyorsa, bunun nedeni belirtilmelidir.
3.	Uyarılar ve Riskler:
o	Bir fonksiyonun belirli koşullar altında çalışmayabileceği belirtilmelidir.
o	Örneğin: 
o	// Bu fonksiyon sadece JSON formatındaki verilerle çalışır.
Yorumlardan Kaçınılması Gereken Durumlar
1.	Kodun Ne Yaptığını Açıklamak:
o	Kod zaten anlaşılır olmalıdır. Yorumlar, kodun ne yaptığını açıklamaktan ziyade neden yaptığını açıklamalıdır.
o	Örneğin: 
o	// Kullanıcının yaşını 18 ile karşılaştırıyoruz.
o	if (user.getAge() >= 18) {
o	    // ...
o	}
Yukarıdaki yorum gereksizdir.
2.	Eski veya Güncellenmeyen Yorumlar:
o	Kodun değişmesi durumunda, yorumun güncellenmemesi kafa karışıklığı yaratır.
o	Eğer kod kendini açıklıyorsa, eski ve gereksiz yorumları kaldırın.
3.	Blok Yorumlar ve Yığın Yorumlar:
o	Yüzlerce satırlık kodu açıklayan devasa yorumlar genellikle gereksizdir ve kodun okunabilirliğini azaltır.
Yorum Yerine Kodunuzu Geliştirin
•	Kötü Örnek: 
•	// Değeri kontrol ediyoruz.
•	if (value == 10) {
•	    // İşlem
•	}
•	İyi Örnek: 
•	if (isValidThreshold(value)) {
•	    // İşlem
•	}
Kodun Dokümantasyonu
•	Dokümantasyon yorumları, bir API veya dışa açık kod parçasında açıklayıcı olabilir. Ancak, bu yorumlar da temiz ve kısa olmalıdır.
________________________________________
Özet
•	3. Bölüm: Fonksiyonlar küçük, tek sorumluluğa sahip ve okunabilir olmalıdır. Çok parametre kullanmaktan, derin iç içe yapılardan ve yan etkilerden kaçınılmalıdır.
•	4. Bölüm: Kod mümkün olduğunca kendini açıklamalı, gereksiz yorumlardan kaçınılmalı ve yalnızca gerekli durumlarda açıklayıcı yorumlar eklenmelidir.


