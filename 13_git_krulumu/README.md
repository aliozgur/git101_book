# 1.3 Git İle Çalışmaya Başlamak

## Komut satırı mı yoksa görsel arayüz mü?

Git ile çalışmak için git'in kendi **komut satırı arayüznü** (git CLI) veya görsel kullanıcı arayüzü olan 3. parti masaüstü uygulamalar (SourceTree, Tortoise Git, Tower veya Github) kullanabilirsiniz.

Git ile çalışırken görsel arayüzü olan bir uygulama kullanmanız üretkenliğinizi arttırmanıza ve git'in göreceli karmaşık komutlarına daha hızlı ve kolay erişmenizi sağlayacaktır. Diğer yandan git'in komut satırı arayüzünü kullanmanız git ile ilgli daha ayrıntılı bilgilenmenizi ve 3. parti uygulamalara bağımlı kalmadan git ile çalışmanızı sağlayacaktır.

> Komut satırı kullanarak git komutlarını öğrendikten sonra günlük çalışmanızı daha kolay hale getirmek için 3. parti görsel arayüzü olan bir uygulama kullanmanızı öneriyorum.

## Kurulum

Git'in kurulumu hem Windows hem de OS X için oldukça kolay bir işlemdir. Her iki işletim sistemi için tek tıklama ile kurulum yapmanızı sağlayan kurulum programları vardır.

### Windows
İşletim sisteminiz Windows ise git ile çalışmak için "msysgit" paketini kullanabilirsiniz.

**msysgit** paketini kurmak için [http://msysgit.github.io/](http://msysgit.github.io/) adresinden kurulum uygulamasını indirip çalıştırmalısınız. Kurulum adımları sırasında karşınıza çıkacak olan ekranlarda varsayılan ayarları seçili olarak bırakarak kurulumunuzu tamamlayabilirsiniz.

Kurulum tamamlandıktan sonra Windows Başlangıç menüsünden *Git* klasörü altındaki **Git Bash** uygulamasını çalıştırarak git'in komut satırı arayüzünü kullanmaya başlayabilirsiniz.

> git'in kurulumunun sorunsuz gerçekleştiğini görmek için **Git Bash** uygulamasını çalıştırdıktan sonra **git --version** komutunu yazabilirsiniz. Bu komut ile git'in versiyon bilgisini ekranınızda görmeniz gerekiyor. Eğer hata alırsanız msysgit paketinin ana sayfasından sornu gidermek için kaynakları inceleyebilirsiniz.

### Mac OS X

İşletim siszeminiz OS X ise git kurulumu için iki yöntem kullanabilirsiniz.
* Apple'in geliştirici araçlarını kurarak Apple tarafından sağlanan git dağıtımının bilgisayarınıza kurabilirsiniz
* [https://code.google.com/p/git-osx-installer/downloads/list?can=3](https://code.google.com/p/git-osx-installer/downloads/list?can=3) adresinde OS X için kurulum uygulamasını indirip git'i bilgisayarınıza kurabilirsiniz.

Git kurulumunu tamamladıktan sonra Applications klasörü altındaki Terminal.app uygulamasını çalıştırınız.

> Spotlight'a *terminal* yazarak da Terminal.app uygulamasına çalıştırabilirsiniz

Kurulumunuzu denetlemek için komut satırında **git --version** komutunu çalıştırabilirsiniz. Bu komut git'in versiyonunu ekranda görmenizi sağlayacaktır.Herhangi bir hata almanız durumunda kurulum yönteminize göre ilgili kaynakları araştırmanız gerekecek.

### Git konfigürasyonu
Git kurulumunuzu yaptığınıza göre artık git ile çalışmak için bazı ayarlar yapabilirsiniz. Bu ayarlar için git bize **git config** isimli bir araç sunmaktadır. Bu araç ile yapacağınız ayarları bir defa yapmanız yeterli olacaktır.

> Bu ayarları istediğiniz zaman değiştirebilirsiniz.

Git ayarlarınız aşağıda belirtilen üç konumda kayıt altında tutulmaktadır


1. Seviye (/etc/gitconfig dosyası) : Tüm kullanıcı ve projeler için geçerli olan git ayarları bu dosyada kaydedilir. **git config** aracına **--system** parametresini vererek bu dosyadaki ayarları okuyabilir veya bu dosyaya yazabilirsiniz.
2. Seviye (/.gitconfig dosyası) : Sadece sizin kullanıcınız için tanımlanan git ayarlarının kaydedildiği dosyadır. **git config** aracını **--global** parametresi ile çalıştırısanız ayarlar bu dosyaya kaydedilecek veya bu dosyadan okunacaktır
3. Seviye : Proje klasörünüzün (projenizin git ile versiyon kontrolüne alınmış olması gerekiyor) altında yer alan  **.git/config** dosyasında ise proje bazındaki git ayarlarınız yer almaktadır.

Git ayarlarınızın değerini belirlemek için bu üç konumdaki dosyaları 3. seviye, 2. seviye ve 1. seviye sıralaması ile okur. Ayar'a ilişkin değere ilk hangi seviyede rastlandıysa o seviyedeki değer dikkate alınır diğer seviyelerdeki değerler dikkate alınmaz.

Windows işletim sisteminde global (**git config --global** komutu) git ayarlarınız Windows'un $HOME klasörü altında yer alan (genellikle C:\Documents and Settings\$USER) **.config** dosyasında kayıt altına alınır. Proje seviyesindeki ayarlarınız ise OS X'de olduğu gibi **[Projenizin Ana Klasörü]\.git\config** dosyasında kayıt altına alınır.

### Kullanıcı adınızı ve email bilgisi

Git ayarlarından en önemli olanlarından bir tanesi de kullanıcı adınızın ve email adresinizdir. Git bu ayarlar ile sağladığınız değerleri **commit** vb işlemleri gerçekleştirirken otomatik olarak kullanır. Bu ayarları yapmak için komut satırınızda aşağıdaki komutları çalıştırmalısınız
> * git config --global user.name "ali özgür"
> * git config --global user.email "ali.ozgur@example.com"

Yukarıdaki komutlarda **git config --global** kısmı ile git'e global ayarları düzenlediğinizi ifade ediyorsunuz **user.name** (user.email aynı zamanda) ise değerini değiştirmek istediğiniz anahtar'ı belirterek ardından da çift tırnak içinde ilgili anakhtarın değerini giriyorsunuz.

Bu değerleri **--global** ibaresi ile tüm projeleriniz için geçerli olacak şekilde yapıyoruz, proje seviyesinde bu ayarları yapmak için komut satırında projesinizi klasörüne giderek **git config user.name "ali özgür"** komutu ile --global değerini kullanmadan yapabilirsiniz.

Herhangi bir seviyede ayarlarınızın değeri görmek için aşağıdaki komutları kullanabilirsiniz.

* Global seviyede tüm ayarlarınızı listelemek için
> **git config --global -l** komutunu
* Global seviyede tek bir ayarın değerini görmek için ise
> **git config --global user.name** komutunu kullanabilirsiniz.

<div style="background-color:rgb(247,248,250); padding:10px; marign:10px; border:1px solid darkgrey">
    <p style="font-weight:bold">İPUCU</p>
    <p>git'in komutları ve bu komutların parametreleri ile ilgili yardım almak istediğinizde
        <ul>
            <li>git [komut adı] --help</li>
            <li>git help [komut adı]</li>
        </ul>
    komutlarını kullanabilirsiniz.
    </p>
</div>

### Editör ayarı
Git'in bazı komutları sizden interaktif olarak yorum veya bilgi girmenizi isteyebilir. Bu tür durumlar için git'in hangi metin editörünü kullanmasını istediğinizi ayarlayabilirsiniz. Varsayılan olarak git Vi veya Vim editörlerini kullanır. Ancak bu editörler özellikle başlangıç seviyesindeki kullanıcılar için kullanımı zor olabilir. Ben, Vi veya Vim ile karşılaştırıldığında kullanımının daha kolay olduğunu düşündüğüm için **GNU Midnight Commander (MC)** kullanmanızı öneriyorum.

Midnight Commander'i [Homebrew](http://brew.sh/) ile
> brew install midnight-commander

komutu ile kurabilirsiniz.

Midnight Commander veya git'i destekleyen herhangi bir editör uygulamanızın kurulumunu tamamladıktan sonra

> git config --global core.editor mcedit

komutu ile git'in kullanacağı edtör ayarınızı yapabilirsiniz.

### Diff aracı ayarları

Diff kavramını kitabın ilerleyen bölümlerinde daha ayrıntılı ele alacağız, ancak kısaca değinmek gerekirse

> Bir dosyanın T1 anındaki içeriği ile Tx anındaki içeriğinin arasındaki farkları tespit etme ve gösterme işlemine **diff** denilir

Bu işlemi göz ile yapmak zorunda kalmadan dosyalar arasındaki farkları (aslında sadece dosyalar değil klasörler arasındaki farkları da ele alabliriz) tespit etmek ve görselleştirmek için kullanılan araçlara genel olarak Diff Araçları ismi verilir.

OS X platformunda ben şahsen açık kaynak olan **diffmerge** isimli uygulamayı kullanmayı tercih ediyorum. Git'in diff tool'u olarak **diffmerge**'i kullanmasını sağlamak için
> git config --global merge.tool diffmerge

komutunu kullanabilirsiniz. Diffmerge'in OS X'de tam olarak ayarlanması için gerekli yönergelere [bu adresten](http://twobitlabs.com/2011/08/install-diffmerge-git-mac-os-x/) göz atabilirsiniz.

Windows işletim sisteminde ise yine açık kaynak olan [WinMerge](http://winmerge.org/downloads/) uygulamasını veya ücretli bir araç olan [Araxis Merge'i](http://www.araxis.com/merge/download.en) kullanabilirsiniz. Bu araçların git ayarlarının nasıl yapılacağını yardım dokümanlarından faydalanarak öğrenebilirsiniz.



