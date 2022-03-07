---
layout: post
title: "Gnome Masaüstü 4K Deneyimi"
date: 2022-02-11 13:32:20 +0300
description: Gnome masaüstü arayüzünü 4K bir ekranda kendi kullanımım için nasıl özelleştirdim - 1
tags: linux gnome customization hidpi tweaks
img:  /assets/img/gnome.png
---
Gnome çok başarılı bir özgür masaüstü ortamı olsa da varsayılan olarak ne yazık ki yüksek çözünürlüklü (HiDPI) ekranlar için güzel bir deneyim sunamıyor. 
Bunu daha da genişleterek diğer özgür masaüstü ortamları için de söylemek mümkün ancak özellikle tile-based masaüstü ortamlarını kendim çok deneyimlemediğim 
için onları yine de bahis dışı bırakmak istiyorum. Öncelikle kendim ayarlar için kullandığım sistemden bahsedeyim: 

- LG 27" 27UD58-B 4K IPS monitör
- AMD CPU ve Ekran Kartı
- Ubuntu 21.10
- Gnome 40.5

Ubuntu 21.10 kurulum bittikten sonra 4K ekranda varsayılan olarak güzel bir görüntü karşılamıyor bizleri. Sistem herhangi bir karar vermiyor ve tüm arayüzü 
3840x2160 ortamda 1e1 çiziyor. Bu nedenle de ekranda tüm öğeleri oldukça küçük görünüyor. Bu şekilde ekran alanı oldukça geniş ve bu şekilde de kullanmayı 
tercih edenler olabilir. İşletim sistemleri HiDPI ekranlarda arayüzlerini genelde scale ederek ekrana çizmek konusunda opsiyon sunuyorlar. Linux dağıtımlarında 
ve özgür masaüstü ortamlarında da bu opsiyonlar var ancak ortamdan ortama ve dağıtımdan dağıtıma farklılıklar mevcut.  

Bu yazı daha çok arayüz özelleştirmeyle ilgili olacak bu yüzden scale konusuna çok girmeyeceğim. Kısaca söylemek gerekirse örneğin gnome için scale değerleri 
"sorunsuz" olarak 1x, 2x, 3x ve 4x olarak geliyor. 2x kullandığımızda 3840x2160 olan çözünürlüğümüz 1920x1080 gibi davranacak, 1080P bir hareket alanımız olacak
ancak ekranda çizilen her şey için daha fazla piksel kullanıldığı için görüntümüz daha keskin olacak. Bu, çoğu için tercih edilen seçenek olabilir. Ama benim
gibi biraz keskinlik biraz kullanım alanı olsun diyenler için fractional scale opsiyonları mevcut. Yine gnome için fractional scaling varsayılan olarak kapalı
gelmekte ve performans sorunlarına yol açabileceği uyarısıyla birlikte sunulmakta. O yüzden bunu da tercih etmiyorum.  

KDE masaüstü ortamı için de kullandığım Gnome için de uyguladığım yöntem ise font scaling. KDE'de bu Font DPI olarak kendi ayarlarından düzenlenebiliyor. 
Gnome için ise gnome-tweaks uygulamasını kurmamız gerekiyor. Sadece font scale ayarı için değil tüm özelleştirmeler için kullanacağımız bir araç. Alsında terminal 
üzerinde bulunan gsettings komutlarının çoğu için arayüz sunan bir program yani burada yaptığımız çok şeyi terminalden de yapabiliriz ama o kadar zahmete 
girmeye gerek yok doğrusu. Gnome Tweaks, Ubuntu 21.10 için universe repository aktif olduğu sürece doğrudan apt ile kurulabiliyor: 

```bash
sudo add-apt-repository universe
sudo apt install gnome-tweaks
```
Gnome Tweaks kurulduktan sonra uygulamada Fonts altında şu ayarları yapıyorum. (Font seçimi konusunda ayrı bir yazı yazmayı planlıyorum):

- Interface Text: sevdiğiniz bir font mevcut ubuntu fontu da kalabilir (12px)
- Document Text: sevdiğiniz bir font mevcut ubuntu fontu da kalabilir (11px) 
- Monospace Text: sevdiğiniz bir font mevcut font da kalabilir ama mono yani her harfin yatayda kapladığı piksel alanı aynı olmalı ki özellikle kod yazarken okunabilirliği kaybetmeyelim (12px) 
- Legacy Window Titles: sevdiğiniz bir font mevcut ubuntu fontu da kalabilir ama bold yerine semibold bir seçim öneririm (12px) 
- Hinting: Slight
- Antialiasing: Subpixel
- Scaling Factor: 1,25

Bu ayarları yaptığımızda anında ekranda fontların büyüdüğünü ve tam olmasa bile arayüz bileşenlerinin de kendilerini büyüyen fontlara uydurduğunu göreceğiz. 
Bu noktada şunu eklemem lazım: arayüz bileşenleri tercih etmediğimiz 1,25 ekran scaling ile büyüdüğü kadar büyümeyecek ama bu benim için bir problem değil hatta
daha kompakt tasarımları sevdiğim için avantaj bile oluyor diyebilirim.  

İlk aşama için fena değil gibi ama hem bazı çözmemiz gereken sorunlar olacak hem de daha görsel olarak özelleştirmelere başlayamadık. Bir sonraki yazımda 1,25
font scaling sonrası sorunları çözüp arayüz bileşenlerini özelleştirmeye başlayacağım. 
