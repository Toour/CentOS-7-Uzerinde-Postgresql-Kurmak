# VMware Workstation Üzerinde Postgresql Kurmak
## Sanal Makinenin Kurulumu
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
8. Karşımıza gelen pencere üzerinde "Memory" bölümünde makinenin memory değerini 2 GB olarak ayarlıyoruz. <br><br>
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
11. Daha sonra aşağıdaki "OK" butonuna basarak makinamızı fiziksel olarak kurmuş oluyoruz. Şimdi ise makineyi çalıştırmak ve boot kurulumunu yapmak kalıyor.
12. Öncelikle makineyi çalıştırıyoruz. Karşımıza aşağıdaki gibi bir ekran geliyor. Burada ilk seçeneği ok tuşları ile seçerek enter tuşu ile kurulumu başlatıyoruz.
<p align="center">
  <img src="https://user-images.githubusercontent.com/44029095/121354945-0e49c800-c938-11eb-831b-a9812ca59ed5.png">
</p>
13. 






