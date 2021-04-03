---
description: Ali Özgür
---

# 10.Gün: Rebase

Git’de merge ve rebase komutları benzer işlevleri yerine getirmek için kullanılıyor. Her iki komut da bir daldaki değişiklikleri başka bir dala birleştirmek için kullanılır. Ancak bu iki komut arasında proje tarihçesinin oluşturulması ile ilgili ciddi bir farklılık vardır.

Merge komutu ile A dalındaki değişiklikler B dalı ile birleştirildiğinde B dalının commit tarihçesinde merge işleminden kaynaklanan ve merge commit adı verilen otomatik oluşturulmuş bir commit yer alır. Bu commit A ve B dallarının tarihçelerini birbiri ile ilişkilendirir.

> Merge commit’in ayrıntılarını kitabımızın 5. Bölümünde “Merge Alternatifi Olarak Rebase Kullanımı” başlığı altında ele almıştık.

**rebase** komutu kullandığımızda ise ile A dalındaki her bir commit B dalına sanki commit işlemi B dalında yapılmış gibi yeniden yazılır. Bu sayede B dalının commit tarihçesi sanki tüm değişiklikler bu dalda olmuş gibi düz ve kesintisiz görünür.

## Ne zaman rebase kullanmalıyız?

Rebase komutu yerel ve kısa süreliğine \(örneğin bir hata giderme veya deneysel bir çalışma için oluşturulan\) geçerli dallar için kullanılmalı. Paylaşılan depolarda rebase komutunu kullanmamanızı tavsiye ediyorum, çünkü rebase sonrasında projenizin ana dallarında değişikliklerin nereden kaynaklandığına dair bir bilgi veya ipucu göremezsiniz. Bu durum takım çalışmasını olumsuz yönde etkiler.

> Alıştırmalara başlamadan önce master dalından kopyalanan yerel bir dal oluşturun

## Alıştırma-1

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# master dalını aktif hale getirelim
git checkout master 

# Yeni bir dosya oluşturun
touch ornek_rebase1.txt

# Değişikliklerinizi commit edin
git add -A .
git commit -m “Ad ve soyad eklendi”
```

## Alıştırma-2

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Oluşturduğunuz dalı aktif hale getirelim
git checkout <dalınızın adı> 

# rebase işlemini yapın
git rebase master 

# dalınızın commit tarihçesinin bilgilerini listeleyen
git hist --all # repository tarihçesine göz atın
```

**Soru-1:** Merge ile rebase arasındaki farkı yorumlayın.

## Alıştırma-3

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# master dalını aktif hale getirelim
git checkout master 

# ornek_rebase1 dosyasının içeriğini metin editörünüz ile değiştirin
git add -A .
git commit -m “Master dalındaki değişiklik mesajınız”

# Dalınızı aktif hale getirin
git checkout <dalınızın adı> 

# ornek_rebase1 dosyasının içeriğini metin editörünüz ile değiştirin
git add -A .
git commit -m “Diğer daldaki değişiklik mesajınız”

# rebase işlemini yapın
git rebase master
```

[&lt;&lt; Geri](gun_09.md) \| [İleri &gt;&gt;](gun_11.md)

