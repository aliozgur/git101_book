---
description: Ali Özgür
---

# 6.Gün: Commit Edilmiş Değişiklikleri İptal Etmek

Bu bölüme kadar değişiklikleri geri almanın iki yöntemini ele aldık, hatırlatmak gerekirse

* Track edilmeyen dosyalardaki \(unstaged\) değişiklikleri iptal etmek için git checkout 
* Track edilen fakat henüz commit edilmemiş \(staged\) dosyalardaki değişiklikleri iptal etmek için ise git reset HEAD  

komutlarını kullanabiliriz. Bu bölümde ise commit edilmiş değişiklikleri git revert komutu ile nasıl geri alabileceğimizi hatırlayıp alıştırmalar yapacağız.

Revert komutunun en önemli özelliği commit edilmiş bir değişikliği otomatik olarak yeni bir commit oluşturarak geri almanızı sağlamasıdır. Revert komutunun bu özelliği sayesinde hata ile yapılan commit'ler de proje tarihçesinde kalmaya devam eder. Özellikle diğer kullanıcılar ile paylaşılan bir depoda çalışıyorsanız ve geri almanız gereken bir commitiniz varsa revert komutunu kullanmamız tavsiye ediyoruz. Ekip arkadaşlarımız bizim yanlışlıkla oluşturduğumuz commit'e dayanarak geliştirme yapmış olabilirler bu nedenle commitimizi geri alırken proje tarihçesine bir iz bırakmalı ve ekipteki diğer kişilerin revert işleminden haberdar olmalarını sağlamamız gerekiyor.

Özetlemek gerekirse git revert ile yeni bir commit oluşturularak önceki commit’deki değişiklikleri proje tarihçesinde iz bırakarak geri alabiliyoruz.

Alıştırmaya geçmeden önce örnek proje deponuzda yaptığınız tüm değişiklikleri `git push` komutu ile uzak deponuza yazmanız gerekiyor

## Alıştırma

```bash
# Projenizdeki herhangi bir dosyayı açıp içeriğini değiştirin
# adiniz.txt dosyasını staging area'ya ekleyin
git add -A .

# Değişikliğinizi commit edin
git commit -m “6. Gün alıştırma”

# Yerel deponuzu uzak depo ile senkronize edin
git push
```

Son commit işleminin hatalı olduğunu varsayalım. Bu değişikliği iptal edip bir önceki versiyona geri dönmek için aşağıdaki komutları sırası ile çalıştıralım

```bash
# Commit tarihçesindeki en son 5 commit kaydının bilgilerini listeleyin
git log -n 5 

# Geri dönmek istediğiniz commit’in hash değerini belirledikten sonra

git revert <commit_hash_ilk_7_karakter> --no-edit

# Yerel deponuzu uzak depo ile senkronize edin
git push
```

**Soru-1:** git push ile değişikliklerinizi uzak depoya göndermemiş olsaydınız geri alma işlemini nasıl yapacaktınız?

**Soru-2:** Son commit hash değerinin tamamı veya 7 karakterini kullanmak yerine farklı nasıl bir parametre kullanabilirdiniz?

**Soru-3:** Commit hash değerinin ilk 7 karakterini kullanmak neden yeterli?

**Soru-4:** git reset ile git revert komutları arasındaki fark nedir?

[&lt;&lt; Geri](gun_05.md) \| [İleri &gt;&gt;](gun_07.md)

