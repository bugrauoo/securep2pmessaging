# ayşe-tatile-çıksın

## Tanım

Uçtan uca şifrelemeli, P2P bağlantı sağlanan mesajlaşma programı.

## Ne hedefledik?

Projemizi aslında ders projesi olarak yaptık. Projemizin konusunu projeyi yaptığımız 
tarihte olan belli başlı veri sızıntıları ve insanların mesajlaşma uygulamalarına 
karşı "dinleniyor muyuz?" diye sorgulaması üzerine seçtik. 

Amacımız programı kullanırken P2P bağlantı sağlayıp, uçtan uca asimetrik şifrelenmiş mesajların 
iletimi idi.  

## Ne yaptık?

**P2P için bir sorun çıktı karşımıza: NAT**. Ekipten hiçbirimizin internete doğrudan çıkabildiği bir IPv4 
adresi yoktu. Tek de değil, birkaç ayrı NAT sonrasında internete çıktığımız ve IP:PORT bağlantısını 
direkt olarak yapamayacağımızdan ötürü "Rendezvous" yani randevu protokolü kullandık. Burada sunucuyu 
mesaj iletiminde aktif kılmak istemediğimizden böyle bir tercih yaptık. Mesaj iletiminde arada olmaması 
bizim için bir hedefti, gerçekleyebildik.

**Şifreleme: yaptık**. Burası planlandığı gibi gitti, maharetli eller sağ olsun. 
Program başlangıçta oluşturduğu anahtarlardan açık anahtarları karşıya program ilk mesaj olarak iletiyor. Açık anahtarlar alındıktan 
sonra mesajlaşmayı başlatıyoruz. Ekstra olarak, şifreleme kısmında "Side-channel attack"a karşı da önlem aldık.

Ayrıca görüldüğü şekilde, Python ile yazdık. 

## Ne yap(a)madık?

**Arayüz: eksik kaldı.** Zamanın azı buraya kaldı, pek ilgilenemedik. Projenin sunumu için yetecek kadar yaptık.

NOT: Anahtarlarla alakalı txt'lerin ilk içeriği önemli değil, program icra edilirken onları zaten yoksa oluşturacak, 
varsa içeriğini okumadan değiştirecek.

## Ne yapabilirdik?

+Bağlantı yöntemlerini geliştirebilirdik.
+NAT arkasında olmayanlar için direkt P2P bağlanabilecekleri seçenek ekleyebilirdik.
+Randevu noktası darboğaza çok müsait, farklı bir şekilde kodlayabilirdik.
...
gibi bir çok fikir, tek ders için ayrılabilecek görece kısa bir süre vardı.