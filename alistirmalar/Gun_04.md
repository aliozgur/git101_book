# 4.Gün: Değişiklikleri Kaydetme

Bu bölümde bilgisayarınızda oluşturduğunuz yerel bir deponun veya uzaktaki bir deponun bilgisayarınızdaki kopyasında yapacağınız değişiklikleri nasıl versiyon kontrolü altına alacağımız ile ilgili bilgilerimizi tazeleyip alıştırmalar yapacağız.

Projenizi ister yerel bir depoda olsun isterseniz uzak bir depodan klonlamış olsun tüm değişiklikleriniz yerel diskinizde gerçekleşecek ve commitleriniz ile oluşturacağınız tüm versiyonlar git tarafından yerel diskinizdeki .git klasöründeki Git veri tabanında kayıt altına alınıp takip edilecektir. git push komutunu çalıştırmadığınız sürece yaptığınız değişiklikler sadece yerel diskinizde kayıt altına alınır.

## Dosya Durumları
Git'de dosyalarınız genel olarak iki durumda olabilir

Takip Edilmeyen (Untracked), bu durumdaki dosyalar versiyon kontrolü altında olmayan veya sizin henüz versiyon kontrolü yapmak için Git'e eklemediğiniz dosyalardır. Bu dosyalardaki değişiklikler siz dosyaları Git'e eklemediğiniz sürece versiyon kontrolüne tabi değildir

Takip Altında (Tracked), bu durumdaki dosyalar ise Git'in versiyon kontrolü takibi altında olan dosyalardır. Bu dosyalar üzerinde yapacağınız tüm değişiklikler git tarafından takip edilmektedir.

## Staging Area
Çoğu versiyon kontrol sisteminde değişiklikleriniz iki yerde kaydedilir
* Yerel diskinizdeki çalışma klasörünüz (working copy) veya
* Versiyon kontrol sisteminin veri tabanı

Ancak Git'de değişikliklerinizin kayıt altına alındığı üçüncü bir alan daha vardır ki buna Staging Area denir ve Git'in en temel kavramlarından birisidir. Staging Area'yı, proje dosyalarımızdaki bir dizi değişikliği yeni bir versiyon olarak mühürlemeden önce kayıt altında tuttuğunuz veri tabanı olarak tanımlayabiliriz.

## git add
Git ile versiyon kontrolü altına aldığınız projenize dosya eklediğinizde, dosya sildiğinizde veya var olan bir dosyanın içeriğini değiştirdiğinizde bu değişiklikler Git tarafından otomatik olarak takip edilmez. Git'in bu dosyaları takip etmesi için git add komutu ile bu dosyaları önce Git’e tanıtmanız gerekir.

### Alıştırma - 1
Uzak deponuzdan bilgisayarınıza klonladığınız proje deponuzun src klasörü altındaki gun_04_01.txt isimli bir dosya ekleyip bu dosyanın içine adınızı ve soyadınızı yazın ve komut satırı ara yüzünden aşağıdaki komutları çalıştırın

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

git status
```
**Soru:** ```git status``` komutunun sonucunda yeni eklediğiniz dosya yukarıda bahsedilen iki durumdan hangisindedir?

### Alıştırma - 2
Uzak deponuzdan bilgisayarınıza klonladığınız proje deponuzun kök klasörü altında gun_04_02 isimli yeni bir klasör oluşturun ve aşağıdaki komutları komut satırı ara yüzünde çalıştırın

```bash
cd <proje_klasörü>

git add -A .

git status
```

**Soru:** ```git status``` komutunun sonucunda yeni eklediğiniz klasör *tracked* bir klasör haline geldi mi?

**Soru:** Boş klasörü tracked hale getirmek için nasıl bir yöntem izlemelisiniz?


### Alıştırma - 3
```git help add``` komutu çalıştırarak add komutuna aşağıdaki işlemleri desteklemek için hangi parametrelerin geçilebileceğini araştırıp her bir durum için git add komutunu çalıştırın.

* gun_04_03 isimli klasörün altındaki tüm txt uzantılı dosyalar
* gun_04_03 isimli klasörün altındaki tüm dosyalar
* Proje klasörünüze eklenen tüm dosyalar
* gun_04_03.txt isimli tek bir metin dosya



## git checkout
Checkout komutu birden fazla amaçla kullanılabilen komutlardan birisidir. Bunlar

* Bir dosyadaki değişiklikleri iptal etmek 
* Çalışma kopyanızdaki (Working Copy) değişiklikleri kaybetmeden projenizin herhangi bir commit'ini incelemek
* Farklı bir dalı çalışma kopyanız olarak aktif hale getirmek
 
Bu bölümde bu komutun kullanımlarından birincisi ile ilgileniyoruz. Checkout komutu ile değiştirdiğimiz ancak henüz git add ile Staging Area'ya eklemediğimiz dosyalardaki değişiklikleri aşağıdaki komut şablonunun kullanarak iptal edebiliriz.

```bash
git checkout <dosya_yolu_ve_dosya_adı>
```

### Alıştırma - 1
Bu alıştırmayı yapmak için öncelikle proje kök klasörü altındaki src klasörüne txt uzantılı metin bir dosya ekleyip dosyayı commit etmeniz gerekiyor. Bu işlemi aşağıdaki komutlar ile hızlıca yapabilirsiniz.

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

touch <dosya_adı_1>.txt

git add -A .

git commit -m “4. gün, ikinci bölüm 1. Alıştırma hazırlığı”
```

Dosyanızı commit ettikten sonra komut satırı ara yüzünde aşağıdaki komutları çalıştırın

```baseh
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# <dosya_adı>.txt dosyasının içeriğini değiştirdikten sonra aşağıdaki komutları çalıştırın
git status

git checkout <dosya_adı_1>.txt
```

### Alıştırma - 2

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# <dosya_adı_2>.txt isimli yeni bir dosya ekleyin ve içine adınızı soyadınızı yazın
git status

git checkout <dosya_adı_2>.txt
```

**Soru:** Aldığınız hatayı nasıl yorumlamamız lazım.

### Alıştırma - 3

```bash
# önceki alıştırmada eklediğiniz <dosya_adı_2>.txt dosyasını git add ile Staging Area'ya ekleyin
# dosyanın içeriğini değiştirin ve kaydedin

$ git checkout <dosya_adı_2>.txt
```

**Soru:** git checkout işlemi sonrasında <dosya_adı_2>.txt dosyasının içeriği Staging Area'ya eklenmeden önceki haline döndü mü? Neden?

## git reset
Reset komut ile Staging Area'ya git add ile eklediğimiz ve Git tarafından takip edilen (tracked) dosyaları Staging Area'dan çıkarabiliriz. Komut şu şablonu şöyle 

```bash
git reset HEAD <dosya_adı>
```

Komut şablonundaki <dosya_adı> parametre değerini vermeden de komutu çalıştırabilirsiniz. Bu durumda Staging Area'daki tüm dosyalar bu alandan çıkarılır ve tekrar takip edilmeyen(untracked) durumuna gelir.

Komut şablonundaki **HEAD** parametre değeri verilmeden de komutu çalıştırabilirsiniz. Bu durumda reset işlemi dosyanızı son commit’de olduğu haline geri getirir. 
 
### Alıştırma

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Daha önceki alıştırmalarda eklediğiniz ve commit ettiğiniz herhangi bir dosyanın içeriğini değiştirin
git status

# dosyanız henüz track edilmiyor

# Değiştirdiğiniz txt uzantılı tüm dosyaları Staging Area’ya ekleyin
git add *.txt

git status
# dosyalarınız tracked hale geldi

git reset HEAD <dosya_adı>.txt

git status
# <dosya_adı>.txt isimli dosyanız tekrar untracked halde
```

**Soru-1:** Dosyanızda yaptığınız değişiklik kayboldu mu?

**Soru-2:** Dosyanızı değişiklik yapılmadan önceki hale getirmek için hangi komutu kullanmanız lazım? 
(İPUCU: Son durumda dosyanız untracked durumda yani Staging Area'da değil)


[<< Geri](Gun_03.md) | [İleri >>](Gun_05.md)