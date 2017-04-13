# 11.Gün: Birlikte Çalışma (Collaboration)

Bu bölüme kadar ele aldığımız Git komutları ile kendi lokalimizde Git ile temel versiyon kontrol işlemlerini nasıl yapacağımız ile ilgili alıştırmalar yaptık. Bu bölümde ise takım çalışması için, tüm diğer versiyon kontrol sistemlerinde olduğu gibi, Git'in de bize sunduğu imkanlar ile ilgili alıştırmalar yapacağız .

Takım çalışması ve birlikte çalışma modeli açısından Git'i öncülü olan CVS ve Subversion gibi versiyon kontrol sistemlerinden ayıran en önemli iki özelliği şunlardır

* Git her takım üyesine merkezi uzak deponun tam bir yerel kopyasını sağlar. Takım üyeleri bu yerel kopya üzerinde kendi commit'lerini ve dallarını merkezi depo’ya ihtiyaç duymadan istedikleri gibi oluşturup yönetebilirler
* Git ile takım üyeleri değişiklik kümeleri yerine (change set) tekil değişiklikleri ifade eden commit'leri birbirleri ile merkezi depo üzerinden paylaşırlar.

Bu bölümde ele aldığımız komutlar ile diğer repository'ler ile olan bağlantıların nasıl sağlandığını (remote), kendi lokalimizdeki değişiklikleri diğerleri ile nasıl paylaşacağımızı (push) ve diğerlerinin değişikliklerini kendi lokalimize nasıl entegre edeceğimizi (pull) öğreneceğiz.

## git remote
Remote komutu ile yerel deponuz ile uzaktaki bir depo arasında bağlantıları tanımlayabilir, silebilir veya isimlerini değiştirebilirsiniz. Remote komutu ile tanımlanan bağlantı gerçek zamanlı ve canlı bir bağlantı değildir ve bu bağlantılar kullanılarak uzaktaki depo üzerinden doğrudan işlem yapamazsınız. Bu bağlantıları uzun URL'ler yerine diğer Git komutlarında parametre olarak kullanılabilecek kısa yollar olarak düşünmelisiniz.

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Uzak depo kısa yol isimlerini listele
git remote

# Uzak depo ilişkilerini daha ayrıntılı listele
git remote -v

# Uzak depo ilişkisi tanımla
git remote add <kısa yol adı> <uzak depo adresi>

# Uzak depo ilişkisini sil
git remote rm <kısa yol adı>

# Uzak depo kısa yolunun adını değiştir
git remote rename <kısa yol adı> <kısa yol yeni adı>

```

**Soru-1:** remote komutunu çalıştırdığınızda çıktı olarak gördüğünüz origin ne anlama geliyor?

**Soru-2:** git remote add komutu ile kullanabileceğimiz URL tipleri nelerdir?

## git fetch
Fetch komutu uzak depolardaki değişiklikler ile ilgili bilgeleri yerel deponuzun Git veri tabanı ile senkronize etmenizi sağlar. 

```bash
# varsayılan uzak depodaki (origin) tüm dalların bilgilerini almak için
git fetch

# Uzak depo kısa yolu ile tanımlı uzak depodaki tüm dalların bilgilerini almak için
git fetch <uzak depo kısa yolu>

# Uzak depo kısa yolu ile tanımlı uzak depodaki belirli bir dalın bilgilerini almak için
git fetch <uzak depo kısa yolu> <dal adı>

```

Fetch sonrasında uzak depo dallarını git checkout ile aktif hale getirip inceleyebilir ve git log ile de uzak depo dalının commit tarihçesine göz atabilirsiniz. Eğer uzak depo dalındaki değişiklikleri kendi yerel deponuzdaki bir dala birleştirmek etmek isterseniz git merge komutunu kullanabilirsiniz.


### Alıştırma
Projeniz için Git servisi üzerinde oluşturduğunuz uzak depodaki değişiklikleri fetch ile alıp yerel dalınız ile birleştirin. Bu alıştırmayı yapmak için uzak deponuzu bu aşamaya kadar kullandığınız klasörden farklı bir konuma klonlayın ve bu klon üzerinden değişikli yaparak uzak deponuza push edin.

**Soru-1:** downstream ve upstream terimlerinin ne anlama geldiğini araştırın.

## git pull
Uzak depodaki değişikliklerin yerel deponuza kopyalanması ve otomatik olarak entegre edilmesi için kullanılır. Bu işlemi git fetch ve sonrasında git merge ile iki komut kullanarak da yapabilirsiniz, ancak git pull bu işlemi tek komutla yapmamızı sağlar.

```bash
# varsayılan uzak depodaki (origin) değişiklikleri almak için 
git pull

# Uzak depo kısa yolu ile ilişkilendirilmiş konumdan değişiklikleri almak için
git pull <uzak depo kısa yolu>

# Merge yerine rebase kullanarak değişiklikleri almak için
git pull –rebase <uzak depo kısa yolu>
```

## git push
Yerel deponuzdaki commit'leri (değişiklikleri) uzaktaki depoya gönderip takımın geri kalanı ile paylaşmak için git push komutu kullanılır.

```bash
# Yerel daldaki değişiklikleri uzak depoya gönder 
git push

# Bir daldaki değişiklikleri uzak depo kısa yolu ile ilişkilendirilmiş uzak depoya gönder
git push <uzak depo kısa yolu> <dalın adı>

# Tüm yerel dallardaki değişiklikleri uzak depo kısa yolu ile ilişkilendirilmiş uzak depoya gönder
git push <uzak depo kısa yolu> -- all

# Yerel depodaki tag’leri uzak depoya gönder
git push <uzak depo kısa yolu> -- tags
```

**Soru-1:** push işlemi sırasında bir çakışma oluşabilir mi?


[<< Geri](Gun_10.md) | [Ana Sayfa](README.md)
