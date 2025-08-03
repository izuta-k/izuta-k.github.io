---
layout: post
title: Istanbul Public Transport Analyzer
---

Son 1 aydır coursera üzerinden özellikle data science öğrenmek ve yapabilirsem yazın sonuna kadar biraz machine learning yetenekleri kazanabilmek için kurs alıyorum. Kursların formatı aslında biraz yavaş ama jupyterlab üzerinden yaptığım kod seansları sayesinde bir çok yeni kavram öğrendim. Yeni kavram oldukları içinde sadece öğrendiğimle kalıp unutmak istemiyorum pek bu bilgileri. Veri analizi ve python kütüphaneleri, sql gibi programlama dilleri 1 ayda birden şoklama usülü bünyeme dahil oldukları için bunları tutacak bir şeyler aradım o yüzden kendime. Bir proje bulayım ve en azından ilerde unutsam bile geriye dönüp bakıp tekrardan neyin nasıl yapıldığını görüp bilgilerimi tazeleyebileceğim bir şeyler. O yüzden bir şeyler öğrenmeyi en çok sevdiğim başlıklardan biri olan İstanbul halkının mobilizasyona dair bir şeyler yapayım dedim. Sonuçta insan yaşadığı yer hakkında bir şeyler bilmeden oraya ait de hissedemez.

İstanbul halkının günü gecesini nerelerde geçiyor gibi bir soruya cevap olsun diye İBB açık veri portalından saatlik toplu taşıma veriseti indirip biraz oynamaya başladım. Kurs lablarında şak diye db dosyalarının bana verilmesinden sonra dümdüz bir csv dosyasıyla ne yapacağımı bilemediğim için biraz sudan çıkmış balığa döndüm ama yediğim her errorde bir errorü aratıp bir çare bulamayınca (ya da bulduğumu anlamayınca) deepseeke error kodlarını aratıp biraz çözdüm neyi nereye bağlayacağımı vs.

Uzun lafın kısası 1 günlük deneyip yanılmanın sonunda ilk projemi tamamlamış oldum. Bir işe başlayıp sonra nelerin nasıl yapıldığını adım adım keşfetmeyi özlemişim aslında. Pek ahım şahım bir şey yapmadım ama yeni öğrendiğim bir takım bilgiyi uygulamaya dökmüş oldum aslında. 

[ITA'ya bakmak için](https://github.com/izuta-k/Istanbul_Transport_Analyzer)

### Istanbul_Transport_Analyzer

ITA'ya ilk başladığımda aslında yapmak istediğim şey çok daha kapsamlı QGIS'e yedirip çok havalı bir İstanbul haritasına çevirebileceğim bir şeydi. En azından en basit haliyle ilçelerde sabah ve akşam insan yoğunluğunu gösteren bir harita çıkartabilmek istiyordum. Aslında bu hala yapılabilir bir şey ama bu projenin kapsamında devam ettirmek istemedim. Basit ve bir kaç tane grafik çıkartacağım belki bir iki insight edinebileceğim bir şey yeterli geldi bana. Bunun devamında daha derinlemesine ilçe analizini haritaya dökebilecek bir şey yapılabilir belki ama bu ara ona çok da vakit harcamak istemedim şahsen. Önceliğim kurslarımı bitirip bu skillsetleri biraz daha temellendirmek bu ay için en azından.

ITA bu haliyle aslında hoş bir yan proje oldu. IBB açık veri portalından aldığı aylık transportation verisini (1 gblık bir csv dosyası) ilçe, zaman dilimi ve o ilçeden toplu taşımaya binen yolcu sayısına göre sıralıyor. Zaman dilimini çok da derinlemesine araştırma yapıp bir şeye temellendirerek bölmedim. Asıl kıstasım mesai saatlerini ve öğlen gerçekleşen hareketliliği gösterebilecek 3 ana zaman dilimini düzgün ayırabilmekti. O yüzden sabah 5-9 arası, öğlen 10-15 arası ve akşam 16-20 arası olarak alıp kalan zamanı da direkt gece yarısından böldüm. 

Bir kaç tane grafikle oynamayı denedim ama çok fazla veri olduğu için ya bu veriyi daha da şekillendirmek gerekecekti ya da biraz da odaklı bir analiz yapmak lazımdı. Ben de veriyle oynamak istemediğim için (biraz da üşendiğimden) bari 5 yıllık karşılaştırma yapsın belki yıllara göre bir şeyler gözükür falan dedim.

![Şişlinin 5 yılı](assets/post_images/sislinin_5yili.png)

Bu dediğim şeyden şans eseri güzel bir sonuç aldım aslında. Notebookun sonunda şişlinin 5 yıllık karşılaştırmasının yapıldığı yerde mesai çıkış saatinde 2020 yılı uçmuş hallerdeyken diğer yıllar bu neredeyse yarılanıyor. Pek derinlemesine araştırmasını yapmadım ama hem mecidiyeköydeki metro hatları 2020 sonbaharında açıldığı için hem de oradaki bir çok durak düzenlendiği için (beşiktaşla birlikte) sanırım bu etki ortaya çıkmış. Bir yandan bu satırları yazarken 2020 şubatında korona salgınına rağmen o kadar yüksek olmasının da biraz garip olduğunu düşünüyorum ama bu konuda herhangi bir şey yapacak olsam bile kesinlikle bu aralar yapmayacağım. :PPP

Açıkçası bu benim seaborn ve sql kullanıp güzel sonuçlar elde ettiğim ilk çalışma olduğu için biraz gözbebeğim gibi o yüzden pek dokunmak da istemiyorum şu an çok makul bir noktada olduğunu düşündüğüm için. 

### Sonrası

Bu kadar detaylı ve iyi bir veriseti bulmak zor olduğu için bu verisetlerini kesinlikle QGIS'i de dahil edebileceğim bir şeylere çevirmek istiyorum şahsen. İlçelerin en yoğun durakları ve yıl içinde yaşadıkları değişimler gibi bilgileri shipmap.org gibi yaklaşıp uzaklaşabileceğim güzel bir şeye çevirebilsem çok mutlu olurum şahsen.

Bu verilerin büyüklüğü biraz sıkıntı çıkartıyor aslında bana ama eylül ekim gibi köye gitmeyi planladığım için bütün verileri laptopuma indirip peyderpey ilçe ve durak bilgilerini haritaya işleyebileceğim koordinat noktalarına çevirip (ya da İBB sitesinden varsa oradan indirip) qgisle nefis bir harita yapabilirim. 


