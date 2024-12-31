---
title: "Ağ Topolojisi Nedir"
date: 2024-12-31
draft: false
tags: ["ağ", "topoloji"]
categories: ["Network"]
author: "Oğuzhan Kuşca"
description: "Ağ topolojisine genel bir bakış ve fiziksel topoloji türleri."
---

Selamlar. İlk yazımda sizlere **ağ topolojilerinden** bahsetmek istiyorum. Ağ topolojisi "Bir ağı oluşturan cihazların fiziksel ve mantıksal yerleşimi" olarak tanımlanır. Yine ağ topolojilerini **fiziksel topoloji** ve **mantıksal topoloji** olarak ikiye ayırabiliriz.
<!--more-->
Yazının ana odağı fiziksel topolojiler olacak. Ancak konuya geçmeden önce mantıksal topolojiye kısaca değinelim.


## Mantıksal Topoloji Nedir?
___
Ağ cihazlarının birbirleriyle nasıl iletişim kuracaklarını, verilerin ağ içinde nasıl aktığını gösteren topolojilerdir. Broadcast (Yayın) ve Token Passing (Jetonlu Geçiş) olmak üzere iki başlıkta incelenebilir.

## Fiziksel Topoloji Nedir?
___
Gelelim asıl konumuz olan fiziksel topolojiye... Fiziksel topolojiyi tanımlamak istediğimiz zaman ağı oluştururken kullanılan çevre birimlerinden (router, switch, access point, bilgisayar, çeşitli kablolar) ve bu cihazlar arasındaki fiziksel bağlantı metodlarından bahsederken kullanılan kavramdır şeklinde bir tanım yapabiliriz.

Fiziksel topoloji türlerini **ortak yol (bus)**, **halka (ring)**, **yıldız (star)**, **gelişmiş yıldız (extended star)**, **ağ/örgü (mesh)**, **noktadan noktaya (point-to-point)** ve **ağaç (tree)** topolojileri olarak sınıflandırabiliriz. Bunlar en sık kullanılan topolojilerdir. Bunlar dışında **çift halka (dual ring)**, **hücresel (cellular)**, **eğri (irregular)** gibi çeşitlerinden de bahsedebiliriz.

Her topoloji çeşidinin diğerlerine göre avantajları ve dezavantajları bulunuyor, bu yüzden bir topoloji oluşturmak istediğimiz zaman bu avantaj ve dezavantajları göz önünde bulundurarak dikkatli bir seçim yapmamız gerekiyor.

Gelin şimdi bu sık kullanılan topoloji türlerine bir bakalım.

### Noktadan Noktaya Topolojisi (Point-to-Point Topology)
___
Bir alıcı ve bir göndericiden oluşan en temel topolojidir. Bu topolojide veri aktarımı tek yönlü olabileceği gibi çift yönlü de olabilir. Cihazlar arasındaki bağlantı bir kablo aracılığıyla sağlanabileceği gibi kablosuz olarak da sağlanabilir.

Yalnızca bir gönderici ve bir alıcıdan oluştuğu için bu topoloji türü veri güvenliği bakımından avantajlı bir konumdadır.

Özetleyecek olursak noktadan noktaya topolojinin;
#### Avantajları:
- Yüksek bant genişliğine sahiptir.
- Yalnızca iki cihaz arasında bağlantı kurulduğu için oldukça hızlıdır.
- Kurulumu ve bakımı oldukça kolaydır.
- Cihazlar arasında ekstra bir aracı olmadığı için veri güvenliği konusunda avantajlıdır.
#### Dezavantajları:
- Cihazlar arasında tek bir bağlantı olduğu için bu bağlantının zarar görmesi durumunda ağ çöker.
- Yine sadece iki cihazdan oluşan bir ağ olduğu için iki cihazdan birinin zarar görmesi durumunda ağ kullanılamaz hâle gelir.

### Ortak Yol Topolojisi (Bus Topology)
___
Ortak yol topolojisinde tüm cihazlar tek bir **omurgaya** bağlıdır.

Bu topolojide veri tüm cihazları teker teker dolaşır ve sonunda hedef cihaza ulaşır. Tüm cihazları dolaştığı esnada cihazlar gelen veriyi kontrol eder ve şayet verinin adresi kendisiyle alakalıysa veriyi işler, değilse pasif davranır ve veriyi bırakır.

Tüm cihazların bağlı olduğu omurgada koaksiyel kablo kullanılır. Kullanılan koaksiyel kablonun ince olduğu durumlarda hat uzunluğu maksimum 185 metre, kablonun kalın olduğu durumlarda hat uzunluğu maksimum 500 metredir. Ayrıca bu tip bir ağa en fazla 30 cihaz bağlanabilir.

Bu tip hatların her iki ucunda da birer adet sonlandırıcı bulunur.

Veri hedef cihaza ulaşana kadar yoldaki tüm cihazları teker teker dolaştığı için ağ performansı düşüktür.

Özetleyecek olursak ortak yol topolojisinin;

#### Avantajları:
- Ağın kurulumu kolaydır.
- Ağa yeni cihaz eklemek kolaydır.
- Kablo kullanımı azdır, haliyle ekonomiktir.
- Ağ omurgası üzerinde veri iletimi doğrudan yapıldığı için Switch/Hub gerekmez, bu yönüyle de ek maliyetlerin önüne geçer.
- Ağ üzerindeki cihazlardan birinin arızalanması diğer cihazları etkilemez.
#### Dezavantajları:
- Ağa bağlanabilecek cihaz sayısı sınırlıdır.
- Hat uzunluğu sınırlıdır.
- Omurgada yaşanan herhangi bir sıkıntı ağın genelini etkiler.
- Yaşanan sorunların tespiti ve giderilmesi zordur.
- Bant genişliği düşüktür.
- Eklenen her cihaz ağ performansını düşürür.

### Halka Topolojisi (Ring Topology)
___
Halka topolojisinde adından da anlaşılacağı üzere tüm cihazlar halka şeklinde birbirine bağlıdır. Merkezde bir [MAU (Multistation Access Unit)](https://networkencyclopedia.com/multistation-access-unit-mau/) bulunur. Gönderilen veri alıcıya ulaşana kadar tüm cihazlara teker teker uğrar. Sinyaller bir cihazdan diğer cihaza tek yönlü olarak iletilir. (Bu topolojinin çift yönlü olanı Dual Ring olarak adlandırılır.) Yani her cihaz kendinden önceki cihaz için bir alıcı, kendinden sonraki cihaz için ise bir gönderici konumundadır. Gelen sinyal her cihazda yeniden oluşturulduğu için zayıflanama en düşük düzeydedir.

Ağ üzerindeki veriler **jeton (token)** adı verilen 3 byte'lık paketlerle gönderilir. Bu paket alıcıya ulaşana kadar ağdaki tüm cihazları dolaşır.

Örneğin 50 cihazdan oluşan bir ağımız olduğunu düşünelim. İlk cihazdan son cihaza gönderilen bir veri aradaki 48 cihazı teker teker dolaştıktan sonra alıcıya ulaşacaktır.

Özetleyecek olursak halka topolojisinin;

#### Avantajları:
- Herhangi bir sunucuya ihtiyaç yoktur.
- Ağda bulunan tüm cihazlar aynı yetkiye sahiptir.
- Ağın büyütülmesinin performansa etkisi düşüktür.
- Kurulumu kolaydır.
- Ağda çarpışma olasılığı minimumdur.
#### Dezavantajları:
- Kullanılan kablo miktarı fazla olduğu ve MAU'ların hub'lara göre daha pahalı olmasından kaynaklı olarak maliyeti yüksektir.
- Cihazlardan herhangi birinde yaşanan bir problem tüm ağı etkilemektedir.

### Yıldız Topolojisi (Star Topology)
___
Günümüzde en yaygın kullanıma sahip olan yıldız topolojisi, ağdaki her cihazın merkezde bulunan switch veya hub'a bağlanmasıyla oluşturulan topoloji türüdür. Göndericiden çıkan veri önce merkezdeki Switch/Hub'a gider, oradan da alıcı cihaza iletilir.

Cihazlar arasındaki bağlantı çift burgulu kablolar ile sağlanır. Ağa bağlı cihazların merkezdeki Switch/Hub'a olan uzaklığı maksimum 100 metredir. Bu uzaklığın üstüne çıkıldığı durumlarda ağda ciddi performans kayıpları yaşanmaktadır.

Yıldız topolojisi sıklıkla yerel ağlarda (LAN) kullanılır. Oluşturulan yıldız topolojilerinin birbirine eklenmesiyle gelişmiş yıldız (extended star) olarak adlandırılan topolojiler oluşturulmaktadır.

Özetleyecek olursak yıldız topolojisinin;
#### Avantajları:
- Ağa yeni cihaz eklemek ya da ağdan cihaz çıkarmak kolaydır.
- Ağda yaşanan bir sorunun tespiti ve ağ yönetimi kolaydır.
- Bağlı cihazlardan birinde oluşan bir sorun ağın genelini etkilemez.
- Yapısı ve anlaşılması oldukça basittir.
#### Dezavantajları:
- Merkezdeki hub ya da switch'te yaşanan bir arıza tüm ağı etkiler.
- Diğer topolojilere göre kablo kullanımı daha fazladır.

### Örgü Topolojisi (Mesh Topology)
___
Örgü topolojisinde ağdaki bir cihaz diğer tüm cihazlarla doğrudan bağlantılıdır. Çoğunlukla geniş alan ağları (WAN) arasında kullanılır.

Her cihaz diğer bütün cihazlarla bağlantı kurduğu için ağdaki herhangi bir bağlantının kopması durumunda, veri diğer bağlantıları kullanarak alıcıya ulaşabilmektedir.

Ağa bağlı cihaz sayısının "N" olduğu bir senaryoda "N*(N-1)/2" sayıda bağlantı vardır.

Tam örgü ve kısmi örgü olmak üzere iki çeşidi vardır. Tam örgüde bütün cihazlar birbiriyle bağlantı kurarken kısmi örgüde bir cihazın diğer tüm cihazlarla bağlantılı olmadığı durumlar vardır.

By topolojinin başlıca öne çıkan özellikleri **ölçeklenebilirlik**, **esneklik**,**sağlamlık** ve **tutarlı veri aktarımı** olarak sıralanabilir. Ayrıca bu topolojide herhangi bir merkez noktaya ihtiyaç duyulmaması da öne çıkan özelliklerden bir diğeridir.

Özetleyecek olursak örgü topolojisinin;
#### Avantajları:
- Cihazlardan birinde yaşanan arıza ağın genelini etkilemez.
- Veri iletim hızı oldukça yüksektir.
- Ağın genişletilmek istediği durumlarda diğer bağlantılar etkilenmediği için ağa yeni cihaz eklemek kolaydır.
#### Dezavantajları:
- Bağlantı sayısı çoktur. Bu yüzden karmaşık bir yapıdadır.
- Her cihaz birbiriyle bağlantı kurduğu için kablo kullanımı çok yüksektir. Haliyle maliyet yüksektir.

### Ağaç Topolojisi (Tree Topology)
Temel olarak yıldız topolojisi ve ortak yol topolojisinin birleşimi şeklinde oluşmuş bir topolojidir. Yıldız şeklinde oluşturulmuş ağların bir omurga üzerinde toplanmasıyla oluşur.

Bir başka yönden de gelişmiş yıldız topolojisine benzemektedir. Aralarındaki fark ise ağaç topolojisinde herhangi bir merkezi düğüme ihtiyaç olmamasıdır.

Ağaç topolojisi büyük ağların omurgalarını oluşturmak için kullanılır.

**Omurga ağacı (backbone tree)** ve **ikili ağaç (binary tree)** olarak iki farklı yapıda oluşturulabilir. Omurga ağaç düzeninde bütün düğümler hiyerarşik bir düzen içinde alt dallara ayrılır. İkili ağaç düzeninde ise her düğüm sadece iki dala bölünerek yapıyı oluşturur. Ağaç topolojisinde verinin akışı hiyerarşik bir düzendedir. Bu yüzden bu yapı **Hiyerarşik Ağaç Topolojisi (Hierarchical Tree Topology)** olarak da adlandırılmaktadır.

Özetleyecek olursak ağaç topolojisinin;
#### Avantajları:
- Alt cihazlar arasında yaşanan bir arıza ağın genelini etkilemez.
- Hata tespiti kolaydır.
- Farklı donanım üreticilerinin cihazları uyum içinde çalışabilir.

#### Dezavantajları:
- Kullanılan kablo tipine göre alt cihazlar arasındaki uzunluk limitli olabilir.
- Ana omurgada yaşanan bir arıza tüm ağın çökmesine neden olur.
- Ana omurgada aşırı trafik olduğu durumlarda çarğışmalar ve gecikmeler yaşanabilir.
#### Özetleyecek Olursak
Ağ topolojisi, bir ağı oluşturan cihazların fiziksel veya mantıksal yerleşimini ifade eder. **Mantıksal Topoloji**, cihazlar arasındaki veri akışını ve iletişim yöntemlerini tanımlarken; **fiziksel topoloji** ise cihazların fiziksel olarak nasıl bağladnığını, ağ oluştururken hangi cihazların kullanıldığını gösterir.
Fiziksel topolojileri inceleyecek olursak en basit şekilde tasarlanan **noktadan noktaya (point-to-point)** topoloji, günümzde en yaygın kullanılan **yıldız (star)** topolojisi diyebiliriz.

##### Kaynaklar
- [Temel Ağ Topolojileri](https://www.cozumpark.com/temel-ag-topolojileri/)
- [Ağ Topolojileri](https://www.teknologweb.com/ag-topolojileri-nedir)
- [What is Star Topology](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-star-topology/)
- [Types of Network Topology](https://www.geeksforgeeks.org/types-of-network-topology/?ref=ml_lbp)
- [Network Topology](https://www.geeksforgeeks.org/network-topology/?ref=ml_lbp)
- [What is Mesh Topology](https://www.geeksforgeeks.org/advantage-and-disadvantage-of-mesh-topology/?ref=ml_lbp)
- [A Guide to Mesh Topology](https://www.zenarmor.com/docs/network-basics/what-is-mesh-topology)
- [Point-to-Point Networking](https://networkencyclopedia.com/point-to-point/)
