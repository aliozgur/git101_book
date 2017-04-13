# 7.Gün: Commit Edilmiş Değişiklikleri Silmek

Bu bölüme kadar değişiklikleri geri almanın üç yöntemini ele aldık, hatırlatmak gerekirse

* Track edilmeyen dosyalardaki (unstaged) değişiklikleri iptal etmek için **git checkout [dosya_adı]**
* Track edilen fakat henüz commit edilmemiş (staged) dosyalardaki değişiklikleri iptal etmek için **git reset HEAD [dosya_adı]** 
* Commit edilmiş bir değişikliği proje tarihçesini bozmadan **git revert [commit_hash]**
	
komutlarını kullanabiliriz.

Bu bölümde ise commit edilmiş değişiklikleri ```git reset --hard``` komutu ile proje tarihçesinden nasıl silebileceğimizi ele alıyoruz. Reset komutunu **--hard** parametresi ile paylaşımlı çalışılan projelerde özellikle uzak depoya yazdığınız değişiklikler için kullanmamanızı öneriyorum. Ancak, çalışma kopyanızda (Working Copy) henüz uzak depoya yazarak ekibinizin geri kalanı ile paylaşmadığınız commitleri **--hard** parametresi ile silebilirsiniz.

Özetlemek gerekirse ```git reset --hard <commit_hash>``` komutu ile yeni bir commit oluşturmadan geri dönülmez bir şekilde herhangi bir commit’i silebilirsiniz.

## Alıştırma-1: Tag oluşturma

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Yeni bir dosya oluşturun
touch <dosya_adı>.txt

# Oluşturduğunuz dosyayı commit edelim
git add -A .
git commit -m “7. gün 1. alıştırma”

# Deponuzun şu anki halini yansıtan v0.1 isimli tag oluşturduk
git tag v0.1
# Depomuzdaki tag’ları listeledik
git tag 

# Depomuzdaki değişiklikleri uzak depo ile senkronize ettik
git push 
```

## Alıştırma-2: Değişikliğn geri alınması

```bash

# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# 1. Alıştırmadaki dosyanızın içeriğini değiştirin

# Dosyadaki değişiklikleri commit edelim
git add -A .
git commit -m “7. gün 2. alıştırma”

# Depomuzu v0.1 ile tagladığımız haline geri döndürelim.
git reset --hard v0.1

# Oluşturduğunuz dosyanın içeriğinin v0.1’deki hali ile aynı oldp olmadığını kontrol edin

# Depomuzun commit tarihçesindeki son 5 commiti listeleyelim
git log -n 5 

# Depomuzdaki değişiklikleri uzak depo ile senkronize ettik
git push 

```

**Soru-1:** Dosyanızın içeriğini tekrar değiştirerek add/commit/push işlemlerini yapın. Sonra projenizi git reset --hard v0.1 komutu ile tekrar v0.1 versiyonuna geri alıp ardından git push ile uzak depoya göndermeye çalıştığınızda nasıl bir hata ile karşılaşıyorsunuz? Bu durumda v0.1'e geri dönmek için ne yapmanız lazım?

**Soru-2:** Oluşturduğunuz v0.1 isimli tag'ı nasıl silersiniz?

**Soru-3:** Oluşturduğunuz tag’ları uzak deponuza nasıl gönderebilirsiniz?


[<< Geri](Gun_06.md) | [İleri >>](Gun_08.md)