## Soru 1: Git Nedir?

Git bir versiyon kontrol sistemidir. Yaptığımız çalışmalara kontrol noktaları koyabildiğimiz daha sonrasında bu kontrol noktalarını inceleyip ihtiyaç halinde geri dönebildiğimiz bir sistemdir. Her bir kontrol noktasında (commit) dosyalarımızdaki değişiklikleri gözlemlememize olanak sağlar.

## Soru 2: "git pull" ile "git fetch" komutlarının farkı nedir?

"git fetch" yaptıktan sonra local branc'lerimiz güncellemelerini alır fakat "git merge" yapmadan bu değişiklikler working directory'e işlenmez. "git pull" ise hem "git fetch" yapar hem de "git merge" yapar. Yani remote repository'den güncellemeleri local repository'e alıp bunları working directory'e işler.

## Soru 3: Eğer takım arkadaşımız "kodlarımı gönderdim, benim geliştirmemin üzerine devam et" derse ve gönderdiği kodları "git pull" ile lokalimize alamıyorsak nerelerde hata yapılmış olabilir?

Kod gönderilmiş olabilir ama nereye? Kodumuzun yolculuğu ilk yazmaya başladığımız andan itibaren şu şekilde oluyor: İlk başta "git add" komutu ile kodumuzu staging area'ya alıyoruz. Ardından staging area'daki kodu local repository'e eklemek için "git commit" komutunu kullanıyoruz. En sonunda local repository'de bulunan kodlarımızı remote repository'e aktarmak için "git push" komutunu kullanıyoruz. Bu aşamaların hepsi incelenip hangi aşamada eksik olduğu bulunmalıdır.
