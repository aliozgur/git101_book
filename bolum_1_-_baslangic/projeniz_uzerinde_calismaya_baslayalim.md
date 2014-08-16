# Projemiz Üzerinde Çalışmaya Başlayalım

Üzerinde çalışacağımız projemizin dosyaları artık yerel diskimizde yer aldığına göre projemiz ile ilgili normal çalışmamıza başlayabiliriz.

> Projenizi ister local bir proje olarak oluşturmuş olun isterseniz remote bir repository'yi klonlamış olun tüm değişiklikleriniz yerel diskinizde gerçekleşecek ve **commitleriniz** ile oluşturacağınız tüm versiyonlar git tarafından yerel diskinizdeki .git klasöründe takip edilecektir. İlerleyen bölümlerde ayrıntılı olarak değineceğimiz **git push** komutunu çalıştırmadığınız sürece yaptığınız değişiklikler remote repository'nin yer aldığı sunucuya gönderilmeyecek.

## Dosya Durumları
Git'de dosyalarınız genel olarak iki durumda olabilir

* Untracked (Takip Edilmeyen): Bu dosyalar versiyon kontrolü altında olmayan veya sizin henüz versiyon kontrolü yapmak için git'e eklemediğiniz dosyalardır. Bu dosyalardaki değişiklikler siz dosyaları git'e eklemediğiniz sürece versiyon kontrolüne tabi değildir
* Tracked (Takip Edilen): Bu dosyalar ise git'in versiyon kontrolü takibi altında olan dosyalardır. Bu dosyalar üzerinde yapacağınız tüm değişiklikler git tarafından takip edilmektedir.

## Staging Area
Git'deki en temel kavramlarından birisi de **Staging Area** kavramıdır. Staging Area'yı, proje dosyalarımızdaki bir dizi değişikliği remote repository'ye göndermeden önce kayıt altına aldığımız veritabanı/alan olarak tanımlayabiliriz.
