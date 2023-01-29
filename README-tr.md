# Clean Code Kitap Özeti

<p align="center">
  <img src="images/chapter-00.jpg">
  <br/>
</p>

Merhabalar,yazılım dünyasında bir mihenk taşı olarak kabul görülen, ve sektörde "clean" yazıyor musun gibi literatüre girmiş bir konuyu sizinle paylaşmak istiyorum. İlk olarak kitap ve yazarından kısaca bahsedeyim.

Robert C. Martin(Uncle Bob); 1970'ten beri bir yazılım uzmanı olan Robert, son 40 yılını Agile Alliance'ı başlatmaktan Agile Programming, Clean Code ve daha fazlası hakkında dönüm noktası niteliğindeki kitaplar yazmaya kadar alanın iyileştirilmesine katkıda bulundu. Bu kitap teknik, pragmatik ve önemlidir. Yazar, teoride neyin işe yarayabileceğinin aksine, pratikte neyin işe yaradığını yazmaya kendisini adamış son derece deneyimli usta ve profesyoneldir.

Not çıkarırken önemli gördüğüm yerleri yazdım yani bu bir özet niteliğindedir. En doğru kaynak tabi kide kitabın kendisini okumanızdır. Uzun bir yazıdan çok madde madde ilerleyerek sizlere yalın halde aktarmayı hedefliyorum. Kitap toplamda 17 bölümden oluşuyor ve tüm bölümlerden bahsedeceğim. Haydi başlayalım;

## İçerik tablosu

- [Chapter 01 - Clean Code](#chapter-01-clean-code)
- [Chapter 02 - Meaningful Names](#chapter-02-meaningful-names)
- [Chapter 03 - Functions](#chapter-03-functions)
- [Chapter 04 - Comments](#chapter-04-comments)
- [Chapter 05 - Formatting](#chapter-05-formatting)
- [Chapter 06 - Objects and Data Structures](#chapter-06-objects-and-data-structures)
- [Chapter 07 - Error Handling](#chapter-07-error-handling)
- [Chapter 08 - Boundaries](#chapter-08-boundaries)
- [Chapter 09 - Unit Tests](#chapter-09-unit-tests)
- [Chapter 10 - Classes](#chapter-10-classes)
- [Chapter 11 - Systems](#chapter-11-systems)
- [Chapter 12 - Emergence](#chapter-12-emergence)
- [Chapter 13 - Concurrency](#chapter-13-concurrency)
- [Chapter 14 - Successive Refinement](#chapter-14-successive-refinement)
- [Chapter 15 - JUnit Internals](#chapter-15-junit-internals)
- [Chapter 16 - Refactoring SerialDate](#chapter-16-refactoring-serialdate)
- [Chapter 17 - Smells and Heuristics](#chapter-17-smells-and-heuristics)
- [Referans](#referans)

## Chapter-01 Clean Code

<p align="center">
  <img src="images/chapter-01.png">
  <br/>
</p>

- Kod yazarken minimal ve düz mantık olmalı. Bu sayede maintenance kolay olur ve error handling konusunda problemler minimal olur.
- Yazılan kod niyetini basit ve etkili bir biçimde yani direkt aktarabilmesi gerekli.
- Okunurluğu yüksek olmalı. Örneğin gazete gibi yukarıdan aşağıya doğru okurken takılmamalı ve rahatça anlaşılabilir olması gerekir.
- Kodu okuyan kişinin beklentisini karşılayabilmesi gerekmektedir.
- Bir kodun clean olduğu okurken ne kadar az yorum yapıldığı ile anlaşılır. Örneğin burada ne demek istemiş sorusunu yada bu ne işe yarıyor gibi şeyleri ne kadar az söylersek o kadar clean olmuştur.
- Tüm testlerden geçmesi gerekmektedir. Testler bir kodun stability artırır ve hataları minimuma yaklaştır.
- Kodun içerisinde tekrar eden kod parçaları olmamalı.
- Minimal class, method, function olması gerek.

## Chapter-02 Meaningful Names

<p align="center">
  <img src="images/chapter-02.png">
  <br/>
</p>

- Variable isimleri okununca ne olduğu anlaşılır olmalı.
- Sabit değerler static variable olarak tutulmalı.
- Variable isimleri genel geçer isimler ile aynı olamalı. Örneğin, kullanılan dilin sabit isimleri yada Unix platformunun kullanılan isimlendirmelerden kaçınmalıdır.
- Programcı kodun anlamını gizleyen yanlış ipuçları bırakmaktan kaçınmalıdır
- Herhangi bir listeyi belir belirtmek için sonuna "List" eklememeliyiz. Ait olduğu şeyi çoğul kullanmalıyız. Örneğin, animal -> animals.
- Anlamlı ayrımlar yapmamalıyız yani noise words kullanmaktan kaçınmalıyız.("the","a","an",etc.)
- Telaffuz edilebilir isimlendirmeler kullanmalıyız.
- Aranabilir isimlendirmeler koymalıyız. İlgili şeyleri belirli bir pattern ile yazmak gibi.
- Bir variable scope göre verilen isimlendirme anlamı doğru oranda artmalıdır.
- Encoding edilmiş değişken isimleri kullanmaktan kaçınmalıyız.
- Class isimlendirmesi verb olmamalıdır.
- Methods isimlendirmesi verb yada verb phrase olmalıdır.
- İsimlendirmeler de şakacı, komik ve alaycı davranmayın. Yani kelime oyunu yapmayın.
- Her abstract concept için farklı bir kelime seçin ve ona bağlı kalın.
- Kodunuzu okuyan kişilerin programcı olacağını unutmayın. Computer Science terimlerini, algoritma adlarını, kalıp adlarını, matematik terimlerini vb. kullanın.

## Chapter-03 Functions

<p align="center">
  <img src="images/chapter-03.png">
  <br/>
</p>

- Fonksiyonlar ve metotlar, class'ların behevior'larını yönetirler.
- Bir fonksiyon uzunluğu 100 satırı geçmemeli. Geçmesi durumunda test yazmayı zorlaştırır.
- Satır uzunluğu 150 karakteri geçmemesi gereklidir. Geçmesi durumunda okunurluğu düşürür.
- Fonksiyon tek bir işten sorumlu olmalıdır. Yani tek bir şey yapmalıdır.
  "Functions should do one thing. They should do it well. They should do it only."
- Fonksiyonumuzun tek bir şey yaptığından emin olmak için, fonksiyondaki tüm ifadelerin aynı abstraction düzeyinde olduğundan emin olmamız gerekir.
- Kod yukarıdan aşağıya doğru akmalıdır. (The Stepdown Rule)
- Fonksiyonumuzu bölerken domain bazlı bölme işlemi yapmalıyız.
- Switch case her zaman kaçınamayız, ancak her bir switch case low-level class gömüldüğünden ve asla tekrarlanamadığından emin olabiliriz. Bunu elbette polymorphism ile yapıyoruz.
- Switch case ile fonksiyonları değil, class'ları çağırmalıyız.
- Fonksiyon isimleri çok uzun yada encoding biçiminde olmamalıdır.
- Bir fonksiyon 3-4 argument geçmemelidir. Daha fazlasından kaçınmalıyız. Test edilebilirliği zorlaştırıyor.
- Daha fazla argument yollamak için ya bir object yada list yollamalıyız.
- Ortak monadic form'dan kaçınmalıyız.
- Flag argument eklemekten kaçınmalıyız. Bu işlevin birden fazla şey yaptığını gösterir. Flag doğruysa bir şey yapar, yanlışsa başka bir şey yapar!
- Side effect'e yol açmamalı. Yani gizlice başka şeylere etkisi olamamalı.
- Fonksiyon ya bir şey yapmalı ya da bir şeye cevap vermeli, ikisini birden yapmamalı. Ya senin fonksiyon bir object durumunu değiştirmeli veya hakkında bazı bilgiler döndürmelidir.
- Error handling'te bir şeydir ve ayrı yönetilmelidir.
- DRY principle(Don’t Repeat Yourself) kendini tekrar etmemek olarak karşımıza gelen güçlü bir prensiptir. Tekrar eden işler karmaşıklığı artırır.
- İlk olarak fonksiyonu çalışır şekilde yaz ve sonra refactoring ederek clean'e çek.

## Chapter-04 Comments

<p align="center">
  <img src="images/chapter-04.png">
  <br/>
</p>

- Rastgele yorum yazılmamalı. Hiç bir amacı olmayan yada rastgele yazılacağına hiç yazılmaması gerekir.
- Kod ile anlatacağın şeyleri yorum ile anlatmak başarısızlıktır.
- Yorumlar kötü kodu telafi etmez. Yorumlar kötü kodlar için yazılmamıştır.
- Anlatmaya çalıştığın şeyi kodla anlat.
- En iyi yorum bir yolunu bulup yazmadığın yorumdur.
- Bazen kurumsal kodlama standartlarımız bizi yasal amaçlar için belirli yorumlar yazmaya zorlar. Yani legal comment yazabiliriz.
- Bilgilendirme yorumları yazabiliriz. (tarih format, regex, etc.)
- Yorumu niyetimizi anlatmaya çalışırken kullanmalıyız.
- Test yazarken yada koda bir işlem sonucunun ne gelmesi gerektiği yoruma yazılabilir.
- İptal edilen yada sorun çıkaran koda yorum yazılabilir.
- TODO yorumlar yazılabilir.
- Önemsiz gözüken bir kısmı öneminin vurgulanması için yazılabilir.
- Kötü yorum kötü kodun bahanesidir.
- Yapmak için yapacaksan hiç yapma. Üstüne düşünerek ve kafa yorarak yorum yazılmalı gerekmektedir.
- Kodu özetleyen yorum yazılmamalı.
- Yorumun ne için yazıldığı belirli olmalı.
- Kodun en tepesinde günlük tarzı yorumlar tutma.
- Boş yorumlar yazma. (Noise Comments)
- Yazdığın kodun aynısını yoruma yazma. (Scary Noise)
- Bazen programcılar bir kaynak dosyada belirli bir konumu işaretlemeyi severler. Bunu yapma.(Position Markers)
- Koda yorum olarak yazar ekleme.
- Kapanan bir parantezin sonuna hangisinin kapandığını yorum olarak yazma.

## Chapter-05 Formatting

<p align="center">
  <img src="images/chapter-05.png">
  <br/>
</p>

- Formatting önemli bir konudur. Farklı formatlar olduğu zaman yapılan değişiklikler asla tespit edilemez. Koda ki diff her zaman anlaşılmaz olur.
- Vertical formatlama önemlidir. Bir kaynak dosya ne kadar büyük olmalıdır sorusuna genel bir cevap vardır. Çok uzun olmaması önerilir. Bunun bir log ölçeği olduğuna dikkat edin, bu nedenle Vertical konumdaki küçük fark, mutlak boyutta çok büyük bir fark anlamına gelir.
- The Newspaper Metaphor; yani bir source dosyasının gazete makalesi gibi olmalıdır. İsim basit ama açıklayıcı olmalıdır. İsim tek başına doğru modülde olup olmadığımızı bize anlatmaya yeterli olmalıdır. Source dosyanın en üst kısımları üst düzey kavramları ve algoritmaları sağlamalıdır. Aşağıya doğru ilerledikçe detay artmalıdır, sonunda source dosyada en düşük seviyedeki fonksiyonları ve detayları bulana kadar. Bir gazete birçok makaleden oluşur; çoğu çok küçüktür. Bazıları biraz daha büyük. Çok azı bir sayfanın tutabileceği kadar metin içerir. Bu, gazeteyi kullanılabilir hale getirir. Gazete, gerçeklerin, tarihlerin ve isimlerin düzensiz bir yığınını içeren uzun bir hikaye olsaydı, o zaman onu okumazdık.
- Vertical Openness Between Concepts; neredeyse tüm kodlar soldan sağa ve yukarıdan aşağıya okunur. Her satır bir ifadeyi veya bir cümleyi temsil eder ve her satır grubu tam bir düşünceyi temsil eder. Bu düşünceler birbirinden boş satırlarla ayrılmalıdır.
- Vertical Density; Açıklık kavramları birbirinden ayırıyorsa, Vertical Density yakın ilişki anlamına gelir. Bu nedenle, sıkı bir şekilde ilişkili olan kod satırları dikey olarak yoğun görünmelidir.
- Vertical Distance; Yakın ilişkili kavramlar dikey olarak birbirine yakın tutulmalıdır. Ayrı dosyalardaki kavramlar için geçersizdir. Yakından ilişkili kavramlar farklı dosyalara ayrılmamalıdır.
- Variable Declarations; variables mümkün olduğunca kullanıldığı yere yakın tanımlanmalıdır.
- Instance variables; class'ların en üstünde tanımlanmalıdır.
- Dependent Functions; Bir fonksiyon diğerini çağırırsa, bunlar dikey olarak yakın olmalı ve mümkünse arayan, arananın üzerinde olmalıdır.
- Conceptual Affinity; belirli kod parçaları, diğer parçalarla yakınında olmak ister. Belli bir kavramsal yakınlıkları var. Bu yakınlık ne kadar güçlüyse,
  aralarında daha az dikey mesafe olmalıdır. Örnek; assert fonksiyonları, çünkü ortak bir adlandırma şemasını paylaşırlar ve aynı temel görevin varyasyonlarını gerçekleştirirler.
- Vertical Ordering; genel olarak, fonksiyon çağrısı bağımlılıklarının aşağı yönü göstermesini istiyoruz. Yani çağrılan bir fonksiyon, çağıran bir fonksiyonun altında olmalıdır
- Horizontal formatlama önemlidir. Bu, satırlarımızı kısa tutmaya çalışmamız gerektiğini gösteriyor. Satır uzunluğumuz 100-120 karaktere kadar çıkabilir.
- Horizontal Openness and Density; aralarındaki ilişkinin güçlü yada zayıf olmasına göre ayırmak için boşluk kullanırız.
- Horizontal Alignment; variable tanımlarken yatay hizalama yapmak yararsızdır.
- Indentation; kodun yukarıdan aşağıya doğru yapısal bir taslağı vardır. Buna uyulması gerekmektedir.
- Breaking Indentation; kısa tanımları tek satıra düşürme.
- Team Rules; her programcının kendi favori formatting kuralları vardır, ancak bir ekipte çalışıyorsa, o zaman ekip kuralları koyar.

## Chapter-06 Objects and Data Structures

<p align="center">
  <img src="images/chapter-06.png">
  <br/>
</p>

- Data abstraction ile verilerimizi saklayabiliriz. (Getter, Setter)
- Procedural kod kullanımı mevcut data structures'ı değiştirmeden mevcut fonksiyon eklenmesini sağlar.
- Object-Oriented kod mevcut fonksiyonlarını değiştirmeden yeni class'lar eklemeyi kolaylaştırır.
- Procedural kod tüm fonksiyonları değişmesi gerektiğinden yeni data structures eklemek zordur.
- Object-Oriented kod tüm class'lar değişmesi gerektiğinden yeni method'lar eklemek zordur.
- Hibrit yapılardan uzak durulmalıdır. Her şeyi zorlaştırır.
- Object dönem bir yapıda, onun üzerinden objeye erişilememesi gerekmektedir. Data structures dönen bir yapıdan, onun üstünden yapının method'una erişilememesi gerekmektedir.
- Data structures ve object'lerden hibrit yapılar kurulmamalıdır.
- Data Transfer Objects; bir data structures'ın özlü biçimi, public variables'ı olan ve fonksiyonları olmayan bir class'tır. Buna bazen veri aktarım nesnesi veya DTO denir. DTO'lar, özellikle veritabanıyla iletişim kurarken veya soketler den gelen mesajları ayrıştırırken vb. çok kullanışlı yapılardır.

## Chapter-07 Error Handling

<p align="center">
  <img src="images/chapter-07.png">
  <br/>
</p>

- Kodu if-else ile kontrol etmektense expection dön.
- Farklı farklı hatalar oluşturabiliriz ve bunları yönetebiliriz.
- Bir Try-Catch-Finally deyiminin Try kısmında kod yürüttüğünüzde, yürütmenin herhangi bir noktada iptal edilebileceğini ve ardından Catch konumunda devam edebileceğini belirtmiş olursunuz. Try blokları bir bakıma transactions gibidir. Catch, denemede ne olursa olsun, programınızı tutarlı bir durumda bırakmalıdır.
- Exception oluşturabilecek bir kod yazarken Try-Catch-Finally ifadesiyle başlamak iyi bir uygulamadır.
- Unchecked Exceptions kullanın.
- Context Exceptions sağlayın.
- Kendi error handling yapını kurmalısın.
- Fonksiyonlar null değer dönmemeli.
- Fonksiyonlara null değer pass edilmemeli.

## Chapter-08 Boundaries

<p align="center">
  <img src="images/chapter-08.png">
  <br/>
</p>

- Bazen Third-Party paketleri satın alırız veya açık kaynak kullanırız. Bir şekilde bu yabancı kodu kendi kodunuza temiz bir şekilde entegre etmeliyiz. Bu bölümde, yazılımımızın sınırlarını temiz tutmaya yönelik uygulamalara ve tekniklere bakıyoruz.
- Using Third-Party Code; direkt kullanma. Bu kod içerisinde çok fazla bağımlılık ve zafiyet doğuruyor. Onun yerine onu kullanan tek bir client yazıp kendi kodun içerisinde istediğin yerden daha kısıtlı bir şekilde erişim sağlayabilirsin. Anlaşılması daha kolay ve kötüye kullanılması daha zor olan bir kodla sonuçlanır.
- Third-Party bağımlılığın olduğunda mock data ile test edebilirsin.
- Third-Party kodu için testler yazmak bizim çıkarımıza olabilir. Third-Party kitaplığımızı nasıl kullanacağınızın net olmadığını varsayalım. Belgeleri okumak ve onu nasıl kullanacağımıza karar vermek için bir veya iki gün (veya daha fazla) harcayabiliriz. Ardından, Third-Party kodunu kullanmak için kodumuzu yazabilir ve düşündüğümüzü yapıp yapmadığını görebiliriz. Karşılaştığımız hataların bizim kodumuzda mı yoksa onların kodunda mı olduğunu anlamaya çalışırken kendimizi uzun hata ayıklama oturumlarında saplanıp kalmış bulsak şaşırmayacağız.
- Third-Party kodunu öğrenmek ve entegre etmek zordur. İkisini aynı anda yapmak iki kat daha zor. Üretim konumuzdaki yeni şeyleri denemek ve denemek yerine, Third-Party kodu anlayışımızı keşfetmek için bazı testler yazabiliriz. Jim Newkirk bu tür testleri öğrenme testleri olarak adlandırır.
- Öğrenme testleri hiçbir şeye mal olmaz. Her halükarda API'yi öğrenmemiz gerekiyordu ve bu testleri yazmak, bu bilgiyi elde etmenin kolay ve izole bir yoluydu. Öğrenme testleri, anlayışımızı artırmaya yardımcı olan kesin deneyimlerdir.
- Öğrenme testleri ücretsiz olmasının yanı sıra olumlu bir yatırım getirisine sahiptir. Third-Party paketinin yeni sürümleri olduğunda, davranışsal farklılıklar olup olmadığını görmek için öğrenme testleri çalıştırıyoruz.
- Bazen geliştirilmekte olan başka bir modüle bağlanacak bir modülde çalışmak gerekir ve API henüz tasarlanmadığı için bilgilerin nasıl gönderileceği hakkında hiçbir fikrimiz yoktur. Bu durumlarda, bekleyen modül ile iletişimi encapsulation için bir interface oluşturmanız önerilir. Bu şekilde modülün kontrolünü elimizde tutuyoruz ve ikinci modül henüz mevcut olmasa da test edebiliyoruz.
- Sınırlarda ilginç şeyler oluyor. Değişim de bunlardan biridir. İyi yazılım tasarımları, büyük yatırımlar ve yeniden çalışma gerektirmeden değişime ayak uydurur. Kontrolümüz dışında bir kod kullandığımızda, yatırımımızı korumak ve gelecekteki değişikliklerin çok maliyetli olmamasını sağlamak için özel dikkat gösterilmelidir.

## Chapter-09 Unit Tests

<p align="center">
  <img src="images/chapter-09.png">
  <br/>
</p>

- Test-Driven Development'ın 3 kuralı, bu üç kural sizi döngüye hapseder ve istenilen geliştirme yapılana kadar tekrarlanır;
  - Başarısız bir unit testi yazmadan production kodu yazamazsınız.
  - Başarısız olmak için yeterli olandan daha fazla unit testi yazamayabilirsin ve compiling başarısız olur.
  - Halihazırda başarısız olan testi geçmek için yeterli olandan daha fazla production kodu yazamazsınız.
- Testleri clean tut.
- Test kodu, production kod kadar önemlidir.
- Code Base de değişiklik yapmamızı kolaylaştırır.
- Testler kesinlikle onurluğu yüksek olamalı ve okunabilir olmalı.
- Test başına bir assert'ta sahip olmalı.
- Her test tek bir işi test etmeli.
- Clean testler bu kısaltmayı takip eder. F.I.R.S.T
  - Fast -> Testler hızlı olmalı.
  - Independent -> Testler bağımsız olmalı.
  - Repeatable -> Testler her ortamda test edilebilir olamalıdır.
  - Self-Validating -> Testler bir sonuç içermeli.(Fail or Pass)
  - Timely -> Testler zamanında yazılması,test yazımını daha başarılı kılar.

## Chapter-10 Classes

<p align="center">
  <img src="images/chapter-10.png">
  <br/>
</p>

- Class organizasyonu (java convention'a göre)
  1. Variables listesi.
  2. Public static constants variables.
  3. Private static variables.
  4. Private instance variables.
  5. Public variable.
  6. Public functions.
  7. Private utilities.
- Yukarıdaki adımları takip eder ve programın bir gazete makalesi gibi okunmasına yardımcı olur.
- Encapsulation; class içerisindeki variables'a direkt erişmek yerine, fonksiyonlar üzerinden erişim sağlanmasıdır.
- Class'lar küçük olamalıdır. Ölcebilmek için sorumluluğuna bakılmalıdır.
- Bir Class yada fonksiyon birine anlatırken, tanımlarken "eğer(if)", "ve(and)", "yada(or)" ve "ama(but)" kelimelerini kullanıyorsan birden fazla sorumluluğa sahip demektir. Clean değildir.
- The Single Responsibility Principle (SRP); bir class veya module yalnızca bir sorumluluğu,değişmesi için yalnızca bir nedeni olması gerektiğini belirtir.
- Bir şeyi yaptım bitti mantığı yanlıştır. Dönüp iyleştirme odaklı olmalısın.
- Hedef işi yapan birden çok ve kendi arasında rotate eden yapılara sahip olmalısın.
- Cohesion; birbirine yakın olan yapıları bir arada tutmalısın.
- Clean code yazmak değişim zamanındaki riski büyük oranda azaltır eder.
- Bazı geliştirmelerde yani class yazmak, sistemin SRP özelliğini korur. Bu yapılması gereken işlemdir. Bu sayede yeni eklenecek yapılar mevcut yapıyı değiştirmeden eklememizi sağlar.
- Isolation için abstract class'lar, interface'lere bağımlı olun.

## Chapter-11 Systems

<p align="center">
  <img src="images/chapter-11.png">
  <br/>
</p>

- Complexity ölcülmelidir.
- Yapım aşaması ile kullanım aşaması birbirinden farklıdır ve ayrılmalıdır.
- Builder patterns kullanılabilinir.
- Dependency Injection; ikincil sorumlukları bir nesneden(IOC) amaca tahsis edilmiş diğer nesnelere tahsis eder ve böylece SRP desteklenir.
- Dependency injection, bağımlılıkları enjecte eden method ve constructor argümant sağlar ve bağımlılıkları birbirine bağlar.
- System Design önemli bir unsurdur.
- Separate concerns adequate yapısı düzgün kurgulanmalıdır.
- Cross-Cutting concerns çözmek için aspect-oriented programming (AOP) kullanılmalıdır.
- Basit ve genişlemeye açık olan sistemler üzerinde dur.
- Sistem test edilebilinir tasarlanmalıdır.
- Standartlar değer kattığını görebiliyorsan, kullanmalısın.
- System clean olamalıdır. Sürecler Agile ilerlenmeli ve TDD odaklı yaklısım sergilenmelidir.
- Hangi seviyede olursanız olun basit düşünmelisiniz.

## Chapter-12 Emergence

<p align="center">
  <img src="images/chapter-12.png">
  <br/>
</p>

- Kent Beck'in dört kuralının iyi tasarlanmış bir yazılım yaratmada önemli ölçüde yardımcı olduğunu düşünüyoruz. Kent'e göre bir tasarım, şu kurallara uyuyorsa basittir;
  - Tüm testleri çalıştırır.
  - Tekrarlanan kod içermez.
  - Programcının amacını net ifade edmişse.
  - Class ve method sayısını en aza indirir.
- Refactoring önemlidir. Düzenli yapılmalı ve sorgulanmalıdır.
- Design pattern kullanımında isimlendirme pattern'ına dikkat edilmelidir. Bu okunurluğu artırır.
- Çok fazla pratik yapmak gereklidir.

## Chapter-13 Concurrency

<p align="center">
  <img src="images/chapter-13.png">
  <br/>
</p>

- Objeler process'lerin absraction'larıdır. Thread'ler ise schedule'un.
- Concurrent programlama kolay değildir. Özellikle yük altında çalışmaya başladığı zaman problemler ortaya çıkacaktır.
- Concurency bir ayrıştırma stratejisidir.(Decoupling)
- Ne zaman çalışacağına schedule belirler.
- Aynı anda birden fazla şey ile muhatap olunuyor.
- Concurency her zaman performansı artırmaya bilir.
- Concurency bir sistem yapılacaksa tasarım değişmelidir.
- Concurency update ve deadlock ile nasıl başa çıkacağını bilmen gereklidir.
- Aynı hatayı yeniden simile etmek zordur.
- Concurency'nin bir life cycle'ı vardır. Ama diğer kod kısımlarından tamamen farklı ve ayrı tutulmalıdır.
- Data consistency için "Lock" kullanılır. Atomic yapılarda aynı işlemi arka kısımda gerçekleştirmektedir.
- Data encopsulation'ı önde tut ve paylaşımlı data ile oynamayı azalt.
- Thread'ler bağımsız olmalıdır. Örnekler, ReentrantLock, Semaphore CountDownLatch.(Öneri: Kullanabileceğiniz sınıfları gözden geçirin.)
- Execution Models; Bound Resources, Mutual Exclusion, Starvation, Deadlock, Livelock. Örnekler; Producer-Consumer,Readers-Writers, Dining Philosophers. (Öneri: Bu temel algoritmaları öğrenin ve çözümlerini anlayın)
- Synchronized Methods; Client-Based Locking,Server-Based Locking,Adapted Server. (Öneri: Paylaşılan bir nesne üzerinde birden fazla yöntem kullanmaktan kaçının)
- Synchronized bölümlerinizi mümkün olduğunca küçük tutun.
- Doğru Shut-Down Kodunu Yazmak Zordur. Graceful shutdown düzeltilmesi zor olabilir. (Öneri: Kapatmayı erken düşünün ve erkenden çalışmasını sağlayın. Beklediğinden daha uzun sürecek. Mevcut algoritmaları gözden geçirin çünkü bu muhtemelen düşündüğünüzden daha zordur.)
- Test etmek için değişik senaryolarda denemeler yapın.
  - Threading hataları ele al.
  - Nonthreaded kodları önce çalıştır.
  - Thread kodu pluggable yap.
  - Thread kodu ayarlanabilir yap.
  - İşlemci sayısından daha fazla thread çağır.
  - Farklı platformlarda çalıştır.
  - Hataları denemek ve sistemi zorlamak için kod kullan.

## Chapter-14 Successive Refinement

<p align="center">
  <img src="images/chapter-14.png">
  <br/>
</p>

Yazılmayı bekliyor.

## Chapter-15 JUnit Internals

<p align="center">
  <img src="images/chapter-15.png">
  <br/>
</p>

Yazılmayı bekliyor.

## Chapter-16 Refactoring SerialDate

<p align="center">
  <img src="images/chapter-16.png">
  <br/>
</p>

Yazılmayı bekliyor.

## Chapter-17 Smells and Heuristics

<p align="center">
  <img src="images/chapter-17.png">
  <br/>
</p>

Yazılmayı bekliyor.

## Referans

- <https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882>
