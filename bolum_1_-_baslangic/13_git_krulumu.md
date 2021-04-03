---
description: Ali Özgür
---

# Git İle Çalışmaya Başlamak

## Komut satırı mı yoksa görsel arayüz mü?

Git ile çalışmak için git'in kendi **komut satırı arayüzünü** \(Git Command Line Interface\) veya görsel kullanıcı arayüzü olan masaüstü uygulamalar \(SourceTree, Tortoise Git, Tower veya GitHub\) kullanabilirsiniz.

Git ile çalışırken görsel arayüzü olan bir uygulama kullanmanız üretkenliğinizi arttırıp Git'in çok sayıdaki karmaşık komutuna daha hızlı ve kolay erişmenizi sağlar. Diğer yandan Git'in komut satırı arayüzünü kullanmanız Git ile ilgli daha ayrıntılı bilgilenmenizi ve 3. parti uygulamalara bağımlı kalmadan Git ile çalışabilmenizi sağlar.

> Git komutlarını komut satırında öğrendikten sonra günlük çalışmanızda görsel arayüzü olan bir uygulamayı mutlaka kullanmanızı öneriyorum.

## Kurulum

Git'in kurulumu hem Windows hem de Mac OS X için oldukça kolay bir işlemdir. Her iki işletim sistemi için tek tıkla kurulum yapmanızı sağlayan kurulum sihirbazları vardır.

### Windows

İşletim sisteminiz Windows ise git ile çalışmak için "msysgit" paketini kullanabilirsiniz.

**msysgit** paketini kurmak için [http://msysgit.github.io/](http://msysgit.github.io/) adresinden kurulum uygulamasını indirip çalıştırmalısınız. Kurulum adımları sırasında karşınıza çıkacak olan ekranlarda varsayılan ayarları seçili olarak bırakarak kurulumunuzu tamamlayabilirsiniz.

Kurulum tamamlandıktan sonra Windows Başlangıç menüsünden _Git_ klasörü altındaki **Git Bash** uygulamasını çalıştırıp Git'in komut satırı arayüzünü kullanmaya başlayabilirsiniz.

> Git'in kurulumunun sorunsuz gerçekleştiğini teyid etmek için **Git Bash**'i açıp **git --version** komutunu yazın. Bu komut ekrana Git'in versiyon bilgisini basar. Eğer hata alırsanız msysgit ana sayfasından sorunun giderilmesi için ne yapmanız gerektiğini öğrenebilirsiniz.

### Mac OS X

İşletim sisteminiz Mac OS X ise Git kurulumu için iki yöntem kullanabilirsiniz.

* Apple'in geliştirici araçlarını kurarak \(XCode\) Apple tarafından sağlanan Git dağıtımını kurabilirsiniz
* [Git OS X Installer](https://code.google.com/p/git-osx-installer/downloads/list?can=3) paketini indirip Git'i kurabilirsiniz.

Git kurulumunu tamamladıktan sonra Applications klasörü altındaki Terminal.app uygulamasını çalıştırın.

> Spotlight'a _terminal_ yazarak da Terminal.app uygulamasını bulup çalıştırabilirsiniz

Kurulumunuzu denetlemek için komut satırında **git --version** komutunu çalıştırın. Bu komut Git'in versiyonunu ekrana basar.Herhangi bir hata almanız durumunda kurulum yönteminize göre ilgili kaynakları araştırmanız gerekebilir.

### Git Konfigürasyonu

Git'i kurduğumuza göre artık Git ile çalışmak için bazı ayarlar yapabiliriz. Bu ayarlar için Git bize **git config** isimli bir araç/komut sunar. Git ayarlarını bir defa yapmanız yeterli olacaktır.

> Bu ayarları istediğiniz zaman değiştirebilirsiniz.

Git ayarlarınız aşağıda belirtilen üç konumda kaydedilir ve hiyerarşik olarak bu konumlardan yüklenir

1. Seviye \(/etc/gitconfig dosyası\) : Tüm kullanıcı ve projeler için geçerli olan ayarlar bu dosyada kaydedilir. **git config** komutunu **--system** seçeneği ile çalıştırırsanız ayarlar bu dosyada kaydedilecek ve bu dosyadan okunacaktır
2. Seviye \(/.gitconfig dosyası\) : Sadece sizin kullanıcınız için tanımlanan ayarların kaydedildiği dosyadır. **git config** komutunu **--global** seçeneği ile çalıştırısanız ayarlar bu dosyaya kaydedilecek ve bu dosyadan okunacaktır
3. Seviye : Proje klasörünüzün \(projenizin Git ile versiyon kontrolüne alınmış olması gerekiyor\) altında yer alan  **.git/config** dosyasında ise proje bazındaki git ayarlarınız yer alır.

Git, ayarlarınızın değerini belirlemek için bu üç konumdaki dosyaları 3. seviye, 2. seviye ve 1. seviye sıralaması ile hiyerarşik olarak okur. Belirli bir ayar'a ilişkin değere ilk hangi seviyede rastlandıysa o seviyedeki değer dikkate alınır diğer seviyelerdeki değerler dikkate alınmaz.

Windows'da global \(**git config --global** komutu\) git ayarlarınız Windows'un $HOME klasörü altında yer alan \(genellikle C:\Documents and Settings$USER\) **.config** dosyasında yer alır. Proje seviyesindeki ayarlarınız ise OS X'de olduğu gibi **\[Projenizin Ana Klasörü\].git\config** dosyasında kayıt altına alınır.

### Kullanıcı adınızı ve email bilgisi

Git ayarlarından en önemli olanları kullanıcı adınız ve email adresinizdir. Git, ayar olarak tanımladığınız değerleri **commit** vb işlemlerde otomatik olarak kullanır. Bu ayarların değerini belirlemek için komut satırında aşağıdaki komutları çalıştırıyoruz

```text
git config --global user.name "ali özgür"
git config --global user.email "ali.ozgur@example.com"
```

Yukarıdaki komutlarda

* **--global** seçeneği ile Git'e global ayarları düzenlediğinizi söylüyoruz
* **user.name** \(ve user.email\) ile değerini değiştirmek istediğiniz ayarın anahtar'ını belirtiyoruz
* Ardından da çift tırnak içinde ilgili ayarın değerini giriyoruz

Bu ayarları **--global** ibaresi ile tüm projelerinizde geçerli olacak şekilde yaptık, proje seviyesinde bu ayarları yapmak için komut satırında \(terminal'de\) projenizin klasörüne konumlanıp **git config user.name "ali özgür"** komutu ile _--global_ seçeneğini kullanmadan yapabilirsiniz.

Kendi yaptığımız veya kurulum ile hazır gelen ayarların değerlerini görmek için aşağıdaki komutları kullanabiliriz.

* Global seviyede tüm ayarları listelemek için

  > **git config --global -l**

* Global seviyede tek bir ayar'ın değerini \(örneğimizde user.name anahtarına sahip ayar\) görmek için ise

  > **git config --global user.name**

İPUCU

Git'in komutları ve bu komutların seçenek ve parametreleri ile ilgili yardım almak istediğinizde

* git \[komut adı\] --help \(örneğin: git init --help\)
* git help \[komut adı\] \(örneğin: git help init\)

 komutlarını kullanabilirsiniz.

### Editör ayarı

Git'in bazı komutları sizden interaktif olarak yorum veya bilgi girmenizi ister. Bu tür durumlar için Git'in hangi metin düzenleme uygulamasını kullanacağını ayarlayabilirsiniz. Git varsayılan olarak [Vi](http://en.wikipedia.org/wiki/Vi) veya \[Vim\]\([http://en.wikipedia.org/wiki/Vim\_\(text\_editor](http://en.wikipedia.org/wiki/Vim_%28text_editor)\)\) kullanır. Ancak bu editörlerin kullanımı başlangıç seviyesindeki kullanıcılar için zor olabilir. Ben, Vi veya Vim ile karşılaştırıldığında kullanımının daha kolay olduğunu düşündüğüm [**GNU Midnight Commander \(MC\)**](https://www.midnight-commander.org/) kullanmanızı öneriyorum.

Midnight Commander'i Mac OS X'e [Homebrew](http://brew.sh/) kullanarak

```text
brew install midnight-commander
```

komutu ile kurabilirsiniz.

Midnight Commander veya Git'i destekleyen editör kurulumunu tamamladıktan sonra

```text
git config --global core.editor mcedit
```

ile Git'in kullanacağı editör ayarınızı yapabilirsiniz.

### Diff aracı ayarları

Diff kavramını ilerleyen bölümlerimizde daha ayrıntılı ele alacağız, ancak kısaca değinmek gerekirse

> Bir dosyanın Tx anındaki içeriği ile Ty anındaki içeriğinin arasındaki farkları tespit etme ve gösterme işlemidir. İngilizcede **difference** \(fark\) kelimesinin kısaltması olan **diff** şeklide kullanılır.

Bu işlemi göz ile yapmak zorunda kalmadan dosyalar ve/veya klasörler arasındaki farkları tespit etmek ve görselleştirmek için kullanılan araçlara genel olarak Diff Araçları ismi verilir.

Ben, Mac OS X üzerinde ücretsiz bir uygulama olan **SourceGear DiffMerge** kullanmayı tercih ediyorum. Git'in diff aracı olarak SourceGear DiffMerge'i kullanmasını sağlamak için

```text
git config --global merge.tool diffmerge
```

komutu ile ayar yapabilirsiniz. DiffmMerge'in OS X'de tam olarak ayarlarının nasıl yapılacağını öğrenmek için [bu linkte](http://twobitlabs.com/2011/08/install-diffmerge-git-mac-os-x/) göz atabilirsiniz.

Windows'da ise yine ücretsiz bir uygulama olan [WinMerge](http://winmerge.org/downloads/) veya ücretli bir uygulama olan [Araxis Merge'i](http://www.araxis.com/merge/download.en) kullanılabilir. Bu araçların Git ayarlarının nasıl yapılacağını yardım dokümanlarından faydalanarak öğrenebilirsiniz.

