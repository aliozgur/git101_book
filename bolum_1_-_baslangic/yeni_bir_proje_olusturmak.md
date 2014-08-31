# Local bir proje oluşturmak
Henüz version kontrolü altında olmayan bir projenizi versiyon kontrolü altına almak için **git init** komutunu kullanırız. Bu işlemi gerçekleştirmek için Mac OS X'de Terminal uygulamasını Windows'da ise Git Bash'i açarak aşağıdaki komutları çalıştırmanız gerekir

    $ cd proje/klasörünüzün/yolu/
    $ git init

Bu işlemden sonra

    ls -la

komutu ile proje klasörünüz altındaki dosyaları listelediğinizde klasörün içinde *.git* isimli gizli bir klasörün olduğunu göreceksiniz. *git init* komutu ile projemiz için **boş** bir repository oluşturduk. Ancak proje klasörümüzde dosyalar ve başka klasörler bulunmasına rağmen bu dosya ve klasörlerin hiç biri henüz Git tarafından versiyon kontrolü altına alınmadı.
> **Working copy**: Projenizin ana klasörüne *Working Copy* veya *Working Directory* ismi verilir. Bu klasörde projenizde yer alan dosyaların ve klasörlerin bir kopyası bulunur. Versiyon kontrol sistemine projenizin herhangi bir versiyonunu Working Copy'nize kopyalamasını söyleyebilirsiniz, ancak bir anda Working Copy'nizde projenizin sadece bir versiyonu yer alır.

## Versiyon kontrolü altına almak istemediğimiz dosyalar

Tüm geliştirme ortamları ve işletim sistemlerinde kullandığımız araçlar tarafından ara bir ürün olarak üretilen ve aslında doğrudan versiyon kontrolü altına almak istemediğimiz dosya veya klasörler olacaktır. Örneğin Mac OS X'in otomatik olarak ürettiği gizli *DS_Store* isimli klasör veya C++ derleyicileri tarafından üretilen *.o* uzantılı *obj* dosyaları gibi. Hangi dosyaların versiyon kontrolü altında tutulacağına ve hangilerinin göz ardı edileceğine Git otomatik olarak karar vermez, bu kararı sizin vermeniz gerekir.

> Kullandığınız geliştirme araçlarına bağlı olarak hangi dosyaların göz ardı edilebileceği ile ilgili GitHub'in yayınladığı [derlemeye](https://github.com/github/gitignore) göz atabilirsiniz.

Versiyon kontrolü altına almak istemediğiniz dosya ve klasörleri tanımlamak için proje klasörüne eklenen *.gitignore* dosyası kullanılır. Bu dosya'ya göz ardı etmek istediğiniz dosya ve klasörlerin tespit edilebilmesi için doğrudan isimler veya basit kurallar ekleriz. Projelerinizi versiyon kontrolü altına aldıktan sonra ilk iş olarak GitHub'in yayınladığı derlemeyi veya kendi deneyiminiz ve bilginiz ile karar vereceğiniz dosya ve klasörleri **.gitignore** dosyasına ekleyiniz. Projenizin ilerleyen aşamalarında bu işlemi yapmanız biraz daha zahmetli olacaktır.

Şimdi gelin *.gitignore* dosyasında kuralları nasıl tanımlayabileceğimize bir göz atalım

    *.[oa]
    .~
İlk satırda **o** veya **a** uzantısı ile biten dosyaların versiyon kontrolü dışında tutulması için bir kural tanımlıyoruz. İkinci satırda ise **~** karakteri ile biten (çoğu metin düzenleme uygulaması geçici dosyaları ~ ile biten dosyalar olarak otomatik oluşturur) dosyaların versiyon kontrolü haricinde tutması için kural tanımlıyoruz.

.gitignore dosyasında tanımlama yaparken aşağıdaki kurallar geçerlidir

* Boş satırlar veya # ile başlayan satırlarda yaptığınız tanımlamalar Git tarafından dikkate alınmaz.
* \*, ?, [ ], { }, [!] ve \ gibi karakterler kullanılarak oluşturulan ve  *[globbing patterns](http://www.tldp.org/LDP/GNU-Linux-Tools-Summary/html/x11655.htm)* adı verilen tanımlayıcılar kullanabilirsiniz
* Klasörleri belirtmek için **/** karekteri kullanılır. Örneğin **/projemde/versiyon/kontrolü/istemedigim/bir/klasor/** şeklinde bir tanım yaptığımızda ilgili klasör ve altındaki tüm dosyalar Git tarafından göz ardı edilir.
* Tanımladığınız bir kuralın tersini **!** simgesi ile tanımlarız. Örneğin *!/projemin/kaynak/kodu/* şeklinde bir tanım yaptığımızda bu klasör dışındaki tüm klasör ve dosyalar Git tarafından göz ardı edilecektir.

## İlk commitimiz
Projemizi versiyon kontrolüne alıp göz ardı edilmesini istediğimiz klasör ve dosyaları da belirledikten sonra aşağıdaki komutlar ile ilk commit işlemimizi yapabiliriz

    $ git add -A
    $ git commit -m "İlk commit işlemimizi yaptık"

Bu komutların ne işe yaradığına sonraki bölümlerde değineceğiz, şimdilik
* İlk komutun tüm proje dosyalarının Staging Area'ya eklenmesi için,
* İkinci komutun ise dosyalarımızın bir açıklama ile commit edilmesi için
kullanıldığını söylemek ile yetinelim.

> Yukarıdaki iki komut'u arka arkaya kullanmak yerine aynı işlemi *git commit -a* komutu ile de yapabiliriz.
