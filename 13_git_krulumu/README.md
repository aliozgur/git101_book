# 1.3 Git İle Çalışmaya Başlamak

## Komut satırı mı yoksa görsel arayüz mü?

Git ile çalışmak için git'in kendi **komut satırı arayüznü** (git CLI) veya görsel kullanıcı arayüzü olan 3. parti masaüstü uygulamalar (SourceTree, Tortoise Git, Tower veya Github) kullanabilirsiniz.

Git ile çalışırken görsel arayüzü olan bir uygulama kullanmanız üretkenliğinizi arttırmanıza ve git'in göreceli karmaşık komutlarına daha hızlı ve kolay erişmenizi sağlayacaktır. Diğer yandan git'in komut satırı arayüzünü kullanmanız git ile ilgli daha ayrıntılı bilgilenmenizi ve 3. parti uygulamalara bağımlı kalmadan git ile çalışmanızı sağlayacaktır.

> Komut satırı kullanarak git komutlarını öğrendikten sonra günlük çalışmanızı daha kolay hale getirmek için 3. parti görsel arayüzü olan bir uygulama kullanmanızı öneriyorum.

## Kurulum

Git'in kurulumu hem Windows hem de OS X için oldukça kolay bir işlemdir. Her iki işletim sistemi için tek tıklama ile kurulum yapmanızı sağlayan kurulum programları vardır.

### Windows
İşletim sisteminiz Windows git ile çalışmak için "msysgit" paketini kullanabilirsiniz.

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


### Kullanıcı Adı ve E-mail ayarı




