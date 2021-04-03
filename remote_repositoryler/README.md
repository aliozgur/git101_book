---
description: Ali Özgür
---

# Remote Repository'ler

Günlük çalışmamız sırasında staging ve commit gibi versiyon kontrolü ile ilgili işlemlerin çoğunu yerel diskimizde yer alan local repository üzerinde yaparız. Proje'de çalışan tek kişi siz iseniz muhtemelen Internet'de veya yerel ağıda yer alan remote bi repository oluşturmanıza da gerek olmayacaktır.

Ancak takım çalışması söz konusu olduğunda, takımdaki geliştiricilerin birlikte çalışabilmesi için herkesin değişikliklerini ortak bir alanda yayınlaması ve diğerlerinin de bu ortak alan üzerinden bu değişiklikleri kendi branch'lerine entegre etmesi gerekecektir. Bu durumda başvuracağınız en etkin araç Git'deki Remote Repository işlevleridir. Remote repository'leri en basit anlamda tüm ekibin erişimi olan dosya sunucusu olarak düşünebilirsiniz.

Gelin şimdi Local ve Remote repository'leri birbirinden ayıran temel özelliklere göz atalım

## Konum

Local repository'ler geliştiricilerin kendi bilgisayarlarında yer alırken Remote repository'ler, çoğunlukla internet olmak üzere, ekipteki herkesin erişebileceği bir sunucuda yer alırlar.

## Özellikler

Teknik olarak remote repository'ler ile local repositoryler arasında bir fark yoktur. Local repository'ler için önceki bölümlerde ele aldığımız commit işlemi, branch oluşturma gibi işlemlerin tamamı remote repository'ler için de yapılabiliyor. Ancak tüm bu benzerliklere rağmen remote repository'ler için Working Copy \(aktif branch'deki dosyaların diskimizdeki kopyaları\) yapısı geçerli değildir, remote repository'lerde sadece Git'in veri tabanının tutulduğu **.git** klasörü yer alır.

## Repository Oluşturma

Local bir repository ancak iki şekilde oluşturulabilir

* Boş bir repository olarak sıfırdan **git init** komutu ile oluşturabilirsiniz veya
* Remote bir repository'yi **git clone** komutu ile yerel diskinizde indirebilirsiniz.

Remote repository'ler de iki yöntem ile oluşturulabilir

* Local repository'nizi **git clone** komutunu **--bare** parametresi ile kullanarak remote bir repoository'ye klonlayabilirsiniz veya
* Boş bir remote repository oluşturmak için **git init** komutunu yine **--bare** parametresi ile kullanabilirsiniz.

## Local/Remote iş akışı

Git'de remote repository işlemleri için az sayıda komut vardır. Günlük çalışmamız srasında bölümün başında da belirttiğimiz gibi Git işlemlerimizin çoğu local repositorymiz üzerinde gerçekleşir ve internet veya ağ bağlantısına ihtiyaç duymayız. Ancak remote repository komutlarını kullanabilmek için internet veya ağ bağlantısına ihtiyaç vardır.

Bu bölümümüzde Remote Respository'ler ile ilgili aşağıdaki konuları ele alarak ayrıntıları öğreneceğiz

* Remote Bir Repository'ye Nasıl Bağlantı Sağlanır
* Remote Repository'deki Verilerin İncelenmesi
* Remote Değişiklikleri Entegre Etmek
* Local Bir Branch'i Yayınlamak \(Publish\)
* Branch'leri Silmek

