### Git Nedir?
- Git, kısaca yapacağımız işlerin (bireysel proje geliştirmeleri veya ekip içerisindeki projelerin geliştirilmesinde) takibini, yönetilebilirliğini ve bir sorun olması durumunda versiyonlar arası geçiş yaparak kontrol edilmesini sağlayan bir versiyon yönetim aracıdır.

### "git pull" ile "git fetch" komutlarının farkı nedir?
- Aslında her ikiside genel olarak bakıldığında uzak sunucuda var olan güncellemeleri (değişiklikleri) kendi yerel sunucunuza indirir fakat aralarında birkaç farklı yöntem mevcuttur.

- Git fetch, çalışma alanınıza herhangi bir etkide bulunmadan uzak sunucudaki değişiklikleri indirir ve sizin yerel çalışma alanınıza herhangi bir müdahalede bulunmaz.

- Git pull, hem uzak sunucudaki değişiklikleri bilgisayarınıza indirir hem de yerel sunucunuzdaki verileri onlar ile günceller.

### Eğer takım arkadaşımız "kodlarımı gönderdim, benim geliştirmemin üzerine devam et" derse ve gönderdiği kodları "git pull" ile lokalimize alamıyorsak nerelerde hata yapılmış olabilir?

- Arkadaşımızın kesin olarak bu kodları sunucuya doğru bir şekilde gönderebildiğini göz önüne alarak aşağıdaki işlemleri kontrol ederim.

- Bizim öncesinde açmış olduğumuz branchin eskide kalması sonucu branchini göremiyor olabiliriz. Böyle bir durumda kişinin branchine geçiş yapmamız gerekecektir.

- Conflict yemiş olabiliriz. Bu durum genelde localimize çekmeye çalıştığımız kodlar ile var olan kodlarımız arasında bir çakışma sonucu veyahut hali hazırda çalışıyor olduğumuz bir kod mevcutsa ve oradaki değişiklikleri stashlememiş veya geri almadan pull işlemi yapmaya çalıştıysak sorun çıkıyor olacaktır. Böyle bir durumu ise conflict aldığımız kodların problemlerini çözüp olması gerektiği hal ile güncelleyerek çözüme ulaşacağızdır.

### "git fetch origin" komutundaki "origin" neye karşılık gelmektedir?

- Origin, Türkçe'ye köken, orjinal gibi anlamlarla çevrilmiştir. Buradan bile yola çıkarak aslında local sunucumuzun işaret ettiğin ana projeyi temsil etmektedir. Mesela bir projeyi klonladık. Yapacağımız fetch işlemi veya pull işlemi doğrudan tanımlı projeye gider ve oradaki değişiklikleri kendi local sunucumuza getirir.

- Github, Gitlab... gibi ortamlara bir şeyleri pushladığımız zaman aslında git sistemine orayı referans almasını söylüyoruz. Hal böyleyken origin kullanıldığında sunucumuzun işaret ettiği yere göre yeni işlemler yapacaktır.

### "HEAD" kelimesi neyi temsil etmektedir?

- Head, kullanmış olduğumuz branchteki son commiti temsil eder.

### "Staging Area" ya da "Index" diye isimlendirilen bölge tam olarak ne demektir?

- Staging Area, bir tür geçici depolama alanıdır. Takibe aldığımız
değişikliklerimizi tuttuğumuz alandır. Burada değişiklikleri commite dahil etmeden önce inceleyip düzenleyebileceğiniz işlemleri yaparsınız.

### "Untracked file" ne demektir?

- Git tarafından takibe alınmayan dosyalardır. Gerektiği durumda git add komutunu kullanarak stage area tarafına aktararak takibe alınmasını sağlayabiliriz.

### ".git" klasörünü silersek ne olur?

- Git'e dair yapmış olduğumuz tüm değişiklikler ve kayıt altına aldığınız her şey geri dönülmez bir şekilde silinmiş olur.

### Kendi lokalimizde her "git init" komutunu kullanıdığımızda otomatik olarak "ReadMe.md" dosyası oluşturulmasını istiyorsak ne yapmalıyız?

- Ardından, Git'in şablon dizinini belirleyin ve bu dosyaları içine kopyalayın. Örneğin, ~/.git_template gibi bir dizin oluşturabilirsiniz.

- Son olarak, Git'in bu dizini kullanmasını sağlamak için git config komutunu kullanarak bu dizini belirtin

- git config --global init.templateDir ~/.git_template

### Git konusunda bahsi geçen "branch" yapısı nedir? Bize ne sağlar?

- Branchler bizler için main branchi kopyalayan ayrı bir dal oluşturur.

- Bir nevi yol gibi düşünün bu da o yola ek sapa başka bir yol oluşturur fakat her ikiside birbirinin kopyasıdır. 

- Amacımız genelde main branchtekileri değiştirmeden aynı branchi kopyalayarak tüm değişiklikleri orada yapmamızı sağlarız. Ardından her şey yolundaysa bu branchleri birbiri ile birleştiririz.

### Sıfırdan bir "branch" nasıl oluşturabiliriz?

- git checkout -b branch_adı

### Var olan bir "branch"e nasıl geçebiliriz?

- git checkout branch_adı

### "git clone" komutunu kullanırken belirli bir spesifik branch'i sadece çekmek istiyorsak nasıl yapabiliriz?

- git clone -b mybranch <repository_url>

### "Merge conflict" ne demektir?

- "Merge conflict", Git'in birleştirme işlemi sırasında karşılaştığı ve otomatik olarak çözemediği çatışmaları ifade eder. Bu durum, farklı kaynaklardan gelen değişikliklerin aynı dosya veya satırları içermesi ve Git'in hangi değişikliği kullanacağını belirleyememesi durumunda ortaya çıkar.

- İki farklı dalda aynı dosyanın aynı satırlarında yapılan değişiklikler.

- Bir dalda bir dosyanın belirli satırlarının silinmesi ve diğer dalda aynı dosyanın aynı satırlarının değiştirilmesi.

### "git log" komutu ile hangi bilgileri görebiliriz?

- Daha önce atmış olduğumuz commitlerin listesini görebiliriz ve bu listede bulunan id gibi bilgiler ile geriye dönebiliriz veya commitleri resetleyebiliriz.

### "git diff" ile kaç farklı iki durumun arasındaki değişiklikleri görebiliriz?

- Çalışma dizini (working directory) ile Staging Area arasındaki farklar: git diff

- Staging Area ile son commit arasındaki farklar: git diff --staged veya git diff --cached

- İki belirli commit arasındaki farklar: git diff commit1SHA commit2SHA

### Git reset ile neyi geri alıyoruz?

- git reset komutu, bir Git deposundaki son commit işlemini geri almak  için kullanılır. Bu komut, son commit'in yapıldığı commit'i işaret eden HEAD işaretçisini taşıyarak çalışır.

- git reset --soft: Son commit'i geri alır, ancak değişiklikleri çalışma alanınızda ve staging area'da (index) korur. Bu, son commit'inizi değiştirmek istediğinizde veya yanlış bir commit yaptığınızda yararlı olabilir.

- git reset --mixed veya sadece git reset: Bu varsayılan davranıştır. Son commit'i geri alır ve değişiklikleri staging area'da iptal eder. Yani, çalışma dizinizdeki değişiklikler korunur ancak staging area'ya geri alınır. Bu seçenek, bir commit'in içeriğini değiştirmek istediğinizde veya commit'e eklenmemesi gereken dosyaları staging area'dan çıkarmak istediğinizde yararlı olabilir.

- git reset --hard: Son commit'i geri alır ve değişiklikleri tamamen iptal eder. Yani, hem staging area'daki hem de çalışma dizinizdeki değişiklikler silinir. Bu seçenek, son commit'i tamamen geri almak ve tüm değişiklikleri silmek istediğinizde yararlı olabilir.

### "git commit" ile "git push" arasındaki fark nedir?

- git commit komutunu kullandığınızda, değişiklikler sadece yerel depoda saklanır ve henüz uzak depoya gönderilmez.

- git push, yerel çalışma dizetindeki commitleri uzak bir depoya göndermek için kullanılır.

### Atomic commit ne demektir?

- Atomic commit, yapılacak 1 task var fakat içerisinde 10 farklı görev mevcut olarak varsayalım. Bunları teker teker commitleyerek oluşabilecek olumsuz bir durumda yönetilebilirliği arttırmak amaçlı kullanan bir standarttır.

### Repository ne demektir?

- Bir yazılım projesinin tüm dosyalarının ve geçmişinin saklandığı bir yer olarak tanımlanabilir.

### "git tag" nedir? "git branch"’ten farkı nedir?

- git tag komutu, etiketlerin listelenmesi, oluşturulması, silinmesi veya kontrol edilmesi için kullanılabilir.

- git branch, farklı geliştirme hatlarını (branches) temsil eden ve belirli bir commit'in bir parçası olan bir işaretçidir.

### Git'i görsel olarak kullanabilmek için hangi üçüncü taraf araçları ve uygulamaları kullanabiliriz?

- Github Desktop bildiklerim arasındadır.

### "GitHub" ile "git" arasındaki fark nedir? GitHub benzeri diğer siteler nelerdir? GitHub veya diğer sitelerdeki kullanıcı adlarını yazar mısınız?

- Git bir versiyon yönetim aracıyken Github, Gitlab, Bitbucket gibi siteler bir nevi bunları depoladığımız alanlardır.

### main ya da master branch'inin diğer branchlerden farkı nedir?

- Projenin ana orjinal halini temsil eden branchtir.

### ".gitignore" dosyası nedir ve ne amaçla kullanılır?

- Github gibi depolama yapacağımız yerlere ulaşmasını istemediğimiz dosyaları içerisinde ignorelayarak diğer insanların görmemesini sağladığımız dosyaları içeren özel git dosyasıdır.

- Mesela api key, db password gibi özel bilgileri depolamazlar.