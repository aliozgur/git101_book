---
description: Ali Özgür
---

# Versiyon Kontrolüne Neden İhtiyacımız Var?

Versiyon kontrol sistemi kullanmanın bir çok faydası var ve bu bölümde versiyon kontrol sistemi kullanımının bize sağladığı avantajlardan bahsediyoruz.

## Uyumlu ekip çalışması

Herhangi bir versiyon kontrol sistemi kullanmadığınızda beraber çalıştığınız diğer kişiler ile aynı dosyalar üzerinde çalışabilmek için muhtemelen herkesin erişimine açık paylaşımlı bir klasör kullanmak zorunda kalacaksınız.

Bu tür bir senaryoda kullanılan yazılımların çoğu değiştirilen dosyaya **kilit** koyar ve başka birisi aynı dosyayı düzenlemek istediğinde

* Kullandığı programa bağlı olarak dosya yazma korumalı olarak salt okunur modda \(readonly\) açılır veya
* Değişiklikler kaydedilmek istendiğinde hata verir

Bu tür bir çalışma hem çok zahmetli hem de hatalara açıktır. Örneğin bir dosyanın en son geçerli versiyonunun nerede olduğunun takip edilmesi gibi çözüm bulunması gereken sorunlar ile uğraşmak zorunda kalırsınız.

> Üzerinde çalıştığınız dosyada sizden önce başkasının değişiklik yapıp yapmadığından haberiniz yoksa hatalı içerik üretme ihtimaliniz vardır.

Versiyon kontrol sistemi kullanıldığında ise ekibinizdeki herkes özgür bir şekilde istediği dosyalar üzerinde güvenli bir şekilde istediği değişikliği yapabilir. Herkes değişikliklerini tamamladıktan sonra da tüm değişiklikler versiyon kontrol sistemi kullanılarak sağlıklı bir şekilde **merge** \(_birleştirme_\) edilebilir.

## Versiyonların düzgün bir şekilde takip edilebilmesi

Üzerinde çalıştığınız bir dosyanın veya bir dizi proje dosyasının zaman içinde farklı versiyonları oluşur ve bu versiyonların kayıt altına alınması gerekir. Bu sorumluluk genelde çok zahmetli ve sıkıcı bir iş ve süreçtir. Aşağıdakine benzer sorular canınızı gereğinden fazla sıkabilir

* Sadece değişen dosyalar mı yoksa bir projedeki tüm dosyaların versiyonları mı kaydedilmeli?

  > * Bir sürü dosya içinden sadece değişen dosyaların belirlenmesi zordur
  > * Her seferinde dosyaların hepsinin teker teker kaydedilmesi durumunda ise ihtiyaç duyulandan daha fazla disk alanı kullanılır

* Dosyalara verilecek isimler tam bir baş ağrısına dönüşebilir.

  > * Personel\_Maas.xlsx
  > * Personel\_Maas1.xlsx
  > * Personel\_Maas\_Ozet.xlsx
  > * Personel\_Maas\_BrutHaricDetay.xlsx
  >
  >   şeklinde dosya isimleri üretmek zorunda kalabilirsiniz.

* Belki de canınızı en çok sıkacak şey projenizin iki versiyonu arasında tam olarak ne tür farkların olduğunu sağlıklı bir şekilde bilme şansınız olmaması olacaktır

Versiyon kontrol sistemi kullandığınızda sizin çalıştığınız disk alanında proje dosyalarının sadece bir versiyonu bulunur, bu dosyaların daha önceki halleri versiyon kontrol sisteminin denetimindedir. Bu sayede istediğiniz zaman önceki versiyonlara geri dönebilir, versiyonlar arasındaki farklılıkları rahatlıkla inceleyebilir ve versiyonları kaydederken eklediğiniz ilave bilgileri ve yorumlarınızı rahatlıkla görebilirsiniz.

## Önceki Versiyonlara Geri Dönebilme

Dosyalarınızın veya aslında tüm projenizin daha önceki versiyonuna geri dönebilme imkanın size ciddi anlamda özgürlük sağlar; dosyalarınızı ve projenizi istediğiniz gibi değiştirme özgürlüğü. Yaptığınız değişiklikler projenizi çöpe döndürdüyse, geliştirdiğiniz bir işlev tam istediğiniz gibi olmadıysa veya müşteriniz veya patronunuz geliştirdiğiniz bir işlevi artık istemediğine karar verirse projenizin önceki temiz haline çok hızlı ve rahat bir şekilde dönebilirsiniz.

## Dosyalarınızın neden değiştiğini anlama

Versiyon kontrol sistemleri değişikliklerinizi tamamlayıp **commit** etmek istediğinizde **comment** adı verilen açıklamalar girmenizi isterler. Bu comment’ler sayesinde projenizin herhangi bir versiyonundaki değişikliklerin nedenlerini de kayıt altına alıp ihtiyaç halinde geri dönüp inceleyebilirsiniz.

> Git'de commit işlemi yapılırken comment \(yorum metni\) girilmesi zorunludur

## Yedekleme

Git gibi dağıtık versiyon kontrol \(DVCS\) sistemlerinin yan etki olarak sağladığı faydalardan birisi de yedeklemedir. Git sayesinde aynı projede çalışan herkesin kendi bilgisayarında projenin tam bir tarihçesi tutulur. Merkezi versiyon kontrol sistemi sunucusunda bir sorun oluştuğunda takımdaki herhangi birinin kendi diskindeki projeyi sunucuya geri yüklemesi yeterlidir. Diğerleri de kendi bilgisayarlarındaki proje dosyalarını geri yüklenen proje dosyaları ile senkronize edebilirler.

