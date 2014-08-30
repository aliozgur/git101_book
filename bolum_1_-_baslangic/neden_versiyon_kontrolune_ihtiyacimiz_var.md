# Versiyon Kontrolüne Neden İhtiyacımız Var?
Versiyon kontrol sistemi kullanmanın bir çok faydası var ve bu bölümde versiyon kontrol sistemi kullanımının bize sağladığı avantajlardan bahsediyoruz.

## Uyumlu ekip çalışması
Herhangi bir versiyon kontrol sistemi kullanmadığınızda  beraber çalıştığını diğer kişiler ile aynı dosyalar üzerinde değişiklik yapabilmek için muhtemelen herkesin erişimine açık paylaşımlı bir klasör kullanmak zorunda kalacaksınız.

Bu tür bir senaryoda kullanılan yazılımların çoğu değiştirilen dosyaya **kilit** koyar ve başka bir kişi aynı dosyayı düzenlemek istediğinde
* Kullandığı programa bağlı olarak dosya yazma korumalı olarak salt okunur modda (readonly) açılır veya
* Değişiklikler kaydeidlmek istendiğinde hata verir

Bu tür bir çalışma hem çok zahmetli hem de hatalara açıktır. Örneğin bir dosyanın en son geçerli versiyonunun nerede olduğunun takip edilebilmesi gibi çözüm bulunması gereken sorunlar ile uğraşmak zorunda kalırsınız.

> Üzerinde çalışmaya başladığınız dosyada sizden önce başka birisini değişiklik yapıp yapmadığından haberiniz yoksa hatalı içerik üretme ihtimaliniz vardır.

Versiyon kontrol sistemi kullanıldığında ise ekibinizdeki herkes özgür bir şekilde istediği dosyalar üzerinde güvenli bir şekilde istediği değişikliği yapabilir. Herkes değişikliklerini tamamladıktan sonra da tüm değişiklikler versiyon kontrol sistemi kullanılarak sağlıklı bir şekilde **merge** (*birleştirme*) edilebilir.

## Versiyonların düzgün bir şekilde takip edilebilmesi

Üzerinde çalıştığınız bir dosyanın veya bir dizi proje dosyasının zaman içinde farklı versiyonları oluşur ve bu versiyonların hepsinin kayıt altına alınması gerekir. Bu sorumluluk genelde çok zahmetli ve sıkıcı bir iş halini alır. Örneğin aşağıdaki sorular canınızı gereğinden fazla sıkabilir

* Sadece değişen dosyaların mı yoksa bir projedeki tüm dosyaların versiyonlarını mı kaydetmeliyim?
> * Bir sürü dosya içinden sadece değişen dosyaların belirlenmesi zordur
> * Tüm dosyaların kaydedilmesi durumunda ise ihtiyaç duyulandan daha fazla disk alanı kullanırsınız

* Dosyalara verilecek isimler tam bir baş ağırısına dönüşebilir.
> * Personel_Maas.xlsx
> * Personel_Maas1.xlsx
> * Personel_Maas_Ozet.xlsx
> * Personel_Maas_BrutHaricDetay.xlsx
> şeklinde dosya isimleri üretmek zorunda kalabilirsiniz.

* Belki de canınızı en çok sıkacak şey projenizin iki versiyonu arasında tam olarak ne tür farkların olduğunu sağlıklı bir şekilde bilme şansınız olmaması olacaktır

Versiyon kotrol sistemi kullandığınızda sizin çalıştığınız disk alanında proje dosyalarının sadece bir versiyonu bulunur, bu dosyaların daha önceki halleri versiyon kontrol sistemin denetimindedir.Bu sayede istediğiniz zaman önceki versiyonlara geri dönebilir, versiyonlar arasındaki farklılıkları rahatlıkla inceleyebilir ve versiyonları kaydederken eklediğiniz ilave bilgileri ve yorumlarınızı rahatlıkla görebilirsiniz.

## Önceki Versiyonlara Geri Dönebilme
Dosyalarınızın veya aslında tüm projenizin daha önceki versiyonuna geri dönebilme imkanın size ciddi anlamda özgürlük sağlar; dosyalarınızı ve projenizi istediğiniz gibi değiştirme özgürlüğü. Yaptığınız değişiklikler projenizi çöpe döndürdüyse, geliştirdiğiniz bir işlev tam istediğiniz gibi olmadıysa veya müşteriniz veya patronunuz geliştirdiğiniz bir işlevi artık istemediğine karar verirse projenizin önceki temiz aline çok hızlı ve rahat bir şekilde dönebilirsiniz.

## Dosyalarınızın neden değiştiğini anlama
Versiyon kontrol sistemleri değişikliklerinizi versiyon kontrolüne almak için kaydettiğiniz anda **comment** adı verilen açıklamalar girmenizi isterler. Bu commentler sayesinde projenizin herhangi bir versiyonundaki değişikliklerin nedenlerini de kayıt altına alıp ihtiyaç halinde daha sonra görebilirsiniz.

> Git'de commit işlemi yapılırken comment (yorum metni) girilmesi zorunludur

## Yedekleme
Git gibi dağıtık versiyon kontrol (DVCS) sistemlerinin yan etki olarak sağladıkları imkanlardan birisi de yedeklemedir. Git gibi sistemler sayesinde aynı proje üzerinde çalışan herkesin kendi bilgisayarlarında tam bir tarihçesi tutulur. Merkezi versiyon kontrol sistemi sunucusunda bir sorun olması durumunda takımdaki herhangi birinin kendi diskindeki proje'yi sunucuya geri yüklemesi yeterlidir. Diğerleri de kendi bilgisayarlarındaki proje dosylarını yeni yüklenen proje dosyaları ile senkronize edebilirler.
