# Neden Versiyon Kontrolüne İhtiyacımız Var?
Versiyon kontrol sistemi kullanmanın bir çok faydası vardır. Bu bölümde versiyon kontrol sistemlerinin sağladığı avantajlardan bazılarını ele alıyoruz.

## Ahenkli ekip çalışması
Herhangi bir versiyon kontrol sistemi kullanmadığınızda  ekibinizdeki diğer kişiler ile aynı dosyalar üzerinde çalışabilmek için muhtemelen herkesin erişimine açık paylaşımlı bir klasör kullanmak zorunda kalacaksınız.

Bu tür bir senaryoda kullanılan yazılımların çoğu A kullanıcısının açıp düzenlemeye başladığı dosyaya **kilit** koyar ve başka bir kişi aynı dosyayı düzenlemek istediğinde
* Kullandığı programa bağlı olarak dosya yazma korumalı okuma modunda açılır veya
* Düzenlemeler kaydetmek istenildiğinde hata verir veya
* Düzenlemeleri kaydetmek için diğer kişiden dosyayı kapatmasını istemek zorundadır

Bu tür bir çalışma hem çok zahmetli hem de hatalara açıktır. Herhangi bir dosyanın en gücel halinin nerde bulunduğunun haricen takip edilmesi gerekliliği gibi manuel işlemlerin yapılması zorunluluğu ortaya çıkar (aslında çoğu zaman insanlar bir dosyanın en son halinin nerde olduğunu birbirlerine sorarak keşfetmeyi tercih ederler)

> Örneğin; A kişisinin düzenlediği dosyada kendinden önce başka birisini değişiklik yapıp yapmadığından haberi olmaz. Bu durum A'nın ürettiği içeriğin yanlış/hatalı olmasına sebep olabilir.

Versiyon kontrol sistemi kullanıldığında ise ekibinizdeki herkes özgür bir şekilde istediği dosyalar üzerinde güvenli bir şekilde istediği değişikliği yapabilir. Daha sonrasında herkes değişikliklerini tamamladıktan sonra tüm değişiklikler versiyon kontrol sistrmi kullanılarak sağlıklı bir şekilde **merge** (*birleştirme*) edilebilir. Herhangi bir dosyanın

## Versiyonların düzgün bir şekilde takip edilebilmesi

Üzerinde çalıştığınız bir dosyanı veya bir dizi proje dosyasnın versiyonlarının kaydedilmesi kaçınılmazdır. Bu sorumluluk çoğu zaman çok zahmetli ve sıkıcı bir iş halini alır. Örneğin aşağıdaki sorular canınızı gereğinden fazla sıkabilir

* Sadece değişen dosyalar mı yoksa bir projedeki tüm dosyaların versiyonlarını mı kaydetmeliyiz?
> * Sadece değişen dosyaların belirlenmesi zor olablir
> * Tüm dosyaların kaydedilmesi durumunda ise ihtiyaç duyulandan daha fazla disk kapasitesi kullanacaksınız

* Dosyaların isimlendirmesi tam bir baş ağırısına dönüşebilir.
> * Personel_Maas.xlsx
> * Personel_Maas1.xlsx
> * Personel_Maas_Ozet.xlsx
> * Personel_Maas_BrutHaricDetay.xlsx
> şeklinde dosya isimleri üretmek zorunda kalabilirsiniz.

* Belki de canınızı en çok sıkacak konu projenizin iki versiyonu arasında tam olarak ne tür farkların olduğunu sağlıklı bir şekilde bilme şansınız olmaması olacaktır

Versiyon kotrol sistemi kullandığınızda sizin çalıştığınız disk alanındaproje dosyalarının sadece bir hali yer alır, bu dosyaların daha önceki halleri versiyon kontrol sistemin denetimindedir.Bu sayede istediğiniz zaman önceki versiyonlara geri dönebilir, versiyonlar arasındaki farklılıkları rahatlıkla inceleyebilirve versiyonları kaydederken eklediğiniz yorumlarınızı rahatlıkla görüntüleyebilirsiniz.

## Önceki Versiyonlara Geri Dönebilme
Dosyalarınızın veya aslında tüm projenizin daha önceki hallerine (versiyon) geri dönebilme imkanın size çok çok önemli bir özgürlük sağlar; dosyalarınızı ve projenizi istediğiniz gibi kurcalama özgürlüğü. Yaptığınız değişiklikler projenizi çöpe döndürdüyse, geliştirdiğiniz bir işlev tam istediğiniz gibi olmadıysa veya müşteriniz veya patronunuz geliştirdiğiniz bir işlevi artık istemediğine karar verirse projenizin önceki temiz aline çok hızlı ve rahat bir şekilde dönebilirsiniz.

## Dosyalarınızın neden değiştiğini anlama
Versiyon kontrol sistemleri değiştirdiğiniz dosyaların versiyonlarını oluşturduğunuz sırada sizden yaptığınız değişiklikler ile ilgili **comment** adı verilen açıklamalar girmenizi isterler. Bu commentler sayesinde projenizin herhangi bir versiyonundaki değişikliklerin sebebini de görebilirsiniz.

> Git de commit sırasında comment girilmesi zorunludur

## Yedekleme
Git gibi dağıtık versiyon kontrol (DVCS) sistemlerinin yan etki olarak sağladıkları imkanlardan birisi de yedeklemedir. Git gibi sistemler sayesinde aynı proje üzerinde çalışan bir ekipteki herkesin kendi diskleri üzerinde projenin tam bir tarihçesi tutulur. Merkezi versiyon kontrol sistemi sunucusunda bir sorun olması durumunda ekip üyelerinden herhangi birinin kendi diskindeki proje'yi sunucuya rahatlıkla geri yükleyebilir, diğer ekip üyelerinin disklerindeki proje dosylarının yeni yüklenen proje dosyaları ile senkronize edilmesi sağlanabilir.
