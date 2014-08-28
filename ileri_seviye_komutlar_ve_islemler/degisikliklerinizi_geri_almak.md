# Değişikliklerinizi Geri Almak

Git'in en güzel yanlarından biri de yaptığınız herhangi bir değişikliği kolayca geri alabilmemızı ağlamasıdır.

## Son Commit Bilgilerini Düzeltmek

Commit işlemlerinizi ne kadar dikkatli yaparsanız yapın bazen commit'e dahil etmeyi unuttuğunuz veya yanlışlıkla dahil ettiğiniz dosyalar olabilir veya commit mesajında eksik bilgi vermiş olabilirsiniz. Bu durumda son commit işleminizi yeniden yapmak için **git commit** komutunu **--amend** seçeneği ile kullanabilirsiniz. Sadece commit mesajınızı değiştirmek istiyorsanız **-- amend -m** seçenekleri ile git commit komutunu çalıştırabilirsiniz, eğer son commit'e dosya eklemek veya dosya çıkarmak isterseniz commit komutundan önce önceki bölümlerde de bahsettiğimiz **git add** ve **git rm** komutları ile önce Staging işlemini yapabilirsiniz.

<div style="padding:10px;border:1px solid #fcedd7;background-color:#fef9f1">
<p style="color:darkgray">Versyon Kontrolünün Altın Kuralları</p>
<p style="font-weight:bold">#5 Adsla Yayınlanmış Commitlerinizi Düzeltip Tekrar Yayınlamayın </p>
<p>
**git commit** komutunun --amend seçeneği commit hatalarımızı hızlıca ve kolayca düzeltebilmemiz için oldukça faydalı bir seçenektir. Ancak bu seçeneği kullanmadan önce aşağıdaki noktaları dikkate almalısınız
* Bu seçenek sadece son commit işlemimizi düzeltmemizi sağlar, önceki commitlerimizi bu seçenek ile düzeltemeyiz.
* Bu seçenek ile commit işlemi sonrasında bir önceki commit işlemine dair bilgiler silinir. Proje üzerinde çalışan tek kişi iseniz bu seçeneği kullanmanız sorun yaratmayacaktır ancak bir takım içinde yer alıyorsanız diğer takım arkadaşlarınız sonradan --amend ile düzeltttiğiniz hatalı commit işleminizi baz alarak kendileri de değişiklikler yapmış olabilirler. Bu durum takım arkadaşlarınız için sorun oluşturacaktır, çünkü onların baz aldıkları commit ile ilgili Git'de artık herhangi bir kayıt yer almaycak.
</p>
</div>

## Local Değişiklikleri Geri Almak

Henüz commit etmediğimiz değişiklikliklere Local değişiklik denir. Bazen önceki halinden daha kötü olan kod yazabilirsiniz ve bu değişikliği geri almak isteyebilirsiniz. Bu gibi durumlarda değiştirdiğiniz halinden memnun olmadığınız dosyadaki değişiklikleri geri alıp dosyanın son commit edilmiş haline geri dönmek istediğinizde, önceki bölümlerde de sıkca kullandığımız, **fit checkout** komutunu **--** seçeneği ile çalıştırmanız yeterli olacaktır.

>* **$ git checkout -- dosya1.md** veya
>* **$ git checkout -- klasor/dosya2.md**
> şeklinde kullanabilirsiniz.

Tüm dosyalarda yaptığınız değişiklikleri geri almak istiyorsanız **git reset** komutunu **--hard** seçeneği ile kullanabilirsiniz

> **$ git reset --hard HEAD**

Bu komut ile Git tüm dosyaların son commit edilen değişiklikleri içeren HEAD versiyonundaki hallerinin Working Copy'nize geri yükler.

> **git checkout --** ve **git reset --hard** komutları sonrasında kayıt altına alınmamış olan tüm değişiklikler geri dönüşü olmayacak şekilde yok olur. Bu nedenle bu komutları çalıştırırken dikkatli olmalısınız ve iki defa düşünmelisiniz.

## Commit Edilen Değişiklikleri Geri Almak

