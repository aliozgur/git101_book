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

