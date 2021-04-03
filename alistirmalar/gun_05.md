---
description: Ali Özgür
---

# 5.Gün: Değişiklikleri Versiyon Kontrolüne Alma

Git'in temel yaklaşımlarından birisi de değişikliklerinizin versiyon kontrolü altına alınmaya hazır olduğuna karar verene kadar Git ile herhangi bir etkileşime geçmenize gerek olmamasıdır. Staging Area denilen ara bir alanın varlığı da bu yaklaşım ile uyumludur; birden fazla dosyanızı değiştirip mantıksal olarak anlamlı bütünler halinde Staging Area'da yer almasını sağlayıp daha sonra da bu değişiklikleri yeni versiyon \(commit\) olarak mühürleyebilirsiniz

Örneğin a.txt, b.txt ve c.txt isimli üç dosyada değişiklik yaptığınızı düşünelim. Bu değişikliklerden a.txt ve b.txt dosyalarındakilerinin birbiri ile ilişkili olduğunu, c.txt dosyasındaki değişikliğin ise kendi başına anlamlı olduğunu düşünelim. Aşağıdaki Git komutları ile değişikliklerimizi iki commit oluşturacak şekilde mantıksal olarak gruplayabilirsiniz.

```bash
git add a.txt

git add b.txt

git commit -m "a ve b dosyalarında değişiklik yapıldı"

git add c.txt

git commit -m "c dosyasında değişiklik yapıldı"
```

Dosyalarınızda yaptığınız değişikliklerin versiyonlanması için önce Staging Area'ya eklenmesi daha sonra da git commit ile tüm değişikliklerinizin yeni bir versiyon olarak mühürlenerek Git tarafından kayıt altına alınmasını sağlamalısınız. Bu döngü tüm değişiklikler için geçerli olan edit/stage/commit döngüsü olarak anılır.

## Alıştırma - 1

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Boş bir dosya oluşturun
touch <dosya_adı>.txt

# Dosyayı Staging Area’ya ekleyin
git add <dosya_adı>.txt

# Değişikliklerinizi commit edin
git commit -m "<dosya_adı> isimli dosyayı ekledim"
```

**Soru-1:** git commit komutunu -m parametresi kullanmadan çalıştırırsanız ne olur?

**Soru-2:** Commit tarihçenizdeki commit mesajlarını tek satır halinde görmek için hangi komutu çalıştırmalısınız?

## Alıştırma - 2

Git'in commit mesajları ve diğer metin düzenleme işlemler için varsayılan metin editör uygulaması olarak Windows üzerinde Notepad++, OSX üzerinde Sublime Text, Linux üzerinde de gEdit veya kendi tercih ettiğiniz bir metin editörü kullanabilmesi için gerekli Git ayarlarını yapın

## Alıştırma - 3

Git’in her bir commit işlemi için otomatik ürettiği hash değerinin ne olduğunu araştırın.

[&lt;&lt; Geri](gun_04.md) \| [İleri &gt;&gt;](gun_06.md)

