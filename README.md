# VMware Workstation ile CentOS 7 üzerinde Postgresql Kurmak
## Sanal Makinenin Kurulumu
- Kullanılıcak sanallaştırma ortamı: VMware Workstation 16
- Kurulacak sanal makina: CentOS 7 - 64 bit (minimal)
- Sanal makina üzerinde çalıştırılacak veritabanı: Postgresql 11
- Öncelikle burada vermiş olduğum linke giderek gerekli CentOS ISO dosyasını indirmemiz gerekiyor. Link: [Buradan İndirebilirsiniz...](https://www.centos.org/download/)
- Link sizi çeşitli mirror linklerin olduğu bir siteye yönlendirecek. Burada herhangi bir mirror link'i seçerek indirme işlemini kolaylıkla başlatabilirsiniz. <br>

Ben CentOS Linux 7 x86_64 ISO dosyasını indirmeyi tercih ettim. Yaklaşık olarak 1 GB boyutunda bir dosya. <br>
ISO dosyamız indirilirken o sırada biz makinemiz için gerekli iskeleti oluşturmaya başlayalım: <br>
1. Öncelikle aşağıda da görüldüğü üzere VM Workstation programını çalıştırıp File > New Virtual Machine seçeneğini seçmemiz gerekiyor.
<p align="center">
<img src="https://user-images.githubusercontent.com/44029095/121349966-c2485480-c932-11eb-95f5-d7f7a55d8498.png">
</p>
2. Daha sonra aşağıda görülen bir ekran ile karşı karşıya geleceğiz. Bu durumda 2. seçeneği işaretleyerek şu an inmekte olan ISO dosyamızı, makineye daha sonra aktaracağımızı belirtiyoruz ve "NEXT" tuşuna basıyoruz.<br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121350791-be690200-c933-11eb-992b-bd479108cc26.png">
</p>
3. Karşılaştığımız sayfada işletim sistemini ve seçilen işletim sisteminin hangi sürümünü kullanacağını işaretliyoruz. Eğer CentOS 7 - 64 bit kuracaksınız aşağıda görülen seçenekleri seçmeniz gerekmekte. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121352320-69c68680-c935-11eb-88a9-23d057582cb1.png"> 
</p>
4. Daha sonra sanal makinenizi isimlendirmeniz ve makinenin dosyalarının depolanacağı yeri seçmeniz istenecek. Makineyi isimlendirip lokasyonu default değer olarak bırakabilirsiniz.<br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121352463-911d5380-c935-11eb-88a3-1b7d307c5649.png">
</p>
5. Bir sonraki adımda bizden disk boyutu ve diskin bölümlendirilmesi hakkında seçenek isteyecektir. Disk boyutunu 20GB olan default değer olarak bırakabilir ve alttaki seçeneğe ise hiç dokunmadan bir sonraki adıma geçiş yapabilirsiniz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121352982-0e48c880-c936-11eb-9f1d-161eba01ac92.png">
</p>
6. Sonraki sayfada sanal makinamızın genel özellikleri görülmektedir. "Finish" seçeneğini seçerek makinamızın iskeletinin kurulumunu tamamlıyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121353214-4819cf00-c936-11eb-95ec-745a1bce8f10.png">
</p>
7. Daha sonra aşağıda görüldüğü üzere kurmuş olduğumuz makinemizin üzerine sağ tıklayarak "settings" seçeneğine tıklıyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121353578-af378380-c936-11eb-9a83-fa2d0a0546cb.png">
</p>
8. Karşımıza gelen pencere üzerinde "Memory" bölümünde makinenin memory değerini 2 GB olarak ayarlıyoruz. (Eğer minimal kurulum ise 1 GB olarak da bırakılabilir.) <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121353842-fa519680-c936-11eb-9743-c9d8ef8d9ba6.png">
</p>
9. "Memory" bölümünün hemen altında bulunan "Processors" bölümüne geçip işlemicimizi 2'ye ayarlıyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121354013-24a35400-c937-11eb-8022-208ee3f0e968.png">
</p>
10. "CD/DVD" bölümüne giderek aşağıda görülen seçenekleri seçiyoruz. "Connect at power on" seçeneğinin seçili olması gerekmektedir. Connection kısmı için ise "Use ISO image file" seçeneğini seçerek "Browse" tuşu ile indirmiş olduğumuz ISO dosyamızı seçiyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121354564-a98e6d80-c937-11eb-82ed-1c019bf93a87.png">
</p>
11. Daha sonra aşağıdaki "OK" butonuna basarak makinamızı fiziksel olarak kurmuş oluyoruz. Şimdi ise makineyi çalıştırmak ve boot kurulumunu yapmak kalıyor. <br>
12. Öncelikle makineyi çalıştırıyoruz. Karşımıza aşağıdaki gibi bir ekran geliyor. Burada ilk seçeneği ok tuşları ile seçerek enter tuşu ile kurulumu başlatıyoruz.<br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121354945-0e49c800-c938-11eb-831b-a9812ca59ed5.png">
</p>
13. Enter'a bastıktan sonra birkaç saniye sonrasında aşağıdaki ekran ile karşılaşıyoruz. İstediğimiz dili seçerek devam et seçeneğine tıklıyoruz. (Türkçe dili de mevcut.) <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121355261-5ff25280-c938-11eb-9110-e4ca60a34505.png">
</p>
14. Kurulum özeti ekranı ile karşılaşıyoruz. Bu ekranda ikaz ifadesinin görüntülendiği seçenek olan "Installiation Destination" seçeneğine tıklıyoruz. Bende bu seçenek yok demeyin, scroll down yaparak bulabilirsiniz :) <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121355661-c4adad00-c938-11eb-87f3-be0d52d02cf2.png">
</p>
15. Daha önce belirlemiş olduğumuz 20GB'lık diski işaretleyerek sol-yukarıda bulunan "Done" butonuna tıklıyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121355899-09394880-c939-11eb-90e1-4c5c90a914dc.png">
</p>
16. Daha sonra Software alanı altında yer alan "Software Selection" seçeneğine tıklıyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121356187-4d2c4d80-c939-11eb-853d-41875cadffd0.png">
</p>
17. Bu başlık altında GUI kurmak ve sanal makinenizi uzaktan görüntülemek gibi seçenekler bulunmakta. Aşağıdaki seçenekleri seçerek "Done" butonuna basabilirsiniz. Eğer ISO dosyanızı minimal olarak indirmiş iseniz bu seçenekleri göremezsiniz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121356665-bb711000-c939-11eb-9271-63971bbfaaf6.png">
</p>
18. Gerekli seçenekleri seçmiş bulunmaktayız. Artık ana menüden "Begin Installiation" seçeneğini seçerek makinenin kurulumunu tamamlayabiliriz. Fakat bu butona bastıktan sonra makine bizlerden bir şifre ve kullanıcı oluşturmamızı isteyecektir. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121356961-0d199a80-c93a-11eb-855a-ca4541a40ae8.png">
</p>
19. Bir root şifresi ve bir kullanıcı oluştururken arkaplanda zaten makine kurulmaya başlanmış oluyor. Artık sadece beklememiz gerekiyor. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121357409-77323f80-c93a-11eb-938e-3908e8bf267e.png">
</p>
20. Gerekli kurulum tamamlandığında, aşağıda görüldüğü gibi makinemiz bizden kendisini reboot etmemizi istiyor. Makineyi reboot ederek artık kullanıma hazır hale getirmiş oluyoruz. <br><br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121357680-a943a180-c93a-11eb-949b-f83ba14526e3.png">
</p>

## Postgresql Kurulumu
### Postgresql'in indirilmesi
- Şimdi sanal makine üzerinde postgresql kurulumu gerçekleştirilecektir. <br>
- İlk olarak makineyi uzaktan kontrol etmek için "Putty" adlı uygulamayı indirmemiz gerekiyor. Buradan indirebilirsiniz: [putty.org](https://www.putty.org/) <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121468152-0125eb00-c9c3-11eb-9940-ee77eae6c1f4.png">
</p>

- Minimal kurulu olduğu için terminal ile karşı karşıya kalınır. Çalışır durumda olan makineye giriş yapılır. <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121468871-2c5d0a00-c9c4-11eb-9781-d68cd9126baf.png">
</p>

- "ip addr show" komutu ile makinenin IP adresi öğrenilir. <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121468963-58788b00-c9c4-11eb-8819-76be22a1037e.png">
</p>

- Eğer IP adresi gözükmüyor ise telaşa gerek yok. "dhclient ens33" komutu ile makinenin ağ üzerinde bir IP kazanması sağlanılır. Dikkat edilmesi gereken şey ise bu işlemin yönetici izni gerektirmesidir. Yani komutun başına "sudo" ekleyerek yazılması gerekmektedir.
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121469291-ec4a5700-c9c4-11eb-83c5-cd20b4d3506d.png">
</p>

- Putty uygulaması açılır ve aşağıdaki ekran ile karşılaşılır. <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121469545-5b27b000-c9c5-11eb-8d5e-27b443effb6e.png">
</p>

- Putty uygulaması üzerinden makinenin IP adresi aşağıda gösterilen yere girilir ve SSH bağlantısı seçilerek bağlantı kurulur. <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121469853-e5701400-c9c5-11eb-8ab4-3d1cb45eb497.png">
</p>

- Putty bağlantısı kurulunca aşağıdaki ekran ile karşılaşılır. İstenilen kullanıcı ile oturum açılabilir. Burada "root" kullanıcısı ile daha önce CentOS'un kurulumunda belirlenmiş root şifresi sayesinde oturum açılır: <br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121470119-5f080200-c9c6-11eb-80a5-1f87fb81f584.png">
</p>

- Daha sonra <br>
~~~
sudo vi /etc/yum.repos.d/CentOS-Base.repo
~~~

komutu çalıştırılır <br>
Komutun anlamı: makinenin Base Repository bölümünü "Vi" editörü ile editle.<br>
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121470459-ee151a00-c9c6-11eb-960f-b846c5edb976.png">
</p>

- Burada [base] ve [updates] başlıkları altına <br>
~~~
exclude=postgresql*
~~~

ifadesi yazılır. <br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121472074-59f88200-c9c9-11eb-9100-bfc4fb93d290.png">
</p>


":" işaretine basılarak "wq" ifadesi girilip Enter tuşuna basılır.<br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121472175-7d233180-c9c9-11eb-9266-310e7ad1c828.png">
</p>

":wq" ifadesinin anlamı, w=write, q=quit şeklinde olup "dosyanın üstüne yaz ve dosyadan çık" şeklindedir.<br> 
Daha sonra CentOS üzerinde çalışacak Postgresql için gerekli paket indirilmesi gerçekleştirilir. <br>
Paketi indirmek için aşağıdaki komut çalıştırılır: <br>
~~~
sudo yum install https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm <br>
~~~

Ekran görüntüsü: <br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121472335-b8bdfb80-c9c9-11eb-81a5-2c8d211e0543.png">
</p>

Aşağıdaki komut kullanılarak kullanılabilir tüm paketler ve versiyonları görüntülenebilir. Burada paketlerin hepsi "y" yazarak yüklenebilir.<br>
~~~
yum list postgresql*
~~~
Ekran Görüntüsü: <br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121473615-9f1db380-c9cb-11eb-857d-23969670ded8.png">
</p>

Daha sonra Postgresql server'ı kurmak için aşağıdaki komut çalıştırılır: <br>
~~~
sudo yum install postgresql11-server
~~~
Komut çalışırken arada gelecek olan seçeneklere "y" yazarak devam edilir. <br>
Ekran Görüntüsü: <br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121475093-a940b180-c9cd-11eb-8bb2-2b52e2b3f9b2.png">
</p>

Her şey tamamlandıktan sonra aşağıdaki görüntü ile karşılaşılır. <br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121475560-3dab1400-c9ce-11eb-8b84-d6a918831729.png">
</p>

Böylelikle server'ın yazılımsal kısmı yüklenmiş olmaktadır. Şimdi ise Postgresql için yeni bir veritabanı cluster'ı oluşturma zamanı. <br>
Veritabanı kullanılmadan önce bir cluster oluşturulması gerekmektedir. Cluster, tek bir server örneği tarafından yönetilen veritabanı koleksiyonuna verilen addır. <br>
Aşağıdaki komut çalıştırılarak Postgresql veritabanı cluster'ı oluşturulur: <br>
~~~
sudo /usr/pgsql-11/bin/postgresql-11-setup initdb
~~~
Ekran Görüntüsü:
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121476661-9e871c00-c9cf-11eb-941b-067342bfd9e0.png">
</p>

Sırada Postgresql'in başlatılması ve aktif hale getirilmesi var. Aşağıdaki komutlar sırayla çalıştırılarak bu iş yapılır: <br>
~~~
sudo systemctl start postgresql-11
sudo systemctl enable postgresql-11
~~~
Ekran Görüntüsü: <br>
<p align="center">
 <img src="https://user-images.githubusercontent.com/44029095/121477047-05a4d080-c9d0-11eb-892d-ced87852a5c7.png">
</p>



