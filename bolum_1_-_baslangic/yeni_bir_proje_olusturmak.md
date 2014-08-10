# 1.5 Yeni bir proje oluşturmak
Henüz version kontrolü altında olmayan bir projenizi versiyon kontrolü altına almak için *git init* komutunu kullanmalıyız. Bu işlemi gerçekleştirmek için OS X'de Terminal uygulamasını Windows'da ise Git Bash'i açarak aşağıdaki komutları yazmanız gerekiyor

    $ cd proje/klasörünüzün/yolu/
    $ git init

Bu işlemden sonra

    ls -la

komutu ile proje klasörünüz altındaki dosyalara göz attığımızda proje klasörümüze *.git* isimli gizli bir klasörün eklendiğiniz göreceksiniz. *git init* komutu ile projemiz için **boş** bir repository oluşturduk. Ancak proje klasörümüzde dosyalar ve başka klasörler bulunmasına rağmen bu dosya ve klasörlerin hiç biri henüz git tarafından versiyon kontrolü altına alınmadı.
> **Working copy**: Proje'nizin ana klasörüne *Working Copy* veya *Working Directory* ismi verilir. Bu klasörde projenizde yer alan dosyaların ve klasörlerin yerel bir kopyası bulunur. Versiyon kontrol sistemine projenizin herhangi bir versiyonunu Working Copy'nize kopyalamasını söyleyebilirsiniz, ancak bir anda Working Copy'nizde projenizin sadece bir versiyonu yer alır.

## Versiyon kontrolü altına almak istemediğimiz dosyalar

Tüm geliştirme ortamları ve işletim sistemlerinde kullandığımız araçlar tarafından ara bir ürün olarak üretilen ve aslında doğrudan versiyon kontrolü altına almak istemediğimiz dosya veya klasörler olacaktır. Örneğin OS X işletim sisteminin otomatik olarak ürettiği gizli DS_Store isimli klasör veya C++ derleyicileri tarafından üretilen .o uzantılı obj dosyaları gibi. Hangi dosyaların versiyon kontrolü altında tutulacağına ve hangilerinin göz ardı edileceğine git otomatik karar vermez, bu kararı sizin vermeniz gerekiyor.

> Kullandığınız geliştirme araçlarına bağlı olarak hangi dosyaların göz ardı edilebileceği ile ilgili GitHub'in yayınladığı [derlemeye](https://github.com/github/gitignore) göz atabilirsiniz.

Versiyon kontrolü altına almak istemediğiniz dosyla ve klasörleri tanımlamak için git proje klasörünüz altındaki *.gitignore* dosyasını kullanmakatadır. Bu dosya'ya göz ardı etmek istediğiniz dosya ve klasörlerin tespit edilebilmesi için doğrudan isimler veya basit kurallar tanımlayabilirsiniz. Projelerinizi versiyon kontrolü altına aldıktan sonra ilk iş olarak GitHub'in yayınladığı derlemeyi veya kendi deneyiminiz ve bilginiz ile karar vereceğiniz dosya ve klasörleri .gitignore dosyasına ekleyiniz. Projenizin ilerleyen aşamalarında bu işlemi yapmanız biraz daha zahmetli olacaktır.

Şimdi gelin *.gitignore* dosyasında kuralları nasıl tanımlayabileceğimize bir göz atalım

    *.[oa]
    .~
İlk satırda git'e **o** veya **a** uzantısı ile biten dosyaları versiyon kontrolü dışında tutumasını söylüyoruz. İkinci satırda ise **~** karakteri ile biten (çoğu metin düzenleme uygulaması geçici dosyaları ~ ile biten dosyalar olarak otomatik oluşturur) dosyaları versiyon kontrolü haricinde tutması gerektiğini tarif ediyoruz.

.gitignore dosyasında tanımlama yaparken aşağıdaki kurallar geçerlidir

* Boş satırlar veya # ile başlayan satırlarda yaptığınız tanımlamalar git tarafından dikkate alınmaz.
* \*, ?, [ ], { }, [!] ve \ gibi karakterler kullanılarak oluşturulan ve  *[globbing patterns](http://www.tldp.org/LDP/GNU-Linux-Tools-Summary/html/x11655.htm)* adı verilen tanımlayıcılar
* Klasörleri tarif etmek için / karekteri kullanılır. Örneğin **/projemde/versiyon/kontrolü/istemedigim/bir/klasor/** şeklinde bir tanım yaptığımızda ilgili klasör ve içeriği git tarafından göz ardı edilecektir.
* Tanımladığınız bir kuralın tersini ! işareti ile tanımlayabilirsiniz. Örneğin *!/projemin/kaynak/kodu/* şeklinde bir tanım yapıldığında belirtilen klasör dışındaki tüm klasör ve dosyalar git tarafından göz ardı edilecektir.

## İlk commit'imiz
Projemizi versiyon kontrolü altına alıp git'e göz ardı etmesini istediğimiz klasör ve dosyaları tarif ettikten sonra aşağıdaki komutar ile ilk commit'imizi yapabiliriz

    $ git add -A
    $ git commit -m "İlk commit işlemimizi yaptık"

Bu komutları tek tek ne işe yaradığına ilerleyen kısımlarda değineceğiz, şimdilik ilk komutun tüm proje dosyalarımızı commit işlemimiz için eklemesini, ikinci komut ise eklenen bu dosyaların bir yorum mesajı ile birlikte daha önce bahsettiğimiz "staging area" isimli mantıksal alana alınmasını sağlar.

