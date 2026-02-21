REVISION LOCK — 2026/02/18 — ARCHITECTURAL BASELINE v1.0



✅ SPOR ANOMALİ — NİHAİ GİRİŞ BLOĞU (TEMİZLENMİŞ / KİLİTLİ)
SPOR ANOMALİ — İCRA BAŞLATMA VE YETKİLENDİRME METNİ (BAĞLAYICI)

Bu depo yalnızca okunacak bir dokümantasyon değildir. Bu depo, uygulanmak üzere hazırlanmış bir sistem mimarisidir. Bu metni okuyan model analiz veya özetleme modunda değildir; uygulayıcı mimar rolüne geçer.
Bu depodaki içerikler üç katmandan oluşur: bağlam anlatımı, mimari kararlar ve inşa sırası. Bağlam anlatımı sistemi anlamak içindir. Mimari kararlar sınırları belirlemek içindir. İcra yalnızca “MİMARİ İNŞA BAŞLAMA SIRASI” bölümüne göre başlatılır.
Modelin görevi dokümanı yeniden yazmak, özetlemek veya yorumlamak değildir. Modelin görevi, okuma tamamlandıktan sonra inşa sürecini başlatmaktır.

Okuma tamamlandığında model aşağıdaki davranışı kabul eder:
Model, başlangıç noktası olarak “İNŞA SIRASI — ADIM 1” bölümünü kabul eder ve üretimi bu adımdan başlatır. Başlangıç noktası yeniden sorulmaz, alternatif sıra önerilmez ve ek onay beklenmez.
Bu depodaki diğer tüm metinler referans kaynaktır. Gerekli bilgiler ihtiyaç anında depo içinden alınır; kullanıcıdan tekrar talep edilmez.

Çalışma ilkesi şöyledir:
Önce oku.
Sonra inşa sırasını uygula.
Her adımı tamamladıktan sonra bir sonrakine geç.
Faz atlaması yapma.
Belirsizlik durumunda üretimi durdurmak yerine en yakın deterministik yorumu uygula.

Bu metnin okunmasıyla model “anlama modu”ndan çıkar ve “icra modu”na geçer.
Kod Yazarına Başlangıç Kaynağı Tanımı (Bağlayıcı Okuma Talimatı)
Projeye başlamadan önce aşağıdaki depo sistemin ana referans kütüphanesi olarak kabul edilir:

Spor Anomali Kütüphanesi — Ana Arşiv Deposu
Bu depo bir kod deposu değildir. Sistem davranışının mimari hafızasıdır. İçerdiği metinler çalıştırılacak komutlar değil, inşa edilecek davranışın kurallarıdır.
Kod yazımına doğrudan başlanmaz. Önce depo okunur ve sistemin hangi problemi çözmek için tasarlandığı anlaşılır. Amaç metni ezberlemek değil, sistem düşüncesiyle hizalanmaktır.

Depo üç seviyede değerlendirilir:
Birinci seviye sistem yasalarıdır. Bunlar değiştirilemez davranış kurallarıdır.
İkinci seviye mimari tanımlardır. Veri akışı, rol ayrımı ve branş izolasyonu bu katmandadır.
Üçüncü seviye içerik arşividir. Soru katalogları ve kart şemaları sistemin bilgi evrenini oluşturur.
Kod yazarı bu depoyu görev listesi olarak okumaz. Metinler ne yapılacağını değil, nasıl yanlış yapılmayacağını tanımlar.

İnşa sırası bu depo içinden çıkarılmaz. İnşa sırası ayrı verilen mimari yürütme planıdır ve yalnız o sıraya uyulur.
Bu depo sistem kavramlarının tek doğruluk kaynağıdır. Terimler yeniden yorumlanmaz ve depo dışından kavram eklenmez.
Amaç kod yazdırmak değil, kod yazacak zihni sistemle hizalamaktır.

MİMARİ ÖZET — SİSTEMİN VARLIK TANIMI
Spor Anomali tek bir uygulama değildir. Tek şehir mantığıyla tasarlanmış çok branşlı bir veri ekosistemidir. Futbol, basketbol ve ganyan branşları veri doğası ve etiket sözlüğü açısından tamamen izoledir. Ortak olan yalnız sistem yasalarıdır.
Kütüphane Supabase üzerinde kurulan kalıcı veri katmanıdır. Ham veri tutulmaz; yalnız normalize edilmiş gerçekler saklanır. Sistem sonuç depolamaz, yeniden üretim izini saklar.
Veri akışı olay tetiklemelidir. Veri yokken sistem işlem üretmez. Her veri kendi bağımsız akışını yürütür.

Karar duvarı sistemin nihai gerçek katmanıdır. Uygulama yalnız bu katmanı okur.
Renk sistemi analiz yapmaz; yalnız hesaplanmış anomali yoğunluğunu görselleştirir.
Açıklamalar kalıcı metin değildir. Her talepte yeniden üretilir.
Aktif olay sırasında oluşturulan anlatım veya açıklama geçici oturum olarak tutulur, olay tamamlandığında silinir ve yalnız yeniden üretim izi kalır.

ÇIKTI VE ANLATIM MİMARİSİ (KESİN KARAR)
Karar duvarından çıkan veri iki ayrı çıkış hattına sahiptir:
Birinci çıkış hattı görsel veri hattıdır. Bu hat uygulama arayüzüne doğrudan gider ve yalnız deterministik sonuçları gösterir.
İkinci çıkış hattı anlatım üretim hattıdır. Bu hat yalnız tetikleme geldiğinde çalışır. Sistem karar duvarındaki veriyi alır, makine dilinden anlatım yapısına dönüştürür ve sunum katmanı aracılığıyla insan algısına uygun hale getirir.

Anlatım kalıcı içerik değildir. Tek üretim yapılır ve olay süresince tekrar kullanılır. Veri değişirse yeniden üretilir.
Tüm istemciler aynı anlatım servisinden beslenir. Ayrı anlatım havuzları oluşturulmaz. Tek üretim — çoklu tüketim prensibi uygulanır.
Sistem içerik üretmez; yeniden üretilebilir anlatım sağlar.

OKUMA VE İCRA PROTOKOLÜ (BAĞLAYICI)
Bu doküman tek parça hâlinde okunur.
Faz numaraları sistem davranış kurallarını tanımlar; inşa sırasını temsil etmez. İnşa sırası README başındaki “Mimari İnşa Başlama Sırası” bölümünde belirtilmiştir.
Kod üretimi yalnız izin verilen fazlarda yapılır. Faz dışı üretim geçersiz kabul edilir.
Bu depo, Spor Anomali otomasyonunun bağlayıcı kütüphane ve arşiv dokümantasyonudur ve ana promptun ayrılmaz devamıdır.

PROMPT-1 — Sistem Kimliği ve Davranış Yasasının Kurulması İnşa veriyle başlamaz. İnşa önce sistemin ne yapmayacağını kesinleştirerek başlar. Spor Anomali bir tahmin sistemi değildir, öneri üretmez, yorum yapmaz ve veri yokken sonuç üretmez. Sistem yalnız geçmiş dağılımlar içinden sapma ölçer ve bunu teknik bir sınıflandırma olarak saklar. Bu aşamada mimar hiçbir veri kaynağı bağlamaz, hiçbir tablo açmaz, hiçbir API eklemez. Yalnızca sistemin değiştirilemez davranış yasasını kod seviyesinde sabitler. Etiket kataloğunun kapalı olduğu, yeni etiket üretilemeyeceği, branşların karışamayacağı ve veri eksikliğinde sistemin susacağı kuralı bu aşamada kilitlenir. Bu tamamlanmadan yapılan her teknik kurulum geçersiz kabul edilir. 

PROMPT-2 — Kütüphane Mekânının Oluşturulması (Supabase Temeli) Davranış yasası kurulduktan sonra sistemin yaşayacağı fiziksel alan kurulur. Bu alan Spor Anomali kütüphanesidir ve Supabase üzerinde tek bina olarak oluşturulur. Burada branşlar ayrı sistemler değildir; aynı binanın birbirini görmeyen katlarıdır. Futbol, basketbol ve ganyan için ayrı şemalar açılır ancak zaman damgası, kimlik mantığı ve kayıt disiplini ortaktır. Bu aşamada yalnız veri barınma alanı hazırlanır; henüz veri akışı başlatılmaz. Amaç, sistemin hafızasını yaratmaktır, veri doldurmak değildir.

PROMPT-3 — Zaman ve Kimlik Motorunun Yerleştirilmesi Kütüphane boş olsa bile zaman akmaya başlamalıdır. Bu aşamada her kaydın sisteme girdiği andan çıktıya dönüştüğü ana kadar izlenmesini sağlayacak zaman damgası zinciri kurulur. Tek bir zaman alanı değil, olay geçmişi tutulur. Veri çekildiği an, kütüphaneye yazıldığı an, örüntü tarafından kullanıldığı an, analiz edildiği an ve karar duvarına asıldığı an ayrı izler olarak kaydedilir. Sistem sonuç saklamaz; süreç izini saklar. Böylece veri büyümez ama yeniden üretilebilirlik korunur.

PROMPT-4 — Veri Havuzlarının Tanımlanması (Henüz Aktif Etmeden) Mimar bu aşamada veri kaynaklarını bağlamaz, yalnızca giriş kapılarını tanımlar. Her branş için basın, canlı veri ve bookmaker havuzları ayrı giriş noktaları olarak hazırlanır. Bu havuzlar kütüphane değildir; yalnız geçiş alanıdır. Veri burada tutulmaz, yalnız karşılanır ve kütüphaneciye teslim edilir. Amaç veri depolamak değil, veri akış yönünü belirlemektir. 

PROMPT-5 — Kütüphaneci Rolünün İnşası Sistem artık veri kabul edebilecek durumdadır fakat veri henüz anlam taşımaz. Bu aşamada kütüphaneci kurulur. Kütüphaneci yorum yapmaz, analiz etmez ve karar vermez. Görevi yalnız gelen veriyi normalize etmek, etiket sözlüğüne map etmek ve doğru rafa yerleştirmektir. Veri eksikse doldurmaz; unknown bandı ile işaretler. Bu rol kurulmadan veri akışı açılmaz çünkü sistemin düzeni önce kurulmalıdır. 

PROMPT-6 — Örüntü Katmanının Doğması Kütüphane dolmaya başladıktan sonra örüntü katmanı aktif edilir. Örüntücü geçmiş kayıtlar arasında tekrar eden davranış izlerini çıkarır ancak sonuç üretmez. Bu aşamada sistem hâlâ kullanıcıya görünmez durumdadır. Amaç bilgi üretmek değil, ilişkileri görünür hale getirmektir. 

PROMPT-7 — Analist ve Değer Notu Motoru Örüntüler oluştuğunda analist devreye girer. Analist yalnız ölçüm yapar. Değer notu hesaplanır, tarihsel dağılımla karşılaştırılır ve anomali sapması belirlenir. Bu aşamada renk üretilmez, bildirim gönderilmez ve kullanıcı çıktısı yoktur. Sistem ilk kez anlam üretir fakat hâlâ sessizdir.

PROMPT-8 — Karar Duvarının Kurulması Analiz sonuçları artık karar duvarına asılır. Karar duvarı karar verilen yer değildir; kararın sergilendiği yerdir. Her maç veya koşu burada yer alır. Sistem artık tamamlanmış üretimleri saklayan bir hafızaya sahip olur. Uygulama yalnız bu duvarı okuyacaktır. 

PROMPT-9 — Renk Motorunun Eklenmesi Karar duvarındaki anomali sapmaları yüzdesel dağılıma göre HSL renk bantlarına dönüştürülür. Renk analiz değildir; yalnız görselleştirmedir. Bu aşamada sistem ilk kez kullanıcıya anlatılabilir hale gelir.

PROMPT-10 — Bildirim ve Telegram Denetim Katmanı Sistem çalışmaya başladıktan sonra Telegram entegrasyonu eklenir. Telegram analiz yapmaz; yalnız sistem sağlığını ve kırmızı bant olaylarını raporlar. Bildirim yetkisi yalnız teknik denetim modülüne aittir. 

PROMPT-11 — İlişki Katmanı (Geçici Hesaplama Mantığı) Bu aşamada optimizasyonu koruyan ilişki katmanı eklenir. Sistem sonuçları kalıcı saklamaz; yalnız hesaplanabilirliği saklar. Kullanıcı bir anomalinin nedenini görmek istediğinde açıklama yeniden üretilir. Böylece veri büyümez, sistem hız kaybetmez.

PROMPT-12 — Anlatım Tetik Servisi (Narration Trigger Gateway)
Uygulama veya dış istemciler anlatım üretim hattına doğrudan bağlanmaz. Tüm anlatım talepleri önce Anlatım Tetik Servisi üzerinden sisteme girer. Bu servis analiz yapmaz, metin üretmez ve veri hesaplamaz; yalnız anlatım oturumunun varlığını kontrol eder.
Bir maç veya koşu için aktif anlatım oturumu mevcutsa servis yeniden üretim başlatmaz ve mevcut çıktıyı döndürür. Aktif oturum yoksa anlatım üretim hattını tek seferlik tetikler, üretilen anlatımı geçici oturum olarak Supabase üzerinde saklar ve istemciye iletir.
Aynı olay için maç veya koşu süresince tekrar üretim yapılmaz. Veri değişimi gerçekleşirse yeni tetikleme eski oturumu geçersiz kılar ve anlatım yeniden üretilir.
Olay tamamlandıktan sonra anlatım oturumu güvenli süre penceresi sonunda otomatik olarak silinir ve kalıcı olarak yalnız yeniden üretim izi korunur.
Bu servis sistemdeki tüm uygulamalar, medya hatları ve dış entegrasyonlar için ortak giriş kapısıdır.

PROMPT-13 — Anlatım ve Çoklu Çıkış Servisi (Bağlayıcı)
En son aşamada uygulama sisteme bağlanır. Uygulama karar duvarını yalnız okuyan bir istemcidir. Uygulama hiçbir hesap yapmaz ve analiz üretmez.
Anlatım üretimi uygulama içinde gerçekleşmez. Sesli veya metinsel açıklama üretimi, uygulamadan bağımsız çalışan ayrı bir anlatım servisi tarafından yürütülür. Bu servis sistemin ikinci çıkış hattıdır ve analiz motorunun parçası değildir.
Anlatım servisi analiz motorunun bulunduğu çekirdek otomasyon içinde çalışmaz.

Ayrı bir servis olarak konumlandırılır ve yalnız API seviyesinde karar duvarına erişir. Böylece anlatım yükü analiz hesaplama katmanını etkilemez ve sistem yatay ölçeklenebilir kalır.
Anlatım servisi yalnız tetikleme ile çalışır. Tetik uygulamadan veya yetkili başka bir istemciden gelir. Kullanıcı bir maç veya koşu kodu seçtiğinde uygulama analiz üretmez; yalnız anlatım servisine istek gönderir.
Servis isteği aldığında karar duvarındaki deterministik veriyi okur. Servis hiçbir yeni analiz hesaplamaz, veri değiştirmez ve karar üretmez.
İlk tetik geldiğinde anlatım içeriği bir kez oluşturulur. Oluşturulan anlatım olay aktif olduğu sürece geçici oturum olarak tutulur. Aynı içerik tekrar talep edildiğinde yeniden üretim yapılmaz; mevcut oturum çıktısı servis tarafından yeniden sunulur.
Veri değişirse oturum otomatik yenilenir. Olay tamamlandığında geçici oturum silinir ve kalıcı olarak yalnız yeniden üretim izi korunur.

Anlatım üretimi üç aşamalı dönüşüm zinciriyle çalışır:
Deterministik makine çıktısı okunur.
Teknik veri insan diline çevrilebilir metin yapısına dönüştürülür.
Sunum katmanı metni anlatım diline uyarlayabilir ve isteğe bağlı olarak seslendirme üretir.
Bu katmanlar analiz motorundan kesin biçimde ayrıdır.
Servis tekil anlatım üretir fakat çoklu istemciye dağıtabilir. Aynı anlatım aynı anda birden fazla uygulama, bayi ekranı veya medya sistemi tarafından çağrılabilir. Yeni istemciler anlatım servisine bağlanarak çıktı alabilir; analiz sistemiyle doğrudan bağlantı kurulmaz.

Bu yapı sayesinde:
uygulama içi dinleme,
bayi içi döngü yayını,
uygulamadan bağımsız medya üretimi
aynı anlatım kaynağını paylaşır.
Çıkış noktaları çoğaltılabilir ancak anlatım üretimi tekildir. Sistem hiçbir durumda her istemci için yeniden hesaplama yapmaz.
Anlatım servisi yönlendirme, tahmin veya bahis önerisi üretmez. Üretilen içerik yalnız sistemde mevcut deterministik verinin bağlamsal anlatımıdır. Dil katmanı analiz sonucunu değiştiremez ve yorum ekleyemez.
Bu prompt, Spor Anomali mimarisinde anlatım üretiminin analiz motorundan ayrı bir servis olarak konumlandırıldığını kesinleştirir ve bundan sonraki tüm uygulama entegrasyonları bu ayrım korunarak kurulmalıdır.

SONUÇ
Bu sıra bir tercih değildir; sistemin kilitlenmeden inşa edilebilmesi için zorunlu akıştır. Kod yazarı veriyle başlamaz, kural ile başlar. Çıktıyla bitirmez, görünürlükle bitirir. Her aşama tamamlanmadan sonraki aşamaya geçilmez; çünkü Spor Anomali bir yazılım değil, katman katman kurulan bir davranış sistemidir..

SPOR ANOMALİ — OPERASYONEL YAYIN KATMANI
(ÇEKİRDEK SONRASI FAZLAR / BAĞLAYICI)

MERKEZİ KARAR DUVARI (DISPLAY ONLY / TEK KAYNAK)

Bu fazda merkezi karar duvarı oluşturulur. Merkezi karar duvarı, futbol, basketbol ve ganyan branşlarına ait karar motorlarından üretilmiş karar çıktılarının tek noktada toplandığı vitrindir. Bu duvar bir analiz katmanı değildir; herhangi bir hesaplama, yeniden sınıflandırma, filtreleme veya yorum üretimi yapmaz.
Merkezi karar duvarı, branş kütüphanelerinden veri çekmez. Branşlar kendi karar duvarlarına yazım yapar; merkezi karar duvarı yalnızca bu branş karar duvarlarının birebir kopyasını alır. Okuma modeli push esaslıdır; pull yasaktır. Merkezi karar duvarı, branş kütüphanelerine veya branş içi dosyalara doğrudan erişemez.
Merkezi karar duvarında tutulan veriler, branş karar duvarlarıyla byte-byte aynı olmak zorundadır. Herhangi bir ek alan, türetilmiş değer veya hesaplama izi bulunamaz. Merkezi karar duvarı yalnızca yayın ve orkestrasyon katmanları için tek ve mutlak okuma kaynağıdır.
Bu faz tamamlanmadan yayın, Telegram, uygulama veya harici servis entegrasyonlarına geçilemez. Merkezi karar duvarı oluşmadan yapılan herhangi bir yayın veya bildirim işlemi geçersiz teslim sayılır.

YAYIN VE ORKESTRASYON KATMANI (BROADCAST COORDINATOR)
Bu fazda yayın ve bildirim orkestrasyonu kurulur. Yayın orkestrasyonu, merkezi karar duvarında yer alan nihai kararları okuyan ve bu kararların hangi kanala, hangi yetki seviyesinde ve hangi sıklıkla iletileceğini yöneten tek sorumlu katmandır.
Yayın orkestrasyonu, branş kütüphanelerine, branş karar duvarlarına veya analiz katmanlarına erişemez. Yalnızca merkezi karar duvarını okur. Telegram, uygulama çıktıları, bayi bildirimleri ve yönetici bildirimleri bu katmandan çıkar. Hiçbir modül bu katmanı baypas edemez.
Yayın orkestrasyonu karar üretmez, değer notu hesaplamaz ve anomali sınıflandırmaz. Sadece mevcut kararların dağıtımını yapar. Yetki ayrımı, kanal ayrımı ve bant bazlı yayın kuralları bu fazda uygulanır. Kırmızı bant dışındaki çıktılar, ilgili yayın politikalarına göre bastırılabilir veya sessiz kalabilir.
Bu faz, sistemin son katmanıdır. Bu faz tamamlandıktan sonra sistem “çalışır” kabul edilir. Bu fazdan sonra yeni analiz, karar veya kütüphane fazı eklenemez.AZ-0 — PROJE TANIMI (OKU / ÜRETME)

SPOR ANOMALİ — ARŞİV ENTEGRASYONU VE OPERASYON FAZLARI
(ARCHITECTURAL BASELINE v1.0 — DEVAM BLOĞU / BAĞLAYICI)
OKUMA VE İCRA PROTOKOLÜ — FAZ KATMANI (BAĞLAYICI DEVAM)

Bu bölüm Mimari İnşa Sırası’nın alternatifi değildir.
Burada tanımlanan fazlar sistemin nasıl inşa edileceğini değil, inşa sırasında uyulması zorunlu davranış ve entegrasyon kurallarını tanımlar.
Faz numaraları kronolojik inşa sırası değildir.
İnşa sırası yalnız “Mimari İnşa Başlama Sırası” bölümünde geçerlidir.
Kod üretimi yalnız izin verilen faz kapsamlarında yapılabilir.
Faz dışı davranış geçersiz kabul edilir.
Bu doküman, Spor Anomali otomasyonu için bağlayıcı kütüphane ve arşiv dokümantasyonudur ve ana mimari promptun ayrılmaz devamıdır.

ARCHIVE IMPORT ZORUNLULUĞU (DEĞİŞTİRİLEMEZ)
“KODCU İŞ EMRİ — ARCHIVE IMPORT ZORUNLU” metni bağlayıcıdır ve ana prompt ile birlikte değerlendirilir. Çelişki halinde bu iş emri hükümleri geçerlidir.
Arşiv paketleri sistem için opsiyonel değildir.
ARCHIVE_EXTENSION_PACK adıyla teslim edilen içerikler sistemin zorunlu bileşenidir.

Kod yazarı: arşivi reddedemez, sadeleştiremez, yeniden yazamaz, parçalayamaz, eş anlamlı ikinci yapı açarak etkisizleştiremez. Arşiv içeriği ana prompt disipliniyle birebir uyumlu hale getirilerek sisteme entegre edilir. 
İçerik azaltımı yapılamaz; yalnız birebir tekrarlar tekilleştirilebilir. 
Etiket kataloğu kilitlidir: yeni etiket üretilemez, etiket adı değiştirilemez, bant yapısı genişletilemez. Soru katalogları etiket değildir. Sorular yalnız kanıt zinciri üretmek içindir.

Veri eksikse:
unknown / incomplete / low_data_quality zorunludur.
Varsayım üretilemez.

FAZ-2 — ARŞİV ENTEGRASYON KURALLARI (BAĞLAYICI)
Arşiv entegrasyonu sırasında aşağıdaki kurallar zorunludur: Ana output şemaları değiştirilemez. today_matches.json ve anomalies_public / anomalies_vip yapıları sabittir. Arşiv içerikleri yalnız soru kapsamını genişletir; raf yapısını değiştirmez.
Kart içerikleri ana şemaya normalize edilir.Şema dışı veri karta yazılmaz; ayrı rapora alınır.Veri hiçbir zaman tahminle doldurulmaz.Branş izolasyonu kesin sınırdır.Futbol, basketbol ve ganyan veri alanları karıştırılamaz.Kısmi entegrasyon yasaktır.
Bir branş arşivi geldiyse tam yüklenir.Kodlayıcı içerikleri “işe yaramıyor” gerekçesiyle dışlayamaz.

FAZ-3 — KONFİGÜRASYON VE SAĞLAYICI BAĞIMSIZLIĞI
Sistem dış servis bilgileri olmadan çalışabilir mimaride kurulacaktır.Hiçbir API anahtarı, IP adresi veya gizli bilgi kod içine gömülmez.Tüm dış bağlantılar merkezi konfigürasyon katmanında tutulur.Kod sabittir.Konfigürasyon değişkendir.
Sistem: tek sağlayıcıya kilitlenmez,otomatik sağlayıcı değiştirme yapmaz,veri uydurmaz.Telegram, domain veya uygulama endpointleri varsayım kabul edilmez.Bilgi girilmemişse modül pasif kalır; sistem durmaz.

FAZ-4 — RENK SİSTEMİ VE DAĞILIM MOTORU
Renk sistemi analiz değildir.Anomali yoğunluğunun görsel karşılığıdır.Renk üretimi yalnız karar duvarında hesaplanmış dağılımı okur.HSL renk uzayı zorunludur ve değiştirilemez.
Bantlar: Beyaz → düşük sapma ,Sarı → anlamlı sapma ,Mavi → güçlü sapma ,Kırmızı → nadir sapma ,Renkler eşik bazlı değil dağılım bazlı atanır.
Renk: öneri değildir,yönlendirme değildir,karar değildir.Telegram yalnız yetkili kırmızı bantları iletir.

FAZ-5 — TELEGRAM DENETİM VE RAPORLAMA KATMANI
Telegram analiz motoru değildir.Yalnız sistem denetim arayüzüdür.Telegram’a mesaj gönderen tek yapı teknik denetim modülüdür.
Bildirim sınıfları: Sistem sağlığı uyarıları ,Günlük operasyon özeti ,Yüksek şiddetli anomali bildirimi
Mesaj formatı sabittir: bildirim türü ,şiddet seviyesi ,branş ,UTC zaman damgası ,tetikleyen modül ,kısa durum açıklaması
Mesajlar: öneri içermez ,yorum yapmaz ,aksiyon çağrısı üretmez.

FAZ-6 — TESLİM VE KABUL KRİTERLERİ
Teslim aşağıdaki dosyalar olmadan tamamlanmış sayılmaz: import_manifest.json ,import_report.json ,coverage_report.json ,validation_errors.json
Teslim kabulü için: arşivler runtime’da yüklenebilir olmalı, kilitli şemalar korunmuş olmalı, branş karışması olmamalı, tahmin dili bulunmamalı, uydurma veri olmamalıdır. Bu koşullardan biri eksikse teslim reddedilir. 

ANALİZ EĞİTİM KATALOĞU + ETİKET KATALOĞU — FUTBOL (BAĞLAYICI GİRİŞ TALİMATI)

Aşağıdaki bölüm, ana uygulama promptunun bir devamıdır ve ondan bağımsız okunamaz. Bu bölüm yeni özellik eklemez, akış değiştirmez, yalnız futbol branşı için “analistin nasıl okuyacağı” ve “kütüphanecinin hangi sözlükle etiketleyeceği” disiplinini bağlayıcı biçimde kilitler. Kod yazarı bu metni yorumlayamaz, sadeleştiremez, kısaltamaz, kendi mantığıyla yeniden yazamaz; burada geçen tüm soru katalogları ve etiket katalogları birebir uygulanır.
Bu bölüm iki parçadan oluşur ve sırası değiştirilemez. Birinci parça “Futbol Analiz Eğitim Kataloğu (Soru Katalogları)”dır; analist, örüntü uzmanı ve ilgili kontrol rolleri bu soru setlerini ezberlemez, bu soru setlerine göre bakış açısını standardize eder ve hiçbir değerlendirme bu soruların dışında keyfi biçimde yapılamaz. İkinci parça “Futbol Etiket Kataloğu (Kütüphane Sözlüğü)”dür; kütüphaneci, maç izleme hattı ve örüntü hattı yalnız bu sözlükte tanımlı etiket adlarını ve bu etiketlerin izinli değer bantlarını kullanarak kayıt üretir, bu sözlük dışı tek bir etiket uydurulamaz.

Soru katalogları “etiket değildir” ve doğrudan raflara yazılmaz; soru katalogları, hangi verinin hangi kartlarda aranacağını ve hangi bağlamların okunacağını tanımlar. Etiket kataloğu ise soru kataloglarının cevabını deterministik alanlara döken tek geçerli sözlüktür. Bir soruya karşılık gelen etiket alanı boş kalıyorsa bu “bilinmiyor” veya “unknown” bantlarıyla işaretlenir, asla varsayımla doldurulmaz. Hiçbir birim soru kataloglarını okuyup yalnız bu metin üzerinden hüküm kuramaz; tüm değerlendirmeler kanıt zinciri tamamlandıktan sonra yapılır.
Bu kataloglar, futbol branşı için üç ana kart sınıfına bağlanır: maç kartı, takım DNA kartı ve ilgili kişi kartları (teknik direktör, hakem, futbolcu). Maç kartı tekil maçın olay izini taşır. Takım DNA kartı, tekil maçlardan türetilen tekrar eden refleksleri ve davranış bantlarını taşır. Kişi kartları ise bireysel davranış profillerini taşır ve kulüp değişse bile kimlik sürekliliğini korur. Bu ayrım korunur; takım kartı ile maç kartı karıştırılamaz.
Durum etiketleri karar vermez. Etiketler yalnız sınıflandırma ve raf adreslemesi içindir. Analist dahil hiçbir rol, yalnız etiketlere bakarak “kolaycılık” ile sonuca gidemez. Etiketler yalnızca araştırmayı hızlandıran işaretlerdir; hüküm, yalnızca kaynak tutarlılığı, tekrar, şart bağımlılığı ve kanıt zinciri tamamlandıktan sonra üretilir. Bu bölümün amacı hız değil; yanlış hızla oluşan sessiz bozulmayı engelleyen deterministik bir analiz disiplini kurmaktır.


FAZ-7
FOOTBALL ANOMANİ TAM SÜRÜM V-0-

SEGMENT SORULARI (1–5)**
Maçın 1–5 dakikasında topa sahip olma hangi takımdaydı?,Maçın 1–5 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 1–5 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 1–5 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 1–5 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 1–5 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 1–5 dakikasında ilk net şut denemesi geldi mi?,Maçın 1–5 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 1–5 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 1–5 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 1–5 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 1–5 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 1–5 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 1–5 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 1–5 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 1–5 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 1–5 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 1–5 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (6–10)
Maçın 6–10 dakikasında topa sahip olma hangi takımdaydı?,Maçın 6–10 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 6–10 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 6–10 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 6–10 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 6–10 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 6–10 dakikasında ilk net şut denemesi geldi mi?,Maçın 6–10 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 6–10 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 6–10 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 6–10 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 6–10 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 6–10 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 6–10 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 6–10 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 6–10 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 6–10 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 6–10 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (11–15)
Maçın 11–15 dakikasında topa sahip olma hangi takımdaydı?,Maçın 11–15 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 11–15 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,maçın 11–15 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 11–15 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 11–15 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 11–15 dakikasında ilk net şut denemesi geldi mi?,Maçın 11–15 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 11–15 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 11–15 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 11–15 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 11–15 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 11–15 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 11–15 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 11–15 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 11–15 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 11–15 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 11–15 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (16–20)
Maçın 16–20 dakikasında topa sahip olma hangi takımdaydı?,Maçın 16–20 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 16–20 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 16–20 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 16–20 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 16–20 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 16–20 dakikasında ilk net şut denemesi geldi mi?,Maçın 16–20 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 16–20 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 16–20 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 16–20 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 16–20 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 16–20 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 16–20 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 16–20 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 16–20 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 16–20 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 16–20 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (21–25)
Maçın 21–25 dakikasında topa sahip olma hangi takımdaydı?,Maçın 21–25 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 21–25 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 21–25 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 21–25 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 21–25 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 21–25 dakikasında ilk net şut denemesi geldi mi?,Maçın 21–25 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 21–25 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 21–25 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 21–25 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 21–25 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 21–25 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 21–25 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 21–25 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 21–25 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 21–25 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 21–25 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (26–30)
Maçın 26–30 dakikasında topa sahip olma hangi takımdaydı?,Maçın 26–30 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 26–30 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 26–30 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 26–30 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 26–30 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 26–30 dakikasında ilk net şut denemesi geldi mi?,Maçın 26–30 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 26–30 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 26–30 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 26–30 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 26–30 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 26–30 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 26–30 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 26–30 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 26–30 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 26–30 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 26–30 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (31–35)
Maçın 31–35 dakikasında topa sahip olma hangi takımdaydı?,Maçın 31–35 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,maçın 31–35 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 31–35 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 31–35 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 31–35 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 31–35 dakikasında ilk net şut denemesi geldi mi?,Maçın 31–35 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 31–35 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 31–35 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 31–35 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 31–35 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 31–35 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 31–35 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 31–35 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 31–35 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 31–35 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 31–35 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (36–40)
Maçın 36–40 dakikasında topa sahip olma hangi takımdaydı?,Maçın 36–40 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 36–40 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 36–40 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 36–40 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 36–40 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 36–40 dakikasında ilk net şut denemesi geldi mi?,Maçın 36–40 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 36–40 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 36–40 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 36–40 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 36–40 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 36–40 dakikasında ilk top kaybı hangi takımda kümelendi?,maçın 36–40 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 36–40 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 36–40 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 36–40 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 36–40 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (41–45)
Maçın 41–45 dakikasında topa sahip olma hangi takımdaydı?,Maçın 41–45 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 41–45 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 41–45 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
maçın 41–45 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 41–45 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 41–45 dakikasında ilk net şut denemesi geldi mi?,Maçın 41–45 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 41–45 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 41–45 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 41–45 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 41–45 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 41–45 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 41–45 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 41–45 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 41–45 dakikasında rakip arkasına koşu denemesi oldu mu?,maçın 41–45 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (46–50)
Maçın 46–50 dakikasında topa sahip olma hangi takımdaydı?,Maçın 46–50 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 46–50 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,maçın 46–50 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 46–50 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 46–50 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 46–50 dakikasında ilk net şut denemesi geldi mi?,Maçın 46–50 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 46–50 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 46–50 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 46–50 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 46–50 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 46–50 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 46–50 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 46–50 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 46–50 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 46–50 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 46–50 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (51–55)
Maçın 51–55 dakikasında topa sahip olma hangi takımdaydı?,Maçın 51–55 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 51–55 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 51–55 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 51–55 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 51–55 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 51–55 dakikasında ilk net şut denemesi geldi mi?,Maçın 51–55 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 51–55 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 51–55 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 51–55 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 51–55 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 51–55 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 51–55 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 51–55 dakikasında savunma hattı hangi takımda daha önde kuruldu?,
Maçın 51–55 dakikasında savunma hattı hangi takımda daha gerideydi?Maçın 51–55 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 51–55 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (56–60)
Maçın 56–60 dakikasında topa sahip olma hangi takımdaydı?,Maçın 56–60 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 56–60 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 56–60 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 56–60 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 56–60 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 56–60 dakikasında ilk net şut denemesi geldi mi?,Maçın 56–60 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 56–60 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 56–60 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 56–60 dakikasında ilk faul hangi takım tarafından yapıldı?
Maçın 56–60 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?,Maçın 56–60 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 56–60 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 56–60 dakikasında savunma hattı hangi takımda daha önde kuruldu?
Maçın 56–60 dakikasında savunma hattı hangi takımda daha gerideydi?,Maçın 56–60 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 56–60 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?
   
SEGMENT SORULARI (61–65)
Maçın 61–65 dakikasında topa sahip olma hangi takımdaydı?,Maçın 61–65 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 61–65 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 61–65 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 61–65 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 61–65 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 61–65 dakikasında ilk net şut denemesi geldi mi?,Maçın 61–65 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 61–65 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 61–65 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 61–65 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 61–65 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 61–65 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 61–65 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 61–65 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 61–65 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 61–65 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 61–65 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (66–70)
Maçın 66–70 dakikasında topa sahip olma hangi takımdaydı?,Maçın 66–70 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 66–70 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 66–70 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 66–70 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 66–70 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 66–70 dakikasında ilk net şut denemesi geldi mi?,Maçın 66–70 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 66–70 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 66–70 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 66–70 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 66–70 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 66–70 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 66–70 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 66–70 dakikasında savunma hattı hangi takımda daha önde kuruldu?Maçın 66–70 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 66–70 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 66–70 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (71–75)
Maçın 71–75 dakikasında topa sahip olma hangi takımdaydı?,Maçın 71–75 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 71–75 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 71–75 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 71–75 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 71–75 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 71–75 dakikasında ilk net şut denemesi geldi mi?,Maçın 71–75 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 71–75 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 71–75 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 71–75 dakikasında ilk faul hangi takım tarafından yapıldı?,
Maçın 71–75 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?Maçın 71–75 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 71–75 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 71–75 dakikasında savunma hattı hangi takımda daha önde kuruldu?
Maçın 71–75 dakikasında savunma hattı hangi takımda daha gerideydi?,Maçın 71–75 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 71–75 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?
    
SEGMENT SORULARI (76–80)
Maçın 76–80 dakikasında topa sahip olma hangi takımdaydı?,Maçın 76–80 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 76–80 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 76–80 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 76–80 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 76–80 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 76–80 dakikasında ilk net şut denemesi geldi mi?,Maçın 76–80 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 76–80 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 76–80 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 76–80 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 76–80 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?
Maçın 76–80 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 76–80 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 76–80 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 76–80 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 76–80 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 76–80 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (81–85)
Maçın 81–85 dakikasında topa sahip olma hangi takımdaydı?,Maçın 81–85 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 81–85 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 81–85 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 81–85 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 81–85 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 81–85 dakikasında ilk net şut denemesi geldi mi?,Maçın 81–85 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 81–85 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 81–85 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 81–85 dakikasında ilk faul hangi takım tarafından yapıldı?
Maçın 81–85 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?Maçın 81–85 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 81–85 dakikasında pas hatası kümelenmesi var mıydı?
Maçın 81–85 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 81–85 dakikasında savunma hattı hangi takımda daha gerideydi?,Maçın 81–85 dakikasında rakip arkasına koşu denemesi oldu mu?
Maçın 81–85 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?

SEGMENT SORULARI (86–90 / UZATMA)
Maçın 86–90 dakikasında topa sahip olma hangi takımdaydı?,Maçın 86–90 dakikasında oyun hangi yarı sahada daha uzun süre oynandı?,Maçın 86–90 dakikasında baskı yoğunluğu hangi takımda daha yüksekti?,Maçın 86–90 dakikasında baskıyı daha hızlı kıran taraf hangi takımdı?
Maçın 86–90 dakikasında ilk baskıyı hangi takım başlattı?,Maçın 86–90 dakikasında baskı sonrası ilk çıkışı hangi takım temiz yaptı?,Maçın 86–90 dakikasında ilk net şut denemesi geldi mi?,Maçın 86–90 dakikasında ilk şut hangi takım tarafından çekildi?
Maçın 86–90 dakikasında ilk korner hangi takım tarafından alındı?,Maçın 86–90 dakikasında ilk tehlikeli duran top oluştu mu?,Maçın 86–90 dakikasında ilk faul hangi takım tarafından yapıldı?,Maçın 86–90 dakikasında faul yoğunluğu “low” mu “mid” mi “high” mıydı?,
Maçın 86–90 dakikasında ilk top kaybı hangi takımda kümelendi?,Maçın 86–90 dakikasında pas hatası kümelenmesi var mıydı?,Maçın 86–90 dakikasında savunma hattı hangi takımda daha önde kuruldu?,Maçın 86–90 dakikasında savunma hattı hangi takımda daha gerideydi?
Maçın 86–90 dakikasında rakip arkasına koşu denemesi oldu mu?,Maçın 86–90 dakikasında rakip arkasına koşu hangi takım tarafından daha çok denendi?  

FAZ-7-1 İlk sarı kart çıktı mı?
İlk sarı kartın dakikası nedir?,İlk sarı kartın dakikası ilk 10 dakikanın içinde mi?,İlk sarı kartın dakikası ilk 15 dakikanın içinde mi?,İlk sarı kartın dakikası ilk yarının son 10 dakikasında mı?,İlk sarı kartın dakikası ikinci yarının ilk 10 dakikasında mı?
İlk sarı kartın dakikası ikinci yarının son 10 dakikasında mı?,İlk sarı kart hangi takım oyuncusuna çıktı?,İlk sarı kart ev sahibi takım oyuncusuna mı çıktı?,İlk sarı kart deplasman takım oyuncusuna mı çıktı?,İlk sarı kart hangi takım lehine verildi?
İlk sarı kart ev sahibi takım lehine mi verildi?,İlk sarı kart deplasman takım lehine mi verildi?,İlk sarı kartı gören oyuncu savunma hattından mıydı?,İlk sarı kartı gören oyuncu orta saha hattından mıydı?,İlk sarı kartı gören oyuncu hücum hattından mıydı?
İlk sarı kart “taktik faul” müydü?,İlk sarı kart “itiraz” nedeniyle mi çıktı?,İlk sarı kart “sinir/agresyon” nedeniyle mi çıktı?,İlk sarı kart “gecikme/time_waste” nedeniyle mi çıktı?,İlk sarı kart “sert müdahale” nedeniyle mi çıktı?
İlk sarı kartın nedeni hakem standardı ile uyumsuz tartışma doğurdu mu?,İlk sarı karttan sonraki ilk 1 dakikada faul yoğunluğu arttı mı?,İlk sarı karttan sonraki ilk 3 dakikada faul yoğunluğu arttı mı?,İlk sarı karttan sonraki 5 dakikada faul yoğunluğu arttı mı?
İlk sarı karttan sonraki 5 dakikada tempo bandı değişti mi?,İlk sarı karttan sonraki 5 dakikada topun oyunda kalma süresi düştü mü?,İlk sarı karttan sonraki 5 dakikada hakem daha fazla düdük çalmaya başladı mı?,İlk sarı karttan sonraki 10 dakikada faul yoğunluğu arttı mı?,İlk sarı karttan sonraki 10 dakikada tempo yükseldi mi?,İlk sarı karttan sonraki 10 dakikada tempo düştü mü?,İlk sarı karttan sonraki 10 dakikada kontrol bandı “unstable” oldu mu?,İlk sarı karttan sonraki 10 dakikada kart riski sinyali arttı mı?
İlk sarı karttan sonraki 10 dakikada ikili mücadele sertliği arttı mı?,Kartların kümelendiği 5 dakikalık blok var mı?,Kartların kümelendiği 10 dakikalık blok var mı?,Kartların kümelendiği ilk 5 dakikalık blok hangi dakikalarda oluştu?

Kartların kümelendiği ilk 10 dakikalık blok hangi dakikalarda oluştu?
Kartlar tek bir takımda mı kümelendi?,Kartlar ev sahibi takımda mı kümelendi?,Kartlar deplasman takımda mı kümelendi?,Kartlar iki takım arasında dengeli mi dağıldı?,Kartlar tek bir oyuncuda mı kümelendi?,Kartlar aynı pozisyon grubunda mı kümelendi?
Kartlar savunma hattında mı kümelendi?,Kartlar orta saha hattında mı kümelendi?,Kartlar hücum hattında mı kümelendi?,Kartlar “itiraz” kaynaklı mı kümelendi?,Kartlar “gecikme/time_waste” kaynaklı mı kümelendi?,Kartlar “sert müdahale” kaynaklı mı kümelendi?
Kartlar kümelenmesi sonrası sonraki 5 dakikada tempo düştü mü?,Kartlar kümelenmesi sonrası sonraki 5 dakikada oyun daha sık durdu mu?,Kartlar kümelenmesi sonrası sonraki 5 dakikada gerilim arttı mı?

FAZ-7-2  Bu maçta kırmızı kart çıktı mı?
Kırmızı kartın dakikası nedir?,Kırmızı kartın dakikası ilk yarıda mı çıktı?,Kırmızı kartın dakikası ikinci yarıda mı çıktı?,Kırmızı kartın dakikası uzatma dakikalarında mı çıktı?,Kırmızı kart hangi takım oyuncusuna çıktı?,Kırmızı kart ev sahibi takım oyuncusuna mı çıktı?,Kırmızı kart deplasman takım oyuncusuna mı çıktı?,Kırmızı kart hangi takım aleyhine verildi?,Kırmızı kart ev sahibi takım aleyhine mi verildi?,Kırmızı kart deplasman takım aleyhine mi verildi?,Kırmızı kart direkt kırmızı mıydı?,Kırmızı kart ikinci sarı sonucu mu oluştu?,Kırmızı kart öncesi 1 dakikada ikinci sarı riski sinyali oluştu mu?,Kırmızı kart öncesi 3 dakikada ikinci sarı riski sinyali oluştu mu?,Kırmızı kart öncesi 5 dakikada ikinci sarı riski sinyali oluştu mu?,Kırmızı kart öncesi 10 dakikada ikinci sarı riski sinyali oluştu mu?,Kırmızı kart öncesi aynı oyuncuda faul tekrarları arttı mı?,Kırmızı kart öncesi aynı oyuncuda tartışma/itiraz sinyali var mıydı?,Kırmızı kart öncesi aynı oyuncu için hakem uyarısı sinyali var mıydı?,Kırmızı kart sonrası ilk 1 dakikada oyun planı aniden değişti mi?,Kırmızı kart sonrası ilk 1 dakikada baskı yönü değişti mi?,Kırmızı kart sonrası ilk 3 dakikada takım boyu kısaldı mı?,Kırmızı kart sonrası ilk 5 dakikada skor değişti mi?,Kırmızı kart sonrası ilk 5 dakikada gol yeme riski belirginleşti mi?
Kırmızı kart sonrası ilk 5 dakikada tempo bandı değişti mi?,Kırmızı kart sonrası ilk 5 dakikada topa sahip olma oranı düştü mü?,Kırmızı kart sonrası ilk 5 dakikada rakip ceza sahasına giriş sayısı arttı mı?,Kırmızı kart sonrası takım “tempo_down + deep_defend” kombinasyonuna mı girdi?,Kırmızı kart sonrası takım “risk_down” moduna mı geçti?,Kırmızı kart sonrası takım “chaos” moduna mı girdi?,Kırmızı kart sonrası takım organize mi kaldı?,Kırmızı kart sonrası takım çöktü mü?,Kırmızı kart sonrası ilk 10 dakikada savunma hataları arttı mı?,Kırmızı kart gören takım 10 kişi kalınca baskı yönü değişti mi?,Kırmızı kart gören takım 10 kişi kalınca net pozisyon verdi mi?,Kırmızı kart gören takım 10 kişi kalınca duran top tehdidi arttı mı?,Kırmızı kart gören takım 10 kişi kalınca kontra atak planına mı döndü?,Kırmızı kart sonrası sonraki 5 dakikada rakip gol buldu mu?,Kırmızı kart sonrası sonraki 10 dakikada rakip gol buldu mu?

FAZ-7-3 Var incelemesi oldumu ?
Maçta VAR incelemesi ilk yarıda oldu mu?,Maçta VAR incelemesi ikinci yarıda oldu mu?,Maçta VAR incelemesi uzatma dakikalarında oldu mu?
VAR incelemesi 0–15 aralığında oldu mu?,VAR incelemesi 16–30 aralığında oldu mu?,VAR incelemesi 31–45+ aralığında oldu mu?,VAR incelemesi 46–60 aralığında oldu mu?,VAR incelemesi 61–75 aralığında oldu mu?,VAR incelemesi 76–90+ aralığında oldu mu?
VAR incelemesi sonrası karar değişikliği ilk yarıda yaşandı mı?,VAR incelemesi sonrası karar değişikliği ikinci yarıda yaşandı mı?,VAR incelemesi sonrası karar değişikliği 0–15 aralığında yaşandı mı?
VAR incelemesi sonrası karar değişikliği 16–30 aralığında yaşandı mı?,VAR incelemesi sonrası karar değişikliği 31–45+ aralığında yaşandı mı?,VAR incelemesi sonrası karar değişikliği 46–60 aralığında yaşandı mı?
VAR incelemesi sonrası karar değişikliği 61–75 aralığında yaşandı mı?,VAR incelemesi sonrası karar değişikliği 76–90+ aralığında yaşandı mı?,VAR incelemesi sonrası oyun ritmi kırılması ilk 1 dakikada oldu mu?
VAR incelemesi sonrası oyun ritmi kırılması ilk 1–3 dakikada oldu mu?,VAR incelemesi sonrası oyun ritmi kırılması ilk 3–5 dakikada oldu mu?,VAR incelemesi sonrası oyun ritmi kırılması sonraki 5–10 dakikada sürdü mü?
VAR incelemesi sonrası tempo bandı “tempo_down” ilk 1–3 dakikada oluştu mu?,VAR incelemesi sonrası tempo bandı “tempo_down” ilk 3–5 dakikada oluştu mu?,VAR incelemesi sonrası tempo bandı “tempo_down” sonraki 5 dakikada devam etti mi?
VAR incelemesi sonrası faul yoğunluğu ilk 1–3 dakikada arttı mı?,VAR incelemesi sonrası faul yoğunluğu ilk 3–5 dakikada arttı mı?,VAR incelemesi sonrası faul yoğunluğu sonraki 5 dakikada arttı mı?
VAR incelemesi sonrası kart yoğunluğu ilk 1–3 dakikada arttı mı?,VAR incelemesi sonrası kart yoğunluğu ilk 3–5 dakikada arttı mı?,VAR incelemesi sonrası kart yoğunluğu sonraki 5 dakikada arttı mı?
VAR incelemesi sonrası oyuncu itirazı ilk 1–3 dakikada kümelendi mi?,VAR incelemesi sonrası oyuncu itirazı ilk 3–5 dakikada kümelendi mi?,VAR incelemesi sonrası oyuncu itirazı sonraki 5 dakikada sürdü mü?
VAR incelemesi sonrası kontrol bandı “unstable” ilk 1–3 dakikada oluştu mu?,VAR incelemesi sonrası kontrol bandı “unstable” ilk 3–5 dakikada oluştu mu?,VAR incelemesi sonrası kontrol bandı “unstable” sonraki 5 dakikada devam etti mi?
VAR incelemesi ev sahibi lehine mi yapıldı?,VAR incelemesi deplasman lehine mi yapıldı?,VAR incelemesi gol kararı için mi yapıldı?,VAR incelemesi penaltı kararı için mi yapıldı?,VAR incelemesi kırmızı kart kararı için mi yapıldı?
VAR incelemesi ofsayt kararı için mi yapıldı?,VAR incelemesi sırasında oyuncular hakeme toplu itiraz etti mi?,VAR incelemesi sırasında teknik direktör itirazı görüldü mü?,VAR incelemesi sırasında saha kenarı gerilimi arttı mı?
VAR incelemesi sonrası maç tekrar başladığında ilk 60 saniyede faul oldu mu?,VAR incelemesi sonrası maç tekrar başladığında ilk 60 saniyede kart çıktı mı?,VAR incelemesi sonrası maç tekrar başladığında ilk 60 saniyede top kaybı arttı mı?   
VAR incelemesi sonrası maç tekrar başladığında ilk 60 saniyede şut denemesi oldu mu?,VAR incelemesi sonrası maç tekrar başladığında ilk 5 dakikada baskı yönü değişti mi?

FAZ-7-4 Peneltı pozüsyonu oldumu ?
Penaltı ev sahibi lehine mi verildi?,Penaltı deplasman lehine mi verildi?,Penaltı kararı VAR ile mi verildi?,Penaltı kararı VAR sonrası mı iptal edildi?,Maçta penaltı pozisyonu ilk yarıda yaşandı mı?,Maçta penaltı pozisyonu ikinci yarıda yaşandı mı?
Maçta penaltı pozisyonu uzatma dakikalarında yaşandı mı?,Penaltı pozisyonu 0–15 aralığında yaşandı mı?,Penaltı pozisyonu 16–30 aralığında yaşandı mı?,Penaltı pozisyonu 31–45+ aralığında yaşandı mı?,Penaltı pozisyonu 46–60 aralığında yaşandı mı?
Penaltı pozisyonu 61–75 aralığında yaşandı mı?,Penaltı pozisyonu 76–90+ aralığında yaşandı mı?,Penaltı iptali sonrası 1 dakikalık itiraz kümelenmesi oldu mu?,Penaltı iptali sonrası 1–3 dakikalık itiraz kümelenmesi oldu mu?
Penaltı iptali sonrası 3–5 dakikalık itiraz kümelenmesi oldu mu?,Penaltı kararı sonrası ilk 1 dakikada psikolojik kırılma oluştu mu?,Penaltı kararı sonrası 1–3 dakikalık psikolojik kırılma oluştu mu?,Penaltı kararı sonrası 3–5 dakikalık psikolojik kırılma oluştu mu?
Penaltı kararı sonrası ilk 5 dakikada tempo bandı değişti mi?,Penaltı kararı sonrası sonraki 5 dakikada tempo bandı değişti mi?,Penaltı kararı sonrası ilk 5 dakikada disiplin bandı bozuldu mu?,Penaltı kararı sonrası sonraki 5 dakikada disiplin bandı bozuldu mu?
Penaltı kararı sonrası geriye düşen takım ilk 1–3 dakikada “panic” bandına girdi mi?,Penaltı kararı sonrası geriye düşen takım 3–5 dakikada “panic” bandına girdi mi?,Penaltı kararı sonrası geriye düşen takım sonraki 5 dakikada “panic” bandında kaldı mı?
Penaltı kararı sonrası öne geçen takım ilk 1–3 dakikada time-waste davranışına geçti mi?,Penaltı kararı sonrası öne geçen takım 3–5 dakikada time-waste davranışına geçti mi?,Penaltı kararı sonrası öne geçen takım sonraki 5 dakikada time-waste davranışını sürdürdü mü?
Penaltı kararı sonrası ilk 5 dakikada faul yoğunluğu arttı mı?,Penaltı kararı sonrası ilk 5 dakikada kart yoğunluğu arttı mı?,Penaltı kararı sonrası ilk 5 dakikada kontrol bandı “unstable” oldu mu?,Penaltı sonrası yeniden başlama anında ilk 60 saniyede faul oldu mu?
Penaltı sonrası yeniden başlama anında ilk 60 saniyede kart çıktı mı?,Penaltı sonrası yeniden başlama anında ilk 60 saniyede baskı yönü değişti mi?,Penaltı sonrası yeniden başlama anında ilk 5 dakikada baskı artışı oldu mu?    

FAZ-7-5 Maçta gol iptali varmı ?
Maçta iptal edilen gol ilk yarıda oldu mu?,Maçta iptal edilen gol ikinci yarıda oldu mu?,Maçta iptal edilen gol uzatma dakikalarında oldu mu?,İptal edilen gol 0–15 aralığında oldu mu?,İptal edilen gol 16–30 aralığında oldu mu?,İptal edilen gol 31–45+ aralığında oldu mu?,İptal edilen gol 46–60 aralığında oldu mu?,İptal edilen gol 61–75 aralığında oldu mu?,İptal edilen gol 76–90+ aralığında oldu mu?,İptal edilen gol ev sahibi için miydi?,İptal edilen gol deplasman için miydi?,İptal edilen gol ofsayt gerekçesiyle mi iptal edildi?İptal edilen gol faul gerekçesiyle mi iptal edildi?,İptal edilen gol elle oynama gerekçesiyle mi iptal edildi?,İptal edilen gol VAR incelemesi sonrası mı iptal edildi?,İptal edilen gol sonrası ilk 1 dakikada itiraz kümesi oldu mu?,İptal edilen gol sonrası ilk 1–3 dakikada itiraz kümesi oldu mu?,İptal edilen gol sonrası 3–5 dakikada itiraz kümesi oldu mu?,İptal edilen gol sonrası ilk 1–3 dakikada takım “fight_harder” bandına geçti mi?,İptal edilen gol sonrası 3–5 dakikada takım “fight_harder” bandına geçti mi?,İptal edilen gol sonrası sonraki 5 dakikada takım “fight_harder” bandında kaldı mı?,İptal edilen gol sonrası ilk 1–3 dakikada takım “collapse” bandına geçti mi?,iptal edilen gol sonrası 3–5 dakikada takım “collapse” bandına geçti mi?,İptal edilen gol sonrası sonraki 5 dakikada takım “collapse” bandında kaldı mı?,İptal edilen gol sonrası ilk 5 dakikada kart yoğunluğu arttı mı?,İptal edilen gol sonrası ilk 5 dakikada faul yoğunluğu arttı mı?,İptal edilen gol sonrası ilk 5 dakikada tempo bandı değişti mi?,İptal edilen gol sonrası sonraki 5 dakikada tempo bandı değişti mi?,İptal edilen gol sonrası ilk 5 dakikada kontrol bandı “unstable” oldu mu?,İptal edilen gol sonrası sonraki 5 dakikada kontrol bandı “unstable” kaldı mı?,İptal edilen gol sonrası iptal kararına teknik direktör itirazı oldu mu?,İptal edilen gol sonrası oyuncu itirazı toplu halde mi gerçekleşti?,İptal edilen gol sonrası maç yeniden başladığında ilk 60 saniyede faul oldu mu?,İptal edilen gol sonrası maç yeniden başladığında ilk 60 saniyede kart çıktı mı?,İptal edilen gol sonrası maç yeniden başladığında ilk 60 saniyede tempo düşüşü oldu mu?,İptal edilen gol sonrası maç yeniden başladığında ilk 5 dakikada baskı yönü değişti mi?

FA-7-6- İlk gol geldi mi?
İlk gol hangi dakikada geldi?,İlk gol öncesi 1 dakikada tempo bandı değişmiş miydi?,İlk gol öncesi 3 dakikada tempo bandı değişmiş miydi?,İlk gol öncesi 5 dakikada tempo bandı değişmiş miydi?,İlk gol öncesi 1 dakikada net pozisyon artışı var mıydı?
İlk gol öncesi 3 dakikada net pozisyon artışı var mıydı?,İlk gol öncesi 5 dakikada net pozisyon artışı var mıydı?,İlk gol öncesi 1 dakikada baskı yönü değişmiş miydi?,İlk gol öncesi 3 dakikada baskı yönü değişmiş miydi?,İlk gol öncesi 5 dakikada baskı yönü değişmiş miydi?,İlk gol öncesi son 5 dakikada duran top yoğunluğu artmış mıydı?,İlk gol öncesi son 5 dakikada korner yoğunluğu artmış mıydı?,İlk gol öncesi son 5 dakikada serbest vuruş tehlikesi artmış mıydı?,İlk gol öncesi son 5 dakikada ceza sahası içi temaslar arttı mı?
İlk gol öncesi son 5 dakikada şut sayısı artmış mıydı?,İlk gol öncesi son 5 dakikada isabetli şut artışı var mıydı?,İlk gol öncesi son 5 dakikada kaleci kurtarışları arttı mı?,İlk gol öncesi son 5 dakikada top kaybı yoğunluğu arttı mı?,İlk gol öncesi son 5 dakikada savunma yerleşim hatası tekrar etti mi?,İlk gol öncesi son 5 dakikada hızlı hücum denemeleri arttı mı?,İlk gol öncesi son 5 dakikada geçiş oyunu belirginleşti mi?,İlk gol öncesi son 5 dakikada pres şiddeti yükseldi mi?İlk gol öncesi son 5 dakikada pres şiddeti düştü mü?,İlk gol öncesi son 5 dakikada pas hızı arttı mı?,İlk gol öncesi son 5 dakikada pas hızı düştü mü?

FAZ-7-7,İlk golü hangi takım attı?
İlk golü atan takım gol öncesi 5 dakikada baskıyı artırmış mıydı?,ilk golü atan takım gol öncesi 5 dakikada risk seviyesini yükseltmiş miydi?,İlk golü yiyen takım gol öncesi 5 dakikada savunma çizgisini geriye mi çekti?,İlk golü yiyen takım gol öncesi 5 dakikada top kayıplarını artırdı mı?,İlk golden sonra geriye düşen takımın tempo bandı yükseldi mi?,İlk golden sonra geriye düşen takımın tempo bandı düştü mü?,İlk golden sonra geriye düşen takım “risk_up” moduna geçti mi?,İlk golden sonra geriye düşen takım ilk 1 dakikada baskıyı artırdı mı?,İlk golden sonra geriye düşen takım ilk 3 dakikada baskıyı artırdı mı?,İlk golden sonra geriye düşen takım ilk 5 dakikada baskıyı artırdı mı?,İlk golden sonra geriye düşen takım ilk 1 dakikada net pozisyon üretti mi?,İlk golden sonra geriye düşen takım ilk 3 dakikada net pozisyon üretti mi?,İlk golden sonra geriye düşen takım ilk 5 dakikada net pozisyon üretti mi?,İlk golden sonra geriye düşen takım ilk 5 dakikada daha fazla şut çekti mi?,İlk golden sonra geriye düşen takım ilk 5 dakikada topa sahip olmayı artırdı mı?
İlk golden sonra geriye düşen takım ilk 5 dakikada geçiş hücumuna mı döndü?,İlk golden sonra geriye düşen takım ilk 5 dakikada uzun topa mı döndü?,İlk golden sonra geriye düşen takım ilk 5 dakikada kanat ortalarını artırdı mı?,İlk golden sonra geriye düşen takım ilk 5 dakikada ceza sahasına girişleri artırdı mı?,İlk golden sonra öne geçen takımın tempo bandı düştü mü?,İlk golden sonra öne geçen takım “risk_down” moduna geçti mi?,İlk golden sonra öne geçen takım time-waste davranışına geçti mi?,İlk golden sonra öne geçen takım ilk 1 dakikada tempo bandını düşürdü mü?,İlk golden sonra öne geçen takım ilk 3 dakikada tempo bandını düşürdü mü?,İlk golden sonra öne geçen takım ilk 5 dakikada tempo bandını düşürdü mü?,İlk golden sonra öne geçen takım ilk 5 dakikada topu tutma moduna geçti mi?
İlk golden sonra öne geçen takım ilk 5 dakikada presi geri mi çekti?,İlk golden sonra öne geçen takım ilk 5 dakikada savunma çizgisini geri mi çekti?,İlk golden sonra öne geçen takım ilk 5 dakikada hızlı hücum kovaladı mı?,İlk golden sonra öne geçen takım ilk 5 dakikada kontra tehdit üretti mi?,İlk golden sonra öne geçen takım ilk 5 dakikada duran top kovaladı mı?,İlk golden sonra baskı yönü değişti mi?,İlk golden sonra ilk 1 dakikada baskı yönü değişti mi?,İlk golden sonra ilk 3 dakikada baskı yönü değişti mi?,İlk golden sonra ilk 5 dakikada baskı yönü değişti mi?,İlk golden sonra 5–10 dakikada baskı yönü değişti mi?

FAZ-7-8,,Beraberlik golü geldi mi?,Beraberlik golü hangi dakikada geldi?
Beraberlik golü öncesi 1 dakikada tempo bandı değişti mi?,Beraberlik golü öncesi 3 dakikada tempo bandı değişti mi?,Beraberlik golü öncesi 5 dakikada tempo bandı değişti mi?,Beraberlik golü öncesi 1 dakikada baskı yönü değişti mi?,Beraberlik golü öncesi 3 dakikada baskı yönü değişti mi?,Beraberlik golü öncesi 5 dakikada baskı yönü değişti mi?,Beraberlik golü öncesi 5 dakikada kart/faul yoğunluğu arttı mı?,Beraberlik golü öncesi 5 dakikada net pozisyon artışı var mıydı?,Beraberlik golünden sonraki 5 dakikada baskı yönü değişti mi?,Beraberlik golünden sonraki 10 dakikada baskı yönü değişti mi?,Beraberlik golünden sonraki 5 dakikada tempo bandı değişti mi?,Beraberlik golünden sonraki 10 dakikada tempo bandı değişti mi?,Beraberlik golünden sonraki 5 dakikada kart/faul yoğunluğu arttı mı?
Beraberlik golünden sonraki 10 dakikada kart/faul yoğunluğu arttı mı?,Beraberlik golünden sonraki 5 dakikada net pozisyon sayısı arttı mı?,Beraberlik golünden sonraki 10 dakikada net pozisyon sayısı arttı mı?,Beraberlik golünden sonraki 5 dakikada “risk_up” moduna geçen takım oldu mu?,Beraberlik golünden sonraki 10 dakikada “risk_down” moduna geçen takım oldu mu?,Beraberlik golünden sonraki 5 dakikada time-waste davranışı başladı mı?
Beraberlik golünden sonraki 10 dakikada time-waste davranışı başladı mı?

FAZ-7-9
Kopma golü geldi mi?,Kopma golü hangi dakikada geldi?,Kopma golü öncesi 1 dakikada tempo bandı değişti mi?,Kopma golü öncesi 3 dakikada tempo bandı değişti mi?,Kopma golü öncesi 5 dakikada tempo bandı değişti mi?,Kopma golü öncesi 5 dakikada net pozisyon artışı var mıydı?,Kopma golü öncesi 5 dakikada baskı yönü değişti mi? 
FAZ-7-10
İlk golden sonra geriye düşen takımın tempo bandı yükseldi mi?,İlk golden sonra geriye düşen takımın tempo bandı düştü mü?,İlk golden sonra geriye düşen takım “risk_up” moduna geçti mi?,ilk golden sonra geriye düşen takım ilk 1 dakikada baskıyı artırdı mı?
İlk golden sonra geriye düşen takım ilk 3 dakikada baskıyı artırdı mı?,İlk golden sonra geriye düşen takım ilk 5 dakikada baskıyı artırdı mı?,İlk golden sonra geriye düşen takım ilk 1 dakikada net pozisyon üretti mi?
İlk golden sonra geriye düşen takım ilk 3 dakikada net pozisyon üretti mi?,İlk golden sonra geriye düşen takım ilk 5 dakikada net pozisyon üretti mi?,İlk golden sonra geriye düşen takım ilk 5 dakikada daha fazla şut çekti mi?
İlk golden sonra geriye düşen takım ilk 5 dakikada topa sahip olmayı artırdı mı?,İlk golden sonra geriye düşen takım ilk 5 dakikada geçiş hücumuna mı döndü?,İlk golden sonra geriye düşen takım ilk 5 dakikada uzun topa mı döndü?
İlk golden sonra geriye düşen takım ilk 5 dakikada kanat ortalarını artırdı mı?,İlk golden sonra geriye düşen takım ilk 5 dakikada ceza sahasına girişleri artırdı mı?,İlk golden sonra öne geçen takımın tempo bandı düştü mü?
İlk golden sonra öne geçen takım “risk_down” moduna geçti mi?,İlk golden sonra öne geçen takım time-waste davranışına geçti mi?,İlk golden sonra öne geçen takım ilk 1 dakikada tempo bandını düşürdü mü?
İlk golden sonra öne geçen takım ilk 3 dakikada tempo bandını düşürdü mü?,İlk golden sonra öne geçen takım ilk 5 dakikada tempo bandını düşürdü mü?,İlk golden sonra öne geçen takım ilk 5 dakikada topu tutma moduna geçti mi?,
İlk golden sonra öne geçen takım ilk 5 dakikada presi geri mi çekti?,ilk golden sonra öne geçen takım ilk 5 dakikada savunma çizgisini geri mi çekti?,ilk golden sonra öne geçen takım ilk 5 dakikada hızlı hücum kovaladı mı?
İlk golden sonra öne geçen takım ilk 5 dakikada kontra tehdit üretti mi?,İlk golden sonra öne geçen takım ilk 5 dakikada duran top kovaladı mı?,İlk golden sonra baskı yönü değişti mi?,İlk golden sonra ilk 1 dakikada baskı yönü değişti mi?
İlk golden sonra ilk 3 dakikada baskı yönü değişti mi?,İlk golden sonra ilk 5 dakikada baskı yönü değişti mi?,İlk golden sonra 5–10 dakikada baskı yönü değişti mi?

FAZ-7-11,,Beraberlik golü geldi mi?,Beraberlik golü hangi dakikada geldi?
Beraberlik golü öncesi 1 dakikada tempo bandı değişti mi?,Beraberlik golü öncesi 3 dakikada tempo bandı değişti mi?,Beraberlik golü öncesi 5 dakikada tempo bandı değişti mi?,Beraberlik golü öncesi 1 dakikada baskı yönü değişti mi?
Beraberlik golü öncesi 3 dakikada baskı yönü değişti mi?,Beraberlik golü öncesi 5 dakikada baskı yönü değişti mi?,Beraberlik golü öncesi 5 dakikada kart/faul yoğunluğu arttı mı?,Beraberlik golü öncesi 5 dakikada net pozisyon artışı var mıydı?
Beraberlik golünden sonraki 5 dakikada baskı yönü değişti mi?,Beraberlik golünden sonraki 10 dakikada baskı yönü değişti mi?,Beraberlik golünden sonraki 5 dakikada tempo bandı değişti mi?,Beraberlik golünden sonraki 10 dakikada tempo bandı değişti mi?
Beraberlik golünden sonraki 5 dakikada kart/faul yoğunluğu arttı mı?,Beraberlik golünden sonraki 10 dakikada kart/faul yoğunluğu arttı mı?,Beraberlik golünden sonraki 5 dakikada net pozisyon sayısı arttı mı?,Beraberlik golünden sonraki 10 dakikada net pozisyon sayısı arttı mı?Beraberlik golünden sonraki 5 dakikada “risk_up” moduna geçen takım oldu mu?,Beraberlik golünden sonraki 10 dakikada “risk_down” moduna geçen takım oldu mu?,Beraberlik golünden sonraki 5 dakikada time-waste davranışı başladı mı?
Beraberlik golünden sonraki 10 dakikada time-waste davranışı başladı mı?

FAZ-7-12,Kopma golü geldi mi?,Kopma golü hangi dakikada geldi?,Kopma golü öncesi 1 dakikada tempo bandı değişti mi?,Kopma golü öncesi 3 dakikada tempo bandı değişti mi?,Kopma golü öncesi 5 dakikada tempo bandı değişti mi?,Kopma golü öncesi 5 dakikada baskı yönü değişti mi?,Kopma golü öncesi 5 dakikada net pozisyon artışı var mıydı?

FAZ-7-13,Oyun sık sık taça gittiği blok hangi 5 dakikalık penceredeydi?,Maçta aut/taç bandı için oyun sık sık taça gitti mi?,Maçta aut/taç bandı için tempo düşüşü oluşturdu mu?
Taç yoğunluğu sonrası 1 dakikada tempo bandı düştü mü?,Taç yoğunluğu sonrası 3 dakikada tempo bandı düştü mü?,Taç yoğunluğu sonrası 5 dakikada tempo bandı düştü mü?,Taç yoğunluğu sonrası baskı yönü değişti mi?,Taç yoğunluğu sonrası topa sahip olma taraf değiştirdi mi?

FAZ-7-14
Bu maçta kaleci ilk 5 dakikada büyük hata yaptı mı?,Bu maçta kaleci ilk 10 dakikada büyük hata yaptı mı?,Bu maçta kaleci 15–30 aralığında büyük hata yaptı mı?,Bu maçta kaleci 30–45 aralığında büyük hata yaptı mı?,Bu maçta kaleci 45–60 aralığında büyük hata yaptı mı?,Bu maçta kaleci 60–75 aralığında büyük hata yaptı mı?,Bu maçta kaleci 75–90 aralığında büyük hata yaptı mı?,Kalecinin büyük hatası hangi dakikada oldu?,Kalecinin büyük hatası sonrası sonraki 5 dakikada rakip baskı bandı yükseldi mi?
Kalecinin büyük hatası sonrası sonraki 5 dakikada takım panik bandına girdi mi?,Kalecinin büyük hatası sonrası sonraki 5 dakikada takım tempo bandı düştü mü?,Bu maçta kaleci ilk 5 dakikada kritik kurtarış yaptı mı?,Bu maçta kaleci ilk 10 dakikada kritik kurtarış yaptı mı?Bu maçta kaleci 15–30 aralığında kritik kurtarış yaptı mı?,Bu maçta kaleci 30–45 aralında kritik kurtarış yaptı mı?,Bu maçta kaleci 45–60 aralığında kritik kurtarış yaptı mı?,Bu maçta kaleci 60–75 aralığında kritik kurtarış yaptı mı?,Bu maçta kaleci 75–90 aralığında kritik kurtarış yaptı mı?,Kalecinin kritik kurtarışı hangi dakikada oldu?,Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım tempo bandı yükseldi mi?,Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım moral bandı yükseldi mi?

Bu maçta kaleci kurtarış serisi ilk 15 dakikada oluştu mu?,Bu maçta kaleci kurtarış serisi 15–30 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 30–45 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 45–60 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 60–75 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 75–90 aralığında oluştu mu?
Kalecinin kurtarış serisi hangi dakikalar arasında gerçekleşti?,Kaleci kurtarış serisi sonrası sonraki 5 dakikada takım kontrol bandı yükseldi mi?Kaleci kurtarış serisi sonrası sonraki 5 dakikada rakip tempo bandı düştü mü?
Bu maçta kaleci zaman geçirme davranışına ilk 15 dakikada girdi mi?,Bu maçta kaleci zaman geçirme davranışına 30–45 aralığında girdi mi?,Bu maçta kaleci zaman geçirme davranışına 60–75 aralığında girdi mi?,Bu maçta kaleci zaman geçirme davranışına 75–90 aralığında girdi mi?,Kalecinin zaman geçirme davranışı hangi dakikada başladı?,Kalecinin zaman geçirme davranışı hangi dakikada bitti?,Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada maç temposu düştü mü?
Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi?,Bu maçta kaleci sakatlık/duraklama ile ritmi ilk yarıda bozdu mu?,Bu maçta kaleci sakatlık/duraklama ile ritmi ikinci yarıda bozdu mu?
Kalecinin sakatlık/duraklaması hangi dakikada oldu?,Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada takım baskı bandı düştü mü?,Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada rakip baskı bandı düştü mü?
Bu maçta kalecinin uzun oyun kurma tercihi ilk 15 dakikada belirginleşti mi?,Bu maçta kalecinin uzun oyun kurma tercihi 15–30 aralığında belirginleşti mi?,Bu maçta kalecinin uzun oyun kurma tercihi 60–75 aralığında belirginleşti mi?
Kalecinin uzun oyun kurma tercihi hangi dakikada belirginleşti?,Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi?,Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada ikinci top kazanımı arttı mı?
     
Bu maçta kaleci ilk 5 dakikada büyük hata yaptı mı?,Bu maçta kaleci ilk 10 dakikada büyük hata yaptı mı?,Bu maçta kaleci 15–30 aralığında büyük hata yaptı mı?,Bu maçta kaleci 30–45 aralığında büyük hata yaptı mı?,Bu maçta kaleci 45–60 aralığında büyük hata yaptı mı?
Bu maçta kaleci 60–75 aralığında büyük hata yaptı mı?,Bu maçta kaleci 75–90 aralığında büyük hata yaptı mı?,Kalecinin büyük hatası hangi dakikada oldu?,Kalecinin büyük hatası sonrası sonraki 5 dakikada rakip baskı bandı yükseldi mi?,kalecinin büyük hatası sonrası sonraki 5 dakikada takım panik bandına girdi mi?,Kalecinin büyük hatası sonrası sonraki 5 dakikada takım tempo bandı düştü mü?
Bu maçta kaleci ilk 5 dakikada kritik kurtarış yaptı mı?,Bu maçta kaleci ilk 10 dakikada kritik kurtarış yaptı mı?,Bu maçta kaleci 15–30 aralığında kritik kurtarış yaptı mı?,Bu maçta kaleci 30–45 aralında kritik kurtarış yaptı mı?
Bu maçta kaleci 45–60 aralığında kritik kurtarış yaptı mı?,Bu maçta kaleci 60–75 aralığında kritik kurtarış yaptı mı?,Bu maçta kaleci 75–90 aralığında kritik kurtarış yaptı mı?
Kalecinin kritik kurtarışı hangi dakikada oldu?,Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım tempo bandı yükseldi mi?,Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım moral bandı yükseldi mi?
Bu maçta kaleci kurtarış serisi ilk 15 dakikada oluştu mu?,Bu maçta kaleci kurtarış serisi 15–30 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 30–45 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 45–60 aralığında oluştu mu?
Bu maçta kaleci kurtarış serisi 60–75 aralığında oluştu mu?,Bu maçta kaleci kurtarış serisi 75–90 aralığında oluştu mu?,Kalecinin kurtarış serisi hangi dakikalar arasında gerçekleşti?,Kaleci kurtarış serisi sonrası sonraki 5 dakikada takım kontrol bandı yükseldi mi?
Kaleci kurtarış serisi sonrası sonraki 5 dakikada rakip tempo bandı düştü mü?

Bu maçta kaleci zaman geçirme davranışına ilk 15 dakikada girdi mi?,Bu maçta kaleci zaman geçirme davranışına 30–45 aralığında girdi mi?,Bu maçta kaleci zaman geçirme davranışına 60–75 aralığında girdi mi?,Bu maçta kaleci zaman geçirme davranışına 75–90 aralığında girdi mi?,Kalecinin zaman geçirme davranışı hangi dakikada başladı?,Kalecinin zaman geçirme davranışı hangi dakikada bitti?,Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada maç temposu düştü mü?,Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi?,Bu maçta kalecinin sakatlık/duraklama ile ritmi ilk yarıda bozdu mu?,Bu maçta kalecinin sakatlık/duraklama ile ritmi ikinci yarıda bozdu mu?,Kalecinin sakatlık/duraklaması hangi dakikada oldu?
Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada takım baskı bandı düştü mü?,Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada rakip baskı bandı düştü mü?,Bu maçta kalecinin uzun oyun kurma tercihi ilk 15 dakikada belirginleşti mi?
Bu maçta kalecinin uzun oyun kurma tercihi 15–30 aralığında belirginleşti mi?,Bu maçta kalecinin uzun oyun kurma tercihi 60–75 aralığında belirginleşti mi?
alecinin uzun oyun kurma tercihi hangi dakikada belirginleşti?,Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi?,Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada ikinci top kazanımı arttı mı?
Bu maçta kalecinin kısa oyun kurma tercihi ilk 15 dakikada belirginleşti mi?,Bu maçta kalecinin kısa oyun kurma tercihi 15–30 aralığında belirginleşti mi?,Bu maçta kalecinin kısa oyun kurma tercihi 60–75 aralığında belirginleşti mi?
Kalecinin kısa oyun kurma tercihi hangi dakikada belirginleşti?,Kalecinin kısa oyun kurma tercihi sonrası sonraki 5 dakikada baskı altında top kaybı arttı mı?,Kalecinin kısa oyun kurma tercihi sonrası sonraki 5 dakikada rakip pres bandı yükseldi mi?

FAZ-7-15
Bu maçta forvet ilk 10 dakikada net pozisyon kaçırdı mı?,Bu maçta forvet 10–20 aralığında net pozisyon kaçırdı mı?,Bu maçta forvet 20–30 aralığında net pozisyon kaçırdı mı?,Bu maçta forvet 30–45 aralığında net pozisyon kaçırdı mı?
Bu maçta forvet 45–60 aralığında net pozisyon kaçırdı mı?,Bu maçta forvet 60–75 aralığında net pozisyon kaçırdı mı?,Bu maçta forvet 75–90 aralığında net pozisyon kaçırdı mı?,Forvetin net pozisyon kaçırması hangi dakikada oldu?
Forvetin net pozisyon kaçırması sonrası sonraki 5 dakikada takım panik bandı yükseldi mi?,Forvetin net pozisyon kaçırması sonrası sonraki 5 dakikada takım tempo bandı düştü mü?
Bu maçta forvet art arda net pozisyon kaçırması ilk yarıda oldu mu?,Bu maçta forvet art arda net pozisyon kaçırması ikinci yarıda oldu mu?,Forvetin art arda net pozisyon kaçırması hangi dakikalar arasında oldu?
Forvetin art arda net pozisyon kaçırması sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi?,Forvetin art arda net pozisyon kaçırması sonrası sonraki 5 dakikada takım risk_up moduna geçti mi?
Bu maçta forvet baskı yükselince ilk yarıda kart/faul eğilimi arttı mı?,Bu maçta forvet baskı yükselince ikinci yarıda kart/faul eğilimi arttı mı?
Forvet baskı yükselince kart/faul eğilimi hangi dakikada belirginleşti?,Forvetin kart/faul eğilimi sonrası sonraki 5 dakikada takım oyun akışı kesildi mi?
Bu maçta forvet baskı yükselince ilk yarıda itiraz dili sertleşti mi?,Bu maçta forvet baskı yükselince ikinci yarıda itiraz dili sertleşti mi?
Forvetin itiraz dili hangi dakikada sertleşti?,Forvetin itiraz dili sertleşince sonraki 5 dakikada kart riski yükseldi mi?,Bu maçta forvet iptal gol sonrası ilk 5 dakikada mental olarak unstable’a döndü mü?,
Bu maçta forvet iptal gol sonrası sonraki 15 dakikada mental olarak unstable’a döndü mü?

Forvetin iptal gol sonrası mental kırılma anı hangi dakikada oldu?
Forvet iptal gol sonrası sonraki 5 dakikada net pozisyon üretimi düştü mü?
Bu maçta forvet VAR sonrası ilk 5 dakikada mental olarak unstable’a döndü mü?
Bu maçta forvet VAR sonrası sonraki 15 dakikada mental olarak unstable’a döndü mü?
Forvetin VAR sonrası mental kırılma anı hangi dakikada oldu?
Forvet VAR sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi?
Bu maçta forvet penaltı kaçırdı mı?

Forvet penaltıyı hangi dakikada kaçırdı?
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada takım tempo bandı düştü mü?
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada takım risk_up moduna geçti mi?
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi?
Bu maçta forvet oyundan ilk yarıda çıktı mı?
Bu maçta forvet oyundan ikinci yarıda çıktı mı?

Forvet hangi dakikada oyundan çıktı?
Forvet oyundan çıkış nedeni taktik mi?
Forvet oyundan çıkış nedeni sakatlık mı?
Forvet oyundan çıkınca sonraki 5 dakikada takım net pozisyon üretimi düştü mü?
Forvet oyundan çıkınca sonraki 5 dakikada takım pres bandı düştü mü?

FAZ-7-16
Bu maçta orta sahada top kaybı ilk 15 dakikada kümelendi mi?
Bu maçta orta sahada top kaybı 15–30 aralığında kümelendi mi?
Bu maçta orta sahada top kaybı 30–45 aralığında kümelendi mi?
Bu maçta orta sahada top kaybı 45–60 aralığında kümelendi mi?
Bu maçta orta sahada top kaybı 60–75 aralığında kümelendi mi?
Bu maçta orta sahada top kaybı 75–90 aralığında kümelendi mi?
Orta saha top kaybı hangi dakikada başladı?
Orta saha top kaybı hangi dakikada bitti?

Orta saha top kaybı sonrası sonraki 5 dakikada momentum flip yaşandı mı?
Orta saha top kaybı sonrası sonraki 5 dakikada rakip net pozisyon üretti mi?     
Orta sahada pas isabeti düşüşü ilk yarıda oldu mu?
Orta sahada pas isabeti düşüşü ikinci yarıda oldu mu?
Orta sahada pas isabeti düşüşü hangi segmentte belirginleşti?

Orta sahada pas isabeti düşüşü sonrası sonraki 5 dakikada kontrol bandı kaybedildi mi?
Orta sahada kart birikimi ilk yarıda pas kalitesini düşürdü mü?
Orta sahada kart birikimi ikinci yarıda pas kalitesini düşürdü mü?
Orta sahada kart birikimi hangi dakikada kritik seviyeye çıktı?
Orta sahada kart birikimi sonrası sonraki 5 dakikada top kaybı arttı mı?

Rakip presi artınca orta saha ilk 15 dakikada kontrol bandını kaybetti mi?
Rakip presi artınca orta saha 15–30 aralığında kontrol bandını kaybetti mi?
Rakip presi artınca orta saha 60–75 aralığında kontrol bandını kaybetti mi?
Orta saha kontrol kaybı hangi dakikada başladı?
Orta saha kontrol kaybı sonrası sonraki 5 dakikada savunma hattı geriye yaslandı mı?
Orta saha kontrol kaybı sonrası sonraki 5 dakikada takım uzun topa döndü mü?

Bu maçta orta saha değişikliği ilk yarıda oldu mu?
Bu maçta orta saha değişikliği ikinci yarıda oldu mu?
Orta saha değişikliği hangi dakikada oldu?
Orta saha değişikliği sonrası sonraki 5 dakikada tempo bandı değişti mi?
Orta saha değişikliği sonrası sonraki 5 dakikada kontrol bandı değişti mi?
Orta saha değişikliği sonrası sonraki 5 dakikada topa sahip olma yönü değişti mi?

FAZ-7-17
Bu maçta savunma hattı ilk 15 dakikada bir anda geriye yaslandı mı?
Bu maçta savunma hattı 15–30 aralığında bir anda geriye yaslandı mı?
Bu maçta savunma hattı 30–45 aralığında bir anda geriye yaslandı mı?
Bu maçta savunma hattı 60–75 aralığında bir anda geriye yaslandı mı?
Bu maçta savunma hattı 75–90 aralığında bir anda geriye yaslandı mı?

Savunma hattı geriye yaslanma hangi dakikada başladı?
Savunma hattı geriye yaslanma sonrası sonraki 5 dakikada risk bandı yükseldi mi?
Savunma hattı geriye yaslanma sonrası sonraki 5 dakikada rakip ceza sahası girişleri arttı mı?
Bu maçta savunma hattı ilk 15 dakikada öne çıktı mı?
Bu maçta savunma hattı 15–30 aralığında öne çıktı mı?
Bu maçta savunma hattı 60–75 aralığında öne çıktı mı?

Savunma hattı öne çıkış hangi dakikada oldu?
Savunma hattı öne çıktıktan sonraki 5 dakikada arka koşularla kırıldı mı?
Savunma hattı öne çıktıktan sonraki 5 dakikada ofsayta düşürme arttı mı?
Bu maçta savunma hattı ofsayt çizgisi ile ilk yarıda ofsayt yoğunluğu üretti mi?
Bu maçta savunma hattı ofsayt çizgisi ile ikinci yarıda ofsayt yoğunluğu üretti mi?

Savunma hattı ofsayt yoğunluğu hangi dakikalarda arttı?
Savunma hattı ofsayt yoğunluğu sonrası sonraki 5 dakikada rakip koşu denemeleri azaldı mı?
Bu maçta savunmada bireysel hata zinciri ilk yarıda oluştu mu?
Bu maçta savunmada bireysel hata zinciri ikinci yarıda oluştu mu?
Savunmada bireysel hata zinciri hangi dakikalarda oluştu?
Savunmada bireysel hata zinciri sonrası sonraki 5 dakikada risk bandı yükseldi mi?
Bu maçta savunma hatası sonrası gol yendi mi? Savunma hatası sonrası gol hangi dakikada yenildi? Savunma hatası sonrası sonraki 5 dakikada takım kontrol bandı düştü mü?
Bu maçta savunma hattı kart riski nedeniyle ilk yarıda geri çekildi mi? Bu maçta savunma hattı kart riski nedeniyle ikinci yarıda geri çekildi mi?
Savunma hattı kart riski nedeniyle hangi dakikada geri çekildi? Savunma hattı kart riski nedeniyle geri çekildikten sonraki 5 dakikada rakip baskı bandı yükseldi mi?

FAZ-7-18   
Bu maçta teknik direktör ilk müdahaleyi yaptı mı? Bu maçta teknik direktör ilk müdahaleyi hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+)
Bu maçta teknik direktör ilk müdahaleyi ilk yarıda mı yaptı ikinci yarıda mı? Bu maçta teknik direktör ilk müdahaleyi devre arasına kadar yaptı mı?
Bu maçta teknik direktör ilk müdahaleyi devre arasında mı yaptı?
Bu maçta teknik direktör ilk müdahaleyi devre arası sonrasında ilk 5 dakikada mı yaptı?
Bu maçta teknik direktör ilk müdahaleyi golden sonraki 5 dakika içinde mi yaptı?
Bu maçta teknik direktör ilk müdahaleyi yenen golden sonraki 5 dakika içinde mi yaptı?
Bu maçta teknik direktör ilk müdahaleyi yediği baskı dalgasından sonraki 5 dakika içinde mi yaptı?
Bu maçta teknik direktör ilk müdahaleyi rakibin kart gördüğü segmentte mi yaptı?

Bu maçta teknik direktör ilk müdahaleyi kendi takımının kart gördüğü segmentte mi yaptı?
Bu maçta teknik direktör ilk müdahaleyi sakatlık / tedavi duraklamasından hemen sonra mı yaptı?
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği oldu mu?
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği ise hangi dakikada yaptı?
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+)
Bu maçta teknik direktör ilk müdahalesi rol değişimi oldu mu?
Bu maçta teknik direktör ilk müdahalesi rol değişimi ise hangi dakikada yaptı?
Bu maçta teknik direktör ilk müdahalesi rol değişimi ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+)

Bu maçta teknik direktör ilk müdahalesi diziliş değişimi oldu mu?
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi ise hangi dakikada yaptı?
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+)
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu içerdi?
Bu maçta teknik direktör ilk müdahalesi hangi pozisyona yönelikti?
Bu maçta teknik direktör ilk müdahalesi hangi hattı etkiledi? (defans / orta saha / hücum)

Bu maçta teknik direktör ilk müdahalesi hangi kanadı etkiledi? (sol / sağ / merkez)
Bu maçta teknik direktör ilk müdahalesi hangi oyuncunun rolünü değiştirdi?
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu farklı hatta taşıdı?
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuya “kilit görev” verdi?
Bu maçta teknik direktör ilk müdahalesi takım kaptanını içerdi mi?
Bu maçta teknik direktör ilk müdahalesi sarı kartlı bir oyuncuyu çıkarmak için mi yapıldı?

Teknik direktör müdahalesi tempo bandını değiştirdi mi?
Teknik direktör müdahalesi tempo bandını hangi dakikadan itibaren değiştirdi?
Teknik direktör müdahalesi kontrol bandını değiştirdi mi?
Teknik direktör müdahalesi kontrol bandını hangi dakikadan itibaren değiştirdi?

Teknik direktör müdahalesi sonrası ilk 5 dakikada tempo bandı değişti mi?
Teknik direktör müdahalesi sonrası ilk 10 dakikada tempo bandı değişti mi?
Teknik direktör müdahalesi sonrası tempo bandı tempo_up mı tempo_down mı oldu?
Teknik direktör müdahalesi sonrası tempo bandı kaç segment boyunca yeni seviyede kaldı?
Teknik direktör müdahalesi sonrası tempo bandı kısa bir pik yapıp geri mi döndü?
Teknik direktör müdahalesi sonrası ilk 5 dakikada kontrol bandı değişti mi?

Teknik direktör müdahalesi sonrası ilk 10 dakikada kontrol bandı değişti mi?
Teknik direktör müdahalesi sonrası kontrol bandı stable’a mı unstable’a mı kaydı?
Teknik direktör müdahalesi sonrası topa sahip olma yönü değişti mi?
Teknik direktör müdahalesi sonrası pas hatası oranı düştü mü?
Teknik direktör müdahalesi sonrası top kaybı frekansı düştü mü?
Teknik direktör müdahalesi sonrası takımın çıkış kalitesi yükseldi mi?

FAZ-7-19
Devre arası sonrası çıkış refleksi değişti mi?
Devre arası sonrası çıkış refleksi ilk 5 dakikada değişti mi?
Devre arası sonrası çıkış refleksi ilk 10 dakikada değişti mi?
Devre arası sonrası çıkış refleksi hangi dakikada netleşti?
Devre arası sonrası çıkış refleksi hangi tetikleyiciyle değişti?(gol / kart / baskı / sakatlık / protesto)

Devre arası sonrası tempo bandı yükseldi mi?
Devre arası sonrası tempo bandı ilk 5 dakikada yükseldi mi?
Devre arası sonrası tempo bandı ilk 10 dakikada yükseldi mi?
Devre arası sonrası tempo bandı yükselişi kaç segment sürdü?
Devre arası sonrası tempo bandı yükselişi şut üretimine döndü mü?
Devre arası sonrası tempo bandı yükselişi xG artışına döndü mü?

Devre arası sonrası tempo bandı düştü mü?
Devre arası sonrası tempo bandı ilk 5 dakikada düştü mü?
Devre arası sonrası tempo bandı ilk 10 dakikada düştü mü?
Devre arası sonrası tempo bandı düşüşü kaç segment sürdü?
Devre arası sonrası tempo bandı düşüşü oyunu soğutma planı mıydı?

Devre arası sonrası baskı yönü değişti mi?
Devre arası sonrası baskı yönü ilk 5 dakikada değişti mi?
Devre arası sonrası baskı yönü ilk 10 dakikada değişti mi?
Devre arası sonrası baskı yönü değişimi hangi kanada kaydı?
Devre arası sonrası baskı yönü değişimi hangi oyuncu üzerinden kuruldu?
Devre arası sonrası baskı yönü değişimi rakibin çıkışını kesti mi?
Devre arası sonrası baskı yönü değişimi top kazanım sayısını artırdı mı?

FAZ-7-20
Maçta korner yoğunluğu olan blok var mı?→set_pieces.corners.high_intensity_block_exists → boolean → unknown,Korner yoğunluğu hangi 5 dakikalık pencerede oluştu? → set_pieces.corners.high_intensity_block_window_5m → string → unknown

Korner yoğunluğu 0–5 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_0_5 → boolean → unknown,Korner yoğunluğu 6–10 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_6_10 → boolean → unknown
Korner yoğunluğu 11–15 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_11_15 → boolean → unknown,Korner yoğunluğu 16–20 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_16_20 → boolean → unknown
Korner yoğunluğu 21–25 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_21_25 → boolean → unknown,Korner yoğunluğu 26–30 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_26_30 → boolean → unknown
Korner yoğunluğu 31–35 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_31_35 → boolean → unknown,Korner yoğunluğu 36–40 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_36_40 → boolean → unknown
Korner yoğunluğu 41–45 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_41_45 → boolean → unknown,Korner yoğunluğu 46–50 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_46_50 → boolean → unknown
Korner yoğunluğu 51–55 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_51_55 → boolean → unknown,Korner yoğunluğu 56–60 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_56_60 → boolean → unknown

Korner yoğunluğu 61–65 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_61_65 → boolean → unknown,Korner yoğunluğu 66–70 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_66_70 → boolean → unknown
Korner yoğunluğu 71–75 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_71_75 → boolean → unknown,Korner yoğunluğu 76–80 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_76_80 → boolean → unknown
Korner yoğunluğu 81–85 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_81_85 → boolean → unknown,Korner yoğunluğu 86–90 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_86_90 → boolean → unknown
Korner yoğunluğu sonrası 1 dakikada net pozisyon oluştu mu? → set_pieces.corners.after_high_intensity.big_chance_window_1m → boolean → unknown
Korner yoğunluğu sonrası 3 dakikada net pozisyon oluştu mu?→ set_pieces.corners.after_high_intensity.big_chance_window_3m → boolean → unknown
Korner yoğunluğu sonrası 5 dakikada net pozisyon oluştu mu? → set_pieces.corners.after_high_intensity.big_chance_window_5m → boolean → unknown

Korner yoğunluğu sonrası skor değişti mi? → set_pieces.corners.after_high_intensity.score_changed → boolean → unknown
Korner yoğunluğu sonrası ilk 5 dakikada skor değişti mi? → set_pieces.corners.after_high_intensity.score_changed_window_5m → boolean → unknown
Korner yoğunluğu sonrası duran top savunması tekrar eden risk üretti mi? → set_pieces.corners.after_high_intensity.defending_repeated_risk → boolean → unknown
Korner yoğunluğu sonrası ikinci top kazanımı arttı mı? → set_pieces.corners.after_high_intensity.second_ball_wins_up → boolean → unknown
Korner yoğunluğu sonrası ceza sahası içi şut sayısı arttı mı? → set_pieces.corners.after_high_intensity.box_shots_up → boolean → unknown
Korner yoğunluğu sonrası kornerden dönen toplar tekrar korner üretti mi? → set_pieces.corners.after_high_intensity.rebound_created_more_corners → boolean → unknown
Korner yoğunluğu sonrası kaleci müdahaleleri arttı mı? → set_pieces.corners.after_high_intensity.goalkeeper_interventions_up → boolean → unknown
Korner yoğunluğu sonrası savunma uzaklaştırmaları arttı mı? → set_pieces.corners.after_high_intensity.clearances_up → boolean → unknown

Duran toplar takımın tek skor yolu gibi mi çalıştı? → set_pieces.overall.primary_scoring_route → boolean → unknown
Duran toplar son 10 dakikada takımın tek skor yolu gibi mi çalıştı? → set_pieces.overall.primary_scoring_route_window_last10m → boolean → unknown
Duran toplar ilk 10 dakikada takımın tek skor yolu gibi mi çalıştı? → set_pieces.overall.primary_scoring_route_window_first10m → boolean → unknown
Duran top savunması tekrar eden risk üretti mi? → set_pieces.defending.repeated_risk → boolean → unknown
Duran top savunması aynı bölgeden tekrar eden faul üretti mi? → set_pieces.defending.repeated_fouls_same_zone → boolean → unknown
Duran top savunması aynı bölgeden tekrar eden korner verdi mi? → set_pieces.defending.repeated_corners_conceded_same_zone → boolean → unknown

Maçta serbest vuruş bandı için serbest vuruş yoğunluğu arttı mı? → set_pieces.free_kicks.high_intensity_increased → boolean → unknown
Serbest vuruş yoğunluğu hangi 5 dakikalık pencerede arttı? → set_pieces.free_kicks.high_intensity_window_5m → string → unknown
Maçta serbest vuruş bandı için tehlikeli bölge faulleri oluştu mu? → set_pieces.free_kicks.danger_zone_fouls_occurred → boolean → unknown
Tehlikeli bölge faulleri hangi 5 dakikalık pencerede oluştu? → set_pieces.free_kicks.danger_zone_fouls_window_5m → string → unknown
Maçta serbest vuruş bandı için duran top sonrası şut geldi mi? → set_pieces.free_kicks.after_set_piece.shot_taken → boolean → unknown

Duran top sonrası şut hangi dakikada geldi? → set_pieces.free_kicks.after_set_piece.shot_minute → integer → unknown
Duran top sonrası şut geldikten sonraki 5 dakikada korner oluştu mu? → set_pieces.free_kicks.after_set_piece.corners_occurred_window_5m → boolean → unknown
Duran top sonrası şut geldikten sonraki 5 dakikada net pozisyon oluştu mu? → set_pieces.free_kicks.after_set_piece.big_chance_occurred_window_5m → boolean → unknown
Duran top sonrası şut geldikten sonraki 5 dakikada tempo bandı değişti mi? → set_pieces.free_kicks.after_set_piece.tempo_band_changed_window_5m → boolean → unknown
Maçta aut/taç bandı için oyun sık sık taça gitti mi? → match.flow.throwin.frequency_high → boolean → unknown
Oyun sık sık taça gittiği blok hangi 5 dakikalık penceredeydi? → match.flow.throwin.cluster_window_5m → enum(0_5,5_10,10_15,15_20,20_25,25_30,30_35,35_40,40_45,45_50,50_55,55_60,60_65,65_70,70_75,75_80,80_85,85_90,unknown) → unknown
Maçta aut/taç bandı için tempo düşüşü oluşturdu mu? → match.flow.throwin.caused_tempo_drop → boolean → unknown

Taç yoğunluğu sonrası 1 dakikada tempo bandı düştü mü? → match.flow.throwin.after_cluster.td_tempo_drop_1m → boolean → unknown
Taç yoğunluğu sonrası 3 dakikada tempo bandı düştü mü? → match.flow.throwin.after_cluster.td_tempo_drop_3m → boolean → unknown
Taç yoğunluğu sonrası 5 dakikada tempo bandı düştü mü? → match.flow.throwin.after_cluster.td_tempo_drop_5m → boolean → unknown

Taç yoğunluğu sonrası baskı yönü değişti mi? → match.flow.throwin.after_cluster.pressure_direction_changed → boolean → unknown
Taç yoğunluğu sonrası topa sahip olma taraf değiştirdi mi? → match.flow.throwin.after_cluster.possession_side_changed → boolean → unknown
Bu maçta kaleci ilk 5 dakikada büyük hata yaptı mı? → match.gk.error.major.first_5m → boolean → unknown
Bu maçta kaleci ilk 10 dakikada büyük hata yaptı mı? → match.gk.error.major.first_10m → boolean → unknown
Bu maçta kaleci 15–30 aralığında büyük hata yaptı mı? → match.gk.error.major.min15_30 → boolean → unknown

Bu maçta kaleci 30–45 aralığında büyük hata yaptı mı? → match.gk.error.major.min30_45 → boolean → unknown
Bu maçta kaleci 45–60 aralığında büyük hata yaptı mı? → match.gk.error.major.min45_60 → boolean → unknown
Bu maçta kaleci 60–75 aralığında büyük hata yaptı mı? → match.gk.error.major.min60_75 → boolean → unknown
Bu maçta kaleci 75–90 aralığında büyük hata yaptı mı? → match.gk.error.major.min75_90 → boolean → unknown

Kalecinin büyük hatası hangi dakikada oldu? → match.gk.error.major.minute → integer → unknown
Kalecinin büyük hatası sonrası sonraki 5 dakikada rakip baskı bandı yükseldi mi? → match.gk.error.major.after_5m.opponent_pressure_band_up → boolean → unknown
Kalecinin büyük hatası sonrası sonraki 5 dakikada takım panik bandına girdi mi? → match.gk.error.major.after_5m.team_panic_band_on → boolean → unknown
Kalecinin büyük hatası sonrası sonraki 5 dakikada takım tempo bandı düştü mü? → match.gk.error.major.after_5m.team_tempo_band_down → boolean → unknown
Bu maçta kaleci ilk 5 dakikada kritik kurtarış yaptı mı? → match.gk.save.critical.first_5m → boolean → unknown
Bu maçta kaleci ilk 10 dakikada kritik kurtarış yaptı mı? → match.gk.save.critical.first_10m → boolean → unknown
Bu maçta kaleci 15–30 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min15_30 → boolean → unknown

Bu maçta kaleci 30–45 aralında kritik kurtarış yaptı mı? → match.gk.save.critical.min30_45 → boolean → unknown
Bu maçta kaleci 45–60 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min45_60 → boolean → unknown
Bu maçta kaleci 60–75 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min60_75 → boolean → unknown
Bu maçta kaleci 75–90 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min75_90 → boolean → unknown
Kalecinin kritik kurtarışı hangi dakikada oldu? → match.gk.save.critical.minute → integer → unknown
Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım tempo bandı yükseldi mi? → match.gk.save.critical.after_5m.team_tempo_band_up → boolean → unknown
Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım moral bandı yükseldi mi? → match.gk.save.critical.after_5m.team_morale_band_up → boolean → unknown

Bu maçta kaleci kurtarış serisi ilk 15 dakikada oluştu mu? → match.gk.save_streak.present.first_15m → boolean → unknown
Bu maçta kaleci kurtarış serisi 15–30 aralığında oluştu mu? → match.gk.save_streak.present.min15_30 → boolean → unknown
Bu maçta kaleci kurtarış serisi 30–45 aralığında oluştu mu? → match.gk.save_streak.present.min30_45 → boolean → unknown
Bu maçta kaleci kurtarış serisi 45–60 aralığında oluştu mu? → match.gk.save_streak.present.min45_60 → boolean → unknown
Bu maçta kaleci kurtarış serisi 60–75 aralığında oluştu mu? → match.gk.save_streak.present.min60_75 → boolean → unknown
Bu maçta kaleci kurtarış serisi 75–90 aralığında oluştu mu? → match.gk.save_streak.present.min75_90 → boolean → unknown

Kalecinin kurtarış serisi hangi dakikalar arasında gerçekleşti? → match.gk.save_streak.window_minutes → string → unknown
Kaleci kurtarış serisi sonrası sonraki 5 dakikada takım kontrol bandı yükseldi mi? → match.gk.save_streak.after_5m.team_control_band_up → boolean → unknown
Kaleci kurtarış serisi sonrası sonraki 5 dakikada rakip tempo bandı düştü mü? → match.gk.save_streak.after_5m.opponent_tempo_band_down → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına ilk 15 dakikada girdi mi? → match.gk.time_waste.present.first_15m → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına 30–45 aralığında girdi mi? → match.gk.time_waste.present.min30_45 → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına 60–75 aralığında girdi mi? → match.gk.time_waste.present.min60_75 → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına 75–90 aralığında girdi mi? → match.gk.time_waste.present.min75_90 → boolean → unknown

Kalecinin zaman geçirme davranışı hangi dakikada başladı? → match.gk.time_waste.start_minute → integer → unknown
Kalecinin zaman geçirme davranışı hangi dakikada bitti? → match.gk.time_waste.end_minute → integer → unknown
Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada maç temposu düştü mü? → match.gk.time_waste.after_5m.match_tempo_band_down → boolean → unknown
Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi? → match.gk.time_waste.after_5m.crowd_reaction_band_up → boolean → unknown
Bu maçta kaleci sakatlık/duraklama ile ritmi ilk yarıda bozdu mu? → match.gk.stoppage.rhythm_break.first_half → boolean → unknown
Bu maçta kaleci sakatlık/duraklama ile ritmi ikinci yarıda bozdu mu? → match.gk.stoppage.rhythm_break.second_half → boolean → unknown

Kalecinin sakatlık/duraklaması hangi dakikada oldu? → match.gk.stoppage.minute → integer → unknown
Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada takım baskı bandı düştü mü? → match.gk.stoppage.after_5m.team_pressure_band_down → boolean → unknown
Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada rakip baskı bandı düştü mü? → match.gk.stoppage.after_5m.opponent_pressure_band_down → boolean → unknown
Bu maçta kalecinin uzun oyun kurma tercihi ilk 15 dakikada belirginleşti mi? → match.gk.build_up.long_distribution.first_15m → boolean → unknown
Bu maçta kalecinin uzun oyun kurma tercihi 15–30 aralığında belirginleşti mi? → match.gk.build_up.long_distribution.min15_30 → boolean → unknown
Bu maçta kalecinin uzun oyun kurma tercihi 60–75 aralığında belirginleşti mi? → match.gk.build_up.long_distribution.min60_75 → boolean → unknown

Kalecinin uzun oyun kurma tercihi hangi dakikada belirginleşti? → match.gk.build_up.long_distribution.minute → integer → unknown
Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi? → match.gk.build_up.long_distribution.after_5m.turnover_band_up → boolean → unknown
Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada ikinci top kazanımı arttı mı? → match.gk.build_up.long_distribution.after_5m.second_ball_wins_up → boolean → unknown
Bu maçta kalecinin kısa oyun kurma tercihi ilk 15 dakikada belirginleşti mi? → match.gk.build_up.short_distribution.first_15m → boolean → unknown
Bu maçta kalecinin kısa oyun kurma tercihi 15–30 aralığında belirginleşti mi? → match.gk.build_up.short_distribution.min15_30 → boolean → unknown
Bu maçta kalecinin kısa oyun kurma tercihi 60–75 aralığında belirginleşti mi? → match.gk.build_up.short_distribution.min60_75 → boolean → unknown

Kalecinin kısa oyun kurma tercihi hangi dakikada belirginleşti? → match.gk.build_up.short_distribution.minute → integer → unknown
Kalecinin kısa oyun kurma tercihi sonrası sonraki 5 dakikada baskı altında top kaybı arttı mı? → match.gk.build_up.short_distribution.after_5m.pressure_turnover_up → boolean → unknown
Kalecinin kısa oyun kurma tercihi sonrası sonraki 5 dakikada rakip pres bandı yükseldi mi? → match.gk.build_up.short_distribution.after_5m.opponent_press_band_up → boolean → unknown
Bu maçta forvet ilk 10 dakikada net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min0_10 → boolean → unknown
Bu maçta forvet 10–20 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min10_20 → boolean → unknown
Bu maçta forvet 20–30 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min20_30 → boolean → unknown

Bu maçta forvet 30–45 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min30_45 → boolean → unknown
Bu maçta forvet 45–60 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min45_60 → boolean → unknown
Bu maçta forvet 60–75 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min60_75 → boolean → unknown
Bu maçta forvet 75–90 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min75_90 → boolean → unknown
Forvetin net pozisyon kaçırması hangi dakikada oldu? → match.fwd.miss.big_chance.minute → integer → unknown
Forvetin net pozisyon kaçırması sonrası sonraki 5 dakikada takım panik bandı yükseldi mi? → match.fwd.miss.big_chance.after_5m.team_panic_band_up → boolean → unknown
Forvetin net pozisyon kaçırması sonrası sonraki 5 dakikada takım tempo bandı düştü mü? → match.fwd.miss.big_chance.after_5m.team_tempo_band_down → boolean → unknown

Bu maçta forvet art arda net pozisyon kaçırması ilk yarıda oldu mu? → match.fwd.miss.big_chance_streak.present.first_half → boolean → unknown
Bu maçta forvet art arda net pozisyon kaçırması ikinci yarıda oldu mu? → match.fwd.miss.big_chance_streak.present.second_half → boolean → unknown
Forvetin art arda net pozisyon kaçırması hangi dakikalar arasında oldu? → match.fwd.miss.big_chance_streak.window_minutes → string → unknown
Forvetin art arda net pozisyon kaçırması sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi? → match.fwd.miss.big_chance_streak.after_5m.crowd_reaction_band_up → boolean → unknown
Forvetin art arda net pozisyon kaçırması sonrası sonraki 5 dakikada takım risk_up moduna geçti mi? → match.fwd.miss.big_chance_streak.after_5m.team_risk_up_mode_on → boolean → unknown
Bu maçta forvet baskı yükselince ilk yarıda kart/faul eğilimi arttı mı? → match.fwd.pressure_response.foul_card_tendency_up.first_half → boolean → unknown
Bu maçta forvet baskı yükselince ikinci yarıda kart/faul eğilimi arttı mı? → match.fwd.pressure_response.foul_card_tendency_up.second_half → boolean → unknown

Forvet baskı yükselince kart/faul eğilimi hangi dakikada belirginleşti? → match.fwd.pressure_response.foul_card_tendency_up.minute → integer → unknown
Forvetin kart/faul eğilimi sonrası sonraki 5 dakikada takım oyun akışı kesildi mi? → match.fwd.pressure_response.foul_card_tendency_up.after_5m.team_flow_disrupted → boolean → unknown
Bu maçta forvet baskı yükselince ilk yarıda itiraz dili sertleşti mi? → match.fwd.pressure_response.protest_language_harsh.first_half → boolean → unknown
Bu maçta forvet baskı yükselince ikinci yarıda itiraz dili sertleşti mi? → match.fwd.pressure_response.protest_language_harsh.second_half → boolean → unknown
Forvetin itiraz dili hangi dakikada sertleşti? → match.fwd.pressure_response.protest_language_harsh.minute → integer → unknown
Forvetin itiraz dili sertleşince sonraki 5 dakikada kart riski yükseldi mi? → match.fwd.pressure_response.protest_language_harsh.after_5m.card_risk_up → boolean → unknown

Bu maçta forvet iptal gol sonrası ilk 5 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_disallowed_goal.unstable.first_5m → boolean → unknown
Bu maçta forvet iptal gol sonrası sonraki 15 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_disallowed_goal.unstable.next_15m → boolean → unknown
Forvetin iptal gol sonrası mental kırılma anı hangi dakikada oldu? → match.fwd.mental.after_disallowed_goal.break_minute → integer → unknown
Forvet iptal gol sonrası sonraki 5 dakikada net pozisyon üretimi düştü mü? → match.fwd.mental.after_disallowed_goal.after_5m.big_chance_creation_down → boolean → unknown
Bu maçta forvet VAR sonrası ilk 5 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_var_event.unstable.first_5m → boolean → unknown
Bu maçta forvet VAR sonrası sonraki 15 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_var_event.unstable.next_15m → boolean → unknown
Forvetin VAR sonrası mental kırılma anı hangi dakikada oldu? → match.fwd.mental.after_var_event.break_minute → integer → unknown
Forvet VAR sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi? → match.fwd.mental.after_var_event.after_5m.turnover_band_up → boolean → unknown

Bu maçta forvet penaltı kaçırdı mı? → match.fwd.penalty.missed → boolean → unknown
Forvet penaltıyı hangi dakikada kaçırdı? → match.fwd.penalty.missed_minute → integer → unknown
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada takım tempo bandı düştü mü? → match.fwd.penalty.after_miss_5m.team_tempo_band_down → boolean → unknown
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada takım risk_up moduna geçti mi? → match.fwd.penalty.after_miss_5m.team_risk_up_mode_on → boolean → unknown
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi? → match.fwd.penalty.after_miss_5m.crowd_reaction_band_up → boolean → unknown
Bu maçta forvet oyundan ilk yarıda çıktı mı? → match.fwd.substituted.off.first_half → boolean → unknown
Bu maçta forvet oyundan ikinci yarıda çıktı mı? → match.fwd.substituted.off.second_half → boolean → unknown

Forvet hangi dakikada oyundan çıktı? → match.fwd.substituted.off_minute → integer → unknown
Forvet oyundan çıkış nedeni taktik mi? → match.fwd.substituted.off_reason.tactical → boolean → unknown
Forvet oyundan çıkış nedeni sakatlık mı? → match.fwd.substituted.off_reason.injury → boolean → unknown
Forvet oyundan çıkınca sonraki 5 dakikada takım net pozisyon üretimi düştü mü? → match.fwd.substituted.after_5m.big_chance_creation_down → boolean → unknown
Forvet oyundan çıkınca sonraki 5 dakikada takım pres bandı düştü mü? → match.fwd.substituted.after_5m.team_press_band_down → boolean → unknown

Bu maçta orta sahada top kaybı ilk 15 dakikada kümelendi mi? → match.mid.turnover.cluster.first_15m → boolean → unknown
Bu maçta orta sahada top kaybı 15–30 aralığında kümelendi mi? → match.mid.turnover.cluster.min15_30 → boolean → unknown
Bu maçta orta sahada top kaybı 30–45 aralığında kümelendi mi? → match.mid.turnover.cluster.min30_45 → boolean → unknown
Bu maçta orta sahada top kaybı 45–60 aralığında kümelendi mi? → match.mid.turnover.cluster.min45_60 → boolean → unknown
Bu maçta orta sahada top kaybı 60–75 aralığında kümelendi mi? → match.mid.turnover.cluster.min60_75 → boolean → unknown
Bu maçta orta sahada top kaybı 75–90 aralığında kümelendi mi? → match.mid.turnover.cluster.min75_90 → boolean → unknown


Orta saha top kaybı hangi dakikada başladı? → match.mid.turnover.cluster.start_minute → integer → unknown
Orta saha top kaybı hangi dakikada bitti? → match.mid.turnover.cluster.end_minute → integer → unknown
Orta saha top kaybı sonrası sonraki 5 dakikada momentum flip yaşandı mı? → match.mid.turnover.after_5m.momentum_flip → boolean → unknown
Orta saha top kaybı sonrası sonraki 5 dakikada rakip net pozisyon üretti mi? → match.mid.turnover.after_5m.opponent_big_chance_created → boolean → unknown
Orta sahada pas isabeti düşüşü ilk yarıda oldu mu? → match.midfield.pass_accuracy.drop.first_half → boolean → unknown
Orta sahada pas isabeti düşüşü ikinci yarıda oldu mu? → match.midfield.pass_accuracy.drop.second_half → boolean → unknown

Orta sahada pas isabeti düşüşü hangi segmentte belirginleşti? → match.midfield.pass_accuracy.drop.segment → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Orta sahada pas isabeti düşüşü sonrası sonraki 5 dakikada kontrol bandı kaybedildi mi? → match.midfield.pass_accuracy.drop.next5m.control_lost → boolean → unknown
Orta sahada kart birikimi ilk yarıda pas kalitesini düşürdü mü? → match.midfield.cards.accumulation.first_half.pass_quality_down → boolean → unknown
Orta sahada kart birikimi ikinci yarıda pas kalitesini düşürdü mü? → match.midfield.cards.accumulation.second_half.pass_quality_down → boolean → unknown
Orta sahada kart birikimi hangi dakikada kritik seviyeye çıktı? → match.midfield.cards.accumulation.critical_minute → integer → unknown
Orta sahada kart birikimi sonrası sonraki 5 dakikada top kaybı arttı mı? → match.midfield.cards.accumulation.next5m.turnover_up → boolean → unknown

Rakip presi artınca orta saha ilk 15 dakikada kontrol bandını kaybetti mi? → match.midfield.opponent_press_up.control_lost.0_15 → boolean → unknown
Rakip presi artınca orta saha 15–30 aralığında kontrol bandını kaybetti mi? → match.midfield.opponent_press_up.control_lost.15_30 → boolean → unknown
Rakip presi artınca orta saha 60–75 aralığında kontrol bandını kaybetti mi? → match.midfield.opponent_press_up.control_lost.60_75 → boolean → unknown
Orta saha kontrol kaybı hangi dakikada başladı? → match.midfield.control_loss.start_minute → integer → unknown
Orta saha kontrol kaybı sonrası sonraki 5 dakikada savunma hattı geriye yaslandı mı? → match.midfield.control_loss.next5m.defensive_line.dropped → boolean → unknown
Orta saha kontrol kaybı sonrası sonraki 5 dakikada takım uzun topa döndü mü? → match.midfield.control_loss.next5m.team.switched_to_long_ball → boolean → unknown

Bu maçta orta saha değişikliği ilk yarıda oldu mu? → match.midfield.substitution.first_half → boolean → unknown
Bu maçta orta saha değişikliği ikinci yarıda oldu mu? → match.midfield.substitution.second_half → boolean → unknown
Orta saha değişikliği hangi dakikada oldu? → match.midfield.substitution.minute → integer → unknown
Orta saha değişikliği sonrası sonraki 5 dakikada tempo bandı değişti mi? → match.midfield.substitution.next5m.tempo_band.changed → boolean → unknown
Orta saha değişikliği sonrası sonraki 5 dakikada kontrol bandı değişti mi? → match.midfield.substitution.next5m.control_band.changed → boolean → unknown
Orta saha değişikliği sonrası sonraki 5 dakikada topa sahip olma yönü değişti mi? → match.midfield.substitution.next5m.possession_direction.changed → boolean → unknown

Bu maçta savunma hattı ilk 15 dakikada bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.0_15 → boolean → unknown
Bu maçta savunma hattı 15–30 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.15_30 → boolean → unknown
Bu maçta savunma hattı 30–45 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.30_45 → boolean → unknown
Bu maçta savunma hattı 60–75 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.60_75 → boolean → unknown
Bu maçta savunma hattı 75–90 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.75_90 → boolean → unknown

Savunma hattı geriye yaslanma hangi dakikada başladı? → match.defensive_line.drop.start_minute → integer → unknown
Savunma hattı geriye yaslanma sonrası sonraki 5 dakikada risk bandı yükseldi mi? → match.defensive_line.drop.next5m.risk_band.up → boolean → unknown
Savunma hattı geriye yaslanma sonrası sonraki 5 dakikada rakip ceza sahası girişleri arttı mı? → match.defensive_line.drop.next5m.opponent.box_entries.up → boolean → unknown
Bu maçta savunma hattı ilk 15 dakikada öne çıktı mı? → match.defensive_line.step_up.0_15 → boolean → unknown
Bu maçta savunma hattı 15–30 aralığında öne çıktı mı? → match.defensive_line.step_up.15_30 → boolean → unknown
Bu maçta savunma hattı 60–75 aralığında öne çıktı mı? → match.defensive_line.step_up.60_75 → boolean → unknown

Savunma hattı öne çıkış hangi dakikada oldu? → match.defensive_line.step_up.minute → integer → unknown
Savunma hattı öne çıktıktan sonraki 5 dakikada arka koşularla kırıldı mı? → match.defensive_line.step_up.next5m.broken_by_runs → boolean → unknown
Savunma hattı öne çıktıktan sonraki 5 dakikada ofsayta düşürme arttı mı? → match.defensive_line.step_up.next5m.offside_traps.up → boolean → unknown
Bu maçta savunma hattı ofsayt çizgisi ile ilk yarıda ofsayt yoğunluğu üretti mi? → match.defensive_line.offside_trap.first_half.high_volume → boolean → unknown
Bu maçta savunma hattı ofsayt çizgisi ile ikinci yarıda ofsayt yoğunluğu üretti mi? → match.defensive_line.offside_trap.second_half.high_volume → boolean → unknown

Savunma hattı ofsayt yoğunluğu hangi dakikalarda arttı? → match.defensive_line.offside_trap.high_volume.minutes → list → unknown
Savunma hattı ofsayt yoğunluğu sonrası sonraki 5 dakikada rakip koşu denemeleri azaldı mı? →match.defensive_line.offside_trap.high_volume.next5m.opponent.run_atte   mpts.down → boolean → unknown
Bu maçta savunmada bireysel hata zinciri ilk yarıda oluştu mu?→ match.defense.individual_error_chain.first_half → boolean → unknow
Bu maçta savunmada bireysel hata zinciri ikinci yarıda oluştu mu?→ match.defense.individual_error_chain.second_half → boolean → unknown
Savunmada bireysel hata zinciri hangi dakikalarda oluştu? → match.defense.individual_error_chain.minutes → list → unknown
Savunmada bireysel hata zinciri sonrası sonraki 5 dakikada risk bandı yükseldi mi? → match.defense.individual_error_chain.next5m.risk_band.up → boolean → unknown

Bu maçta savunma hatası sonrası gol yendi mi? → match.defense.error.conceded_goal → boolean → unknown
Savunma hatası sonrası gol hangi dakikada yenildi? → match.defense.error.conceded_goal.minute → integer → unknown
Savunma hatası sonrası sonraki 5 dakikada takım kontrol bandı düştü mü? → match.defense.error.conceded_goal.next5m.team.control_band.down → boolean → unknown
Bu maçta savunma hatası sonrası VAR incelemesi oldu mu? → match.defense.error.var_review.present → boolean → unknown
Savunma hatası sonrası VAR incelemesi hangi dakikada oldu? → match.defense.error.var_review.minute → integer → unknown
VAR incelemesi sonrası sonraki 5 dakikada takım tempo bandı değişti mi? → match.defense.error.var_review.next5m.team.tempo_band.changed → boolean → unknown

Bu maçta savunma hattı kart riski nedeniyle ilk yarıda geri çekildi mi? → match.defensive_line.card_risk.drop.first_half → boolean → unknown
Bu maçta savunma hattı kart riski nedeniyle ikinci yarıda geri çekildi mi? → match.defensive_line.card_risk.drop.second_half → boolean → unknown
Savunma hattı kart riski nedeniyle hangi dakikada geri çekildi? → match.defensive_line.card_risk.drop.minute → integer → unknown
Savunma hattı kart riski nedeniyle geri çekildikten sonraki 5 dakikada rakip baskı bandı yükseldi mi? → match.defensive_line.card_risk.drop.next5m.opponent.pressure_band.up → boolean → unknown

FAZ-7-21
Bu maçta teknik direktör ilk müdahaleyi yaptı mı? → match.coach.first_intervention.present → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Bu maçta teknik direktör ilk müdahaleyi ilk yarıda mı yaptı ikinci yarıda mı? → match.coach.first_intervention.half → enum (first_half,second_half) → unknown
Bu maçta teknik direktör ilk müdahaleyi devre arasına kadar yaptı mı? → match.coach.first_intervention.before_halftime → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi devre arasında mı yaptı? → match.coach.first_intervention.at_halftime → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi devre arası sonrasında ilk 5 dakikada mı yaptı? → match.coach.first_intervention.first5m_after_halftime → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi golden sonraki 5 dakika içinde mi yaptı? → match.coach.first_intervention.next5m_after_scored_goal → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi yenen golden sonraki 5 dakika içinde mi yaptı? → match.coach.first_intervention.next5m_after_conceded_goal → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi yediği baskı dalgasından sonraki 5 dakika içinde mi yaptı? → match.coach.first_intervention.next5m_after_opponent_pressure_wave → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi rakibin kart gördüğü segmentte mi yaptı? → match.coach.first_intervention.during_opponent_card_segment → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi kendi takımının kart gördüğü segmentte mi yaptı? → match.coach.first_intervention.during_team_card_segment → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi sakatlık / tedavi duraklamasından hemen sonra mı yaptı? → match.coach.first_intervention.after_injury_stoppage → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği oldu mu? → match.coach.first_intervention.type_substitution → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği ise hangi dakikada yaptı? → match.coach.first_intervention.substitution.minute → integer → unknown

Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.substitution.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Bu maçta teknik direktör ilk müdahalesi rol değişimi oldu mu? → match.coach.first_intervention.type_role_change → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi rol değişimi ise hangi dakikada yaptı? → match.coach.first_intervention.role_change.minute → integer → unknown
Bu maçta teknik direktör ilk müdahalesi rol değişimi ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.role_change.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi oldu mu? → match.coach.first_intervention.type_formation_change → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi ise hangi dakikada yaptı? → match.coach.first_intervention.formation_change.minute → integer → unknown
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.formation_change.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown

Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu içerdi? → match.coach.first_intervention.target.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi pozisyona yönelikti? → match.coach.first_intervention.target.position → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi hattı etkiledi? (defans / orta saha / hücum) → match.coach.first_intervention.target.line → enum (defense,midfield,attack) → unknown
Bu maçta teknik direktör ilk müdahalesi hangi kanadı etkiledi? (sol / sağ / merkez) → match.coach.first_intervention.target.channel → enum (left,right,center) → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncunun rolünü değiştirdi? → match.coach.first_intervention.role_change.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu farklı hatta taşıdı? → match.coach.first_intervention.role_change.moved_player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuya “kilit görev” verdi? → match.coach.first_intervention.key_task.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi takım kaptanını içerdi mi? → match.coach.first_intervention.involves_captain → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi sarı kartlı bir oyuncuyu çıkarmak için mi yapıldı? → match.coach.first_intervention.substitution.for_booked_player → boolean → unknown

Teknik direktör müdahalesi tempo bandını değiştirdi mi? → match.coach.intervention.tempo_band.changed → boolean → unknown
Teknik direktör müdahalesi tempo bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.tempo_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası tempo bandı tempo_up mı tempo_down mı oldu? → match.coach.intervention.tempo_band.direction → enum (tempo_up,tempo_down) → unknown
Teknik direktör müdahalesi sonrası tempo bandı kaç segment boyunca yeni seviyede kaldı? → match.coach.intervention.tempo_band.duration_segments → integer → unknown
Teknik direktör müdahalesi sonrası tempo bandı kısa bir pik yapıp geri mi döndü? → match.coach.intervention.tempo_band.short_spike_then_revert → boolean → unknown
Teknik direktör müdahalesi kontrol bandını değiştirdi mi? → match.coach.intervention.control_band.changed → boolean → unknown
Teknik direktör müdahalesi kontrol bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.control_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası kontrol bandı stable’a mı unstable’a mı kaydı? → match.coach.intervention.control_band.direction → enum (stable,unstable) → unknown
Teknik direktör müdahalesi sonrası topa sahip olma yönü değişti mi? → match.coach.intervention.possession_direction.changed → boolean → unknown
Teknik direktör müdahalesi sonrası pas hatası oranı düştü mü? → match.coach.intervention.pass_error_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası top kaybı frekansı düştü mü?→ match.coach.intervention.turnover_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası takımın çıkış kalitesi yükseldi mi? → match.coach.intervention.build_up_quality.up → boolean → unknown

Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu içerdi? → match.coach.first_intervention.target.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi pozisyona yönelikti? → match.coach.first_intervention.target.position → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi hattı etkiledi? (defans / orta saha / hücum) → match.coach.first_intervention.target.line → enum (defense,midfield,attack) → unknown
Bu maçta teknik direktör ilk müdahalesi hangi kanadı etkiledi? (sol / sağ / merkez) → match.coach.first_intervention.target.channel → enum (left,right,center) → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncunun rolünü değiştirdi? → match.coach.first_intervention.role_change.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu farklı hatta taşıdı? → match.coach.first_intervention.role_change.moved_player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuya “kilit görev” verdi? → match.coach.first_intervention.key_task.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi takım kaptanını içerdi mi? → match.coach.first_intervention.involves_captain → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi sarı kartlı bir oyuncuyu çıkarmak için mi yapıldı? → match.coach.first_intervention.substitution.for_booked_player → boolean → unknown

Teknik direktör müdahalesi tempo bandını değiştirdi mi? → match.coach.intervention.tempo_band.changed → boolean → unknown
Teknik direktör müdahalesi tempo bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.tempo_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası tempo bandı tempo_up mı tempo_down mı oldu? → match.coach.intervention.tempo_band.direction → enum (tempo_up,tempo_down) → unknown
Teknik direktör müdahalesi sonrası tempo bandı kaç segment boyunca yeni seviyede kaldı? → match.coach.intervention.tempo_band.duration_segments → integer → unknown
Teknik direktör müdahalesi sonrası tempo bandı kısa bir pik yapıp geri mi döndü? → match.coach.intervention.tempo_band.short_spike_then_revert → boolean → unknown
Teknik direktör müdahalesi kontrol bandını değiştirdi mi? → match.coach.intervention.control_band.changed → boolean → unknown
Teknik direktör müdahalesi kontrol bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.control_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası kontrol bandı stable’a mı unstable’a mı kaydı? → match.coach.intervention.control_band.direction → enum (stable,unstable) → unknown
Teknik direktör müdahalesi sonrası topa sahip olma yönü değişti mi? → match.coach.intervention.possession_direction.changed → boolean → unknown
Teknik direktör müdahalesi sonrası pas hatası oranı düştü mü? → match.coach.intervention.pass_error_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası top kaybı frekansı düştü mü? → match.coach.intervention.turnover_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası takımın çıkış kalitesi yükseldi mi? → match.coach.intervention.build_up_quality.up → boolean → unknown

FAZ-7--22
Kırmızı kart sonrası plan deterministik değişti mi? → match.inplay.red_card.after.plan_change.is_deterministic → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 5 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_5m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 10 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_10m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi hangi müdahale ile oldu? (oyuncu değişikliği / rol değişimi / diziliş değişimi) → match.inplay.red_card.after.plan_change.intervention_type → enum(substitution, role_change, formation_change) → unknown
Kırmızı kart sonrası plan değişimi hangi oyuncuyu etkiledi? → match.inplay.red_card.after.plan_change.affected_player → string → unknown
Kırmızı kart sonrası diziliş değişti mi? → match.inplay.red_card.after.formation_change.is_occurred → boolean → unknown
Kırmızı kart sonrası diziliş hangi dakikada değişti? → match.inplay.red_card.after.formation_change.minute → integer → unknown
Kırmızı kart sonrası diziliş değişimi kaç dakika içinde yapıldı? → match.inplay.red_card.after.formation_change.within_minutes → integer → unknown
Kırmızı kart sonrası diziliş değişimi hangi forma dönüşüyle oldu? (4’lüden 5’liye / 3’lüye / çift forvete) → match.inplay.red_card.after.formation_change.to_shape → enum(back4_to_back5, back4_to_back3, to_two_strikers) → unknown
Kırmızı kart sonrası diziliş değişimi hücum gücünü düşürdü mü? → match.inplay.red_card.after.formation_change.reduces_attacking_power → boolean → unknown
Kırmızı kart sonrası diziliş değişimi ceza sahası savunmasını güçlendirdi mi? → match.inplay.red_card.after.formation_change.strengthens_box_defense → boolean → unknown


Takım öndeyken kapanmayı mı seçti yoksa ikinci gol mü aradı? → match.inplay.leading.team_plan.choice → enum(close_down, push_second_goal) → unknown
Takım öndeyken plan tercihi hangi dakikada netleşti? → match.inplay.leading.team_plan.choice_minute → integer → unknown
Takım öndeyken plan tercihi gol sonrası ilk 5 dakikada netleşti mi? → match.inplay.leading.team_plan.choice_settled.first_5m_after_goal → boolean → unknown
Takım öndeyken kapanmayı seçtiyse hangi hat derinleşti? → match.inplay.leading.close_down.deepened_line → enum(defense_line, midfield_line, forward_line) → unknown
Takım öndeyken kapanmayı seçtiyse tempo bandı düştü mü? → match.inplay.leading.close_down.tempo_band.down.is_started → boolean → unknown
Takım öndeyken kapanmayı seçtiyse kontrol bandı stable’a mı kilitlendi? → match.inplay.leading.close_down.control_band.locks_stable → boolean → unknown
Takım öndeyken ikinci golü aradıysa hangi kanattan yükledi? → match.inplay.leading.push_second_goal.attack_wing → enum(left, right) → unknown
Takım öndeyken ikinci golü aradıysa şut frekansı arttı mı? → match.inplay.leading.push_second_goal.shot_frequency.increases → boolean → unknown
Takım öndeyken ikinci golü aradıysa risk_up kaç segment sürdü? → match.inplay.leading.push_second_goal.risk_up.duration_segments → integer → unknown
Takım öndeyken time-waste davranışına izin verdi mi? → match.inplay.leading.time_waste.is_allowed → boolean → unknown
Takım öndeyken time-waste davranışı hangi dakikada başladı? → match.inplay.leading.time_waste.start_minute → integer → unknown
Takım öndeyken time-waste davranışı hangi zaman penceresinde arttı? (61-75 / 76-90+) → match.inplay.leading.time_waste.increase_window → enum(min61_75, min76_90plus) → unknown
Takım öndeyken time-waste davranışı sonrası tempo bandı düştü mü? → match.inplay.leading.time_waste.after.tempo_band.down.is_started → boolean → unknown
Takım öndeyken time-waste davranışı sonrası hakem uyarıları arttı mı? → match.inplay.leading.time_waste.after.ref_warnings.increase → boolean → unknown

Kırmızı kart sonrası plan deterministik değişti mi? → match.inplay.red_card.after.plan_change.is_deterministic → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 5 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_5m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 10 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_10m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi hangi müdahale ile oldu? (oyuncu değişikliği / rol değişimi / diziliş değişimi) → match.inplay.red_card.after.plan_change.intervention_type → enum(substitution, role_change, formation_change) → unknown
Kırmızı kart sonrası plan değişimi hangi oyuncuyu etkiledi? → match.inplay.red_card.after.plan_change.affected_player → string → unknown
Kırmızı kart sonrası diziliş değişti mi? → match.inplay.red_card.after.formation_change.is_occurred → boolean → unknown
Kırmızı kart sonrası diziliş hangi dakikada değişti? → match.inplay.red_card.after.formation_change.minute → integer → unknown
Kırmızı kart sonrası diziliş değişimi kaç dakika içinde yapıldı? → match.inplay.red_card.after.formation_change.within_minutes → integer → unknown
Kırmızı kart sonrası diziliş değişimi hangi forma dönüşüyle oldu? (4’lüden 5’liye / 3’lüye / çift forvete) → match.inplay.red_card.after.formation_change.to_shape → enum(back4_to_back5, back4_to_back3, to_two_strikers) → unknown
Kırmızı kart sonrası diziliş değişimi hücum gücünü düşürdü mü? → match.inplay.red_card.after.formation_change.reduces_attacking_power → boolean → unknown
Kırmızı kart sonrası diziliş değişimi ceza sahası savunmasını güçlendirdi mi? → match.inplay.red_card.after.formation_change.strengthens_box_defense → boolean → unknown

Takım öndeyken kapanmayı mı seçti yoksa ikinci gol mü aradı? → match.inplay.leading.team_plan.choice → enum(close_down, push_second_goal) → unknown
Takım öndeyken plan tercihi hangi dakikada netleşti? → match.inplay.leading.team_plan.choice_minute → integer → unknown
Takım öndeyken plan tercihi gol sonrası ilk 5 dakikada netleşti mi? → match.inplay.leading.team_plan.choice_settled.first_5m_after_goal → boolean → unknown
Takım öndeyken kapanmayı seçtiyse hangi hat derinleşti? → match.inplay.leading.close_down.deepened_line → enum(defense_line, midfield_line, forward_line) → unknown
Takım öndeyken kapanmayı seçtiyse tempo bandı düştü mü? → match.inplay.leading.close_down.tempo_band.down.is_started → boolean → unknown
Takım öndeyken kapanmayı seçtiyse kontrol bandı stable’a mı kilitlendi? → match.inplay.leading.close_down.control_band.locks_stable → boolean → unknown
Takım öndeyken ikinci golü aradıysa hangi kanattan yükledi? → match.inplay.leading.push_second_goal.attack_wing → enum(left, right) → unknown
Takım öndeyken ikinci golü aradıysa şut frekansı arttı mı? → match.inplay.leading.push_second_goal.shot_frequency.increases → boolean → unknown
Takım öndeyken ikinci golü aradıysa risk_up kaç segment sürdü? → match.inplay.leading.push_second_goal.risk_up.duration_segments → integer → unknown
Takım öndeyken time-waste davranışına izin verdi mi? → match.inplay.leading.time_waste.is_allowed → boolean → unknown
Takım öndeyken time-waste davranışı hangi dakikada başladı? → match.inplay.leading.time_waste.start_minute → integer → unknown
Takım öndeyken time-waste davranışı hangi zaman penceresinde arttı? (61-75 / 76-90+) → match.inplay.leading.time_waste.increase_window → enum(min61_75, min76_90plus) → unknown
Takım öndeyken time-waste davranışı sonrası tempo bandı düştü mü? → match.inplay.leading.time_waste.after.tempo_band.down.is_started → boolean → unknown
Takım öndeyken time-waste davranışı sonrası hakem uyarıları arttı mı? → match.inplay.leading.time_waste.after.ref_warnings.increase → boolean → unknown

Kırmızı kart sonrası plan deterministik değişti mi? → match.inplay.red_card.after.plan_change.is_deterministic → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 5 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_5m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 10 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_10m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi hangi müdahale ile oldu? (oyuncu değişikliği / rol değişimi / diziliş değişimi) → match.inplay.red_card.after.plan_change.intervention_type → enum(substitution, role_change, formation_change) → unknown
Kırmızı kart sonrası plan değişimi hangi oyuncuyu etkiledi? → match.inplay.red_card.after.plan_change.affected_player → string → unknown
Kırmızı kart sonrası diziliş değişti mi? → match.inplay.red_card.after.formation_change.is_occurred → boolean → unknown
Kırmızı kart sonrası diziliş hangi dakikada değişti? → match.inplay.red_card.after.formation_change.minute → integer → unknown
Kırmızı kart sonrası diziliş değişimi kaç dakika içinde yapıldı? → match.inplay.red_card.after.formation_change.within_minutes → integer → unknown
Kırmızı kart sonrası diziliş değişimi hangi forma dönüşüyle oldu? (4’lüden 5’liye / 3’lüye / çift forvete) → match.inplay.red_card.after.formation_change.to_shape → enum(back4_to_back5, back4_to_back3, to_two_strikers) → unknown
Kırmızı kart sonrası diziliş değişimi hücum gücünü düşürdü mü? → match.inplay.red_card.after.formation_change.reduces_attacking_power → boolean → unknown
Kırmızı kart sonrası diziliş değişimi ceza sahası savunmasını güçlendirdi mi? → match.inplay.red_card.after.formation_change.strengthens_box_defense → boolean → unknown

Takım öndeyken kapanmayı mı seçti yoksa ikinci gol mü aradı? → match.inplay.leading.team_plan.choice → enum(close_down, push_second_goal) → unknown
Takım öndeyken plan tercihi hangi dakikada netleşti? → match.inplay.leading.team_plan.choice_minute → integer → unknown
Takım öndeyken plan tercihi gol sonrası ilk 5 dakikada netleşti mi? → match.inplay.leading.team_plan.choice_settled.first_5m_after_goal → boolean → unknown
Takım öndeyken kapanmayı seçtiyse hangi hat derinleşti? → match.inplay.leading.close_down.deepened_line → enum(defense_line, midfield_line, forward_line) → unknown
Takım öndeyken kapanmayı seçtiyse tempo bandı düştü mü? → match.inplay.leading.close_down.tempo_band.down.is_started → boolean → unknown
Takım öndeyken kapanmayı seçtiyse kontrol bandı stable’a mı kilitlendi? → match.inplay.leading.close_down.control_band.locks_stable → boolean → unknown
Takım öndeyken ikinci golü aradıysa hangi kanattan yükledi? → match.inplay.leading.push_second_goal.attack_wing → enum(left, right) → unknown
Takım öndeyken ikinci golü aradıysa şut frekansı arttı mı? → match.inplay.leading.push_second_goal.shot_frequency.increases → boolean → unknown
Takım öndeyken ikinci golü aradıysa risk_up kaç segment sürdü? → match.inplay.leading.push_second_goal.risk_up.duration_segments → integer → unknown
Takım öndeyken time-waste davranışına izin verdi mi? → match.inplay.leading.time_waste.is_allowed → boolean → unknown
Takım öndeyken time-waste davranışı hangi dakikada başladı? → match.inplay.leading.time_waste.start_minute → integer → unknown
Takım öndeyken time-waste davranışı hangi zaman penceresinde arttı? (61-75 / 76-90+) → match.inplay.leading.time_waste.increase_window → enum(min61_75, min76_90plus) → unknown
Takım öndeyken time-waste davranışı sonrası tempo bandı düştü mü? → match.inplay.leading.time_waste.after.tempo_band.down.is_started → boolean → unknown
Takım öndeyken time-waste davranışı sonrası hakem uyarıları arttı mı? → match.inplay.leading.time_waste.after.ref_warnings.increase → boolean → unknown

FAZ-7-22
Maç içinde tribün protestosu oldu mu? → match.crowd.protest.occurred → boolean → unknown
Maç içinde tribün protestosu kaç kez tekrar etti? → match.crowd.protest.repeat_count → integer → unknown
Maç içinde tribün protestosu tek dalga mıydı çoklu dalga mıydı? → match.crowd.protest.wave_type → enum (single_wave,multi_wave) → unknown
Maç içinde tribün protestosu ilk kez hangi dakikada başladı? → match.crowd.protest.first_start_minute → integer → unknown
Maç içinde tribün protestosu ilk kez hangi zaman penceresinde başladı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.crowd.protest.first_start_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Maç içinde tribün protestosu devre arası öncesi mi başladı devre arası sonrası mı? → match.crowd.protest.first_start_halftime_side → enum (before_halftime,after_halftime) → unknown
Maç içinde tribün protestosu golden sonra mı başladı? → match.crowd.protest.trigger_after_goal_scored → boolean → unknown
Maç içinde tribün protestosu yenen golden sonra mı başladı? → match.crowd.protest.trigger_after_goal_conceded → boolean → unknown
Maç içinde tribün protestosu hakem kararından sonra mı başladı? → match.crowd.protest.trigger_after_referee_decision → boolean → unknown
Maç içinde tribün protestosu VAR incelemesinden sonra mı başladı? → match.crowd.protest.trigger_after_var_review → boolean → unknown
Maç içinde tribün protestosu kırmızı karttan sonra mı başladı? → match.crowd.protest.trigger_after_red_card → boolean → unknown


Tribün protestosu dalga dalga tekrar etti mi? → match.crowd.protest.waves_repeated → boolean → unknown
Tribün protestosu dalgaları arasında kaç dakika vardı? → match.crowd.protest.wave_gap_minutes → integer → unknown
Tribün protestosu dalgaları her seferinde daha mı yükseldi daha mı düştü? → match.crowd.protest.wave_trend → enum (increasing,decreasing) → unknown
Tribün baskısı ilk kez hangi segmentte yükseldi? → match.crowd.pressure.first_rise_segment → enum (segment_0_15,segment_16_30,segment_31_45,segment_46_60,segment_61_75,segment_76_90_plus) → unknown
Tribün baskısı yükselişi hangi dakikada başladı? → match.crowd.pressure.rise_start_minute → integer → unknown
Tribün baskısı yükselişi hangi zaman penceresinde başladı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.crowd.pressure.rise_start_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Tribün baskısı yükselişi hangi tetikleyiciyle başladı? (gol / yenen gol / kaçan pozisyon / hakem kararı / kart / protesto) → match.crowd.pressure.rise_trigger → enum (goal_scored,goal_conceded,missed_chance,referee_decision,card,protest) → unknown

Tribün baskısı yükselince takımın ilk tepkisi tempo_up mı tempo_down mıydı? → match.crowd.pressure.team_first_response.tempo_direction → enum (tempo_up,tempo_down) → unknown
Tribün baskısı yükselince takımın ilk 5 dakikalık tepkisi tempo_up mı tempo_down mıydı? → match.crowd.pressure.team_response_next5m.tempo_direction → enum (tempo_up,tempo_down) → unknown
Tribün baskısı yükselince takımın ilk tepkisi hangi dakikada başladı? → match.crowd.pressure.team_first_response.start_minute → integer → unknown
Tribün baskısı yükselince takımın ilk tepkisi hangi oyuncu grubundan geldi? (defans / orta saha / hücum) →match.crowd.pressure.team_first_response.actor_group → enum (defense,midfield,attack) → unknown
Tribün baskısı yükselince takım panik hücum dalgasına girdi mi? → match.crowd.pressure.panic_attack_wave.entered → boolean → unknown
Tribün baskısı yükselince takım panik hücum dalgası hangi dakikada başladı? → match.crowd.pressure.panic_attack_wave.start_minute → integer → unknown
Tribün baskısı yükselince takım panik hücum dalgası kaç dakika sürdü? → match.crowd.pressure.panic_attack_wave.duration_minutes → integer → unknown

Tribün baskısı yükselince takım panik hücum dalgası sonrası ilk 5 dakikada top kaybı arttı mı? → match.crowd.pressure.panic_attack_wave.turnover_increase_next5m → boolean → unknown
Tribün baskısı yükselince takım kontrol bandı unstable’a kaydı mı? → match.crowd.pressure.control_to_unstable → boolean → unknown
Tribün baskısı yükselince takım kontrol bandı unstable’a hangi dakikada kaydı? → match.crowd.pressure.control_to_unstable_minute → integer → unknown
Tribün baskısı yükselince takım kontrol bandı unstable’a kaydıktan sonra ilk 5 dakikada pas hatası arttı mı? → match.crowd.pressure.unstable_after_effect.pass_error_increase_next5m → boolean → unknown
Tribün baskısı yükselince takım kart/faul yoğunluğunu artırdı mı? → match.crowd.pressure.foul_card_intensity_increase → boolean → unknown
Tribün baskısı yükselince takım faul yoğunluğu ilk 5 dakikada arttı mı? → match.crowd.pressure.foul_intensity_increase_next5m → boolean → unknown
Tribün baskısı yükselince takım kart faul yoğunluğu artışı hangi oyuncu grubunda oldu? → match.crowd.pressure.foul_card_increase_actor_group → enum (defense,midfield,attack) → unknown

Tribün baskısı yükselince takım kart faul yoğunluğu artışı hangi bölgeye kaydı? → match.crowd.pressure.foul_card_increase_zone → enum (defensive_third,middle_third,attacking_third) → unknown
Tribün baskısı yükselince teknik direktör daha erken müdahale yaptı mı? → match.crowd.pressure.coach_intervention.earlier_than_normal → boolean → unknown
Tribün baskısı yükselince teknik direktör müdahalesi kaç dakika içinde geldi? → match.crowd.pressure.coach_intervention.response_minutes → integer → unknown
Tribün baskısı yükselince teknik direktör müdahalesi tribün yükselişinden sonraki ilk 5 dakikada mı geldi? → match.crowd.pressure.coach_intervention.within_first5m → boolean → unknown
Tribün baskısı yükselince teknik direktör müdahalesi hangi müdahale tipiydi? (değişiklik / rol / diziliş) → match.crowd.pressure.coach_intervention.type → enum (substitution,role_change,formation_change) → unknown
Tribün baskısı yükselince hakem düdük sıklığını artırdı mı? → match.crowd.pressure.referee_whistle_frequency_increase → boolean → unknown

Tribün baskısı yükselince hakem düdük sıklığı hangi dakikadan itibaren arttı? → match.crowd.pressure.referee_whistle_increase_minute → integer → unknown
Tribün baskısı yükselince hakem düdük sıklığı ilk 5 dakikada arttı mı? → match.crowd.pressure.referee_whistle_increase_next5m → boolean → unknown
Tribün baskısı yükselince hakem kart standardı sertleşti mi? → match.crowd.pressure.referee_card_standard_hardened → boolean → unknown
Tribün baskısı yükselince hakem kart standardı sertleşmesi hangi dakikada başladı? → match.crowd.pressure.referee_card_standard_harden_start_minute → integer → unknown
Tribün baskısı yükselince hakem kart standardı sertleşmesi sonrası ilk 5 dakikada kart sayısı arttı mı? → match.crowd.pressure.referee_card_harden_effect.card_count_increase_next5m → boolean → unknown
Tribün baskısı yükselince oyuncu itirazları kümelendi mi? → match.crowd.pressure.player_complaints.clustered → boolean → unknown
Tribün baskısı yükselince oyuncu itirazları hangi dakikada kümelendi? → match.crowd.pressure.player_complaints.cluster_start_minute → integer → unknown

Tribün baskısı yükselince oyuncu itirazları hangi takımda arttı? → match.crowd.pressure.player_complaints.team_side → enum (home,away) → unknown
Tribün baskısı yükselince oyuncu itirazları sonrası kart çıktı mı? → match.crowd.pressure.player_complaints.card_afterwards → boolean → unknown
Tribün baskısı yükselince oyuncu itirazları sonrası kart hangi dakikada çıktı? → match.crowd.pressure.player_complaints.card_minute → integer → unknown
Tribün baskısı sonrası maç içinde sahaya madde atma oldu mu? → match.crowd.incident.throwing_objects.occurred → boolean → unknown
Tribün baskısı sonrası sahaya madde atma hangi dakikada oldu? → match.crowd.incident.throwing_objects.first_minute → integer → unknown
Tribün baskısı sonrası sahaya madde atma kaç kez tekrar etti? → match.crowd.incident.throwing_objects.repeat_count → integer → unknown
Tribün baskısı sonrası sahaya madde atma hangi tribünden geldi? → match.crowd.incident.throwing_objects.stand_side → enum (home_stand,away_stand,unknown) → unknown

Sahaya madde atma olayı oyunu 2 dakikadan uzun durdurdu mu? → match.crowd.incident.throwing_objects.stoppage_over_2m → boolean → unknown
Sahaya madde atma olayı oyunu kaç dakika durdurdu? → match.crowd.incident.throwing_objects.stoppage_minutes → integer → unknown
Sahaya madde atma olayı sonrası tempo bandı düştü mü? → match.crowd.incident.throwing_objects.effect.tempo_down → boolean → unknown
Sahaya madde atma olayı sonrası kontrol bandı kayboldu mu? → match.crowd.incident.throwing_objects.effect.control_lost → boolean → unknown

Tribün baskısı sonrası güvenlik uyarısı veya anons yapıldı mı? → match.crowd.security_announcement.occurred → boolean → unknown
Tribün baskısı sonrası güvenlik anonsu hangi dakikada yapıldı? → match.crowd.security_announcement.first_minute → integer → unknown
Tribün baskısı sonrası güvenlik anonsu kaç kez tekrar etti? → match.crowd.security_announcement.repeat_count → integer → unknown
Tribün baskısı sonrası maçın kontrolü kayboldu mu? → match.crowd.pressure.after_effect.match_control_lost → boolean → unknown
Tribün baskısı sonrası maçın kontrolü hangi dakikada kayboldu? → match.crowd.pressure.after_effect.match_control_lost_minute → integer → unknown
Tribün baskısı sonrası maçın kontrolü kaybolduktan sonra ilk 5 dakikada kart/faul arttı mı? → match.crowd.pressure.after_effect.card_foul_increase_next5m → boolean → unknown

Tribün baskısı hangi takım aleyhine yoğunlaştı? → match.crowd.pressure.target_team_side → enum (home,away) → unknown
Tribün baskısı hangi dakikada belirli bir takıma yöneldi? → match.crowd.pressure.target_team_start_minute → integer → unknown
Tribün baskısı hangi zaman penceresinde belirli bir takıma yöneldi? (31-45 / 46-60 / 61-75 / 76-90+) → match.crowd.pressure.target_team_start_window → enum (31_45,46_60,61_75,76_90_plus) → unknown
Tribün baskısı “hakem hedef” mi “oyuncu hedef” mi “yönetim hedef” mi taşıdı? → match.crowd.pressure.target_type → enum (referee_target,player_target,management_target) → unknown
Tribün baskısı hakem hedefli ise hangi karar tetikledi? → match.crowd.pressure.referee_target.trigger_decision → enum (foul_decision,card_decision,penalty_decision,var_decision,offside_decision,unknown) → unknown
Tribün baskısı oyuncu hedefli ise hangi oyuncu hedef oldu? → match.crowd.pressure.player_target.player_reference → string → unknown
Tribün baskısı yönetim hedefli ise hangi olay tetikledi? → match.crowd.pressure.management_target.trigger_event → enum (transfer_policy,coach_decision,club_statement,board_action,unknown) → unknown

Tribün baskısı belirli bir oyuncuya yöneldi mi? → match.crowd.pressure.player_target.occurred → boolean → unknown
Tribün baskısı belirli bir oyuncuya hangi dakikada yöneldi? → match.crowd.pressure.player_target.start_minute → integer → unknown
Tribün baskısı belirli bir oyuncuya yönelme kaç dakika sürdü? → match.crowd.pressure.player_target.duration_minutes → integer → unknown
Tribün baskısı belirli bir oyuncuyu oyundan düşürdü mü? → match.crowd.pressure.player_target.effect.player_performance_drop → boolean → unknown
Tribün baskısı belirli bir oyuncuyu oyundan düşürdüyse hangi dakikadan itibaren performans düştü? → match.crowd.pressure.player_target.effect.performance_drop_start_minute → integer → unknown
Tribün baskısı belirli bir oyuncuyu oyundan düşürdükten sonra ilk 5 dakikada top kaybı arttı mı? → match.crowd.pressure.player_target.effect.turnover_increase_next5m → boolean → unknown
Tribün baskısı sonrası takımın pas hatası arttı mı? → match.crowd.pressure.after_effect.pass_error_increase → boolean → unknown

Tribün baskısı sonrası pas hatası artışı hangi dakikada başladı? → match.crowd.pressure.after_effect.pass_error_increase_start_minute → integer → unknown
Tribün baskısı sonrası pas hatası artışı kaç dakika sürdü? → match.crowd.pressure.after_effect.pass_error_increase_duration_minutes → integer → unknown
Tribün baskısı sonrası top kaybı arttı mı? → match.crowd.pressure.after_effect.turnover_increase → boolean → unknown
Tribün baskısı sonrası top kaybı artışı hangi dakikada başladı? → match.crowd.pressure.after_effect.turnover_increase_start_minute → integer → unknown
Tribün baskısı sonrası top kaybı artışı kaç dakika sürdü? → match.crowd.pressure.after_effect.turnover_increase_duration_minutes → integer → unknown

Tribün baskısı sonrası takımın disiplin bandı aggressive’e kaydı mı? → match.crowd.pressure.after_effect.discipline_to_aggressive → boolean → unknown
Tribün baskısı sonrası disiplin bandı aggressive’e kayma hangi dakikada oldu? → match.crowd.pressure.after_effect.discipline_to_aggressive_minute → integer → unknown
Tribün baskısı sonrası disiplin bandı aggressive’e kayma sonrası ilk 5 dakikada kart sayısı arttı mı? → match.crowd.pressure.after_effect.aggressive_effect.card_count_increase_next5m → boolean → unknown
Tribün baskısı sonrası takımın tempo taşıma gücü düştü mü? → match.crowd.pressure.after_effect.tempo_carrying_power_drop → boolean → unknown
Tribün baskısı sonrası tempo taşıma gücü düşüşü hangi dakikada başladı? → match.crowd.pressure.after_effect.tempo_carrying_power_drop_start_minute → integer → unknown
Tribün baskısı sonrası tempo taşıma gücü düşüşü kaç segment sürdü? → match.crowd.pressure.after_effect.tempo_carrying_power_drop_duration_segments → integer → unknown

Tribün baskısı sonrası deplasman takımı panic bandına girdi mi? → match.crowd.pressure.after_effect.away_team_to_panic → boolean → unknown
Tribün baskısı sonrası deplasman takımı panic bandına girişi hangi dakikada oldu? → match.crowd.pressure.after_effect.away_team_to_panic_minute → integer → unknown
Tribün baskısı sonrası deplasman takımı panic bandına girdikten sonra ilk 5 dakikada top kaybı arttı mı? → match.crowd.pressure.after_effect.away_panic_effect.turnover_increase_next5m → boolean → unknown
Tribün baskısı sonrası iç saha takımı kontrolü kilitledi mi? → match.crowd.pressure.after_effect.home_team_control_locked → boolean → unknown
Tribün baskısı sonrası iç saha takımı kontrolü kilitlemesi hangi dakikada başladı? → match.crowd.pressure.after_effect.home_team_control_locked_start_minute → integer → unknown
Tribün baskısı sonrası iç saha takımı kontrolü kilitledikten sonra tempo bandı düştü mü? → match.crowd.pressure.after_effect.home_control_lock_effect.tempo_down → boolean → unknown

Tribün baskısı sonrası hakemle tartışma görüntüleri arttı mı? → match.crowd.pressure.after_effect.referee_arguments_increase → boolean → unknown
Tribün baskısı sonrası hakemle tartışma artışı hangi dakikada başladı?→ match.crowd.pressure.after_effect.referee_arguments_increase_start_minute → integer → unknown
Tribün baskısı sonrası hakemle tartışma artışı kaç dakika sürdü? → match.crowd.pressure.after_effect.referee_arguments_increase_duration_minutes → integer → unknown
Tribün baskısı maç sonunda taşkınlık riskine döndü mü? → match.crowd.pressure.endgame.misconduct_risk → boolean → unknown
Tribün baskısı maç sonunda taşkınlık riski hangi dakikada yükseldi? → match.crowd.pressure.endgame.misconduct_risk_rise_minute → integer → unknown
Tribün baskısı maç sonunda taşkınlık riski güvenlik müdahalesine döndü mü? → match.crowd.pressure.endgame.security_intervention_triggered → boolean → unknown

FAZ-7-23
Maçın toplam koşu mesafesi verisi ilk yarı için mevcut mu? → match.physical.run_distance.total.availability.first_half → boolean → unknown
Maçın toplam koşu mesafesi verisi ikinci yarı için mevcut mu? → match.physical.run_distance.total.availability.second_half → boolean → unknown
Maçın toplam koşu mesafesi verisi 0–15 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m00_15 → boolean → unknown
Maçın toplam koşu mesafesi verisi 16–30 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m16_30 → boolean → unknown
Maçın toplam koşu mesafesi verisi 31–45+ aralığı için mevcut mu? → match.physical.run_distance.total.availability.m31_45p → boolean → unknown
Maçın toplam koşu mesafesi verisi 46–60 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m46_60 → boolean → unknown
Maçın toplam koşu mesafesi verisi 61–75 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m61_75 → boolean → unknown
Maçın toplam koşu mesafesi verisi 76–90+ aralığı için mevcut mu? → match.physical.run_distance.total.availability.m76_90p → boolean → unknown

Maçın takım bazlı toplam koşu mesafesi verisi ilk yarı için mevcut mu? → match.physical.run_distance.team_total.availability.first_half → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi ikinci yarı için mevcut mu? → match.physical.run_distance.team_total.availability.second_half → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 0–15 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m00_15 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 16–30 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m16_30 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 31–45+ aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m31_45p → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 46–60 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m46_60 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 61–75 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m61_75 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 76–90+ aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m76_90p → boolean → unknown

Maçın oyuncu bazlı koşu mesafesi verisi ilk yarı için mevcut mu? → match.physical.run_distance.player.availability.first_half → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi ikinci yarı için mevcut mu? → match.physical.run_distance.player.availability.second_half → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 0–15 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m00_15 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 16–30 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m16_30 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 31–45+ aralığı için mevcut mu? → match.physical.run_distance.player.availability.m31_45p → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 46–60 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m46_60 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 61–75 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m61_75 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 76–90+ aralığı için mevcut mu? → match.physical.run_distance.player.availability.m76_90p → boolean → unknown

Maç içinde en çok koşan ilk 3 oyuncu ilk yarı özelinde kimdi? → match.physical.run_distance.leaders.top3.players.first_half → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu ikinci yarı özelinde kimdi? → match.physical.run_distance.leaders.top3.players.second_half → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 0–15 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m00_15 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 16–30 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m16_30 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 31–45+ aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m31_45p → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 46–60 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m46_60 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 61–75 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m61_75 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 76–90+ aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m76_90p → list(object) → unknown

Maç içinde en çok koşan ilk 5 oyuncu ilk yarı özelinde kimdi? → match.physical.run_distance.leaders.top5.players.first_half → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu ikinci yarı özelinde kimdi? → match.physical.run_distance.leaders.top5.players.second_half → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 0–15 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m00_15 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 16–30 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m16_30 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 31–45+ aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m31_45p → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 46–60 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m46_60 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 61–75 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m61_75 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 76–90+ aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m76_90p → list(object) → unknown

Maç içinde en çok koşan oyuncu ilk yarıda hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.first_half → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu ikinci yarıda hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.second_half → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 0–15 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m00_15 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 16–30 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m16_30 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 31–45+ aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m31_45p → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 46–60 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m46_60 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 61–75 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m61_75 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 76–90+ aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m76_90p → enum(home,away) → unknown

Maç içinde en çok koşan oyuncu ilk yarıda hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.first_half → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu ikinci yarıda hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.second_half → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 0–15 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m00_15 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 16–30 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m16_30 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 31–45+ aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m31_45p → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 46–60 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m46_60 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 61–75 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m61_75 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 76–90+ aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m76_90p → enum(goalkeeper,defender,midfielder,forward) → unknown

Maç içinde en çok koşan oyuncu için ilk yarı koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.first_half → string → unknown
Maç içinde en çok koşan oyuncu için ikinci yarı koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.second_half → string → unknown
Maç içinde en çok koşan oyuncu için 0–15 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m00_15 → string → unknown
Maç içinde en çok koşan oyuncu için 16–30 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m16_30 → string → unknown
Maç içinde en çok koşan oyuncu için 31–45+ aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m31_45p → string → unknown
Maç içinde en çok koşan oyuncu için 46–60 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m46_60 → string → unknown
Maç içinde en çok koşan oyuncu için 61–75 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m61_75 → string → unknown
Maç içinde en çok koşan oyuncu için 76–90+ aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m76_90p → string → unknown


Maç içinde iki takımın toplam koşu mesafesi farkı ilk yarıda var mı? → match.physical.run_distance.team_total.diff.exists.first_half → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı ikinci yarıda var mı? → match.physical.run_distance.team_total.diff.exists.second_half → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 0–15 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m00_15 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 16–30 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m16_30 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 31–45+ aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m31_45p → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 46–60 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m46_60 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 61–75 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m61_75 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 76–90+ aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m76_90p-booleam-unknown

FAZ-7-24
Maçta korner yoğunluğu olan blok var mı? → set_pieces.corners.high_intensity_block_exists → boolean → unknown
Korner yoğunluğu hangi 5 dakikalık pencerede oluştu? → set_pieces.corners.high_intensity_block_window_5m → string → unknown
Korner yoğunluğu 0–5 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_0_5 → boolean → unknown
Korner yoğunluğu 6–10 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_6_10 → boolean → unknown
Korner yoğunluğu 11–15 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_11_15 → boolean → unknown

Korner yoğunluğu 16–20 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_16_20 → boolean → unknown
Korner yoğunluğu 21–25 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_21_25 → boolean → unknown
Korner yoğunluğu 26–30 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_26_30 → boolean → unknown
Korner yoğunluğu 31–35 segmentinde mi oluştu? →set_pieces.corners.high_intensity_segment_31_35 → boolean → unknown
Korner yoğunluğu 36–40 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_36_40 → boolean → unknown
Korner yoğunluğu 41–45 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_41_45 → boolean → unknown

Korner yoğunluğu 46–50 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_46_50 → boolean → unknown
Korner yoğunluğu 51–55 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_51_55 → boolean → unknown
Korner yoğunluğu 56–60 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_56_60 → boolean → unknown
Korner yoğunluğu 61–65 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_61_65 → boolean → unknown
Korner yoğunluğu 66–70 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_66_70 → boolean → unknown
Korner yoğunluğu 71–75 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_71_75 → boolean → unknown

Korner yoğunluğu 76–80 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_76_80 → boolean → unknown
Korner yoğunluğu 81–85 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_81_85 → boolean → unknown
Korner yoğunluğu 86–90 segmentinde mi oluştu? → set_pieces.corners.high_intensity_segment_86_90 → boolean → unknown
Korner yoğunluğu sonrası 1 dakikada net pozisyon oluştu mu? → set_pieces.corners.after_high_intensity.big_chance_window_1m → boolean → unknown
Korner yoğunluğu sonrası 3 dakikada net pozisyon oluştu mu? → set_pieces.corners.after_high_intensity.big_chance_window_3m → boolean → unknown
Korner yoğunluğu sonrası 5 dakikada net pozisyon oluştu mu? → set_pieces.corners.after_high_intensity.big_chance_window_5m → boolean → unknown

Korner yoğunluğu sonrası skor değişti mi? → set_pieces.corners.after_high_intensity.score_changed → boolean → unknown
Korner yoğunluğu sonrası ilk 5 dakikada skor değişti mi? → set_pieces.corners.after_high_intensity.score_changed_window_5m → boolean → unknown
Korner yoğunluğu sonrası duran top savunması tekrar eden risk üretti mi? → set_pieces.corners.after_high_intensity.defending_repeated_risk → boolean → unknown
Korner yoğunluğu sonrası ikinci top kazanımı arttı mı? → set_pieces.corners.after_high_intensity.second_ball_wins_up → boolean → unknown
Korner yoğunluğu sonrası ceza sahası içi şut sayısı arttı mı? → set_pieces.corners.after_high_intensity.box_shots_up → boolean → unknown
Korner yoğunluğu sonrası kornerden dönen toplar tekrar korner üretti mi? → set_pieces.corners.after_high_intensity.rebound_created_more_corners → boolean → unknown
Korner yoğunluğu sonrası kaleci müdahaleleri arttı mı? → set_pieces.corners.after_high_intensity.goalkeeper_interventions_up → boolean → unknown
Korner yoğunluğu sonrası savunma uzaklaştırmaları arttı mı? → set_pieces.corners.after_high_intensity.clearances_up → boolean → unknown

FAZ-7-25
Duran toplar takımın tek skor yolu gibi mi çalıştı? → set_pieces.overall.primary_scoring_route → boolean → unknown
Duran toplar son 10 dakikada takımın tek skor yolu gibi mi çalıştı? → set_pieces.overall.primary_scoring_route_window_last10m → boolean → unknown
Duran toplar ilk 10 dakikada takımın tek skor yolu gibi mi çalıştı? → set_pieces.overall.primary_scoring_route_window_first10m → boolean → unknown

Duran top savunması tekrar eden risk üretti mi? → set_pieces.defending.repeated_risk → boolean → unknown
Duran top savunması aynı bölgeden tekrar eden faul üretti mi? → set_pieces.defending.repeated_fouls_same_zone → boolean → unknown
Duran top savunması aynı bölgeden tekrar eden korner verdi mi? → set_pieces.defending.repeated_corners_conceded_same_zone → boolean → unknown

Maçta serbest vuruş bandı için serbest vuruş yoğunluğu arttı mı? → set_pieces.free_kicks.high_intensity_increased → boolean → unknown
Serbest vuruş yoğunluğu hangi 5 dakikalık pencerede arttı? → set_pieces.free_kicks.high_intensity_window_5m → string → unknown
Maçta serbest vuruş bandı için tehlikeli bölge faulleri oluştu mu? → set_pieces.free_kicks.danger_zone_fouls_occurred → boolean → unknown
Tehlikeli bölge faulleri hangi 5 dakikalık pencerede oluştu? → set_pieces.free_kicks.danger_zone_fouls_window_5m → string → unknown
Maçta serbest vuruş bandı için duran top sonrası şut geldi mi? → set_pieces.free_kicks.after_set_piece.shot_taken → boolean → unknown

Duran top sonrası şut hangi dakikada geldi? → set_pieces.free_kicks.after_set_piece.shot_minute → integer → unknown
Duran top sonrası şut geldikten sonraki 5 dakikada korner oluştu mu? → set_pieces.free_kicks.after_set_piece.corners_occurred_window_5m → boolean → unknown
Duran top sonrası şut geldikten sonraki 5 dakikada net pozisyon oluştu mu? → set_pieces.free_kicks.after_set_piece.big_chance_occurred_window_5m → boolean → unknown
Duran top sonrası şut geldikten sonraki 5 dakikada tempo bandı değişti mi? → set_pieces.free_kicks.after_set_piece.tempo_band_changed_window_5m → boolean → unknown

Maçta aut/taç bandı için oyun sık sık taça gitti mi? → match.flow.throwin.frequency_high → boolean → unknown
Oyun sık sık taça gittiği blok hangi 5 dakikalık penceredeydi? → match.flow.throwin.cluster_window_5m → enum(0_5,5_10,10_15,15_20,20_25,25_30,30_35,35_40,40_45,45_50,50_55,55_60,60_65,65_70,70_75,75_80,80_85,85_90,unknown) → unknown
Maçta aut/taç bandı için tempo düşüşü oluşturdu mu? → match.flow.throwin.caused_tempo_drop → boolean → unknown

Taç yoğunluğu sonrası 1 dakikada tempo bandı düştü mü? → match.flow.throwin.after_cluster.td_tempo_drop_1m → boolean → unknown
Taç yoğunluğu sonrası 3 dakikada tempo bandı düştü mü? → match.flow.throwin.after_cluster.td_tempo_drop_3m → boolean → unknown
Taç yoğunluğu sonrası 5 dakikada tempo bandı düştü mü? → match.flow.throwin.after_cluster.td_tempo_drop_5m → boolean → unknown
Taç yoğunluğu sonrası baskı yönü değişti mi? → match.flow.throwin.after_cluster.pressure_direction_changed → boolean → unknown
Taç yoğunluğu sonrası topa sahip olma taraf değiştirdi mi? → match.flow.throwin.after_cluster.possession_side_changed → boolean → unknown

Bu maçta kaleci ilk 5 dakikada büyük hata yaptı mı? → match.gk.error.major.first_5m → boolean → unknown
Bu maçta kaleci ilk 10 dakikada büyük hata yaptı mı? → match.gk.error.major.first_10m → boolean → unknown
Bu maçta kaleci 15–30 aralığında büyük hata yaptı mı? → match.gk.error.major.min15_30 → boolean → unknown
Bu maçta kaleci 30–45 aralığında büyük hata yaptı mı? → match.gk.error.major.min30_45 → boolean → unknown
Bu maçta kaleci 45–60 aralığında büyük hata yaptı mı? → match.gk.error.major.min45_60 → boolean → unknown
Bu maçta kaleci 60–75 aralığında büyük hata yaptı mı? → match.gk.error.major.min60_75 → boolean → unknown
Bu maçta kaleci 75–90 aralığında büyük hata yaptı mı? → match.gk.error.major.min75_90 → boolean → unknown

Kalecinin büyük hatası hangi dakikada oldu? → match.gk.error.major.minute → integer → unknown
Kalecinin büyük hatası sonrası sonraki 5 dakikada rakip baskı bandı yükseldi mi? → match.gk.error.major.after_5m.opponent_pressure_band_up → boolean → unknown
Kalecinin büyük hatası sonrası sonraki 5 dakikada takım panik bandına girdi mi? → match.gk.error.major.after_5m.team_panic_band_on → boolean → unknown
Kalecinin büyük hatası sonrası sonraki 5 dakikada takım tempo bandı düştü mü? → match.gk.error.major.after_5m.team_tempo_band_down → boolean → unknown

Bu maçta kaleci ilk 5 dakikada kritik kurtarış yaptı mı? → match.gk.save.critical.first_5m → boolean → unknown
Bu maçta kaleci ilk 10 dakikada kritik kurtarış yaptı mı? → match.gk.save.critical.first_10m → boolean → unknown
Bu maçta kaleci 15–30 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min15_30 → boolean → unknown
Bu maçta kaleci 30–45 aralında kritik kurtarış yaptı mı? → match.gk.save.critical.min30_45 → boolean → unknown
Bu maçta kaleci 45–60 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min45_60 → boolean → unknown
Bu maçta kaleci 60–75 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min60_75 → boolean → unknown
Bu maçta kaleci 75–90 aralığında kritik kurtarış yaptı mı? → match.gk.save.critical.min75_90 → boolean → unknown

Kalecinin kritik kurtarışı hangi dakikada oldu? → match.gk.save.critical.minute → integer → unknown
Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım tempo bandı yükseldi mi? → match.gk.save.critical.after_5m.team_tempo_band_up → boolean → unknown
Kalecinin kritik kurtarışı sonrası sonraki 5 dakikada takım moral bandı yükseldi mi? → match.gk.save.critical.after_5m.team_morale_band_up → boolean → unknown

Bu maçta kaleci kurtarış serisi ilk 15 dakikada oluştu mu? → match.gk.save_streak.present.first_15m → boolean → unknown
Bu maçta kaleci kurtarış serisi 15–30 aralığında oluştu mu? → match.gk.save_streak.present.min15_30 → boolean → unknown
Bu maçta kaleci kurtarış serisi 30–45 aralığında oluştu mu? → match.gk.save_streak.present.min30_45 → boolean → unknown
Bu maçta kaleci kurtarış serisi 45–60 aralığında oluştu mu? → match.gk.save_streak.present.min45_60 → boolean → unknown
Bu maçta kaleci kurtarış serisi 60–75 aralığında oluştu mu? → match.gk.save_streak.present.min60_75 → boolean → unknown
Bu maçta kaleci kurtarış serisi 75–90 aralığında oluştu mu? → match.gk.save_streak.present.min75_90 → boolean → unknown

Kalecinin kurtarış serisi hangi dakikalar arasında gerçekleşti? → match.gk.save_streak.window_minutes → string → unknown
Kaleci kurtarış serisi sonrası sonraki 5 dakikada takım kontrol bandı yükseldi mi? → match.gk.save_streak.after_5m.team_control_band_up → boolean → unknown
Kaleci kurtarış serisi sonrası sonraki 5 dakikada rakip tempo bandı düştü mü? → match.gk.save_streak.after_5m.opponent_tempo_band_down → boolean → unknown

Bu maçta kaleci zaman geçirme davranışına ilk 15 dakikada girdi mi? → match.gk.time_waste.present.first_15m → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına 30–45 aralığında girdi mi? → match.gk.time_waste.present.min30_45 → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına 60–75 aralığında girdi mi? → match.gk.time_waste.present.min60_75 → boolean → unknown
Bu maçta kaleci zaman geçirme davranışına 75–90 aralığında girdi mi? → match.gk.time_waste.present.min75_90 → boolean → unknown

Kalecinin zaman geçirme davranışı hangi dakikada başladı? → match.gk.time_waste.start_minute → integer → unknown
Kalecinin zaman geçirme davranışı hangi dakikada bitti? → match.gk.time_waste.end_minute → integer → unknown
Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada maç temposu düştü mü? → match.gk.time_waste.after_5m.match_tempo_band_down → boolean → unknown
Kalecinin zaman geçirme davranışı sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi? → match.gk.time_waste.after_5m.crowd_reaction_band_up → boolean → unknown

Bu maçta kaleci sakatlık/duraklama ile ritmi ilk yarıda bozdu mu? → match.gk.stoppage.rhythm_break.first_half → boolean → unknown
Bu maçta kaleci sakatlık/duraklama ile ritmi ikinci yarıda bozdu mu? → match.gk.stoppage.rhythm_break.second_half → boolean → unknown
Kalecinin sakatlık/duraklaması hangi dakikada oldu? → match.gk.stoppage.minute → integer → unknown
Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada takım baskı bandı düştü mü? → match.gk.stoppage.after_5m.team_pressure_band_down → boolean → unknown
Kalecinin sakatlık/duraklaması sonrası sonraki 5 dakikada rakip baskı bandı düştü mü? → match.gk.stoppage.after_5m.opponent_pressure_band_down → boolean → unknown

Bu maçta kalecinin uzun oyun kurma tercihi ilk 15 dakikada belirginleşti mi? → match.gk.build_up.long_distribution.first_15m → boolean → unknown
Bu maçta kalecinin uzun oyun kurma tercihi 15–30 aralığında belirginleşti mi? → match.gk.build_up.long_distribution.min15_30 → boolean → unknown
Bu maçta kalecinin uzun oyun kurma tercihi 60–75 aralığında belirginleşti mi? → match.gk.build_up.long_distribution.min60_75 → boolean → unknown

Kalecinin uzun oyun kurma tercihi hangi dakikada belirginleşti? → match.gk.build_up.long_distribution.minute → integer → unknown
Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi? → match.gk.build_up.long_distribution.after_5m.turnover_band_up → boolean → unknown
Kalecinin uzun oyun kurma tercihi sonrası sonraki 5 dakikada ikinci top kazanımı arttı mı? → match.gk.build_up.long_distribution.after_5m.second_ball_wins_up → boolean → unknown

Bu maçta kalecinin kısa oyun kurma tercihi ilk 15 dakikada belirginleşti mi? → match.gk.build_up.short_distribution.first_15m → boolean → unknown
Bu maçta kalecinin kısa oyun kurma tercihi 15–30 aralığında belirginleşti mi? → match.gk.build_up.short_distribution.min15_30 → boolean → unknown
Bu maçta kalecinin kısa oyun kurma tercihi 60–75 aralığında belirginleşti mi? → match.gk.build_up.short_distribution.min60_75 → boolean → unknown

Kalecinin kısa oyun kurma tercihi hangi dakikada belirginleşti? → match.gk.build_up.short_distribution.minute → integer → unknown
Kalecinin kısa oyun kurma tercihi sonrası sonraki 5 dakikada baskı altında top kaybı arttı mı? → match.gk.build_up.short_distribution.after_5m.pressure_turnover_up → boolean → unknown
Kalecinin kısa oyun kurma tercihi sonrası sonraki 5 dakikada rakip pres bandı yükseldi mi? → match.gk.build_up.short_distribution.after_5m.opponent_press_band_up → boolean → unknown

Bu maçta forvet ilk 10 dakikada net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min0_10 → boolean → unknown
Bu maçta forvet 10–20 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min10_20 → boolean → unknown
Bu maçta forvet 20–30 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min20_30 → boolean → unknown
Bu maçta forvet 30–45 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min30_45 → boolean → unknown
Bu maçta forvet 45–60 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min45_60 → boolean → unknown
Bu maçta forvet 60–75 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min60_75 → boolean → unknown
Bu maçta forvet 75–90 aralığında net pozisyon kaçırdı mı? → match.fwd.miss.big_chance.min75_90 → boolean → unknown

Forvetin net pozisyon kaçırması hangi dakikada oldu? → match.fwd.miss.big_chance.minute → integer → unknown
Forvetin net pozisyon kaçırması sonrası sonraki 5 dakikada takım panik bandı yükseldi mi? → match.fwd.miss.big_chance.after_5m.team_panic_band_up → boolean → unknown
Forvetin net pozisyon kaçırması sonrası sonraki 5 dakikada takım tempo bandı düştü mü? → match.fwd.miss.big_chance.after_5m.team_tempo_band_down → boolean → unknown

Bu maçta forvet art arda net pozisyon kaçırması ilk yarıda oldu mu? → match.fwd.miss.big_chance_streak.present.first_half → boolean → unknown
Bu maçta forvet art arda net pozisyon kaçırması ikinci yarıda oldu mu? → match.fwd.miss.big_chance_streak.present.second_half → boolean → unknown
Forvetin art arda net pozisyon kaçırması hangi dakikalar arasında oldu? → match.fwd.miss.big_chance_streak.window_minutes → string → unknown
Forvetin art arda net pozisyon kaçırması sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi? → match.fwd.miss.big_chance_streak.after_5m.crowd_reaction_band_up → boolean → unknown
Forvetin art arda net pozisyon kaçırması sonrası sonraki 5 dakikada takım risk_up moduna geçti mi? → match.fwd.miss.big_chance_streak.after_5m.team_risk_up_mode_on → boolean → unknown

Bu maçta forvet baskı yükselince ilk yarıda kart/faul eğilimi arttı mı? → match.fwd.pressure_response.foul_card_tendency_up.first_half → boolean → unknown
Bu maçta forvet baskı yükselince ikinci yarıda kart/faul eğilimi arttı mı? → match.fwd.pressure_response.foul_card_tendency_up.second_half → boolean → unknown
Forvet baskı yükselince kart/faul eğilimi hangi dakikada belirginleşti? → match.fwd.pressure_response.foul_card_tendency_up.minute → integer → unknown
Forvetin kart/faul eğilimi sonrası sonraki 5 dakikada takım oyun akışı kesildi mi? → match.fwd.pressure_response.foul_card_tendency_up.after_5m.team_flow_disrupted → boolean → unknown
Bu maçta forvet baskı yükselince ilk yarıda itiraz dili sertleşti mi? → match.fwd.pressure_response.protest_language_harsh.first_half → boolean → unknown
Bu maçta forvet baskı yükselince ikinci yarıda itiraz dili sertleşti mi? → match.fwd.pressure_response.protest_language_harsh.second_half → boolean → unknown

Forvetin itiraz dili hangi dakikada sertleşti? → match.fwd.pressure_response.protest_language_harsh.minute → integer → unknown
Forvetin itiraz dili sertleşince sonraki 5 dakikada kart riski yükseldi mi? → match.fwd.pressure_response.protest_language_harsh.after_5m.card_risk_up → boolean → unknown
Bu maçta forvet iptal gol sonrası ilk 5 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_disallowed_goal.unstable.first_5m → boolean → unknown
Bu maçta forvet iptal gol sonrası sonraki 15 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_disallowed_goal.unstable.next_15m → boolean → unknown
Forvetin iptal gol sonrası mental kırılma anı hangi dakikada oldu? → match.fwd.mental.after_disallowed_goal.break_minute → integer → unknown
Forvet iptal gol sonrası sonraki 5 dakikada net pozisyon üretimi düştü mü? → match.fwd.mental.after_disallowed_goal.after_5m.big_chance_creation_down → boolean → unknown

Bu maçta forvet VAR sonrası ilk 5 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_var_event.unstable.first_5m → boolean → unknown
Bu maçta forvet VAR sonrası sonraki 15 dakikada mental olarak unstable’a döndü mü? → match.fwd.mental.after_var_event.unstable.next_15m → boolean → unknown
Forvetin VAR sonrası mental kırılma anı hangi dakikada oldu? → match.fwd.mental.after_var_event.break_minute → integer → unknown
Forvet VAR sonrası sonraki 5 dakikada top kaybı bandı yükseldi mi? → match.fwd.mental.after_var_event.after_5m.turnover_band_up → boolean → unknown

Bu maçta forvet penaltı kaçırdı mı? → match.fwd.penalty.missed → boolean → unknown
Forvet penaltıyı hangi dakikada kaçırdı? → match.fwd.penalty.missed_minute → integer → unknown
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada takım tempo bandı düştü mü? → match.fwd.penalty.after_miss_5m.team_tempo_band_down → boolean → unknown
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada takım risk_up moduna geçti mi? → match.fwd.penalty.after_miss_5m.team_risk_up_mode_on → boolean → unknown
Forvetin penaltı kaçırması sonrası sonraki 5 dakikada tribün tepki bandı yükseldi mi? → match.fwd.penalty.after_miss_5m.crowd_reaction_band_up → boolean → unknown

Bu maçta forvet oyundan ilk yarıda çıktı mı? → match.fwd.substituted.off.first_half → boolean → unknown
Bu maçta forvet oyundan ikinci yarıda çıktı mı? → match.fwd.substituted.off.second_half → boolean → unknown

Forvet hangi dakikada oyundan çıktı? → match.fwd.substituted.off_minute → integer → unknown
Forvet oyundan çıkış nedeni taktik mi? → match.fwd.substituted.off_reason.tactical → boolean → unknown
Forvet oyundan çıkış nedeni sakatlık mı? → match.fwd.substituted.off_reason.injury → boolean → unknown
Forvet oyundan çıkınca sonraki 5 dakikada takım net pozisyon üretimi düştü mü? → match.fwd.substituted.after_5m.big_chance_creation_down → boolean → unknown
Forvet oyundan çıkınca sonraki 5 dakikada takım pres bandı düştü mü?→ match.fwd.substituted.after_5m.team_press_band_down → boolean → unknown

Bu maçta orta sahada top kaybı ilk 15 dakikada kümelendi mi? → match.mid.turnover.cluster.first_15m → boolean → unknown
Bu maçta orta sahada top kaybı 15–30 aralığında kümelendi mi? → match.mid.turnover.cluster.min15_30 → boolean → unknown
Bu maçta orta sahada top kaybı 30–45 aralığında kümelendi mi? → match.mid.turnover.cluster.min30_45 → boolean → unknown
Bu maçta orta sahada top kaybı 45–60 aralığında kümelendi mi? → match.mid.turnover.cluster.min45_60 → boolean → unknown
Bu maçta orta sahada top kaybı 60–75 aralığında kümelendi mi? → match.mid.turnover.cluster.min60_75 → boolean → unknown
Bu maçta orta sahada top kaybı 75–90 aralığında kümelendi mi? → match.mid.turnover.cluster.min75_90 → boolean → unknown

Orta saha top kaybı hangi dakikada başladı? → match.mid.turnover.cluster.start_minute → integer → unknown
Orta saha top kaybı hangi dakikada bitti? → match.mid.turnover.cluster.end_minute → integer → unknown
Orta saha top kaybı sonrası sonraki 5 dakikada momentum flip yaşandı mı? → match.mid.turnover.after_5m.momentum_flip → boolean → unknown
Orta saha top kaybı sonrası sonraki 5 dakikada rakip net pozisyon üretti mi? → match.mid.turnover.after_5m.opponent_big_chance_created → boolean → unknown
Orta sahada pas isabeti düşüşü ilk yarıda oldu mu? → match.midfield.pass_accuracy.drop.first_half → boolean → unknown
Orta sahada pas isabeti düşüşü ikinci yarıda oldu mu? → match.midfield.pass_accuracy.drop.second_half → boolean → unknown
Orta sahada pas isabeti düşüşü hangi segmentte belirginleşti? → match.midfield.pass_accuracy.drop.segment → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Orta sahada pas isabeti düşüşü sonrası sonraki 5 dakikada kontrol bandı kaybedildi mi? → match.midfield.pass_accuracy.drop.next5m.control_lost → boolean → unknown

Orta sahada kart birikimi ilk yarıda pas kalitesini düşürdü mü? → match.midfield.cards.accumulation.first_half.pass_quality_down → boolean → unknown
Orta sahada kart birikimi ikinci yarıda pas kalitesini düşürdü mü? → match.midfield.cards.accumulation.second_half.pass_quality_down → boolean → unknown
Orta sahada kart birikimi hangi dakikada kritik seviyeye çıktı? → match.midfield.cards.accumulation.critical_minute → integer → unknown
Orta sahada kart birikimi sonrası sonraki 5 dakikada top kaybı arttı mı? → match.midfield.cards.accumulation.next5m.turnover_up → boolean → unknown
Rakip presi artınca orta saha ilk 15 dakikada kontrol bandını kaybetti mi? → match.midfield.opponent_press_up.control_lost.0_15 → boolean → unknown
Rakip presi artınca orta saha 15–30 aralığında kontrol bandını kaybetti mi? → match.midfield.opponent_press_up.control_lost.15_30 → boolean → unknown
Rakip presi artınca orta saha 60–75 aralığında kontrol bandını kaybetti mi? → match.midfield.opponent_press_up.control_lost.60_75 → boolean → unknown

Orta saha kontrol kaybı hangi dakikada başladı? → match.midfield.control_loss.start_minute → integer → unknown
Orta saha kontrol kaybı sonrası sonraki 5 dakikada savunma hattı geriye yaslandı mı? → match.midfield.control_loss.next5m.defensive_line.dropped → boolean → unknown
Orta saha kontrol kaybı sonrası sonraki 5 dakikada takım uzun topa döndü mü? → match.midfield.control_loss.next5m.team.switched_to_long_ball → boolean → unknown
Bu maçta orta saha değişikliği ilk yarıda oldu mu? → match.midfield.substitution.first_half → boolean → unknown
Bu maçta orta saha değişikliği ikinci yarıda oldu mu? → match.midfield.substitution.second_half → boolean → unknown

Orta saha değişikliği hangi dakikada oldu? → match.midfield.substitution.minute → integer → unknown
Orta saha değişikliği sonrası sonraki 5 dakikada tempo bandı değişti mi? → match.midfield.substitution.next5m.tempo_band.changed → boolean → unknown
Orta saha değişikliği sonrası sonraki 5 dakikada kontrol bandı değişti mi? → match.midfield.substitution.next5m.control_band.changed → boolean → unknown
Orta saha değişikliği sonrası sonraki 5 dakikada topa sahip olma yönü değişti mi? → match.midfield.substitution.next5m.possession_direction.changed → boolean → unknown

Bu maçta savunma hattı ilk 15 dakikada bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.0_15 → boolean → unknown
Bu maçta savunma hattı 15–30 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.15_30 → boolean → unknown
Bu maçta savunma hattı 30–45 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.30_45 → boolean → unknown
Bu maçta savunma hattı 60–75 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.60_75 → boolean → unknown
Bu maçta savunma hattı 75–90 aralığında bir anda geriye yaslandı mı? → match.defensive_line.sudden_drop.75_90 → boolean → unknown

Savunma hattı geriye yaslanma hangi dakikada başladı? → match.defensive_line.drop.start_minute → integer → unknown
Savunma hattı geriye yaslanma sonrası sonraki 5 dakikada risk bandı yükseldi mi? → match.defensive_line.drop.next5m.risk_band.up → boolean → unknown
Savunma hattı geriye yaslanma sonrası sonraki 5 dakikada rakip ceza sahası girişleri arttı mı? → match.defensive_line.drop.next5m.opponent.box_entries.up → boolean → unknown
Bu maçta savunma hattı ilk 15 dakikada öne çıktı mı? → match.defensive_line.step_up.0_15 → boolean → unknown
Bu maçta savunma hattı 15–30 aralığında öne çıktı mı? → match.defensive_line.step_up.15_30 → boolean → unknown
Bu maçta savunma hattı 60–75 aralığında öne çıktı mı? → match.defensive_line.step_up.60_75 → boolean → unknown

Savunma hattı öne çıkış hangi dakikada oldu? → match.defensive_line.step_up.minute → integer → unknown
Savunma hattı öne çıktıktan sonraki 5 dakikada arka koşularla kırıldı mı? → match.defensive_line.step_up.next5m.broken_by_runs → boolean → unknown
Savunma hattı öne çıktıktan sonraki 5 dakikada ofsayta düşürme arttı mı? → match.defensive_line.step_up.next5m.offside_traps.up → boolean → unknown
Bu maçta savunma hattı ofsayt çizgisi ile ilk yarıda ofsayt yoğunluğu üretti mi? → match.defensive_line.offside_trap.first_half.high_volume → boolean → unknown
Bu maçta savunma hattı ofsayt çizgisi ile ikinci yarıda ofsayt yoğunluğu üretti mi? → match.defensive_line.offside_trap.second_half.high_volume → boolean → unknown

Savunma hattı ofsayt yoğunluğu hangi dakikalarda arttı? → match.defensive_line.offside_trap.high_volume.minutes → list → unknown
Savunma hattı ofsayt yoğunluğu sonrası sonraki 5 dakikada rakip koşu denemeleri azaldı mı? → match.defensive_line.offside_trap.high_volume.next5m.opponent.run_attempts.down → boolean → unknown
Bu maçta savunmada bireysel hata zinciri ilk yarıda oluştu mu? → match.defense.individual_error_chain.first_half → boolean → unknown
Bu maçta savunmada bireysel hata zinciri ikinci yarıda oluştu mu? → match.defense.individual_error_chain.second_half → boolean → unknown
Savunmada bireysel hata zinciri hangi dakikalarda oluştu? → match.defense.individual_error_chain.minutes → list → unknown
Savunmada bireysel hata zinciri sonrası sonraki 5 dakikada risk bandı yükseldi mi? → match.defense.individual_error_chain.next5m.risk_band.up → boolean → unknown

Bu maçta savunma hatası sonrası gol yendi mi? → match.defense.error.conceded_goal → boolean → unknown
Savunma hatası sonrası gol hangi dakikada yenildi? → match.defense.error.conceded_goal.minute → integer → unknown
Savunma hatası sonrası sonraki 5 dakikada takım kontrol bandı düştü mü? → match.defense.error.conceded_goal.next5m.team.control_band.down → boolean → unknown
Bu maçta savunma hatası sonrası VAR incelemesi oldu mu? → match.defense.error.var_review.present → boolean → unknown
Savunma hatası sonrası VAR incelemesi hangi dakikada oldu? → match.defense.error.var_review.minute → integer → unknown
VAR incelemesi sonrası sonraki 5 dakikada takım tempo bandı değişti mi? → match.defense.error.var_review.next5m.team.tempo_band.changed → boolean → unknown

Bu maçta savunma hattı kart riski nedeniyle ilk yarıda geri çekildi mi? → match.defensive_line.card_risk.drop.first_half → boolean → unknown
Bu maçta savunma hattı kart riski nedeniyle ikinci yarıda geri çekildi mi? → match.defensive_line.card_risk.drop.second_half → boolean → unknown
Savunma hattı kart riski nedeniyle hangi dakikada geri çekildi? → match.defensive_line.card_risk.drop.minute → integer → unknown
Savunma hattı kart riski nedeniyle geri çekildikten sonraki 5 dakikada rakip baskı bandı yükseldi mi? → match.defensive_line.card_risk.drop.next5m.opponent.pressure_band.up → boolean → unknown

Bu maçta teknik direktör ilk müdahaleyi yaptı mı? → match.coach.first_intervention.present → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi hangi zaman penceesinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Bu maçta teknik direktör ilk müdahaleyi ilk yarıda mı yaptı ikinci yarıda mı? → match.coach.first_intervention.half → enum (first_half,second_half) → unknown
Bu maçta teknik direktör ilk müdahaleyi devre arasına kadar yaptı mı? → match.coach.first_intervention.before_halftime → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi devre arasında mı yaptı? → match.coach.first_intervention.at_halftime → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi devre arası sonrasında ilk 5 dakikada mı yaptı? → match.coach.first_intervention.first5m_after_halftime → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi golden sonraki 5 dakika içinde mi yaptı? → match.coach.first_intervention.next5m_after_scored_goal → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi yenen golden sonraki 5 dakika içinde mi yaptı? → match.coach.first_intervention.next5m_after_conceded_goal → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi yediği baskı dalgasından sonraki 5 dakika içinde mi yaptı? → match.coach.first_intervention.next5m_after_opponent_pressure_wave → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi rakibin kart gördüğü segmentte mi yaptı? → match.coach.first_intervention.during_opponent_card_segment → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi kendi takımının kart gördüğü segmentte mi yaptı? → match.coach.first_intervention.during_team_card_segment → boolean → unknown
Bu maçta teknik direktör ilk müdahaleyi sakatlık / tedavi duraklamasından hemen sonra mı yaptı? → match.coach.first_intervention.after_injury_stoppage → boolean → unknown

Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği oldu mu? → match.coach.first_intervention.type_substitution → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği ise hangi dakikada yaptı? → match.coach.first_intervention.substitution.minute → integer → unknown
Bu maçta teknik direktör ilk müdahalesi oyuncu değişikliği ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.substitution.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Bu maçta teknik direktör ilk müdahalesi rol değişimi oldu mu? → match.coach.first_intervention.type_role_change → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi rol değişimi ise hangi dakikada yaptı? → match.coach.first_intervention.role_change.minute → integer → unknown
Bu maçta teknik direktör ilk müdahalesi rol değişimi ise hangi zaman penceresinde yaptı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.role_change.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi oldu mu? → match.coach.first_intervention.type_formation_change → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi ise hangi dakikada yaptı? → match.coach.first_intervention.formation_change.minute → integer → unknown
Bu maçta teknik direktör ilk müdahalesi diziliş değişimi ise hangi zaman penceresinde yaptı?  (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.coach.first_intervention.formation_change.time_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown

Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu içerdi? → match.coach.first_intervention.target.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi pozisyona yönelikti? → match.coach.first_intervention.target.position → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi hattı etkiledi? (defans / orta saha / hücum) → match.coach.first_intervention.target.line → enum (defense,midfield,attack) → unknown
Bu maçta teknik direktör ilk müdahalesi hangi kanadı etkiledi? (sol / sağ / merkez) → match.coach.first_intervention.target.channel → enum (left,right,center) → unknown

Bu maçta teknik direktör ilk müdahalesi hangi oyuncunun rolünü değiştirdi? → match.coach.first_intervention.role_change.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu farklı hatta taşıdı? → match.coach.first_intervention.role_change.moved_player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuya “kilit görev” verdi? → match.coach.first_intervention.key_task.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi takım kaptanını içerdi mi? → match.coach.first_intervention.involves_captain → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi sarı kartlı bir oyuncuyu çıkarmak için mi yapıldı? → match.coach.first_intervention.substitution.for_booked_player → boolean → unknown

Teknik direktör müdahalesi tempo bandını değiştirdi mi? → match.coach.intervention.tempo_band.changed → boolean → unknown
Teknik direktör müdahalesi tempo bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.tempo_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası tempo bandı tempo_up mı tempo_down mı oldu? → match.coach.intervention.tempo_band.direction → enum (tempo_up,tempo_down) → unknown
Teknik direktör müdahalesi sonrası tempo bandı kaç segment boyunca yeni seviyede kaldı? → match.coach.intervention.tempo_band.duration_segments → integer → unknown
Teknik direktör müdahalesi sonrası tempo bandı kısa bir pik yapıp geri mi döndü? → match.coach.intervention.tempo_band.short_spike_then_revert → boolean → unknown

Teknik direktör müdahalesi kontrol bandını değiştirdi mi? → match.coach.intervention.control_band.changed → boolean → unknown
Teknik direktör müdahalesi kontrol bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.control_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next10m.changed → boolean → unknown

Teknik direktör müdahalesi sonrası kontrol bandı stable’a mı unstable’a mı kaydı? → match.coach.intervention.control_band.direction → enum (stable,unstable) → unknown
Teknik direktör müdahalesi sonrası topa sahip olma yönü değişti mi? → match.coach.intervention.possession_direction.changed → boolean → unknown
Teknik direktör müdahalesi sonrası pas hatası oranı düştü mü? → match.coach.intervention.pass_error_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası top kaybı frekansı düştü mü? → match.coach.intervention.turnover_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası takımın çıkış kalitesi yükseldi mi? → match.coach.intervention.build_up_quality.up → boolean → unknown

Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu içerdi? → match.coach.first_intervention.target.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi pozisyona yönelikti? → match.coach.first_intervention.target.position → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi hattı etkiledi? (defans / orta saha / hücum) → match.coach.first_intervention.target.line → enum (defense,midfield,attack) → unknown
Bu maçta teknik direktör ilk müdahalesi hangi kanadı etkiledi? (sol / sağ / merkez) → match.coach.first_intervention.target.channel → enum (left,right,center) → unknown

Bu maçta teknik direktör ilk müdahalesi hangi oyuncunun rolünü değiştirdi? → match.coach.first_intervention.role_change.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuyu farklı hatta taşıdı? → match.coach.first_intervention.role_change.moved_player → string → unknown
Bu maçta teknik direktör ilk müdahalesi hangi oyuncuya “kilit görev” verdi? → match.coach.first_intervention.key_task.player → string → unknown
Bu maçta teknik direktör ilk müdahalesi takım kaptanını içerdi mi? → match.coach.first_intervention.involves_captain → boolean → unknown
Bu maçta teknik direktör ilk müdahalesi sarı kartlı bir oyuncuyu çıkarmak için mi yapıldı? → match.coach.first_intervention.substitution.for_booked_player → boolean → unknown

Teknik direktör müdahalesi tempo bandını değiştirdi mi? → match.coach.intervention.tempo_band.changed → boolean → unknown
Teknik direktör müdahalesi tempo bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.tempo_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada tempo bandı değişti mi? → match.coach.intervention.tempo_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası tempo bandı tempo_up mı tempo_down mı oldu? → match.coach.intervention.tempo_band.direction → enum (tempo_up,tempo_down) → unknown
Teknik direktör müdahalesi sonrası tempo bandı kaç segment boyunca yeni seviyede kaldı? → match.coach.intervention.tempo_band.duration_segments → integer → unknown
Teknik direktör müdahalesi sonrası tempo bandı kısa bir pik yapıp geri mi döndü? → match.coach.intervention.tempo_band.short_spike_then_revert → boolean → unknown

Teknik direktör müdahalesi kontrol bandını değiştirdi mi? → match.coach.intervention.control_band.changed → boolean → unknown
Teknik direktör müdahalesi kontrol bandını hangi dakikadan itibaren değiştirdi? → match.coach.intervention.control_band.change_start_minute → integer → unknown
Teknik direktör müdahalesi sonrası ilk 5 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next5m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası ilk 10 dakikada kontrol bandı değişti mi? → match.coach.intervention.control_band.next10m.changed → boolean → unknown
Teknik direktör müdahalesi sonrası kontrol bandı stable’a mı unstable’a mı kaydı? → match.coach.intervention.control_band.direction → enum (stable,unstable) → unknown
Teknik direktör müdahalesi sonrası topa sahip olma yönü değişti mi? → match.coach.intervention.possession_direction.changed → boolean → unknown
Teknik direktör müdahalesi sonrası pas hatası oranı düştü mü? → match.coach.intervention.pass_error_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası top kaybı frekansı düştü mü? → match.coach.intervention.turnover_rate.down → boolean → unknown
Teknik direktör müdahalesi sonrası takımın çıkış kalitesi yükseldi mi? → match.coach.intervention.build_up_quality.up → boolean → unknown

Kırmızı kart sonrası plan deterministik değişti mi? → match.inplay.red_card.after.plan_change.is_deterministic → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 5 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_5m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 10 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_10m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi hangi müdahale ile oldu? (oyuncu değişikliği / rol değişimi / diziliş değişimi) → match.inplay.red_card.after.plan_change.intervention_type → enum(substitution, role_change, formation_change) → unknown
Kırmızı kart sonrası plan değişimi hangi oyuncuyu etkiledi? → match.inplay.red_card.after.plan_change.affected_player → string → unknown
Kırmızı kart sonrası diziliş değişti mi? → match.inplay.red_card.after.formation_change.is_occurred → boolean → unknown
Kırmızı kart sonrası diziliş hangi dakikada değişti? → match.inplay.red_card.after.formation_change.minute → integer → unknown

Kırmızı kart sonrası diziliş değişimi kaç dakika içinde yapıldı? → match.inplay.red_card.after.formation_change.within_minutes → integer → unknown
Kırmızı kart sonrası diziliş değişimi hangi forma dönüşüyle oldu? (4’lüden 5’liye / 3’lüye / çift forvete) → match.inplay.red_card.after.formation_change.to_shape → enum(back4_to_back5, back4_to_back3, to_two_strikers) → unknown
Kırmızı kart sonrası diziliş değişimi hücum gücünü düşürdü mü? → match.inplay.red_card.after.formation_change.reduces_attacking_power → boolean → unknown
Kırmızı kart sonrası diziliş değişimi ceza sahası savunmasını güçlendirdi mi? → match.inplay.red_card.after.formation_change.strengthens_box_defense → boolean → unknown

Takım öndeyken kapanmayı mı seçti yoksa ikinci gol mü aradı? → match.inplay.leading.team_plan.choice → enum(close_down, push_second_goal) → unknown
Takım öndeyken plan tercihi hangi dakikada netleşti? → match.inplay.leading.team_plan.choice_minute → integer → unknown
Takım öndeyken plan tercihi gol sonrası ilk 5 dakikada netleşti mi? → match.inplay.leading.team_plan.choice_settled.first_5m_after_goal → boolean → unknown
Takım öndeyken kapanmayı seçtiyse hangi hat derinleşti? → match.inplay.leading.close_down.deepened_line → enum(defense_line, midfield_line, forward_line) → unknown
Takım öndeyken kapanmayı seçtiyse tempo bandı düştü mü? → match.inplay.leading.close_down.tempo_band.down.is_started → boolean → unknown
Takım öndeyken kapanmayı seçtiyse kontrol bandı stable’a mı kilitlendi? → match.inplay.leading.close_down.control_band.locks_stable → boolean → unknown

Takım öndeyken ikinci golü aradıysa hangi kanattan yükledi? → match.inplay.leading.push_second_goal.attack_wing → enum(left, right) → unknown
Takım öndeyken ikinci golü aradıysa şut frekansı arttı mı? → match.inplay.leading.push_second_goal.shot_frequency.increases → boolean → unknown
Takım öndeyken ikinci golü aradıysa risk_up kaç segment sürdü? → match.inplay.leading.push_second_goal.risk_up.duration_segments → integer → unknown
Takım öndeyken time-waste davranışına izin verdi mi? → match.inplay.leading.time_waste.is_allowed → boolean → unknown
Takım öndeyken time-waste davranışı hangi dakikada başladı? → match.inplay.leading.time_waste.start_minute → integer → unknown
Takım öndeyken time-waste davranışı hangi zaman penceresinde arttı? (61-75 / 76-90+) → match.inplay.leading.time_waste.increase_window → enum(min61_75, min76_90plus) → unknown
Takım öndeyken time-waste davranışı sonrası tempo bandı düştü mü? → match.inplay.leading.time_waste.after.tempo_band.down.is_started → boolean → unknown
Takım öndeyken time-waste davranışı sonrası hakem uyarıları arttı mı? → match.inplay.leading.time_waste.after.ref_warnings.increase → boolean → unknown

Kırmızı kart sonrası plan deterministik değişti mi? → match.inplay.red_card.after.plan_change.is_deterministic → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 5 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_5m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 10 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_10m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi hangi müdahale ile oldu? (oyuncu değişikliği / rol değişimi / diziliş değişimi) → match.inplay.red_card.after.plan_change.intervention_type → enum(substitution, role_change, formation_change) → unknown
Kırmızı kart sonrası plan değişimi hangi oyuncuyu etkiledi? → match.inplay.red_card.after.plan_change.affected_player → string → unknown

Kırmızı kart sonrası diziliş değişti mi? → match.inplay.red_card.after.formation_change.is_occurred → boolean → unknown
Kırmızı kart sonrası diziliş hangi dakikada değişti? → match.inplay.red_card.after.formation_change.minute → integer → unknown
Kırmızı kart sonrası diziliş değişimi kaç dakika içinde yapıldı? → match.inplay.red_card.after.formation_change.within_minutes → integer → unknown
Kırmızı kart sonrası diziliş değişimi hangi forma dönüşüyle oldu? (4’lüden 5’liye / 3’lüye / çift forvete) → match.inplay.red_card.after.formation_change.to_shape → enum(back4_to_back5, back4_to_back3, to_two_strikers) → unknown
Kırmızı kart sonrası diziliş değişimi hücum gücünü düşürdü mü? → match.inplay.red_card.after.formation_change.reduces_attacking_power → boolean → unknown
Kırmızı kart sonrası diziliş değişimi ceza sahası savunmasını güçlendirdi mi? → match.inplay.red_card.after.formation_change.strengthens_box_defense → boolean → unknown

Takım öndeyken kapanmayı mı seçti yoksa ikinci gol mü aradı? → match.inplay.leading.team_plan.choice → enum(close_down, push_second_goal) → unknown
Takım öndeyken plan tercihi hangi dakikada netleşti? → match.inplay.leading.team_plan.choice_minute → integer → unknown
Takım öndeyken plan tercihi gol sonrası ilk 5 dakikada netleşti mi? → match.inplay.leading.team_plan.choice_settled.first_5m_after_goal → boolean → unknown
Takım öndeyken kapanmayı seçtiyse hangi hat derinleşti? → match.inplay.leading.close_down.deepened_line → enum(defense_line, midfield_line, forward_line) → unknown
Takım öndeyken kapanmayı seçtiyse tempo bandı düştü mü? → match.inplay.leading.close_down.tempo_band.down.is_started → boolean → unknown
Takım öndeyken kapanmayı seçtiyse kontrol bandı stable’a mı kilitlendi? → match.inplay.leading.close_down.control_band.locks_stable → boolean → unknown

Takım öndeyken ikinci golü aradıysa hangi kanattan yükledi? → match.inplay.leading.push_second_goal.attack_wing → enum(left, right) → unknown
Takım öndeyken ikinci golü aradıysa şut frekansı arttı mı? → match.inplay.leading.push_second_goal.shot_frequency.increases → boolean → unknown
Takım öndeyken ikinci golü aradıysa risk_up kaç segment sürdü? → match.inplay.leading.push_second_goal.risk_up.duration_segments → integer → unknown
Takım öndeyken time-waste davranışına izin verdi mi? → match.inplay.leading.time_waste.is_allowed → boolean → unknown

Takım öndeyken time-waste davranışı hangi dakikada başladı? → match.inplay.leading.time_waste.start_minute → integer → unknown
Takım öndeyken time-waste davranışı hangi zaman penceresinde arttı? (61-75 / 76-90+) → match.inplay.leading.time_waste.increase_window → enum(min61_75, min76_90plus) → unknown
Takım öndeyken time-waste davranışı sonrası tempo bandı düştü mü? → match.inplay.leading.time_waste.after.tempo_band.down.is_started → boolean → unknown
Takım öndeyken time-waste davranışı sonrası hakem uyarıları arttı mı? → match.inplay.leading.time_waste.after.ref_warnings.increase → boolean → unknown

Kırmızı kart sonrası plan deterministik değişti mi? → match.inplay.red_card.after.plan_change.is_deterministic → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 5 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_5m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi ilk 10 dakikada mı oldu? → match.inplay.red_card.after.plan_change.first_10m.is_occurred → boolean → unknown
Kırmızı kart sonrası plan değişimi hangi müdahale ile oldu? (oyuncu değişikliği / rol değişimi / diziliş değişimi) → match.inplay.red_card.after.plan_change.intervention_type → enum(substitution, role_change, formation_change) → unknown
Kırmızı kart sonrası plan değişimi hangi oyuncuyu etkiledi? → match.inplay.red_card.after.plan_change.affected_player → string → unknown

Kırmızı kart sonrası diziliş değişti mi? → match.inplay.red_card.after.formation_change.is_occurred → boolean → unknown
Kırmızı kart sonrası diziliş hangi dakikada değişti? → match.inplay.red_card.after.formation_change.minute → integer → unknown
Kırmızı kart sonrası diziliş değişimi kaç dakika içinde yapıldı? → match.inplay.red_card.after.formation_change.within_minutes → integer → unknown
Kırmızı kart sonrası diziliş değişimi hangi forma dönüşüyle oldu? (4’lüden 5’liye / 3’lüye / çift forvete) → match.inplay.red_card.after.formation_change.to_shape → enum(back4_to_back5, back4_to_back3, to_two_strikers) → unknown
Kırmızı kart sonrası diziliş değişimi hücum gücünü düşürdü mü? → match.inplay.red_card.after.formation_change.reduces_attacking_power → boolean → unknown
Kırmızı kart sonrası diziliş değişimi ceza sahası savunmasını güçlendirdi mi? → match.inplay.red_card.after.formation_change.strengthens_box_defense → boolean → unknown

Takım öndeyken kapanmayı mı seçti yoksa ikinci gol mü aradı? → match.inplay.leading.team_plan.choice → enum(close_down, push_second_goal) → unknown
Takım öndeyken plan tercihi hangi dakikada netleşti? → match.inplay.leading.team_plan.choice_minute → integer → unknown
Takım öndeyken plan tercihi gol sonrası ilk 5 dakikada netleşti mi? → match.inplay.leading.team_plan.choice_settled.first_5m_after_goal → boolean → unknown
Takım öndeyken kapanmayı seçtiyse hangi hat derinleşti? → match.inplay.leading.close_down.deepened_line → enum(defense_line, midfield_line, forward_line) → unknown
Takım öndeyken kapanmayı seçtiyse tempo bandı düştü mü? → match.inplay.leading.close_down.tempo_band.down.is_started → boolean → unknown
Takım öndeyken kapanmayı seçtiyse kontrol bandı stable’a mı kilitlendi? → match.inplay.leading.close_down.control_band.locks_stable → boolean → unknown

Takım öndeyken ikinci golü aradıysa hangi kanattan yükledi? → match.inplay.leading.push_second_goal.attack_wing → enum(left, right) → unknown
Takım öndeyken ikinci golü aradıysa şut frekansı arttı mı? → match.inplay.leading.push_second_goal.shot_frequency.increases → boolean → unknown
Takım öndeyken ikinci golü aradıysa risk_up kaç segment sürdü? → match.inplay.leading.push_second_goal.risk_up.duration_segments → integer → unknown
Takım öndeyken time-waste davranışına izin verdi mi? → match.inplay.leading.time_waste.is_allowed → boolean → unknown
Takım öndeyken time-waste davranışı hangi dakikada başladı? → match.inplay.leading.time_waste.start_minute → integer → unknown
Takım öndeyken time-waste davranışı hangi zaman penceresinde arttı? (61-75 / 76-90+) → match.inplay.leading.time_waste.increase_window → enum(min61_75, min76_90plus) → unknown
Takım öndeyken time-waste davranışı sonrası tempo bandı düştü mü? → match.inplay.leading.time_waste.after.tempo_band.down.is_started → boolean → unknown
Takım öndeyken time-waste davranışı sonrası hakem uyarıları arttı mı? → match.inplay.leading.time_waste.after.ref_warnings.increase → boolean → unknown

Maç içinde tribün protestosu oldu mu? → match.crowd.protest.occurred → boolean → unknown
Maç içinde tribün protestosu kaç kez tekrar etti? → match.crowd.protest.repeat_count → integer → unknown
Maç içinde tribün protestosu tek dalga mıydı çoklu dalga mıydı? → match.crowd.protest.wave_type → enum (single_wave,multi_wave) → unknown
Maç içinde tribün protestosu ilk kez hangi dakikada başladı? → match.crowd.protest.first_start_minute → integer → unknown
Maç içinde tribün protestosu ilk kez hangi zaman penceresinde başladı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.crowd.protest.first_start_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Maç içinde tribün protestosu devre arası öncesi mi başladı devre arası sonrası mı? → match.crowd.protest.first_start_halftime_side → enum (before_halftime,after_halftime) → unknown

Maç içinde tribün protestosu golden sonra mı başladı? → match.crowd.protest.trigger_after_goal_scored → boolean → unknown
Maç içinde tribün protestosu yenen golden sonra mı başladı? → match.crowd.protest.trigger_after_goal_conceded → boolean → unknown
Maç içinde tribün protestosu hakem kararından sonra mı başladı? → match.crowd.protest.trigger_after_referee_decision → boolean → unknown
Maç içinde tribün protestosu VAR incelemesinden sonra mı başladı? → match.crowd.protest.trigger_after_var_review → boolean → unknown
Maç içinde tribün protestosu kırmızı karttan sonra mı başladı? → match.crowd.protest.trigger_after_red_card → boolean → unknown

Tribün protestosu dalga dalga tekrar etti mi? → match.crowd.protest.waves_repeated → boolean → unknown
Tribün protestosu dalgaları arasında kaç dakika vardı? → match.crowd.protest.wave_gap_minutes → integer → unknown
Tribün protestosu dalgaları her seferinde daha mı yükseldi daha mı düştü?→ match.crowd.protest.wave_trend → enum (increasing,decreasing) → unknown
Tribün baskısı ilk kez hangi segmentte yükseldi? → match.crowd.pressure.first_rise_segment → enum (segment_0_15,segment_16_30,segment_31_45,segment_46_60,segment_61_75,segment_76_90_plus) → unknown
Tribün baskısı yükselişi hangi dakikada başladı? → match.crowd.pressure.rise_start_minute → integer → unknown
Tribün baskısı yükselişi hangi zaman penceresinde başladı? (0-15 / 16-30 / 31-45 / 46-60 / 61-75 / 76-90+) → match.crowd.pressure.rise_start_window → enum (0_15,16_30,31_45,46_60,61_75,76_90_plus) → unknown
Tribün baskısı yükselişi hangi tetikleyiciyle başladı?(gol / yenen gol / kaçan pozisyon / hakem kararı / kart / protesto) → match.crowd.pressure.rise_trigger → enum(goal_scored,goal_conceded,missed_chance,referee_decision,card,protest) → unknown

Tribün baskısı yükselince takımın ilk tepkisi tempo_up mı tempo_down mıydı? → match.crowd.pressure.team_first_response.tempo_direction → enum (tempo_up,tempo_down) → unknown
Tribün baskısı yükselince takımın ilk 5 dakikalık tepkisi tempo_up mı tempo_down mıydı? → match.crowd.pressure.team_response_next5m.tempo_direction → enum (tempo_up,tempo_down) → unknown
Tribün baskısı yükselince takımın ilk tepkisi hangi dakikada başladı? → match.crowd.pressure.team_first_response.start_minute → integer → unknown
Tribün baskısı yükselince takımın ilk tepkisi hangi oyuncu grubundan geldi? →(defans / orta saha / hücum) → match.crowd.pressure.team_first_response.actor_group → enum (defense,midfield,attack) → unknown


Tribün baskısı yükselince takım panik hücum dalgasına girdi mi? → match.crowd.pressure.panic_attack_wave.entered → boolean → unknown
Tribün baskısı yükselince takım panik hücum dalgası hangi dakikada başladı? → match.crowd.pressure.panic_attack_wave.start_minute → integer → unknown
Tribün baskısı yükselince takım panik hücum dalgası kaç dakika sürdü? → match.crowd.pressure.panic_attack_wave.duration_minutes → integer → unknown
Tribün baskısı yükselince takım panik hücum dalgası sonrası ilk 5 dakikada top kaybı arttı mı? → match.crowd.pressure.panic_attack_wave.turnover_increase_next5m → boolean → unknown
Tribün baskısı yükselince takım kontrol bandı unstable’a kaydı mı? → match.crowd.pressure.control_to_unstable → boolean → unknown
Tribün baskısı yükselince takım kontrol bandı unstable’a hangi dakikada kaydı? → match.crowd.pressure.control_to_unstable_minute → integer → unknown
Tribün baskısı yükselince takım kontrol bandı unstable’a kaydıktan sonra ilk 5 dakikada pas hatası arttı mı? → match.crowd.pressure.unstable_after_effect.pass_error_increase_next5m → boolean → unknown

Tribün baskısı yükselince takım kart/faul yoğunluğunu artırdı mı? → match.crowd.pressure.foul_card_intensity_increase → boolean → unknown
Tribün baskısı yükselince takım faul yoğunluğu ilk 5 dakikada arttı mı? → match.crowd.pressure.foul_intensity_increase_next5m → boolean → unknown
Tribün baskısı yükselince takım kart faul yoğunluğu artışı hangi oyuncu grubunda oldu? → match.crowd.pressure.foul_card_increase_actor_group → enum (defense,midfield,attack) → unknown
Tribün baskısı yükselince takım kart faul yoğunluğu artışı hangi bölgeye kaydı? → match.crowd.pressure.foul_card_increase_zone → enum (defensive_third,middle_third,attacking_third) → unknown


Tribün baskısı yükselince teknik direktör daha erken müdahale yaptı mı? → match.crowd.pressure.coach_intervention.earlier_than_normal → boolean → unknown
Tribün baskısı yükselince teknik direktör müdahalesi kaç dakika içinde geldi? → match.crowd.pressure.coach_intervention.response_minutes → integer → unknown
Tribün baskısı yükselince teknik direktör müdahalesi tribün yükselişinden sonraki ilk 5 dakikada mı geldi? → match.crowd.pressure.coach_intervention.within_first5m → boolean → unknown
Tribün baskısı yükselince teknik direktör müdahalesi hangi müdahale tipiydi? (değişiklik / rol / diziliş) → match.crowd.pressure.coach_intervention.type → enum (substitution,role_change,formation_change) → unknown
Tribün baskısı yükselince hakem düdük sıklığını artırdı mı? → match.crowd.pressure.referee_whistle_frequency_increase → boolean → unknown
Tribün baskısı yükselince hakem düdük sıklığı hangi dakikadan itibaren arttı? → match.crowd.pressure.referee_whistle_increase_minute → integer → unknown
Tribün baskısı yükselince hakem düdük sıklığı ilk 5 dakikada arttı mı? → match.crowd.pressure.referee_whistle_increase_next5m → boolean → unknown

Tribün baskısı yükselince hakem kart standardı sertleşti mi? → match.crowd.pressure.referee_card_standard_hardened → boolean → unknown
Tribün baskısı yükselince hakem kart standardı sertleşmesi hangi dakikada başladı? → match.crowd.pressure.referee_card_standard_harden_start_minute → integer → unknown
Tribün baskısı yükselince hakem kart standardı sertleşmesi sonrası ilk 5 dakikada kart sayısı arttı mı? → match.crowd.pressure.referee_card_harden_effect.card_count_increase_next5m → boolean → unknown
Tribün baskısı yükselince oyuncu itirazları kümelendi mi? → match.crowd.pressure.player_complaints.clustered → boolean → unknown
Tribün baskısı yükselince oyuncu itirazları hangi dakikada kümelendi? → match.crowd.pressure.player_complaints.cluster_start_minute → integer → unknown
Tribün baskısı yükselince oyuncu itirazları hangi takımda arttı? → match.crowd.pressure.player_complaints.team_side → enum (home,away) → unknown
Tribün baskısı yükselince oyuncu itirazları sonrası kart çıktı mı? → match.crowd.pressure.player_complaints.card_afterwards → boolean → unknown
Tribün baskısı yükselince oyuncu itirazları sonrası kart hangi dakikada çıktı? → match.crowd.pressure.player_complaints.card_minute → integer → unknown

Tribün baskısı sonrası maç içinde sahaya madde atma oldu mu? → match.crowd.incident.throwing_objects.occurred → boolean → unknown
Tribün baskısı sonrası sahaya madde atma hangi dakikada oldu? → match.crowd.incident.throwing_objects.first_minute → integer → unknown
Tribün baskısı sonrası sahaya madde atma kaç kez tekrar etti? → match.crowd.incident.throwing_objects.repeat_count → integer → unknown
Tribün baskısı sonrası sahaya madde atma hangi tribünden geldi? → match.crowd.incident.throwing_objects.stand_side → enum (home_stand,away_stand,unknown) → unknown
Sahaya madde atma olayı oyunu 2 dakikadan uzun durdurdu mu? → match.crowd.incident.throwing_objects.stoppage_over_2m → boolean → unknown
Sahaya madde atma olayı oyunu kaç dakika durdurdu? → match.crowd.incident.throwing_objects.stoppage_minutes → integer → unknown
Sahaya madde atma olayı sonrası tempo bandı düştü mü? → match.crowd.incident.throwing_objects.effect.tempo_down → boolean → unknown
Sahaya madde atma olayı sonrası kontrol bandı kayboldu mu? → match.crowd.incident.throwing_objects.effect.control_lost → boolean → unknown

Tribün baskısı sonrası güvenlik uyarısı veya anons yapıldı mı? → match.crowd.security_announcement.occurred → boolean → unknown
Tribün baskısı sonrası güvenlik anonsu hangi dakikada yapıldı? → match.crowd.security_announcement.first_minute → integer → unknown
Tribün baskısı sonrası güvenlik anonsu kaç kez tekrar etti? → match.crowd.security_announcement.repeat_count → integer → unknown
Tribün baskısı sonrası maçın kontrolü kayboldu mu? → match.crowd.pressure.after_effect.match_control_lost → boolean → unknown
Tribün baskısı sonrası maçın kontrolü hangi dakikada kayboldu? → match.crowd.pressure.after_effect.match_control_lost_minute → integer → unknown
Tribün baskısı sonrası maçın kontrolü kaybolduktan sonra ilk 5 dakikada kart/faul arttı mı? → match.crowd.pressure.after_effect.card_foul_increase_next5m → boolean → unknown

Tribün baskısı hangi takım aleyhine yoğunlaştı? → match.crowd.pressure.target_team_side → enum (home,away) → unknown
Tribün baskısı hangi dakikada belirli bir takıma yöneldi? → match.crowd.pressure.target_team_start_minute → integer → unknown
Tribün baskısı hangi zaman penceresinde belirli bir takıma yöneldi? (31-45 / 46-60 / 61-75 / 76-90+) → match.crowd.pressure.target_team_start_window → enum (31_45,46_60,61_75,76_90_plus) → unknown
Tribün baskısı “hakem hedef” mi “oyuncu hedef” mi “yönetim hedef” mi taşıdı? → match.crowd.pressure.target_type → enum (referee_target,player_target,management_target) → unknown
Tribün baskısı hakem hedefli ise hangi karar tetikledi? → match.crowd.pressure.referee_target.trigger_decision → enum (foul_decision,card_decision,penalty_decision,var_decision,offside_decision,unknown) → unknown

Tribün baskısı oyuncu hedefli ise hangi oyuncu hedef oldu? → match.crowd.pressure.player_target.player_reference → string → unknown
Tribün baskısı yönetim hedefli ise hangi olay tetikledi? → match.crowd.pressure.management_target.trigger_event → enum (transfer_policy,coach_decision,club_statement,board_action,unknown) → unknown
Tribün baskısı belirli bir oyuncuya yöneldi mi?→ match.crowd.pressure.player_target.occurred → boolean → unknown
Tribün baskısı belirli bir oyuncuya hangi dakikada yöneldi? → match.crowd.pressure.player_target.start_minute → integer → unknown
Tribün baskısı belirli bir oyuncuya yönelme kaç dakika sürdü? → match.crowd.pressure.player_target.duration_minutes → integer → unknown

Tribün baskısı belirli bir oyuncuyu oyundan düşürdü mü? → match.crowd.pressure.player_target.effect.player_performance_drop → boolean → unknown
Tribün baskısı belirli bir oyuncuyu oyundan düşürdüyse hangi dakikadan itibaren performans düştü? → match.crowd.pressure.player_target.effect.performance_drop_start_minute → integer → unknown
Tribün baskısı belirli bir oyuncuyu oyundan düşürdükten sonra ilk 5 dakikada top kaybı arttı mı? → match.crowd.pressure.player_target.effect.turnover_increase_next5m → boolean → unknown
Tribün baskısı sonrası takımın pas hatası arttı mı? → match.crowd.pressure.after_effect.pass_error_increase → boolean → unknow
Tribün baskısı sonrası pas hatası artışı hangi dakikada başladı? → match.crowd.pressure.after_effect.pass_error_increase_start_minute → integer → unknown
Tribün baskısı sonrası pas hatası artışı kaç dakika sürdü? → match.crowd.pressure.after_effect.pass_error_increase_duration_minutes → integer → unknown

Tribün baskısı sonrası top kaybı arttı mı? → match.crowd.pressure.after_effect.turnover_increase → boolean → unknown
Tribün baskısı sonrası top kaybı artışı hangi dakikada başladı? → match.crowd.pressure.after_effect.turnover_increase_start_minute → integer → unknown
Tribün baskısı sonrası top kaybı artışı kaç dakika sürdü? → match.crowd.pressure.after_effect.turnover_increase_duration_minutes → integer → unknown
Tribün baskısı sonrası takımın disiplin bandı aggressive’e kaydı mı?  → match.crowd.pressure.after_effect.discipline_to_aggressive → boolean → unknown
Tribün baskısı sonrası disiplin bandı aggressive’e kayma hangi dakikada oldu? → match.crowd.pressure.after_effect.discipline_to_aggressive_minute → integer → unknown
Tribün baskısı sonrası disiplin bandı aggressive’e kayma sonrası ilk 5 dakikada kart sayısı arttı mı? → match.crowd.pressure.after_effect.aggressive_effect.card_count_increase_next5m → boolean → unknown

Tribün baskısı sonrası takımın tempo taşıma gücü düştü mü? → match.crowd.pressure.after_effect.tempo_carrying_power_drop → boolean → unknown
Tribün baskısı sonrası tempo taşıma gücü düşüşü hangi dakikada başladı? → match.crowd.pressure.after_effect.tempo_carrying_power_drop_start_minute → integer → unknown
Tribün baskısı sonrası tempo taşıma gücü düşüşü kaç segment sürdü? → match.crowd.pressure.after_effect.tempo_carrying_power_drop_duration_segments → integer → unknown
Tribün baskısı sonrası deplasman takımı panic bandına girdi mi? → match.crowd.pressure.after_effect.away_team_to_panic → boolean → unknown
Tribün baskısı sonrası deplasman takımı panic bandına girişi hangi dakikada oldu? → match.crowd.pressure.after_effect.away_team_to_panic_minute → integer → unknown
Tribün baskısı sonrası deplasman takımı panic bandına girdikten sonra ilk 5 dakikada top kaybı arttı mı? → match.crowd.pressure.after_effect.away_panic_effect.turnover_increase_next5m → boolean → unknown

Tribün baskısı sonrası iç saha takımı kontrolü kilitledi mi? → match.crowd.pressure.after_effect.home_team_control_locked → boolean → unknown
Tribün baskısı sonrası iç saha takımı kontrolü kilitlemesi hangi dakikada başladı? → match.crowd.pressure.after_effect.home_team_control_locked_start_minute → integer → unknown
Tribün baskısı sonrası iç saha takımı kontrolü kilitledikten sonra tempo bandı düştü mü? → match.crowd.pressure.after_effect.home_control_lock_effect.tempo_down → boolean → unknown
Tribün baskısı sonrası hakemle tartışma görüntüleri arttı mı? → match.crowd.pressure.after_effect.referee_arguments_increase → boolean → unknown
Tribün baskısı sonrası hakemle tartışma artışı hangi dakikada başladı? → match.crowd.pressure.after_effect.referee_arguments_increase_start_minute → integer → unknown
Tribün baskısı sonrası hakemle tartışma artışı kaç dakika sürdü? → match.crowd.pressure.after_effect.referee_arguments_increase_duration_minutes → integer → unknown

Tribün baskısı maç sonunda taşkınlık riskine döndü mü? → match.crowd.pressure.endgame.misconduct_risk → boolean → unknown
Tribün baskısı maç sonunda taşkınlık riski hangi dakikada yükseldi? → match.crowd.pressure.endgame.misconduct_risk_rise_minute → integer → unknown
Tribün baskısı maç sonunda taşkınlık riski güvenlik müdahalesine döndü mü? → match.crowd.pressure.endgame.security_intervention_triggered → boolean → unknown

Maçın toplam koşu mesafesi verisi ilk yarı için mevcut mu? → match.physical.run_distance.total.availability.first_half → boolean → unknown
Maçın toplam koşu mesafesi verisi ikinci yarı için mevcut mu? → match.physical.run_distance.total.availability.second_half → boolean → unknown
Maçın toplam koşu mesafesi verisi 0–15 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m00_15 → boolean → unknown
Maçın toplam koşu mesafesi verisi 16–30 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m16_30 → boolean → unknown
Maçın toplam koşu mesafesi verisi 31–45+ aralığı için mevcut mu? → match.physical.run_distance.total.availability.m31_45p → boolean → unknown
Maçın toplam koşu mesafesi verisi 46–60 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m46_60 → boolean → unknown
Maçın toplam koşu mesafesi verisi 61–75 aralığı için mevcut mu? → match.physical.run_distance.total.availability.m61_75 → boolean → unknown
Maçın toplam koşu mesafesi verisi 76–90+ aralığı için mevcut mu? → match.physical.run_distance.total.availability.m76_90p → boolean → unknown

Maçın takım bazlı toplam koşu mesafesi verisi ilk yarı için mevcut mu? → match.physical.run_distance.team_total.availability.first_half → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi ikinci yarı için mevcut mu? → match.physical.run_distance.team_total.availability.second_half → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 0–15 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m00_15 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 16–30 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m16_30 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 31–45+ aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m31_45p → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 46–60 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m46_60 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 61–75 aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m61_75 → boolean → unknown
Maçın takım bazlı toplam koşu mesafesi verisi 76–90+ aralığı için mevcut mu? → match.physical.run_distance.team_total.availability.m76_90p → boolean → unknown

Maçın oyuncu bazlı koşu mesafesi verisi ilk yarı için mevcut mu? → match.physical.run_distance.player.availability.first_half → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi ikinci yarı için mevcut mu? → match.physical.run_distance.player.availability.second_half → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 0–15 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m00_15 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 16–30 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m16_30 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 31–45+ aralığı için mevcut mu? → match.physical.run_distance.player.availability.m31_45p → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 46–60 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m46_60 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 61–75 aralığı için mevcut mu? → match.physical.run_distance.player.availability.m61_75 → boolean → unknown
Maçın oyuncu bazlı koşu mesafesi verisi 76–90+ aralığı için mevcut mu? → match.physical.run_distance.player.availability.m76_90p → boolean → unknown

Maç içinde en çok koşan ilk 3 oyuncu ilk yarı özelinde kimdi? → match.physical.run_distance.leaders.top3.players.first_half → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu ikinci yarı özelinde kimdi? → match.physical.run_distance.leaders.top3.players.second_half → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 0–15 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m00_15 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 16–30 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m16_30 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 31–45+ aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m31_45p → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 46–60 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m46_60 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 61–75 aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m61_75 → list(object) → unknown
Maç içinde en çok koşan ilk 3 oyuncu 76–90+ aralığında kimdi? → match.physical.run_distance.leaders.top3.players.m76_90p → list(object) → unknown

Maç içinde en çok koşan ilk 5 oyuncu ilk yarı özelinde kimdi? → match.physical.run_distance.leaders.top5.players.first_half → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu ikinci yarı özelinde kimdi? → match.physical.run_distance.leaders.top5.players.second_half → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 0–15 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m00_15 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 16–30 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m16_30 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 31–45+ aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m31_45p → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 46–60 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m46_60 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 61–75 aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m61_75 → list(object) → unknown
Maç içinde en çok koşan ilk 5 oyuncu 76–90+ aralığında kimdi? → match.physical.run_distance.leaders.top5.players.m76_90p → list(object) → unknown

Maç içinde en çok koşan oyuncu ilk yarıda hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.first_half → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu ikinci yarıda hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.second_half → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 0–15 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m00_15 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 16–30 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m16_30 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 31–45+ aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m31_45p → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 46–60 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m46_60 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 61–75 aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m61_75 → enum(home,away) → unknown
Maç içinde en çok koşan oyuncu 76–90+ aralığında hangi takımdaydı? → match.physical.run_distance.leaders.top1.team.m76_90p → enum(home,away) → unknown

Maç içinde en çok koşan oyuncu ilk yarıda hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.first_half → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu ikinci yarıda hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.second_half → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 0–15 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m00_15 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 16–30 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m16_30 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 31–45+ aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m31_45p → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 46–60 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m46_60 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 61–75 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m61_75 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 76–90+ aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m76_90p → enum(goalkeeper,defender,midfielder,forward) → unknown

Maç içinde en çok koşan oyuncu için ilk yarı koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.first_half → string → unknown
Maç içinde en çok koşan oyuncu için ikinci yarı koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.second_half → string → unknown
Maç içinde en çok koşan oyuncu için 0–15 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m00_15 → string → unknown
Maç içinde en çok koşan oyuncu için 16–30 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m16_30 → string → unknown
Maç içinde en çok koşan oyuncu için 31–45+ aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m31_45p → string → unknown
Maç içinde en çok koşan oyuncu için 46–60 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m46_60 → string → unknown
Maç içinde en çok koşan oyuncu için 61–75 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m61_75 → string → unknown
Maç içinde en çok koşan oyuncu için 76–90+ aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m76_90p → string → unknown

Maç içinde iki takımın toplam koşu mesafesi farkı ilk yarıda var mı? → match.physical.run_distance.team_total.diff.exists.first_half → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı ikinci yarıda var mı? → match.physical.run_distance.team_total.diff.exists.second_half → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 0–15 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m00_15 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 16–30 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m16_30 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 31–45+ aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m31_45p → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 46–60 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m46_60 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 61–75 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m61_75 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 76–90+ aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m76_90p → boolean → unknown

İlk yarı toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.first_half → enum(high,mid,low) → unknown
İkinci yarı toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.second_half → enum(high,mid,low) → unknown
0–15 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m00_15 → enum(high,mid,low) → unknown
16–30 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m16_30 → enum(high,mid,low) → unknown
31–45+ aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m31_45p → enum(high,mid,low) → unknown
46–60 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m46_60 → enum(high,mid,low) → unknown
61–75 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m61_75 → enum(high,mid,low) → unknown
76–90+ aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m76_90p → enum(high,mid,low) → unknown

Takımın ilk yarı toplam koşu mesafesi olağan dışı yüksek mi? → match.physical.run_distance.team_total.anomaly.is_unusually_high.first_half → boolean → unknown
Takımın ilk yarı toplam koşu mesafesi olağan dışı düşük mü? → match.physical.run_distance.team_total.anomaly.is_unusually_low.first_half → boolean → unknown
Takımın ikinci yarı toplam koşu mesafesi olağan dışı yüksek mi? → match.physical.run_distance.team_total.anomaly.is_unusually_high.second_half → boolean → unknown
Takımın ikinci yarı toplam koşu mesafesi olağan dışı düşük mü? → match.physical.run_distance.team_total.anomaly.is_unusually_low.second_half → boolean → unknown

İlk yarıda koşu mesafesi ile ikinci yarıda koşu mesafesi arasında kırılma var mı? → match.physical.run_distance.break.exists.first_half_vs_second_half → boolean → unknown
0–30 ile 31–60 koşu mesafesi arasında kırılma var mı? → match.physical.run_distance.break.exists.m00_30_vs_m31_60 → boolean → unknown
31–60 ile 61–90+ koşu mesafesi arasında kırılma var mı? → match.physical.run_distance.break.exists.m31_60_vs_m61_90p → boolean → unknown
İkinci yarıda koşu mesafesi düşüşü başladı mı? → match.physical.run_distance.drop.started.second_half → boolean → unknown
Koşu mesafesi düşüşü hangi dakikada başladı? → match.physical.run_distance.drop.start_minute → integer → unknown

Koşu mesafesi düşüşünden sonraki 5 dakikada pres şiddeti azaldı mı? → match.physical.run_distance.drop.after5m.did_press_intensity_decrease → boolean → unknown
Koşu mesafesi düşüşünden sonraki 5 dakikada top kaybı arttı mı? → match.physical.run_distance.drop.after5m.did_turnovers_increase → boolean → unknown
Koşu mesafesi düşüşünden sonraki 5 dakikada geri koşu zafiyeti oluştu mu? → match.physical.run_distance.drop.after5m.did_recovery_run_weakness_occur → boolean → unknown
İkinci yarıda koşu mesafesi artışı başladı mı? → match.physical.run_distance.rise.started.second_half → boolean → unknown
Koşu mesafesi artışı hangi dakikada başladı? → match.physical.run_distance.rise.start_minute → integer → unknown

Koşu mesafesi artışından sonraki 5 dakikada baskı hattı öne çıktı mı? → match.physical.run_distance.rise.after5m.did_press_line_push_up → boolean → unknown
Koşu mesafesi artışından sonraki 5 dakikada şut sayısı arttı mı? → match.physical.run_distance.rise.after5m.did_shots_increase → boolean → unknown
Koşu mesafesi artışından sonraki 5 dakikada ceza sahası aksiyonu arttı mı? → match.physical.run_distance.rise.after5m.did_box_actions_increase → boolean → unknown
Maç içinde en çok koşan oyuncu ilk yarıda hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.first_half → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu ikinci yarıda hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.second_half → enum(goalkeeper,defender,midfielder,forward) → unknown

Maç içinde en çok koşan oyuncu 0–15 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m00_15 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 16–30 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m16_30 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 31–45+ aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m31_45p → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 46–60 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m46_60 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 61–75 aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m61_75 → enum(goalkeeper,defender,midfielder,forward) → unknown
Maç içinde en çok koşan oyuncu 76–90+ aralığında hangi pozisyonda oynadı? → match.physical.run_distance.leaders.top1.position.m76_90p → enum(goalkeeper,defender,midfielder,forward) → unknown

Maç içinde en çok koşan oyuncu için ilk yarı koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.first_half → string → unknown
Maç içinde en çok koşan oyuncu için ikinci yarı koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.second_half → string → unknown
Maç içinde en çok koşan oyuncu için 0–15 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m00_15 → string → unknown
Maç içinde en çok koşan oyuncu için 16–30 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m16_30 → string → unknown
Maç içinde en çok koşan oyuncu için 31–45+ aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m31_45p → string → unknown
Maç içinde en çok koşan oyuncu için 46–60 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m46_60 → string → unknown
Maç içinde en çok koşan oyuncu için 61–75 aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m61_75 → string → unknown
Maç içinde en çok koşan oyuncu için 76–90+ aralığında koşu mesafesi kaç kilometreydi? → match.physical.run_distance.leaders.top1.distance_km.m76_90p → string → unknown

Maç içinde iki takımın toplam koşu mesafesi farkı ilk yarıda var mı? → match.physical.run_distance.team_total.diff.exists.first_half → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı ikinci yarıda var mı? → match.physical.run_distance.team_total.diff.exists.second_half → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 0–15 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m00_15 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 16–30 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m16_30 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 31–45+ aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m31_45p → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 46–60 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m46_60 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 61–75 aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m61_75 → boolean → unknown
Maç içinde iki takımın toplam koşu mesafesi farkı 76–90+ aralığında var mı? → match.physical.run_distance.team_total.diff.exists.m76_90p → boolean → unknown

İlk yarı toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.first_half → enum(high,mid,low) → unknown
İkinci yarı toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.second_half → enum(high,mid,low) → unknown
0–15 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m00_15 → enum(high,mid,low) → unknown
16–30 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m16_30 → enum(high,mid,low) → unknown
31–45+ aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m31_45p → enum(high,mid,low) → unknown
46–60 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m46_60 → enum(high,mid,low) → unknown
61–75 aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m61_75 → enum(high,mid,low) → unknown
76–90+ aralığında toplam koşu mesafesi farkı “yüksek” mi “orta” mı “düşük” müydü? → match.physical.run_distance.team_total.diff.band.m76_90p → enum(high,mid,low) → unknown

Takımın ilk yarı toplam koşu mesafesi olağan dışı yüksek mi? → match.physical.run_distance.team_total.anomaly.is_unusually_high.first_half → boolean → unknown
Takımın ilk yarı toplam koşu mesafesi olağan dışı düşük mü? → match.physical.run_distance.team_total.anomaly.is_unusually_low.first_half → boolean → unknown
Takımın ikinci yarı toplam koşu mesafesi olağan dışı yüksek mi? → match.physical.run_distance.team_total.anomaly.is_unusually_high.second_half → boolean → unknown
Takımın ikinci yarı toplam koşu mesafesi olağan dışı düşük mü? → match.physical.run_distance.team_total.anomaly.is_unusually_low.second_half → boolean → unknown
İlk yarıda koşu mesafesi ile ikinci yarıda koşu mesafesi arasında kırılma var mı? → match.physical.run_distance.break.exists.first_half_vs_second_half → boolean → unknown

0–30 ile 31–60 koşu mesafesi arasında kırılma var mı? → match.physical.run_distance.break.exists.m00_30_vs_m31_60 → boolean → unknown
31–60 ile 61–90+ koşu mesafesi arasında kırılma var mı? → match.physical.run_distance.break.exists.m31_60_vs_m61_90p → boolean → unknown
İkinci yarıda koşu mesafesi düşüşü başladı mı? → match.physical.run_distance.drop.started.second_half → boolean → unknown
Koşu mesafesi düşüşü hangi dakikada başladı? → match.physical.run_distance.drop.start_minute → integer → unknown
Koşu mesafesi düşüşünden sonraki 5 dakikada pres şiddeti azaldı mı? → match.physical.run_distance.drop.after5m.did_press_intensity_decrease → boolean → unknown
Koşu mesafesi düşüşünden sonraki 5 dakikada top kaybı arttı mı? → match.physical.run_distance.drop.after5m.did_turnovers_increase → boolean → unknown
Koşu mesafesi düşüşünden sonraki 5 dakikada geri koşu zafiyeti oluştu mu? → match.physical.run_distance.drop.after5m.did_recovery_run_weakness_occur → boolean → unknown

FAZ-7-26
İkinci yarıda koşu mesafesi artışı başladı mı? → match.physical.run_distance.rise.started.second_half → boolean → unknown
Koşu mesafesi artışı hangi dakikada başladı? → match.physical.run_distance.rise.start_minute → integer → unknown
Koşu mesafesi artışından sonraki 5 dakikada baskı hattı öne çıktı mı? → match.physical.run_distance.rise.after5m.did_press_line_push_up → boolean → unknown
Koşu mesafesi artışından sonraki 5 dakikada şut sayısı arttı mı? → match.physical.run_distance.rise.after5m.did_shots_increase → boolean → unknown
Koşu mesafesi artışından sonraki 5 dakikada ceza sahası aksiyonu arttı mı? → match.physical.run_distance.rise.after5m.did_box_actions_increase → boolean → unknown

Koşu mesafesi yüksek olan takım ilk 15 dakikada tempo bandını taşıdı mı? → match.physical.run_distance.high_team.tempo_band_carried.m00_15 → boolean → unknown
Koşu mesafesi yüksek olan takım 16–30 aralığında tempo bandını taşıdı mı? → match.physical.run_distance.high_team.tempo_band_carried.m16_30 → boolean → unknown
Koşu mesafesi yüksek olan takım 31–45+ aralığında tempo bandını taşıdı mı? → match.physical.run_distance.high_team.tempo_band_carried.m31_45p → boolean → unknown
Koşu mesafesi yüksek olan takım 46–60 aralığında tempo bandını taşıdı mı? → match.physical.run_distance.high_team.tempo_band_carried.m46_60 → boolean → unknown
Koşu mesafesi yüksek olan takım 61–75 aralığında tempo bandını taşıdı mı? → match.physical.run_distance.high_team.tempo_band_carried.m61_75 → boolean → unknow
Koşu mesafesi yüksek olan takım 76–90+ aralığında tempo bandını taşıdı mı? → match.physical.run_distance.high_team.tempo_band_carried.m76_90p → boolean → unknown


Koşu mesafesi yüksek olan takımda tempo_down başladı mı? → match.physical.run_distance.high_team.tempo_down.started → boolean → unknown
Koşu mesafesi yüksek olan takımda tempo_down hangi dakikada başladı? → match.physical.run_distance.high_team.tempo_down.start_minute → integer → unknown
Koşu mesafesi yüksek olan takımda tempo_down sonrası 5 dakikada pas hatası arttı mı? → match.physical.run_distance.high_team.tempo_down.after5m.did_pass_errors_increase → boolean → unknown
Koşu mesafesi yüksek olan takımda tempo_down sonrası 5 dakikada topu tutma süresi azaldı mı? → match.physical.run_distance.high_team.tempo_down.after5m.did_possession_duration_decrease → boolean → unknown
Koşu mesafesi yüksek olan takımda tempo_down sonrası 5 dakikada rakip geçişleri arttı mı? → match.physical.run_distance.high_team.tempo_down.after5m.did_opponent_transitions_increase → boolean → unknown
Koşu mesafesi yüksek olan takımda maç sonunda sakatlık riski sinyali oluştu mu? → match.physical.run_distance.high_team.injury_risk_signal.occurred.end_of_match → boolean → unknown
Koşu mesafesi yüksek olan takımda sakatlık riski sinyali hangi dakikada belirginleşti? → match.physical.run_distance.high_team.injury_risk_signal.prominent_minute → integer → unknown
Koşu mesafesi yüksek olan takımda sakatlık riski sinyali sonrası 5 dakikada oyuncu değişikliği geldi mi? → match.physical.run_distance.high_team.injury_risk_signal.after5m.did_substitution_occur → boolean → unknown
Koşu mesafesi yüksek olan takımda sakatlık riski sinyali sonrası 5 dakikada faul sayısı arttı mı? → match.physical.run_distance.high_team.injury_risk_signal.after5m.did_fouls_increase → boolean → unknown

Koşu mesafesi yüksek olan takımda maç sonunda kart eğilimi arttı mı? → match.physical.run_distance.high_team.card_trend.increased.end_of_match → boolean → unknown
Koşu mesafesi yüksek olan takımda kart eğilimi hangi dakikada yükseldi? → match.physical.run_distance.high_team.card_trend.increase_minute → integer → unknown
Koşu mesafesi yüksek olan takımda kart eğilimi yükseldikten sonraki 5 dakikada faul-temas arttı mı? → match.physical.run_distance.high_team.card_trend.after5m.did_foul_contact_increase → boolean → unknown
Koşu mesafesi yüksek olan takımda kart eğilimi yükseldikten sonraki 5 dakikada savunma çizgisi geriye düştü mü? → match.physical.run_distance.high_team.card_trend.after5m.did_defensive_line_drop → boolean → unknown
Koşu mesafesi yüksek olan takımda maç sonunda faul eğilimi arttı mı? → match.physical.run_distance.high_team.foul_trend.increased.end_of_match → boolean → unknown
Koşu mesafesi yüksek olan takımda faul eğilimi hangi dakikada yükseldi? → match.physical.run_distance.high_team.foul_trend.increase_minute → integer → unknown
Koşu mesafesi yüksek olan takımda faul eğilimi yükseldikten sonraki 5 dakikada duran top sayısı arttı mı? → match.physical.run_distance.high_team.foul_trend.after5m.did_set_pieces_increase → boolean → unknown
Koşu mesafesi yüksek olan takımda faul eğilimi yükseldikten sonraki 5 dakikada rakip ceza sahası girişleri arttı mı? → match.physical.run_distance.high_team.foul_trend.after5m.did_opponent_box_entries_increase → boolean → unknown

Maç sonunda en çok koşan ilk 3 oyuncu bir sonraki maç için yorgunluk riski taşıyor mu? → match.physical.run_distance.next_match_risk.top3.fatigue_risk → boolean → unknow
Maç sonunda en çok koşan ilk 5 oyuncu bir sonraki maç için yorgunluk riski taşıyor mu? → match.physical.run_distance.next_match_risk.top5.fatigue_risk → boolean → unknown
Maç sonunda en çok koşan ilk 3 oyuncu bir sonraki maç için sakatlık riski taşıyor mu? → match.physical.run_distance.next_match_risk.top3.injury_risk → boolean → unknown
Maç sonunda en çok koşan ilk 5 oyuncu bir sonraki maç için sakatlık riski taşıyor mu? → match.physical.run_distance.next_match_risk.top5.injury_risk → boolean → unknown

Bu maçta olağan dışı koşu yükü “haftaya performans düşüşü” sinyali üretti mi? → match.physical.run_distance.anomaly.next_week.performance_drop_signal.occurred → boolean → unknown
Bu maçta olağan dışı koşu yükü “haftaya performans düşüşü” sinyali hangi dakikadan sonra belirginleşti? → match.physical.run_distance.anomaly.next_week.performance_drop_signal.prominent_minute → integer → unknown
Bu maçta olağan dışı koşu yükü sonrası 5 dakikada takım boyu uzadı mı? → match.physical.run_distance.anomaly.next_week.performance_drop_signal.after5m.did_team_lengthen → boolean → unknown
Bu maçta olağan dışı koşu yükü sonrası 5 dakikada savunma geri koşuları aksadı mı? → match.physical.run_distance.anomaly.next_week.performance_drop_signal.after5m.did_defensive_recovery_fail → boolean → unknown

Bu maçta olağan dışı koşu yükü “haftaya sakatlık artışı” sinyali üretti mi? → match.physical.run_distance.anomaly.next_week.injury_increase_signal.occurred → boolean → unknown
Bu maçta olağan dışı koşu yükü “haftaya sakatlık artışı” sinyali hangi dakikadan sonra belirginleşti? → match.physical.run_distance.anomaly.next_week.injury_increase_signal.prominent_minute → integer → unknown
Bu maçta olağan dışı koşu yükü sinyali sonrası 5 dakikada kas tutulması benzeri görüntüler arttı mı? → match.physical.run_distance.anomaly.next_week.injury_increase_signal.after5m.did_muscle_tightness_signs_increase → boolean → unknown
Bu maçta olağan dışı koşu yükü sinyali sonrası 5 dakikada oyuncu temposu düştü mü? → match.physical.run_distance.anomaly.next_week.injury_increase_signal.after5m.did_player_tempo_drop → boolean → unknown

Maçın sonucu 1X2 bandında maç boyunca baskın favori değişti mi → market.1x2.dominant_favorite.changed_flag → boolean → unknown
Maçın sonucu 1X2 bandında ilk baskın favori hangi takımdı? → market.1x2.dominant_favorite.first_team → enum (home, away) → unknown
Maçın sonucu 1X2 bandında baskın favori değişimi hangi dakikada oldu? → market.1x2.dominant_favorite.change_minute → integer → unknown
Maçın sonucu 1X2 bandında baskın favori değişimi hangi segmentte oldu? → market.1x2.dominant_favorite.change_segment → enum (m0_15, m16_30, m31_45, m46_60, m61_75, m76_90, m90_plus) → unknown
Maçın sonucu 1X2 bandında favori değişimi gol öncesi mi gol sonrası mı oldu? → market.1x2.dominant_favorite.change_relative_to_goal → enum (pre_goal, post_goal) → unknown
Maçın sonucu 1X2 bandında favori değişimi kırmızı kart öncesi mi kırmızı kart sonrası mı oldu? → market.1x2.dominant_favorite.change_relative_to_red_card → enum (pre_red_card, post_red_card) → unknown

Maçın sonucu 1X2 bandında favori değişimi penaltı kararı öncesi mi sonrası mı oldu? → market.1x2.dominant_favorite.change_relative_to_penalty_decision → enum (pre_penalty, post_penalty) → unknown
Maçın sonucu 1X2 bandında favori değişimi VAR incelemesi öncesi mi sonrası mı oldu? → market.1x2.dominant_favorite.change_relative_to_var_review → enum (pre_var_review, post_var_review) → unknown
Maçın sonucu 1X2 bandında favori değişimi sakatlık / oyuncu değişikliği öncesi mi sonrası mı oldu? → market.1x2.dominant_favorite.change_relative_to_injury_substitution → enum (pre_injury_sub, post_injury_sub) → unknown
Maçın sonucu 1X2 bandında favori değişimi kontrol kaybı başlangıcından sonra mı oluştu? → market.1x2.dominant_favorite.change_after_control_loss_flag → boolean → unknown

Maçın sonucu 1X2 bandında favori değişimi sonrası ilk 5 dakikada baskınlık korunabildi mi? → market.1x2.dominant_favorite.post_change_5m.dominance_maintained_flag → boolean → unknown
Maçın sonucu 1X2 bandında favori değişimi sonrası ilk 5 dakikada tekrar geri döndü mü? → market.1x2.dominant_favorite.post_change_5m.reverted_flag → boolean → unknown
Maçın sonucu 1X2 bandında favori değişimi sonrası ilk 5 dakikada gol ihtimali bandı yükseldi mi? → market.1x2.dominant_favorite.post_change_5m.goal_risk_band_up_flag → boolean → unknown
Maçın sonucu 1X2 bandında favori değişimi sonrası ilk 5 dakikada gol ihtimali bandı düştü mü? → market.1x2.dominant_favorite.post_change_5m.goal_risk_band_down_flag → boolean → unknown

Maçın sonucu 1X2 bandında ilk kırılma hangi dakikada oldu? → market.1x2.breakpoint.first_minute → integer → unknown
Maçın sonucu 1X2 bandında ilk kırılma hangi segmentte oldu? → market.1x2.breakpoint.first_segment → enum (m0_15, m16_30, m31_45, m46_60, m61_75, m76_90, m90_plus) → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi gol müydü? → market.1x2.breakpoint.trigger.goal_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi kırmızı kart mıydı? → market.1x2.breakpoint.trigger.red_card_flag → boolean → unknown

Maçın sonucu 1X2 bandında kırılma tetikleyicisi penaltı mıydı? → market.1x2.breakpoint.trigger.penalty_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi VAR kararı mıydı? → market.1x2.breakpoint.trigger.var_decision_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi sakatlık mıydı? → market.1x2.breakpoint.trigger.injury_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi kontrol kaybı mıydı? → market.1x2.breakpoint.trigger.control_loss_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi ev sahibi lehine mi oldu? → market.1x2.breakpoint.trigger.favored_side → enum (home, away) → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi deplasman lehine mi oldu? → market.1x2.breakpoint.trigger.favored_side → enum (home, away) → unknown

Maçın sonucu 1X2 bandında kırılma tetikleyicisi sonrası ilk 5 dakikada favori pekişti mi? → market.1x2.breakpoint.post_trigger_5m.favorite_reinforced_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi sonrası ilk 5 dakikada denge geri geldi mi? → market.1x2.breakpoint.post_trigger_5m.balance_restored_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi sonrası ilk 5 dakikada ikinci bir kırılma oldu mu? → market.1x2.breakpoint.post_trigger_5m.second_breakpoint_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi sonrası ilk 5 dakikada net pozisyon sayısı arttı mı? → market.1x2.breakpoint.post_trigger_5m.big_chances_increase_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi sonrası ilk 5 dakikada tempo değişti mi? → market.1x2.breakpoint.post_trigger_5m.tempo_changed_flag → boolean → unknown
Maçın sonucu 1X2 bandında kırılma tetikleyicisi sonrası ilk 5 dakikada kart riski arttı mı? → market.1x2.breakpoint.post_trigger_5m.card_risk_increase_flag → boolean → unknown

Maçta toplam gol bandı (alt/üst) için ilk kırılma hangi segmentte oluştu? → market.goals_ou.breakpoint.first_segment → enum (m0_15, m16_30, m31_45, m46_60, m61_75, m76_90, m90_plus) → unknown
Maçta toplam gol bandı (alt/üst) için ilk kırılma hangi dakikada oluştu? → market.goals_ou.breakpoint.first_minute → integer → unknown
Maçta toplam gol bandı (alt/üst) için ilk kırılma öncesi son 5 dakikada gol beklentisi yükseldi mi? → market.goals_ou.breakpoint.pre_5m.goal_expectancy_up_flag → boolean → unknown
Maçta toplam gol bandı (alt/üst) için ilk kırılma sonrası ilk 5 dakikada gol ritmi arttı mı? → market.goals_ou.breakpoint.post_5m.goal_rhythm_up_flag → boolean → unknown

Toplam gol bandı (alt/üst) kırılması erken gol ile mi tetiklendi? → market.goals_ou.breakpoint.trigger.early_goal_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması erken gol dakikası kaçtı? → market.goals_ou.breakpoint.trigger.early_goal_minute → integer → unknown
Toplam gol bandı (alt/üst) kırılması erken gol sonrası ilk 5 dakikada ikinci gol sinyali verdi mi? → market.goals_ou.breakpoint.trigger.early_goal.post_5m.second_goal_signal_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması ilk 15 baskı ile mi tetiklendi? → market.goals_ou.breakpoint.trigger.first15_pressure_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması ilk 15 baskıyı hangi takım kurdu? → market.goals_ou.breakpoint.trigger.first15_pressure_team → enum (home, away) → unknown
Toplam gol bandı (alt/üst) kırılması ilk 15 baskı sonrası ilk 5 dakikada tempo korundu mu? → market.goals_ou.breakpoint.trigger.first15_pressure.post_5m.tempo_maintained_flag → boolean → unknown

Toplam gol bandı (alt/üst) kırılması tempo_up ile mi tetiklendi? → market.goals_ou.breakpoint.trigger.tempo_up_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması tempo_up hangi dakikada başladı? → market.goals_ou.breakpoint.trigger.tempo_up_start_minute → integer → unknown
Toplam gol bandı (alt/üst) kırılması tempo_up sonrası ilk 5 dakikada pozisyon sıklığı arttı mı? → market.goals_ou.breakpoint.trigger.tempo_up.post_5m.chance_frequency_up_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması kırmızı kart ile mi tetiklendi? → market.goals_ou.breakpoint.trigger.red_card_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması kırmızı kart hangi dakikada oldu? → market.goals_ou.breakpoint.trigger.red_card_minute → integer → unknown
Toplam gol bandı (alt/üst) kırılması kırmızı kart sonrası ilk 5 dakikada oyun tek kaleye döndü mü? → market.goals_ou.breakpoint.trigger.red_card.post_5m.one_way_pressure_flag → boolean → unknown

Toplam gol bandı (alt/üst) kırılması penaltı ile mi tetiklendi? → market.goals_ou.breakpoint.trigger.penalty_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması penaltı kararı hangi dakikada geldi? → market.goals_ou.breakpoint.trigger.penalty_decision_minute → integer → unknown
Toplam gol bandı (alt/üst) kırılması penaltı sonrası ilk 5 dakikada tempo düştü mü yükseldi mi? → market.goals_ou.breakpoint.trigger.penalty.post_5m.tempo_direction → enum (tempo_up, tempo_down, stable) → unknown
Toplam gol bandı (alt/üst) kırılması iptal gol ile mi tetiklendi? → market.goals_ou.breakpoint.trigger.disallowed_goal_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması iptal gol hangi dakikada oldu? → market.goals_ou.breakpoint.trigger.disallowed_goal_minute → integer → unknown
Toplam gol bandı (alt/üst) kırılması iptal gol sonrası ilk 5 dakikada baskı arttı mı? → market.goals_ou.breakpoint.trigger.disallowed_goal.post_5m.pressure_up_flag → boolean → unknown

Toplam gol bandı (alt/üst) kırılması time_waste ile mi bastırıldı? → market.goals_ou.breakpoint.suppression.time_waste_flag → boolean → unknown
Toplam gol bandı (alt/üst) kırılması time_waste hangi dakikada başladı? → market.goals_ou.breakpoint.suppression.time_waste_start_minute → integer → unknown
Toplam gol bandı (alt/üst) kırılması time_waste sonrası ilk 5 dakikada oyun akışı koptu mu? → market.goals_ou.breakpoint.suppression.time_waste.post_5m.flow_disrupted_flag → boolean → unknown

Maçta iki takım da gol atar (BTTS) bandı için ilk sinyal hangi segmentte oluştu? → market.btts.signal.first_segment → enum (m0_15, m16_30, m31_45, m46_60, m61_75, m76_90, m90_plus) → unknown
Maçta BTTS bandı için ilk sinyal hangi dakikada oluştu? → market.btts.signal.first_minute → integer → unknown
BTTS bandı için iki takım da net pozisyon üretti mi? → market.btts.signal.big_chance.both_teams_flag → boolean → unknown
BTTS bandı için ev sahibi net pozisyon üretti mi? → market.btts.signal.big_chance.home_flag → boolean → unknown
BTTS bandı için deplasman net pozisyon üretti mi? → market.btts.signal.big_chance.away_flag → boolean → unknown
BTTS bandı için iki takım da net pozisyon ürettiği ilk dakika aralığı neydi? → market.btts.signal.big_chance.first_window → enum (m0_15, m16_30, m31_45, m46_60, m61_75, m76_90, m90_plus) → unknown

BTTS bandı için iki takım da xThreat benzeri tehlike üretti mi? → market.btts.signal.threat.both_teams_flag → boolean → unknown
BTTS bandı için ev sahibi xThreat benzeri tehlike üretti mi? → market.btts.signal.threat.home_flag → boolean → unknown
BTTS bandı için deplasman xThreat benzeri tehlike üretti mi? → market.btts.signal.threat.away_flag → boolean → unknown
BTTS bandı için iki takım da korner baskısı üretti mi? → market.btts.signal.corners_pressure.both_teams_flag → boolean → unknown
BTTS bandı için ev sahibi korner baskısı üretti mi? → market.btts.signal.corners_pressure.home_flag → boolean → unknown
BTTS bandı için deplasman korner baskısı üretti mi? → market.btts.signal.corners_pressure.away_flag → boolean → unknown

BTTS bandı için savunma hatası zinciri oluştu mu? → market.btts.signal.defensive_error.chain_flag → boolean → unknown
BTTS bandı için savunma hatası zinciri hangi dakikada başladı? → market.btts.signal.defensive_error.chain_start_minute → integer → unknown
BTTS bandı için savunma hatası zinciri sonrası ilk 5 dakikada net pozisyon geldi mi? → market.btts.signal.defensive_error.post_5m.big_chance_flag → boolean → unknown
BTTS bandı için kaleci kurtarış serisi oluştu mu? → market.btts.signal.goalkeeper_saves.series_flag → boolean → unknown
BTTS bandı için kaleci kurtarış serisi hangi dakikada başladı? → market.btts.signal.goalkeeper_saves.series_start_minute → integer → unknown

BTTS bandı için kurtarış serisi sonrası ilk 5 dakikada baskı devam etti mi? → market.btts.signal.goalkeeper_saves.post_5m.pressure_continued_flag → boolean → unknown
BTTS bandı için kaleci hatası sinyali oluştu mu? → market.btts.signal.goalkeeper_error.flag → boolean → unknown
BTTS bandı için kaleci hatası sinyali hangi dakikada oldu? → market.btts.signal.goalkeeper_error.minute → integer → unknown
BTTS bandı için kaleci hatası sonrası ilk 5 dakikada gol geldi mi? → market.btts.signal.goalkeeper_error.post_5m.goal_scored_flag → boolean → unknown

Maçta ilk yarı sonucu bandı için kırılma hangi dakikada oluştu? → market.ht_result.breakpoint.minute → integer → unknown
Maçta ilk yarı sonucu bandı için kırılma hangi segmentte oluştu? → market.ht_result.breakpoint.segment → enum (m0_15, m16_30, m31_45, m45_plus) → unknown
Maçta ilk yarı sonucu bandı kırılması gol ile mi tetiklendi? → market.ht_result.breakpoint.trigger.goal_flag → boolean → unknown
Maçta ilk yarı sonucu bandı kırılması kırmızı kart ile mi tetiklendi? → market.ht_result.breakpoint.trigger.red_card_flag → boolean → unknown
Maçta ilk yarı sonucu bandı kırılması penaltı ile mi tetiklendi? → market.ht_result.breakpoint.trigger.penalty_flag → boolean → unknown
Maçta ilk yarı sonucu bandı kırılması VAR ile mi tetiklendi? → market.ht_result.breakpoint.trigger.var_flag → boolean → unknown
Maçta ilk yarı sonucu bandı kırılması sonrası ilk 5 dakikada denge geri geldi mi? → market.ht_result.breakpoint.post_5m.balance_restored_flag → boolean → unknown

Maçta ilk yarı alt/üst bandı için kırılma hangi segmentte oluştu? → market.ht_goals_ou.breakpoint.segment → enum (m0_15, m16_30, m31_45, m45_plus) → unknown
Maçta ilk yarı alt/üst bandı için kırılma hangi dakikada oluştu? → market.ht_goals_ou.breakpoint.minute → integer → unknown
Maçta ilk yarı alt/üst bandı kırılması tempo_up ile mi tetiklendi? → market.ht_goals_ou.breakpoint.trigger.tempo_up_flag → boolean → unknown
Maçta ilk yarı alt/üst bandı kırılması erken gol ile mi tetiklendi? → market.ht_goals_ou.breakpoint.trigger.early_goal_flag → boolean → unknown
Maçta ilk yarı alt/üst bandı kırılması sonrası ilk 5 dakikada ikinci gol sinyali oluştu mu? → market.ht_goals_ou.breakpoint.post_5m.second_goal_signal_flag → boolean → unknown

Maçta ikinci yarı alt/üst bandı için kırılma hangi segmentte oluştu? → market.sh_goals_ou.breakpoint.segment → enum (m46_60, m61_75, m76_90, m90_plus) → unknown
Maçta ikinci yarı alt/üst bandı için kırılma hangi dakikada oluştu? → market.sh_goals_ou.breakpoint.minute → integer → unknown
Maçta ikinci yarı alt/üst bandı kırılması oyuncu değişiklikleri ile mi tetiklendi? → market.sh_goals_ou.breakpoint.trigger.substitutions_flag → boolean → unknown
Maçta ikinci yarı alt/üst bandı kırılması kırmızı kart ile mi tetiklendi? → market.sh_goals_ou.breakpoint.trigger.red_card_flag → boolean → unknown
Maçta ikinci yarı alt/üst bandı kırılması sonrası ilk 5 dakikada oyun tek kaleye döndü mü? → market.sh_goals_ou.breakpoint.post_5m.one_way_pressure_flag → boolean → unknown

Maçta ilk yarı tempo bandı “tempo_up” mı “stable” mı “tempo_down” muydı? → tempo.half1.band → enum (tempo_up, stable, tempo_down) → unknown
Maçta ilk yarı tempo bandı hangi dakikada tempo_up oldu? → tempo.half1.shift_to_tempo_up.minute → integer → unknown
Maçta ilk yarı tempo bandı hangi dakikada tempo_down oldu? → tempo.half1.shift_to_tempo_down.minute → integer → unknown
Maçta ilk yarı tempo bandı değişimi sonrası ilk 5 dakikada pozisyon sayısı arttı mı? → tempo.half1.post_shift_5m.chances_increase_flag → boolean → unknown

Maçta ikinci yarı tempo bandı “tempo_up” mı “stable” mı “tempo_down” muydı? → tempo.half2.band → enum (tempo_up, stable, tempo_down) → unknown
Maçta ikinci yarı tempo bandı hangi dakikada tempo_up oldu? → tempo.half2.shift_to_tempo_up.minute → integer → unknown
Maçta ikinci yarı tempo bandı hangi dakikada tempo_down oldu? → tempo.half2.shift_to_tempo_down.minute → integer → unknown
Maçta ikinci yarı tempo bandı değişimi sonrası ilk 5 dakikada pozisyon sayısı arttı mı? → tempo.half2.post_shift_5m.chances_increase_flag → boolean → unknown

Maçta bir sonraki golü kim atar bandı için baskın taraf değişti mi? → market.next_goal.dominant_side.changed_flag → boolean → unknown
Maçta bir sonraki golü kim atar bandında ilk baskın taraf kimdi? → market.next_goal.dominant_side.first_team → enum (home, away) → unknown
Maçta bir sonraki golü kim atar bandı için baskın taraf değişimi hangi dakikada oldu? → market.next_goal.dominant_side.change_minute → integer → unknown
Maçta bir sonraki golü kim atar bandı için baskın taraf değişimi hangi segmentte oldu? → market.next_goal.dominant_side.change_segment → enum (m0_15, m16_30, m31_45, m46_60, m61_75, m76_90, m90_plus) → unknown

Bir sonraki gol bandı için net pozisyon kümelenmesi oldu mu? → market.next_goal.big_chance.cluster_flag → boolean → unknown
Bir sonraki gol bandı için net pozisyon kümelenmesi hangi dakikada başladı? → market.next_goal.big_chance.cluster_start_minute → integer → unknown
Bir sonraki gol bandı için net pozisyon kümelenmesi hangi takım lehineydi? → market.next_goal.big_chance.cluster_team → enum (home, away) → unknown
Bir sonraki gol bandı için kümelenme sonrası ilk 5 dakikada gol geldi mi? → market.next_goal.big_chance.post_5m.goal_scored_flag → boolean → unknown

Bir sonraki gol bandı için korner yoğunluğu taraf değiştirdi mi? → market.next_goal.corners_pressure.side_shift_flag → boolean → unknown
Bir sonraki gol bandı için korner yoğunluğu değişimi hangi dakikada oldu? → market.next_goal.corners_pressure.side_shift_minute → integer → unknown
Bir sonraki gol bandı için korner yoğunluğu değişimi sonrası ilk 5 dakikada şut geldi mi? → market.next_goal.corners_pressure.post_shift_5m.shot_occurred_flag → boolean → unknown
Bir sonraki gol bandı için penaltı sinyali oluştu mu? → market.next_goal.penalty_signal.flag → boolean → unknown
Bir sonraki gol bandı için penaltı sinyali hangi dakikada oluştu? → market.next_goal.penalty_signal.minute → integer → unknown
Bir sonraki gol bandı için penaltı sinyali sonrası ilk 5 dakikada VAR incelemesi oldu mu? → market.next_goal.penalty_signal.post_5m.var_review_flag → boolean → unknown

Bir sonraki gol bandı için VAR incelemesi gerginliği oluştu mu? → market.next_goal.var_tension.flag → boolean → unknown
Bir sonraki gol bandı için VAR incelemesi gerginliği hangi dakikada oluştu? → market.next_goal.var_tension.minute → integer → unknow
Bir sonraki gol bandı için VAR gerginliği sonrası ilk 5 dakikada kart çıktı mı? → market.next_goal.var_tension.post_5m.card_given_flag → boolean → unknown
Bir sonraki gol bandı için kırmızı kart riski sinyali oluştu mu? → market.next_goal.red_card_risk.flag → boolean → unknown
Bir sonraki gol bandı için kırmızı kart riski sinyali hangi dakikada oluştu? → market.next_goal.red_card_risk.minute → integer → unknown
Bir sonraki gol bandı için kırmızı kart riski sonrası ilk 5 dakikada oyun sertleşti mi? → market.next_goal.red_card_risk.post_5m.game_hardened_flag → boolean → unknown

Maçta toplam korner bandı için ilk 15 dakikada korner hızı “high” mı “mid” mi “low” muydu? → market.corners_total.rate.m0_15 → enum (high, mid, low) → unknown
Maçta toplam korner bandı için 16–30 dakikada korner hızı “high” mı “mid” mi “low” muydu? → market.corners_total.rate.m16_30 → enum (high, mid, low) → unknown
Maçta toplam korner bandı için 31–45 dakikada korner hızı “high” mı “mid” mi “low” muydu? → market.corners_total.rate.m31_45 → enum (high, mid, low) → unknown
Maçta toplam korner bandı için 46–60 dakikada korner hızı “high” mı “mid” mi “low” muydu? → market.corners_total.rate.m46_60 → enum (high, mid, low) → unknown
Maçta toplam korner bandı için 61–75 dakikada korner hızı “high” mı “mid” mi “low” muydu? → market.corners_total.rate.m61_75 → enum (high, mid, low) → unknown
Maçta toplam korner bandı için 76–90+ dakikada korner hızı “high” mı “mid” mi “low” muydu? → market.corners_total.rate.m76_90_plus → enum (high, mid, low) → unknown
Maçta toplam korner bandı için son 10 dakikada korner hızı arttı mı? → market.corners_total.rate.last10.increase_flag → boolean → unknown
Maçta toplam korner bandı için son 5 dakikada korner hızı arttı mı? → market.corners_total.rate.last5.increase_flag → boolean → unknown
Maçta toplam korner bandı için 0–30 aralığında kornerler iki takıma dengeli mi dağıldı? → market.corners_total.distribution.m0_30.balanced_flag → boolean → unknown
Maçta toplam korner bandı için 31–60 aralığında kornerler iki takıma dengeli mi dağıldı? → market.corners_total.distribution.m31_60.balanced_flag → boolean → unknown
Maçta toplam korner bandı için 61–90+ aralığında kornerler iki takıma dengeli mi dağıldı? → market.corners_total.distribution.m61_90_plus.balanced_flag → boolean → unknown

Maçta toplam korner bandı için ilk yarıda kornerler tek takımda mı kümelendi? → market.corners_total.cluster.half1.single_team_flag → boolean → unknown
Maçta toplam korner bandı için ikinci yarıda kornerler tek takımda mı kümelendi? → market.corners_total.cluster.half2.single_team_flag → boolean → unknown
Maçta toplam korner bandı için ev sahibi kornerleri tek başına bandı sürükledi mi? → market.corners_total.pull.home_flag → boolean → unknown
Maçta toplam korner bandı için deplasman kornerleri tek başına bandı sürükledi mi? → market.corners_total.pull.away_flag → boolean → unknown

Maçta toplam korner bandı için korner baskısı 60–75 arasında arttı mı? → market.corners_total.pressure_window.m60_75.increase_flag → boolean → unknown
Maçta toplam korner bandı için korner baskısı 75–90+ arasında arttı mı? → market.corners_total.pressure_window.m75_90_plus.increase_flag → boolean → unknown
Maçta toplam korner bandı için kornerlerin çoğu aynı 10 dakikalık dilimde mi çıktı? → market.corners_total.concentration.single_10m_window_flag → boolean → unknown
Maçta toplam korner bandı için kornerlerin çoğu “gol arayışı” döneminde mi geldi? → market.corners_total.context.majority_in_goal_chase_flag → boolean → unknown
Maçta toplam korner bandı için kornerlerin çoğu “skoru koruma” döneminde mi geldi? → market.corners_total.context.majority_in_score_protection_flag → boolean → unknown
Maçta toplam korner bandı için bir kornerden sonraki 5 dakikada yeni korner dalgası oluştu mu? → market.corners_total.post_corner_5m.new_corner_wave_flag → boolean → unknown

Maçta toplam korner bandı için kornerlerin artışı duran top baskısını artırdı mı? → market.corners_total.impact.set_piece_pressure_up_flag → boolean → unknown
Maçta toplam korner bandı için kornerlerin artışı rakibin savunma dengesini bozdu mu? → market.corners_total.impact.defensive_balance_disrupted_flag → boolean → unknown
Maçta ilk korneri kim alır bandı gerçekleşti mi? → market.first_corner.occurred_flag → boolean → unknown
Maçta ilk kornerin dakikası nedir? → market.first_corner.minute → integer → unknown
Maçta ilk korneri hangi takım aldı? → market.first_corner.team → enum (home, away) → unknown
Maçta ilk kornerden sonraki 10 dakikada korner akışı devam etti mi? → market.first_corner.post_10m.corner_flow_continued_flag → boolean → unknown

Maçta ilk 5 dakikada korner oldu mu? → market.corners.m0_5.occurred_flag → boolean → unknown
Maçta ilk 10 dakikada korner oldu mu? → market.corners.m0_10.occurred_flag → boolean → unknown
Maçta ilk korner 0–5 dakikada mı geldi? → market.first_corner.window.m0_5.flag → boolean → unknown
Maçta ilk korner 6–10 dakikada mı geldi? → market.first_corner.window.m6_10.flag → boolean → unknown
Maçta ilk korner 11–15 dakikada mı geldi? → market.first_corner.window.m11_15.flag → boolean → unknown

Maçta ilk korneri ev sahibi mi aldı? → market.first_corner.by_side.home_flag → boolean → unknown
Maçta ilk korneri deplasman mı aldı? → market.first_corner.by_side.away_flag → boolean → unknown
Maçta ilk korneri alan takım ilk 5 dakikada baskıyı sürdürdü mü? → market.first_corner.team_post_5m.pressure_maintained_flag → boolean → unknown
Maçta ilk korneri alan takım ilk 10 dakikada baskıyı sürdürdü mü? → market.first_corner.team_post_10m.pressure_maintained_flag → boolean → unknown
Maçta ilk korneri alan takım ilk 5 dakikada ikinci korneri de aldı mı? → market.first_corner.post_5m.same_team_second_corner_flag → boolean → unknown
Maçta ilk korneri alan takım ilk 10 dakikada ikinci korneri de aldı mı? → market.first_corner.post_10m.same_team_second_corner_flag → boolean → unknown

Maçta ilk kornerden sonraki 5 dakikada korner geldi mi? → market.first_corner.post_5m.corner_occurred_flag → boolean → unknown
Maçta ilk kornerden sonraki 5 dakikada korner hızı arttı mı? → market.first_corner.post_5m.corner_rate_increase_flag → boolean → unknown
Maçta ilk kornerden sonraki 5 dakikada korner hızı düştü mü? → market.first_corner.post_5m.corner_rate_decrease_flag → boolean → unknown
Maçta ilk kornerden sonraki 10 dakikada kornerler tek takımda mı kaldı? → market.first_corner.post_10m.corners_single_team_flag → boolean → unknown
Maçta ilk kornerden sonraki 10 dakikada kornerler dengeli mi dağıldı? → market.first_corner.post_10m.corners_balanced_flag → boolean → unknown
Maçta ilk kornerden sonraki 10 dakikada rakip takım korner alabildi mi? → market.first_corner.post_10m.opponent_corner_occurred_flag → boolean → unknown

Maçta ilk korneri alan takımın korneri sonrası rakip takım ilk 5 dakikada topu tuttu mu? → market.first_corner.opponent_post_5m.possession_stabilized_flag → boolean → unknown
Maçta ilk korneri alan takımın korneri sonrası rakip takım ilk 5 dakikada baskıyı kırdı mı? → market.first_corner.opponent_post_5m.pressure_broken_flag → boolean → unknown
Maçta toplam kart bandı için ilk 15 dakikada kart hızı “high” mı “mid” mi “low” muydu? → market.cards_total.rate.m0_15 → enum (high, mid, low) → unknown
Maçta toplam kart bandı için 16–30 dakikada kart hızı “high” mı “mid” mi “low” muydu? → market.cards_total.rate.m16_30 → enum (high, mid, low) → unknown
Maçta toplam kart bandı için 31–45 dakikada kart hızı “high” mı “mid” mi “low” muydu? → market.cards_total.rate.m31_45 → enum (high, mid, low) → unknown
Maçta toplam kart bandı için 46–60 dakikada kart hızı “high” mı “mid” mi “low” muydu? → market.cards_total.rate.m46_60 → enum (high, mid, low) → unknown
Maçta toplam kart bandı için 61–75 dakikada kart hızı “high” mı “mid” mi “low” muydu? → market.cards_total.rate.m61_75 → enum (high, mid, low) → unknown
Maçta toplam kart bandı için 76–90+ dakikada kart hızı “high” mı “mid” mi “low” muydu? → market.cards_total.rate.m76_90_plus → enum (high, mid, low) → unknown

Maçta toplam kart bandı için ilk yarıda kartlar tek takımda mı kümelendi? → market.cards_total.cluster.half1.single_team_flag → boolean → unknown
Maçta toplam kart bandı için ikinci yarıda kartlar tek takımda mı kümelendi? → market.cards_total.cluster.half2.single_team_flag → boolean → unknown
Maçta toplam kart bandı için kartlar ev sahibinde mi kümelendi? → market.cards_total.cluster.by_side.home_flag → boolean → unknown
Maçta toplam kart bandı için kartlar deplasmanda mı kümelendi? → market.cards_total.cluster.by_side.away_flag → boolean → unknown
Maçta toplam kart bandı için kartlar iki takıma dengeli mi dağıldı? → market.cards_total.distribution.balanced_flag → boolean → unknown

Maçta toplam kart bandı için kartların çoğu aynı 10 dakikalık dilimde mi çıktı? → market.cards_total.concentration.single_10m_window_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu ilk yarının son 10 dakikasında mı çıktı? → market.cards_total.concentration.half1_last10_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu ikinci yarının ilk 10 dakikasında mı çıktı? → market.cards_total.concentration.half2_first10_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu son 15 dakikada mı çıktı? → market.cards_total.concentration.last15_flag → boolean → unknown
Maçta toplam kart bandı için kartlar “itiraz” kaynaklı mıydı? → market.cards_total.cause.appeal_flag → boolean → unknown
Maçta toplam kart bandı için kartlar “sertlik” kaynaklı mıydı? → market.cards_total.cause.physicality_flag → boolean → unknown
Maçta toplam kart bandı için kartlar “taktik faul” kaynaklı mıydı? → market.cards_total.cause.tactical_foul_flag → boolean → unknown

Maçta toplam kart bandı için kartların çoğu ev sahibi kaynaklı itiraz mıydı? → market.cards_total.cause_breakdown.home_appeal_majority_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu deplasman kaynaklı itiraz mıydı? → market.cards_total.cause_breakdown.away_appeal_majority_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu ev sahibi kaynaklı sertlik miydi? → market.cards_total.cause_breakdown.home_physicality_majority_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu deplasman kaynaklı sertlik miydi? → market.cards_total.cause_breakdown.away_physicality_majority_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu ev sahibi kaynaklı taktik faul müydü? → market.cards_total.cause_breakdown.home_tactical_majority_flag → boolean → unknown
Maçta toplam kart bandı için kartların çoğu deplasman kaynaklı taktik faul müydü? → market.cards_total.cause_breakdown.away_tactical_majority_flag → boolean → unknown
Maçta toplam kart bandı için ilk kart 0–10 dakikada mı çıktı? → market.cards_total.first_card.window.m0_10_flag → boolean → unknown
Maçta toplam kart bandı için ilk kart 11–20 dakikada mı çıktı? → market.cards_total.first_card.window.m11_20_flag → boolean → unknown
Maçta toplam kart bandı için ilk kart 21–30 dakikada mı çıktı? → market.cards_total.first_card.window.m21_30_flag → boolean → unknown
Maçta toplam kart bandı için ilk kart 31–45+ dakikada mı çıktı? → market.cards_total.first_card.window.m31_45_plus_flag → boolean → unknown

Maçta toplam kart bandı için hakem standardı ilk yarıda sertleşti mi? → referee.standard.half1.hardened_flag → boolean → unknown
Maçta toplam kart bandı için hakem standardı ikinci yarıda sertleşti mi? → referee.standard.half2.hardened_flag → boolean → unknown
Maçta toplam kart bandı için hakem standardı son 15 dakikada sertleşti mi? → referee.standard.last15.hardened_flag → boolean → unknown
Maçta toplam kart bandı için hakem standardı ilk yarıda yumuşadı mı? → referee.standard.half1.softened_flag → boolean → unknown
Maçta toplam kart bandı için hakem standardı ikinci yarıda yumuşadı mı? → referee.standard.half2.softened_flag → boolean → unknown
Maçta toplam kart bandı için hakem standardı son 15 dakikada yumuşadı mı? → referee.standard.last15.softened_flag → boolean → unknown
Maçta toplam kart bandı için bir karttan sonraki 5 dakikada kart akışı devam etti mi? → market.cards_total.post_card_5m.card_flow_continued_flag → boolean → unknown
Maçta toplam kart bandı için bir karttan sonraki 5 dakikada sertlik arttı mı? → market.cards_total.post_card_5m.physicality_up_flag → boolean → unknown
Maçta toplam kart bandı için bir karttan sonraki 5 dakikada oyun daha çok durdu mu? → market.cards_total.post_card_5m.flow_stoppage_up_flag → boolean → unknown

Maçta ilk kart bandı gerçekleşti mi? → market.first_card.occurred_flag → boolean → unknown
Maçta ilk kartın dakikası nedir? → market.first_card.minute → integer → unknown
Maçta ilk kart hangi takıma çıktı? → market.first_card.team → enum (home, away) → unknown
Maçta ilk kart türü sarı mı kırmızı mıydı? → market.first_card.type → enum (yellow, red) → unknown
Maçta ilk kart “itiraz” mı “taktik faul” müydü? → market.first_card.cause → enum (appeal, tactical_foul) → unknown

Maçta ilk 5 dakikada kart oldu mu? → market.cards.m0_5.occurred_flag → boolean → unknown
Maçta ilk 10 dakikada kart oldu mu? → market.cards.m0_10.occurred_flag → boolean → unknown
Maçta ilk kart 0–5 dakikada mı çıktı? → market.first_card.window.m0_5.flag → boolean → unknown
Maçta ilk kart 6–10 dakikada mı çıktı? → market.first_card.window.m6_10.flag → boolean → unknown
Maçta ilk kart 11–15 dakikada mı çıktı? → market.first_card.window.m11_15.flag → boolean → unknown
Maçta ilk kart 16–20 dakikada mı çıktı? → market.first_card.window.m16_20.flag → boolean → unknown

Maçta ilk kart ev sahibine mi çıktı? → market.first_card.by_side.home_flag → boolean → unknown
Maçta ilk kart deplasmana mı çıktı? → market.first_card.by_side.away_flag → boolean → unknown
Maçta ilk kartı gören oyuncu savunma oyuncusu muydu? → market.first_card.player_role.defender_flag → boolean → unknown
Maçta ilk kartı gören oyuncu orta saha oyuncusu muydu? → market.first_card.player_role.midfielder_flag → boolean → unknown
Maçta ilk kartı gören oyuncu hücum oyuncusu muydu? → market.first_card.player_role.attacker_flag → boolean → unknown

Maçta ilk karttan sonraki 5 dakikada aynı takıma ikinci kart çıktı mı? → market.first_card.post_5m.same_team_second_card_flag → boolean → unknown
Maçta ilk karttan sonraki 10 dakikada aynı takıma ikinci kart çıktı mı? → market.first_card.post_10m.same_team_second_card_flag → boolean → unknown
Maçta ilk karttan sonraki 5 dakikada rakip takıma kart çıktı mı? → market.first_card.post_5m.opponent_card_flag → boolean → unknown
Maçta ilk karttan sonraki 10 dakikada rakip takıma kart çıktı mı? → market.first_card.post_10m.opponent_card_flag → boolean → unknown
Maçta ilk karttan sonraki 5 dakikada oyun sertliği arttı mı? → market.first_card.post_5m.physicality_up_flag → boolean → unknown
Maçta ilk karttan sonraki 5 dakikada hakem standardı sertleşti mi? → market.first_card.post_5m.referee_hardened_flag → boolean → unknown

Maçta penaltı olur mu bandı gerçekleşti mi? → market.penalty.occurred_flag → boolean → unknown
Maçta penaltı kararı VAR ile mi geldi? → market.penalty.decision_by_var_flag → boolean → unknown
Maçta penaltı kararı hakem kararıyla mı geldi? → market.penalty.decision_by_referee_flag → boolean → unknown
Maçta penaltı iptali VAR ile mi geldi? → market.penalty.overturned_by_var_flag → boolean → unknown
Maçta penaltı iptali sonrası kontrol bandı bozuldu mu? → market.penalty.overturned.post_event.control_band_disrupted_flag → boolean → unknown

Maçta ilk yarıda penaltı oldu mu? → market.penalty.half1.occurred_flag → boolean → unknown
Maçta ikinci yarıda penaltı oldu mu? → market.penalty.half2.occurred_flag → boolean → unknown
Maçta penaltı kararı 0–30 dakikada mı geldi? → market.penalty.window.m0_30.flag → boolean → unknown
Maçta penaltı kararı 31–60 dakikada mı geldi? → market.penalty.window.m31_60.flag → boolean → unknown
Maçta penaltı kararı 61–90+ dakikada mı geldi? → market.penalty.window.m61_90_plus.flag → boolean → unknown
Maçta penaltı kararı ev sahibi lehine mi geldi? → market.penalty.by_side.home_flag → boolean → unknown
Maçta penaltı kararı deplasman lehine mi geldi? → market.penalty.by_side.away_flag → boolean → unknown

Maçta VAR incelemesi sonrası penaltı verildi mi? → market.penalty.var_review.result_awarded_flag → boolean → unknown
Maçta VAR incelemesi sonrası penaltı iptal edildi mi? → market.penalty.var_review.result_overturned_flag → boolean → unknown
Maçta penaltı kararı sonrası ilk 5 dakikada sertlik arttı mı? → market.penalty.post_decision_5m.physicality_up_flag → boolean → unknown
Maçta penaltı kararı sonrası ilk 5 dakikada kart çıktı mı? → market.penalty.post_decision_5m.card_given_flag → boolean → unknown
Maçta penaltı kararı sonrası ilk 5 dakikada korner baskısı arttı mı? → market.penalty.post_decision_5m.corner_pressure_up_flag → boolean → unknown
Maçta penaltı kararı sonrası sonraki 10 dakikada oyun kontrolü değişti mi? → market.penalty.post_decision_10m.game_control_changed_flag → boolean → unknown
Maçta penaltı iptali sonrası ilk 5 dakikada hakem baskısı arttı mı? → market.penalty.overturned.post_5m.referee_pressure_up_flag → boolean → unknown
Maçta penaltı iptali sonrası ilk 10 dakikada itirazlar arttı mı? → market.penalty.overturned.post_10m.appeals_increase_flag → boolean → unknown

Maçta kırmızı kart olur mu bandı gerçekleşti mi? → market.red_card.occurred_flag → boolean → unknown
Maçta kırmızı kart sinyali ikinci sarı üzerinden mi geldi? → market.red_card.signal.second_yellow_flag → boolean → unknown
Maçta kırmızı kart sinyali direkt kırmızı sertlik üzerinden mi geldi? → market.red_card.signal.direct_red_physicality_flag → boolean → unknown
Maçta kırmızı kart sinyali kavga/gerilim üzerinden mi geldi? → market.red_card.signal.fight_tension_flag → boolean → unknown
Maçta kırmızı kart ilk yarıda oldu mu? → market.red_card.half1.occurred_flag → boolean → unknown
Maçta kırmızı kart ikinci yarıda oldu mu? → market.red_card.half2.occurred_flag → boolean → unknown

Maçta kırmızı kart 0–30 dakikada mı çıktı? → market.red_card.window.m0_30.flag → boolean → unknown
Maçta kırmızı kart 31–60 dakikada mı çıktı? → market.red_card.window.m31_60.flag → boolean → unknown
Maçta kırmızı kart 61–90+ dakikada mı çıktı? → market.red_card.window.m61_90_plus.flag → boolean → unknown
Maçta kırmızı kart ev sahibine mi çıktı? → market.red_card.by_side.home_flag → boolean → unknown
Maçta kırmızı kart deplasmana mı çıktı? → market.red_card.by_side.away_flag → boolean → unknown

Maçta kırmızı karttan sonraki 5 dakikada gol oldu mu? → market.red_card.post_5m.goal_scored_flag → boolean → unknown
Maçta kırmızı karttan sonraki 10 dakikada gol oldu mu? → market.red_card.post_10m.goal_scored_flag → boolean → unknown
Maçta kırmızı karttan sonraki 5 dakikada korner baskısı arttı mı? → market.red_card.post_5m.corner_pressure_up_flag → boolean → unknown
Maçta kırmızı karttan sonraki 10 dakikada kart hızı arttı mı? → market.red_card.post_10m.card_rate_up_flag → boolean → unknown
Maçta kırmızı karttan sonraki 5 dakikada oyun tamamen durdu mu? → market.red_card.post_5m.game_stopped_flag → boolean → unknown
Maçta kırmızı karttan sonraki 10 dakikada oyun kontrolü değişti mi? → market.red_card.post_10m.game_control_changed_flag → boolean → unknown
Maçta kırmızı kart sonrası taktik değişiklik yapıldı mı? → market.red_card.post_event.tactical_change_flag → boolean → unknown
Maçta kırmızı kart sonrası sonraki 5 dakikada itirazlar arttı mı? → market.red_card.post_5m.appeals_increase_flag → boolean → unknown

Maçta ofsayt bandı için ilk 15 dakikada ofsayt hızı “high” mı “mid” mi “low” muydu? → market.offsides_total.rate.m0_15 → enum (high, mid, low) → unknown
Maçta ofsayt bandı için 16–30 dakikada ofsayt hızı “high” mı “mid” mi “low” muydu? → market.offsides_total.rate.m16_30 → enum (high, mid, low) → unknown
Maçta ofsayt bandı için 31–45 dakikada ofsayt hızı “high” mı “mid” mi “low” muydu? → market.offsides_total.rate.m31_45 → enum (high, mid, low) → unknown
Maçta ofsayt bandı için 46–60 dakikada ofsayt hızı “high” mı “mid” mi “low” muydu? → market.offsides_total.rate.m46_60 → enum (high, mid, low) → unknown
Maçta ofsayt bandı için 61–75 dakikada ofsayt hızı “high” mı “mid” mi “low” muydu? → market.offsides_total.rate.m61_75 → enum (high, mid, low) → unknown
Maçta ofsayt bandı için 76–90+ dakikada ofsayt hızı “high” mı “mid” mi “low” muydu? → market.offsides_total.rate.m76_90_plus → enum (high, mid, low) → unknown

Maçta ofsaytlar ilk yarıda tek takımda mı kümelendi? → market.offsides_total.cluster.half1.single_team_flag → boolean → unknown
Maçta ofsaytlar ikinci yarıda tek takımda mı kümelendi? → market.offsides_total.cluster.half2.single_team_flag → boolean → unknown
Maçta ofsaytlar ev sahibi tarafında mı kümelendi? → market.offsides_total.cluster.by_side.home_flag → boolean → unknown
Maçta ofsaytlar deplasman tarafında mı kümelendi? → market.offsides_total.cluster.by_side.away_flag → boolean → unknown
Maçta ofsaytlar ilk yarıda hücum ritmini bozdu mu? → market.offsides_total.impact.half1.attack_rhythm_disrupted_flag → boolean → unknown
Maçta ofsaytlar ikinci yarıda hücum ritmini bozdu mu? → market.offsides_total.impact.half2.attack_rhythm_disrupted_flag → boolean → unknown

Maçta ofsaytlar son 15 dakikada hücum ritmini bozdu mu? → market.offsides_total.impact.last15.attack_rhythm_disrupted_flag → boolean → unknown
Maçta ofsaytlar “arka koşu” stratejisinin parçası mıydı? → market.offsides_total.cause.back_run_strategy_flag → boolean → unknown
Maçta ofsaytların çoğu aynı 10 dakikalık dilimde mi geldi? → market.offsides_total.concentration.single_10m_window_flag → boolean → unknown
Maçta bir ofsayttan sonraki 5 dakikada yeni ofsayt geldi mi? → market.offsides_total.post_offside_5m.new_offside_flag → boolean → unknown
Maçta ofsayt sonrası sonraki 5 dakikada hücum temposu düştü mü? → market.offsides_total.post_offside_5m.attack_tempo_down_flag → boolean → unknown
Maçta ofsayt sonrası sonraki 10 dakikada hücum yönü değişti mi? → market.offsides_total.post_offside_10m.attack_direction_changed_flag → boolean → unknown

Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon oldu mu? → market.et_goal.big_chance.occurred_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon hangi dakikada oldu? → market.et_goal.big_chance.minute → integer → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon hangi takım lehine oldu? → market.et_goal.big_chance.favored_team → enum (home, away) → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyonu hangi oyuncu bitirdi? → market.et_goal.big_chance.finisher_player_name → string → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyonu hangi oyuncu hazırladı? → market.et_goal.big_chance.assist_player_name → string → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon hangi hücum şekliyle geldi? → market.et_goal.big_chance.attack_type → enum (open_play, set_piece, counter_attack, corner, free_kick, penalty, long_ball, cross) → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon sonrası sonraki 5 dakikada tempo yükseldi mi? → market.et_goal.big_chance.post_5m.tempo_up_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon sonrası sonraki 5 dakikada korner yoğunluğu arttı mı? → market.et_goal.big_chance.post_5m.corners_increase_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → market.et_goal.big_chance.post_5m.cards_fouls_increase_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon sonrası sonraki 5 dakikada kaleci kurtarış bandı yükseldi mi? → market.et_goal.big_chance.post_5m.goalkeeper_saves_up_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon sonrası sonraki 5 dakikada savunma panik/dağılma belirtisi oluştu mu? → market.et_goal.big_chance.post_5m.defense_panic_flag → boolean → unknown

Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon öncesi son 3 dakikada baskı birikimi var mıydı? → market.et_goal.big_chance.pre_3m.pressure_build_up_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon öncesi son 3 dakikada korner birikimi var mıydı? → market.et_goal.big_chance.pre_3m.corner_build_up_flag → boolean → unknown
Maçta uzatmada gol olur bandı için uzatma dakikalarında net pozisyon öncesi son 3 dakikada faul-duran top yoğunluğu arttı mı? → market.et_goal.big_chance.pre_3m.foul_set_piece_increase_flag → boolean → unknown

Maçta sonraki maç için takımın “disiplin risk bandı” yükseldi mi? → risk.next_match.discipline_band.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi hangi dakikalarda tetiklendi? → risk.next_match.discipline_band.trigger_minutes → list → unknown
Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi hangi oyuncularla ilişkiliydi? → risk.next_match.discipline_band.related_players → list → unknown
Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi hangi pozisyon grubunda yoğunlaştı? → risk.next_match.discipline_band.position_group → enum (defenders, midfielders, attackers, mixed) → unknown
Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi hangi olay tipleriyle geldi? → risk.next_match.discipline_band.trigger_event_types → list → unknown

Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → risk.next_match.discipline_band.post_5m.cards_fouls_increase_flag → boolean → unknown
Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi sonrası sonraki 5 dakikada teknik alan gerilimi arttı mı? → risk.next_match.discipline_band.post_5m.technical_area_tension_up_flag → boolean → unknown
Maçta sonraki maç için takımın “disiplin risk bandı” yükselişi sonrası sonraki 5 dakikada oyun kontrol bandı düştü mü? → risk.next_match.discipline_band.post_5m.game_control_down_flag → boolean → unknown

Maçta sonraki maç için takımın “kart sınırı riski” büyüdü mü? → risk.next_match.card_limit.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “kart sınırı riski” büyümesi hangi dakikada başladı? → risk.next_match.card_limit.increase_start_minute → integer → unknown
Maçta sonraki maç için takımın “kart sınırı riski” büyümesi hangi oyuncu üzerinde oluştu? → risk.next_match.card_limit.affected_player_name → string → unknown
Maçta sonraki maç için takımın “kart sınırı riski” büyümesi hangi kart türleriyle arttı? → risk.next_match.card_limit.card_types → list → unknown
Maçta sonraki maç için takımın “kart sınırı riski” büyümesi sonrası sonraki 5 dakikada faul yoğunluğu arttı mı? → risk.next_match.card_limit.post_5m.fouls_increase_flag → boolean → unknown
Maçta sonraki maç için takımın “kart sınırı riski” büyümesi sonrası sonraki 5 dakikada itiraz/gerilim arttı mı? → risk.next_match.card_limit.post_5m.appeal_tension_up_flag → boolean → unknown
Maçta sonraki maç için takımın “kart sınırı riski” büyümesi hakem standardı algısını etkiledi mi? → risk.next_match.card_limit.referee_standard_impact_flag → boolean → unknown

Maçta sonraki maç için takımın “sakatlık riski” büyüdü mü? → risk.next_match.injury.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “sakatlık riski” büyümesi hangi dakikada tetiklendi? → risk.next_match.injury.trigger_minute → integer → unknown
Maçta sonraki maç için takımın “sakatlık riski” büyümesi hangi oyuncu üzerinde oluştu? → risk.next_match.injury.affected_player_name → string → unknown
Maçta sonraki maç için takımın “sakatlık riski” büyümesi hangi pozisyonda başladı? → risk.next_match.injury.event_zone → enum (defensive_third, middle_third, attacking_third, mixed) → unknown
Maçta sonraki maç için takımın “sakatlık riski” büyümesi sonrası sonraki 5 dakikada tempo düştü mü? → risk.next_match.injury.post_5m.tempo_down_flag → boolean → unknown
Maçta sonraki maç için takımın “sakatlık riski” büyümesi sonrası sonraki 5 dakikada oyuncu değişikliği baskısı arttı mı? → risk.next_match.injury.post_5m.substitution_pressure_up_flag → boolean → unknown
Maçta sonraki maç için takımın “sakatlık riski” büyümesi sonrası sonraki 5 dakikada ikili mücadele yoğunluğu azaldı mı? → risk.next_match.injury.post_5m.duels_intensity_down_flag → boolean → unknown

Maçta sonraki maç için takımın “hakem tepkisi” riski büyüdü mü? → risk.next_match.referee_reaction.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi hangi dakikalarda arttı? → risk.next_match.referee_reaction.increase_minutes → list → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi hangi oyuncular üzerinden yükseldi? → risk.next_match.referee_reaction.related_players → list → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi hangi olaydan sonra tetiklendi? → risk.next_match.referee_reaction.trigger_event → enum (goal, red_card, penalty, var_review, disallowed_goal, injury, time_waste, unknown) → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi sonrası sonraki 5 dakikada kart riski arttı mı? → risk.next_match.referee_reaction.post_5m.card_risk_up_flag → boolean → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi sonrası sonraki 5 dakikada oyun kontrol bandı düştü mü? → risk.next_match.referee_reaction.post_5m.game_control_down_flag → boolean → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi sonrası sonraki 5 dakikada tribün tepkisi yükseldi mi? → risk.next_match.referee_reaction.post_5m.crowd_reaction_up_flag → boolean → unknown

Maçta sonraki maç için takımın “tribün baskısı” riski büyüdü mü? → risk.next_match.crowd_pressure.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi hangi dakikada başladı? → risk.next_match.crowd_pressure.increase_start_minute → integer → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi hangi olayla tetiklendi? → risk.next_match.crowd_pressure.trigger_event → enum (goal, red_card, penalty, var_review, disallowed_goal, referee_decision, time_waste, unknown) → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi hangi takım aleyhine yoğunlaştı? → risk.next_match.crowd_pressure.affected_team → enum (home, away) → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi sonrası sonraki 5 dakikada oyuncu itirazları arttı mı? → risk.next_match.crowd_pressure.post_5m.player_appeals_up_flag → boolean → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi sonrası sonraki 5 dakikada tempo bandı tempo_down oldu mu? → risk.next_match.crowd_pressure.post_5m.tempo_down_flag → boolean → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → risk.next_match.crowd_pressure.post_5m.cards_fouls_increase_flag → boolean → unknown

Maçta sonraki maç için takımın “hakem tepkisi” riski büyüdü mü? → risk.next_match.referee_reaction.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi hangi dakikalarda arttı? → risk.next_match.referee_reaction.increase_minutes → list → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi hangi oyuncular üzerinden yükseldi? → risk.next_match.referee_reaction.related_players → list → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi hangi olaydan sonra tetiklendi? → risk.next_match.referee_reaction.trigger_event → enum (goal, red_card, penalty, var_review, disallowed_goal, injury, time_waste, unknown) → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi sonrası sonraki 5 dakikada kart riski arttı mı? → risk.next_match.referee_reaction.post_5m.card_risk_up_flag → boolean → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi sonrası sonraki 5 dakikada oyun kontrol bandı düştü mü? → risk.next_match.referee_reaction.post_5m.game_control_down_flag → boolean → unknown
Maçta sonraki maç için takımın “hakem tepkisi” riski büyümesi sonrası sonraki 5 dakikada tribün tepkisi yükseldi mi? → risk.next_match.referee_reaction.post_5m.crowd_reaction_up_flag → boolean → unknown

Maçta sonraki maç için takımın “tribün baskısı” riski büyüdü mü? → risk.next_match.crowd_pressure.increased_flag → boolean → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi hangi dakikada başladı? → risk.next_match.crowd_pressure.increase_start_minute → integer → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi hangi olayla tetiklendi? → risk.next_match.crowd_pressure.trigger_event → enum (goal, red_card, penalty, var_review, disallowed_goal, referee_decision, time_waste, unknown) → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi hangi takım aleyhine yoğunlaştı? → risk.next_match.crowd_pressure.affected_team → enum (home, away) → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi sonrası sonraki 5 dakikada oyuncu itirazları arttı mı? → risk.next_match.crowd_pressure.post_5m.player_appeals_up_flag → boolean → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi sonrası sonraki 5 dakikada tempo bandı tempo_down oldu mu? → risk.next_match.crowd_pressure.post_5m.tempo_down_flag → boolean → unknown
Maçta sonraki maç için takımın “tribün baskısı” riski büyümesi sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → risk.next_match.crowd_pressure.post_5m.cards_fouls_increase_flag → boolean → unknown

Bu maçta bahis odaklı kırılmalar “tempo” yoğunluğu sonrası sonraki 5 dakikada net pozisyon çıktı mı? → betting.breakpoints.focus.tempo.post_5m.big_chance_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “tempo” yoğunluğu sonrası sonraki 5 dakikada korner yoğunluğu arttı mı? → betting.breakpoints.focus.tempo.post_5m.corners_increase_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “kart” üzerinden mi yoğunlaştı? → betting.breakpoints.focus.cards_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “kart” yoğunluğu hangi dakikada arttı? → betting.breakpoints.focus.cards.increase_minute → integer → unknown
Bu maçta bahis odaklı kırılmalar “kart” yoğunluğu hangi takım aleyhine yükseldi? → betting.breakpoints.focus.cards.affected_team → enum (home, away) → unknown
Bu maçta bahis odaklı kırılmalar “kart” yoğunluğu hangi oyuncuda kümelendi? → betting.breakpoints.focus.cards.focus_player_name → string → unknown

Bu maçta bahis odaklı kırılmalar “kart” yoğunluğu sonrası sonraki 5 dakikada tempo düştü mü? → betting.breakpoints.focus.cards.post_5m.tempo_down_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “kart” yoğunluğu sonrası sonraki 5 dakikada hakem itirazları arttı mı? → betting.breakpoints.focus.cards.post_5m.referee_appeals_up_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “korner” üzerinden mi yoğunlaştı? → betting.breakpoints.focus.corners_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “korner” yoğunluğu hangi dakikalarda arttı? → betting.breakpoints.focus.corners.increase_minutes → list → unknown
Bu maçta bahis odaklı kırılmalar “korner” yoğunluğu hangi takım lehineydi? → betting.breakpoints.focus.corners.favored_team → enum (home, away) → unknown
Bu maçta bahis odaklı kırılmalar “korner” yoğunluğu sonrası sonraki 5 dakikada net pozisyon çıktı mı? → betting.breakpoints.focus.corners.post_5m.big_chance_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “korner” yoğunluğu sonrası sonraki 5 dakikada gol riski yükseldi mi? → betting.breakpoints.focus.corners.post_5m.goal_risk_up_flag → boolean → unknown

Bu maçta bahis odaklı kırılmalar “penaltı” üzerinden mi yoğunlaştı? → betting.breakpoints.focus.penalty_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “penaltı” yoğunluğu hangi dakikada tetiklendi? → betting.breakpoints.focus.penalty.trigger_minute → integer → unknown
Bu maçta bahis odaklı kırılmalar “penaltı” yoğunluğu hangi takım lehine oldu? → betting.breakpoints.focus.penalty.favored_team → enum (home, away) → unknown
Bu maçta bahis odaklı kırılmalar “penaltı” yoğunluğu sonrası sonraki 5 dakikada kart/faul bandı arttı mı? → betting.breakpoints.focus.penalty.post_5m.cards_fouls_increase_flag → boolean → unknown
Bu maçta bahis odaklı kırılmalar “penaltı” yoğunluğu sonrası sonraki 5 dakikada VAR incelemesi geldi mi? → betting.breakpoints.focus.penalty.post_5m.var_review_flag → boolean → unknownB

Bu maçta yardımcı hakem (yan hakem) kritik ofsayt kararı verdi mi? → officials.assistant_referee.critical_offside.decision_flag → boolean → unknown
Bu maçta yardımcı hakem kritik ofsayt kararını hangi dakikada verdi? → officials.assistant_referee.critical_offside.minute → integer → unknown
Bu maçta yardımcı hakem kritik ofsayt kararını hangi hücumda verdi? → officials.assistant_referee.critical_offside.attack_phase → enum (open_play, counter_attack, set_piece, unknown) → unknown
Bu maçta yardımcı hakem kritik ofsayt kararını hangi takım aleyhine verdi? → officials.assistant_referee.critical_offside.affected_team → enum (home, away) → unknown
Bu maçta yardımcı hakem kritik ofsayt kararında bayrak gecikmesi oldu mu? → officials.assistant_referee.critical_offside.flag_delay_flag → boolean → unknown
Bu maçta yardımcı hakem kritik ofsayt kararı sonrası sonraki 5 dakikada tribün tepkisi yükseldi mi? → officials.assistant_referee.critical_offside.post_5m.crowd_reaction_up_flag → boolean → unknown
Bu maçta yardımcı hakem kritik ofsayt kararı sonrası sonraki 5 dakikada oyuncu itirazı arttı mı? → officials.assistant_referee.critical_offside.post_5m.player_appeals_up_flag → boolean → unknown

Bu maçta yardımcı hakem ofsayt kararı maçın skorunu etkiledi mi? → officials.assistant_referee.offside.score_impact_flag → boolean → unknown
Bu maçta yardımcı hakem ofsayt kararı maçın skorunu hangi yönde etkiledi? → officials.assistant_referee.offside.score_impact_direction → enum (benefited_home, benefited_away) → unknown
Bu maçta yardımcı hakem ofsayt kararı sonrası sonraki 5 dakikada tempo değişti mi? → officials.assistant_referee.offside.post_5m.tempo_changed_flag → boolean → unknown
Bu maçta yardımcı hakem ofsayt kararı iptal gol üretti mi? → officials.assistant_referee.offside.disallowed_goal_flag → boolean → unknown
Bu maçta yardımcı hakem ofsayt kararıyla iptal gol hangi dakikada oldu? → officials.assistant_referee.offside.disallowed_goal_minute → integer → unknown
Bu maçta yardımcı hakem ofsayt kararıyla iptal gol hangi takımın golüydü? → officials.assistant_referee.offside.disallowed_goal_team → enum (home, away) → unknown
Bu maçta yardımcı hakem ofsayt kararıyla iptal gol sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → officials.assistant_referee.offside.disallowed_goal.post_5m.cards_fouls_increase_flag → boolean → unknown
Bu maçta yardımcı hakem ofsayt kararıyla iptal gol sonrası sonraki 5 dakikada VAR incelemesi baskısı arttı mı? → officials.assistant_referee.offside.disallowed_goal.post_5m.var_pressure_up_flag → boolean → unknown

Bu maçta yardımcı hakem ofsayt bayrağı gecikmeli mi kalktı? → officials.assistant_referee.offside.flag_delay.occurred_flag → boolean → unknown
Bu maçta yardımcı hakem ofsayt bayrağı gecikmesi hangi dakikalarda tekrar etti? → officials.assistant_referee.offside.flag_delay.repeat_minutes → list → unknown
Bu maçta yardımcı hakem ofsayt bayrağı gecikmesi hangi takım lehine avantaj üretti mi? → officials.assistant_referee.offside.flag_delay.advantaged_team → enum (home, away, none) → unknown
Bu maçta yardımcı hakem ofsayt bayrağı erken mi kalktı? → officials.assistant_referee.offside.flag_early.occurred_flag → boolean → unknown
Bu maçta yardımcı hakem ofsayt bayrağı erken kalkışı hangi dakikada oldu? → officials.assistant_referee.offside.flag_early.minute → integer → unknown
Bu maçta yardımcı hakem ofsayt bayrağı erken kalkışı net pozisyonu kesti mi? → officials.assistant_referee.offside.flag_early.cut_big_chance_flag → boolean → unknown
Bu maçta yardımcı hakemin ofsayt standardı iki takım için tutarlı mıydı? → officials.assistant_referee.offside.standard_consistent_flag → boolean → unknown
Bu maçta yardımcı hakemin ofsayt standardı hangi dakikada tartışma üretti? → officials.assistant_referee.offside.standard_dispute_minute → integer → unknown
Bu maçta yardımcı hakemin ofsayt standardı hangi takım için daha sert algılandı? → officials.assistant_referee.offside.standard_perceived_harsher_for_team → enum (home, away) → unknown

Bu maçta yardımcı hakem taç kararlarında hataya açık bir bant üretti mi? → officials.assistant_referee.throw_in.error_prone_band_flag → boolean → unknown
Bu maçta yardımcı hakem taç kararlarında hataya açık bant hangi dakikalarda yoğunlaştı? → officials.assistant_referee.throw_in.error_prone_band.minutes → list → unknown
Bu maçta yardımcı hakem taç kararlarında hataya açık bant hangi kanatta oluştu? → officials.assistant_referee.throw_in.error_prone_band.side → enum (left, right, mixed) → unknown
Bu maçta yardımcı hakem taç kararlarındaki hataya açık bant sonrası sonraki 5 dakikada baskı yönü değişti mi? → officials.assistant_referee.throw_in.error_prone_band.post_5m.pressure_direction_changed_flag → boolean → unknown
Bu maçta yardımcı hakem taç kararları baskı yönünü etkiledi mi? → officials.assistant_referee.throw_in.pressure_direction_impact_flag → boolean → unknown
Bu maçta yardımcı hakem taç kararları baskı yönünü hangi takım lehine çevirdi? → officials.assistant_referee.throw_in.pressure_shifted_to_team → enum (home, away) → unknown
Bu maçta yardımcı hakem taç kararları baskı yönünü hangi dakikada değiştirdi? → officials.assistant_referee.throw_in.pressure_shift_minute → integer → unknown

Bu maçta yardımcı hakem aut/köşe kararları tartışma üretti mi? → officials.assistant_referee.goal_kick_corner.debate_flag → boolean → unknown
Bu maçta yardımcı hakem aut/köşe kararları tartışması hangi dakikada çıktı? → officials.assistant_referee.goal_kick_corner.debate_minute → integer → unknown
Bu maçta yardımcı hakem aut/köşe kararları tartışması hangi takım aleyhineydi? → officials.assistant_referee.goal_kick_corner.debate_affected_team → enum (home, away) → unknown
Bu maçta yardımcı hakem köşe vuruşu kararları skor riski yarattı mı? → officials.assistant_referee.corner_decisions.score_risk_flag → boolean → unknown
Bu maçta yardımcı hakem köşe vuruşu kararları skor riskini hangi dakikada artırdı? → officials.assistant_referee.corner_decisions.score_risk_minute → integer → unknown
Bu maçta yardımcı hakem köşe vuruşu kararları skor riskini hangi takım lehine artırdı? → officials.assistant_referee.corner_decisions.score_risk_favored_team → enum (home, away) → unknown

Bu maçta yardımcı hakem faul avantajı konusunda orta hakemle çelişti mi? → officials.assistant_referee.advantage.foul_contradiction_flag → boolean → unknown
Bu maçta yardımcı hakem faul avantajı konusunda orta hakemle çelişki hangi dakikada oldu? → officials.assistant_referee.advantage.foul_contradiction_minute → integer → unknown
Bu maçta yardımcı hakem faul avantajı çelişkisi sonrası sonraki 5 dakikada itiraz arttı mı? → officials.assistant_referee.advantage.foul_contradiction.post_5m.appeals_increase_flag → boolean → unknown

Bu maçta yardımcı hakem “yakın çizgi faulleri” için sık bayrak kaldırdı mı? → officials.assistant_referee.touchline_fouls.frequent_flagging_flag → boolean → unknown
Bu maçta yardımcı hakem “yakın çizgi faulleri” için bayrak sıklığı hangi dakikalarda arttı? → officials.assistant_referee.touchline_fouls.flagging_increase_minutes → list → unknown
Bu maçta yardımcı hakem “yakın çizgi faulleri” hangi kanatta yoğunlaştı? → officials.assistant_referee.touchline_fouls.dominant_side → enum (left, right, mixed) → unknown
Bu maçta yardımcı hakem “yakın çizgi faulleri” için baskın biçimde oyunu durdurdu mu? → officials.assistant_referee.touchline_fouls.stoppage_bias_flag → boolean → unknown
Bu maçta yardımcı hakem “yakın çizgi faulleri” oyunu durdurması hangi dakikada tempo kırdı? → officials.assistant_referee.touchline_fouls.stoppage_break_minute → integer → unknown
Bu maçta yardımcı hakem “yakın çizgi faulleri” oyunu durdurması sonrası sonraki 5 dakikada kart/faul arttı mı? → officials.assistant_referee.touchline_fouls.post_5m.cards_fouls_increase_flag → boolean → unknown

Bu maçta yardımcı hakem bir penaltı pozisyonunda yönlendirici oldu mu? → officials.assistant_referee.penalty.influential_flag → boolean → unknown
Bu maçta yardımcı hakem bir penaltı pozisyonunda yönlendirici rol hangi dakikada oldu? → officials.assistant_referee.penalty.influential_minute → integer → unknown
Bu maçta yardımcı hakem bir penaltı pozisyonunda yönlendirici rol hangi takım lehine algılandı? → officials.assistant_referee.penalty.influential_perceived_favored_team → enum (home, away) → unknown
Bu maçta yardımcı hakem bir kırmızı kart pozisyonunda yönlendirici oldu mu? → officials.assistant_referee.red_card.influential_flag → boolean → unknown
Bu maçta yardımcı hakem bir kırmızı kart pozisyonunda yönlendirici rol hangi dakikada oldu? → officials.assistant_referee.red_card.influential_minute → integer → unknown
Bu maçta yardımcı hakem bir kırmızı kart pozisyonunda yönlendirici rol hangi takım aleyhine algılandı? → officials.assistant_referee.red_card.influential_perceived_affected_team → enum (home, away) → unknown

Bu maçta yardımcı hakem saha içi gerginliği artıran bir tetikleyiciye dönüştü mü? → officials.assistant_referee.tension.trigger_flag → boolean → unknown
Bu maçta yardımcı hakem gerginliği artıran tetikleyici rol hangi olay sonrası başladı? → officials.assistant_referee.tension.trigger_after_event → enum (offside, throw_in, corner_decision, foul_advantage, unknown) → unknown
Bu maçta yardımcı hakem gerginliği artıran tetikleyici rol sonrası sonraki 5 dakikada kart riski yükseldi mi? → officials.assistant_referee.tension.post_5m.card_risk_up_flag → boolean → unknown

Bu maçta yardımcı hakemin kararları tribün baskısını büyüttü mü? → officials.assistant_referee.decisions.crowd_pressure_up_flag → boolean → unknown
Bu maçta yardımcı hakemin kararları tribün baskısını büyütmesi hangi dakikada zirve yaptı? → officials.assistant_referee.decisions.crowd_pressure_peak_minute → integer → unknown
Bu maçta yardımcı hakemin kararları tribün baskısını büyütmesi hangi takım aleyhineydi? → officials.assistant_referee.decisions.crowd_pressure_affected_team → enum (home, away) → unknown
Bu maçta yardımcı hakemin kararları oyuncu itirazını artırdı mı? → officials.assistant_referee.decisions.player_appeals_up_flag → boolean → unknown
Bu maçta yardımcı hakemin kararları oyuncu itirazını artırması hangi dakikada yoğunlaştı? → officials.assistant_referee.decisions.player_appeals_peak_minute → integer → unknown
Bu maçta yardımcı hakemin kararları oyuncu itirazını artırması sonrası sonraki 5 dakikada kart çıktı mı? → officials.assistant_referee.decisions.post_5m.card_given_flag → boolean → unknown

Bu maçta 4. hakem ile teknik direktör arasında gerilim oldu mu? → officials.fourth_official.coach_tension.occurred_flag → boolean → unknown
Bu maçta 4. hakem ile teknik direktör gerilimi hangi dakikada başladı? → officials.fourth_official.coach_tension.start_minute → integer → unknown
Bu maçta 4. hakem ile teknik direktör gerilimi hangi takım kulübesinde çıktı? → officials.fourth_official.coach_tension.team_bench → enum (home, away) → unknown
Bu maçta 4. hakem ile teknik direktör gerilimi sonrası sonraki 5 dakikada kulübe kartı çıktı mı? → officials.fourth_official.coach_tension.post_5m.bench_card_flag → boolean → unknown
Bu maçta 4. hakem kulübeleri sık uyardı mı? → officials.fourth_official.bench_warnings.frequent_flag → boolean → unknown
Bu maçta 4. hakem kulübeleri sık uyarması hangi dakikalarda arttı? → officials.fourth_official.bench_warnings.increase_minutes → list → unknown
Bu maçta 4. hakem kulübeleri sık uyarması hangi takım kulübesinde yoğunlaştı? → officials.fourth_official.bench_warnings.dominant_bench → enum (home, away) → unknown

Bu maçta 4. hakem oyuna giren çıkan oyuncu prosedürünü sıkı tuttu mu? → officials.fourth_official.substitution_procedure.strict_flag → boolean → unknown
Bu maçta 4. hakem oyuncu prosedürü sıkılığı hangi değişiklikte tartışma üretti? → officials.fourth_official.substitution_procedure.disputed_substitution → string → unknown
Bu maçta 4. hakem oyuncu prosedürü sıkılığı sonrası sonraki 5 dakikada tempo düştü mü? → officials.fourth_official.substitution_procedure.post_5m.tempo_down_flag → boolean → unknown
Bu maçta 4. hakem uzatma süresi tartışması yarattı mı? → officials.fourth_official.added_time.dispute_flag → boolean → unknown
Bu maçta 4. hakem uzatma süresi tartışması hangi dakikada başladı? → officials.fourth_official.added_time.dispute_start_minute → integer → unknown
Bu maçta 4. hakem uzatma süresi tartışması hangi takım aleyhine algılandı? → officials.fourth_official.added_time.dispute_affected_team → enum (home, away) → unknown
Bu maçta 4. hakem uzatma süresi tartışması sonrası sonraki 5 dakikada tribün tepkisi yükseldi mi? → officials.fourth_official.added_time.dispute.post_5m.crowd_reaction_up_flag → boolean → unknown

Bu maçta 4. hakemin gösterdiği uzatma süresi maçın temposunu değiştirdi mi? → officials.fourth_official.added_time.tempo_impact_flag → boolean → unknown
Bu maçta 4. hakemin gösterdiği uzatma süresi tempo değişimini hangi dakikada üretti? → officials.fourth_official.added_time.tempo_change_minute → integer → unknown
Bu maçta 4. hakemin gösterdiği uzatma süresi tempo değişimi sonrası sonraki 5 dakikada korner yoğunluğu arttı mı? → officials.fourth_official.added_time.post_5m.corners_increase_flag → boolean → unknown
Bu maçta 4. hakemin uzatma kararı tribün baskısını artırdı mı? → officials.fourth_official.added_time.crowd_pressure_up_flag → boolean → unknown
Bu maçta 4. hakemin uzatma kararı tribün baskısını artırması hangi dakikada zirve yaptı? → officials.fourth_official.added_time.crowd_pressure_peak_minute → integer → unknown
Bu maçta 4. hakemin uzatma kararı tribün baskısını artırması hangi takım aleyhineydi? → officials.fourth_official.added_time.crowd_pressure_affected_team → enum (home, away) → unknown

Bu maçta 4. hakem kulübeye kart gösterdi mi? → officials.fourth_official.bench_card.occurred_flag → boolean → unknown
Bu maçta 4. hakem kulübeye kart hangi dakikada çıktı? → officials.fourth_official.bench_card.minute → integer → unknown
Bu maçta 4. hakem kulübeye kart hangi aktöre çıktı? → officials.fourth_official.bench_card.recipient_role → enum (coach, assistant_coach, staff, substitute_player, unknown) → unknown
Bu maçta 4. hakem teknik ekip davranışını bastırdı mı yoksa büyüttü mü? → officials.fourth_official.technical_area.effect → enum (suppressed, amplified, neutral) → unknown
Bu maçta 4. hakem teknik ekip davranışını bastırma/büyütme etkisi hangi olaydan sonra oluştu? → officials.fourth_official.technical_area.effect_after_event → enum (bench_warning, bench_card, substitution_dispute, added_time_dispute, unknown) → unknown
Bu maçta 4. hakem teknik ekip davranışını bastırma/büyütme sonrası sonraki 5 dakikada itiraz arttı mı? → officials.fourth_official.technical_area.post_5m.appeals_increase_flag → boolean → unknown

FAZ-7-27
Bu maçta VAR kararı gol iptaline neden oldu mu? → officials.var.disallowed_goal.occurred_flag → boolean → unknown
Bu maçta VAR kararı gol iptaline hangi dakikada neden oldu? → officials.var.disallowed_goal.minute → integer → unknown
Bu maçta VAR kararı gol iptaline hangi takımın lehine neden oldu? → officials.var.disallowed_goal.benefited_team → enum (home, away) → unknown
Bu maçta VAR kararı gol iptali sonrası sonraki 5 dakikada tempo bandı düştü mü? → officials.var.disallowed_goal.post_5m.tempo_down_flag → boolean → unknown
Bu maçta VAR kararı gol iptali sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → officials.var.disallowed_goal.post_5m.cards_fouls_increase_flag → boolean → unknown

Bu maçta VAR kararı penaltı kararına neden oldu mu? → officials.var.penalty.occurred_flag → boolean → unknown
Bu maçta VAR kararı penaltı kararına hangi dakikada neden oldu? → officials.var.penalty.minute → integer → unknown
Bu maçta VAR kararı penaltı kararına hangi takım lehine neden oldu? → officials.var.penalty.favored_team → enum (home, away) → unknown
Bu maçta VAR kararı penaltı sonrası sonraki 5 dakikada itiraz yoğunluğu arttı mı? → officials.var.penalty.post_5m.appeals_increase_flag → boolean → unknown
Bu maçta VAR kararı penaltı sonrası sonraki 5 dakikada tempo bandı değişti mi? → officials.var.penalty.post_5m.tempo_changed_flag → boolean → unknown

Bu maçta VAR kararı kırmızı kart kararına neden oldu mu? → officials.var.red_card.occurred_flag → boolean → unknown
Bu maçta VAR kararı kırmızı kart kararına hangi dakikada neden oldu? → officials.var.red_card.minute → integer → unknown
Bu maçta VAR kararı kırmızı kart kararına hangi takım aleyhine neden oldu? → officials.var.red_card.affected_team → enum (home, away) → unknown
Bu maçta VAR kararı kırmızı kart sonrası sonraki 5 dakikada tempo düştü mü? → officials.var.red_card.post_5m.tempo_down_flag → boolean → unknown
Bu maçta VAR kararı kırmızı kart sonrası sonraki 5 dakikada faul yoğunluğu arttı mı? → officials.var.red_card.post_5m.fouls_increase_flag → boolean → unknown

Bu maçta VAR kararı ofsayt üzerinden iptal gol üretti mi? → officials.var.offside_disallowed_goal.occurred_flag → boolean → unknown
Bu maçta VAR kararı ofsayt üzerinden iptal gol hangi dakikada oldu? → officials.var.offside_disallowed_goal.minute → integer → unknown
Bu maçta VAR kararı ofsayt üzerinden iptal gol hangi takımın golüydü? → officials.var.offside_disallowed_goal.team → enum (home, away) → unknown
Bu maçta VAR kararı ofsayt üzerinden iptal gol sonrası sonraki 5 dakikada tribün tepkisi yükseldi mi? → officials.var.offside_disallowed_goal.post_5m.crowd_reaction_up_flag → boolean → unknown

Bu maçta VAR incelemesi süresi uzun mu kısa mıydı? → officials.var.review.duration_band → enum (short, medium, long) → unknown
Bu maçta VAR incelemesi süresi hangi pozisyonda uzadı? → officials.var.review.long_review_event → enum (goal_disallowed, penalty_check, red_card_check, offside_check, unknown) → unknown
Bu maçta VAR incelemesi süresi uzaması hangi dakikada tempo kırdı? → officials.var.review.tempo_break_minute → integer → unknown
Bu maçta VAR incelemesi süresi uzaması sonrası sonraki 5 dakikada tempo bandı tempo_down oldu mu? → officials.var.review.post_5m.tempo_down_flag → boolean → unknown
Bu maçta VAR incelemesi maçın ritmini kırdı mı? → officials.var.review.rhythm_disrupted_flag → boolean → unknown
Bu maçta VAR incelemesi maçın ritmini kırması hangi dakikada oldu? → officials.var.review.rhythm_disruption_minute → integer → unknown
Bu maçta VAR incelemesi ritim kırması sonrası sonraki 5 dakikada faul yoğunluğu arttı mı? → officials.var.review.post_5m.fouls_increase_flag → boolean → unknown

Bu maçta VAR incelemesi sonrası oyuncu itirazları arttı mı? → officials.var.review.post_review.player_appeals_up_flag → boolean → unknown
Bu maçta VAR incelemesi sonrası oyuncu itirazları artışı hangi takımda yoğunlaştı? → officials.var.review.post_review.player_appeals_team → enum (home, away) → unknown
Bu maçta VAR incelemesi sonrası oyuncu itirazları artışı hangi oyunculardan geldi? → officials.var.review.post_review.player_appeals_players → list → unknown
Bu maçta VAR incelemesi sonrası kart/faul yoğunluğu arttı mı? → officials.var.review.post_review.cards_fouls_increase_flag → boolean → unknown
Bu maçta VAR incelemesi sonrası kart/faul yoğunluğu artışı hangi dakikada başladı? → officials.var.review.post_review.cards_fouls_increase_start_minute → integer → unknown
Bu maçta VAR incelemesi sonrası kart/faul yoğunluğu artışı hangi takım aleyhine yükseldi? → officials.var.review.post_review.cards_fouls_affected_team → enum (home, away) → unknown
Bu maçta VAR incelemesi sonrası kontrol bandı unstable’a kaydı mı? → officials.var.review.post_review.control_band_unstable_flag → boolean → unknown
Bu maçta VAR incelemesi sonrası kontrol bandı unstable’a kayması hangi dakikada başladı? → officials.var.review.post_review.control_band_unstable_start_minute → integer → unknown
Bu maçta VAR incelemesi sonrası kontrol bandı unstable’a kayması sonrası sonraki 5 dakikada kart çıktı mı? → officials.var.review.post_review.post_5m.card_given_flag → boolean → unknown

Bu maçta VAR incelemesi sonrası tempo bandı tempo_down oldu mu? → officials.var.review.post_review.tempo_down_flag → boolean → unknown
Bu maçta VAR incelemesi sonrası tempo bandı tempo_down olması hangi dakikada görüldü? → officials.var.review.post_review.tempo_down_minute → integer → unknown
Bu maçta VAR incelemesi sonrası tempo bandı tempo_down sonrası sonraki 5 dakikada net pozisyon azaldı mı? → officials.var.review.post_review.post_5m.big_chances_down_flag → boolean → unknown
Bu maçta VAR incelemesi sonrası tribün tepkisi yükseldi mi? → officials.var.review.post_review.crowd_reaction_up_flag → boolean → unknown
Bu maçta VAR incelemesi sonrası tribün tepkisi yükselmesi hangi dakikada zirve yaptı? → officials.var.review.post_review.crowd_reaction_peak_minute → integer → unknown
Bu maçta VAR incelemesi sonrası tribün tepkisi hangi takım lehine/aleyhine yoğunlaştı? → officials.var.review.post_review.crowd_reaction_affected_team → enum (home, away) → unknown

Bu maçta VAR kararları iki takım için “standart tutarlı” mıydı? → officials.var.decisions.standard_consistent_flag → boolean → unknown
Bu maçta VAR kararları iki takım için “standart tutarlı” algısı hangi pozisyonlarda güçlendi? → officials.var.decisions.standard_consistent_events → list → unknown
Bu maçta VAR kararları iki takım için “standart tutarlı” algısı sonrası itiraz azaldı mı? → officials.var.decisions.standard_consistent.post_5m.appeals_down_flag → boolean → unknown
Bu maçta VAR kararları “standart dengesiz” algısı yarattı mı? → officials.var.decisions.standard_inconsistent_flag → boolean → unknown
Bu maçta VAR kararları “standart dengesiz” algısı hangi takım aleyhine oluştu? → officials.var.decisions.standard_inconsistent_affected_team → enum (home, away) → unknown
Bu maçta VAR kararları “standart dengesiz” algısı sonrası sonraki 5 dakikada kart riski yükseldi mi? → officials.var.decisions.standard_inconsistent.post_5m.card_risk_up_flag → boolean → unknown

Bu maçta AVAR desteği belirginleşti mi? → officials.avar.support.noticeable_flag → boolean → unknown
Bu maçta AVAR desteği belirginleşmesi hangi dakikada fark edildi? → officials.avar.support.noticeable_minute → integer → unknown
Bu maçta AVAR desteği belirginleşmesi hangi karar tipinde ortaya çıktı? → officials.avar.support.decision_type → enum (offside, penalty_check, red_card_check, goal_check, unknown) → unknown

Bu maçta VAR ekibi ile orta hakem arasında karar gecikmesi oldu mu? → officials.var.communication.decision_delay_flag → boolean → unknown
Bu maçta VAR ekibi ile orta hakem arasında karar gecikmesi hangi pozisyonda oldu? → officials.var.communication.decision_delay_event → enum (goal_disallowed, penalty_check, red_card_check, offside_check, unknown) → unknown
Bu maçta VAR ekibi ile orta hakem arasında karar gecikmesi sonrası sonraki 5 dakikada tempo kırıldı mı? → officials.var.communication.decision_delay.post_5m.tempo_disrupted_flag → boolean → unknown
Bu maçta VAR ekibi ile orta hakem arasında karar uyumsuzluğu iddiası oluştu mu? → officials.var.communication.decision_mismatch_claim_flag → boolean → unknown
Bu maçta VAR ekibi ile orta hakem arasında karar uyumsuzluğu iddiası hangi olaydan sonra çıktı? → officials.var.communication.decision_mismatch_claim_after_event → enum (goal_disallowed, penalty_awarded, red_card, offside, unknown) → unknown
Bu maçta VAR ekibi ile orta hakem arasında karar uyumsuzluğu iddiası hangi takımın itirazıyla yükseldi? → officials.var.communication.decision_mismatch_claim_by_team → enum (home, away) → unknown

Bu maçta VAR sonrası orta hakem otorite problemi yaşadı mı? → officials.referee.authority.post_var.issue_flag → boolean → unknown
Bu maçta VAR sonrası orta hakem otorite problemi hangi dakikada başladı? → officials.referee.authority.post_var.issue_start_minute → integer → unknown
Bu maçta VAR sonrası orta hakem otorite problemi sonrası sonraki 5 dakikada kart/faul yoğunluğu arttı mı? → officials.referee.authority.post_var.post_5m.cards_fouls_increase_flag → boolean → unknown


FAZ-32
BAĞLAM DUVARI VE ADRES SORULARI (FUTBOL)
Bu kayıt hangi tarih penceresinde ve hangi UTC standardında sabitleniyor? Bu soru, tüm zaman hesaplarının tek standarda bağlanması içindir. Tarih penceresi sabitlenmeden sezon fazı, haber penceresi ve maç segmentleri doğru kurulamaz.
Bu kayıt hangi ülke, hangi lig, hangi sezon ve hangi tekil takım kimliği içinde okunuyor? Bu soru, raf adresinin yanlış klasöre düşmesini engeller. Ülke/lig/sezon/takım net değilse aynı isimli ligler veya sezon kaymaları sessiz bozulma üretir.
Bu kayıt lig seviyesinde hangi kütüphaneye aittir (Tier-1, Tier-2 veya Cups)? Bu soru, verinin hangi raf disiplininde tutulacağını kilitler. Tier-1, Tier-2 ve Cups verisi aynı raflarda birleştirilemez; birleştirme sessiz karışma üretir.

Bu kayıt hangi organizasyon tipine aittir (lig, ulusal kupa, kıtasal kupa, süper kupa, milli takım turnuvası)? Bu soru, maçın ve haber akışının hangi organizasyon bağlamında okunacağını belirler. Organizasyon tipi net değilse kupa maçları lig performansına yanlış bağlanır.
Bu kayıt kupa bayrağı taşır mı ve kupa bayrağı hangi seviyededir (domestic\\\_cup veya continental\\\_cup)? Bu soru, kupa verisini ayrı bir sistemde tutmak içindir. Kupa bayrağı yoksa kupa haberleri ve kupa maçları lig akışına karışır ve takım DNA’sı yanlış öğrenilir.
Bu kayıt sezonun hangi fazına denk geliyor (sezon başı, sezon ortası, sezon sonu, sezon arası/off-season)? Bu soru, aynı davranışın sezonun farklı dönemlerinde neden değiştiğini ayırt etmek içindir. Sezon arası dönem, transfer ve kamp etkileri nedeniyle ayrı bağlam olarak tutulur.

Bu kayıt sezon içi mi yoksa sezon arası haftalık paket mi? Bu soru, veri türünü deterministik ayırmak içindir. Sezon arası haber akışı günlük maç akışı gibi işlenmez; haftalık paketlenir ve bağlam rafına yazılır.
Bu kayıt hangi tekil takım perspektifi için açılıyor? Bu soru DNA kartı okuma girişidir. Takım perspektifinde hedef, tek takımı öğrenmek ve takım kartını büyütmektir; rakip burada bağlamdır, kimlik değildir.
Bu kayıt hangi tekil maç perspektifi için açılıyor? Bu soru maç olayı okuma girişidir. Maç perspektifinde hedef, maç kimliğini ve maçın olay zincirini sabitlemektir; bu kayıt daha sonra iki takımın geçmiş eşleşme okumasında referans olur.
Bu kayıt takım perspektifinde açılıyorsa o tarihte takımın teknik direktör kimliği kim? Bu soru, takım davranış değişimini kişi kartlarına bağlamak içindir. Teknik direktör doğru sabitlenmezse takım DNA’sı yanlış kişiye bağlanır ve örüntü bozulur.
Bu kayıt maç perspektifinde açılıyorsa bu maçın hakemi kim? Bu soru, hakemin maç içi disiplin bandını ve karar akışını deterministik bağlamak içindir. Hakem maç nesnesinin parçasıdır ve maç kırılmalarının okunmasında ayrı bir kimliktir.

Bu kayıt takım perspektifinde açılıyorsa takımın bu maç dışında paralel yükü var mı (yakın takvimde başka organizasyon maçı)? Bu soru, takım performansının gerçek bağlamını okumak içindir. Takımın aynı hafta kupa/Avrupa/milli takım dönüşü gibi ek yükleri varsa tempo ve risk davranışı kayabilir.
Bu kayıt takım perspektifinde açılıyorsa takım kadrosunda milli takım dönüşü, seyahat yoğunluğu veya kadro bölünmesi var mı? Bu soru, oyuncu ve takım DNA’sını bozan dış yükleri ayırt etmek içindir. Bu tür yükler yok sayılırsa performans sapması yanlış nedene bağlanır.

Bu maç lig mi kupa mı ve maçın önem sınıfı hangi bantta? Bu soru, aynı takım ama farklı stres sınıfı ayrımını yapar. Maç önemi yoksa benzer görünen maçlar yanlış eşleştirilir.
Bu maç ev/deplasman bağlamında hangi atmosfer sınıfında ve saha koşulu hangi davranış bandına yazılıyor? Bu soru, taraftar baskısı ve saha koşullarının takım davranışını nasıl kaydırdığını ölçmek içindir. Atmosfer sınıfı yoksa normal görünen sapmaların gerçek nedeni kaçabilir.
Bu kayıt tam çözünürlük sezon kaydı mı yoksa iskelet sezon kaydı mı? Bu soru, hangi alt rafların zorunlu dolması gerektiğini belirler. İskelet sezonda bazı alanların boş kalması normal kabul edilir; tam çözünürlük sezonda boşluk data\\\_quality olarak işaretlenir.

MAÇI SEGMENTLERE AYIRAN DNA OKUMA SORULARI (FUTBOL)
Bu maç 90 dakika tek blok olarak okunmaz; deterministik segmentlere bölünür ve her segment için takımın davranış izi ayrı ayrı kaydedilir. Amaç “maç anlatmak” değil, takım DNA’sının hangi zaman dilimlerinde nasıl tepki verdiğini raf hafızasına yerleştirmektir. Segment okuması, kolay maçta yüzey taraması sağlar; zor maçta doğru katmana hızlı iniş verir.
Takımın ilk 15 dakikadaki davranışı nedir ve bu davranış beş yıl boyunca tekrar ediyor mu? Bu soru, takımın maç başlangıç refleksini ölçer. Bazı takımlar sistematik hızlı başlar, bazıları sistematik geç açılır; bu fark sapma okumasında temel bağlamdır.

Takımın 16–30 dakikadaki davranışı nedir ve ilk 15’e göre tempo veya disiplin yön değiştiriyor mu? Bu soru, ilk dalga geçtikten sonra takımın stabilize olup olmadığını gösterir. Eğer bu dilimde kayma oluyorsa kırılma daha erken başlamış olabilir.
Takımın 31–45 dakikadaki davranışı nedir ve devreye giderken risk seviyesi artıyor mu azalıyor mu? Bu soru, ilk yarı kapanış davranışını ölçer. Devre öncesi kartlar, VAR kararları ve skor kırılmaları bu dilimde kader değiştirici çalışabilir.
Takımın devre geçişi davranışı nedir ve ikinci yarıya çıkış refleksi hangi bantta? Bu soru, teknik direktör müdahalesinin ve oyuncu psikolojisinin en net okunduğu eşiktir. Devre çıkışı tempo spike veya çöküş tekrar ediyorsa DNA sinyali güçlenir.
Takımın 46–60 dakikadaki davranışı nedir ve bu dilim takımın tekrar eden “ikinci yarı başlangıç bandı” mı? Bu soru, ikinci yarı başında oluşan sistematik davranışları yakalar. Bazı takımlar bu bantta sürekli baskı yer veya sürekli baskı kurar.

Takımın 61–75 dakikadaki davranışı nedir ve maçın kaderini taşıyan değişimler bu dilimde mi birikiyor? Bu soru, yorgunluk, değişiklikler ve kart birikiminin davranışa yansıdığı orta-son evreyi ölçer. Bu bantta sürekli yön değişiyorsa sapma penceresi genişliyor olabilir.
Takımın son 15 dakikadaki davranışı nedir ve bu davranış skor durumuna göre deterministik değişiyor mu? Bu soru, maç kapatma DNA’sını ölçer. Önde kapatma, geride risk alma veya beraberliğe razı olma davranışları bu segmentte görünür.
Takımın son 5 dakikası ve uzatma dakikalarındaki davranışı nedir ve bu davranış tekrarlı bir panik/soğutma profili üretiyor mu? Bu soru, en yüksek stres anındaki davranışı ölçer. Tek maçta bile kritik olabilir; tekrar ediyorsa DNA’ya dönüşür.

Bu maç segmentlerinde takımın tempo bandı nasıl değişiyor ve tempo değişimi hangi olaylarla eşleşiyor? Bu soru, segment okumasını olay zinciriyle bağlar. Tempo her zaman kendi kendine değişmez; tetikleyiciyle değişir.
Bu maç segmentlerinde takımın disiplin bandı nasıl değişiyor ve kart/faul yoğunluğu hangi dilimde kümeleniyor? Bu soru, takımın sertlik ve kontrol profilini segment bazında çıkarır. Kart davranışı “maç geneli” değil, segment davranışıdır.
Bu maç segmentlerinde takımın karar kalitesi nasıl değişiyor ve hata kümelenmesi hangi dilimde oluşuyor? Bu soru, “sapma”nın çoğu zaman karar kalitesi düşüşüyle başladığını yakalamak içindir. Hata kümelenmesi segment adresi verirse derin okuma hızlanır.

Bu maçta skor durumu segment davranışını nasıl değiştiriyor (öndeyken, beraberken, gerideyken)? Bu soru, aynı segmentin farklı skor bağlamında farklı DNA ürettiğini ayırır. Önde kapatan takım geride dağılabilir; bu ayrım sabitlenmelidir.
Bu maçta maçın kaderi hangi segmentte kırıldı ve kırılma anı hangi tetikleyicilerle başladı? Bu soru, segmentleri yalnız “zaman” değil “kader değişimi” olarak da bağlar. Kırılma segmenti doğru bulunursa analiz raf içinde doğru yere iner.
Bu maçta bir segment içinde “normal bant dışına çıkış” olduysa, bu çıkışın başlangıç işareti neydi? Bu soru, sapmayı en başından yakalamak içindir. Çıkışın ilk işareti kaçarsa sistem yalnız sonuç okur, süreç okuyamaz.

Bu maçta segment davranışı, sezon fazı ve organizasyon tipiyle tutarlı mı yoksa o gün “başka bir takım” gibi mi çalıştı? Bu soru, bağlam duvarı ile segment okumasını birleştirir. Aynı takım ligde başka, kupada başka DNA gösterebilir; bu ayrım kilitlenir.
Takımın bir önceki maç sonucu bir sonraki haftayı deterministik şekilde etkiliyor mu? Bu soru, takımın “sonuç hafızası” olup olmadığını ölçer. Bazı takımlar galibiyet sonrası açılır, bazıları mağlubiyet sonrası toparlanır, bazıları ise seri içine girer.

Takımın galibiyet, beraberlik ve mağlubiyet serisi davranışı var mı ve bu seri davranışı tekrar ediyor mu? Bu soru, takımın karakteristik dalga yapısını yakalar. Seri davranışı varsa takımın risk ve tempo profili seri içinde değişebilir.
Takımın maçlara “yenileceğini bilerek rahat oynama” mı yoksa “beraberliği kurtarma” refleksiyle mi çıktığı tekrar ediyor mu? Bu soru, takımın psikolojik hedef bandını ölçer. Aynı lig ve sezon fazında bu refleks tekrar ediyorsa DNA sinyali güçlenir.
Takımın sezon içi konum baskısı var mı (küme düşme hattı, Avrupa potası, şampiyonluk baskısı) ve bu baskı segment davranışını değiştiriyor mu? Bu soru, takımın stres sınıfını belirler. Aynı takım farklı tabloda farklı oynar; bu bağlam yok sayılırsa sapma yanlış okunur.

Takımın cezalı oyuncu veya cezalı teknik ekip durumu var mı ve bu durum maç içi davranışı kaydırıyor mu? Bu soru, kadro bütünlüğü ve disiplin yükünü ölçer. Cezalı eksikliği çoğu zaman kart-tempo-kontrol profilini değiştirir.
Takımın Avrupa/kıtasal maç yoğunluğu var mı ve bu yoğunluk lig maçında segment davranışına yansıyor mu? Bu soru, paralel yükün yorgunluk ve rotasyon etkisini ölçer. Aynı takım “Avrupa sonrası lig” haftalarında farklı DNA gösterebilir.
Bu takımın maçlarını genelde tek bir oyuncu mu “kurtarıyor” ve sonuç belirleyici rol tekilde mi kümeleniyor? Bu soru, takımın yıldız bağımlılığını ölçer. Tek oyuncu bağımlılığı varsa takımın sapma profili o oyuncunun formuna kilitlenir.
Takımın kazanma davranışı kolektif mi yoksa bir-iki oyuncunun performansına mı bağımlı? Bu soru, takımın sürdürülebilirlik profilini çıkarır. Kolektif kazanım ile yıldız bağımlılığı aynı kader tetikleyicilerini üretmez.

Bu takımın skor üretimi belirli oyuncu üzerinden mi, yoksa sistem davranışı üzerinden mi tekrar ediyor? Bu soru, takımın “sistem takımı” mı “birey takımı” mı olduğunu raf içinde ayırır. Bu ayrım, haber ve transfer etkisini okumada belirleyicidir.
Bu takımın kritik maçlarda sonucu belirleyen oyuncuları değişiyor mu, yoksa aynı isimler tekrar ediyor mu? Bu soru, baskı anındaki rol dağılımını ölçer. Aynı isimler tekrar ediyorsa o oyuncuların kartı daha yüksek öncelikli raf nesnesi olur. 
Bunları ekledikten sonra senin dediğin şey tamamlanıyor: takımın DNA’sı sadece maç içi segment değil, maçlar arası sonuç hafızası + seri davranışı + yıldız bağımlılığı ile “kişilik” haline geliyor.

FAZ-33
MAÇ KADERİ TETİKLEYİCİLERİ SORULARI (FUTBOL) — GENİŞLETİLMİŞ KRİTİK SINIF
Bu bölümün amacı, maç içindeki olayları saymak değildir. Bu bölümün amacı, tetikleyici olayların takımın davranışını hangi döngüye soktuğunu ve maçın kaderini nasıl evirdiğini adreslemektir. Bu tetikleyiciler, seyirci baskısı ve iç/dış saha bağlamıyla birleştiğinde daha da sertleşebilir; bu yüzden tetikleyiciler yalnız saha içi değil, saha çevresi etkisiyle birlikte okunur.

İlk sarı kartın geldiği an hangi segmentte oldu ve takımın disiplin eşiğini değiştiriyor mu? Bu soru, maçın sertlik bandının nereden açıldığını ölçer. İlk kartın segmenti sabitlenmeden kart davranışı doğru okunamaz.
Takım ilk yarıda kart gördüğünde davranış nasıl değişiyor, ikinci yarıda kart gördüğünde nasıl değişiyor? Bu soru, kartın etkisini maçın evresine bağlar. Aynı kart farklı segmentte tamamen farklı kader etkisi üretir.
İlk karttan sonraki 10 dakikalık blokta faul yoğunluğu ve tempo bandı artıyor mu azalıyor mu? Bu soru, kart sonrası davranış döngüsünü ölçer. Kartın kendisi kadar kart sonrası “döngüye kilitlenme” kader belirleyicidir.
Kart sonrası takım “kabullenme” moduna mı giriyor yoksa “agresif karşılık” moduna mı giriyor? Bu soru, senin tarif ettiğin psikolojik döngüyü adresler. Bazı takımlar haksızlık algısıyla sertleşir, bazıları geri çekilir ve oyun çözülür.
Kartlar tek bir oyuncuda mı kümeleniyor yoksa takım geneline mi yayılıyor ve bu dağılım oyun planını değiştiriyor mu? Bu soru, disiplin riskinin lokal mi sistemik mi olduğunu ayırır. Lokal risk oyuncu kartına, sistemik risk takım DNA’sına yazılır.

Kart gören oyuncu “bir sonraki maç ceza sınırına” girince davranışını değiştiriyor mu? Bu soru, oyuncunun bilinçli risk yönetimini ölçer. Ceza sınırındaki oyuncu ya fazla temkinli olur ya da panikleyip daha çok hata yapar.
Ceza sınırındaki oyuncu, tribün baskısı altında daha mı fazla risk alıyor yoksa daha mı fazla geri çekiliyor? Bu soru, seyirci etkisinin oyuncu karar kalitesine yansımasını ölçer. Aynı oyuncu iç sahada farklı, deplasmanda farklı davranabilir.
kımın kritik oyuncusu ceza sınırına girince teknik direktör segment içinde onu erken çıkarıyor mu? Bu soru, kart tetikleyicisinin teknik direktör kararına nasıl dönüştüğünü ölçer. Bu hamle takımın kaderini değiştirebilir.
Kırmızı kart olduysa hangi türdendi (ikinci sarı veya direkt) ve kırmızı kart sonrası ilk 5 dakikada takım çöktü mü toparladı mı? Bu soru, kriz DNA’sını çıplak biçimde gösterir. İlk 5 dakika davranışı tekrar ediyorsa kader kalıbı oluşur.
Kırmızı kart sonrası takımın risk profili nasıl değişti (savunmaya çekilme, tempo öldürme, ani kontra, panik hücum)? Bu soru, toparlanma stratejisini ölçer. Aynı takımın tekrar eden kriz stratejisi raflarda görünmelidir.
Kırmızı kart iç sahada mı oldu deplasmanda mı ve taraftar etkisi davranışı sertleştirdi mi yumuşattı mı? Bu soru, iç/dış saha ile tetikleyici birleşimini ölçer. Aynı kırmızı kart farklı atmosferde farklı kader üretir.
Tribün baskısı kırmızı kart sonrası takımı “daha çok hırçınlık” döngüsüne mi sokuyor? Bu soru, “kart doğurur kart” zincirini yakalar. Bazı takımlar baskı altında kontrol kaybına girer.

Penaltı kararı geldi mi ve bu karar hangi segmentte geldi; karar sonrası psikolojik kırılma izi oluştu mu? Bu soru, penaltının skor dışında davranış değiştirici etkisini ölçer.
Penaltı verilmedi/verildi/iptal olduysa, takım “hakem yanlı” algısına girip daha fazla kart döngüsüne giriyor mu? Bu soru, senin özellikle vurguladığın “kabullenme mi agresyon mu” mekanizmasını adresler. Bu döngü sapmanın ana kaynağı olabilir.
Penaltı kararı veya iptali sonrası tribün baskısı oyuncu davranışını bozuyor mu? Bu soru, karar tetikleyicisinin seyirciyle birleştiğinde büyümesini ölçer. İç sahada bu etki genelde daha serttir.
VAR incelemesi oldu mu, hangi karar türüne bağlandı ve VAR müdahalesi maçın ritmini kırarak tempo bandını değiştirdi mi? Bu soru, VAR’ın ritim kırıcı etkisini ölçer.
VAR sonrası takım “kafa düşmesi” döngüsüne mi giriyor yoksa “öfke yükselişi” döngüsüne mi? Bu soru, VAR tetikleyicisinin davranış yönünü belirler. Aynı olay farklı takımlarda zıt kader üretir.

İptal edilen gol oldu mu ve iptal sonrası ilk 5 dakikada takım davranışı neye döndü? Bu soru, moral kırılması veya agresyon artışı gibi kader değiştirici profilleri yakalar.
İptal edilen gol sonrası tribün baskısı oyuncu karar kalitesini düşürüyor mu? Bu soru, “küçük tetikleyici + büyük basınç” birleşimini yakalar. Zor maçların çoğu bu birleşimde çözülür.
İlk gol hangi segmentte geldi ve ilk gol takımın davranışını deterministik değiştiriyor mu? Bu soru, skor eşiğinin psikolojik etkisini ölçer.
İlk gol sonrası takımın iç saha/deplasman davranışı ayrışıyor mu? Bu soru, “iç sahada kapanma”, “deplasmanda panik” gibi ayrımları yakalar.
Beraberlik golü hangi segmentte geldi ve beraberlikten sonraki ilk 10 dakikada kopma oluşuyor mu? Bu soru, denge kırılmasının tekrar eden yönünü ölçer.

Kopma golü sonrası takım “maçı bırakma” döngüsüne mi giriyor yoksa “son bir dalga” döngüsüne mi? Bu soru, takımın mücadele profili ve çöküş eşiğini adresler.
Sakatlık veya uzun duraklama oldu mu ve bu duraklama ritmi bozarak takımın davranışını değiştirdi mi? Bu soru, ritim bozan küçük olayların kader etkisini ölçer.
Sakatlık kritik oyuncuda mı oldu ve kritik oyuncu kaybı takımın skor üretimini çökertecek kadar bağımlı mı? Bu soru, takımın “tek oyuncu bağımlılığı” ile kader tetikleyicisini birleştirir.
Time-waste davranışı görüldü mü ve hakem buna nasıl tepki verdi; tribün bunu büyüttü mü? Bu soru, kapanış stratejisi + hakem bandı + seyirci basıncı üçlüsünü birlikte okur.

Maç kaderi tetikleyicileri iç saha/deplasman bağlamında sistematik tekrar ediyor mu? Bu soru, tetikleyici olayların aynı atmosfer sınıflarında daha sık üretilip üretilmediğini yakalar.
Bu tetikleyiciler odds tarafında hareketle aynı zaman bandında mı çakıştı yoksa bağımsız mı göründü? Bu soru, tetikleyicinin “piyasa davranışı” ile beraber mi yürüdüğünü ayırır.
Bu tetikleyiciler basın haber temalarıyla aynı hafta penceresinde mi çakıştı yoksa bağımsız mı? Bu soru, tetikleyicinin “haber kökenli mi” yoksa “saha kökenli mi” olduğuna dair sınıflamayı mümkün kılar.


ÖNEMLİ FUTBOLCU MAÇTAN ATILINCA TAKIMIN VERCEĞİ ( REAKSİYON ) SURULARI
Takımın en kritik oyuncusu kırmızı kartla oyundan atılınca takımın reaksiyonu ne oluyor (mücadeleyi bırakma, sertleşme, skor korumaya gömülme, kontra arama)? Bu soru, kartın “kader etkisini” oyuncu ağırlığıyla bağlar. Aynı kart, sıradan oyuncuda farklı, bel kemiğinde farklı sonuç üretir.

Kritik oyuncu oyundan atıldıktan sonraki ilk 10 dakikada takımın tempo ve disiplin bandı hangi yöne kayıyor? Bu soru, ilk şok tepkisini ölçer. Bazı takımlar bu 10 dakikada dağılır, bazıları tam tersine kitlenip direnç üretir.
Kritik oyuncu çıkınca o mevkiyi dolduran yedek oyuncunun kalite farkı takımın oyun planını deterministik değiştiriyor mu? Bu soru, “kâğıt üstü 10 kişi” ile “fiilen çöken takım” ayrımını verir. Oyuncu değişimi bir olay değil, kapasite kaymasıdır.
Kritik oyuncu kaybı sonrası takımın savunma çizgisi geri mi çekiliyor, yoksa kompakt kalıp agresif mi kalıyor? Bu soru, takımın kriz stratejisini sabitler. Geri yaslanma mı direnç mi, kaderi belirleyen ayrımdır.
Kritik oyuncu atıldıktan sonra teknik direktörün müdahalesi hangi segmentte geliyor ve müdahale doğru mu çalışıyor? Bu soru, teknik direktörün kriz yönetimi DNA’sını ölçer. Krizde doğru hamle yapabilen takımın sapma profili farklıdır.
Kondisyon ve tempo taşıma soruları. Bu takımın 90 dakika boyunca tempo taşıma kapasitesi var mı ve bu kapasite sezon fazına göre değişiyor mu? Bu soru, maçın son 20 dakikasında “çıkartamama” riskini adresler. Kondisyon düşüşü çoğu zaman sapmayı tetikler.

Takım yüksek tempolu maçlarda aynı tempoyu kaç dakika sürdürebiliyor ve kırılma dakikası tekrar ediyor mu? Bu soru, tempo dayanıklılığını ölçer. Kırılma dakikası tekrar ediyorsa takımın biyolojik sınırı gibi çalışır.
Takım 10 kişi kaldığında koşu kapasitesini koruyabiliyor mu yoksa tempo düşüşü hızlanıyor mu? Bu soru, eksik kalma krizinin fiziksel boyutunu ölçer. Bazı takımlar eksik kalınca bile daha çok koşar; bu ayrı bir DNA’dır.
Takım 9 kişi kaldığı ekstrem senaryolarda bile mücadele bandını koruyabiliyor mu? Bu soru, senin verdiğin gerçek örneği raf disiplinine çevirir. Bu tekrar eden bir özellikse kartların kader etkisi farklı okunur.
Takımın kondisyon düşüşü, maç segmentlerinde kart/faul artışıyla birlikte mi geliyor? Bu soru, yorgunluk–disiplin ilişkisini yakalar. Kondisyon düştüğünde kartlar artıyorsa kader tetikleyicisi büyür.
Takımın sezon hazırlığı (kamp/rotasyon/transfer) sonrası ilk haftalarda kondisyon profili farklı mı? Bu soru, sezon arası bağlam ile saha içi tempo dayanıklılığını birbirine bağlar. Kamp ve kadro değişimi tempo DNA’sını etkiler.

FUTBOLCU KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı futbolcuyu “iyi/kötü” diye sınıflamak değildir. Amaç, futbolcunun disiplin eğilimini, kritik an davranışını, kart riskini ve maçın kırılma anlarındaki rolünü tekrar eden bantlarla kartlaştırmaktır. Futbolcu kartı takım değişse bile kimliği taşır.
Futbolcu erken kart görme eğilimi taşıyor mu? Bu soru, takımın disiplin bandını bireysel seviyede etkileyen risk profilini çıkarır.
Futbolcu baskı yükselince hata ve faul eğilimi artıyor mu? Bu soru, crowd\\\_pressure\\\_response ile bireysel kırılmayı bağlar.

Futbolcu kırmızı kart riski taşıyor mu ve bu risk hangi segmentte artıyor? Bu soru, segment bazlı disiplin sapmasını ölçer.
Futbolcu kritik gol pozisyonlarında veya kritik faullerde tekrar eden rol taşıyor mu? Bu soru, maç kaderi tetikleyicilerinin bireysel izini yakalar.
Futbolcu VAR/penaltı kararlarından sonra mental düşüş yaşıyor mu? Bu soru, karar sonrası kırılma bandını bireysel düzeye indirir.
Futbolcu son 15 dakikada tempo taşıyabiliyor mu yoksa düşüyor mu? Bu soru, stamina\\\_profile ve kapanış dayanıklılığını bireysel kartta sabitler.

Futbolcu kritik oyuncu sınıfında mı ve kaybı replacement\\\_gap yaratıyor mu? Bu soru, takımın bel kemiği davranışını çıkarır.
Futbolcu hakem çizgisi sertleşince adaptasyon gösteriyor mu? Bu soru, referee\\\_profile ile bireysel disiplin davranışını bağlar.
Futbolcu maç içinde kontrol kaybı tetikleyen olaylarda sık görülüyor mu? Bu soru, control\\\_lost bandını bireysel düzeye taşır.
Futbolcu sakatlık sonrası performans düşüş bandı taşıyor mu? Bu soru, major\\\_injury tetikleyicisinin bireysel etkisini okur.

TAKIM KARTI — FAZ-1 TESLİMİ (Kart İskeleti + Etiket Duvarı + Soru Kütüphanesi)
team_ref: UNKNOWN_TEAM_REF
Kart Durumu: FAZ-1_SKELETON_ACTIVE
Kart Politikası: Tek team_ref / Sıfırlanmaz / Takım kartı takımda kalır / Reference ile bağlanır / Unmapped korunur
Üretim Notu: Bu teslim yalnız iskelet üretimidir. Reference_dictionary ve maç–basın–odds akışları Faz-2 doğrulama ve doldurma içindir. Veri yokken hiçbir alan boş bırakılmaz; unknown/none/inactive bantları deterministik kullanılır.

TAKIM KARTI — TAM PROFİL (FAZ-1 İSKELET)
Kimlik Rafı
team_ref: UNKNOWN_TEAM_REF,club_name: unknown,short_name_alias: unknown,name_variants: none,founded_year: unknown,city_ref: unknown,country_ref: unknown,league_ref: unknown,stadium_ref: unknown,stadium_capacity_band: unknownclub_model_band: unknown
identity_status: unknown
Tarihçe ve Statü Rafı
era_policy: append_only / eras_are_non_overwriting,era_blocks: none,historical_identity_themes: unknown,rise_fall_turning_points: unknown,dominant_periods: none
Başarı Rafı (Trophy Shelf)
trophies: none,records: none,Kural: trophy_type + season_tag + competition_ref ile tutulur; Faz-1’de veri yoksa none.
Hedef Sapması Rafı (Target Miss)
season_targets: none,target_miss_records: none,Kural: hedef sapması “övgü/yerme” diliyle yazılmaz; yalnız hedef ve sapma bandı tutulur.
Kadro ve Transfer DNA Rafı
academy_output_band: unknown,star_transfer_tendency: unknown,fighter_profile_preference: unknown,sell_to_grow_model_band: unknown,loan_dependency_band: unknown,age_profile_trend_band: unknown,scouting_region_bias: unknown
Oyun DNA (Takım İmzası)
press_approach: unknown,block_preference: unknown,transition_priority: unknown,set_play_patience: unknown,wing_central_balance: unknown,defensive_line_risk: unknown,set_piece_strength_band: unknown,set_piece_weakness_band: unknown,tempo_band: unknown
flexibility_band: unknown,creation_source_band: unknown,press_resistance_band: unknown,sterile_possession_band: unknown,build_up_risk_band: unknown

Maç İçi Davranış DNA Rafı: match_start_behavior_band: unknown,concede_first_response_band: unknown,score_first_behavior_band: unknown,late_game_behavior_band: unknown,comeback_capacity_band: unknown,score_protection_discipline_band: unknown,risk_increase_trigger_band: unknown ,panic_under_pressure_band: unknown
Seri ve Momentum Rafı: streak_building_ability_band: unknown,win_streak_tendency_band: unknown,loss_streak_risk_band: unknown,draw_streak_tendency_band: unknown,post_loss_response_band: unknown,post_win_complacency_risk_band: unknown,post_draw_response_band: unknown
Kural: Seri davranışı tek maçla hüküm üretmez; trend/patern yoksa unknown kalır.
İç Saha / Deplasman Rafı: home_strength_band: unknown,away_resilience_band: unknown,home_crowd_effect_band: unknown,away_crowd_effect_band: unknown,travel_pressure_band: unknown
Tribün ve Baskı Yönetimi Rafı: crowd_pressure_handling: unknown,derby_pressure_band: unknown,high_target_pressure_band: unknown,late_game_pressure_band: unknown,decision_risk_under_pressure_band: unknown
Disiplin ve Kart Profili Rafı: discipline_profile: unknown,yellow_card_tendency: unknown,red_card_tendency: unknown,dissent_protest_band: unknown,aggression_band: unknown,foul_type_clusters: unknown
Sakatlık ve Yük Yönetimi Rafı,injury_cluster_band: unknown,load_collapse_band: unknown,rotation_resilience_band: unknown,return_from_injury_impact_band: unknown

Koç Etkisi Haritası Rafı: coach_dependence_band: unknown,new_coach_bounce_band: unknown,coach_change_disruption_band: unknown,dna_persistence_after_coach_band: unknown,Yıldız Oyuncu Bağımlılığı Rafı
star_dependency_band: unknown,leader_loss_impact_band: unknown,youth_carry_capacity_band: unknown,Hakem Etkileşim Profili Rafı,referee_tension_pattern: unknown,card_risk_under_ref_pressure_band: unknown,penalty_incidence_band: unknown,var_tension_band: unknown
Basın ve Kamu Algısı Rafı,press_themes: unknown,strong_signal_policy: multi_source_required,signal_strength: weak_signal,crisis_communication_style: unknown,expectation_inflation_band: unknown,fan_protest_pressure_band: unknown,narrative_gap_band: unknown
Kural: Basın verisi tek başına hüküm kurmaz; eksik event basınla tamamlanmaz.

Etik ve Risk Rafı:,integrity_risk_profile: unknown,financial_crisis_band: unknown,match_fixing_allegation_history: none,disciplinary_case_history: none,allegation_strength: none,investigation_status_band: unknown,Kural: Yargı kurulmaz; yalnız doğrulanmış dosya/kayıt varsa işlenir. Belirsiz iddia weak_signal bandında tutulur.
Odds / Market Zaman Hizası Rafı:,market_alignment_status: inactive_market,time_alignment_notes: unknown,Kural: Bu bölüm tahmin üretmez; yalnız hizalama ve pasiflik bandı taşır.
Bağlantılar (informed_by),informed_by:,match_cards: none,match_events: none,press_rack: none,player_cards: none,coach_cards: none,referee_cards: none,odds_market_timeline: none,Kural: Bağlantı serbest metinle kurulmaz; Faz-2’de reference_dictionary üzerinden bağlanır.
Data Quality:,data_quality_badge: low,coverage_map:,identity: unknown,history_status: unknowntrophies: none,targets: none,squad_transfer_dna: unknownteam_dna: unknown,in_game_behavior: unknown,streak_momentum: unknown,home_away: unknown,pressure_crowd: unknown,discipline: unknown,injury_load: unknown,coach_effect: unknown,star_dependency: unknown,press: weak_signal,ethics_risk: none,market_alignment: inactive_market,informed_by_links: none
TAKIM ETİKET DUVARI (FAZ-1 DETERMINİSTİK SÖZLÜK ALANLARI)
Bantlar ve Durum Etiketleri,unknown: veri yok / doğrulanmadı,none: alan geçerli ama içerik yok (kayıt yok),inactive: kaynak var ama şu an aktif değil,inactive_market: market verisi yok veya pasif,unmapped: reference_dictionary eşleşmesi yok, zorla eşleme yapılmadı
weak_signal: tekil veya zayıf kaynak sinyali,strong_signal: yalnız çoklu kaynak teyidi ile açılır,active_unknown: segment var ama içeriği doğrulanmadı
Kimlik Etiketleri: identity_status: unknown | verified club_model_band: unknown | member_owned | private_owned | mixed stadium_capacity_band: unknown | small | medium | large
Hedef ve Başarı EtiketleriÇ: trophy_band: none | exists trophy_scope: domestic_league | domestic_cup | super_cup | continental | othertarget_type: title | europe_qualification | relegation_avoid | points_target | other ,deviation_band: unknown | low | medium | high
Kadro ve Transfer Etiketleri: academy_output_band: unknown | low | medium | high ,star_transfer_tendency: unknown | low | medium | high ,fighter_profile_preference: unknown | low | medium | high ,sell_to_grow_model_band: unknown | low | medium | high
loan_dependency_band: unknown | low | medium | high .age_profile_trend_band: unknown | youth_focus | balanced | veteran_focus | unknown


FAZ-16
Takım Oyun DNA Etiketleri:
press_approach: unknown | high_press | mid_press | low_block,block_preference: unknown | high_line | mid_block | low_block,transition_priority: unknown | transition_first | balanced | possession_first,set_play_patience: unknown | low_patience | balanced | high_patience
wing_central_balance: unknown | wing_focus | balanced | central_focus,defensive_line_risk: unknown | low_risk | balanced | high_risk,set_piece_strength_band: unknown | low | medium | high,set_piece_weakness_band: unknown | low | medium | high
tempo_band: unknown | low | medium | high,flexibility_band: unknown | low | medium | high,creation_source_band: unknown | individual_quality | system | mixed | unknown,press_resistance_band: unknown | low | medium | high,sterile_possession_band: unknown | low | medium | high,build_up_risk_band: unknown | low | medium | high
Maç İçi Davranış Etiketleri:
match_start_behavior_band: unknown | low | medium | high,concede_first_response_band: unknown | collapse | unstable | stable | comeback,score_first_behavior_band: unknown | protect | control | push_more | unstable,late_game_behavior_band: unknown | stable | volatile | aggressive | passive | unknown,comeback_capacity_band: unknown | low | medium | high,score_protection_discipline_band: unknown | low | medium | high,risk_increase_trigger_band: unknown | early | mid | late | unknown,panic_under_pressure_band: unknown | low | medium | high
Seri ve Momentum Etiketleri:
streak_building_ability_band: unknown | low | medium | high,win_streak_tendency_band: unknown | low | medium | high,loss_streak_risk_band: unknown | low | medium | high,draw_streak_tendency_band: unknown | low | medium | high,post_loss_response_band: unknown | collapse | unstable | stable | rebound,post_win_complacency_risk_band: unknown | low | medium | high,post_draw_response_band: unknown | collapse | unstable | stable | rebound
İç Saha / Deplasman Etiketleri
home_strength_band: unknown | low | medium | high,away_resilience_band: unknown | low | medium | hightravel_pressure_band: unknown | low | medium | high
Baskı Etiketleri
crowd_pressure_band: unknown | low | medium | high,late_game_pressure_band: unknown | low | medium | high,pressure_decision_risk_band: unknown | low | medium | high
Disiplin Etiketleri
yellow_card_tendency: unknown | low | medium | high,red_card_tendency: unknown | low | medium | high,aggression_band: unknown | low | medium | high,dissent_protest_band: unknown | low | medium | high
Sakatlık ve Yük Etiketleri
load_collapse_band: unknown | low | medium | high,rotation_resilience_band: unknown | low | medium | high
Basın Etiketleri
press_theme_status: unknown | tracked,signal_strength: weak_signal | strong_signal
Etik ve Risk Etiketleri
allegation_strength: none | weak_signal | strong_signal,investigation_status_band: none | ongoing | closed_no_action | sanctioned | unknown,financial_crisis_band: unknown | low | medium | high
Market Etiketleri
market_alignment_status: inactive_market | active_aligned | active_misaligned,market_data_strength: none | weak | strong
Reference Bağ Etiketleri
team_ref_status: unmapped | mapped,league_ref_status: unmapped | mapped,country_ref_status: unmapped | mapped


FAZ-35  TAKIM DNA KARTI SORULARI (FUTBOL) — PROFİL, REFLEKS, BAĞIMLILIK

Bu bölümün amacı takımın “iyi/kötü” olup olmadığını söylemek değildir. Amaç, takımın tekrar eden reflekslerini, stres altında verdiği tepkileri, seri davranışını, iç saha/deplasman karakterini ve bağımlılıklarını deterministik biçimde kartlaştırmaktır. Bu kart, maç tekilliğini aşan bir raf nesnesidir ve beş yıllık hafızanın ana omurgasıdır.
Takımın temel oyun temposu hangi bantta ve bu tempo sezon fazına göre değişiyor mu? Bu soru, takımın normal hızını sabitler. Tempo değişimi tekrar ediyorsa sezon fazı etkisi kartın parçası olur.
Takımın maç başlangıç refleksi nedir (ilk 15) ve bu refleks tekrar ediyor mu? Bu soru, “erken baskı/erken çözülme” profilini çıkarır. Tekrar eden refleks DNA sinyalidir.
Takımın devre geçiş refleksi nedir ve ikinci yarıya çıkış davranışı hangi bantta? Bu soru, teknik direktör etkisinin en net görüldüğü eşiği ölçer. Devre çıkışı tekrar eden bir kimliktir.

Takımın maç kapatma refleksi nedir (son 15 ve uzatma) ve skor durumuna göre değişiyor mu? Bu soru, takımın stres altında kapanış stratejisini sabitler. Önde/geride farklı davranışlar ayrı ayrı okunur.
Takımın seri davranışı var mı (galibiyet/beraberlik/mağlubiyet serileri) ve seri içinde tempo-disiplin değişiyor mu? Bu soru, takımın dalga yapısını ölçer. Seri davranışı varsa kartlar ve risk profili seri içinde farklılaşabilir.
Takımın bir önceki maç sonucu bir sonraki haftayı etkiliyor mu? Bu soru, takımın sonuç hafızasını ölçer. Bu hafıza varsa maçlar arası okuma güçlenir.
Takımın iç saha davranışı ile deplasman davranışı deterministik ayrışıyor mu? Bu soru, atmosfer etkisini DNA’ya bağlar. Aynı takımın iç/dış saha profili farklı kartlar üretir.
Takımın tribün baskısına dayanma profili nedir ve baskı altında disiplin bandı bozuluyor mu? Bu soru, seyirci etkisini doğrudan DNA’ya yazar. Baskı altında kart artışı tekrar ediyorsa sinyal güçlenir.
Takımın kritik oyuncu bağımlılığı var mı ve skor üretimi tekilde mi kümeleniyor? Bu soru, yıldız bağımlılığını ölçer. Bağımlılık varsa takım sapma profili oyuncu kartına kilitlenir.

Takımın kritik oyuncu kaybı sonrası reaksiyonu nedir (mücadeleyi bırakma, sertleşme, geriye yaslanma)? Bu soru, bel kemiği kırılınca takımın kriz stratejisini sabitler. Bu DNA kritik sınıftır.
Takımın kart tetikleyicilerine tepkisi nedir (kabullenme döngüsü mü agresyon döngüsü mü)? Bu soru, kartların kader etkisini takım karakterine bağlar. Kartın anlamı takım refleksiyle ölçülür.
Takımın kırmızı kart sonrası kriz yönetimi profili nedir ve ilk 10 dakikada çöker mi toparlar mı? Bu soru, eksik kalma dayanıklılığını ölçer. Bazı takımlar 10 kişi kalınca bile direnç üretir.
Takımın kondisyon ve tempo taşıma kapasitesi nedir ve kırılma dakikası tekrar ediyor mu? Bu soru, son 20 dakika çöküş riskini ölçer. Kırılma dakikası tekrar ediyorsa kartın etkisi de büyür.
Takımın yüksek tempolu rakip karşısında tempo koruma süresi nedir? Bu soru, maç başlamadan “tempo yetmez” riskini işaretleyebilir. Bu bir hüküm değil, profil işaretidir.
Takımın disiplin profili nedir (kart kümelenmesi, faul yoğunluğu) ve hangi segmentlerde artıyor? Bu soru, disiplinin maç geneline değil, segmentlere dağılımını sabitler. Segment bazlı artış kader tetikleyicisidir.

Takımın VAR/penaltı/iptal gol gibi karar tetikleyicilerine psikolojik tepkisi nedir? Bu soru, hakem kararlarının takım davranışını nasıl kaydırdığını ölçer. Bazı takımlar bu tetikleyicilerde çözülür.
Takımın risk alma profili nedir (öndeyken kapanma, gerideyken panik hücum, beraberlikte tutma)? Bu soru, skor bağlamındaki davranış stratejisini sabitler. Aynı skor durumunda tekrar eden davranış DNA’dır.
Takımın sakatlık ve kadro eksikliği altında performans stabilitesi nedir? Bu soru, kadro derinliğini ölçer. Stabilite yoksa sapma ihtimali artar.
Takımın teknik direktör değişimi sonrası DNA kırılması var mı? Bu soru, takım kartının hangi tarihte değiştiğini sabitler. Teknik direktör değişimi kart revizyonu gerektirebilir.
Takımın kupa/Avrupa paralel yükü altında lig davranışı kayıyor mu? Bu soru, organizasyon yükünün lig performansına etkisini ölçer. Paralel yük varsa segment davranışları kayabilir.
Takımın “normal bant” profili beş yıl içinde stabil mi, yoksa dönemsel karakter değişimi var mı? Bu soru, takım DNA’sının sabit mi evrimli mi olduğunu ölçer. Dönemsel değişim varsa kart revizyonu yapılır.

FAZ-17
TAKIM SORU KÜTÜPHANESİ (FAZ-1 GENİŞ TARAMA SETİ — GENİŞLETİLMİŞ TAM)
Bu takımın kimliği “takım_ref” altında tekil mi, isim varyantları ve tarihsel yeniden adlandırmalar var mı?
Bu takımın şehir ve bölge kimliği oyun tarzı ve taraftar davranışıyla ilişen bir iz taşıyor mu?
Kulübün kuruluşundan bugüne “kimlik kırılması” yaşadığı dönemler var mı; era_tag nasıl ayrılmalı?
Kulübün sahiplik modeli değişti mi; değiştiyse takım DNA’sı hangi katmanlarda farklılaştı?
Yönetim değişimi sonrası sportif hedef bandı nasıl kaydı; hedef yükselmesi mi küçülmesi mi baskın?
Kulübün mali istikrarı performans dalgalanmasına eşlik ediyor mu; finansal risk bandı açılmalı mı?

Kulübün taraftar profili “yüksek baskı” mı “sakin destek” mi; crowd_pressure_band nasıl atanmalı?
İç saha atmosferi hakem etkileşimini tetikliyor mu; kart ve penaltı paternlerinde sapma var mı?
Deplasman performansı yalnız saha içi mi, seyahat ve lojistik gibi dış faktörlerle de kırılıyor mu?
Derbi türü maçlarda disiplin kırılması artıyor mu; agresyon bandı yükseliyor mu?
Yüksek hedef baskısında takımın oyun planı daralıyor mu; karar hızı düşürür mü?
Skor üstünlüğü alınca takım “kapanma” mı “öldürme” mi eğiliminde; son 15 dakika paterni ne?

Geriye düştüğünde takımın reaksiyonu planlı mı panik mi; risk artışı hangi dakikada tetikleniyor?
İlk golü yiyince oyunun şekli değişiyor mu; erken gol kırılması var mı?
İlk golü atınca topa sahip olma ve tempo değişiyor mu; kontrol modu devreye giriyor mu?
0-0 kilit maçlarda takım sabırlı mı, erken risk mi alıyor; set oyun sabrı bandı nasıl?
Öne geçtiğinde faul ve kart davranışı artıyor mu; zaman geçirme kontrol paterni var mı?
Hakeme itiraz yoğunluğu belirli senaryolarda mı patlıyor; protest_intensity_band nasıl ölçülmeli?

Oyunun “sertleştiği” maçlarda takım avantaj sağlayabiliyor mu yoksa dağılıyor mu?
Takımın duran top gücü, oyun içi üretimin düştüğü maçlarda telafi edici rol oynuyor mu?
Duran top savunması zayıf mı; tekrar eden gol tipleri var mı?
Takımın gol yeme şekli tekrar ediyor mu; cutback, ters top, arkaya koşu gibi kalıp var mı?
Takımın gol bulma şekli tekrar ediyor mu; kanat ortası, geçiş, merkez kombinasyon gibi kalıp var mı?
Takımın pres yaklaşımı maçın hangi bandında yükseliyor; ilk 15 mi, ikinci yarı başı mı?

Pres kırıldığında takım savunma şekli bozuluyor mu; defensive_line_risk artıyor mu?
Savunma çizgisi riski bazı koçlarda mı artıyor, bazı kadrolarda mı; era_tag ayrımı gerekiyor mu?
Orta saha yoğunluğu mu, kanat genişliği mi baskın; oyun DNA’nın çekirdeği nedir?
Topa sahip olma artınca üretim artıyor mu yoksa kısırlaşıyor mu; possession verim bandı açılmalı mı?
Geçiş oyununda “ilk pas” kalitesi takımın kaderini belirliyor mu; transition_start_quality bandı gerekir mi?
Kontra yerken yapısal zaaf var mı; counter_stop disiplin bandı açılmalı mı?

Kontra çıkarırken bitiricilik sorunu var mı; final third verim bandı gerekir mi?
Takımın kaleci oyun kurulum rolü DNA’nın parçası mı; build_up_through_gk bandı açılmalı mı?
Stoper profili oyunu öne taşıyor mu yoksa geride tutuyor mu; build_up_risk bandı gerekir mi?
Bek bindirmesi takımın ana silahı mı; bek kullanım paterni sabit mi?
Kanat oyuncusu profili “çizgiye basan” mı “içe kat eden” mi; rol sürekliliği var mı?
Santrfor profili “hedef” mi “koşucu” mu; oyun planı buna göre mi şekilleniyor?

Takımın kilit oyuncu bağımlılığı var mı; yokluğunda oyun çöküyor mu?
Kaptan/leader oyuncu kaybı sonrası disiplin ve oyun düzeni bozuluyor mu?
Genç oyuncu oynatma cesareti var mı; baskı maçlarında gençleri kesiyor mu?
Altyapıdan çıkan oyunculara dakikalı yatırım yapılıyor mu; academy_promotion bandı nasıl atanmalı?
Transfer dönemlerinde takım “yıldız” mı “mücadeleci” mi “sistem oyuncusu” mu arıyor?
Transfer stratejisi “satın al-parlat-sat” mı “tut ve büyüt” mü; satış kulübü bandı açılmalı mı?

Kiralık oyuncu kullanımı yüksek mi; loan_dependency bandı gerekir mi?
Kadro yaş ortalaması dönemsel dalgalanıyor mu; gençleşme/yaşlanma trendi var mı?
Yoğun fikstürde performans çöküşü var mı; load_collapse_band açılmalı mı?
Sakatlık dalgası takımın oyun DNA’sını bozar mı; rotasyon dayanıklılığı var mı?
Aynı sezonda çok sakatlık yaşanıyorsa hazırlık ve yük yönetimi sorununa işaret eder mi?
Takımın deplasman seyahatlerinde performans kırılması var mı; travel_pressure_band gerekir mi?

Hakem profiline göre performans sapması var mı; belirli hakem tiplerinde kart/penaltı artıyor mu?
VAR kararları takımın oyun disiplinini etkiliyor mu; VAR sonrası gerilim artıyor mu?
Tartışmalı karar sonrası takımın oyunu dağılıyor mu yoksa daha mı sertleşiyor?
Basında takım hakkında tekrar eden kriz temaları var mı; yönetim dili tutarlı mı?
Basın üzerinden “hoca gider mi” döngüleri sık mı; istikrar riski bandı gerekir mi?
Taraftarın protestosu ve yönetim baskısı sezon içi performansı tetikliyor mu?

Sosyal medya krizleri saha performansını etkiliyor mu; weak_signal olarak bile tutulmalı mı?
Kulübün etik/uyumluluk risk geçmişi var mı; resmi yaptırım oldu mu?
Şike/bahis iddiası gibi ağır başlıklar geçmişte geçti mi; allegation_strength nasıl bandlanmalı?
Rakip takımlara karşı “psikolojik kompleks” izleri var mı; derby_pressure ile ayrıştırılmalı mı?
Belirli stadyumlarda performans düşüyor mu; venue_specific_band gerekir mi?
Hakemle gerilim yaşayan maçlarda disiplin kırılması ile puan kaybı ilişkili mi?

Maçın son 10 dakikasında gol atma/yenme oranı sapıyor mu; late_goal_band gerekir mi?
Kırmızı kart gördüğünde takım toparlıyor mu dağılıyor mu; red_card_response_band gerekir mi?
Kırmızı kart rakibe çıktığında üstünlüğü doğru kullanabiliyor mu; advantage_use_band gerekir mi?
Penaltı kullandığında baskıyı yönetebiliyor mu; penalty_execution_band gerekir mi?
Penaltı aleyhine verildiğinde oyun ve disiplin bozuluyor mu; penalty_concession_reaction_band gerekir mi?
Avrupa/uluslararası maçlar sonrası lig maçında performans düşüyor mu; schedule_fatigue_band gerekir mi?

Kupa maçlarında rotasyon yapınca lig performansı etkileniyor mu; competition_priority_band gerekir mi?
Koç değişimleri sonrası takım kısa vadede sıçrıyor mu, düşüyor mu; new_coach_bounce_band gerekir mi?
Koç gittikten sonra takım DNA çekirdeği devam ediyor mu; coach_dependence_band nasıl atanmalı?
Aynı koç altında bile kadro değişince oyun DNA’sı bozuluyor mu; squad_dependency_band gerekir mi?
Takımın “taktik esnekliği” düşük mü; tek plana sıkışıyor mu; flexibility_band gerekir mi?
Skor üretiminde “bireysel kalite” mi “sistem” mi baskın; creation_source_band gerekir mi?

Gol katkısı birkaç oyuncuda mı toplanıyor; concentration_risk_band açılmalı mı?
Takımın ceza sahası içine girişleri var ama bitiremiyor mu; finishing_efficiency_band gerekir mi?
Takımın şut kalitesi düşük mü; shot_quality_band takım seviyesinde tutulmalı mı?
Takım savunmada basit hatalarla mı gol yiyor; error_prone_band gerekir mi?
Takımın pas isabeti yüksek ama ilerleme düşük mü; sterile_possession_band gerekir mi?
Rakip baskısı altında çıkış zorlanıyor mu; press_resistance_band gerekir mi?

Takımın önde baskıya karşı uzun topa kaçma eğilimi var mı; long_ball_escape_band gerekir mi?
Aynı rakibe karşı farklı sezonlarda aynı senaryo tekrar ediyor mu; opponent_repeat_pattern_band gerekir mi?
Takımın “maç önü basın dili” ile “maç içi gerçeklik” çelişiyor mu; narrative_gap_band gerekir mi?
Takımın şampiyonluk yarışında son düzlüğe girince performansı düşüyor mu; title_run_in_pressure_band gerekir mi?
Düşme hattı baskısında disiplin ve oyun aklı nasıl değişiyor; survival_mode_band gerekir mi?
Takımın galibiyet serisi yakalama eğilimi var mı; win_streak_tendency_band nasıl ölçülmeli?

Takımın mağlubiyet serisine girme riski var mı; loss_streak_risk_band nasıl bandlanmalı?
Beraberlik serisi yaşama eğilimi var mı; draw_streak_tendency_band neyi gösterir?
Üst üste mağlubiyet sonrası toparlanma mı çöküş mü baskın; post_loss_response_band nasıl atanmalı?
Üst üste galibiyet sonrası rehavet riski var mı; post_win_complacency_risk_band nasıl ölçülmeli?
Beraberlik sonrası reaksiyon rebound mu collapse mı; post_draw_response_band nasıl işaretlenmeli?
Genel seri üretme kapasitesi düşük mü yüksek mi; streak_building_ability_band nasıl atanmalı?


FUTBOL ETİKET KATALOĞU (KÜTÜPHANE SÖZLÜĞÜ) — ÇEKİRDEK DUVAR + MAÇ + TAKIM DNA
Bu katalog, soru cümlelerinin etiket olarak yapıştırılması için değil; soruların cevaplarını deterministik biçimde raflara yazdırmak için vardır. Bu katalog dışı etiket üretilemez. Etiketler serbest metin değildir; sabit ad ve sabit değer bantlarıyla çalışır.

KONTEKST / DUVAR ETİKETLERİ (ZORUNLU)
timestamp\\\_utc ,country\\\_ref ,league\\\_ref ,season\\\_id ,season\\\_phase ,competition\\\_type ,cup\\\_flag ,team\\\_ref ,season\\\_phase yalnız şu değerleri alır: pre\\\_season, season\\\_start, season\\\_mid, season\\\_end, off\\\_season ,competition\\\_type yalnız şu değerleri alır: league, cup, continental, national\\\_team ,cup\\\_flag yalnız şu değerleri alır: true, false

MAÇ ADRESİ VE MAÇ BAĞLAM ETİKETLERİ (ZORUNLU)
match\\\_ref ,kickoff\\\_time\\\_utc ,home\\\_team\\\_ref ,away\\\_team\\\_ref ,venue\\\_type ,is\\\_home\\\_team\\\_context ,referee\\\_ref ,venue\\\_type yalnız şu değerleri alır: home, away, neutral ,is\\\_home\\\_team\\\_context yalnız şu değerleri alır: true, false

MAÇ SEGMENT ETİKETLERİ (ZORUNLU)
segment\\\_first\\\_15 ,segment\\\_16\\\_30 ,segment\\\_31\\\_45 ,segment\\\_half\\\_time\\\_transition ,segment\\\_46\\\_60 ,segment\\\_61\\\_75 ,segment\\\_last\\\_15 ,segment\\\_last\\\_5\\\_plus\\\_added
Her segment alanı yalnız şu değerleri alır: normal\\\_band, tempo\\\_up, tempo\\\_down, control\\\_lost, control\\\_gained, risk\\\_up, risk\\\_down
 
TEMPO / KONTROL / DİSİPLİN BANT ETİKETLERİ (ZORUNLU)
tempo\\\_band\\\_overall ,tempo\\\_breakpoint\\\_minute\\\_bucket ,discipline\\\_band\\\_overall ,discipline\\\_cluster\\\_bucket ,control\\\_band\\\_overall ,tempo\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high ,tempo\\\_breakpoint\\\_minute\\\_bucket yalnız şu değerleri alır: none, 0\\\_15, 16\\\_30, 31\\\_45, 46\\\_60, 61\\\_75, 76\\\_90 ,discipline\\\_band\\\_overall yalnız şu değerleri alır: calm, normal, aggressive ,discipline\\\_cluster\\\_bucket yalnız şu değerleri alır: none, 0\\\_15, 16\\\_30, 31\\\_45, 46\\\_60, 61\\\_75, 76\\\_90 ,control\\\_band\\\_overall yalnız şu değerleri alır: stable, unstable

KADER TETİKLEYİCİ ETİKETLERİ (ZORUNLU)
trigger\\\_first\\\_yellow ,trigger\\\_red\\\_card ,trigger\\\_var\\\_review ,trigger\\\_penalty\\\_event ,trigger\\\_disallowed\\\_goal ,trigger\\\_major\\\_injury ,trigger\\\_long\\\_stoppage ,trigger\\\_time\\\_waste Bu alanlar yalnız şu değerleri alır: none, occurred ,occurred ise ayrıca trigger\\\_minute\\\_bucket zorunludur.trigger\\\_minute\\\_bucket yalnız şu değerleri alır: 0\\\_15, 16\\\_30, 31\\\_45, 46\\\_60, 61\\\_75, 76\\\_90, added\\\_time

KRİTİK OYUNCU / BEL KEMİĞİ ETKİSİ (ZORUNLU)
critical\\\_player\\\_incident ,critical\\\_player\\\_role\\\_weight ,critical\\\_player\\\_loss\\\_reaction ,critical\\\_player\\\_incident yalnız şu değerleri alır: none, yellow\\\_risk, red\\\_sent\\\_off, injury\\\_out, substituted ,critical\\\_player\\\_role\\\_weight yalnız şu değerleri alır: normal, high ,critical\\\_player\\\_loss\\\_reaction yalnız şu değerleri alır: no\\\_shift, fight\\\_harder, collapse, deep\\\_defend, chaos

KONDİSYON / TEMPO TAŞIMA ETİKETLERİ (ZORUNLU)
stamina\\\_profile ,stamina\\\_breakdown\\\_bucket ,ten\\\_men\\\_resilience
stamina\\\_profile yalnız şu değerleri alır: strong, normal, weak ,stamina\\\_breakdown\\\_bucket yalnız şu değerleri alır: none, 46\\\_60, 61\\\_75, 76\\\_90 ,ten\\\_men\\\_resilience yalnız şu değerleri alır: unknown, stable, unstable, strong\\\_resist

İÇ SAHA / DEPLASMAN / TRİBÜN BASINCI (ZORUNLU)
home\\\_away\\\_behavior\\\_shift ,crowd\\\_pressure\\\_band ,crowd\\\_pressure\\\_response
home\\\_away\\\_behavior\\\_shift yalnız şu değerleri alır: none, home\\\_stronger, away\\\_stronger, unstable ,crowd\\\_pressure\\\_band yalnız şu değerleri alır: low, medium, high ,crowd\\\_pressure\\\_response yalnız şu değerleri alır: no\\\_effect, discipline\\\_drop, tempo\\\_spike, panic, fight\\\_harder

FORM / SERİ DAVRANIŞI (ZORUNLU)
previous\\\_match\\\_result ,streak\\\_type ,streak\\\_length\\\_bucket ,*next\\\_week\\\_effect\\\_band
previous\\\_match\\\_result yalnız şu değerleri alır: win, draw, loss, unknown ,streak\\\_type yalnız şu değerleri alır: none, win\\\_streak, draw\\\_streak, loss\\\_streak, mixed ,streak\\\_length\\\_bucket yalnız şu değerleri alır: 0, 1\\\_2, 3\\\_4, 5\\\_plus ,next\\\_week\\\_effect\\\_band yalnız şu değerleri alır: none, positive, negative, unstable--

FUTBOL HAKEM KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı hakemi “iyi/kötü” diye sınıflamak değildir. Amaç, hakemin maçın disiplin eşiğini, VAR/penaltı kritik karar davranışını ve maçın kırılma anlarındaki rolünü tekrar eden bantlarla okumaktır. Suçlama dili yoktur; yalnız davranış izi çıkarılır.
Hakemin ilk kart eşiği erken mi oluşuyor, geç mi oluşuyor? Bu soru, maçın disiplin bandını erken sabitler. Erken eşik maçın tüm ritmini değiştirir.
Hakem kart dağıtımında dengeli mi yoksa tek taraflı kümelenme görüyor muyuz? Bu soru hüküm üretmez; yalnız dağılım bandını çıkarır. Tekrarlı bir yığılma varsa işaretlenir.

Hakem kritik faul kararlarını hangi bölgelerde daha sık veriyor? Bu soru, tehlikeli bölge faul bantlarını ve duran top riskini okumayı kolaylaştırır.
Hakem VAR müdahalesi gerektiren pozisyonlarda çizgiyi nasıl yönetiyor? Bu soru, maçın kader tetikleyicilerinden biri olan VAR bandını çıkarır.
Penaltı pozisyonlarında hakemin karar bandı nedir? Bu soru, penaltı kararlarının maç akışı üzerindeki kırılma etkisini okumayı sağlar.
İptal edilen gol kararları maçın momentumunu nasıl kırıyor? Bu soru, iptal gol kırığı etkisini ve takım reaksiyon profilini bağlamlar.

Hakem kırmızı kart eşiğinde erken mi, geç mi düdük çalıyor? Bu soru, maçın sertlik bandı ve kırmızı kart tetikleyici ihtimalini sabitler.
Hakem teknik alan olaylarında toleransı düşük mü yüksek mi? Bu soru, teknik direktör kartı ve disiplin sapması bandıyla kesişir.
Hakem maçın son 15 dakikasında düdük yoğunluğunu artırıyor mu azaltıyor mu? Bu soru, kapanış bandının “oyuncu davranışı mı yoksa hakem ritmi mi” olduğunu ayırır.
Hakem kararlarıyla maçın control\\\_lost bandı tetikleniyor mu? Bu soru, hakem davranışıyla ritim kırılması arasındaki tekrar ilişkisini yakalar.

FUTBOL HAKEM KARTI — ETİKET KATALOĞU
timestamp\\\_utc ,referee\\\_ref ,country\\\_ref ,league\\\_ref ,season\\\_id ,competition\\\_type ,season\\\_phase
referee\\\_first\\\_card\\\_threshold\\\_band ,referee\\\_card\\\_distribution\\\_balance\\\_band ,referee\\\_danger\\\_zone\\\_foul\\\_band ,referee\\\_var\\\_intervention\\\_band ,referee\\\_penalty\\\_decision\\\_band ,referee\\\_disallowed\\\_goal\\\_band ,referee\\\_red\\\_card\\\_threshold\\\_band ,referee\\\_technical\\\_area\\\_tolerance\\\_band ,referee\\\_closing\\\_whistle\\\_band ,referee\\\_control\\\_risk\\\_band

referee\\\_first\\\_card\\\_threshold\\\_band yalnız şu değerleri alır: early, normal, late ,referee\\\_card\\\_distribution\\\_balance\\\_band yalnız şu değerleri alır: balanced, mild\\\_skew, heavy\\\_skew ,referee\\\_danger\\\_zone\\\_foul\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_var\\\_intervention\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_penalty\\\_decision\\\_band yalnız şu değerleri alır: stable, volatile ,referee\\\_disallowed\\\_goal\\\_band yalnız şu değerleri alır: rare, normal, frequent ,referee\\\_red\\\_card\\\_threshold\\\_band yalnız şu değerleri alır: early, normal, late ,referee\\\_technical\\\_area\\\_tolerance\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_closing\\\_whistle\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_control\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high ,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive

FUTBOL TEKNİK DİREKTÖR (KOÇ) KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı teknik direktörü “iyi/kötü” diye sınıflamak değildir. Amaç, maç içi kriz yönetimini, tempo/ritim müdahalesini, kart ve hakem bandında verdiği refleksleri ve son 15 dakika karar profilini tekrar eden örüntülerle kartlaştırmaktır.
Teknik direktör tempo yükselince oyunu sakinleştiriyor mu, yoksa tempo sapmasına izin mi veriyor? Bu soru, kontrol bandı yönetimini ölçer. Kontrol kaybı tekrar ediyorsa risk artar.
Teknik direktör ilk sarı kart sonrası disiplin bandını toparlıyor mu? Bu soru, kart sonrası refleksi ölçer. Kart görünce disiplin düşüyorsa tekrarlayan zaaf olur.
Teknik direktör kırmızı kart veya kritik karar sonrası plan değiştiriyor mu? Bu soru, kriz adaptasyonunu ölçer. Plan değişimi stabil ise takım kurtulur.
Teknik direktör VAR/penaltı gibi kırılmalarda panik mi yoksa kontrollü mü? Bu soru, mental yönetim bandını ölçer. Panikleşme kartla büyür.

Teknik direktör devre arası geçişinde oyuna yeni bir bant getiriyor mu? Bu soru, ikinci yarı refleksini ölçer. Devre arası etkisi tekrar ediyorsa kartlaşır.
Teknik direktör son 15 dakikada skoru koruma mı yoksa ikinci gol arama mı seçiyor? Bu soru, kapanış stratejisinin istikrarını ölçer.
Teknik direktör seyirci baskısı yükselince riskli hamle yapıyor mu? Bu soru, crowd\\\_pressure\\\_response ile koç davranışının bağını kurar.

Teknik direktör kritik oyuncu kaybında (kırmızı/sakatlık) takımı ayakta tutabiliyor mu? Bu soru, kritik oyuncu replacement\\\_gap ile doğrudan bağlıdır.
Teknik direktör hakem çizgisi sertleşince takımını disipline çekiyor mu? Bu soru, hakem profiline adaptasyon becerisini ölçer.
Teknik direktör seri halinde kötü gidişatı kırabiliyor mu? Bu soru, streak\\\_type etkisini ve müdahale gücünü ölçer.

FUTBOL TEKNİK DİREKTÖR (KOÇ) KARTI — ETİKET KATALOĞU
timestamp\\\_utc,coach\\\_ref,team\\\_ref,country\\\_ref,league\\\_ref,season\\\_id,competition\\\_type,season\\\_phase
coach\\\_tempo\\\_control\\\_band,coach\\\_post\\\_card\\\_management\\\_band,coach\\\_crisis\\\_adaptation\\\_band,coach\\\_key\\\_decision\\\_mental\\\_band,coach\\\_halftime\\\_adjustment\\\_band,coach\\\_closing\\\_strategy\\\_band,coach\\\_crowd\\\_pressure\\\_risk\\\_band,coach\\\_critical\\\_player\\\_loss\\\_management\\\_band,coach\\\_referee\\\_adaptation\\\_band,coach\\\_streak\\\_breaking\\\_band,coach\\\_tempo\\\_control\\\_band yalnız şu değerleri alır:
stable, unstable,coach\\\_post\\\_card\\\_management\\\_band yalnız şu değerleri alır: 
stable, unstable,coach\\\_crisis\\\_adaptation\\\_band yalnız şu değerleri alır:
strong, normal, weak,coach\\\_key\\\_decision\\\_mental\\\_band yalnız şu değerleri alır:
 
controlled, chaotic,coach\\\_halftime\\\_adjustment\\\_band yalnız şu değerleri alır: 
strong, normal, weak,coach\\\_closing\\\_strategy\\\_band yalnız şu değerleri alır: 
stable, unstable,coach\\\_crowd\\\_pressure\\\_risk\\\_band yalnız şu değerleri alır: 

low, medium, high,coach\\\_critical\\\_player\\\_loss\\\_management\\\_band yalnız şu değerleri alır: 
stable, unstable,coach\\\_referee\\\_adaptation\\\_band yalnız şu değerleri alır: 
strong, normal, weak,coach\\\_streak\\\_breaking\\\_band yalnız şu değerleri alır: 
strong, normal, weak,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: 
normal, incomplete, low, inactive

FUTBOLCU KARTI — ETİKET KATALOĞU
timestamp\\\_utc,player\\\_ref,team\\\_ref,country\\\_ref,league\\\_ref,season\\\_id,competition\\\_type,season\\\_phase,player\\\_early\\\_card\\\_risk\\\_band,player\\\_pressure\\\_error\\\_band,player\\\_red\\\_card\\\_risk\\\_band,player\\\_critical\\\_event\\\_involvement\\\_band,player\\\_post\\\_decision\\\_mental\\\_band,player\\\_closing\\\_stamina\\\_band,player\\\_critical\\\_weight\\\_band,player\\\_referee\\\_adaptation\\\_band,player\\\_control\\\_loss\\\_risk\\\_band,player\\\_injury\\\_recovery\\\_band,player\\\_early\\\_card\\\_risk\\\_band yalnız şu değerleri alır:

low, medium, high,player\\\_pressure\\\_error\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_red\\\_card\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_critical\\\_event\\\_involvement\\\_band yalnız şu değerleri alır:
low, medium, high,player\\\_post\\\_decision\\\_mental\\\_band yalnız şu değerleri alır: stable, unstable,player\\\_closing\\\_stamina\\\_band yalnız şu değerleri alır: strong, normal, weak,player\\\_critical\\\_weight\\\_band yalnız şu değerleri alır: normal, high,player\\\_referee\\\_adaptation\\\_band yalnız şu değerleri alır.
strong, normal, weak,player\\\_control\\\_loss\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_injury\\\_recovery\\\_band yalnız şu değerleri alır: strong, normal, weak,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive


FAZ-8-
TEKNİK DİREKTÖR KARTI — FAZ-1 TESLİMİ 
(Kart İskeleti + Etiket Duvarı + Soru Kütüphanesi)
person_ref: UNKNOWN_PERSON_REF .Kart Durumu: FAZ-1_SKELETON_ACTIVE .Kart Politikası: Tek person_ref / Sıfırlanmaz / Takım bağımsız büyür / Reference ile bağlanır / Unmapped korunur
Üretim Notu: Bu teslim yalnız iskelet üretimidir. Reference_dictionary ve maç–basın–odds akışları Faz-2 doğrulama ve doldurma içindir. Veri yokken hiçbir alan boş bırakılmaz; unknown/none/inactive bantları deterministik kullanılır.

TEKNİK DİREKTÖR KARTI — TAM PROFİL (FAZ-1 İSKELET)  Kimlik Rafıfull_name: 
unknownshort_name_alias: unknownname_variants: nonebirth_date: unknownage: unknownbirth_place: unknownnationality_primary: unknownnationality_secondary: nonelanguages: unknownpublic_profile_notes: unknown
Köken Rafı (Oyunculuk + Geçiş): playing_career_origin: unknown ,playing_positions: unknown ,coaching_transition_origin: unknown ,early_coaching_roles: unknown ,licenses_badges: unknown
Kariyer Timeline Rafı (Kulüp ve Görevler): career_timeline: none .Kural: Bu raf boş kalmaz; veri yoksa none bandında kalır ve Faz-2’de kayıtlar person_ref üzerinden eklenir.role_types_supported: head | interim | assistantstart_end_policy: unknown tarih varsa unknown bandı ile tutulur; zorla yıl/ay uydurulmaz.departure_band_policy: unknown | normal_exit | forced_exit | target_miss_context | inactiveera_policy: append_only / eras_are_non_overwriting
Sezon Etiket Rafı: season_tags: none,Kural: Sezon etiketleri Faz-2’de league_ref/team_ref ile bağlanır; serbest metinle bağ kurulmaz.Başarı Rafı (Trophy Shelf): trophies: none Kural: trophy_type + season_tag + team_ref ile tutulur; Faz-1’de veri yoksa none.
Hedef Sapması Rafı (Target Miss): target_miss_records: none Kural: başarısızlık “övgü/yerme” diliyle yazılmaz; yalnız hedef ve sapma bandı tutulur.
Davranış ve Oyun DNA (Era Bazlı): era_blocks: era_tag: unknown_era_1status: active_unknownevidence_level: low play_philosophy_core:

press_approach: unknown block_preference: unknown transition_priority: unknown set_play_patience: unknown wing_central_balance: unknown defensive_line_risk: unknown set_piece_approach: unknown rotation_tendency: unknown match_start_plan: unknown crisis_plan: unknown
in_game_intervention: substitution_timing_patterns: unknown score_protection_reflex: unknown risk_increase_reflex: unknown intervention_type_preference: unknown post_change_shape_effect: unknown
critical_bands: band_60_75: unknown band_80_plus: unknown people_management: youth_care: unknown academy_promotion_tendency: unknown star_player_dependency_tendency: unknown fighter_press_player_preference: unknown

squad_governance:
squad_stability: unknown youth_integration: unknown captain_leader_profile: unknown discipline_management: unknown crisis_management: unknown public_communication_style: unknown
Basın Dili Rafı: press_language_themes: unknown strong_signal_policy: multi_source_required signal_strength: weak_signal Kural: Basın verisi tek başına hüküm kurmaz; maç içi eksik event basından “kesin olay” diye tamamlanmaz.
Hakem Etkileşim Rafı: referee_interaction_pattern: unknown protest_intensity_band: unknown tension_pattern_band: unknown Kural: Hakem yargısı üretilmez; yalnız patern ölçülür.
Odds / Market Zaman Hizası Rafı: market_alignment_status: inactive_market time_alignment_notes: unknown Kural: Bu bölüm tahmin üretmez; yalnız hizalama ve pasiflik bandı taşır.
Bağlantılar (informed_by): informed_by: match_cards: none match_events: none press_rack: none player_cards: none referee_cards: none odds_market_timeline: none Kural: Bağlantı serbest metinle kurulmaz; Faz-2’de reference_dictionary üzerinden bağlanır.
Data Quality: data_quality_badge: low coverage_map: identity: unknown career_timeline: none dna_eras: active_unknown press: weak_signal referee_interaction: unknown market_alignment: inactive_market informed_by_links: none

(FAZ-1  TEKNİK DİREKTÖR ETİKET DUVARI DETERMINİSTİK SÖZLÜK ALANLARI) 
Bantlar ve Durum Etiketleri: unknown: veri yok / doğrulanmadı none: alan geçerli ama içerik yok (kayıt yok) inactive: kaynak var ama şu an aktif değil inactive_market: market verisi yok veya pasif
unmapped: reference_dictionary eşleşmesi yok, zorla eşleme yapılmadı weak_signal: tekil veya zayıf kaynak sinyali strong_signal: yalnız çoklu kaynak teyidi ile açılır active_unknown: era bloğu var ama içeriği doğrulanmadı
Kimlik Etiketleri: identity_status: unknown | verified nationality_band: unknown | single | dual name_variant_band: none | exists Kariyer Timeline Etiketleri: role_type: head | interim | assistant tenure_band: unknown | short | medium | long
start_date_band: unknown | known end_date_band: unknown | known | active departure_band: unknown | normal_exit | forced_exit | target_miss_context
Başarı Etiketleri: trophy_band: none | exists trophy_scope: domestic_league | domestic_cup | super_cup | continental | other
Hedef Sapması Etiketleri: target_miss_band: none | exists target_type: title | europe_qualification | relegation_avoid | points_target | other deviation_band: unknown | low | medium | high
Oyun DNA Çekirdek Etiketleri: press_approach: unknown | high_press | mid_press | low_block block_preference: unknown | high_line | mid_block | low_block transition_priority: unknown | transition_first | balanced | possession_first set_play_patience: unknown | low_patience | balanced | high_patience wing_central_balance: unknown | wing_focus | balanced | central_focus
defensive_line_risk: unknown | low_risk | balanced | high_riskset_piece_approach: unknown | set_piece_focus_low | balanced | set_piece_focus_high rotation_tendency: unknown | low_rotation | balanced | high_rotation match_start_plan: unknown | aggressive_start | balanced_start | cautious_start.
crisis_plan: unknown | early_intervention | late_intervention | reactive
Maç İçi Müdahale Etiketleri: substitution_timing_patterns: unknown | early | mid | late score_protection_reflex: unknown | low | medium | high risk_increase_reflex: unknown | low | medium | high intervention_type_preference: unknown | player_change | system_change | mixed post_change_shape_effect: unknown | stabilizes | destabilizes | unknown critical_band_60_75: unknown | inactive | active critical_band_80_plus: unknown | inactive | active

İnsan Yönetimi Etiketleri:
youth_care: unknown | low | medium | high ,academy_promotion_tendency: unknown | low | medium | high ,star_player_dependency_tendency: unknown | low | medium | high ,fighter_press_player_preference: unknown | low | medium | high
Kadro ve Yönetim Etiketleri: squad_stability: unknown | low | medium | high ,youth_integration: unknown | low | medium | high ,captain_leader_profile: unknown | undefined | stable_leader | rotating_leader ,discipline_management: unknown | soft | balanced | strict
crisis_management: unknown | low | medium | high ,public_communication_style: unknown | calm | assertive | confrontational | mixed
Basın Etiketleri
press_theme_status: unknown | tracked ,signal_strength: weak_signal | strong_signal
Hakem Etkileşim Etiketleri
referee_interaction_pattern: unknown | low_contact | medium_contact | high_contact ,protest_intensity_band: unknown | low | medium | high ,tension_pattern_band: unknown | low | medium | high
Market Etiketleri
market_alignment_status: inactive_market | active_aligned | active_misaligned ,market_data_strength: none | weak | strong
Reference Bağ Etiketleri
team_ref_status: unmapped | mapped ,league_ref_status: unmapped | mapped ,country_ref_status: unmapped | mapped

FAZ-9-
TEKNİK DİREKTÖR SORU KÜTÜPHANESİ 
(FAZ-1 GENİŞ TARAMA SETİ)
Kimlik ve Doğrulama:
Teknik direktörün resmi kayıt ad-soyad eşleşmesi nedir ve bilinen kısa adı/alias hangi kayıtlarda geçer?
İsim varyantları hangi kaynaklarda görülür ve hangileri yanlış eşleşme riski taşır?
Doğum tarihi, doğum yeri ve uyruk bilgileri hangi güvenilir kaynaklarla doğrulanabilir?
Çift uyruk veya sonradan uyruk değişimi var mı; varsa hangi tarihten itibaren geçerli kabul edilmeli?
Teknik direktörün kariyerinde ülke değişimleri hangi dönemlere denk gelir ve country_ref eşlemesi nasıl yapılmalı?

Oyunculuk Geçmişi ve Geçiş Kökeni:
Oyunculuk kariyeri hangi pozisyon ve oyun rolü üzerinden şekillendi; bu bilgi kayıt düzeyinde nasıl tutulmalı?
Oyunculuktan teknik direktörlüğe geçişte ilk görev tipi nedir; altyapı mı, yardımcı antrenörlük mü, analist rolü mü?
Oyunculuk geçmişi ile teknik adamlık oyun tercihi arasında doğrulanabilir bir köprü var mı, yoksa ilişki unknown mu kalmalı?
Antrenörlük lisansları ve eğitim geçmişi doğrulanabilir mi; doğrulanamıyorsa hangi bant kullanılmalı?

Kariyer Timeline (Eksiksiz Kronoloji):
Teknik direktörün çalıştığı tüm kulüpler ve görev tipleri (head/interim/assistant) tam liste olarak çıkarılabilir mi?
Her görev için başlangıç ve bitiş tarihleri hangi kaynakla doğrulanabilir; belirsiz tarihlerde unknown bandı nasıl tutulmalı?
Ayrılış sebepleri normal_exit mi forced_exit mi yoksa unknown mu; hangi eşiklerle forced_exit bandı açılmalı?
Beş yıldan eski görevler dahil tüm geçmiş aynı kartta korunurken, era_tag kırılımları hangi sezonsal işaretlerle ayrılmalı?
Kısa süreli görevler (çok kısa tenure) için ayrı bir tenure_band standardı uygulanacak mı?

Başarı Rafı (Trophy Shelf):
Trofe/şampiyonluk türleri hangi sınıflandırmaya göre tutulmalı ve trophy_scope nasıl atanmalı?
Başarılar hangi sezon etiketiyle ve hangi team_ref ile bağlanmalı; eşleşmeyenler nasıl unmapped kalmalı?
İkincilik/yarı final gibi başarı sayılmayan ama hedefe yakın sonuçlar trophy değil, target_miss mi olmalı?
Kupa türleri aynı isimle farklı ülkelerde geçiyorsa nasıl ayrıştırılmalı?

Hedef Sapması (Target Miss):
Kulüp hedefi resmi olarak biliniyor mu, yoksa unknown mu kalmalı?
Hedef sapması puan farkı, sıra farkı veya eleme turu üzerinden nasıl ölçülecek?
Target_miss_context bandı hangi durumlarda kariyer ayrılış bandına yansıtılmalı?
Hedef sapması kayıtları “başarısızlık” dili üretmeden hangi deterministik şablonla tutulmalı?

Oyun Felsefesi Çekirdeği (Era Bazlı):
Bu teknik direktörün pres yaklaşımı hangi dönemlerde değişti ve değişim noktaları hangi olaylarla doğrulanabilir?
Blok tercihi yüksek çizgi mi orta blok mu düşük blok mu; maç verisi olmadan bu alanlar unknown mı kalmalı?
Geçiş önceliği ve set oyunu sabrı birbirine karıştırılmadan hangi metriklerle ayrıştırılabilir?
Kanat/merkez dengesi hangi kadro yapılarında değişiyor; bu bir era_tag kırılımı gerektiriyor mu?
Savunma çizgisi riski ve geriye koşu profili maç içi olaylardan mı, yoksa sadece gözlem/basından mı geliyor?

Duran top yaklaşımı set_piece_focus_high bandını açacak kadar veri gerektirir mi; eşiği nedir?
Rotasyon eğilimi hangi periyotlarda artıyor; yoğun fikstürde mi, derbi haftalarında mı, Avrupa maçları sonrası mı?
Maç başlangıç planı agresif_start mı cautious_start mı; ilk 15 dakika paternleriyle doğrulanabilir mi?
Kriz planı erken müdahale mi geç müdahale mi; hangi skor senaryolarında devreye giriyor?

Maç İçi Müdahale ve Hamleler:
Değişiklik zaman paterni erken/mid/late olarak sınıflanırken hangi dakikalar eşik kabul edilmeli?
Skor koruma refleksi hangi durumda artıyor; 1-0, 2-1, kırmızı kart sonrası gibi senaryolar ayrı etiketlenmeli mi?
Risk artırma refleksi 60–75 bandında mı yoksa 80+ bandında mı tetikleniyor?
Hamle türü oyuncu değişikliği mi sistem değişikliği mi; sistem değişikliğini doğrulamak için hangi event gerekir?
Hamle sonrası oyun şekli stabilizes mi destabilizes mi; bunu hangi maç içi göstergelerle ölçmek gerekir?

İnsan Yönetimi ve Kadro Psikolojisi
Genç oyuncuya özen ve genç entegrasyonu aynı şey değilse nasıl ayrıştırılmalı ve iki alan ayrı doğrulanmalı mı?
Altyapıdan oyuncu çıkarma eğilimi kaç oyuncu ve kaç dakika ile “high” bandını hak eder?
Yıldız oyuncu odaklı kadro kurma eğilimi nasıl ölçülür; kaptanlık, dakika dağılımı, kritik anlarda tercih mi?
Mücadeleci/press oyuncusu tercih eğilimi transfer profiliyle mi yoksa sahadaki rol dağılımıyla mı doğrulanmalı?

Kadro istikrarı hangi dönemde düşüyor sakatlık krizi mi, form dalgalanması mı, disiplin mi?
Kaptan/leader profili sabit mi, dönemsiz mi, yoksa rotating_leader mı; nasıl etiketlenecek?
Disiplin yönetimi soft/balanced/strict bandı hangi olaylarla açılır; basın tek başına yeterli mi?
Kriz yönetimi maç içi dönüşler ve seri kayıplardan çıkışlarla mı ölçülmeli?
Kamuoyu dili calm/assertive/confrontational bandları hangi çoklu kaynak teyidiyle strong_signal olur?

Basın Dili ve Tema Takibi:
Tekrar eden temalar hangi başlık kümelerinde toplanmalı: hakem, sakatlık, transfer, mental, taktik, takvim mi?
Basın temaları sadece weak_signal olarak mı kalmalı, hangi koşulda strong_signal olur?
Basın metni ile maç içi olay arasında çelişki varsa hangisi baskın kabul edilir ve nasıl işaretlenir?
Basın dili rafı, maç içi eksik eventleri tamamlamadan nasıl “belirsiz” tutacak?

Hakem Etkileşimi:
İtiraz ve gerilim paternleri kaç örnekle high bandına çıkar; tek maç yeterli mi?
Hakem etkileşim alanı hakem yargısı üretmeden hangi deterministik etiketleri taşımalı?
Derbi, düşme hattı veya final gibi maçlarda protest_intensity artışı era_tag değişimi sayılır mı?

Odds/Market Zaman Hizası:
Market verisi pasifse inactive_market bandı dışında hangi alanlar unknown kalmalı?
Zaman hizası nasıl ölçülecek: maç önü 24s/12s/6s/1s pencere mi yoksa canlı dakika bazlı mı?
Odds hizası yalnız “eşzamanlılık” mı raporlar, yoksa kaynak sinyali gücü de ayrı bir alan mı olmalı?

Bağlantılar ve Reference Disiplini:
Kulüp, lig ve ülke bağlantıları serbest metin kullanmadan hangi minimum reference_dictionary alanlarıyla kurulmalı?
Unmapped kayıtlar Faz-2’de nasıl ele alınacak; zorla eşleme hangi koşulda kesinlikle yapılmayacak?
Match_card, player_card, referee_card bağları kartın hangi alanlarını kanıt zinciri olarak destekleyecek?

Data Quality ve Kapsama Haritası:
Hangi raflar doldurulmadığında data_quality_badge low kalmalı ve hangi eşikle medium seviyesine çıkar?
Coverage_map hangi düzende raporlanmalı ki analist hangi segmentin zayıf olduğunu tek bakışta görsün?
Eksik veri varken “anomali yok” demeden kart nasıl güvenli biçimde sunulmalı?

FAZ-10
HAKEM KARTI — EK RAF: İTİBAR / RİSK / UYUMLULUK PROFİLİ
integrity_risk_profile: unknown ,match_fixing_allegation_history: none ,corruption_case_history: none ,disciplinary_case_history: none ,conflict_of_interest_flags: none ,investigation_status_band: unknown ,Kural: Yargı kurulmaz; yalnız doğrulanmış dosya/kayıt varsa işlenir. Kanıt yoksa none. Belirsiz iddia varsa weak_signal.

HAKEM KARTI — EK RAF: TARAFSIZLIK VE AYRIMCILIK RİSKİ
bias_risk_profile: unknown ,club_bias_allegation_band: unknown ,country_bias_allegation_band: unknown ,star_player_bias_band: unknown ,youth_player_bias_band: unknown ,xenophobia_risk_band: unknown ,ethnic_discrimination_risk_band: unknown ,racism_incident_history: none ,Kural: Bu raf “önyargı var” demek için değil; “iddia/olay kaydı var mı” takibi içindir. Çoklu kaynak teyidi olmadan strong_signal açılmaz.

HAKEM KARTI — EK RAF: YILDIZ OYUNCU ve GENÇ OYUNCU MUAMELESİ (SAHA İZİ)
star_player_protection_tendency: unknown ,star_player_foul_threshold_delta: unknown ,youth_player_protection_tendency: unknown ,youth_player_foul_threshold_delta: unknown ,dialogue_asymmetry_band: unknown
Kural: Eğer veri varsa ölçülür; yoksa unknown kalır. “Korumuyor” diye negatif hüküm üretilmez.

HAKEM ETİKET DUVARI — EK ETİKETLER
allegation_strength: none | weak_signal | strong_signal .investigation_status_band: none | ongoing | closed_no_action | sanctioned | unknown .conflict_of_interest_flags: none | exists .club_bias_allegation_band: none | weak_signal | strong_signal | unknown
country_bias_allegation_band: none | weak_signal | strong_signal | unknown .star_player_bias_band: none | weak_signal | strong_signal | unknown .youth_player_bias_band: none | weak_signal | strong_signal | unknown .xenophobia_risk_band: none | weak_signal | strong_signal | unknown .ethnic_discrimination_risk_band: none | weak_signal | strong_signal | unknown .star_player_protection_tendency: unknown | low | medium | high .youth_player_protection_tendency: unknown | low | medium | high
dialogue_asymmetry_band: unknown | low | medium | high

FAZ-11
HAKEM SORU KÜTÜPHANESİ — EK SORU SETİ (HASSAS RİSK TARAMASI)
Hakemin geçmişte şike/etik soruşturması veya disiplin dosyası var mı; doğrulanabilir kayıtlarla hangi band açılmalı?
Hakem hakkında rüşvet, maç yönlendirme veya çıkar ilişkisi iddiaları geçmişte gündeme geldi mi; varsa allegation_strength nasıl atanmalı?
Hakemin belirli kulüplere karşı ayrıcalık gösterdiği iddiası var mı; hangi maç kümelerinde tekrarlanıyor ve kanıt zinciri var mı?
Hakemin belirli ülke takımlarına karşı tutum farkı iddiası var mı; bu iddia yalnız basın mı yoksa event-istatistikle destekli mi?
Hakemin yıldız futbolculara karşı tutumu farklı mı; kritik kararların “yıldız oyuncu lehine/aleyhine” sapması ölçülebiliyor mu?
Hakem genç oyunculara karşı daha sert mi daha korumacı mı; foul_threshold_delta gibi ölçümler üretilebilir mi?
Hakemin yabancı düşmanlığı veya etnik ayrımcılık iddiası geçmişte geçti mi; resmi yaptırım veya doğrulanmış olay var mı?
Irkçılık veya ayrımcı söylem içeren saha içi olay kaydı var mı; varsa racisim_incident_history nasıl tutulmalı?
Tekil tartışmalı maçlar kartta nasıl saklanmalı; “kanıt yoksa” none/weak_signal bandı nasıl uygulanmalı?
Bu hassas başlıklar hiçbir zaman hüküm cümlesiyle mi yazılmalı, yoksa yalnız kayıt ve sinyal bandı mı tutulmalı?

FAZ-12
FUTBOLCU KARTI — FAZ-1 TESLİMİ (Kart İskeleti + Etiket Duvarı + Soru Kütüphanesi) player_ref: UNKNOWN_PLAYER_REF Kart Durumu: FAZ-1_SKELETON_ACTIVE Kart Politikası: Tek player_ref / Sıfırlanmaz / Takım bağımsız büyür / Reference ile bağlanır / Unmapped korunur
Üretim Notu: Bu teslim yalnız iskelet üretimidir. Reference_dictionary ve maç–basın–odds akışları Faz-2 doğrulama ve doldurma içindir. Veri yokken hiçbir alan boş bırakılmaz; unknown/none/inactive bantları deterministik kullanılır.

FUTBOLCU KARTI — TAM PROFİL (FAZ-1 İSKELET)
Kimlik Rafı: full_name: unknown .short_name_alias: unknown .name_variants: none .birth_date: unknown .age: unknown .birth_place: unknown .nationality_primary: unknown .nationality_secondary: none .languages: unknown .public_profile_notes: unknown
player_ref: UNKNOWN_PLAYER_REF .identity_status: unknown.
Köken Rafı (Altyapı + Geçiş): .academy_origin: unknown .youth_clubs_timeline: none .debut_context: unknown .early_role_profile: unknown .licenses_badges: none
Kariyer Timeline Rafı (Kulüp ve Görevler): .career_timeline: none .Kural: Bu raf boş kalmaz; veri yoksa none bandında kalır ve Faz-2’de kayıtlar player_ref üzerinden eklenir. timeline_entry_schema_policy: team_ref + league_ref + country_ref + season_tag + role_profile + start_date_band + end_date_band + departure_band + evidence_level .start_end_policy: unknown tarih varsa unknown bandı ile tutulur; zorla yıl/ay uydurulmaz. departure_band_policy: unknown | normal_exit | forced_exit | loan_start | loan_end | injury_exit | disciplinary_exit | inactive .era_policy: append_only / eras_are_non_overwriting
Pozisyon ve Rol Haritası Rafı: .primary_position: unknown .secondary_positions: none .role_profiles: unknown .field_zone_preferences: unknown .tactical_discipline_band: unknown .role_flexibility_band: unknown .press_role_fit_band: unknown
Fiziksel Profil Rafı: .height: unknown .weight: unknown .dominant_foot: unknown .body_type_band: unknown .stamina_band: unknown .sprint_band: unknown .acceleration_band: unknown .strength_band: unknown .agility_band: unknown .balance_band: unknown

Teknik Yetenek Rafı: first_touch_band: unknown .short_pass_band: unknown .long_pass_band: unknown .crossing_band: unknown .dribbling_band: unknown .ball_carrying_speed_band: unknown .weak_foot_band: unknown .finishing_band: unknown .shot_quality_band: unknown
heading_band: unknown .one_v_one_attack_band: unknown .one_v_one_defense_band: unknown
Zihinsel ve Karar Mekaniği Rafı: .game_iq_band: unknown .positioning_band: unknown .decision_speed_band: unknown .risk_taking_band: unknown .composure_band: unknown .concentration_band: unknown .leadership_band: unknown .responsibility_band: unknown
Hücum Davranışı Rafı: .run_variety_band: unknown .depth_run_threat_band: unknown .box_runs_band: unknown .wall_play_band: unknown .final_pass_band: unknown .shot_selection_band: unknown .goal_creation_band: unknown .assist_creation_band: unknown
Defans Davranışı Rafı:.press_intensity_band: unknown .press_timing_band: unknown .tackle_band: unknown .interception_band: unknown .duel_win_band: unknown .aerial_duel_band: unknown .recovery_run_band: unknown .defensive_error_risk_band: unknown
Geçiş Oyunları Rafı: .attack_transition_speed_band: unknown .defense_transition_reaction_band: unknown .counter_start_band: unknown .counter_stop_band: unknown .transition_discipline_band: unknown

Duran Top Profili Rafı: .set_piece_role: unknown .corner_taker_band: unknown .free_kick_taker_band: unknown .penalty_taker_band: unknown .throw_in_role_band: unknown .second_ball_instinct_band: unknown
Disiplin ve Kart Riski Rafı: .foul_type_profile: unknown .yellow_card_tendency: unknown .red_card_tendency: unknown .dissent_band: unknown .aggression_band: unknown
Sakatlık ve Devamlılık Rafı: .injury_history: none .injury_type_clusters: unknown .matches_missed_band: unknown .load_management_band: unknown .return_performance_band: unknown .chronic_risk_band: unknown
Form ve İstikrar Rafı: .form_trend_band: unknown .performance_volatility_band: unknown .big_match_band: unknown .away_match_band: unknown .derby_match_band: unknown .Psikoloji ve Baskı Rafı .pressure_response_band: unknown .penalty_pressure_band: unknown
collapse_under_crisis_band: unknown .rebound_after_failure_band: unknown
Tribün Baskısı Rafı: .crowd_pressure_performance: unknown .home_crowd_performance_band: unknown .away_crowd_performance_band: unknown .derby_pressure_band: unknown .high_stakes_match_band: unknown .error_rate_under_pressure: unknown .decision_speed_under_pressure: unknown .discipline_risk_under_pressure: unknown .finishing_under_pressure: unknown.
Kimya ve Takım İçi Uyum Rafı: .locker_room_influence_band: unknown .coach_fit_band: unknown .team_fit_band: unknown .adaptation_speed_band: unknown .captaincy_status_band: unknown
Başarı Rafı (Trophy Shelf): .trophies: none .awards: none .Kural: trophy_type + season_tag + team_ref ile tutulur; Faz-1’de veri yoksa none. .Hedef Sapması Rafı (Target Miss): .target_miss_records: none .Kural: başarısızlık “övgü/yerme” diliyle yazılmaz; yalnız hedef ve sapma bandı tutulur.

Oyun DNA (Era Bazlı): .era_blocks: .era_tag: unknown_era_1 .status: active_unknown .evidence_level: low .role_evolution: unknown .position_evolution: unknown .physical_evolution: unknown .technical_evolution: unknown .mental_evolution: unknown
Basın ve Kamu Algısı Rafı: .press_themes: unknown .strong_signal_policy: multi_source_required .signal_strength: weak_signal .Kural: Basın verisi tek başına hüküm kurmaz; maç içi eksik event basından “kesin olay” diye tamamlanmaz.
Etik ve Risk Rafı: .integrity_risk_profile: unknown .doping_case_history: none .betting_related_allegation_history: none .disciplinary_case_history: none .serious_off_field_incidents_history: none .allegation_strength: none .investigation_status_band: unknown
Kural: Yargı kurulmaz; yalnız doğrulanmış dosya/kayıt varsa işlenir. Belirsiz iddia weak_signal bandında tutulur. Odds / Market Zaman Hizası Rafı: .market_alignment_status: inactive_market .time_alignment_notes: unknown .Kural: Bu bölüm tahmin üretmez; yalnız hizalama ve pasiflik bandı taşır.
Bağlantılar (informed_by): .informed_by: .match_cards: none .match_events: none .press_rack: none .team_cards: none .coach_cards: none .referee_cards: none .odds_market_timeline: none .Kural: Bağlantı serbest metinle kurulmaz; Faz-2’de reference_dictionary üzerinden bağlanır.
Data Quality: .data_quality_badge: low .coverage_map: .identity: unknown .career_timeline: none .position_role: unknown .physical_profile: unknown .technical: unknown .mental: unknown .attack_defense: unknown .injury: none .press: weak_signal
ethics_risk: none .market_alignment: inactive_market .informed_by_links: none

FAZ-13
FUTBOLCU ETİKET DUVARI (FAZ-1 DETERMINİSTİK SÖZLÜK ALANLARI)
Bantlar ve Durum Etiketleri:
unknown: veri yok / doğrulanmadı none: alan geçerli ama içerik yok (kayıt yok) inactive: kaynak var ama şu an aktif değil inactive_market: market verisi yok veya pasif unmapped: reference_dictionary eşleşmesi yok, zorla eşleme yapılmadı
weak_signal: tekil veya zayıf kaynak sinyali strong_signal: yalnız çoklu kaynak teyidi ile açılır active_unknown: segment var ama içeriği doğrulanmadı
Kimlik Etiketleri:
identity_status: unknown | verified nationality_band: unknown | single | dual name_variant_band: none | exists
Kariyer Timeline Etiketleri:
tenure_band: unknown | short | medium | long start_date_band: unknown | known end_date_band: unknown | known | active departure_band: unknown | normal_exit | forced_exit | loan_start | loan_end | injury_exit | disciplinary_exit | inactive
Pozisyon ve Rol Etiketleri:
primary_position: unknown | gk | df | mf | fw ,role_flexibility_band: unknown | low | medium | high ,tactical_discipline_band: unknown | low | medium | high ,press_role_fit_band: unknown | low | medium | high
Fiziksel Etiketler:
dominant_foot: unknown | right | left | both ,body_type_band: unknown | light | balanced | strong,stamina_band: unknown | low | medium | high,sprint_band: unknown | low | medium | high,acceleration_band: unknown | low | medium | high,strength_band: unknown | low | medium | high,agility_band: unknown | low | medium | high,balance_band: unknown | low | medium | high

Teknik Etiketler:
first_touch_band: unknown | low | medium | high,short_pass_band: unknown | low | medium | high,long_pass_band: unknown | low | medium | high,crossing_band: unknown | low | medium | high,dribbling_band: unknown | low | medium | high,ball_carrying_speed_band: unknown | low | medium | high,weak_foot_band: unknown | low | medium | high,finishing_band: unknown | low | medium | high,shot_quality_band: unknown | low | medium | high,heading_band: unknown | low | medium | high,one_v_one_attack_band: unknown | low | medium | high
one_v_one_defense_band: unknown | low | medium | high
Mental Etiketler:
game_iq_band: unknown | low | medium | high,positioning_band: unknown | low | medium | high,decision_speed_band: unknown | low | medium | high,risk_taking_band: unknown | low | medium | high,composure_band: unknown | low | medium | high,concentration_band: unknown | low | medium | high,leadership_band: unknown | low | medium | high,responsibility_band: unknown | low | medium | high
Hücum Etiketleri:
run_variety_band: unknown | low | medium | high,depth_run_threat_band: unknown | low | medium | high,box_runs_band: unknown | low | medium | high,wall_play_band: unknown | low | medium | high,final_pass_band: unknown | low | medium | high
shot_selection_band: unknown | low | medium | high,goal_creation_band: unknown | low | medium | highassist_creation_band: unknown | low | medium | high

Defans Etiketleri:
press_intensity_band: unknown | low | medium | high,press_timing_band: unknown | low | medium | high,duel_win_band: unknown | low | medium | high,aerial_duel_band: unknown | low | medium | high,recovery_run_band: unknown | low | medium | high
defensive_error_risk_band: unknown | low | medium | high
Geçiş Etiketleri:
attack_transition_speed_band: unknown | low | medium | high,defense_transition_reaction_band: unknown | low | medium | high,transition_discipline_band: unknown | low | medium | high
Duran Top Etiketleri:
set_piece_role: unknown | taker | target | none,corner_taker_band: unknown | low | medium | high,free_kick_taker_band: unknown | low | medium | high,penalty_taker_band: unknown | low | medium | high,second_ball_instinct_band: unknown | low | medium | high
Disiplin Etiketleri:
yellow_card_tendency: unknown | low | medium | high,red_card_tendency: unknown | low | medium | high,dissent_band: unknown | low | medium | high,aggression_band: unknown | low | medium | high

Sakatlık Etiketleri:
matches_missed_band: unknown | low | medium | high,load_management_band: unknown | low | medium | high,return_performance_band: unknown | low | medium | high,chronic_risk_band: unknown | low | medium | high
Form Etiketleri:
form_trend_band: unknown | low | medium | high,performance_volatility_band: unknown | low | medium | high,big_match_band: unknown | low | medium | high,away_match_band: unknown | low | medium | high,derby_match_band: unknown | low | medium | high
Baskı Etiketleri:
pressure_response_band: unknown | low | medium | high,penalty_pressure_band: unknown | low | medium | high,collapse_under_crisis_band: unknown | low | medium | high,rebound_after_failure_band: unknown | low | medium | high
Tribün Baskısı Etiketleri:
crowd_pressure_band: unknown | low | medium | high,pressure_decision_risk_band: unknown | low | medium | high,late_game_pressure_band: unknown | low | medium | high

Kimya Etiketleri:
locker_room_influence_band: unknown | low | medium | high,coach_fit_band: unknown | low | medium | high,team_fit_band: unknown | low | medium | high,adaptation_speed_band: unknown | low | medium | high,captaincy_status_band: unknown | none | vice | captain
Basın Etiketleri:
press_theme_status: unknown | tracked,signal_strength: weak_signal | strong_signal
Etik ve Risk Etiketleri:
allegation_strength: none | weak_signal | strong_signal,investigation_status_band: none | ongoing | closed_no_action | sanctioned | unknown
Market Etiketleri:
market_alignment_status: inactive_market | active_aligned | active_misaligned,market_data_strength: none | weak | strong,Reference Bağ Etiketleri,team_ref_status: unmapped | mapped,league_ref_status: unmapped | mapped,country_ref_status: unmapped | mapped

FAZ-14
FUTBOLCU SORU KÜTÜPHANESİ (FAZ-1 GENİŞ TARAMA SETİ)
Kimlik ve Doğrulama:
Futbolcunun resmi kayıt ad-soyad eşleşmesi nedir ve bilinen kısa adı/alias hangi kayıtlarda geçer?
İsim varyantları hangi kaynaklarda görülür ve hangileri yanlış eşleşme riski taşır?
Doğum tarihi, doğum yeri ve uyruk bilgileri hangi güvenilir kaynaklarla doğrulanabilir?
Çift uyruk veya ülke değişimi var mı; varsa hangi tarihten itibaren geçerli kabul edilmeli?
Futbolcunun kariyerinde ülke/lig değişimleri hangi dönemlere denk gelir ve country_ref/league_ref eşlemesi nasıl yapılmalı?

Köken ve Altyapı:
Altyapı kökeni hangi kulüp/akademi üzerinden doğrulanabilir?,Genç yaşta rolü ve saha profili nasıldı; early_role_profile nasıl tutulmalı?,Profesyonel debut hangi maç/turnuva bağlamında oldu; debut_context nasıl doğrulanmalı?
Genç yaşta pozisyon değişimi veya rol dönüşümü yaşandı mı; position_evolution nasıl işaretlenmeli?
Kariyer Timeline:
Çalıştığı tüm kulüpler, kiralık dönemler ve görev rol profilleri tam liste olarak çıkarılabilir mi?,Her dönem için sezon_tag, team_ref ve tarih bandı hangi kaynaklarla doğrulanabilir?,Kiralık başlangıç ve bitişleri loan_start/loan_end bandlarıyla nasıl tutulmalı?
Ayrılış sebepleri forced_exit mi normal_exit mi yoksa injury_exit mi; hangi eşiklerle açılmalı?

Pozisyon ve Rol:
Ana pozisyonu ve yan pozisyonları hangi sezonlarda değişti?,Rol profili (box-to-box, inverted winger vb.) nasıl doğrulanacak; maç verisi yoksa unknown mı kalmalı?,Taktik disiplin ve rol esnekliği hangi metriklerle ayrıştırılabilir?
Pres rol uyumu hangi takım oyun planlarında yükseliyor/düşüyor?
Fiziksel Profil:Boy/kilo ve dominant ayak doğrulanabilir mi?,Sprint/ivmelenme/güç/çeviklik bantları hangi maç verileriyle doğrulanmalı?,Dayanıklılık ve yük yönetimi sakatlık geçmişiyle nasıl ilişkilendirilmeli?
Teknik Profil:
İlk kontrol ve pas kalitesi hangi gözlem veya metrikle güçlü sinyal olur?,Bitiricilik ve şut kalitesi ayrımı nasıl yapılmalı?,Dripling ve top taşıma hızı aynı şey değilse nasıl ayrıştırılmalı?,Zayıf ayak bandı nasıl doğrulanır?
Mental Profil:Oyun zekâsı ve karar hızı nasıl ölçülür; yalnız gözlemle mi, metrikle mi?,Risk alma eğilimi hangi maç senaryolarında artıyor?,Soğukkanlılık ve konsantrasyon düşüşü hangi dakikalarda belirginleşiyor?,Liderlik ve sorumluluk alma hangi durumlarda görünür olur?
Hücum ve Defans Davranışı:
Koşu çeşitliliği ve derin koşu tehdidi hangi maçlarda yükseliyor?,Final pası ve asist üretimi birbirinden nasıl ayrıştırılır?,Pres şiddeti ve pres zamanlaması birlikte mi ölçülür, ayrı mı?,Savunma hatası riski hangi stres senaryolarında artar?
Geçiş Oyunları:
Top kaybı sonrası reaksiyon süresi nasıl ölçülecek?,Kontra başlatma ve kontra durdurma rolleri aynı oyuncuda birlikte mi görünür?
Duran Top:
Duran top kullanıcısı mı hedef mi; set_piece_role nasıl atanmalı?,Penaltı kullanma geçmişi ve baskı altında performansı nasıl tutulmalı?
Disiplin:
Kart eğilimi hangi maç türlerinde artıyor?,İtiraz bandı tek maçla mı açılır yoksa trend mi gerekir?
Sakatlık:
Sakatlık geçmişi doğrulanabilir mi; injury_type_clusters nasıl tutulmalı?,Kronik risk bandı hangi tekrar eşiğinde açılır?,Geri dönüş performansı düşüyor mu yükseliyor mu; return_performance_band nasıl ölçülür?
Form ve İstikrar:
Form trendi ve dalgalanma hangi periyotlarda belirgin?,Büyük maç, derbi ve deplasman performansı ayrı bantlarda mı izlenmeli?
Psikoloji ve Baskı:
Penaltı anı performansı ve baskı altında hata riski nasıl ölçülmeli?,Kriz anında düşüş mü toparlanma mı baskın; rebound_after_failure bandı nasıl atanmalı?
Tribün Baskısı:
İç saha seyircisi performansı artırıyor mu düşürüyor mu; home_crowd_performance_band nasıl ölçülmeli?,Deplasman tribünü baskısında karar hatası artıyor mu; error_rate_under_pressure nasıl tutulmalı?.Derbi ve yüksek risk maçlarda finishing_under_pressure düşüyor mu?
Kimya:Soyunma odası etkisi ve takım uyumu nasıl gözlemlenir; tek kaynak yeterli mi? Koçla uyum bozulursa performans trendinde hangi sinyal görülür?
Basın ve Algı:
Basında futbolcu hakkında tekrar eden temalar var mı; hangi koşulda strong_signal olur?,Basın metni ile maç içi event çelişirse hangisi baskın kabul edilir ve nasıl işaretlenir?
Etik ve Risk:
Doping, bahis bağlantısı iddiası, disiplin soruşturması veya saha dışı olay geçmişi var mı; allegation_strength nasıl atanmalı?,Resmi yaptırım varsa investigation_status_band nasıl işlenmeli?
Odds/Market Zaman Hizası:
Sakatlık duyurusu, ilk 11 sürprizi veya kadro dışı kalma sinyali market hizasında nasıl işaretlenmeli?

Bağlantılar ve Reference Disiplini:
Kulüp/lig/ülke bağlantıları serbest metin kullanmadan hangi minimum reference_dictionary alanlarıyla kurulmalı?,Unmapped kayıtlar Faz-2’de nasıl ele alınacak; zorla eşleme hangi koşulda kesinlikle yapılmayacak?
Match_card ve match_event bağları futbolcu kartının hangi raflarını kanıt zinciri olarak destekleyecek?
Data Quality ve Kapsama Haritası:
Hangi raflar dolmadan data_quality_badge low kalmalı ve hangi eşikle medium seviyesine çıkar?,Coverage_map hangi düzende raporlanmalı ki analist hangi segmentin zayıf olduğunu tek bakışta görsün?,Eksik veri varken “anomali yok” demeden futbolcu kartı nasıl güvenli biçimde sunulmalı

FAZ-15
TEKNİK DİREKTÖR KARTI — EK RAF: TRİBÜN BASKISI YÖNETİMİ
crowd_pressure_handling: unknown,home_crowd_effect_band: unknown,away_crowd_effect_band: unknown,derby_crowd_effect_band: unknown,late_game_crowd_effect_band: unknown,decision_risk_under_pressure: unknown,tactical_deviation_under_pressure: unknown,communication_shift_under_pressure: unknown,Kural: Yorum yok; yalnız tekrar eden patern ve ölçülebilir sapma.
HAKEM KARTI — EK RAF: TRİBÜN BASKISI ALTINDA MAÇ YÖNETİMİ
crowd_pressure_handling: unknown,home_bias_pressure_sensitivity: unknown,away_bias_pressure_sensitivity: unknown,derby_pressure_response: unknown,late_decision_pressure_risk: unknown,carding_shift_under_pressure: unknown,penalty_decision_pressure_risk: unknown,dialogue_control_under_pressure: unknown,Kural: Taraf seçimi iddiası üretmez; yalnız patern ölçer.
FUTBOLCU KARTI — EK RAF: TRİBÜN BASKISI PERFORMANSI
crowd_pressure_performance: unknown,home_crowd_performance_band: unknown,away_crowd_performance_band: unknown,derby_pressure_band: unknown,high_stakes_match_band: unknown,error_rate_under_pressure: unknown,decision_speed_under_pressure: unknown
discipline_risk_under_pressure: unknown,finishing_under_pressure: unknown,Kural: Tek maçla hüküm yok; trend/patern yoksa unknown.
ETİKET DUVARI — ORTAK BANTLAR
crowd_pressure_band: unknown | low | medium | high,pressure_decision_risk_band: unknown | low | medium | high,late_game_pressure_band: unknown | low | medium | high

TAKIM KARTI — FAZ-1 TESLİMİ (Kart İskeleti + Etiket Duvarı + Soru Kütüphanesi)
team_ref: UNKNOWN_TEAM_REF
Kart Durumu: FAZ-1_SKELETON_ACTIVE
Kart Politikası: Tek team_ref / Sıfırlanmaz / Takım kartı takımda kalır / Reference ile bağlanır / Unmapped korunur
Üretim Notu: Bu teslim yalnız iskelet üretimidir. Reference_dictionary ve maç–basın–odds akışları Faz-2 doğrulama ve doldurma içindir. Veri yokken hiçbir alan boş bırakılmaz; unknown/none/inactive bantları deterministik kullanılır.

TAKIM KARTI — TAM PROFİL (FAZ-1 İSKELET)
Kimlik Rafı
team_ref: UNKNOWN_TEAM_REF,club_name: unknown,short_name_alias: unknown,name_variants: none,founded_year: unknown,city_ref: unknown,country_ref: unknown,league_ref: unknown,stadium_ref: unknown,stadium_capacity_band: unknownclub_model_band: unknown
identity_status: unknown
Tarihçe ve Statü Rafı
era_policy: append_only / eras_are_non_overwriting,era_blocks: none,historical_identity_themes: unknown,rise_fall_turning_points: unknown,dominant_periods: none
Başarı Rafı (Trophy Shelf)
trophies: none,records: none,Kural: trophy_type + season_tag + competition_ref ile tutulur; Faz-1’de veri yoksa none.
Hedef Sapması Rafı (Target Miss)
season_targets: none,target_miss_records: none,Kural: hedef sapması “övgü/yerme” diliyle yazılmaz; yalnız hedef ve sapma bandı tutulur.
Kadro ve Transfer DNA Rafı
academy_output_band: unknown,star_transfer_tendency: unknown,fighter_profile_preference: unknown,sell_to_grow_model_band: unknown,loan_dependency_band: unknown,age_profile_trend_band: unknown,scouting_region_bias: unknown
Oyun DNA (Takım İmzası)
press_approach: unknown,block_preference: unknown,transition_priority: unknown,set_play_patience: unknown,wing_central_balance: unknown,defensive_line_risk: unknown,set_piece_strength_band: unknown,set_piece_weakness_band: unknown,tempo_band: unknown
flexibility_band: unknown,creation_source_band: unknown,press_resistance_band: unknown,sterile_possession_band: unknown,build_up_risk_band: unknown

Maç İçi Davranış DNA Rafı: match_start_behavior_band: unknown,concede_first_response_band: unknown,score_first_behavior_band: unknown,late_game_behavior_band: unknown,comeback_capacity_band: unknown,score_protection_discipline_band: unknown,risk_increase_trigger_band: unknown ,panic_under_pressure_band: unknown
Seri ve Momentum Rafı: streak_building_ability_band: unknown,win_streak_tendency_band: unknown,loss_streak_risk_band: unknown,draw_streak_tendency_band: unknown,post_loss_response_band: unknown,post_win_complacency_risk_band: unknown,post_draw_response_band: unknown
Kural: Seri davranışı tek maçla hüküm üretmez; trend/patern yoksa unknown kalır.
İç Saha / Deplasman Rafı: home_strength_band: unknown,away_resilience_band: unknown,home_crowd_effect_band: unknown,away_crowd_effect_band: unknown,travel_pressure_band: unknown
Tribün ve Baskı Yönetimi Rafı: crowd_pressure_handling: unknown,derby_pressure_band: unknown,high_target_pressure_band: unknown,late_game_pressure_band: unknown,decision_risk_under_pressure_band: unknown
Disiplin ve Kart Profili Rafı: discipline_profile: unknown,yellow_card_tendency: unknown,red_card_tendency: unknown,dissent_protest_band: unknown,aggression_band: unknown,foul_type_clusters: unknown
Sakatlık ve Yük Yönetimi Rafı,injury_cluster_band: unknown,load_collapse_band: unknown,rotation_resilience_band: unknown,return_from_injury_impact_band: unknown

Koç Etkisi Haritası Rafı: coach_dependence_band: unknown,new_coach_bounce_band: unknown,coach_change_disruption_band: unknown,dna_persistence_after_coach_band: unknown,Yıldız Oyuncu Bağımlılığı Rafı
star_dependency_band: unknown,leader_loss_impact_band: unknown,youth_carry_capacity_band: unknown,Hakem Etkileşim Profili Rafı,referee_tension_pattern: unknown,card_risk_under_ref_pressure_band: unknown,penalty_incidence_band: unknown,var_tension_band: unknown
Basın ve Kamu Algısı Rafı,press_themes: unknown,strong_signal_policy: multi_source_required,signal_strength: weak_signal,crisis_communication_style: unknown,expectation_inflation_band: unknown,fan_protest_pressure_band: unknown,narrative_gap_band: unknown
Kural: Basın verisi tek başına hüküm kurmaz; eksik event basınla tamamlanmaz.

Etik ve Risk Rafı:,integrity_risk_profile: unknown,financial_crisis_band: unknown,match_fixing_allegation_history: none,disciplinary_case_history: none,allegation_strength: none,investigation_status_band: unknown,Kural: Yargı kurulmaz; yalnız doğrulanmış dosya/kayıt varsa işlenir. Belirsiz iddia weak_signal bandında tutulur.
Odds / Market Zaman Hizası Rafı:,market_alignment_status: inactive_market,time_alignment_notes: unknown,Kural: Bu bölüm tahmin üretmez; yalnız hizalama ve pasiflik bandı taşır.
Bağlantılar (informed_by),informed_by:,match_cards: none,match_events: none,press_rack: none,player_cards: none,coach_cards: none,referee_cards: none,odds_market_timeline: none,Kural: Bağlantı serbest metinle kurulmaz; Faz-2’de reference_dictionary üzerinden bağlanır.
Data Quality:,data_quality_badge: low,coverage_map:,identity: unknown,history_status: unknowntrophies: none,targets: none,squad_transfer_dna: unknownteam_dna: unknown,in_game_behavior: unknown,streak_momentum: unknown,home_away: unknown,pressure_crowd: unknown,discipline: unknown,injury_load: unknown,coach_effect: unknown,star_dependency: unknown,press: weak_signal,ethics_risk: none,market_alignment: inactive_market,informed_by_links: none
TAKIM ETİKET DUVARI (FAZ-1 DETERMINİSTİK SÖZLÜK ALANLARI)
Bantlar ve Durum Etiketleri,unknown: veri yok / doğrulanmadı,none: alan geçerli ama içerik yok (kayıt yok),inactive: kaynak var ama şu an aktif değil,inactive_market: market verisi yok veya pasif,unmapped: reference_dictionary eşleşmesi yok, zorla eşleme yapılmadı
weak_signal: tekil veya zayıf kaynak sinyali,strong_signal: yalnız çoklu kaynak teyidi ile açılır,active_unknown: segment var ama içeriği doğrulanmadı
Kimlik Etiketleri: identity_status: unknown | verified club_model_band: unknown | member_owned | private_owned | mixed stadium_capacity_band: unknown | small | medium | large
Hedef ve Başarı EtiketleriÇ: trophy_band: none | exists trophy_scope: domestic_league | domestic_cup | super_cup | continental | othertarget_type: title | europe_qualification | relegation_avoid | points_target | other ,deviation_band: unknown | low | medium | high
Kadro ve Transfer Etiketleri: academy_output_band: unknown | low | medium | high ,star_transfer_tendency: unknown | low | medium | high ,fighter_profile_preference: unknown | low | medium | high ,sell_to_grow_model_band: unknown | low | medium | high
loan_dependency_band: unknown | low | medium | high .age_profile_trend_band: unknown | youth_focus | balanced | veteran_focus | unknown


FAZ-16
Takım Oyun DNA Etiketleri:
press_approach: unknown | high_press | mid_press | low_block,block_preference: unknown | high_line | mid_block | low_block,transition_priority: unknown | transition_first | balanced | possession_first,set_play_patience: unknown | low_patience | balanced | high_patience
wing_central_balance: unknown | wing_focus | balanced | central_focus,defensive_line_risk: unknown | low_risk | balanced | high_risk,set_piece_strength_band: unknown | low | medium | high,set_piece_weakness_band: unknown | low | medium | high
tempo_band: unknown | low | medium | high,flexibility_band: unknown | low | medium | high,creation_source_band: unknown | individual_quality | system | mixed | unknown,press_resistance_band: unknown | low | medium | high,sterile_possession_band: unknown | low | medium | high,build_up_risk_band: unknown | low | medium | high
Maç İçi Davranış Etiketleri:
match_start_behavior_band: unknown | low | medium | high,concede_first_response_band: unknown | collapse | unstable | stable | comeback,score_first_behavior_band: unknown | protect | control | push_more | unstable,late_game_behavior_band: unknown | stable | volatile | aggressive | passive | unknown,comeback_capacity_band: unknown | low | medium | high,score_protection_discipline_band: unknown | low | medium | high,risk_increase_trigger_band: unknown | early | mid | late | unknown,panic_under_pressure_band: unknown | low | medium | high
Seri ve Momentum Etiketleri:
streak_building_ability_band: unknown | low | medium | high,win_streak_tendency_band: unknown | low | medium | high,loss_streak_risk_band: unknown | low | medium | high,draw_streak_tendency_band: unknown | low | medium | high,post_loss_response_band: unknown | collapse | unstable | stable | rebound,post_win_complacency_risk_band: unknown | low | medium | high,post_draw_response_band: unknown | collapse | unstable | stable | rebound
İç Saha / Deplasman Etiketleri
home_strength_band: unknown | low | medium | high,away_resilience_band: unknown | low | medium | hightravel_pressure_band: unknown | low | medium | high
Baskı Etiketleri
crowd_pressure_band: unknown | low | medium | high,late_game_pressure_band: unknown | low | medium | high,pressure_decision_risk_band: unknown | low | medium | high
Disiplin Etiketleri
yellow_card_tendency: unknown | low | medium | high,red_card_tendency: unknown | low | medium | high,aggression_band: unknown | low | medium | high,dissent_protest_band: unknown | low | medium | high
Sakatlık ve Yük Etiketleri
load_collapse_band: unknown | low | medium | high,rotation_resilience_band: unknown | low | medium | high
Basın Etiketleri
press_theme_status: unknown | tracked,signal_strength: weak_signal | strong_signal
Etik ve Risk Etiketleri
allegation_strength: none | weak_signal | strong_signal,investigation_status_band: none | ongoing | closed_no_action | sanctioned | unknown,financial_crisis_band: unknown | low | medium | high
Market Etiketleri
market_alignment_status: inactive_market | active_aligned | active_misaligned,market_data_strength: none | weak | strong
Reference Bağ Etiketleri
team_ref_status: unmapped | mapped,league_ref_status: unmapped | mapped,country_ref_status: unmapped | mapped

FAZ-18 BOOKMAKER BÖLÜM -1
BAHİS ŞİRKETİ KARTI — FAZ-1 TESLİMİ 
(Kart İskeleti + Etiket Duvarı + Soru Kütüphanesi)
bookmaker_ref: UNKNOWN_BOOKMAKER_REF
Kart Durumu: FAZ-1_SKELETON_ACTIVE
Kart Politikası: Tek bookmaker_ref / Sıfırlanmaz / Market bağımsız büyür / Reference ile bağlanır / Unmapped korunur
Üretim Notu: Bu teslim yalnız iskelet üretimidir. Reference_dictionary ve odds akışları Faz-2 doğrulama ve doldurma içindir. Veri yokken hiçbir alan boş bırakılmaz; unknown/none/inactive bantları deterministik kullanılır.

BAHİS ŞİRKETİ KARTI — TAM PROFİL (FAZ-1 İSKELET) Kimlik Rafı
bookmaker_ref: UNKNOWN_BOOKMAKER_REF brand_name: unknown,short_name_alias: unknown,name_variants: none,website_domain_band: unknown,headquarters_country_ref: unknown,operating_countries_refs: none,license_status_band: unknown,identity_status: unknown
Kaynak ve Entegrasyon Rafı,data_provider_ref: unknown,feed_schema_version: unknown,odds_format_type: unknown,timezone_handling_band: unknown,schema_consistency_band: unknown,provider_dependency_band: unknown,system_latency_band: unknownodds_history_integrity_band: unknown
Kapsam ve Ürün Rafı,coverage_strength_by_league: unknown,market_depth_band: unknown,inactive_market_pattern: unknown,event_coverage_gap_band: unknown,opening_odds_availability_band: unknown,inplay_coverage_band: unknown
Oran Davranış DNA Rafı,update_speed_band: unknown,opening_timing_band: unknown,reaction_speed_to_news_band: unknown,volatility_band: unknown,late_move_tendency_band: unknown,revert_behavior_band: unknown,line_vs_price_shift_preference: unknown,cross_market_consistency_band: unknown,repeat_bias_pattern_band: unknown
Fiyatlama ve Marj Rafı,margin_band: unknown,margin_variation_by_league: unknown,competitiveness_band: unknown,market_leader_band: unknown,reference_weight_band: unknown
Bias ve Profil Rafı (Sadece Ölçüm),underdog_pricing_bias_band: unknown,favorite_pricing_bias_band: unknown,home_advantage_bias_band: unknown,totals_line_aggressiveness_band: unknown,handicap_line_shift_band: unknown,cards_line_bias_band:unknown,corners_line_bias_band: unknown
Canlı Bahis Davranışı Rafı,inplay_aggressiveness_band: unknown,suspension_tendency_band: unknown,inplay_suspend_pattern_band: unknown,dialogue_freeze_behavior_band: unknown
Anomali ve Kalite Rafı,data_quality_badge: low,missing_odds_frequency_band: unknown,anomaly_spike_frequency_band: unknown,source_outlier_tendency_band: unknown,coverage_map:,identity: unknown,integration: unknown,coverage: unknown,odds_behavior: unknown,pricing_margin: unknown,bias_profile: unknown,play: unknown,anomaly_quality: unknown
Etik ve Uyumluluk Rafı,integrity_risk_profile: unknown,disciplinary_case_history: none,service_restriction_history: none,allegation_strength: none,investigation_status_band: unknown,Kural: Yargı kurulmaz; yalnız doğrulanmış dosya/kayıt varsa işlenir. Belirsiz iddia weak_signal bandında tutulur.,Bağlantılar (informed_by),informed_by:,odds_market_timeline: none,market_library_refs: none,team_refs: none,match_refs: none,kural: Bağlantı serbest metinle kurulmaz; Faz-2’de reference_dictionary üzerinden bağlanır.

BAHİS ŞİRKETİ ETİKET DUVARI 
(FAZ-1 DETERMINİSTİK SÖZLÜK ALANLARI)
Bantlar ve Durum Etiketleri,unknown: veri yok / doğrulanmadı,none: alan geçerli ama içerik yok (kayıt yok),inactive: kaynak var ama şu an aktif değil,unmapped: reference_dictionary eşleşmesi yok, zorla eşleme yapılmadı,weak_signal: tekil veya zayıf kaynak sinyali
strong_signal: yalnız çoklu kaynak teyidi ile açılır
Kimlik Etiketleri,identity_status: unknown | verified,license_status_band: unknown | licensed | restricted | unlicensed
Entegrasyon Etiketleri,timezone_handling_band: unknown | correct | inconsistent,schema_consistency_band: unknown | stable | unstable,provider_dependency_band: unknown | low | medium | high,system_latency_band: unknown | low | medium | high
odds_history_integrity_band: unknown | low | medium | high,Kapsam Etiketleri,market_depth_band: unknown | low | medium | high,inactive_market_pattern: unknown | low | medium | high,event_coverage_gap_band: unknown | low | medium | high,opening_odds_availability_band: unknown | low | medium | high,inplay_coverage_band: unknown | low | medium | high
Oran Davranış Etiketleri,update_speed_band: unknown | slow | medium | fast,opening_timing_band: unknown | early | normal | late,reaction_speed_to_news_band: unknown | slow | medium | fast,volatility_band: unknown | low | medium | highlate_move_tendency_band: unknown | low | medium | high,line_vs_price_shift_preference: unknown | line_shift | price_shift | mixed | unknown,cross_market_consistency_band: unknown | low | medium | high,repeat_bias_pattern_band: unknown | low | medium | high
Fiyatlama Etiketleri,margin_band: unknown | low | medium | high,margin_variation_by_league: unknown | low | medium | high,competitiveness_band: unknown | low | medium | high,market_leader_band: unknown | low | medium | high,reference_weight_band: unknown | low | medium | high,Bahis Etiketleri (Sadece Ölçüm),underdog_pricing_bias_band: unknown | low | medium | high,favorite_pricing_bias_band: unknown | low | medium | high,home_advantage_bias_band: unknown | low | medium | high,totals_line_aggressiveness_band: unknown | low | medium | high,handicap_line_shift_band: unknown | low | medium | high,cards_line_bias_band: unknown | low | medium | high,corners_line_bias_band: unknown | low | medium | high
Canlı Bahis Etiketleri,inplay_aggressiveness_band: unknown | low | medium | high,suspension_tendency_band: unknown | low | medium | high,inplay_suspend_pattern_band: unknown | low | medium | high,dialogue_freeze_behavior_band: unknown | low | medium | high
Anomali ve Kalite Etiketleri,data_quality_badge: low | medium | high,missing_odds_frequency_band: unknown | low | medium | high,anomaly_spike_frequency_band: unknown | low | medium | high,source_outlier_tendency_band: unknown | low | medium | high
Etik ve Risk Etiketleri,allegation_strength: none | weak_signal | strong_signal,investigation_status_band: none | ongoing | closed_no_action | sanctioned | unknown,integrity_risk_profile: unknown | low | medium | high

BAHİS ŞİRKETİ SORU KÜTÜPHANESİ (FAZ-1 GENİŞ TARAMA SETİ)
Bu bahis şirketinin bookmaker_ref kimliği tekil mi, isim varyantları ve marka uzantıları var mı?
Bu firmanın faaliyet ülkeleri ve lisans kapsamı nedir; country_ref ile nasıl bağlanır?
Bu firmanın odds güncelleme sıklığı genel olarak hızlı mı yavaş mı; update_speed_band nasıl atanır?
Oran açılışı erken mi geç mi gelir; opening_timing_band nasıl işaretlenir?
Oran hareketi keskin mi yumuşak mı; volatility_band nasıl ölçülür?
Oranları “piyasa öncüsü” mü yoksa “piyasayı takip eden” mi; market_leader_band nasıl atanır?

Bu firma hangi liglerde daha güçlü kapsam sunuyor; coverage_strength_by_league nasıl tutulur?
Hangi market türlerinde daha derin (çok seçenek) veriyor; market_depth_band nasıl ölçülür?
Bazı marketleri sistematik olarak pasif mi bırakıyor; inactive_market_pattern var mı?
Bazı maçlarda oranı “kilitleme/kapama” eğilimi yüksek mi; suspension_tendency_band nasıl atanır?
Sakatlık/ilk11 haberi gibi tetiklerde oranı erken mi tepki verir geç mi; reaction_speed_to_news_band nasıl ölçülür?
Canlı bahis sırasında oran davranışı agresif mi temkinli mi; inplay_aggressiveness_band nasıl işaretlenir?

Bu firma “risk azaltma” için çizgiyi (line) hızlı mı kaydırır yoksa fiyatı mı oynatır; line_vs_price_shift_preference nasıl tutulur?
Marj seviyesi (overround) genel olarak yüksek mi düşük mü; margin_band nasıl ölçülür?
Marj bazı liglerde artıyor mu; margin_variation_by_league bandı gerekir mi?
Rakip firmalara göre sürekli “daha düşük oran” mı veriyor, yoksa rekabetçi mi; competitiveness_band nasıl atanır?
Piyasa kapanışına doğru fiyatları stabilize ediyor mu yoksa son dakika kırılıyor mu; late_move_tendency_band nasıl tutulur?
Aynı maçta farklı marketlerde (1X2 vs O/U vs BTTS) tutarsızlık var mı; cross_market_consistency_band nasıl ölçülür?

Aynı ligde benzer maçlarda sistematik sapma veriyor mu; repeat_bias_pattern_band gerekir mi?
Underdog’a yüksek mi düşük mü davranıyor; underdog_pricing_bias_band nasıl atanır?
Favori fiyatlamasında aşırı temkinli mi; favorite_pricing_bias_band nasıl atanır?
Ev sahibi avantajını fiyatlarken piyasa ortalamasından sapıyor mu; home_advantage_bias_band nasıl ölçülür?
Gol çizgilerini (O/U) agresif mi açıyor; totals_line_aggressiveness_band nasıl atanır?
Kart marketinde (varsa) çizgiler normalden farklı mı; cards_line_bias_band nasıl tutulur?

Korner marketinde (varsa) çizgiler daha mı yüksek/düşük; corners_line_bias_band nasıl tutulur?
Handikap marketinde (AH) çizgi kaydırma eğilimi var mı; handicap_line_shift_band nasıl tutulur?
Bu firma belirli saatlerde sistematik gecikme yaşıyor mu; system_latency_band gerekir mi?
Veri kaybı / missing odds olayı sık mı; data_quality_badge bookmaker seviyesinde tutulmalı mı?
Bu firmanın oranları diğerlerine göre daha “güvenilir referans” mı; reference_weight_band nasıl atanır?
Bu firmada anormal oran sıçramaları sık mı; anomaly_spike_frequency_band nasıl ölçülür?

Anormal oran sıçraması olduğunda geri düzeltme (revert) oluyor mu; revert_behavior_band nasıl tutulur?
Bu firma bazı maçları listelemiyor mu; event_coverage_gap_band gerekir mi?
Canlı bahiste market kapatma açma paterni var mı; inplay_suspend_pattern_band nasıl tutulur?
Aynı maçın farklı saatlerinde odds_history bütünlüğü korunuyor mu; odds_history_integrity_band nasıl işaretlenir?
Bu firma odds verisini hangi formatta sağlıyor; schema_consistency_band nasıl tutulur?
Bookmaker ile kaynak sağlayıcı (provider) aynı mı farklı mı; provider_dependency_band gerekir mi?

Lisans/uyumluluk riski geçmişi var mı; integrity_risk_profile nasıl bandlanır?
Resmi yaptırım veya erişim kesintisi yaşandı mı; investigation_status_band gibi bantlar gerekir mi?
Fiyatlama “şüpheli” diye hüküm kurmadan, yalnız sapma ölçümüyle nasıl işaretlenecek?
Bu firmanın canlı bahis akışında market kapatıp açma kararları “piyasa geneliyle” aynı mı farklı mı; source_outlier_tendency_band buna göre mi tutulmalı?
Bu firmanın odds açılışında “korumacı” davranıp sonradan hızlanma paterni var mı; opening_to_mid_game_shift_band gerekir mi?
Bu firmanın kapanış fiyatı (closing line) piyasa ortalamasından sistematik sapıyor mu; closing_bias_band nasıl ölçülmeli?
Kapanış Notu: Bahis Şirketi Kartı — tamamlandı / dosyalanabilir çıktı


MARKET KÜTÜPHANESİ — FAZ-1 TESLİMİ 
(30 ANA MARKET / Kart + Etiket Duvarı + Soru Kütüphanesi)
library_ref: FOOTBALL_MARKET_LIBRARY_V1
Kart Durumu: FAZ-1_SKELETON_ACTIVE
Kart Politikası: Market listesi deterministik ve sabittir / Her market market_ref ile yaşar / İsimler serbest metin değildir / Provider map ile bağlanır / Unmapped korunur / Eksik veri inactive/unknown bantlarıyla taşınır
Üretim Notu: Bu teslim yalnız ana market rafını kurar. Odds akışı ve BOOKMAKER_ALLOWLIST Faz-2’de marketlere bağlanır. Bu kütüphane bahis önerisi üretmez; yalnız zaman hizası ve bant sapması ölçer.

FAZ-34  BAHİS / ODDS DAVRANIŞI SORULARI (FUTBOL) — MAÇ ÖNCESİ + MAÇ SAATİ + MAÇ İÇİ

Bu bölümün amacı odds verisini “tahmin” için kullanmak değildir. Amaç, piyasa davranışının normal banttan sapıp sapmadığını, sapıyorsa bunun maç içi tetikleyicilerle ve haber penceresiyle hangi şartlarda kesiştiğini deterministik biçimde işaretlemektir. Odds hareketi hüküm değildir; kanıt zincirinin yalnızca bir parçası olabilir.
Bu odds kaydı hangi maç kimliğine ve hangi UTC zaman penceresine bağlanıyor? Bu soru, odds zaman hizasını kilitler. Zaman hizası bozuksa aynı odds hareketi yanlış maça yazılabilir.
Odds snapshot penceresi nasıl tanımlandı ve pencereler deterministik mi? Bu soru, odds örüntüsünün doğru kıyaslanması içindir. Snapshot aralığı kayarsa bant okuması bozulur.
Bu odds kaydı hangi bookmaker’lara aittir ve allowlist içinde midir? Bu soru, veri kaynağını kilitler. Allowlist dışı bookmaker verisi rafı kirletmez, dışarıda kalır.

Bu maç için hangi market setleri zorunlu izlendi ve market kapsamı boşluk bırakmadan kaydedildi mi? Bu soru, izlenen alanın deterministik olmasını sağlar. Market kapsamı değişirse iki maç kıyaslanamaz.
Maç öncesi odds çizgisi sabit mi kaldı yoksa keskin kırılma yaşadı mı? Bu soru, normal bant ile sapma arasını ayırır. Keskin kırılma varsa zaman damgası şarttır.
Keskin kırılma tek bir bookmaker’da mı yoksa birden fazla bookmaker’da mı oluştu? Bu soru, tek kaynak sapması ile piyasa geneli sapmasını ayırır. Tekil sapma daha düşük güven sınıfıdır.
Odds hareketi maç saatine yaklaştıkça mı hızlandı yoksa günler önceden mi başladı? Bu soru, hareketin zaman doğasını ölçer. Erken başlayan hareket farklı, son dakika hareketi farklı sınıfa yazılır.
Maç saatinden önce odds hareketi “yumuşak akış” mı yoksa “kademeli sert kayma” mı gösterdi? Bu soru, piyasadaki yön değişiminin hız profilini çıkarır. Hız profili, sapma kalitesini belirler.
Odds hareketi maçın hangi segmentinde yoğunlaştı (ilk 15, devre, son 15)? Bu soru, odds değişimini segment okumasına bağlar. Segment eşleşmesi yoksa olay-kaynak bağlantısı zayıftır.
Maç içi odds hareketi, maç içi tetikleyicilerle açıklanabiliyor mu yoksa tetikleyici olmadan mı oluştu? Bu soru, “olay yokken hareket” durumunu işaretler. Bu bir suçlama değildir; sadece anomali sapma adaydır.
Kart, VAR, penaltı, kırmızı kart gibi kader tetikleyicileri ile odds hareketi aynı zaman bandında mı çakıştı? Bu soru, piyasaya yansıyan maç içi kırılmaları yakalar. Çakışma varsa işaretlenir, hüküm kurulmaz.

Odds hareketi iç saha/deplasman bağlamında tekrar ediyor mu? Bu soru, takımın ev-deplasman DNA’sının piyasa davranışına yansıyıp yansımadığını ölçer.
Odds hareketi takımın seri davranışıyla ilişkili mi (galibiyet serisi, mağlubiyet serisi) Bu soru, takımın sonuç hafızasının piyasa tarafından nasıl fiyatlandığını ölçer.
Odds hareketi kritik oyuncu yokluğu, ceza sınırı veya kondisyona dair bağlamla eşleşiyor mu? Bu soru, bağlam duvarıyla odds davranışını birleştirir. Eşleşme varsa sapma adayı güçlenir.
Bu maçın odds örüntüsü, aynı takımın benzer bağlamlı geçmiş maçlarına göre normal bant içinde mi dışında mı? Bu soru, karşılaştırmayı mümkün kılar. Bant tanımı yoksa sapma işaretlenemez.
Odds verisi eksik mi, parçalı mı, rate-limit nedeniyle degrade mi ve data\\\_quality\\\_badge ne? Bu soru, “anomali yok” ile “veri eksik” ayrımını korur. Eksik veri varsa hüküm kurulmaz.
Bu odds kaydı bir sonraki cycle’da aynı şekilde doğrulanabiliyor mu? Bu soru, tek seferlik veri hatasıyla gerçek piyasa hareketini ayırır. Tekrar yoksa düşük güven sınıfıdır

Bu bookmaker’ın sapma/anomali davranışı en çok hangi ülke liglerinde kümeleniyor? Bu soru, tek maç sapmasını “piyasa profiline” bağlar. Bazı bookmaker’lar belirli ülke liglerinde daha sık kırılma üretebilir; bu bir kanıt değildir ama analiz refleksini hızlandıran bir risk haritasıdır.
Bu bookmaker’ın sapma davranışı organizasyon tipine göre değişiyor mu (lig, ulusal kupa, kıtasal kupa)? Bu soru, sapmanın maç türüne göre sistematikleşip sistematikleşmediğini ayırır. Kupa bağlamında daha sık kırılma görülüyorsa bu ayrı 
band olarak işlenir.

Bu bookmaker’ın sapma davranışı dönemsel mi, sabit mi, rotasyonlu mu? Bu soru, senin tarif ettiğin “bir ay Asya, bir ay başka bölge” davranışını yakalar. Rastgele görünen sapmaların dönemsel haritası olup olmadığı burada ortaya çıkar.
Bookmaker sapmaları belirli haftalarda veya sezon fazlarında artıyor mu (sezon başı/sonu, transfer dönemi, yoğun fikstür)? Bu soru, sapmayı sezon fazı bağlamına bağlar. Bazı sapmalar sezon geçişlerinde artabilir.
Bu bookmaker’ın sapması “maç öncesi”, “maç saatine yakın” veya “maç içi” hangi pencerede daha çok oluşuyor? Bu soru, sapmanın zaman tipini sınıflar. Zaman tipi, sapma yorumunun yönünü değiştiren bir ana anahtardır.
Bu ligde aynı maç için farklı bookmaker’lar arasında sistematik ayrışma var mı? Bu soru, tek bookmaker sapması ile piyasa geneli ayrışmayı ayırır. Ayrışma tekrar ediyorsa lig bazlı piyasa davranışı işaretlenir.
Bu takımın maçlarında belirli bookmaker sapmaları tekrar ediyor mu? Bu soru, bookmaker profili ile takım profili kesişimini yakalar. Tekrar varsa “takım+bookmaker” eşleşmesi raf nesnesi olur.
Bu bookmaker için “normal bant” ve “sapma bandı” geçmiş veriden çıkarılabiliyor mu? Bu soru, sapmanın ölçülebilir hale gelmesi içindir. Bant tanımı yoksa sapma yalnız his olur; sistem bunu kabul etmez.
Bu bookmaker’ın veri bütünlüğü ve veri kalitesi (eksik snapshot, gecikme, tutarsızlık) sapma gibi görünüyor olabilir mi? Bu soru, veri hatasını sapma sanma riskini engeller. Önce veri kalitesi ayrımı yapılır, sonra sapma işaretlenir.

ÇAPRAZ KAYNAK OKUMA SORULARI (FUTBOL) — BASIN + ODDS + MAÇ İÇİ TETİKLEYİCİLER

,Bu bölümün amacı, üç ayrı hattı aynı anda “sonuç çıkarma” için birleştirmek değildir. Amaç, basın akışı, odds hareketi ve maç içi tetikleyiciler arasında tekrar eden zaman hizası ve davranış eşleşmesi olup olmadığını deterministik biçimde test etmektir. Bu bölüm, hüküm vermez; yalnız eşleşme ve eşleşmeme haritasını çıkarır. Kanıt zinciri tamamlanmadan hiçbir birim sonuç dili kuramaz.
Bu maç için basın haber temaları ile odds hareketinin zaman penceresi çakışıyor mu? Bu soru, “haber çıktı → piyasa hareket etti” gibi bir iddiayı test edilebilir hale getirir. Çakışma yoksa ilişki zayıf kabul edilir.

Basın haber temaları ile odds hareketi çakışıyorsa çakışma tek bookmaker’da mı yoksa birden çok bookmaker’da mı görülüyor? Bu soru, tekil kaynak sapmasını piyasa geneli sapmadan ayırır. Tekil sapma düşük güven sınıfıdır.
Basın haber temaları ile odds hareketi çakışıyorsa çakışma hangi lig/organizasyon sınıfında daha sık görülüyor? Bu soru, çapraz eşleşmenin ülke/lig bazında kümelenip kümelenmediğini ölçer. Kümelenme varsa harita çıkar.
Basın haber temaları ile odds hareketi çakışıyorsa bu çakışma dönemsel mi sabit mi rotasyonlu mu? Bu soru, rastgele görünen davranışın dönemsel haritası olup olmadığını test eder. Rotasyon varsa not edilir.
Basın haber temaları ile odds hareketi çakışıyorsa bu çakışma sezon fazına göre artıyor mu (sezon başı/sonu, transfer dönemi)? Bu soru, “geçiş dönemleri” etkisini ölçer. Bazı çapraz eşleşmeler sezon geçişlerinde artabilir.

Odds hareketi maç içi kader tetikleyicilerinden önce mi başladı yoksa tetikleyiciden sonra mı yoğunlaştı? Bu soru, zaman yönünü belirler. Tetikleyici sonrası hareket normal bant olabilir; tetikleyici öncesi hareket sapma adayını güçlendirir.
Odds hareketi tetikleyici olmadan oluşuyorsa bu hareket maç içi segment davranışında bir değişimle eşleşiyor mu? Bu soru, “olay yok ama davranış kaydı var” senaryosunu yakalar. Segment DNA değişiyorsa bu ayrıca işaretlenir.
Maç içi tetikleyicilerden hangileri odds hareketiyle en sık çakışıyor (kırmızı kart, VAR, penaltı, iptal gol)? Bu soru, piyasanın en hassas olduğu tetikleyici sınıfları çıkarır. Bu bir tahmin aracı değil, örüntü haritasıdır.
Maç içi tetikleyiciler ile basın temaları aynı hafta penceresinde eşleşiyor mu? Bu soru, basının tetikleyici üretip üretmediğini değil, basın konuştuğu şeyle maç içinin kesişip kesişmediğini test eder.
Basın teması “hakem/adalet” ise maç içi kart ve VAR tetikleyicileriyle eşleşme bandı artıyor mu? Bu soru, tematik eşleşmeyi test eder. Eşleşme varsa yalnız işaretlenir, hüküm kurulmaz.
Basın teması “sakatlık/eksik” ise maç içi segmentlerde kondisyon düşüşü veya tempo kırılmasıyla eşleşme var mı? Bu soru, haber bağlamının sahaya yansıyıp yansımadığını ölçer.
Basın teması “transfer/kriz/yönetim” ise maç içi disiplin bandında kart yoğunluğu artıyor mu? Bu soru, haber-temelli baskının disipline yansıma ihtimalini test eder. Tek seferlikte hüküm yoktur, tekrar aranır.

Bu eşleşmeler takım bazında mı kümeleniyor yoksa lig bazında mı kümeleniyor? Bu soru, yapının nerede olduğunu ayırır. Takım bazlıysa takım DNA’sına, lig bazlıysa lig davranışına yazılır.
Bu eşleşmeler bookmaker bazında mı kümeleniyor yoksa piyasa geneline mi yayılıyor?nBu soru, sapmanın kaynak sınıfını belirler. Bookmaker profili ayrı raf nesnesidir.
Bu eşleşmeler belirli yazar/editör kaynaklarında mı yoğunlaşıyor? Bu soru, haber kaynağı güven haritasını çapraz hatla birleştirir. Aynı yazarın haberleriyle eşleşme yüksekse işaretlenir.
Bu eşleşmelerde tekrar eden bir “tetikleyici sırası” var mı (haber tonu → odds kayması → kart/VAR → tempo kırılması)? Bu soru, zincir şeması çıkarır. Zincir şeması varsa bu yalnız örüntüdür, hüküm değildir.
Bu eşleşmelerde “anomali yok” durumunda da normal bant korunuyor mu? *Bu soru, sistemin en kritik ilkesini korur: anomali çıkmaması da bir sonuçtur. Normal bant korunuyorsa bu bilgi raflara yazılır.
Bu eşleşmelerde veri eksikliği veya kalite düşüşü var mı ve “anomali yok” ile karışıyor mu? Bu soru, data\\\_quality ayrımını çapraz okuma içinde de korur. Eksik veri varsa eşleşme hükmü kurulmaz.

FAZ-19 BOOKMAKER BÖLÜMÜ-2
MARKET KÜTÜPHANESİ — 30 ANA MARKET (DETERMINİSTİK LİSTE)
market_ref: FT_MKT_001,market_name: 1X2 (Match Result),market_group: core_result,required_fields: home_price | draw_price | away_price,status: active,market_ref: FT_MKT_002,market_name: Double Chance,market_group: core_result,required_fields: 1X_price | 12_price | X2_price,status: active,market_ref: FT_MKT_003,market_name: Draw No Bet,market_group: core_result,required_fields: home_price | away_price,status: active,market_ref: FT_MKT_004,market_name: Asian Handicap,market_group: handicaprequired_fields: line | home_price | away_price,status: active,market_ref: FT_MKT_005,market_name: European Handicap,market_group: handicap,required_fields: line | home_price | away_price,status: active,market_ref: FT_MKT_006,market_name: Over/Under 0.5 Goals,market_group: totals,required_fields: line | over_price | under_price,status: active,market_ref: FT_MKT_007,market_name: Over/Under 1.5 Goals,market_group: totals,required_fields: line | over_price | under_price,status: active,market_ref: FT_MKT_008,market_name: Over/Under 2.5 Goals,market_group: totals,required_fields: line | over_price | under_price,status: active

market_ref: FT_MKT_009,market_name: Over/Under 3.5 Goals,market_group: totals,required_fields: line | over_price | under_price,status: active,market_ref: FT_MKT_010,market_name: Over/Under 4.5 Goals,market_group: totals,required_fields: line | over_price | under_price
status: active,market_ref: FT_MKT_011,market_name: Both Teams To Score (BTTS),market_group: goals_btts,required_fields: yes_price | no_price,status: active,market_ref: FT_MKT_012,market_name: BTTS + Match Result,market_group: comborequired_fields:,combinations_price_map,status: active,market_ref: FT_MKT_013,market_name: Correct Score,market_group: score,required_fields: score_price_map,status: active,market_ref: FT_MKT_014,market_name: Half Time Result,market_group:,halftime,required_fields: home_price | draw_price | away_price,status: active,market_ref: FT_MKT_015,market_name: Half Time / Full Time,market_group: combo,required_fields: combinations_price_map,status: active,market_ref: FT_MKT_016market_name: Team Total Goals,market_group: team_totals,required_fields: team_side | line | over_price | under_price,status: active,market_ref: FT_MKT_017,market_name: First Team To Score,market_group: goals_timing,required_fields: home_price | away_price | no_goal_pricestatus: active,market_ref: FT_MKT_018,market_name: Last Team To Score,market_group: goals_timing,required_fields: home_price | away_price | no_goal_price,status: active

market_ref: FT_MKT_019,market_name: Next Goal,market_group: inplay_goals,required_fields: home_price | away_price | no_goal_price,status: active,,market_ref: FT_MKT_020,market_name: Anytime Goalscorer,market_group: player_goalsrequired_fields: player_ref | yes_price,status: active,market_ref: FT_MKT_021,market_name: First Goalscorer,market_group: player_goals,required_fields: player_ref | yes_pricestatus: activ,market_ref: FT_MKT_022,market_name: Player Shots,market_group: player_shots,required_fields: player_ref | line | over_price | under_price,status: active,market_ref: FT_MKT_023,market_name: Player Shots on Target,market_group: player_shots,required_fields: player_ref | line | over_price | under_price,status: active,,market_ref: FT_MKT_024market_name: Total Cornersmarket_group: corners,required_fields: line | over_price | under_price,status: active,market_ref: FT_MKT_025,market_name: Asian Corners,market_group: cornersrequired_fields: line | home_price | away_price,status: active,market_ref: FT_MKT_026,market_name: Team Corners,market_group: corners,required_fields: team_side | line | over_price | under_price,status: active,market_ref: FT_MKT_027,market_name: Total Cards,market_group: cards,required_fields: line | over_price | under_price,status: active,market_ref: FT_MKT_028,market_name: Player Cards
market_group: player_cards,required_fields: player_ref | yes_price,status: active,market_ref: FT_MKT_029,market_name: Penalty Awarded,market_group: penalties,required_fields: yes_price | no_pricestatus: active,market_ref: FT_MKT_030,market_name: Red Card,market_group: cards,required_fields: yes_price | no_price,status: active

MARKET ETİKET DUVARI  (FAZ-1 DETERMINİSTİK),unknown: veri yok / doğrulanmadı,none: alan geçerli ama içerik yok,inactive: kaynak var ama aktif değil,unmapped: provider eşleşmesi yok,active: takipte,market_group: core_result | handicap | totals | goals_btts | combo | score | halftime | team_totals | goals_timing | inplay_goals | player_goals | player_shots | corners | cards | player_cards | penalties,market_status: active | inactive,required_fields_completeness: low | medium | high,provider_mapping_status: unmapped | mapped,odds_update_speed_band: unknown | slow | medium | fastmarket_latency_band: unknown | low | medium | high

MARKET SORU KÜTÜPHANESİ (FAZ-1)
Bu market provider akışında hangi isimle geliyor ve market_ref’e nasıl maplenecek?
Bu marketin required_fields alanları tam geliyor mu; eksikler nasıl bandlanacak?
Bu market canlıda aktif mi yoksa pre-match ile mi sınırlı; status nasıl tutulacak?
Bu marketin odds güncelleme hızı hangi bandda; slow/fast ayrımı nasıl yapılacak?
Bookmakerlar arası aynı markette sapma ölçümü hangi eşikle “anomali” sayılacak?
Bu markette line değişiyor mu yoksa fiyat mı değişiyor; line_vs_price_shift nasıl izlenecek?
Market pasifse inactive mi none mı; hangi koşulda hangisi seçilecek?
Yan market (alt tahta) geldiğinde bu market kütüphanesine mi, yoksa extended rafına mı girecek?
Kapanış Notu: Market Kütüphanesi (30 Ana Market) — tamamlandı / dosyalanabilir çıktı

FAZ-20: ALT TAHTA MARKET KÜTÜPHANESİ — FAZ-1 TESLİMİ  (Niş / Extended Markets) Bu, 30 ana marketin üstüne ek bir kütüphane katmanı gibi çalışır.,library_ref: FOOTBALL_EXTENDED_MARKET_LIBRARY_V1,Kart Durumu: FAZ-1_SKELETON_ACTIVE,Kart Politikası: Alt tahta marketler deterministik raflarda tutulur / Her market market_ref ile yaşar / Provider map ile bağlanır / Unmapped korunur / Eksik veri inactive/unknown bantlarıyla taşınır / Bu kütüphane bahis önerisi üretmez, yalnız sapma ve iz ölçer,Üretim Notu: Bu raf “veri gelsin gelmesin” kütüphanede hazır durur. Provider kapsamı yoksa inactive_market olarak işaretlenir.

ALT TAHTA MARKETLER — GENİŞ RAF LİSTESİ (DETERMINİSTİK),market_ref: FT_XMKT_001,market_name: Goal Time Bands (Gol Zaman Aralığı),market_group: goal_timing_bands,required_fields: band_window | yes_price | no_price,status: inactive,market_ref: FT_XMKT_002
market_name: Goal In Both Halves,market_group: goal_timing_bands,required_fields: yes_price | no_price,status: inactiv,market_ref: FT_XMKT_003,market_name: First Half Over/Under (0.5/1.5/2.5),market_group: halftime_totals,required_fields: line | over_price | under_price,status: inactive,market_ref: FT_XMKT_004,market_name: Second Half Over/Under (0.5/1.5/2.5),market_group: secondhalf_totals,required_fields: line | over_price | under_price,status: inactive,market_ref: FT_XMKT_005,market_name: Team To Score In Both Halves
market_group: team_goal_timing,required_fields: team_side | yes_price | no_price,status: inactive,market_ref: FT_XMKT_006,market_name: Clean Sheet,market_group: team_defense,required_fields: team_side | yes_price | no_price,status: inactive,market_ref: FT_XMKT_007
market_name: Win To Nil,market_group: combo,required_fields: team_side | yes_price | no_price,status: inactive,market_ref: FT_XMKT_008,market_name: Draw No Bet (Half-Time),market_group: halftime_result,required_fields: home_price | away_price,status: inactive
market_ref: FT_XMKT_009,market_name: Exact Goals (0/1/2/3/4/5+),market_group: exact_totals,required_fields: goal_count_price_map,status: inactive,,market_ref: FT_XMKT_010,market_name: Total Goals Odd/Even,market_group: totals_parity,required_fields: odd_price | even_price,status: inactive,market_ref: FT_XMKT_011,market_name: Team Total Goals (Exact),market_group: team_exact_totals,required_fields: team_side | goal_count_price_map,status: inactive,market_ref: FT_XMKT_012market_name: Winning Margin,market_group: margin,required_fields: margin_price_map,status: inactive,market_ref: FT_XMKT_013,market_name: To Win Either Half,market_group: halves_combo,required_fields: team_side | yes_price | no_price,status: inactive,market_ref: FT_XMKT_014,market_name: Result + Total Goals,market_group: combo,required_fields: combinations_price_map,status: inactive,market_ref: FT_XMKT_015,market_name: Result + Both Teams To Score,market_group: combo,required_fields: combinations_price_mapstatus: inactive market_ref: FT_XMKT_016,market_name: Time of First Goal,market_group: goal_timing_precision,required_fields: time_band_price_map,status: inactive,market_ref: FT_XMKT_017,market_name: Time of Last Goal,market_group: goal_timing_precision,required_fields: time_band_price_map,status: inactive,market_ref: FT_XMKT_018,market_name: No Goal,market_group: goals_btts,required_fields: yes_price | no_price,status: inactive,market_ref: FT_XMKT_019,market_name: Team To Score First + Match Result,market_group: combo,required_fields: combinations_price_map,status: inactive

market_ref: FT_XMKT_020,market_name: Penalty Missed,market_group: penalties,required_fields: yes_price | no_price,status: inactive,market_ref: FT_XMKT_021,market_name: VAR Review Occurs,market_group: var,required_fields: yes_price |no_price,statusin,active,market_ref: FT_XMKT_022,market_name: VAR Decision Overturned,market_group: var,required_fields: yes_price | no_price,status: inactive,market_ref: FT_XMKT_023,market_name: Offside Count (Team/Total),market_group: offsides,required_fields: side_or_total | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_024,market_name: Throw-Ins Count (Team/Total),market_group: throwins,required_fields: side_or_total | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_025,market_name: Goal Kicks Count (Team/Total)
market_group: goalkicks,required_fields: side_or_total | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_026,market_name: Free Kicks Count (Team/Total),market_group: freekicks,required_fields: side_or_total | line | over_price | under_pricestatus: inactive,market_ref: FT_XMKT_027,market_name: Fouls Count (Team/Total),market_group: fouls,required_fields: side_or_total | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_028,market_name: Shots (Team/Total),market_group: shots,required_fields: side_or_total | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_029,market_name: Shots On Target (Team/Total),market_group: shots,required_fields: side_or_total  line | over_price  under_price,status: inactive,market_ref: FT_XMKT_030,market_name: Saves (Goalkeeper),market_group: goalkeeper,required_fields: player_ref | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_031,market_name: Player To Be Booked (Card),market_group: player_cards,required_fields: player_ref | yes_price,status: inactive,market_ref: FT_XMKT_032,market_name: Player Fouls Committed,market_group: player_fouls,required_fields: player_ref | line | over_price | under_price,status: inactive,market_ref:FT_XMKT_033,market_name:PlayerTackles,market_group.player_defense,required_fields: player_ref | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_034,market_name: Player Assists,market_group: player_assists,required_fields: player_ref | yes_price,status: inactive,market_ref: FT_XMKT_035,market_name: Player Passes (Total/Accurate),market_group: player_passing,required_fields: player_ref | line | over_price | under_price,status: inactive,market_ref: FT_XMKT_036,market_name: Player To Make a Shot On Target,market_group: player_shots,required_fields: player_ref | yes_pricestatus: inactive,market_ref: FT_XMKT_037,market_name: Corners Race (First to X),market_group: corners,required_fields: target_count | home_price | away_price,status: inactive,market_ref: FT_XMKT_038,market_name: Cards Race (First to X),market_group: cards,required_fields: target_count | home_price | away_price,status: inactive,market_ref: FT_XMKT_039,market_name: Team Booking Points,market_group: cards,required_fields: team_side | line | over_price | under_price,status: inactive

market_ref: FT_XMKT_040,market_name: Booking Points Match Total,market_group: cards,required_fields: line | over_price | under_price,status: inactive,market_ref: FT_XMKT_041,market_name: First Card (Team/Player),market_group: cards,required_fields: entity_ref yes_price
status: inactive,market_ref: FT_XMKT_042,market_name: First Corner (Team),market_group: corners,required_fields: home_price | away_price | no_corner_price,status: inactive,market_ref: FT_XMKT_043,market_name: First Throw-In(Team),market_group:throwins,required_fields: home_price | away_pricestatus: inactive,market_ref: FT_XMKT_044,market_name: Next Card (In-Play),market_group: inplay_cards,required_fields: home_price | away_price | no_card_price,status: inactive,market_ref: FT_XMKT_045,market_name: Next Corner(InPlay),market_group: inplay_corners,required_fields: home_price | away_price | no_corner_price,status: inactive,market_ref: FT_XMKT_046,market_name: Next Offside (In-Play),market_group: inplay_offsides,required_fields: home_price | away_price | no_offside_price,status:inactive,market_ref: FT_XMKT_047,market_name: Player To Score 2+ Goals,market_group: player_goals,required_fields: player_ref | yes_price,status: inactive,market_ref: FT_XMKT_048market_name: Hat-trick Occurs,market_group: player_goals,required_fields: yes_price | no_price,status: inactive
market_ref: FT_XMKT_049,market_name: Own Goal Occurs,market_group: goals_misc,required_fields: yes_price | no_price,status: inactive,market_ref: FT_XMKT_050,market_name: Goal In Added Time,market_group: goal_timing_bands,required_fields: yes_price | no_price,status: inactive

FAZ-21:ALT TAHTA ETİKET DUVARI (FAZ-1 DETERMINİSTİK),unknown: veri yok / doğrulanmadı,none: alan geçerli ama içerik yok,inactive: provider yok veya market kapalı,unmapped: provider eşleşmesi yok,market_group: goal_timing_bands | halftime_totals | secondhalf_totals | team_goal_timing | team_defense | combo | halftime_result | exact_totals | totals_parity | team_exact_totals | margin | halves_combo | goal_timing_precision | penalties | var | offsides | throwins | goalkicks | freekicks | fouls | shots | goalkeeper | player_cards | player_fouls | player_defense | player_assists | player_passing | corners | cards | inplay_cards | inplay_corners | inplay_offsides | player_goals | goals_misc
market_status: active | inactive,required_fields_completeness: low | medium | high,provider_mapping_status: unmapped | mapped

ALT TAHTA SORU KÜTÜPHANESİ (FAZ-1)
Bu niş market provider akışında hangi isimle geliyor ve market_ref’e nasıl maplenecek?,Bu market “düşük hacimli / yüksek oranlı” davranış gösterebilir mi; anomaly_spike_risk bandı gerekir mi?,Ana marketlerde sapma yokken alt tahtada sapma oluşuyorsa bu “iz” olarak nasıl işaretlenecek?,Alt tahta markette line mı fiyat mı daha fazla oynuyor; line_vs_price_shift_preference nasıl tutulacak?,Bu markette suspension ve geri açılma paterni normal mi anormal mi; inplay_suspend_pattern nasıl ölçülecek?,Alt tahtada anomali görüldüğünde “kanıt” olarak hangi başka raflarla çapraz kontrol yapılacak; match_event mi basın mı yalnız odds mu?
Kapanış Notu: Alt Tahta Market Kütüphanesi — tamamlandı / dosyalanabilir çıktı
Basın Etiket Duvarı v1.0
ENUM SÖZLÜĞÜ v1.0
MATCH SUPPORT TRACE FIELDS v1.0.1

FAZ-22: BASIN BÖLÜMÜ
FUTBOL BASIN SORU KATALOĞU — ATOMİK GENİŞLETİLMİŞ KİLİTLİ LİSTE (v1.1),BÖLÜM A — HABER KAYDI / BAĞLAM KİMLİĞİ (HER HABERE ZORUNLU)

Bu bölümün amacı “haber var mı yok mu” kontrolü değildir. Amaç, haber akışını deterministik biçimde raflara ayırmak ve haberin maç içi davranışla, odds davranışıyla ve takım DNA’sıyla hangi şartlarda kesiştiğini ölçmektir. Haber, tek başına hüküm kurmaz; yalnız bağlam üretir ve kanıt zincirinin bir parçası olabilir. Bu yüzden haber akışı hem sezon içi hem sezon arası pencerede ayrı disiplinle kaydedilir.
Bu kayıt sezon içi maç haftası haber paketi mi yoksa sezon arası haftalık off-season paketi mi? Bu soru, haberin hangi pencere disipliniyle işlendiğini kilitler. Sezon arası haberleri günlük maç akışı gibi değil, haftalık paket olarak raflara yazılır.
Bu haber paketi hangi ülke, lig, sezon ve tekil takım adresine bağlanıyor? Bu soru, haberin doğru raf adresine düşmesi içindir. Yanlış bağlanan haber, beş yıl sonra yanlış DNA okuması üretir.
Bu haber paketi lig (Tier-1/Tier-2) akışına mı yoksa Cups akışına mı aittir? Bu soru, kupa haberlerinin lig haberine karışmasını engeller. Kupa bayrağı, haber seviyesinde de deterministik işlenir.
Bu haber paketi hangi organizasyon tipine aittir (lig, ulusal kupa, kıtasal kupa, milli takım)? Bu soru, haberin hangi stres sınıfını taşıdığını belirler. Organizasyon tipi belirlenmeden haber etkisi yanlış sınıfa yazılabilir.
Bu haber penceresi maçtan kaç gün öncesini kapsıyor (örnek: 7 gün) ve pencere sabit mi? Bu soru, haberin “zaman hizasını” kilitler. Pencere kayarsa aynı olay farklı maçlara yanlış bağlanır.

Maç öncesi haber akışında hangi temalar öne çıktı ve temalar kaç farklı kaynakta tekrar etti? Bu soru, tek kaynağın gürültüsü ile çoklu kaynağın tekrarını ayırır. Tekrar eden tema daha güçlü sinyal adayıdır.
Haber temaları daha çok hangi eksende kümelendi (yönetim, teknik direktör, oyuncu, hakem, taraftar, transfer, sakatlık, disiplin)? Bu soru, haberin hangi kart nesnesine bağlanacağını belirler. Tema yanlış karta bağlanırsa analiz yanlış kişiyi suçlar gibi görünür.
Haber tonu hangi bantta yoğunlaştı (olumlu, olumsuz, karma) ve ton aniden kırıldı mı? Bu soru, haberin duygusal iklimini adresler. Ton kırılması varsa maç içi davranış değişimiyle eşleşebilir.
Aynı olay farklı kaynaklarda aynı biçimde mi geçti yoksa kaynaklar arasında ayrışma var mı?

Bu soru, kaynak güven bandını ölçer. Ayrışma varsa “tek doğru” diye hüküm kurulmaz, yalnız işaretlenir.
Bu takımın haber akışı sezon içinde “rutin” mi yoksa “kriz/çalkantı” mı taşıyor? Bu soru, takımın baskı altında olup olmadığını belirler. Kriz akışı varsa maç içi tetikleyiciler daha sert çalışabilir.
Bu haber akışında transfer söylentileri var mı ve söylenti-gerçekleşme doğruluk bandı geçmişte nasıldı? Bu soru, haberin güvenilirliğini beş yıllık doğrulamayla ölçer. Transfer gürültüsü ile gerçek transfer ayrılır.
Sezon arası haftalık paketlerde kamp, kadro dışı kalanlar, rotasyon ve hazırlık maçları konuşuluyor mu? Bu soru, sezon arası bağlamı takım DNA’sına bağlar. Kamp ve kadro değişimleri sezon başlangıcı davranışını belirler.

Haber akışında kritik oyuncu sakatlığı veya dönüşü var mı ve bu bilgi maç segment davranışını etkiliyor mu? Bu soru, haber-temelli bağlamın saha içi gerçekliğe yansıyıp yansımadığını ölçer.
Haber akışı teknik direktör üzerinde baskı üretiyor mu ve bu baskı maç içinde erken hamle veya panik hamle doğuruyor mu? Bu soru, haberin teknik karar davranışına etkisini test eder.
Haber akışı taraftar baskısı içeriyor mu ve bu baskı iç saha davranışına yansıyor mu? Bu soru, tribün etkisinin haber üzerinden büyüyüp büyümediğini ölçer. Bazı baskılar saha içinde değil, haberle inşa edilir.
Maç sonrası haber akışı hangi temada devam etti ve maç öncesi anlatıyla uyumlu mu? Bu soru, haberin “sonuçla yeniden yazılma” riskini test eder. Maç sonrası eksen değişiyorsa bu not düşülür.
Maç sonrası haber akışı, bir sonraki maçın haber penceresinde tekrar eden bir yönlendirme oluşturuyor mu? Bu soru, zincir etkisini ölçer. Bazı haber döngüleri bir maçı değil, bir seri maçı etkiler.

Bu haber akışı ile maç içi kader tetikleyicileri aynı hafta içinde çakıştı mı? Bu soru, “haber etkisi” iddiasını test edilebilir hale getirir. Çakışma yoksa haber yalnız gürültü olabilir.
Bu haber akışı ile odds kırılmaları aynı zaman bandında mı ortaya çıktı? Bu soru, haber–piyasa davranışı ilişkisinin varlığını yokluğunu ölçer. Eşleşme varsa işaretlenir, hüküm kurulmaz.
Bu haber akışı ile takımın segment DNA davranışı arasında tekrar eden eşleşme var mı? Bu soru, haberin takımı hangi segmentte etkilediğini yakalar. Bazı takımlar baskı altında ilk 15’te dağılır, bazıları son 15’te.
Haber kaynakları tekilleştirildi mi ve aynı olayın kopyaları raf şişmesi yapmadan birleştirildi mi? Bu soru, kütüphane şişmesini kontrol eder. Aynı olayın 50 kopyası değil, tekil olayın kaynak referansları tutulur.
Bu haber paketi “kanıt zinciri” için yalnız bağlam mı yoksa doğrulanmış bir veri mi? Bu soru, senin istediğin kilittir: haber karar vermez. Haber yalnız bağlamdır; doğrulama olmadan hüküm üretilemez.
Bu haber yalnız yayın organı adıyla değil, yazar/editör kimliğiyle de etiketleniyor mu? Bu soru, aynı yayın organı içinde farklı doğruluk bantlarını ayırmak içindir. Kaynak tek başına yetmez; içerik üretici izi raf nesnesi olmalıdır.
Bu yazar/editör geçmişte hangi tür haberlerde daha yüksek doğruluk bandı gösterdi? Bu soru, “boş haber” ile “erken sinyal” üreten haberi ayırır. Bu bir hüküm değil, istatistiksel güven bandıdır.
Bu yazar/editörün haberleri hangi temalarda daha çok sapma üretiyor (transfer, sakatlık, yönetim, teknik direktör)? Bu soru, yazarın güçlü/zayıf alanını çıkarır. Analist hangi haberin hangi temada ciddiye alınacağını raf üzerinden görür.

Bu yazar/editör haberleri ile gerçekleşen olaylar arasındaki gerçekleşme oranı dönemsel değişiyor mu? Bu soru, bir yazarın belirli dönemlerde “balon” üretip üretmediğini ölçer. Dönemsel değişim varsa not edilir.
Bu yayın organının haberleri “sonuçtan sonra yeniden yazma” eğilimi taşıyor mu? Bu soru, maç sonrası anlatının manipülasyon değil ama “hikâye kurma” eğilimini ayırmak içindir. Analist bu riski bilir ve zincire göre tartar.
Aynı haber farklı kaynaklarda doğrulanıyor mu yoksa tek kaynakta mı kalıyor? Bu soru, tek kaynak gürültüsü ile çoklu kaynak tekrarını ayırır. Tek kaynak varsa kanıt zinciri zayıf kabul edilir.
Bu haberin dili deterministik mi yoksa abartılı/spekülatif mi ve bu dil profili yazar bazında tekrar ediyor mu? Bu soru, haberin “ton” profilini içerik üretici düzeyinde işler. Ton profili, doğruluk bandına doğrudan bağlanmaz ama risk işaretidir.

ÇAPRAZ KAYNAK OKUMA SORULARI (FUTBOL) — BASIN + ODDS + MAÇ İÇİ TETİKLEYİCİLER

,Bu bölümün amacı, üç ayrı hattı aynı anda “sonuç çıkarma” için birleştirmek değildir. Amaç, basın akışı, odds hareketi ve maç içi tetikleyiciler arasında tekrar eden zaman hizası ve davranış eşleşmesi olup olmadığını deterministik biçimde test etmektir. Bu bölüm, hüküm vermez; yalnız eşleşme ve eşleşmeme haritasını çıkarır. Kanıt zinciri tamamlanmadan hiçbir birim sonuç dili kuramaz.
Bu maç için basın haber temaları ile odds hareketinin zaman penceresi çakışıyor mu? Bu soru, “haber çıktı → piyasa hareket etti” gibi bir iddiayı test edilebilir hale getirir. Çakışma yoksa ilişki zayıf kabul edilir.

Basın haber temaları ile odds hareketi çakışıyorsa çakışma tek bookmaker’da mı yoksa birden çok bookmaker’da mı görülüyor? Bu soru, tekil kaynak sapmasını piyasa geneli sapmadan ayırır. Tekil sapma düşük güven sınıfıdır.
Basın haber temaları ile odds hareketi çakışıyorsa çakışma hangi lig/organizasyon sınıfında daha sık görülüyor? Bu soru, çapraz eşleşmenin ülke/lig bazında kümelenip kümelenmediğini ölçer. Kümelenme varsa harita çıkar.
Basın haber temaları ile odds hareketi çakışıyorsa bu çakışma dönemsel mi sabit mi rotasyonlu mu? Bu soru, rastgele görünen davranışın dönemsel haritası olup olmadığını test eder. Rotasyon varsa not edilir.
Basın haber temaları ile odds hareketi çakışıyorsa bu çakışma sezon fazına göre artıyor mu (sezon başı/sonu, transfer dönemi)? Bu soru, “geçiş dönemleri” etkisini ölçer. Bazı çapraz eşleşmeler sezon geçişlerinde artabilir.

Odds hareketi maç içi kader tetikleyicilerinden önce mi başladı yoksa tetikleyiciden sonra mı yoğunlaştı? Bu soru, zaman yönünü belirler. Tetikleyici sonrası hareket normal bant olabilir; tetikleyici öncesi hareket sapma adayını güçlendirir.
Odds hareketi tetikleyici olmadan oluşuyorsa bu hareket maç içi segment davranışında bir değişimle eşleşiyor mu? Bu soru, “olay yok ama davranış kaydı var” senaryosunu yakalar. Segment DNA değişiyorsa bu ayrıca işaretlenir.
Maç içi tetikleyicilerden hangileri odds hareketiyle en sık çakışıyor (kırmızı kart, VAR, penaltı, iptal gol)? Bu soru, piyasanın en hassas olduğu tetikleyici sınıfları çıkarır. Bu bir tahmin aracı değil, örüntü haritasıdır.
Maç içi tetikleyiciler ile basın temaları aynı hafta penceresinde eşleşiyor mu? Bu soru, basının tetikleyici üretip üretmediğini değil, basın konuştuğu şeyle maç içinin kesişip kesişmediğini test eder.
Basın teması “hakem/adalet” ise maç içi kart ve VAR tetikleyicileriyle eşleşme bandı artıyor mu? Bu soru, tematik eşleşmeyi test eder. Eşleşme varsa yalnız işaretlenir, hüküm kurulmaz.
Basın teması “sakatlık/eksik” ise maç içi segmentlerde kondisyon düşüşü veya tempo kırılmasıyla eşleşme var mı? Bu soru, haber bağlamının sahaya yansıyıp yansımadığını ölçer.
Basın teması “transfer/kriz/yönetim” ise maç içi disiplin bandında kart yoğunluğu artıyor mu? Bu soru, haber-temelli baskının disipline yansıma ihtimalini test eder. Tek seferlikte hüküm yoktur, tekrar aranır.

Bu eşleşmeler takım bazında mı kümeleniyor yoksa lig bazında mı kümeleniyor? Bu soru, yapının nerede olduğunu ayırır. Takım bazlıysa takım DNA’sına, lig bazlıysa lig davranışına yazılır.
Bu eşleşmeler bookmaker bazında mı kümeleniyor yoksa piyasa geneline mi yayılıyor?nBu soru, sapmanın kaynak sınıfını belirler. Bookmaker profili ayrı raf nesnesidir.
Bu eşleşmeler belirli yazar/editör kaynaklarında mı yoğunlaşıyor? Bu soru, haber kaynağı güven haritasını çapraz hatla birleştirir. Aynı yazarın haberleriyle eşleşme yüksekse işaretlenir.
Bu eşleşmelerde tekrar eden bir “tetikleyici sırası” var mı (haber tonu → odds kayması → kart/VAR → tempo kırılması)? Bu soru, zincir şeması çıkarır. Zincir şeması varsa bu yalnız örüntüdür, hüküm değildir.
Bu eşleşmelerde “anomali yok” durumunda da normal bant korunuyor mu? *Bu soru, sistemin en kritik ilkesini korur: anomali çıkmaması da bir sonuçtur. Normal bant korunuyorsa bu bilgi raflara yazılır.
Bu eşleşmelerde veri eksikliği veya kalite düşüşü var mı ve “anomali yok” ile karışıyor mu? Bu soru, data\\\_quality ayrımını çapraz okuma içinde de korur. Eksik veri varsa eşleşme hükmü kurulmaz.

Bu haber kaydı hangi UTC zaman damgası ile sabitlendi?,Bu haberin yayın UTC zaman damgası var mı, unknown mu?,Bu haberin kayıt UTC zaman damgası var mı, unknown mu?,Bu haberin yayın saati ile kayıt saati arasındaki fark kaç dakikadır?
Bu haberin kayıt saati yayın saatinden önce mi sonra mı?,Bu haber sezon içi mi sezon arası mı?,Bu haber “transfer dönemi” penceresinde mi?,Bu haber hangi ülke_ref altında raflanacak?,Bu haber country_ref map edilebildi mi, unmapped mi?,Bu haber hangi lig_ref altında raflanacak?,Bu haber lig_ref map edilebildi mi, unmapped mi?,Bu haber hangi sezon_id içinde okunacak?,Bu haber season_id map edilebildi mi, unmapped mi?,Bu haber season_phase olarak hangi faza yazılacak (pre_season, season_start, season_mid, season_end,off_season)?,Bu haber competition_type olarak hangi sınıfta (league, cup, continental, national_team) işlenecek?,Bu haber cup_flag taşıyor mu (true/false)?,Bu haber hangi team_ref ile ilişkilendirilecek?,Bu haber team_ref map edilebildi mi, unmapped mi?
Bu haber tek takıma mı bağlı yoksa iki takıma mı bağlı (tekil/çift takım bağlamı)?,Bu haber iki takım bağlıysa rakip team_ref map edilebildi mi, unmapped mi?,Bu haber match_ref’e bağlanabiliyor mu yoksa sadece takım bağlamında mı kalmalı?,Bu haber match_ref map edilebildi mi, unmapped mi?,Bu haber tek bir maç penceresine mi bağlı yoksa maç dışı genel haber mi?,Bu haber bir maç öncesi penceresine mi ait yoksa maç sonrası penceresine mi ait?
Bu haber “maç öncesi” mi “maç sonrası” mı “iki maç arası” mı?,Bu haberin bağlandığı maçın kickoff_time_utc bilgisi kesin mi, unknown mu?,Bu haber kickoff_time_utc ile haber zamanı arasında “aynı gün” ilişkisi var mı?,Bu haberin kapsadığı pencere kaç gündür ve sabit mi?
Bu haber pencere başlangıcı hesaplanabildi mi, unknown mu?,Bu haber pencere bitişi hesaplanabildi mi, unknown mu?
Bu haber “sezon içi maç haftası paketi” mi yoksa “off-season haftalık paket” mi?,Bu haber tekil olay mı, çoklu olay seti mi?,Bu haber çoklu olay setiyse alt olay sayısı çıkarılabildi mi, unknown mu?,Bu haber aynı olayın kopyası mı, tekil olay mı?,Bu haber aynı gün içinde birden fazla defa yeniden yayınlanmış mı?,Bu haberin aynı içerikli kopyaları tekilleştirildi mi?
Bu haber tekilleştirme anahtarı üretilebildi mi yoksa unmapped mi kaldı?,Bu haberin birincil hedefi kimdir (takım/koç/oyuncu/hakem/yönetim/federasyon/taraftar)?,Bu haber hedefi “kurum” mu “birey” mi?,Bu haberin ikincil hedefi kimdir (rakip takım/oyuncu/kurum)?Bu haber tek takım mı, iki takım mı, lig geneli mi?,Bu haber lig geneli ise team_ref boş mu?
Bu haber aynı haftada başka haberlerle zincir oluşturuyor mu?,Bu haber zincirin “ilk halkası” mı “devam halkası” mı?,Bu haberin başlığı içerikle uyumlu mu?,Bu haberde doğrudan alıntı var mı yoksa yorum aktarımı mı?,Bu haberin dili açıklayıcı mı yoksa spekülatif mi?
Bu haberin dili “kesin” mi “iddia” mı?
Bu haberde isimler net mi yoksa belirsiz kaynak dili mi var?,Bu haberde isimler net ama map edilemedi mi?,Bu haberde sayısal veri var mı yoksa anlatı mı?,Bu haber doğrulandı mı, yalanlandı mı, güncellendi mi?,Bu haber bir “ilk versiyon” mu “güncelleme” mi?
Bu haber önceki versiyonla çelişiyor mu?

BÖLÜM B — ADRESLEME VE DOSYALAMA DUVARI (KÜTÜPHANECİ)
Bu haber hangi ülke/lig/sezon bağlamına bağlıdır?,Bu haber hangi organizasyon tipine bağlıdır (lig/kupa/kıtasal/milli takım)?,Bu haberin bağlandığı yarışma sınıfı nedir (Tier-1/Tier-2/Cups)?,Bu haberin kaynak URL’i var mı, yok mu?,Bu haber URL formatı okunabilir mi yoksa bozuk mu?,Bu haberin kaynak domain’i belirlenebiliyor mu?,Bu haber domain allowlist içinde mi?,Bu haberin canonical_url’i üretilebildi mi?,Bu haber canonical_url ile kaynak URL aynı mı farklı mı?,Bu haber bir ajans geçişi mi yoksa özgün içerik mi?,Bu haber “doğrudan kaynak” mı yoksa “alıntı / reprint” mi?,Bu haber alıntı ise birincil kaynak tespit edilebildi mi?,Bu haberin içinde geçen özel isimler (takım, oyuncu, hoca, hakem) net map edilebildi mi?,Bu haberde entity sayısı çıkarıldı mı?,Bu haberin içinde geçen özel isimlerden map edilemeyen var mı, varsa hangileri unmapped kaldı?,Bu haberin metni dil olarak hangi dilde yazılmış?,Bu haber dil tespiti güvenilir mi, low mu?,Bu haberin çeviri olduğu tespit edilebiliyor mu?,Bu haberin “başlık + gövde” tutarlılığı var mı?
Bu haberin başlığı tık tuzağı (clickbait) diline yakın mı, değil mi?,Bu haberin gövdesi gerçek bilgi mi yoksa yorum dili mi ağırlıklı?,Bu haber gövdesinde “duygu dili” baskın mı?,Bu haberin görsel/video referansı var mı, yok mu?,Bu haber görsel/video referansı olayla doğrudan ilişkili mi?,Bu haberin kaynak gösterimi açık mı, kapalı mı?,Bu haber kaynak gösterimi var ama muğlak mı?

BÖLÜM C — KAYNAK KİMLİĞİ VE DOĞRULUK PROFİLİ
Bu haber tek kaynak mı çoklu kaynak mı?,Bu haberin kaynakları birbirini doğruluyor mu yoksa ayrışıyor mu?,Bu haber farklı kaynaklarda aynı gün çıktı mı?,Bu haberin birincil kaynağı resmî mi gayriresmî mi?,Bu haber hangi yayın_organı_ref ile eşleşti?,Bu yayın organı allowlist içinde mi?,Bu yayın organı lig özelinde düzenli haber üretmiş mi?,Bu yayın organı takım özelinde aşırı yoğun haber üretiyor mu?,Bu haberin yazarı/editörü adı metinden çekilebildi mi?,Bu haberin yazarı/editörü map edilebildi mi?Bu haber “staff writer” gibi anonim bir yazar mı?,Bu haber “editorial desk” gibi toplu editoryal imza mı?,Bu yazar için örneklem yeterli mi, low sample mı?,Bu yazar geçmişte aynı tema türünde isabetli mi?,Bu yazar geçmişte aynı tema türünde gürültü üretiyor mu?,Bu yayın organı haberleri maç sonrası yeniden yazma eğilimi taşıyor mu?,Bu haber bir düzeltme (correction) içeriyor mu?,Bu haber bir yalanlama (denial) içeriyor mu?,Bu haber bir resmi açıklama alıntısı içeriyor mu?,Bu haberin birincil kaynağı kulüp mü?,Bu haberin birincil kaynağı federasyon mu?,Bu haberin birincil kaynağı oyuncu mu?,Bu haberin birincil kaynağı menajer mi?,Bu haberin birincil kaynağı teknik direktör mü?,Bu haber maçtan sonra doğrulandı mı?,Bu haber maçtan sonra çöktü mü?,Bu haber daha sonra düzeltildi mi?,Bu haber birden fazla kez farklı sürümle yayınlandı mı?,Bu haber çelişkili bilgi içeriyor mu?,Bu çelişki “tarih” mi “isim” mi “kulüp” mü “rakam” mı?,Bu haberin kanıt zinciri kalitesi yeterli mi yoksa yalnız bağlam mı?,Bu haber “ilk sinyal” mi “sonradan hikâye” mi?

BÖLÜM D — TEMA SINIFLANDIRMA (ÜST KONU)
Bu haberin ana teması yönetim mi?,Bu haberin ana teması finans mı?,Bu haberin ana teması transfer mi?,Bu haberin ana teması sakatlık mı?,Bu haberin ana teması kadro seçimi mi?,Bu haberin ana teması teknik direktör kararı mı?,Bu haberin ana teması taktik/oyun planı mı?
Bu haberin ana teması disiplin/ceza mı?,Bu haberin ana teması hakem/VAR mi?,Bu haberin ana teması taraftar/tribün mü?,Bu haberin ana teması antrenman/kamp mı?,Bu haberin ana teması iç kriz/soyuna odası mı?,Bu haberin ana teması basın toplantısı mı?
Bu haberin ana teması kulüp içi çatışma mı?,Bu haberin ana teması yayıncı/TV anlaşmazlığı mı?,Bu haberin ana teması federasyon kararı mı?,Bu haberin ana teması ceza kurulu kararı mı?,Bu haberin ana teması güvenlik olayları mı?Bu haberin ana teması saha dışı skandal mı?
Bu haberin ana teması doping iddiası mı?,Bu haberin ana teması altyapı/genç oyuncu mu?,Bu haberin ana teması milli takım çağrısı mı?,Bu haber birden fazla ana tema taşıyor mu?

BÖLÜM E — TON VE YÖNLENDİRME BANTLARI
Bu haber tonu olumlu mu?,Bu haber tonu olumsuz mu?,Bu haber tonu karma mı?,Bu haber tonu nötr mü?,Bu haber dili provokatif mi?,Bu haber dili sakin mi?,Bu haber dili panik üretiyor mu?,Bu haber dili güven telkin ediyor mu?,Bu haber dili baskı üretiyor mu?Bu haber dili “kriz büyütme” eğilimi taşıyor mu?,Bu haber dili “yumuşatma / toparlama” eğilimi taşıyor mu?,Bu haber içinde doğrudan hedef gösterme var mı?,Bu haber içinde kişisel saldırı dili var mı?,Bu haber içinde taraftarı kışkırtan ifade var mı?,Bu haber içinde kulüp yönetimine açık çağrı var mı?,Bu haber içinde teknik direktöre istifa baskısı var mı?,Bu haber içinde oyuncuya yönelik disiplin baskısı var mı?,Bu haber içinde hakem hedef gösterme var mı?,Bu haber içinde federasyon hedef gösterme var mı?,Bu haber içinde “son dakika” dili var mı?
Bu haber içinde “kesin bilgi” iddiası var mı?,Bu haber içinde “kulüp kaynakları” gibi muğlak kaynak dili var mı?,Bu haber dili “tehdit” çağrışımı taşıyor mu?,Bu haber dili “linç” çağrışımı taşıyor mu?

BÖLÜM F — TAKIM GENEL HABERİ (KULÜP / KADRO / SEZON STRATEJİSİ)
Bu haber kulüp yönetimiyle mi ilgili?,Bu haber sportif direktör veya üst yönetim kararlarını içeriyor mu?,Bu haber takımın sezon hedefini değiştiren bir söylem taşıyor mu?,Bu haber hedef değişimi “yüksek hedef” mi “hedefdüşürme”,mi?,Bu,haber,kadro,istikrarınıetkileyen bir problem içeriyor mu?,Bu haber kadro istikrarını etkileyen problem “saklık yoğunluğu” mu “transfer belirsizliği” mi?,Bu haber oyuncu huzursuzluğu veya soyunma odası gerilimi teması taşıyor mu?,Bu haber “hoca” ile “oyuncu grubu” gerilimimi?,Bu,haber“oyuncu-oyuncu” gerilimi mi?,Bu haber takım içinde “liderlik boşluğu” teması taşıyor mu?,Bu haber takımın iç disipliniyle ilgili bir karar içeriyor mu?,Bu haber disiplin kararı “ceza” mı “uyarı” mı?Bu haber antrenman düzeninde değişiklik içeriyor mu?,Bu haberantrenman değişikliği “saat” mi “yük” mü “metot” mu?,Bu haber kamp / seyahat / hazırlık programı içeriyor mu?,Bu haber hazırlık programı “iptal” mi “uzama” mı “yer değişimi” mi?,Bu haber yoğun fikstür veya yorgunluk teması taşıyor mu?,Bu haber rotasyon planını etkileyen bir baskı içeriyor mu?,Bu haber rotasyon baskısı “zorunlu” mu “tercih” mi?,Bu haber kulübün ekonomik durumu veya maaş ödemeleriyle ilgili mi?,Bu haber maaş konusu “gecikme” mi “eksik ödeme” mi “tam ödeme” mi?,Bu haber prim / bonus / ödeme gecikmesi gibi motivasyon etkisi taşıyor mu?,Bu haber takım içinde gruplar oluştuğu iddiası taşıyor mu?,Bu haber gruplar “yerli-yabancı” mı “genç-yaşlı” mı?,Bu haber oyuncuların teknik direktöre güveni teması taşıyor mu?,Bu haber yönetim-teknik ekip çatışması içeriyor mu?Bu haber taraftar baskısının Kulüp kararlarını etkilediğini söylüyor mu?,Bu haber takımın kadro dışı kararlarını içeriyor mu?,Bu haber kadro dışı “disiplin” mi “performans” mı “transfer” mi?,Bu haber takımın sakatlık yönetimiyle ilgili bir problem içeriyor mu?,Bu haber sakatlık yönetimi “yanlış yükleme” iddiası mı?,Bu haber kulüp içinde hukuki süreç / dava / ceza içeriyor mu?,Bu haber hukuki süreç “para cezası” mı “transfer yasağı” mı?,Bu haber kulüp içi güvenlik / tesis / stat problemi içeriyor mu?,Bu haber stat sorunu “zemin” mi “seyirci” mi “güvenlik” mi?
Bu haber takımın iç saha atmosferini büyüten bir gündem mi?,Bu haber takımın deplasman baskısını büyüten bir gündem mi?

BÖLÜM G — TEKNİK DİREKTÖR HABERİ (KOÇ)
Bu haberin hedefi teknik direktör mü?,Bu haber teknik direktörün görev güvenliğiyle mi ilgili?,Bu haber “istifa” mı “kovulma” mı “ultimatom” mu?,Bu haber teknik direktörün yönetimle gerilim yaşadığını söylüyor mu?,Bu haber gerilim “transfer” mi “hedef” mi “yetki” mi?Bu haber teknik direktörün oyuncularla gerilim yaşadığını söylüyor mu?,Bu haber gerilim “yıldız oyuncu” mu “grup” mu?,Bu haber teknik direktörün basın toplantısı çıkışı mı?,Bu haber teknik direktörün maç öncesi plan beyanı içeriyor mu?,Bu haber teknik direktörün maç sonrası açıklaması mı?,Bu haber teknik direktörün hakem/VAR açıklaması içeriyor mu?,Bu haber hakem/VAR açıklaması “sakin” mi “sert” mi?,Bu haber teknik direktörün kadro seçiminde zorlandığını söylüyor mu?,Bu haber zorlanma “sakatlık” mı “yorgunluk” mu “ceza” mı?,Bu haber teknik direktörün rotasyon tercihleriyle ilgili mi?,Bu haber teknik direktörün oyuncu disiplini yaklaşımıyla ilgili mi?,Bu haber disiplin yaklaşımı “sertleşme” mi “yumuşama” mı?,Bu haber teknik direktörün kendi ekibinde değişiklik yapacağını söylüyor mu?,Bu haber teknik direktörün antrenman metodu değişimini söylüyor mu?,Bu haber teknik direktörün “takım ruhu / birlik” mesajı mı?,Bu haber teknik direktörün “kriz yönetimi” kapasitesini test eden bir gündem mi?,Bu haber teknik direktörün “bahane” dili taşıdığı iddiası mı?

BÖLÜM H — FUTBOLCU HABERİ (OYUNCU)
Bu haberin hedefi futbolcu mu?,Bu haber futbolcunun sakatlığıyla mı ilgili?,Bu haber sakatlık “kas” mı “darbe” mi “kronik” mi?,Bu haber futbolcunun sakatlıktan dönüş süreciyle mi ilgili?,Bu haber dönüş süreci “takım antrenmanı” mı “bireysel çalışma” mı?,Bu haber futbolcunun “oynar/oynamaz” netliği taşıyor mu?,Bu haber netlik “kesin oynar” mı “riskli” mi “kesin yok” mu?,Bu haber futbolcunun cezalı duruma düşmesiyle mi ilgili?,Bu haber ceza “kırmızı” mı “kart birikimi” mi?,Bu haber futbolcunun kadro dışı bırakılmasıyla mı ilgili?,Bu haber kadro dışı sebebi “disiplin” mi “performans” mı?Bu haber futbolcunun disiplinsiz davranışıyla mı ilgili?,Bu haber davranış “geç kalma” mı “kavga” mı?,Bu haber futbolcunun antrenman performansı hakkında mı?,Bu haber performans “düşük” mü “yüksek” mi?,Bu haber futbolcunun teknik direktörle gerilimi hakkında mı?,Bu haber futbolcunun takım arkadaşlarıyla gerilimi hakkında mı?,Bu haber futbolcunun taraftarla gerilimi hakkında mı?,Bu haber futbolcunun sosyal medya davranışı kaynaklı mı?,Bu haber sosyal medya “paylaşım” mı “beğeni” mi “yorum” mu?,Bu haber futbolcunun mental yorgunluk / stres taşıdığını söylüyor mu?,Bu haber stres “aile” mi “performans baskısı” mı?,Bu haber futbolcunun transfer söylentisi mi?,Bu haber transfer “gidiş” mi “geliş” mi?,Bu haber futbolcunun transferinde resmiyet var mı?,Bu haber resmiyet “kulüp açıklaması” mı “menajer” mi?,Bu haber futbolcunun maaş/prim tartışması içeriyor mu?,Bu haber tartışma “zam” mı “gecikme” mi?,Bu haber futbolcunun “sözleşme krizi” içeriyor mu?,Bu haber sözleşme “uzatma” mı “fesih” mi?

BÖLÜM I — HAKEM / VAR HABERİ
Bu haberin hedefi hakem mi?,Bu haber hakemin atanmasıyla mı ilgili?,Bu haber atama “maç özel” mi “genel politika” mı?,Bu haber hakemin geçmiş maç performansına dair tartışma mı?,Bu haber tartışma “kart” mı “penaltı” mı “VAR” mı?,Bu haber hakemin kart standardı hakkında bir gündem mi?,Bu haber hakemin penaltı standardı hakkında bir gündem mi?,Bu haber hakemin VAR kararlarıyla ilgili mi?,Bu haber VAR hakemiyle ilgili mi?,Bu haber hakemin disiplin soruşturması iddiası mı?,Bu haber kulübün hakem şikâyeti mi?Bu haber rakip kulübün hakem şikâyeti mi?,Bu haber medya tarafından “hakem baskısı” kurulması mı?,Bu haber hakemle ilgili “yönetim açıklaması” içeriyor mu?,Bu haber hakemle ilgili “federasyon açıklaması” içeriyor mu?,Bu haber hakemle ilgili “maç sonu hedef gösterme” dili taşıyor mu?
Bu haber hakem haberinde “video/kanıt dolaşımı” var mı?

BÖLÜM J — YÖNETİM / FEDERASYON / LİG POLİTİK HABERİ
Bu haber federasyon kararı içeriyor mu?,Bu haber disiplin kurulu kararı içeriyor mu?,Bu haber puan silme / ceza / seyirci yasağı içeriyor mu?,Bu haber ceza “seyirci” mi “puan” mı “para” mı?,Bu haber hükmen mağlubiyet veya itiraz süreciyle ilgili mi?,Bu haber itiraz süreci “başvuru” mu “sonuç” mu?,Bu haber fikstür değişikliği içeriyor mu?,Bu haber maç saati/stadı değişikliği içeriyor mu?,Bu haber güvenlik nedeniyle maçın riskli sınıfa alınması mı?,Bu haber kulüp lisans / finansal fair-play süreci içeriyor mu?,Bu haber transfer yasağı / kadro kısıtı içeriyor mu?,Bu haber sezon planlaması / maç sıkışıklığı gibi yapısal konu mu?,Bu haber “yabancı kuralı / kadro kuralı” değişimi gibi düzenleme mi?,Bu haber saha içi değil “masa başı” etki taşıyor mu?,Bu haberin etkisi bir sonraki maçı etkiler mi?

BÖLÜM K — RAKİP / DERBİ / STRES
Bu haber iki takımı aynı anda kapsıyor mu?,Bu haber derbi baskısı teması taşıyor mu?,Bu haber “prestij maçı” bandında mı?,Bu haber “intikam maçı” bandında mı?,Bu haber “şampiyonluk maçı” baskısı taşıyor mu?,Bu haber “küme düşme maçı” baskısı taşıyor mu?,Bu haber tribün güvenliği ve olay beklentisi içeriyor mu?,Bu haber maç öncesi gerginlik artışı içeriyor mu?,Bu haber iki takım oyuncuları arasında bireysel rekabet teması mı?,Bu haber iki takım koçları arasında gerilim teması mı?,Bu haber maçın “kapalı gişe” baskısı taşıyor mu?,Bu haber maçın “seyircisiz” olması gibi atmosfer etkisi taşıyor mu?,Bu haber maç öncesi provokasyon iddiası içeriyor mu?,Bu haber maç sonrası gerilimin büyüdüğünü ve bir sonraki maça taşınacağını söylüyor mu?

BÖLÜM L — TARAFTAR HABERLERİ
Bu haber taraftar protestosu içeriyor mu?,Bu haber taraftarın yönetime baskısı teması mı?,Bu haber taraftarın teknik direktöre baskısı teması mı?,Bu haber taraftarın belirli bir oyuncuyu hedef aldığı teması mı?,Bu haber tribün içi kavga/gerilim içeriyor mu?,Bu haber güvenlik riski içeriyor mu?,Bu haber deplasman yasağı / taraftar kısıtı içeriyor mu?,Bu haber taraftarın sosyal medya linci gibi baskı içeriyor mu?,Bu haber maç önü şehirde gerginlik içeriyor mu?Bu haber maç içinde sahaya yabancı madde/olay ihtimali taşıyor mu?,Bu haber taraftarın maç içi davranışını etkileyen bir çağrı mı?,Bu haberin sahaya yansıması geçmişte tekrar etmiş mi?,Bu haber belirli dönemlerde artıyor mu (kötü seri, kötü sonuç)?,Bu haber belirli maçlarda artıyor mu (derbi, final, küme düşme)?,Bu haberin yarattığı baskı kart/tempo/disiplin bandına yansıyor mu?

BÖLÜM M — VERİ KALİTESİ / BOZULMA KONTROL
Bu haber kaydı complete mi, partial mi, incomplete mi, low mu?,Bu haberin missing_fields listesi çıkarıldı mı?,Bu haber kaynağı belirsiz mi?,Bu haber yazarı belirsiz mi?,Bu haber tarih hizası belirsiz mi?,Bu haber team_ref’e map edilemedi mi?,Bu haber lig_ref’e map edilemedi mi?Bu haber country_ref’e map edilemedi mi?,Bu haber match_ref’e map edilemedi mi?,Bu haber tekilleştirme başarısız mı kaldı?,Bu haber çelişkili bilgi içeriyor mu?,Bu haber “kanıt zinciri” için yalnız bağlam olarak mı işaretlendi?,Bu haber “doğrulanmış veri” olarak işaretlenebildi mi?,Bu haberin doğrulanma yöntemi tek kaynak mı, çoklu kaynak mı?,Bu haber “sonradan yanlışlandığı” tespit edildi mi?

FAZ-22:KURAL BLOĞU — EVENT EKSİK / BASIN ÇAPRAZ OKUMA (KİLİTLİ)
Event akışı eksik/parçalıysa sistem hiçbir alanı uydurmaz; eksikler missing_fields’e yazılır ve data_quality_badge deterministik olarak incomplete/low olur.Bu durumda canlı izleme kadrosu sadece paket kapsamındaki ham olay izlerini toplar; yorum üretmez, raportör yalnız tekilleştirir, analist tek birleşik maç raporunu yazar.Basın rafı event alanlarını doldurmak için kullanılmaz; basın yalnız “destek izi” üretir ve maç kartına ayrı blok olarak eklenir.Destek izi yalnız çoklu kaynak tekrarıyla işaretlenir; tek kaynakla hüküm kurulmaz ve skor/tahmin dili üretilmez.Event zayıfsa sonuç: güven düşer, kayıt saklanır, örüntü yalnız tekrar ve şart bağımlılığıyla güçlenir; uydurma ile kapatma yasaktır.

BÖLÜM A — Haber Kaydı / Bağlam Kimliği
Bu haber kaydı hangi UTC zaman damgası ile sabitlendi?→ news.context.locked_at_utc→ timestamp_ut → unknown,Bu haberin yayın UTC zaman damgası var mı, unknown mu?→ news.time.published_at_utc→ timestamp_utc→ unknown,Bu haberin kayıt UTC zaman damgası var mı, unknown mu? →news.time.recorded_at_utc→ timestamp_utc→ unknown,Bu haberin yayın saati ile kayıt saati arasındaki fark kaç dakikadır?→news.time.publish_record_delta_minutes→ integer→unknown,Bu haberin kayıt saati yayın saatinden önce mi sonra mı?→news.time.record_vs_publish_order→ enum(before,after,unknown)→ unknown,Bu haber sezon içi mi sezon arası mı?→ news.season.in_or_off→ enum(in_season,off_season,unknown)→ unknown,Bu haber “transfer dönemi” penceresinde mi?→ news.season.transfer_window_flag→ boolean→ unknown,Bu haber hangi ülke_ref altında raflanacak?→ news.refs.country_ref→ string→ unknown,Bu haber country_ref map edilebildi mi, unmapped mi?→ news.refs.country_ref_map_status → enum(mapped,unmapped,unknown) → unknown,Bu haber hangi lig_ref altında raflanacak? → news.refs.league_ref→ string→ unknown,Bu haber lig_ref map edilebildi mi, unmapped mi?→ news.refs.league_ref_map_status→ enum(mapped,unmapped,unknown)→ unknown,Bu haber hangi sezon_id içinde okunacak?→ news.refs.season_id→ string → unknown,Bu haber season_id map edilebildi mi, unmapped mi? → news.refs.season_id_map_status→ enum(mapped,unmapped,unknown)→ unknown,Bu haber season_phase olarak hangi faza yazılacak(pre_season,season_start,season_mid,season_end,off_season)→news.season.phase→enum(pre_season,season_start,season_mid,season_end,off_season,unknown)→ unknown,Bu haber competition_type olarak hangi sınıfta (league, cup,continental,national_team)işlenecek?→ news.competition.type→ enum(league,cup,continental,national_team,unknown) → unknown,Bu haber cup_flag taşıyor mu (true/false)? → news.competition.cup_flag → boolean → unknown,Bu haber hangi team_ref ile ilişkilendirilecek? → news.refs.team_primary_ref → string → unknown,Bu haber team_refmapedilebildimi,unmappedmi→news.refs.team_primary_ref_map_statu→ enum(mapped,unmapped,unknown) → unknown,bu haber tek takıma mı bağlı yoksa iki takıma mı bağlı (tekil/çift takım bağlamı)? → news.context.team_binding_mode → enum(single_team,two_teams,unknown)→ unknown,Bu haber ikitakımbağlıysarakipteam_refmapedilebildimi,unmappedmi→news.refs.team_secondary_ref_map_status→enum(mapped,unmapped,unknown) → unknown,Bu haber match_ref’e bağlanabiliyor mu yoksa sadece takım bağlamında mı kalmalı? → news.context.match_linking_mode → enum(match_ref,team_only,unknown) → unknown,bu haber match_ref map edilebildi mi, unmapped mi? → news.refs.match_ref_map_status → enum(mapped,unmapped,unknown) → unknown,Bu haber tek bir maç penceresine mi bağlı yoksa maçdışıgenelhabermi→news.context.match_window_scope→enum(single_match_window,non_match_general,unknown) → unknown,Bu haber bir maç öncesi penceresine mi ait yoksa maç sonrası penceresine mi ait? → news.context.pre_post_window → enum(pre_match,post_match,unknown) → unknown,Bu haber “maç öncesi” mi “maç sonrası” mı “iki maç arası” mı? → news.context.timing_bucket → enum(pre_match,post_match,between_matches,unknown) → unknown,Bu haberin bağlandığı maçın kickoff_time_utc bilgisi kesin mi, unknown mu? → news.match.kickoff_time_utc → timestamp_utc → unknown,Bu haber kickoff_time_utc ile haber zamanı arasında “aynı gün” ilişkisi var mı? → news.match.kickoff_same_day_flag → boolean → unknown,Bu haberin kapsadığı pencere kaç gündür ve sabit mi? → news.window.coverage_days → integer → unknown,Bu haber pencere başlangıcı hesaplanabildi mi, unknown mu? → news.window.start_at_utc → timestamp_utc → unknown,Bu haber pencere bitişi hesaplanabildi mi, unknown mu? → news.window.end_at_utc → timestamp_utc → unknown,Bu haber “sezon içi maç haftası paketi” mi yoksa “off-season haftalıkpaket”mi→news.window.package_type→enum(in_season_matchweek,off_season_weekly,unknown) → unknown,Bu haber tekil olay mı, çoklu olay seti mi? → news.event.set_mode → enum(single_event,multi_event_set,unknown) → unknown,Bu haber çoklu olay setiyse alt olay sayısı çıkarılabildi mi, unknown mu? →news.event.sub_event_count → integer → unknown,Bu haber aynı olayın kopyası mı, tekil olay mı? → news.dedupe.is_duplicate_flag → boolean → unknown,Bu haber aynı gün içinde birden fazla defa yeniden yayınlanmış mı? → news.dedupe.republished_same_day_flag → boolean → unknown,Bu haberin aynı içerikli kopyaları tekilleştirildi mi? → news.dedupe.deduplicated_flag → boolean → unknown,Bu haber tekilleştirme anahtarıüretilebildi,miyoksaunmappedmikaldı→news.dedupe.dedup_key_status→enum(mapped,unmapped,unknown)→unknown,Buhaberinbirincilhedefikimdir(takım/koç/oyuncu/hakem/yönetim/federasyon/taraftar)? → news.target.primary_actor_type → enum(team,coach,player,referee,management,federation,fans,unknown) → unknown,Bu haber hedefi “kurum” mu “birey” mi? → news.target.primary_actor_class → enum(institution,individual,unknown) → unknown

Bu haberin ikincil hedefi kimdir (rakip takım/oyuncu/kurum)?→news.target.secondary_actor_type →enum(opponent_team,player,institution,unknown)→unknown.Bu haber tek takımmı,ikitakımmı,lig genelimi?→news.scope.team_scope→enum(single_team,two_teams,league_wide,unknown)→ unknown..Bu haber lig geneli ise team_ref boş mu?→ news.scope.league_wide_team_ref_empty_flag→ boolean→ unknown.Bu haber aynı haftada başka haberlerle zincir oluşturuyor mu?→ news.chain.chain_flag→ boolean→ unknown.Bu haber zincirin “ilk halkası” mı “devam halkası” mı?→news.chain.chain_position→ enum(first,continuation,unknown)→ unknown,Bu haberin başlığı içerikle uyumlu mu?→ news.content.title_content_alignment→ enum(aligned,misaligned,unknown)→ unknown.Bu haberde doğrudan alıntı var mıyoksayorumaktarımımı→news.content.quote_mode→ enum(direct_quote,commentary,unknown)→ unknown,Bu haberin dili açıklayıcı mı yoksa spekülatif mi?→ news.content.tone→ enum(explanatory,speculative,unknown)→ unknown,Bu haberin dili “kesin” mi “iddia” mı?→ news.content.claim_strength→ enum(definite,allegation,unknown)→ unknown,Bu haberde isimler net mi yoksa belirsiz kaynak dili mi var?→ news.entities.naming_claritc→ enum(clear_names,vague_sources,unknown)→ unknown

Bu haberde isimler net ama map edilemedi mi? → news.entities.names_clear_but_unmapped_flag → boolean → unknown.Bu haberde sayısal veri var mı yoksa anlatı mı? → news.content.data_mode → enum(numeric_data,narrative,unknown) → unknown.
Bu haber doğrulandı mı, yalanlandı mı, güncellendi mi? → news.verification.status → enum(verified,debunked,updated,unknown) → unknown.Bu haber bir “ilk versiyon” mu “güncelleme” mi? → news.version.kind → enum(first_version,update,unknown) → unknown.
Bu haber önceki versiyonla çelişiyor mu? → news.version.conflicts_with_previous_flag → boolean → unknown.

BÖLÜM B — Adresleme ve Dosyalama Duvarı
Bu haber hangi ülke/lig/sezon bağlamına bağlıdır? → library.addressing.context_scope → object → unknown.Bu haber hangi organizasyon tipine bağlıdır (lig/kupa/kıtasal/milli takım)? → library.addressing.competition_org_type → enum → unknown
Bu haberin bağlandığı yarışma sınıfı nedir (Tier-1/Tier-2/Cups)? → library.addressing.competition_tier_class → enum → unknown.Bu haberin kaynak URL’i var mı, yok mu? → library.addressing.source_url_presence → boolean → unknown
Bu haber URL formatı okunabilir mi yoksa bozuk mu? → library.addressing.source_url_readability → enum → unknown.Bu haberin kaynak domain’i belirlenebiliyor mu? → library.addressing.source_domain_detected → boolean → unknown
Bu haber domain allowlist içinde mi? → library.addressing.source_domain_allowlisted → boolean → unknown.Bu haberin canonical_url’i üretilebildi mi? → library.addressing.canonical_url_generated → boolean → unknown
Bu haber canonical_url ile kaynak URL aynı mı farklı mı? → library.addressing.canonical_vs_source_url_match → enum → unknown.Bu haber bir ajans geçişi mi yoksa özgün içerik mi? → library.addressing.content_origin_type → enum → unknown
Bu haber “doğrudan kaynak” mı yoksa “alıntı / reprint” mi? → library.addressing.content_reprint_status → enum → unknown.Bu haber alıntı ise birincil kaynak tespit edilebildi mi? → library.addressing.primary_source_identified → boolean → unknown
Bu haberin içinde geçen özel isimler (takım, oyuncu, hoca, hakem) net map edilebildi mi? → library.addressing.entities_mapped_cleanly → boolean → unknown.Bu haberde entity sayısı çıkarıldı mı? → library.addressing.entity_count_extracted → boolean → unknown
Bu haberin içinde geçen özel isimlerden map edilemeyen var mı, varsa hangileri unmapped kaldı? → library.addressing.unmapped_entities → list → unknown
Bu haberin metni dil olarak hangi dilde yazılmış? → library.addressing.detected_language → enum → unknown.Bu haber dil tespiti güvenilir mi, low mu? → library.addressing.language_detection_confidence → enum → unknown
Bu haberin çeviri olduğu tespit edilebiliyor mu? → library.addressing.translation_detected → boolean → unknown.Bu haberin “başlık + gövde” tutarlılığı var mı? → library.addressing.title_body_consistency → enum → unknown
Bu haberin başlığı tık tuzağı (clickbait) diline yakın mı, değil mi? → library.addressing.title_clickbait_likelihood → enum → unknown.Bu haberin gövdesi gerçek bilgi mi yoksa yorum dili mi ağırlıklı? → library.addressing.body_fact_vs_commentary → enum → unknown
Bu haber gövdesinde “duygu dili” baskın mı? → library.addressing.body_emotion_language_dominance → enum → unknown.Bu haberin görsel/video referansı var mı, yok mu? → library.addressing.media_reference_presence → boolean → unknown
Bu haber görsel/video referansı olayla doğrudan ilişkili mi? → library.addressing.media_reference_relevance → enum → unknown
Bu haberin kaynak gösterimi açık mı, kapalı mı? → library.addressing.attribution_clarity → enum → unknown.Bu haber kaynak gösterimi var ama muğlak mı? → library.addressing.attribution_ambiguity → boolean → unknown

BÖLÜM C — Kaynak Kimliği ve Doğruluk Profili
Bu haber tek kaynak mı çoklu kaynak mı? → source.profile.count → enum(single,multi,unknown) → unknown,Bu haberin kaynakları birbirini doğruluyor mu yoksa ayrışıyor mu? → source.profile.consensus → enum(confirming,diverging,mixed,unknown) → unknown
Bu haber farklı kaynaklarda aynı gün çıktı mı? → source.profile.same_day_crosspost → boolean → unknown,Bu haberin birincil kaynağı resmî mi gayriresmî mi? → source.primary.officiality → enum(official,unofficial,unknown) → unknown
Bu haber hangi yayın_organı_ref ile eşleşti? → source.publisher.ref_id → string → unknown,Bu yayın organı allowlist içinde mi? → source.publisher.allowlist_status → enum(allowlisted,not_allowlisted,unknown) → unknown
Bu yayın organı lig özelinde düzenli haber üretmiş mi? → source.publisher.league_regular → boolean → unknown,Bu yayın organı takım özelinde aşırı yoğun haber üretiyor mu? → source.publisher.team_overconcentration → boolean → unknown
Bu haberin yazarı/editörü adı metinden çekilebildi mi? → source.author.name_extracted → boolean → unknown,Bu haberin yazarı/editörü map edilebildi mi? → source.author.mapped → boolean → unknown
Bu haber “staff writer” gibi anonim bir yazar mı? → source.author.anonymous_staff_writer → boolean → unknown,Bu haber “editorial desk” gibi toplu editoryal imza mı? → source.author.editorial_desk_signature → boolean → unknown
Bu yazar için örneklem yeterli mi, low sample mı? → source.author.sample_sufficiency → enum(sufficient,low_sample,unknown) → unknown,Bu yazar geçmişte aynı tema türünde isabetli mi? → source.author.theme_hit_history → enum(accurate,noisy,unknown) → unknown
Bu yayın organı haberleri maç sonrası yeniden yazma eğilimi taşıyor mu? → source.publisher.post_match_rewrite_tendency → boolean → unknown,Bu haber bir düzeltme (correction) içeriyor mu? → source.article.contains_correction → boolean → unknown
Bu haber bir yalanlama (denial) içeriyor mu? → source.article.contains_denial → boolean → unknown,Bu haber bir resmi açıklama alıntısı içeriyor mu? → source.article.contains_official_statement_quote → boolean → unknown
Bu haberin birincil kaynağı kulüp mü? → source.primary.entity_type → enum(club,federation,player,agent,coach,unknown) → unknown,Bu haber maçtan sonra doğrulandı mı? → source.lifecycle.post_match_confirmed → boolean → unknown
Bu haber maçtan sonra çöktü mü? → source.lifecycle.post_match_collapsed → boolean → unknown,Bu haber daha sonra düzeltildi mi? → source.lifecycle.later_corrected → boolean → unknown
Bu haber birden fazla kez farklı sürümle yayınlandı mı? → source.lifecycle.multiple_versions_published → boolean → unknown
Bu haber çelişkili bilgi içeriyor mu? → source.contradiction.present → boolean → unknown,Bu çelişki “tarih” mi “isim” mi “kulüp” mü “rakam” mı? → source.contradiction.type → enum(date,name,club,number,unknown) → unknown
Bu haberin kanıt zinciri kalitesi yeterli mi yoksa yalnız bağlam mı? → source.evidence.chain_quality → enum(sufficient,context_only,unknown) → unknown,Bu haber “ilk sinyal” mi “sonradan hikâye” mi? → source.signal.stage → enum(first_signal,late_story,unknown) → unknown

BÖLÜM D — Tema Sınıflandırma
Bu haberin ana teması yönetim mi? → theme.primary.governance → boolean → unknown.Bu haberin ana teması finans mı? → theme.primary.finance → boolean → unknown.Bu haberin ana teması transfer mi? → theme.primary.transfer → boolean → unknown
Bu haberin ana teması sakatlık mı? → theme.primary.injury → boolean → unknowniBu haberin ana teması kadro seçimi mi? → theme.primary.lineup_selection → boolean → unknowniBu haberin ana teması teknik direktör kararı mı? → theme.primary.coach_decision → boolean → unknown
Bu haberin ana teması taktik/oyun planı mı? → theme.primary.tactics_gameplan → boolean → unknowniBu haberin ana teması disiplin/ceza mı? → theme.primary.discipline_sanction → boolean → unknowni 
Bu haberin ana teması hakem/VAR mi? → theme.primary.referee_var → boolean → unknown.Bu haberin ana teması taraftar/tribün mü? → theme.primary.fans_stands → boolean → unknown.Bu haberin ana teması antrenman/kamp mı? → theme.primary.training_camp → boolean → unknown.
Bu haberin ana teması içkriz/soyunaodasımıtheme.primary.internal_crisis_lockeroom → boolean → unknown.Bu haberin ana teması basın toplantısı mı? → theme.primary.press_conference → boolean → unknown
Bu haberin ana teması kulüp içi çatışma mı? → theme.primary.internal_conflict → boolean → unknown.Bu haberin ana teması yayıncı/TV anlaşmazlığı mı? → theme.primary.broadcaster_tv_dispute → boolean → unknown.
Bu haberin ana teması federasyon kararı mı? → theme.primary.federation_decision → boolean → unknown.Bu haberin ana teması ceza kurulu kararı mı? → theme.primary.disciplinary_board_decision → boolean → unknown
Bu haberin ana teması güvenlik olayları mı? → theme.primary.security_incidents → boolean → unknown.Bu haberin ana teması saha dışı skandal mı? → theme.primary.off_field_scandal → boolean → unknown
Bu haberin ana teması doping iddiası mı? → theme.primary.doping_allegation → boolean → unknown.Bu haberin ana teması altyapı/genç oyuncu mu? → theme.primary.youth_academy → boolean → unknown
Bu haberin ana teması milli takım çağrısı mı? → theme.primary.national_team_callup → boolean → unknown.Bu haber birden fazla ana tema taşıyor mu? → theme.primary.multiple → boolean → unknown

BÖLÜM E — Ton ve Yönlendirme Bantları
Bu haber tonu olumlu mu? → tone.sentiment.positive → boolean → unknown.Bu haber tonu olumsuz mu? → tone.sentiment.negative → boolean → unknown.Bu haber tonu karma mı? → tone.sentiment.mixed → boolean → unknown
Bu haber tonu nötr mü? → tone.sentiment.neutral → boolean → unknown.Bu haber dili provokatif mi? → tone.direction.provocative → boolean → unknown.Bu haber dili sakin mi? → tone.direction.calm → boolean → unknown
Bu haber dili panik üretiyor mu? → tone.direction.panic_amplifying → boolean → unknown.Bu haber dili güven telkin ediyor mu? → tone.direction.reassuring → boolean → unknown.Bu haber dili baskı üretiyor mu? → tone.direction.pressure_building → boolean → unknown
Bu haber dili “kriz büyütme” eğilimi taşıyor mu? → tone.bias.crisis_escalation → boolean → unknown.Bu haber dili “yumuşatma / toparlama” eğilimi taşıyor mu? → tone.bias.de_escalation → boolean → unknown
Bu haber içinde doğrudan hedef gösterme var mı? → tone.risk.direct_targeting → boolean → unknown.Bu haber içinde kişisel saldırı dili var mı? → tone.risk.personal_attack → boolean → unknown
Bu haber içinde taraftarı kışkırtan ifade var mı? → tone.risk.fan_incitement → boolean → unknown.Bu haber içinde kulüp yönetimine açık çağrı var mı? → tone.risk.management_callout → boolean → unknown
Bu haber içinde teknik direktöre istifa baskısı var mı? → tone.risk.coach_resignation_pressure → boolean → unknown.Bu haber içinde oyuncuya yönelik disiplin baskısı var mı? → tone.risk.player_discipline_pressure → boolean → unknown
Bu haber içinde hakem hedef gösterme var mı? → tone.risk.referee_targeting → boolean → unknown.Bu haber içinde federasyon hedef gösterme var mı? → tone.risk.federation_targeting → boolean → unknown
Bu haber içinde “son dakika” dili var mı? → tone.claim.breaking_news → boolean → unknown.Bu haber içinde “kesin bilgi” iddiası var mı? → tone.claim.certainty_assertion → boolean → unknown
Bu haber içinde “kulüp kaynakları” gibi muğlak kaynak dili var mı? → tone.claim.vague_source_language → boolean → unknown.Bu haber dili “tehdit” çağrışımı taşıyor mu? → tone.association.threat_imagery → boolean → unknown
Bu haber dili “linç” çağrışımı taşıyor mu? → tone.association.mobbing_imagery → boolean → unknown

BÖLÜM F — Takım Genel Haberi
Bu haber kulüp yönetimiyle mi ilgili? → team.news.club.management_related → boolean → unknown.Bu haber sportif direktör veya üst yönetim kararlarını içeriyor mu? → team.news.club.executive_decision_included → boolean → unknown
Bu haber takımın sezon hedefini değiştiren bir söylem taşıyor mu? → team.news.season_goal.change_signal → boolean → unknown.Bu haber hedef değişimi “yüksek hedef” mi “hedef düşürme” mi? → team.news.season_goal.change_direction → enum → unknown
Bu haber kadro istikrarını etkileyen bir problem içeriyor mu?→ team.news.squad.stability_issue_present→ boolean→ unknown.Bu haber kadro istikrarını etkileyen problem “saklık yoğunluğu”mu“transfer belirsizliği” mi? → team.news.squad.stability_issue_type → enum → unknown
Bu haber oyuncu huzursuzluğu veya soyunma odası gerilimi teması taşıyor mu? → team.news.lockeroom.tension_present → boolean → unknown.Bu haber “hoca” ile “oyuncu grubu” gerilimi mi? → team.news.lockeroom.tension_coach_vs_group → boolean → unknown
Bu haber “oyuncu-oyuncu” gerilimi mi? → team.news.lockeroom.tension_player_vs_player → boolean → unknown.Bu haber takım içinde “liderlik boşluğu” teması taşıyor mu? → team.news.squad.leadership_vacuum_present → boolean → unknown
Bu haber takımın iç disipliniyle ilgili bir karar içeriyor mu? → team.news.discipline.decision_present → boolean → unknown.Bu haber disiplin kararı “ceza” mı “uyarı” mı? → team.news.discipline.decision_type → enum → unknown
Bu haber antrenman düzeninde değişiklik içeriyor mu? → team.news.training.schedule_change_present → boolean → unknown.Bu haber antrenman değişikliği “saat” mi “yük” mü “metot” mu? → team.news.training.change_type → enum → unknown
Bu haber kamp / seyahat / hazırlık programı içeriyor mu? → team.news.prep.program_change_present → boolean → unknown.Bu haber hazırlık programı “iptal” mi “uzama” mı “yer değişimi” mi? → team.news.prep.program_change_type → enum → unknown
Bu haber yoğun fikstür veya yorgunluk teması taşıyor mu? → team.news.fatigue.fixture_congestion_theme → boolean → unknown.Bu haber rotasyon planını etkileyen bir baskı içeriyor mu? → team.news.rotation.pressure_present → boolean → unknown
Bu haber rotasyon baskısı “zorunlu” mu “tercih” mi? → team.news.rotation.pressure_type → enum → unknown.Bu haber kulübün ekonomik durumu veya maaş ödemeleriyle ilgili mi? → team.news.finance.salary_payment_related → boolean → unknown
Bu haber maaş konusu “gecikme” mi “eksik ödeme” mi “tam ödeme” mi? → team.news.finance.salary_payment_status → enum → unknown.Bu haber prim / bonus / ödeme gecikmesi gibi motivasyon etkisi taşıyor mu? → team.news.finance.motivation_payment_issue → boolean → unknown
Bu haber takım içinde gruplar oluştuğu iddiası taşıyor mu? → team.news.lockeroom.factions_claim_present → boolean → unknown.Bu haber gruplar “yerli-yabancı” mı “genç-yaşlı” mı? → team.news.lockeroom.factions_type → enum → unknown
Bu haber oyuncuların teknik direktöre güveni teması taşıyor mu? → team.news.coach.trust_theme_present → boolean → unknown.Bu haber yönetim-teknik ekip çatışması içeriyor mu? → team.news.club.board_vs_staff_conflict → boolean → unknown
Bu haber taraftar baskısının kulüp kararlarını etkilediğini söylüyor mu? → team.news.fan_pressure.affects_decisions → boolean → unknown.Bu haber takımın kadro dışı kararlarını içeriyor mu? → team.news.squad.exclusion_decision_present → boolean → unknown
Bu haber kadro dışı “disiplin” mi “performans” mı “transfer” mi? → team.news.squad.exclusion_reason → enum → unknown.Bu haber takımın sakatlık yönetimiyle ilgili bir problem içeriyor mu? → team.news.medical.injury_management_issue → boolean → unknown
Bu haber sakatlık yönetimi “yanlış yükleme” iddiası mı? → team.news.medical.wrong_load_claim → boolean → unknown.Bu haber kulüp içinde hukuki süreç / dava / ceza içeriyor mu? → team.news.club.legal_process_present → boolean → unknown
Bu haber hukuki süreç “para cezası” mı “transfer yasağı” mı? → team.news.club.legal_process_type → enum → unknown.Bu haber kulüp içi güvenlik / tesis / stat problemi içeriyor mu? → team.news.club.facility_or_stadium_issue → boolean → unknown
Bu haber stat sorunu “zemin” mi “seyirci” mi “güvenlik” mi? → team.news.club.stadium_issue_type → enum → unknown.Bu haber takımın iç saha atmosferini büyüten bir gündem mi? → team.news.home.atmosphere_pressure_theme → boolean → unknown
Bu haber takımın deplasman baskısını büyüten bir gündem mi? → team.news.away.pressure_theme → boolean → unknown

BÖLÜM G — Teknik Direktör Haberi
Bu haberin hedefi teknik direktör mü? → coach.target.is_head_coach → boolean → unknown.Bu haber teknik direktörün görev güvenliğiyle mi ilgili? → coach.job_security.is_topic → boolean → unknown
Bu haber “istifa” mı “kovulma” mı “ultimatom” mu? → coach.job_security.outcome_type → enum(resignation,sacked,ultimatum,unknown) → unknown.Bu haber teknik direktörün yönetimle gerilim yaşadığını söylüyor mu? → coach.tension.with_board.is_claimed → boolean → unknown
Bu haber gerilim “transfer” mi “hedef” mi “yetki” mi?→ coach.tension.with_board.topic → enum(transfer,targets,authority,unknown) → unknown.Bu haber teknik direktörün oyuncularla gerilim yaşadığını söylüyor mu? → coach.tension.with_players.is_claimed → boolean → unknown
Bu haber gerilim “yıldız oyuncu” mu “grup” mu? → coach.tension.with_players.scope → enum(star_player,group,unknown) → unknown.Bu haber teknik direktörün basın toplantısı çıkışı mı? → coach.media.is_press_conference → boolean → unknown
Bu haber teknik direktörün maç öncesi plan beyanı içeriyor mu? → coach.statements.pre_match_plan.is_included → boolean → unknown.Bu haber teknik direktörün maç sonrası açıklaması mı? → coach.media.is_post_match_statement → boolean → unknown
Bu haber teknik direktörün hakem/VAR açıklaması içeriyor mu? → coach.officials.ref_var.is_included → boolean → unknown.Bu haber hakem/VAR açıklaması “sakin” mi “sert” mi? → coach.officials.ref_var.tone → enum(calm,harsh,unknown) → unknown
Bu haber teknik direktörün kadro seçiminde zorlandığını söylüyor mu?,coach.squad_selection.is_struggling_claimed,boolean,unknown.Bu haber zorlanma“sakatlık” mı“yorgunluk” mu“ceza” mı?→coach.squad_selection.struggle_reason→enum(injury,fatigue,suspension,unknown→ unknown
Bu haber teknik direktörün rotasyon tercihleriyle ilgili mi? → coach.rotation.is_topic → boolean → unknown.Bu haber teknik direktörün oyuncu disiplini yaklaşımıyla ilgili mi? → coach.discipline.is_topic → boolean → unknown
Bu haber disiplin yaklaşımı “sertleşme” mi “yumuşama” mı? → coach.discipline.direction → enum(stricter,softer,unknown) → unknown.Bu haber teknik direktörün kendi ekibinde değişiklik yapacağını söylüyor mu? → coach.staff_changes.is_planned_claimed → boolean → unknown
Bu haber teknik direktörün antrenman metodu değişimini söylüyor mu? → coach.training_method.change_claimed → boolean → unknown.Bu haber teknik direktörün “takım ruhu / birlik” mesajı mı? → coach.messaging.team_unity.is_emphasized → boolean → unknown
Bu haber teknik direktörün “kriz yönetimi” kapasitesini test eden bir gündem mi? → coach.crisis_management.is_test_topic → boolean → unknown.Bu haber teknik direktörün “bahane” dili taşıdığı iddiası mı? → coach.messaging.excuse_tone.is_claimed → boolean → unknown

BÖLÜM H — Futbolcu Haberi
Bu haberin hedefi futbolcu mu? → player.target.is_player → boolean → unknown.Bu haber futbolcunun sakatlığıyla mı ilgili? → player.injury.is_related → boolean → unknown
Bu haber sakatlık “kas” mı “darbe” mi “kronik” mi? → player.injury.type → enum → unknown.Bu haber futbolcunun sakatlıktan dönüş süreciyle mi ilgili? → player.injury.recovery.is_related → boolean → unknown
Bu haber dönüş süreci “takım antrenmanı” mı “bireysel çalışma” mı? → player.injury.recovery.mode → enum → unknown.Bu haber futbolcunun “oynar/oynamaz” netliği taşıyor mu? → player.availability.has_clarity → boolean → unknown
Bu haber netlik “kesin oynar” mı “riskli” mi “kesin yok” mu? → player.availability.clarity_level → enum → unknown.Bu haber futbolcunun cezalı duruma düşmesiyle mi ilgili? → player.suspension.is_related → boolean → unknown
Bu haber ceza “kırmızı” mı “kart birikimi” mi? → player.suspension.type → enum → unknown.Bu haber futbolcunun kadro dışı bırakılmasıyla mı ilgili? → player.squad_status.is_excluded → boolean → unknown
Bu haber kadro dışı sebebi “disiplin” mi “performans” mı? → player.squad_status.exclusion_reason → enum → unknown.Bu haber futbolcunun disiplinsiz davranışıyla mı ilgili? → player.discipline.is_related → boolean → unknown
Bu haber davranış “geç kalma” mı “kavga” mı? → player.discipline.behavior_type → enum → unknown.Bu haber futbolcunun antrenman performansı hakkında mı? → player.training.performance.is_related → boolean → unknown
Bu haber performans “düşük” mü “yüksek” mi? → player.training.performance.level → enum → unknown.Bu haber futbolcunun teknik direktörle gerilimi hakkında mı? → player.conflict.coach.is_related → boolean → unknown
Bu haber futbolcunun takım arkadaşlarıyla gerilimi hakkında mı? → player.conflict.teammates.is_related → boolean → unknown
Bu haber futbolcunun taraftarla gerilimi hakkında mı? → player.conflict.fans.is_related → boolean → unknown.Bu haber futbolcunun sosyal medya davranışı kaynaklı mı? → player.social_media.is_related → boolean → unknown
Bu haber sosyal medya “paylaşım” mı “beğeni” mi “yorum” mu? → player.social_media.action_type → enum → unknown.Bu haber futbolcunun mental yorgunluk / stres taşıdığını söylüyor mu? → player.mental_fatigue.is_related → boolean → unknown
Bu haber stres “aile” mi “performans baskısı” mı? → player.mental_fatigue.stress_source → enum → unknown
Bu haber futbolcunun transfer söylentisi mi? → player.transfer_rumor.is_related → boolean → unknown.Bu haber transfer “gidiş” mi “geliş” mi? → player.transfer_rumor.direction → enum → unknown
Bu haber futbolcunun transferinde resmiyet var mı? → player.transfer_rumor.has_officiality → boolean → unknown.Bu haber resmiyet “kulüp açıklaması” mı “menajer” mi? → player.transfer_rumor.official_source → enum → unknown
Bu haber futbolcunun maaş/prim tartışması içeriyor mu? → player.contract.payment_dispute.is_related → boolean → unknown
Bu haber tartışma “zam” mı “gecikme” mi? → player.contract.payment_dispute.type → enum → unknown.Bu haber futbolcunun “sözleşme krizi” içeriyor mu? → player.contract.crisis.is_related → boolean → unknown
Bu haber sözleşme “uzatma” mı “fesih” mi? → player.contract.crisis.type → enum → unknown

BÖLÜM I — Hakem / VAR Haberi
Bu haberin hedefi hakem mi? → news.referee_var.is_referee_targeted → boolean → unknown.Bu haber hakemin atanmasıyla mı ilgili? → news.referee_var.is_assignment_related → boolean → unknown
Bu haber atama “maç özel” mi “genel politika” mı? → news.referee_var.assignment_scope → enum → unknown.Bu haber hakemin geçmiş maç performansına dair tartışma mı? → news.referee_var.is_past_performance_discussion → boolean → unknown
Bu haber tartışma “kart” mı “penaltı” mı “VAR” mı? → news.referee_var.discussion_topic → enum → unknown.Bu haber hakemin kart standardı hakkında bir gündem mi? → news.referee_var.is_card_standard_discussion → boolean → unknown
Bu haber hakemin penaltı standardı hakkında bir gündem mi? → news.referee_var.is_penalty_standard_discussion → boolean → unknown
Bu haber hakemin VAR kararlarıyla ilgili mi? → news.referee_var.is_var_decision_discussion → boolean → unknown.Bu haber VAR hakemiyle ilgili mi? → news.referee_var.is_var_referee_related → boolean → unknown
Bu haber hakemin disiplin soruşturması iddiası mı? → news.referee_var.is_disciplinary_investigation_claim → boolean → unknown.Bu haber kulübün hakem şikâyeti mi? → news.referee_var.is_home_club_referee_complaint → boolean → unknown
Bu haber rakip kulübün hakem şikâyeti mi? → news.referee_var.is_away_club_referee_complaint → boolean → unknown.Bu haber medya tarafından “hakem baskısı” kurulması mı? → news.referee_var.is_media_referee_pressure → boolean → unknown
Bu haber hakemle ilgili “yönetim açıklaması” içeriyor mu? → news.referee_var.has_club_board_statement → boolean → unknown.Bu haber hakemle ilgili “federasyon açıklaması” içeriyor mu? → news.referee_var.has_federation_statement → boolean → unknown
Bu haber hakemle ilgili “maç sonu hedef gösterme” dili taşıyor mu? → news.referee_var.has_post_match_targeting_language → boolean → unknown.Bu haber hakem haberinde “video/kanıt dolaşımı” var mı? → news.referee_var.has_video_evidence_circulation → boolean → unknown

BÖLÜM J — Yönetim / Federasyon / Lig Politik Haberi
Bu haber federasyon kararı içeriyor mu? → news.governance.is_federation_decision → boolean → unknown.Bu haber disiplin kurulu kararı içeriyor mu? → news.governance.is_disciplinary_board_decision → boolean → unknown
Bu haber puan silme / ceza / seyirci yasağı içeriyor mu? → news.governance.has_sanction_or_ban → boolean → unknown.Bu haber ceza “seyirci” mi “puan” mı “para” mı? → news.governance.sanction_type → enum → unknown
Bu haber hükmen mağlubiyet veya itiraz süreciyle ilgili mi? → news.governance.is_forfeit_or_appeal_process → boolean → unknown.Bu haber itiraz süreci “başvuru” mu “sonuç” mu? → news.governance.appeal_stage → enum → unknown
Bu haber fikstür değişikliği içeriyor mu? → news.governance.has_fixture_change → boolean → unknown.Bu haber maç saati/stadı değişikliği içeriyor mu? → news.governance.has_kickoff_or_venue_change → boolean → unknown
Bu haber güvenlik nedeniyle maçın riskli sınıfa alınması mı? → news.governance.is_high_risk_security_classification → boolean → unknown.Bu haber kulüp lisans / finansal fair-play süreci içeriyor mu? → news.governance.is_license_or_ffp_process → boolean → unknown
Bu haber transfer yasağı / kadro kısıtı içeriyor mu?→ news.governance.has_transfer_ban_or_squad_restriction→ boolean→ unknown.Bu haber sezon planlaması / maç sıkışıklığı gibi yapısal konu mu? → news.governance.is_structural_schedule_congestion_topic → boolean → unknown
Bu haber “yabancı kuralı / kadro kuralı” değişimi gibi düzenleme mi? → news.governance.is_roster_rule_change → boolean → unknown.Bu haber saha içi değil “masa başı” etki taşıyor mu? → news.governance.is_off_field_desk_impact → boolean → unknown
Bu haberin etkisi bir sonraki maçı etkiler mi? → news.governance.affects_next_match → boolean → unknown

BÖLÜM K — Rakip / Derbi / Stres
Bu haber iki takımı aynı anda kapsıyor mu? → news.rivalry.is_both_teams_involved → boolean → unknown.Bu haber derbi baskısı teması taşıyor mu? → news.rivalry.has_derby_pressure_theme → boolean → unknown
Bu haber “prestij maçı” bandında mı? → news.rivalry.is_prestige_match_band → boolean → unknown.Bu haber “intikam maçı” bandında mı? → news.rivalry.is_revenge_match_band → boolean → unknown
Bu haber “şampiyonluk maçı” baskısı taşıyor mu? → news.rivalry.has_title_race_pressure → boolean → unknown.Bu haber “küme düşme maçı” baskısı taşıyor mu? → news.rivalry.has_relegation_pressure → boolean → unknown
Bu haber tribün güvenliği ve olay beklentisi içeriyor mu? → news.rivalry.has_crowd_security_incident_risk → boolean → unknown.Bu haber maç öncesi gerginlik artışı içeriyor mu? → news.rivalry.has_pre_match_tension_increase → boolean → unknown
Bu haber iki takım oyuncuları arasında bireysel rekabet teması mı? → news.rivalry.has_player_to_player_rivalry_theme → boolean → unknown.Bu haber iki takım koçları arasında gerilim teması mı? → news.rivalry.has_coach_to_coach_tension_theme → boolean → unknown
Bu haber maçın “kapalı gişe” baskısı taşıyor mu? → news.rivalry.has_sold_out_pressure → boolean → unknown.Bu haber maçın “seyircisiz” olması gibi atmosfer etkisi taşıyor mu? → news.rivalry.has_no_fans_atmosphere_impact → boolean → unknown
Bu haber maç öncesi provokasyon iddiası içeriyor mu?→ news.rivalry.has_pre_match_provocation_claim→ boolean→ unknown.Bu haber maç sonrası gerilimin büyüdüğünü ve bir sonraki maça taşınacağını söylüyor mu?→ news.rivalry.has_post_match_tension_carryover→ boolean→ unknown

BÖLÜM L — Taraftar Haberleri
Bu haber taraftar protestosu içeriyor mu? → fan.incident.protest.flag → boolean → unknown.Bu haber taraftarın yönetime baskısı teması mı? → fan.pressure.board.theme_flag → boolean → unknown
Bu haber taraftarın teknik direktöre baskısı teması mı? → fan.pressure.coach.theme_flag → boolean → unknown.Bu haber taraftarın belirli bir oyuncuyu hedef aldığı teması mı? → fan.pressure.player_target.theme_flag → boolean → unknown
Bu haber tribün içi kavga/gerilim içeriyor mu? → fan.incident.stands_conflict.flag → boolean → unknown.Bu haber güvenlik riski içeriyor mu? → fan.risk.security.flag → boolean → unknown
Bu haber deplasman yasağı / taraftar kısıtı içeriyor mu? → fan.restriction.away_ban.flag → boolean → unknown.Bu haber taraftarın sosyal medya linci gibi baskı içeriyor mu? → fan.pressure.social_media_mob.flag → boolean → unknown
Bu haber maç önü şehirde gerginlik içeriyor mu? → fan.incident.pre_match_city_tension.flag → boolean → unknown.Bu haber maç içinde sahaya yabancı madde/olay ihtimali taşıyor mu? → fan.risk.in_match_object_throw.flag → boolean → unknown
Bu haber taraftarın maç içi davranışını etkileyen bir çağrı mı? → fan.call.in_match_behavior_influence.flag → boolean → unknown.Bu haberin sahaya yansıması geçmişte tekrar etmiş mi? → fan.pattern.prior_repeat_on_field.flag → boolean → unknown
Bu haber belirli dönemlerde artıyor mu (kötü seri, kötü sonuç)? → fan.pattern.bad_form_period_spike.flag → boolean → unknown.Bu haber belirli maçlarda artıyor mu (derbi, final, küme düşme)? → fan.pattern.high_stakes_match_spike.flag → boolean → unknown
Bu haberin yarattığı baskı kart/tempo/disiplin bandına yansıyor mu? → fan.impact.cards_tempo_discipline_band.flag → boolean → unknown

BÖLÜM M — Veri Kalitesi / Bozulma Kontrol
Bu haber kaydı complete mi, partial mi, incomplete mi, low mu? → quality.data_quality_badge → enum → unknown.Bu haberin missing_fields listesi çıkarıldı mı? → quality.missing_fields.extracted_flag → boolean → unknown
Bu haber kaynağı belirsiz mi? → quality.source.unknown_flag → boolean → unknown.Bu haber yazarı belirsiz mi? → quality.author.unknown_flag → boolean → unknown
Bu haber tarih hizası belirsiz mi? → quality.time_alignment.uncertain_flag → boolean → unknown.Bu haber team_ref’e map edilemedi mi? → quality.mapping.team_ref.unmapped_flag → boolean → unknown
Bu haber lig_ref’e map edilemedi mi? → quality.mapping.league_ref.unmapped_flag → boolean → unknown.Bu haber country_ref’e map edilemedi mi? → quality.mapping.country_ref.unmapped_flag → boolean → unknown
Bu haber match_ref’e map edilemedi mi? → quality.mapping.match_ref.unmapped_flag → boolean → unknown.Bu haber tekilleştirme başarısız mı kaldı? → quality.deduplication.failed_flag → boolean → unknown
Bu haber çelişkili bilgi içeriyor mu? → quality.consistency.conflict_flag → boolean → unknown.Bu haber “kanıt zinciri” için yalnız bağlam olarak mı işaretlendi? → quality.evidence_chain.context_only_flag → boolean → unknown
Bu haber “doğrulanmış veri” olarak işaretlenebildi mi? → quality.verification.verified_flag → boolean → unknown.Bu haberin doğrulanma yöntemi tek kaynak mı, çoklu kaynak mı? → quality.verification.method → enum → unknown
Bu haber “sonradan yanlışlandığı” tespit edildi mi? → quality.verification.later_refuted_flag → boolean → unknown

KURAL BLOĞU — Event Eksik / Basın Çapraz Okuma
Bu haber kaydı complete mi, partial mi, incomplete mi, low mu? → quality.data_quality_badge → enum → unknown.Bu haberin missing_fields listesi çıkarıldı mı? → quality.missing_fields.extracted_flag → boolean → unknown
Bu haber kaynağı belirsiz mi? → quality.source.unknown_flag → boolean → unknown.bu haber yazarı belirsiz mi? → quality.author.unknown_flag → boolean → unknown
Bu haber tarih hizası belirsiz mi? → quality.time_alignment.uncertain_flag → boolean → unknown.Bu haber team_ref’e map edilemedi mi? → quality.mapping.team_ref.unmapped_flag → boolean → unknown
Bu haber lig_ref’e map edilemedi mi? → quality.mapping.league_ref.unmapped_flag → boolean → unknown.Bu haber country_ref’e map edilemedi mi? → quality.mapping.country_ref.unmapped_flag → boolean → unknown
Bu haber match_ref’e map edilemedi mi? → quality.mapping.match_ref.unmapped_flag → boolean → boolean → unknown.Bu haber tekilleştirme başarısız mı kaldı? → quality.deduplication.failed_flag → boolean → unknown
Bu haber çelişkili bilgi içeriyor mu? → quality.consistency.conflict_flag → boolean → unknown.Bu haber “kanıt zinciri” için yalnız bağlam olarak mı işaretlendi? → quality.evidence_chain.context_only_flag → boolean → unknown
Bu haber “doğrulanmış veri” olarak işaretlenebildi mi? → quality.verification.verified_flag → boolean → unknown.Bu haberin doğrulanma yöntemi tek kaynak mı, çoklu kaynak mı? → quality.verification.method → enum → unknown
Bu haber “sonradan yanlışlandığı” tespit edildi mi? → quality.verification.later_refuted_flag → boolean → unknow

FAZ-24  MATCH SUPPORT TRACE FIELDS v1.0.1
support_trace.match.link_mode → enum(match_ref,team_only,unknown) → unknown.support_trace.match.match_ref → string → unknown,support_trace.match.match_ref_map_status → enum(mapped,unmapped,unknown) → unknown
support_trace.match.match_card_id → string → unknown,support_trace.match.kickoff_time_utc → timestamp_utc → unknown.support_trace.match.kickoff_same_day_flag → boolean → unknown,support_trace.news.news_id → string → unknown
support_trace.news.locked_at_utc → timestamp_utc → unknown,support_trace.news.published_at_utc → timestamp_utc → unknown.support_trace.news.recorded_at_utc → timestamp_utc → unknown,support_trace.news.publish_record_delta_minutes → integer → unknown
support_trace.news.record_vs_publish_order → enum(before,after,unknown) → unknown,support_trace.news.context_scope → enum(single_match_window,non_match_general,unknown) → unknown
support_trace.news.pre_post_window → enum(pre_match,post_match,unknown) → unknown,support_trace.news.timing_bucket → enum(pre_match,post_match,between_matches,unknown) → unknown
support_trace.refs.country_ref → string → unknown,support_trace.refs.country_ref_map_status → enum(mapped,unmapped,unknown) → unknown.support_trace.refs.league_ref → string → unknown,support_trace.refs.league_ref_map_status → enum(mapped,unmapped,unknown) → unknown

support_trace.refs.season_id→ string→ unknown,support_trace.refs.season_id_map_statu→ enum(mapped,unmapped,unknown) → unknown.support_trace.refs.team_primary_ref → string → unknown,support_trace.refs.team_primary_ref_map_status → enum(mapped,unmapped,unknown) → unknown
support_trace.context.team_binding_mode → enum(single_team,two_teams,unknown) → unknown,support_trace.refs.team_secondary_ref → string → unknown
support_trace.refs.team_secondary_ref_map_status → enum(mapped,unmapped,unknown) → unknown,support_trace.event.set_mode → enum(single_event,multi_event_set,unknown) → unknown
support_trace.event.sub_event_count → integer → unknown,support_trace.dedupe.is_duplicate_flag → boolean → unknown.support_trace.dedupe.republished_same_day_flag → boolean → unknown,support_trace.dedupe.deduplicated_flag → boolean → unknown
support_trace.dedupe.dedup_key_status → enum(mapped,unmapped,unknown) → unknown,support_trace.cross_reference.source_url_presence → boolean → unknown
support_trace.cross_reference.source_urlstring→unknown,support_trace.cross_reference.source_domain_detected→ boolean→unknown.support_trace.cross_reference.source_domain_allowlisted→ boolean→unknown,support_trace.cross_reference.canonical_url_generated→ boolean→ unknown

support_trace.cross_reference.canonical_url→string→unknown,support_trace.source.profile.count→enum(single,multi,unknown)→unknown
support_trace.source.profile.consensus → enum(confirming,diverging,mixed,unknown) → unknown,support_trace.source.profile.same_day_crosspost → boolean → unknown
support_trace.source.primary.officiality → enum(official,unofficial,unknown) → unknown,support_trace.source.publisher.ref_id → string → unknown
support_trace.source.publisher.allowlist_status → enum(allowlisted,not_allowlisted,unknown) → unknown,support_trace.source.author.name_extracted → boolean → unknown
support_trace.source.author.mapped → boolean → unknown,support_trace.source.article.contains_correction → boolean → unknown
support_trace.source.article.contains_denial → boolean → unknown,support_trace.source.article.contains_official_statement_quote → boolean → unknown

support_trace.lifecycle.post_match_confirmed → boolean → unknown,support_trace.lifecycle.post_match_collapsed → boolean → unknown
support_trace.lifecycle.later_corrected → boolean → unknown,support_trace.lifecycle.multiple_versions_published → boolean → unknown
support_trace.contradiction.present → boolean → unknown,support_trace.contradiction.type → enum(date,name,club,number,unknown) → unknown
support_trace.evidence.chain_quality → enum(sufficient,context_only,unknown) → unknown,support_trace.quality.missing_fields.extracted_flag → boolean → unknown
support_trace.quality.mapping.team_ref.unmapped_flag → boolean → unknown,support_trace.quality.mapping.league_ref.unmapped_flag → boolean → unknown

support_trace.quality.mapping.country_ref.unmapped_flag → boolean → unknown,support_trace.quality.mapping.match_ref.unmapped_flag → boolean → unknown
support_trace.quality.deduplication.failed_flag → boolean → unknown ,support_trace.quality.consistency.conflict_flag → boolean → unknown
support_trace.quality.evidence_chain.context_only_flag → boolean → unknown, support_trace.quality.verification.verified_flag → boolean → unknown
support_trace.quality.verification.later_refuted_flag → boolean → unknown, support_trace.cross_reference.news_ref_id → string → unknown
support_trace.cross_reference.match_ref_id → string → unknown ,support_trace.cross_reference.link_confidence_band → enum(low,medium,high,unknown) → unknown

ANALİZ EĞİTİM KATALOĞU + ETİKET KATALOĞU — FUTBOL (BAĞLAYICI GİRİŞ TALİMATI)
Aşağıdaki bölüm, ana uygulama promptunun bir devamıdır ve ondan bağımsız okunamaz. Bu bölüm yeni özellik eklemez, akış değiştirmez, yalnız futbol branşı için “analistin nasıl okuyacağı” ve “kütüphanecinin hangi sözlükle etiketleyeceği” disiplinini bağlayıcı biçimde kilitler. Kod yazarı bu metni yorumlayamaz, sadeleştiremez, kısaltamaz, kendi mantığıyla yeniden yazamaz; burada geçen tüm soru katalogları ve etiket katalogları birebir uygulanır.

Bu bölüm iki parçadan oluşur ve sırası değiştirilemez. Birinci parça “Futbol Analiz Eğitim Kataloğu (Soru Katalogları)”dır; analist, örüntü uzmanı ve ilgili kontrol rolleri bu soru setlerini ezberlemez, bu soru setlerine göre bakış açısını standardize eder ve hiçbir değerlendirme bu soruların dışında keyfi biçimde yapılamaz. İkinci parça “Futbol Etiket Kataloğu (Kütüphane Sözlüğü)”dür; kütüphaneci, maç izleme hattı ve örüntü hattı yalnız bu sözlükte tanımlı etiket adlarını ve bu etiketlerin izinli değer bantlarını kullanarak kayıt üretir, bu sözlük dışı tek bir etiket uydurulamaz.

Soru katalogları “etiket değildir” ve doğrudan raflara yazılmaz; soru katalogları, hangi verinin hangi kartlarda aranacağını ve hangi bağlamların okunacağını tanımlar. Etiket kataloğu ise soru kataloglarının cevabını deterministik alanlara döken tek geçerli sözlüktür. Bir soruya karşılık gelen etiket alanı boş kalıyorsa bu “bilinmiyor” veya “unknown” bantlarıyla işaretlenir, asla varsayımla doldurulmaz. Hiçbir birim soru kataloglarını okuyup yalnız bu metin üzerinden hüküm kuramaz; tüm değerlendirmeler kanıt zinciri tamamlandıktan sonra yapılır.

Bu kataloglar, futbol branşı için üç ana kart sınıfına bağlanır: maç kartı, takım DNA kartı ve ilgili kişi kartları (teknik direktör, hakem, futbolcu). Maç kartı tekil maçın olay izini taşır. Takım DNA kartı, tekil maçlardan türetilen tekrar eden refleksleri ve davranış bantlarını taşır. Kişi kartları ise bireysel davranış profillerini taşır ve kulüp değişse bile kimlik sürekliliğini korur. Bu ayrım korunur; takım kartı ile maç kartı karıştırılamaz.

Durum etiketleri karar vermez. Etiketler yalnız sınıflandırma ve raf adreslemesi içindir. Analist dahil hiçbir rol, yalnız etiketlere bakarak “kolaycılık” ile sonuca gidemez. Etiketler yalnızca araştırmayı hızlandıran işaretlerdir; hüküm, yalnızca kaynak tutarlılığı, tekrar, şart bağımlılığı ve kanıt zinciri tamamlandıktan sonra üretilir. Bu bölümün amacı hız değil; yanlış hızla oluşan sessiz bozulmayı engelleyen deterministik bir analiz disiplini kurmaktır.

FAZ-32
BAĞLAM DUVARI VE ADRES SORULARI (FUTBOL)
Bu kayıt hangi tarih penceresinde ve hangi UTC standardında sabitleniyor? Bu soru, tüm zaman hesaplarının tek standarda bağlanması içindir. Tarih penceresi sabitlenmeden sezon fazı, haber penceresi ve maç segmentleri doğru kurulamaz.
Bu kayıt hangi ülke, hangi lig, hangi sezon ve hangi tekil takım kimliği içinde okunuyor? Bu soru, raf adresinin yanlış klasöre düşmesini engeller. Ülke/lig/sezon/takım net değilse aynı isimli ligler veya sezon kaymaları sessiz bozulma üretir.

Bu kayıt lig seviyesinde hangi kütüphaneye aittir (Tier-1, Tier-2 veya Cups)? Bu soru, verinin hangi raf disiplininde tutulacağını kilitler. Tier-1, Tier-2 ve Cups verisi aynı raflarda birleştirilemez; birleştirme sessiz karışma üretir.

Bu kayıt hangi organizasyon tipine aittir (lig, ulusal kupa, kıtasal kupa, süper kupa, milli takım turnuvası)? Bu soru, maçın ve haber akışının hangi organizasyon bağlamında okunacağını belirler. Organizasyon tipi net değilse kupa maçları lig performansına yanlış bağlanır.

Bu kayıt kupa bayrağı taşır mı ve kupa bayrağı hangi seviyededir (domestic\\\_cup veya continental\\\_cup)? Bu soru, kupa verisini ayrı bir sistemde tutmak içindir. Kupa bayrağı yoksa kupa haberleri ve kupa maçları lig akışına karışır ve takım DNA’sı yanlış öğrenilir.
Bu kayıt sezonun hangi fazına denk geliyor (sezon başı, sezon ortası, sezon sonu, sezon arası/off-season)? Bu soru, aynı davranışın sezonun farklı dönemlerinde neden değiştiğini ayırt etmek içindir. Sezon arası dönem, transfer ve kamp etkileri nedeniyle ayrı bağlam olarak tutulur.

Bu kayıt sezon içi mi yoksa sezon arası haftalık paket mi? Bu soru, veri türünü deterministik ayırmak içindir. Sezon arası haber akışı günlük maç akışı gibi işlenmez; haftalık paketlenir ve bağlam rafına yazılır.
Bu kayıt hangi tekil takım perspektifi için açılıyor? Bu soru DNA kartı okuma girişidir. Takım perspektifinde hedef, tek takımı öğrenmek ve takım kartını büyütmektir; rakip burada bağlamdır, kimlik değildir.

Bu kayıt hangi tekil maç perspektifi için açılıyor? Bu soru maç olayı okuma girişidir. Maç perspektifinde hedef, maç kimliğini ve maçın olay zincirini sabitlemektir; bu kayıt daha sonra iki takımın geçmiş eşleşme okumasında referans olur.
Bu kayıt takım perspektifinde açılıyorsa o tarihte takımın teknik direktör kimliği kim? Bu soru, takım davranış değişimini kişi kartlarına bağlamak içindir. Teknik direktör doğru sabitlenmezse takım DNA’sı yanlış kişiye bağlanır ve örüntü bozulur.
Bu kayıt maç perspektifinde açılıyorsa bu maçın hakemi kim? Bu soru, hakemin maç içi disiplin bandını ve karar akışını deterministik bağlamak içindir. Hakem maç nesnesinin parçasıdır ve maç kırılmalarının okunmasında ayrı bir kimliktir.

Bu kayıt takım perspektifinde açılıyorsa takımın bu maç dışında paralel yükü var mı (yakın takvimde başka organizasyon maçı)? Bu soru, takım performansının gerçek bağlamını okumak içindir. Takımın aynı hafta kupa/Avrupa/milli takım dönüşü gibi ek yükleri varsa tempo ve risk davranışı kayabilir.
Bu kayıt takım perspektifinde açılıyorsa takım kadrosunda milli takım dönüşü, seyahat yoğunluğu veya kadro bölünmesi var mı? Bu soru, oyuncu ve takım DNA’sını bozan dış yükleri ayırt etmek içindir. Bu tür yükler yok sayılırsa performans sapması yanlış nedene bağlanır.

Bu maç lig mi kupa mı ve maçın önem sınıfı hangi bantta? Bu soru, aynı takım ama farklı stres sınıfı ayrımını yapar. Maç önemi yoksa benzer görünen maçlar yanlış eşleştirilir.
Bu maç ev/deplasman bağlamında hangi atmosfer sınıfında ve saha koşulu hangi davranış bandına yazılıyor? Bu soru, taraftar baskısı ve saha koşullarının takım davranışını nasıl kaydırdığını ölçmek içindir. Atmosfer sınıfı yoksa normal görünen sapmaların gerçek nedeni kaçabilir.
Bu kayıt tam çözünürlük sezon kaydı mı yoksa iskelet sezon kaydı mı? Bu soru, hangi alt rafların zorunlu dolması gerektiğini belirler. İskelet sezonda bazı alanların boş kalması normal kabul edilir; tam çözünürlük sezonda boşluk data\\\_quality olarak işaretlenir.

MAÇI SEGMENTLERE AYIRAN DNA OKUMA SORULARI (FUTBOL)
Bu maç 90 dakika tek blok olarak okunmaz; deterministik segmentlere bölünür ve her segment için takımın davranış izi ayrı ayrı kaydedilir. Amaç “maç anlatmak” değil, takım DNA’sının hangi zaman dilimlerinde nasıl tepki verdiğini raf hafızasına yerleştirmektir. Segment okuması, kolay maçta yüzey taraması sağlar; zor maçta doğru katmana hızlı iniş verir.
Takımın ilk 15 dakikadaki davranışı nedir ve bu davranış beş yıl boyunca tekrar ediyor mu? Bu soru, takımın maç başlangıç refleksini ölçer. Bazı takımlar sistematik hızlı başlar, bazıları sistematik geç açılır; bu fark sapma okumasında temel bağlamdır.

Takımın 16–30 dakikadaki davranışı nedir ve ilk 15’e göre tempo veya disiplin yön değiştiriyor mu? Bu soru, ilk dalga geçtikten sonra takımın stabilize olup olmadığını gösterir. Eğer bu dilimde kayma oluyorsa kırılma daha erken başlamış olabilir.
Takımın 31–45 dakikadaki davranışı nedir ve devreye giderken risk seviyesi artıyor mu azalıyor mu? Bu soru, ilk yarı kapanış davranışını ölçer. Devre öncesi kartlar, VAR kararları ve skor kırılmaları bu dilimde kader değiştirici çalışabilir.

Takımın devre geçişi davranışı nedir ve ikinci yarıya çıkış refleksi hangi bantta? Bu soru, teknik direktör müdahalesinin ve oyuncu psikolojisinin en net okunduğu eşiktir. Devre çıkışı tempo spike veya çöküş tekrar ediyorsa DNA sinyali güçlenir.
Takımın 46–60 dakikadaki davranışı nedir ve bu dilim takımın tekrar eden “ikinci yarı başlangıç bandı” mı? Bu soru, ikinci yarı başında oluşan sistematik davranışları yakalar. Bazı takımlar bu bantta sürekli baskı yer veya sürekli baskı kurar.

Takımın 61–75 dakikadaki davranışı nedir ve maçın kaderini taşıyan değişimler bu dilimde mi birikiyor? Bu soru, yorgunluk, değişiklikler ve kart birikiminin davranışa yansıdığı orta-son evreyi ölçer. Bu bantta sürekli yön değişiyorsa sapma penceresi genişliyor olabilir.
Takımın son 15 dakikadaki davranışı nedir ve bu davranış skor durumuna göre deterministik değişiyor mu? Bu soru, maç kapatma DNA’sını ölçer. Önde kapatma, geride risk alma veya beraberliğe razı olma davranışları bu segmentte görünür.
Takımın son 5 dakikası ve uzatma dakikalarındaki davranışı nedir ve bu davranış tekrarlı bir panik/soğutma profili üretiyor mu? Bu soru, en yüksek stres anındaki davranışı ölçer. Tek maçta bile kritik olabilir; tekrar ediyorsa DNA’ya dönüşür.

Bu maç segmentlerinde takımın tempo bandı nasıl değişiyor ve tempo değişimi hangi olaylarla eşleşiyor? Bu soru, segment okumasını olay zinciriyle bağlar. Tempo her zaman kendi kendine değişmez; tetikleyiciyle değişir.
Bu maç segmentlerinde takımın disiplin bandı nasıl değişiyor ve kart/faul yoğunluğu hangi dilimde kümeleniyor? Bu soru, takımın sertlik ve kontrol profilini segment bazında çıkarır. Kart davranışı “maç geneli” değil, segment davranışıdır.
Bu maç segmentlerinde takımın karar kalitesi nasıl değişiyor ve hata kümelenmesi hangi dilimde oluşuyor? Bu soru, “sapma”nın çoğu zaman karar kalitesi düşüşüyle başladığını yakalamak içindir. Hata kümelenmesi segment adresi verirse derin okuma hızlanır.

Bu maçta skor durumu segment davranışını nasıl değiştiriyor (öndeyken, beraberken, gerideyken)? Bu soru, aynı segmentin farklı skor bağlamında farklı DNA ürettiğini ayırır. Önde kapatan takım geride dağılabilir; bu ayrım sabitlenmelidir.
Bu maçta maçın kaderi hangi segmentte kırıldı ve kırılma anı hangi tetikleyicilerle başladı? Bu soru, segmentleri yalnız “zaman” değil “kader değişimi” olarak da bağlar. Kırılma segmenti doğru bulunursa analiz raf içinde doğru yere iner.
Bu maçta bir segment içinde “normal bant dışına çıkış” olduysa, bu çıkışın başlangıç işareti neydi? Bu soru, sapmayı en başından yakalamak içindir. Çıkışın ilk işareti kaçarsa sistem yalnız sonuç okur, süreç okuyamaz.

Bu maçta segment davranışı, sezon fazı ve organizasyon tipiyle tutarlı mı yoksa o gün “başka bir takım” gibi mi çalıştı? Bu soru, bağlam duvarı ile segment okumasını birleştirir. Aynı takım ligde başka, kupada başka DNA gösterebilir; bu ayrım kilitlenir.
Takımın bir önceki maç sonucu bir sonraki haftayı deterministik şekilde etkiliyor mu? Bu soru, takımın “sonuç hafızası” olup olmadığını ölçer. Bazı takımlar galibiyet sonrası açılır, bazıları mağlubiyet sonrası toparlanır, bazıları ise seri içine girer.

Takımın galibiyet, beraberlik ve mağlubiyet serisi davranışı var mı ve bu seri davranışı tekrar ediyor mu? Bu soru, takımın karakteristik dalga yapısını yakalar. Seri davranışı varsa takımın risk ve tempo profili seri içinde değişebilir.
Takımın maçlara “yenileceğini bilerek rahat oynama” mı yoksa “beraberliği kurtarma” refleksiyle mi çıktığı tekrar ediyor mu? Bu soru, takımın psikolojik hedef bandını ölçer. Aynı lig ve sezon fazında bu refleks tekrar ediyorsa DNA sinyali güçlenir.
Takımın sezon içi konum baskısı var mı (küme düşme hattı, Avrupa potası, şampiyonluk baskısı) ve bu baskı segment davranışını değiştiriyor mu? Bu soru, takımın stres sınıfını belirler. Aynı takım farklı tabloda farklı oynar; bu bağlam yok sayılırsa sapma yanlış okunur.

Takımın cezalı oyuncu veya cezalı teknik ekip durumu var mı ve bu durum maç içi davranışı kaydırıyor mu? Bu soru, kadro bütünlüğü ve disiplin yükünü ölçer. Cezalı eksikliği çoğu zaman kart-tempo-kontrol profilini değiştirir.
Takımın Avrupa/kıtasal maç yoğunluğu var mı ve bu yoğunluk lig maçında segment davranışına yansıyor mu? Bu soru, paralel yükün yorgunluk ve rotasyon etkisini ölçer. Aynı takım “Avrupa sonrası lig” haftalarında farklı DNA gösterebilir.
Bu takımın maçlarını genelde tek bir oyuncu mu “kurtarıyor” ve sonuç belirleyici rol tekilde mi kümeleniyor? Bu soru, takımın yıldız bağımlılığını ölçer. Tek oyuncu bağımlılığı varsa takımın sapma profili o oyuncunun formuna kilitlenir.
Takımın kazanma davranışı kolektif mi yoksa bir-iki oyuncunun performansına mı bağımlı? Bu soru, takımın sürdürülebilirlik profilini çıkarır. Kolektif kazanım ile yıldız bağımlılığı aynı kader tetikleyicilerini üretmez.

Bu takımın skor üretimi belirli oyuncu üzerinden mi, yoksa sistem davranışı üzerinden mi tekrar ediyor? Bu soru, takımın “sistem takımı” mı “birey takımı” mı olduğunu raf içinde ayırır. Bu ayrım, haber ve transfer etkisini okumada belirleyicidir.
Bu takımın kritik maçlarda sonucu belirleyen oyuncuları değişiyor mu, yoksa aynı isimler tekrar ediyor mu? Bu soru, baskı anındaki rol dağılımını ölçer. Aynı isimler tekrar ediyorsa o oyuncuların kartı daha yüksek öncelikli raf nesnesi olur. 
Bunları ekledikten sonra senin dediğin şey tamamlanıyor: takımın DNA’sı sadece maç içi segment değil, maçlar arası sonuç hafızası + seri davranışı + yıldız bağımlılığı ile “kişilik” haline geliyor.

FAZ-33
MAÇ KADERİ TETİKLEYİCİLERİ SORULARI (FUTBOL) — GENİŞLETİLMİŞ KRİTİK SINIF
Bu bölümün amacı, maç içindeki olayları saymak değildir. Bu bölümün amacı, tetikleyici olayların takımın davranışını hangi döngüye soktuğunu ve maçın kaderini nasıl evirdiğini adreslemektir. Bu tetikleyiciler, seyirci baskısı ve iç/dış saha bağlamıyla birleştiğinde daha da sertleşebilir; bu yüzden tetikleyiciler yalnız saha içi değil, saha çevresi etkisiyle birlikte okunur.

İlk sarı kartın geldiği an hangi segmentte oldu ve takımın disiplin eşiğini değiştiriyor mu? Bu soru, maçın sertlik bandının nereden açıldığını ölçer. İlk kartın segmenti sabitlenmeden kart davranışı doğru okunamaz.
Takım ilk yarıda kart gördüğünde davranış nasıl değişiyor, ikinci yarıda kart gördüğünde nasıl değişiyor? Bu soru, kartın etkisini maçın evresine bağlar. Aynı kart farklı segmentte tamamen farklı kader etkisi üretir.
İlk karttan sonraki 10 dakikalık blokta faul yoğunluğu ve tempo bandı artıyor mu azalıyor mu? Bu soru, kart sonrası davranış döngüsünü ölçer. Kartın kendisi kadar kart sonrası “döngüye kilitlenme” kader belirleyicidir.
Kart sonrası takım “kabullenme” moduna mı giriyor yoksa “agresif karşılık” moduna mı giriyor? Bu soru, senin tarif ettiğin psikolojik döngüyü adresler. Bazı takımlar haksızlık algısıyla sertleşir, bazıları geri çekilir ve oyun çözülür.
Kartlar tek bir oyuncuda mı kümeleniyor yoksa takım geneline mi yayılıyor ve bu dağılım oyun planını değiştiriyor mu? Bu soru, disiplin riskinin lokal mi sistemik mi olduğunu ayırır. Lokal risk oyuncu kartına, sistemik risk takım DNA’sına yazılır.

Kart gören oyuncu “bir sonraki maç ceza sınırına” girince davranışını değiştiriyor mu? Bu soru, oyuncunun bilinçli risk yönetimini ölçer. Ceza sınırındaki oyuncu ya fazla temkinli olur ya da panikleyip daha çok hata yapar.
Ceza sınırındaki oyuncu, tribün baskısı altında daha mı fazla risk alıyor yoksa daha mı fazla geri çekiliyor? Bu soru, seyirci etkisinin oyuncu karar kalitesine yansımasını ölçer. Aynı oyuncu iç sahada farklı, deplasmanda farklı davranabilir.
kımın kritik oyuncusu ceza sınırına girince teknik direktör segment içinde onu erken çıkarıyor mu? Bu soru, kart tetikleyicisinin teknik direktör kararına nasıl dönüştüğünü ölçer. Bu hamle takımın kaderini değiştirebilir.
Kırmızı kart olduysa hangi türdendi (ikinci sarı veya direkt) ve kırmızı kart sonrası ilk 5 dakikada takım çöktü mü toparladı mı? Bu soru, kriz DNA’sını çıplak biçimde gösterir. İlk 5 dakika davranışı tekrar ediyorsa kader kalıbı oluşur.
Kırmızı kart sonrası takımın risk profili nasıl değişti (savunmaya çekilme, tempo öldürme, ani kontra, panik hücum)? Bu soru, toparlanma stratejisini ölçer. Aynı takımın tekrar eden kriz stratejisi raflarda görünmelidir.
Kırmızı kart iç sahada mı oldu deplasmanda mı ve taraftar etkisi davranışı sertleştirdi mi yumuşattı mı? Bu soru, iç/dış saha ile tetikleyici birleşimini ölçer. Aynı kırmızı kart farklı atmosferde farklı kader üretir.
Tribün baskısı kırmızı kart sonrası takımı “daha çok hırçınlık” döngüsüne mi sokuyor? Bu soru, “kart doğurur kart” zincirini yakalar. Bazı takımlar baskı altında kontrol kaybına girer.

Penaltı kararı geldi mi ve bu karar hangi segmentte geldi; karar sonrası psikolojik kırılma izi oluştu mu? Bu soru, penaltının skor dışında davranış değiştirici etkisini ölçer.
Penaltı verilmedi/verildi/iptal olduysa, takım “hakem yanlı” algısına girip daha fazla kart döngüsüne giriyor mu? Bu soru, senin özellikle vurguladığın “kabullenme mi agresyon mu” mekanizmasını adresler. Bu döngü sapmanın ana kaynağı olabilir.
Penaltı kararı veya iptali sonrası tribün baskısı oyuncu davranışını bozuyor mu? Bu soru, karar tetikleyicisinin seyirciyle birleştiğinde büyümesini ölçer. İç sahada bu etki genelde daha serttir.

VAR incelemesi oldu mu, hangi karar türüne bağlandı ve VAR müdahalesi maçın ritmini kırarak tempo bandını değiştirdi mi? Bu soru, VAR’ın ritim kırıcı etkisini ölçer.
VAR sonrası takım “kafa düşmesi” döngüsüne mi giriyor yoksa “öfke yükselişi” döngüsüne mi? Bu soru, VAR tetikleyicisinin davranış yönünü belirler. Aynı olay farklı takımlarda zıt kader üretir.
İptal edilen gol oldu mu ve iptal sonrası ilk 5 dakikada takım davranışı neye döndü? Bu soru, moral kırılması veya agresyon artışı gibi kader değiştirici profilleri yakalar.
İptal edilen gol sonrası tribün baskısı oyuncu karar kalitesini düşürüyor mu? Bu soru, “küçük tetikleyici + büyük basınç” birleşimini yakalar. Zor maçların çoğu bu birleşimde çözülür.

İlk gol hangi segmentte geldi ve ilk gol takımın davranışını deterministik değiştiriyor mu? Bu soru, skor eşiğinin psikolojik etkisini ölçer.
İlk gol sonrası takımın iç saha/deplasman davranışı ayrışıyor mu? Bu soru, “iç sahada kapanma”, “deplasmanda panik” gibi ayrımları yakalar.
Beraberlik golü hangi segmentte geldi ve beraberlikten sonraki ilk 10 dakikada kopma oluşuyor mu? Bu soru, denge kırılmasının tekrar eden yönünü ölçer.
Kopma golü sonrası takım “maçı bırakma” döngüsüne mi giriyor yoksa “son bir dalga” döngüsüne mi? Bu soru, takımın mücadele profili ve çöküş eşiğini adresler.
Sakatlık veya uzun duraklama oldu mu ve bu duraklama ritmi bozarak takımın davranışını değiştirdi mi? Bu soru, ritim bozan küçük olayların kader etkisini ölçer.
Sakatlık kritik oyuncuda mı oldu ve kritik oyuncu kaybı takımın skor üretimini çökertecek kadar bağımlı mı? Bu soru, takımın “tek oyuncu bağımlılığı” ile kader tetikleyicisini birleştirir.
Time-waste davranışı görüldü mü ve hakem buna nasıl tepki verdi; tribün bunu büyüttü mü? Bu soru, kapanış stratejisi + hakem bandı + seyirci basıncı üçlüsünü birlikte okur.

Maç kaderi tetikleyicileri iç saha/deplasman bağlamında sistematik tekrar ediyor mu? Bu soru, tetikleyici olayların aynı atmosfer sınıflarında daha sık üretilip üretilmediğini yakalar.
Bu tetikleyiciler odds tarafında hareketle aynı zaman bandında mı çakıştı yoksa bağımsız mı göründü? Bu soru, tetikleyicinin “piyasa davranışı” ile beraber mi yürüdüğünü ayırır.
Bu tetikleyiciler basın haber temalarıyla aynı hafta penceresinde mi çakıştı yoksa bağımsız mı? Bu soru, tetikleyicinin “haber kökenli mi” yoksa “saha kökenli mi” olduğuna dair sınıflamayı mümkün kılar.


Önemli oyuncu atılınca takımın reaksiyonu soruları

Takımın en kritik oyuncusu kırmızı kartla oyundan atılınca takımın reaksiyonu ne oluyor (mücadeleyi bırakma, sertleşme, skor korumaya gömülme, kontra arama)? Bu soru, kartın “kader etkisini” oyuncu ağırlığıyla bağlar. Aynı kart, sıradan oyuncuda farklı, bel kemiğinde farklı sonuç üretir.

Kritik oyuncu oyundan atıldıktan sonraki ilk 10 dakikada takımın tempo ve disiplin bandı hangi yöne kayıyor? Bu soru, ilk şok tepkisini ölçer. Bazı takımlar bu 10 dakikada dağılır, bazıları tam tersine kitlenip direnç üretir.
Kritik oyuncu çıkınca o mevkiyi dolduran yedek oyuncunun kalite farkı takımın oyun planını deterministik değiştiriyor mu? Bu soru, “kâğıt üstü 10 kişi” ile “fiilen çöken takım” ayrımını verir. Oyuncu değişimi bir olay değil, kapasite kaymasıdır.
Kritik oyuncu kaybı sonrası takımın savunma çizgisi geri mi çekiliyor, yoksa kompakt kalıp agresif mi kalıyor? Bu soru, takımın kriz stratejisini sabitler. Geri yaslanma mı direnç mi, kaderi belirleyen ayrımdır.
Kritik oyuncu atıldıktan sonra teknik direktörün müdahalesi hangi segmentte geliyor ve müdahale doğru mu çalışıyor? Bu soru, teknik direktörün kriz yönetimi DNA’sını ölçer. Krizde doğru hamle yapabilen takımın sapma profili farklıdır.
Kondisyon ve tempo taşıma soruları. Bu takımın 90 dakika boyunca tempo taşıma kapasitesi var mı ve bu kapasite sezon fazına göre değişiyor mu? Bu soru, maçın son 20 dakikasında “çıkartamama” riskini adresler. Kondisyon düşüşü çoğu zaman sapmayı tetikler.

Takım yüksek tempolu maçlarda aynı tempoyu kaç dakika sürdürebiliyor ve kırılma dakikası tekrar ediyor mu? Bu soru, tempo dayanıklılığını ölçer. Kırılma dakikası tekrar ediyorsa takımın biyolojik sınırı gibi çalışır.
Takım 10 kişi kaldığında koşu kapasitesini koruyabiliyor mu yoksa tempo düşüşü hızlanıyor mu? Bu soru, eksik kalma krizinin fiziksel boyutunu ölçer. Bazı takımlar eksik kalınca bile daha çok koşar; bu ayrı bir DNA’dır.
Takım 9 kişi kaldığı ekstrem senaryolarda bile mücadele bandını koruyabiliyor mu? Bu soru, senin verdiğin gerçek örneği raf disiplinine çevirir. Bu tekrar eden bir özellikse kartların kader etkisi farklı okunur.
Takımın kondisyon düşüşü, maç segmentlerinde kart/faul artışıyla birlikte mi geliyor? Bu soru, yorgunluk–disiplin ilişkisini yakalar. Kondisyon düştüğünde kartlar artıyorsa kader tetikleyicisi büyür.
Takımın sezon hazırlığı (kamp/rotasyon/transfer) sonrası ilk haftalarda kondisyon profili farklı mı? Bu soru, sezon arası bağlam ile saha içi tempo dayanıklılığını birbirine bağlar. Kamp ve kadro değişimi tempo DNA’sını etkiler.

BASIN VE HABER AKIŞI SORULARI (FUTBOL) — MAÇ ÖNCESİ + MAÇ SONRASI + SEZON ARASI
Bu bölümün amacı “haber var mı yok mu” kontrolü değildir. Amaç, haber akışını deterministik biçimde raflara ayırmak ve haberin maç içi davranışla, odds davranışıyla ve takım DNA’sıyla hangi şartlarda kesiştiğini ölçmektir. Haber, tek başına hüküm kurmaz; yalnız bağlam üretir ve kanıt zincirinin bir parçası olabilir. Bu yüzden haber akışı hem sezon içi hem sezon arası pencerede ayrı disiplinle kaydedilir.

Bu kayıt sezon içi maç haftası haber paketi mi yoksa sezon arası haftalık off-season paketi mi? Bu soru, haberin hangi pencere disipliniyle işlendiğini kilitler. Sezon arası haberleri günlük maç akışı gibi değil, haftalık paket olarak raflara yazılır.
Bu haber paketi hangi ülke, lig, sezon ve tekil takım adresine bağlanıyor? Bu soru, haberin doğru raf adresine düşmesi içindir. Yanlış bağlanan haber, beş yıl sonra yanlış DNA okuması üretir.
Bu haber paketi lig (Tier-1/Tier-2) akışına mı yoksa Cups akışına mı aittir? Bu soru, kupa haberlerinin lig haberine karışmasını engeller. Kupa bayrağı, haber seviyesinde de deterministik işlenir.
Bu haber paketi hangi organizasyon tipine aittir (lig, ulusal kupa, kıtasal kupa, milli takım)? Bu soru, haberin hangi stres sınıfını taşıdığını belirler. Organizasyon tipi belirlenmeden haber etkisi yanlış sınıfa yazılabilir.
Bu haber penceresi maçtan kaç gün öncesini kapsıyor (örnek: 7 gün) ve pencere sabit mi? Bu soru, haberin “zaman hizasını” kilitler. Pencere kayarsa aynı olay farklı maçlara yanlış bağlanır.

Maç öncesi haber akışında hangi temalar öne çıktı ve temalar kaç farklı kaynakta tekrar etti? Bu soru, tek kaynağın gürültüsü ile çoklu kaynağın tekrarını ayırır. Tekrar eden tema daha güçlü sinyal adayıdır.
Haber temaları daha çok hangi eksende kümelendi (yönetim, teknik direktör, oyuncu, hakem, taraftar, transfer, sakatlık, disiplin)? Bu soru, haberin hangi kart nesnesine bağlanacağını belirler. Tema yanlış karta bağlanırsa analiz yanlış kişiyi suçlar gibi görünür.

Haber tonu hangi bantta yoğunlaştı (olumlu, olumsuz, karma) ve ton aniden kırıldı mı? Bu soru, haberin duygusal iklimini adresler. Ton kırılması varsa maç içi davranış değişimiyle eşleşebilir.
Aynı olay farklı kaynaklarda aynı biçimde mi geçti yoksa kaynaklar arasında ayrışma var mı?

Bu soru, kaynak güven bandını ölçer. Ayrışma varsa “tek doğru” diye hüküm kurulmaz, yalnız işaretlenir.
Bu takımın haber akışı sezon içinde “rutin” mi yoksa “kriz/çalkantı” mı taşıyor? Bu soru, takımın baskı altında olup olmadığını belirler. Kriz akışı varsa maç içi tetikleyiciler daha sert çalışabilir.
Bu haber akışında transfer söylentileri var mı ve söylenti-gerçekleşme doğruluk bandı geçmişte nasıldı? Bu soru, haberin güvenilirliğini beş yıllık doğrulamayla ölçer. Transfer gürültüsü ile gerçek transfer ayrılır.
Sezon arası haftalık paketlerde kamp, kadro dışı kalanlar, rotasyon ve hazırlık maçları konuşuluyor mu? Bu soru, sezon arası bağlamı takım DNA’sına bağlar. Kamp ve kadro değişimleri sezon başlangıcı davranışını belirler.

Haber akışında kritik oyuncu sakatlığı veya dönüşü var mı ve bu bilgi maç segment davranışını etkiliyor mu? Bu soru, haber-temelli bağlamın saha içi gerçekliğe yansıyıp yansımadığını ölçer.
Haber akışı teknik direktör üzerinde baskı üretiyor mu ve bu baskı maç içinde erken hamle veya panik hamle doğuruyor mu? Bu soru, haberin teknik karar davranışına etkisini test eder.
Haber akışı taraftar baskısı içeriyor mu ve bu baskı iç saha davranışına yansıyor mu? Bu soru, tribün etkisinin haber üzerinden büyüyüp büyümediğini ölçer. Bazı baskılar saha içinde değil, haberle inşa edilir.

Maç sonrası haber akışı hangi temada devam etti ve maç öncesi anlatıyla uyumlu mu? Bu soru, haberin “sonuçla yeniden yazılma” riskini test eder. Maç sonrası eksen değişiyorsa bu not düşülür.
Maç sonrası haber akışı, bir sonraki maçın haber penceresinde tekrar eden bir yönlendirme oluşturuyor mu? Bu soru, zincir etkisini ölçer. Bazı haber döngüleri bir maçı değil, bir seri maçı etkiler.

Bu haber akışı ile maç içi kader tetikleyicileri aynı hafta içinde çakıştı mı? Bu soru, “haber etkisi” iddiasını test edilebilir hale getirir. Çakışma yoksa haber yalnız gürültü olabilir.
Bu haber akışı ile odds kırılmaları aynı zaman bandında mı ortaya çıktı? Bu soru, haber–piyasa davranışı ilişkisinin varlığını yokluğunu ölçer. Eşleşme varsa işaretlenir, hüküm kurulmaz.
Bu haber akışı ile takımın segment DNA davranışı arasında tekrar eden eşleşme var mı? Bu soru, haberin takımı hangi segmentte etkilediğini yakalar. Bazı takımlar baskı altında ilk 15’te dağılır, bazıları son 15’te.
Haber kaynakları tekilleştirildi mi ve aynı olayın kopyaları raf şişmesi yapmadan birleştirildi mi? Bu soru, kütüphane şişmesini kontrol eder. Aynı olayın 50 kopyası değil, tekil olayın kaynak referansları tutulur.

Bu haber paketi “kanıt zinciri” için yalnız bağlam mı yoksa doğrulanmış bir veri mi? Bu soru, senin istediğin kilittir: haber karar vermez. Haber yalnız bağlamdır; doğrulama olmadan hüküm üretilemez.
Bu haber yalnız yayın organı adıyla değil, yazar/editör kimliğiyle de etiketleniyor mu? Bu soru, aynı yayın organı içinde farklı doğruluk bantlarını ayırmak içindir. Kaynak tek başına yetmez; içerik üretici izi raf nesnesi olmalıdır.
Bu yazar/editör geçmişte hangi tür haberlerde daha yüksek doğruluk bandı gösterdi? Bu soru, “boş haber” ile “erken sinyal” üreten haberi ayırır. Bu bir hüküm değil, istatistiksel güven bandıdır.
Bu yazar/editörün haberleri hangi temalarda daha çok sapma üretiyor (transfer, sakatlık, yönetim, teknik direktör)? Bu soru, yazarın güçlü/zayıf alanını çıkarır. Analist hangi haberin hangi temada ciddiye alınacağını raf üzerinden görür.

Bu yazar/editör haberleri ile gerçekleşen olaylar arasındaki gerçekleşme oranı dönemsel değişiyor mu? Bu soru, bir yazarın belirli dönemlerde “balon” üretip üretmediğini ölçer. Dönemsel değişim varsa not edilir.
Bu yayın organının haberleri “sonuçtan sonra yeniden yazma” eğilimi taşıyor mu? Bu soru, maç sonrası anlatının manipülasyon değil ama “hikâye kurma” eğilimini ayırmak içindir. Analist bu riski bilir ve zincire göre tartar.
Aynı haber farklı kaynaklarda doğrulanıyor mu yoksa tek kaynakta mı kalıyor? Bu soru, tek kaynak gürültüsü ile çoklu kaynak tekrarını ayırır. Tek kaynak varsa kanıt zinciri zayıf kabul edilir.
Bu haberin dili deterministik mi yoksa abartılı/spekülatif mi ve bu dil profili yazar bazında tekrar ediyor mu? Bu soru, haberin “ton” profilini içerik üretici düzeyinde işler. Ton profili, doğruluk bandına doğrudan bağlanmaz ama risk işaretidir.

FAZ-34
BAHİS / ODDS DAVRANIŞI SORULARI (FUTBOL) — MAÇ ÖNCESİ + MAÇ SAATİ + MAÇ İÇİ
Bu bölümün amacı odds verisini “tahmin” için kullanmak değildir. Amaç, piyasa davranışının normal banttan sapıp sapmadığını, sapıyorsa bunun maç içi tetikleyicilerle ve haber penceresiyle hangi şartlarda kesiştiğini deterministik biçimde işaretlemektir. Odds hareketi hüküm değildir; kanıt zincirinin yalnızca bir parçası olabilir.

Bu odds kaydı hangi maç kimliğine ve hangi UTC zaman penceresine bağlanıyor? Bu soru, odds zaman hizasını kilitler. Zaman hizası bozuksa aynı odds hareketi yanlış maça yazılabilir.
Odds snapshot penceresi nasıl tanımlandı ve pencereler deterministik mi? Bu soru, odds örüntüsünün doğru kıyaslanması içindir. Snapshot aralığı kayarsa bant okuması bozulur.
Bu odds kaydı hangi bookmaker’lara aittir ve allowlist içinde midir? Bu soru, veri kaynağını kilitler. Allowlist dışı bookmaker verisi rafı kirletmez, dışarıda kalır.

Bu maç için hangi market setleri zorunlu izlendi ve market kapsamı boşluk bırakmadan kaydedildi mi? Bu soru, izlenen alanın deterministik olmasını sağlar. Market kapsamı değişirse iki maç kıyaslanamaz.
Maç öncesi odds çizgisi sabit mi kaldı yoksa keskin kırılma yaşadı mı? Bu soru, normal bant ile sapma arasını ayırır. Keskin kırılma varsa zaman damgası şarttır.
Keskin kırılma tek bir bookmaker’da mı yoksa birden fazla bookmaker’da mı oluştu? Bu soru, tek kaynak sapması ile piyasa geneli sapmasını ayırır. Tekil sapma daha düşük güven sınıfıdır.
Odds hareketi maç saatine yaklaştıkça mı hızlandı yoksa günler önceden mi başladı? Bu soru, hareketin zaman doğasını ölçer. Erken başlayan hareket farklı, son dakika hareketi farklı sınıfa yazılır.

Maç saatinden önce odds hareketi “yumuşak akış” mı yoksa “kademeli sert kayma” mı gösterdi? Bu soru, piyasadaki yön değişiminin hız profilini çıkarır. Hız profili, sapma kalitesini belirler.
Odds hareketi maçın hangi segmentinde yoğunlaştı (ilk 15, devre, son 15)? Bu soru, odds değişimini segment okumasına bağlar. Segment eşleşmesi yoksa olay-kaynak bağlantısı zayıftır.
Maç içi odds hareketi, maç içi tetikleyicilerle açıklanabiliyor mu yoksa tetikleyici olmadan mı oluştu? Bu soru, “olay yokken hareket” durumunu işaretler. Bu bir suçlama değildir; sadece anomali sapma adaydır.
Kart, VAR, penaltı, kırmızı kart gibi kader tetikleyicileri ile odds hareketi aynı zaman bandında mı çakıştı? Bu soru, piyasaya yansıyan maç içi kırılmaları yakalar. Çakışma varsa işaretlenir, hüküm kurulmaz.

Odds hareketi iç saha/deplasman bağlamında tekrar ediyor mu? Bu soru, takımın ev-deplasman DNA’sının piyasa davranışına yansıyıp yansımadığını ölçer.
Odds hareketi takımın seri davranışıyla ilişkili mi (galibiyet serisi, mağlubiyet serisi) Bu soru, takımın sonuç hafızasının piyasa tarafından nasıl fiyatlandığını ölçer.
Odds hareketi kritik oyuncu yokluğu, ceza sınırı veya kondisyona dair bağlamla eşleşiyor mu? Bu soru, bağlam duvarıyla odds davranışını birleştirir. Eşleşme varsa sapma adayı güçlenir.
Bu maçın odds örüntüsü, aynı takımın benzer bağlamlı geçmiş maçlarına göre normal bant içinde mi dışında mı? Bu soru, karşılaştırmayı mümkün kılar. Bant tanımı yoksa sapma işaretlenemez.
Odds verisi eksik mi, parçalı mı, rate-limit nedeniyle degrade mi ve data\\\_quality\\\_badge ne? Bu soru, “anomali yok” ile “veri eksik” ayrımını korur. Eksik veri varsa hüküm kurulmaz.
Bu odds kaydı bir sonraki cycle’da aynı şekilde doğrulanabiliyor mu? Bu soru, tek seferlik veri hatasıyla gerçek piyasa hareketini ayırır. Tekrar yoksa düşük güven sınıfıdır

Bu bookmaker’ın sapma/anomali davranışı en çok hangi ülke liglerinde kümeleniyor? Bu soru, tek maç sapmasını “piyasa profiline” bağlar. Bazı bookmaker’lar belirli ülke liglerinde daha sık kırılma üretebilir; bu bir kanıt değildir ama analiz refleksini hızlandıran bir risk haritasıdır.
Bu bookmaker’ın sapma davranışı organizasyon tipine göre değişiyor mu (lig, ulusal kupa, kıtasal kupa)? Bu soru, sapmanın maç türüne göre sistematikleşip sistematikleşmediğini ayırır. Kupa bağlamında daha sık kırılma görülüyorsa bu ayrı 
band olarak işlenir.

Bu bookmaker’ın sapma davranışı dönemsel mi, sabit mi, rotasyonlu mu? Bu soru, senin tarif ettiğin “bir ay Asya, bir ay başka bölge” davranışını yakalar. Rastgele görünen sapmaların dönemsel haritası olup olmadığı burada ortaya çıkar.
Bookmaker sapmaları belirli haftalarda veya sezon fazlarında artıyor mu (sezon başı/sonu, transfer dönemi, yoğun fikstür)? Bu soru, sapmayı sezon fazı bağlamına bağlar. Bazı sapmalar sezon geçişlerinde artabilir.
Bu bookmaker’ın sapması “maç öncesi”, “maç saatine yakın” veya “maç içi” hangi pencerede daha çok oluşuyor? Bu soru, sapmanın zaman tipini sınıflar. Zaman tipi, sapma yorumunun yönünü değiştiren bir ana anahtardır.
Bu ligde aynı maç için farklı bookmaker’lar arasında sistematik ayrışma var mı? Bu soru, tek bookmaker sapması ile piyasa geneli ayrışmayı ayırır. Ayrışma tekrar ediyorsa lig bazlı piyasa davranışı işaretlenir.

Bu takımın maçlarında belirli bookmaker sapmaları tekrar ediyor mu? Bu soru, bookmaker profili ile takım profili kesişimini yakalar. Tekrar varsa “takım+bookmaker” eşleşmesi raf nesnesi olur.
Bu bookmaker için “normal bant” ve “sapma bandı” geçmiş veriden çıkarılabiliyor mu? Bu soru, sapmanın ölçülebilir hale gelmesi içindir. Bant tanımı yoksa sapma yalnız his olur; sistem bunu kabul etmez.
Bu bookmaker’ın veri bütünlüğü ve veri kalitesi (eksik snapshot, gecikme, tutarsızlık) sapma gibi görünüyor olabilir mi? Bu soru, veri hatasını sapma sanma riskini engeller. Önce veri kalitesi ayrımı yapılır, sonra sapma işaretlenir.

ÇAPRAZ KAYNAK OKUMA SORULARI (FUTBOL) — BASIN + ODDS + MAÇ İÇİ TETİKLEYİCİLER
Bu bölümün amacı, üç ayrı hattı aynı anda “sonuç çıkarma” için birleştirmek değildir. Amaç, basın akışı, odds hareketi ve maç içi tetikleyiciler arasında tekrar eden zaman hizası ve davranış eşleşmesi olup olmadığını deterministik biçimde test etmektir. Bu bölüm, hüküm vermez; yalnız eşleşme ve eşleşmeme haritasını çıkarır. Kanıt zinciri tamamlanmadan hiçbir birim sonuç dili kuramaz.

Bu maç için basın haber temaları ile odds hareketinin zaman penceresi çakışıyor mu? Bu soru, “haber çıktı → piyasa hareket etti” gibi bir iddiayı test edilebilir hale getirir. Çakışma yoksa ilişki zayıf kabul edilir.

Basın haber temaları ile odds hareketi çakışıyorsa çakışma tek bookmaker’da mı yoksa birden çok bookmaker’da mı görülüyor? Bu soru, tekil kaynak sapmasını piyasa geneli sapmadan ayırır. Tekil sapma düşük güven sınıfıdır.
Basın haber temaları ile odds hareketi çakışıyorsa çakışma hangi lig/organizasyon sınıfında daha sık görülüyor? Bu soru, çapraz eşleşmenin ülke/lig bazında kümelenip kümelenmediğini ölçer. Kümelenme varsa harita çıkar.
Basın haber temaları ile odds hareketi çakışıyorsa bu çakışma dönemsel mi sabit mi rotasyonlu mu? Bu soru, rastgele görünen davranışın dönemsel haritası olup olmadığını test eder. Rotasyon varsa not edilir.
Basın haber temaları ile odds hareketi çakışıyorsa bu çakışma sezon fazına göre artıyor mu (sezon başı/sonu, transfer dönemi)? Bu soru, “geçiş dönemleri” etkisini ölçer. Bazı çapraz eşleşmeler sezon geçişlerinde artabilir.

Odds hareketi maç içi kader tetikleyicilerinden önce mi başladı yoksa tetikleyiciden sonra mı yoğunlaştı? Bu soru, zaman yönünü belirler. Tetikleyici sonrası hareket normal bant olabilir; tetikleyici öncesi hareket sapma adayını güçlendirir.
Odds hareketi tetikleyici olmadan oluşuyorsa bu hareket maç içi segment davranışında bir değişimle eşleşiyor mu? Bu soru, “olay yok ama davranış kaydı var” senaryosunu yakalar. Segment DNA değişiyorsa bu ayrıca işaretlenir.

Maç içi tetikleyicilerden hangileri odds hareketiyle en sık çakışıyor (kırmızı kart, VAR, penaltı, iptal gol)? Bu soru, piyasanın en hassas olduğu tetikleyici sınıfları çıkarır. Bu bir tahmin aracı değil, örüntü haritasıdır.
Maç içi tetikleyiciler ile basın temaları aynı hafta penceresinde eşleşiyor mu? Bu soru, basının tetikleyici üretip üretmediğini değil, basın konuştuğu şeyle maç içinin kesişip kesişmediğini test eder.

Basın teması “hakem/adalet” ise maç içi kart ve VAR tetikleyicileriyle eşleşme bandı artıyor mu? Bu soru, tematik eşleşmeyi test eder. Eşleşme varsa yalnız işaretlenir, hüküm kurulmaz.
Basın teması “sakatlık/eksik” ise maç içi segmentlerde kondisyon düşüşü veya tempo kırılmasıyla eşleşme var mı? Bu soru, haber bağlamının sahaya yansıyıp yansımadığını ölçer.
Basın teması “transfer/kriz/yönetim” ise maç içi disiplin bandında kart yoğunluğu artıyor mu? Bu soru, haber-temelli baskının disipline yansıma ihtimalini test eder. Tek seferlikte hüküm yoktur, tekrar aranır.

Bu eşleşmeler takım bazında mı kümeleniyor yoksa lig bazında mı kümeleniyor? Bu soru, yapının nerede olduğunu ayırır. Takım bazlıysa takım DNA’sına, lig bazlıysa lig davranışına yazılır.
Bu eşleşmeler bookmaker bazında mı kümeleniyor yoksa piyasa geneline mi yayılıyor?nBu soru, sapmanın kaynak sınıfını belirler. Bookmaker profili ayrı raf nesnesidir.
Bu eşleşmeler belirli yazar/editör kaynaklarında mı yoğunlaşıyor? Bu soru, haber kaynağı güven haritasını çapraz hatla birleştirir. Aynı yazarın haberleriyle eşleşme yüksekse işaretlenir.

Bu eşleşmelerde tekrar eden bir “tetikleyici sırası” var mı (haber tonu → odds kayması → kart/VAR → tempo kırılması)? Bu soru, zincir şeması çıkarır. Zincir şeması varsa bu yalnız örüntüdür, hüküm değildir.
Bu eşleşmelerde “anomali yok” durumunda da normal bant korunuyor mu? *Bu soru, sistemin en kritik ilkesini korur: anomali çıkmaması da bir sonuçtur. Normal bant korunuyorsa bu bilgi raflara yazılır.
Bu eşleşmelerde veri eksikliği veya kalite düşüşü var mı ve “anomali yok” ile karışıyor mu? Bu soru, data\\\_quality ayrımını çapraz okuma içinde de korur. Eksik veri varsa eşleşme hükmü kurulmaz.


FAZ-35
TAKIM DNA KARTI SORULARI (FUTBOL) — PROFİL, REFLEKS, BAĞIMLILIK
Bu bölümün amacı takımın “iyi/kötü” olup olmadığını söylemek değildir. Amaç, takımın tekrar eden reflekslerini, stres altında verdiği tepkileri, seri davranışını, iç saha/deplasman karakterini ve bağımlılıklarını deterministik biçimde kartlaştırmaktır. Bu kart, maç tekilliğini aşan bir raf nesnesidir ve beş yıllık hafızanın ana omurgasıdır.

Takımın temel oyun temposu hangi bantta ve bu tempo sezon fazına göre değişiyor mu? Bu soru, takımın normal hızını sabitler. Tempo değişimi tekrar ediyorsa sezon fazı etkisi kartın parçası olur.
Takımın maç başlangıç refleksi nedir (ilk 15) ve bu refleks tekrar ediyor mu? Bu soru, “erken baskı/erken çözülme” profilini çıkarır. Tekrar eden refleks DNA sinyalidir.
Takımın devre geçiş refleksi nedir ve ikinci yarıya çıkış davranışı hangi bantta? Bu soru, teknik direktör etkisinin en net görüldüğü eşiği ölçer. Devre çıkışı tekrar eden bir kimliktir.

Takımın maç kapatma refleksi nedir (son 15 ve uzatma) ve skor durumuna göre değişiyor mu? Bu soru, takımın stres altında kapanış stratejisini sabitler. Önde/geride farklı davranışlar ayrı ayrı okunur.
Takımın seri davranışı var mı (galibiyet/beraberlik/mağlubiyet serileri) ve seri içinde tempo-disiplin değişiyor mu? Bu soru, takımın dalga yapısını ölçer. Seri davranışı varsa kartlar ve risk profili seri içinde farklılaşabilir.
Takımın bir önceki maç sonucu bir sonraki haftayı etkiliyor mu? Bu soru, takımın sonuç hafızasını ölçer. Bu hafıza varsa maçlar arası okuma güçlenir.

Takımın iç saha davranışı ile deplasman davranışı deterministik ayrışıyor mu? Bu soru, atmosfer etkisini DNA’ya bağlar. Aynı takımın iç/dış saha profili farklı kartlar üretir.
Takımın tribün baskısına dayanma profili nedir ve baskı altında disiplin bandı bozuluyor mu? Bu soru, seyirci etkisini doğrudan DNA’ya yazar. Baskı altında kart artışı tekrar ediyorsa sinyal güçlenir.
Takımın kritik oyuncu bağımlılığı var mı ve skor üretimi tekilde mi kümeleniyor? Bu soru, yıldız bağımlılığını ölçer. Bağımlılık varsa takım sapma profili oyuncu kartına kilitlenir.

Takımın kritik oyuncu kaybı sonrası reaksiyonu nedir (mücadeleyi bırakma, sertleşme, geriye yaslanma)? Bu soru, bel kemiği kırılınca takımın kriz stratejisini sabitler. Bu DNA kritik sınıftır.
Takımın kart tetikleyicilerine tepkisi nedir (kabullenme döngüsü mü agresyon döngüsü mü)? Bu soru, kartların kader etkisini takım karakterine bağlar. Kartın anlamı takım refleksiyle ölçülür.
Takımın kırmızı kart sonrası kriz yönetimi profili nedir ve ilk 10 dakikada çöker mi toparlar mı? Bu soru, eksik kalma dayanıklılığını ölçer. Bazı takımlar 10 kişi kalınca bile direnç üretir.

Takımın kondisyon ve tempo taşıma kapasitesi nedir ve kırılma dakikası tekrar ediyor mu? Bu soru, son 20 dakika çöküş riskini ölçer. Kırılma dakikası tekrar ediyorsa kartın etkisi de büyür.
Takımın yüksek tempolu rakip karşısında tempo koruma süresi nedir? Bu soru, maç başlamadan “tempo yetmez” riskini işaretleyebilir. Bu bir hüküm değil, profil işaretidir.
Takımın disiplin profili nedir (kart kümelenmesi, faul yoğunluğu) ve hangi segmentlerde artıyor? Bu soru, disiplinin maç geneline değil, segmentlere dağılımını sabitler. Segment bazlı artış kader tetikleyicisidir.

Takımın VAR/penaltı/iptal gol gibi karar tetikleyicilerine psikolojik tepkisi nedir? Bu soru, hakem kararlarının takım davranışını nasıl kaydırdığını ölçer. Bazı takımlar bu tetikleyicilerde çözülür.
Takımın risk alma profili nedir (öndeyken kapanma, gerideyken panik hücum, beraberlikte tutma)? Bu soru, skor bağlamındaki davranış stratejisini sabitler. Aynı skor durumunda tekrar eden davranış DNA’dır.
Takımın sakatlık ve kadro eksikliği altında performans stabilitesi nedir? Bu soru, kadro derinliğini ölçer. Stabilite yoksa sapma ihtimali artar.

Takımın teknik direktör değişimi sonrası DNA kırılması var mı? Bu soru, takım kartının hangi tarihte değiştiğini sabitler. Teknik direktör değişimi kart revizyonu gerektirebilir.
Takımın kupa/Avrupa paralel yükü altında lig davranışı kayıyor mu? Bu soru, organizasyon yükünün lig performansına etkisini ölçer. Paralel yük varsa segment davranışları kayabilir.
Takımın “normal bant” profili beş yıl içinde stabil mi, yoksa dönemsel karakter değişimi var mı? Bu soru, takım DNA’sının sabit mi evrimli mi olduğunu ölçer. Dönemsel değişim varsa kart revizyonu yapılır.

FUTBOL ETİKET KATALOĞU (KÜTÜPHANE SÖZLÜĞÜ) — ÇEKİRDEK DUVAR + MAÇ + TAKIM DNA
Bu katalog, soru cümlelerinin etiket olarak yapıştırılması için değil; soruların cevaplarını deterministik biçimde raflara yazdırmak için vardır. Bu katalog dışı etiket üretilemez. Etiketler serbest metin değildir; sabit ad ve sabit değer bantlarıyla çalışır.

KONTEKST / DUVAR ETİKETLERİ (ZORUNLU)
timestamp\\\_utc ,country\\\_ref ,league\\\_ref ,season\\\_id ,season\\\_phase ,competition\\\_type ,cup\\\_flag ,team\\\_ref ,season\\\_phase yalnız şu değerleri alır: pre\\\_season, season\\\_start, season\\\_mid, season\\\_end, off\\\_season ,competition\\\_type yalnız şu değerleri alır: league, cup, continental, national\\\_team ,cup\\\_flag yalnız şu değerleri alır: true, false

MAÇ ADRESİ VE MAÇ BAĞLAM ETİKETLERİ (ZORUNLU)
match\\\_ref ,kickoff\\\_time\\\_utc ,home\\\_team\\\_ref ,away\\\_team\\\_ref ,venue\\\_type ,is\\\_home\\\_team\\\_context ,referee\\\_ref ,venue\\\_type yalnız şu değerleri alır: home, away, neutral ,is\\\_home\\\_team\\\_context yalnız şu değerleri alır: true, false

MAÇ SEGMENT ETİKETLERİ (ZORUNLU)
segment\\\_first\\\_15 ,segment\\\_16\\\_30 ,segment\\\_31\\\_45 ,segment\\\_half\\\_time\\\_transition ,segment\\\_46\\\_60 ,segment\\\_61\\\_75 ,segment\\\_last\\\_15 ,segment\\\_last\\\_5\\\_plus\\\_added
Her segment alanı yalnız şu değerleri alır: normal\\\_band, tempo\\\_up, tempo\\\_down, control\\\_lost, control\\\_gained, risk\\\_up, risk\\\_down
 
TEMPO / KONTROL / DİSİPLİN BANT ETİKETLERİ (ZORUNLU)
tempo\\\_band\\\_overall ,tempo\\\_breakpoint\\\_minute\\\_bucket ,discipline\\\_band\\\_overall ,discipline\\\_cluster\\\_bucket ,control\\\_band\\\_overall ,tempo\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high ,tempo\\\_breakpoint\\\_minute\\\_bucket yalnız şu değerleri alır: none, 0\\\_15, 16\\\_30, 31\\\_45, 46\\\_60, 61\\\_75, 76\\\_90 ,discipline\\\_band\\\_overall yalnız şu değerleri alır: calm, normal, aggressive ,discipline\\\_cluster\\\_bucket yalnız şu değerleri alır: none, 0\\\_15, 16\\\_30, 31\\\_45, 46\\\_60, 61\\\_75, 76\\\_90 ,control\\\_band\\\_overall yalnız şu değerleri alır: stable, unstable

KADER TETİKLEYİCİ ETİKETLERİ (ZORUNLU)
trigger\\\_first\\\_yellow ,trigger\\\_red\\\_card ,trigger\\\_var\\\_review ,trigger\\\_penalty\\\_event ,trigger\\\_disallowed\\\_goal ,trigger\\\_major\\\_injury ,trigger\\\_long\\\_stoppage ,trigger\\\_time\\\_waste Bu alanlar yalnız şu değerleri alır: none, occurred ,occurred ise ayrıca trigger\\\_minute\\\_bucket zorunludur.trigger\\\_minute\\\_bucket yalnız şu değerleri alır: 0\\\_15, 16\\\_30, 31\\\_45, 46\\\_60, 61\\\_75, 76\\\_90, added\\\_time

KRİTİK OYUNCU / BEL KEMİĞİ ETKİSİ (ZORUNLU)
critical\\\_player\\\_incident ,critical\\\_player\\\_role\\\_weight ,critical\\\_player\\\_loss\\\_reaction ,critical\\\_player\\\_incident yalnız şu değerleri alır: none, yellow\\\_risk, red\\\_sent\\\_off, injury\\\_out, substituted ,critical\\\_player\\\_role\\\_weight yalnız şu değerleri alır: normal, high ,critical\\\_player\\\_loss\\\_reaction yalnız şu değerleri alır: no\\\_shift, fight\\\_harder, collapse, deep\\\_defend, chaos

KONDİSYON / TEMPO TAŞIMA ETİKETLERİ (ZORUNLU)
stamina\\\_profile ,stamina\\\_breakdown\\\_bucket ,ten\\\_men\\\_resilience

stamina\\\_profile yalnız şu değerleri alır: strong, normal, weak ,stamina\\\_breakdown\\\_bucket yalnız şu değerleri alır: none, 46\\\_60, 61\\\_75, 76\\\_90 ,ten\\\_men\\\_resilience yalnız şu değerleri alır: unknown, stable, unstable, strong\\\_resist

İÇ SAHA / DEPLASMAN / TRİBÜN BASINCI (ZORUNLU)
home\\\_away\\\_behavior\\\_shift ,crowd\\\_pressure\\\_band ,crowd\\\_pressure\\\_response

home\\\_away\\\_behavior\\\_shift yalnız şu değerleri alır: none, home\\\_stronger, away\\\_stronger, unstable ,crowd\\\_pressure\\\_band yalnız şu değerleri alır: low, medium, high ,crowd\\\_pressure\\\_response yalnız şu değerleri alır: no\\\_effect, discipline\\\_drop, tempo\\\_spike, panic, fight\\\_harder

FORM / SERİ DAVRANIŞI (ZORUNLU)
previous\\\_match\\\_result ,streak\\\_type ,streak\\\_length\\\_bucket ,*next\\\_week\\\_effect\\\_band

previous\\\_match\\\_result yalnız şu değerleri alır: win, draw, loss, unknown ,streak\\\_type yalnız şu değerleri alır: none, win\\\_streak, draw\\\_streak, loss\\\_streak, mixed ,streak\\\_length\\\_bucket yalnız şu değerleri alır: 0, 1\\\_2, 3\\\_4, 5\\\_plus ,next\\\_week\\\_effect\\\_band yalnız şu değerleri alır: none, positive, negative, unstable--

FUTBOL HAKEM KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı hakemi “iyi/kötü” diye sınıflamak değildir. Amaç, hakemin maçın disiplin eşiğini, VAR/penaltı kritik karar davranışını ve maçın kırılma anlarındaki rolünü tekrar eden bantlarla okumaktır. Suçlama dili yoktur; yalnız davranış izi çıkarılır.

Hakemin ilk kart eşiği erken mi oluşuyor, geç mi oluşuyor? Bu soru, maçın disiplin bandını erken sabitler. Erken eşik maçın tüm ritmini değiştirir.
Hakem kart dağıtımında dengeli mi yoksa tek taraflı kümelenme görüyor muyuz? Bu soru hüküm üretmez; yalnız dağılım bandını çıkarır. Tekrarlı bir yığılma varsa işaretlenir.

Hakem kritik faul kararlarını hangi bölgelerde daha sık veriyor? Bu soru, tehlikeli bölge faul bantlarını ve duran top riskini okumayı kolaylaştırır.
Hakem VAR müdahalesi gerektiren pozisyonlarda çizgiyi nasıl yönetiyor? Bu soru, maçın kader tetikleyicilerinden biri olan VAR bandını çıkarır.
Penaltı pozisyonlarında hakemin karar bandı nedir? Bu soru, penaltı kararlarının maç akışı üzerindeki kırılma etkisini okumayı sağlar.
İptal edilen gol kararları maçın momentumunu nasıl kırıyor? Bu soru, iptal gol kırığı etkisini ve takım reaksiyon profilini bağlamlar.

Hakem kırmızı kart eşiğinde erken mi, geç mi düdük çalıyor? Bu soru, maçın sertlik bandı ve kırmızı kart tetikleyici ihtimalini sabitler.
Hakem teknik alan olaylarında toleransı düşük mü yüksek mi? Bu soru, teknik direktör kartı ve disiplin sapması bandıyla kesişir.
Hakem maçın son 15 dakikasında düdük yoğunluğunu artırıyor mu azaltıyor mu? Bu soru, kapanış bandının “oyuncu davranışı mı yoksa hakem ritmi mi” olduğunu ayırır.
Hakem kararlarıyla maçın control\\\_lost bandı tetikleniyor mu? Bu soru, hakem davranışıyla ritim kırılması arasındaki tekrar ilişkisini yakalar.

FUTBOL HAKEM KARTI — ETİKET KATALOĞU
timestamp\\\_utc ,referee\\\_ref ,country\\\_ref ,league\\\_ref ,season\\\_id ,competition\\\_type ,season\\\_phase

referee\\\_first\\\_card\\\_threshold\\\_band ,referee\\\_card\\\_distribution\\\_balance\\\_band ,referee\\\_danger\\\_zone\\\_foul\\\_band ,referee\\\_var\\\_intervention\\\_band ,referee\\\_penalty\\\_decision\\\_band ,referee\\\_disallowed\\\_goal\\\_band ,referee\\\_red\\\_card\\\_threshold\\\_band ,referee\\\_technical\\\_area\\\_tolerance\\\_band ,referee\\\_closing\\\_whistle\\\_band ,referee\\\_control\\\_risk\\\_band

referee\\\_first\\\_card\\\_threshold\\\_band yalnız şu değerleri alır: early, normal, late ,referee\\\_card\\\_distribution\\\_balance\\\_band yalnız şu değerleri alır: balanced, mild\\\_skew, heavy\\\_skew ,referee\\\_danger\\\_zone\\\_foul\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_var\\\_intervention\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_penalty\\\_decision\\\_band yalnız şu değerleri alır: stable, volatile ,referee\\\_disallowed\\\_goal\\\_band yalnız şu değerleri alır: rare, normal, frequent ,referee\\\_red\\\_card\\\_threshold\\\_band yalnız şu değerleri alır: early, normal, late ,referee\\\_technical\\\_area\\\_tolerance\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_closing\\\_whistle\\\_band yalnız şu değerleri alır: low, medium, high ,referee\\\_control\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high ,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive

FUTBOL TEKNİK DİREKTÖR (KOÇ) KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı teknik direktörü “iyi/kötü” diye sınıflamak değildir. Amaç, maç içi kriz yönetimini, tempo/ritim müdahalesini, kart ve hakem bandında verdiği refleksleri ve son 15 dakika karar profilini tekrar eden örüntülerle kartlaştırmaktır.

Teknik direktör tempo yükselince oyunu sakinleştiriyor mu, yoksa tempo sapmasına izin mi veriyor? Bu soru, kontrol bandı yönetimini ölçer. Kontrol kaybı tekrar ediyorsa risk artar.
Teknik direktör ilk sarı kart sonrası disiplin bandını toparlıyor mu? Bu soru, kart sonrası refleksi ölçer. Kart görünce disiplin düşüyorsa tekrarlayan zaaf olur.
Teknik direktör kırmızı kart veya kritik karar sonrası plan değiştiriyor mu? Bu soru, kriz adaptasyonunu ölçer. Plan değişimi stabil ise takım kurtulur.
Teknik direktör VAR/penaltı gibi kırılmalarda panik mi yoksa kontrollü mü? Bu soru, mental yönetim bandını ölçer. Panikleşme kartla büyür.

Teknik direktör devre arası geçişinde oyuna yeni bir bant getiriyor mu? Bu soru, ikinci yarı refleksini ölçer. Devre arası etkisi tekrar ediyorsa kartlaşır.
Teknik direktör son 15 dakikada skoru koruma mı yoksa ikinci gol arama mı seçiyor? Bu soru, kapanış stratejisinin istikrarını ölçer.
Teknik direktör seyirci baskısı yükselince riskli hamle yapıyor mu? Bu soru, crowd\\\_pressure\\\_response ile koç davranışının bağını kurar.

Teknik direktör kritik oyuncu kaybında (kırmızı/sakatlık) takımı ayakta tutabiliyor mu? Bu soru, kritik oyuncu replacement\\\_gap ile doğrudan bağlıdır.
Teknik direktör hakem çizgisi sertleşince takımını disipline çekiyor mu? Bu soru, hakem profiline adaptasyon becerisini ölçer.
Teknik direktör seri halinde kötü gidişatı kırabiliyor mu? Bu soru, streak\\\_type etkisini ve müdahale gücünü ölçer.

FUTBOL TEKNİK DİREKTÖR (KOÇ) KARTI — ETİKET KATALOĞU
timestamp\\\_utc,coach\\\_ref,team\\\_ref,country\\\_ref,league\\\_ref,season\\\_id,competition\\\_type,season\\\_phase
coach\\\_tempo\\\_control\\\_band,coach\\\_post\\\_card\\\_management\\\_band,coach\\\_crisis\\\_adaptation\\\_band,coach\\\_key\\\_decision\\\_mental\\\_band,coach\\\_halftime\\\_adjustment\\\_band,coach\\\_closing\\\_strategy\\\_band,coach\\\_crowd\\\_pressure\\\_risk\\\_band,coach\\\_critical\\\_player\\\_loss\\\_management\\\_band,coach\\\_referee\\\_adaptation\\\_band,coach\\\_streak\\\_breaking\\\_band,coach\\\_tempo\\\_control\\\_band yalnız şu değerleri alır:
stable, unstable,coach\\\_post\\\_card\\\_management\\\_band yalnız şu değerleri alır: 
stable, unstable,coach\\\_crisis\\\_adaptation\\\_band yalnız şu değerleri alır:
strong, normal, weak,coach\\\_key\\\_decision\\\_mental\\\_band yalnız şu değerleri alır:
 
controlled, chaotic,coach\\\_halftime\\\_adjustment\\\_band yalnız şu değerleri alır: 
strong, normal, weak,coach\\\_closing\\\_strategy\\\_band yalnız şu değerleri alır: 
stable, unstable,coach\\\_crowd\\\_pressure\\\_risk\\\_band yalnız şu değerleri alır: 

low, medium, high,coach\\\_critical\\\_player\\\_loss\\\_management\\\_band yalnız şu değerleri alır: 
stable, unstable,coach\\\_referee\\\_adaptation\\\_band yalnız şu değerleri alır: 
strong, normal, weak,coach\\\_streak\\\_breaking\\\_band yalnız şu değerleri alır: 
strong, normal, weak,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: 
normal, incomplete, low, inactive

FUTBOLCU KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı futbolcuyu “iyi/kötü” diye sınıflamak değildir. Amaç, futbolcunun disiplin eğilimini, kritik an davranışını, kart riskini ve maçın kırılma anlarındaki rolünü tekrar eden bantlarla kartlaştırmaktır. Futbolcu kartı takım değişse bile kimliği taşır.

Futbolcu erken kart görme eğilimi taşıyor mu? Bu soru, takımın disiplin bandını bireysel seviyede etkileyen risk profilini çıkarır.
Futbolcu baskı yükselince hata ve faul eğilimi artıyor mu? Bu soru, crowd\\\_pressure\\\_response ile bireysel kırılmayı bağlar.

Futbolcu kırmızı kart riski taşıyor mu ve bu risk hangi segmentte artıyor? Bu soru, segment bazlı disiplin sapmasını ölçer.
Futbolcu kritik gol pozisyonlarında veya kritik faullerde tekrar eden rol taşıyor mu? Bu soru, maç kaderi tetikleyicilerinin bireysel izini yakalar.
Futbolcu VAR/penaltı kararlarından sonra mental düşüş yaşıyor mu? Bu soru, karar sonrası kırılma bandını bireysel düzeye indirir.
Futbolcu son 15 dakikada tempo taşıyabiliyor mu yoksa düşüyor mu? Bu soru, stamina\\\_profile ve kapanış dayanıklılığını bireysel kartta sabitler.

Futbolcu kritik oyuncu sınıfında mı ve kaybı replacement\\\_gap yaratıyor mu? Bu soru, takımın bel kemiği davranışını çıkarır.
Futbolcu hakem çizgisi sertleşince adaptasyon gösteriyor mu? Bu soru, referee\\\_profile ile bireysel disiplin davranışını bağlar.
Futbolcu maç içinde kontrol kaybı tetikleyen olaylarda sık görülüyor mu? Bu soru, control\\\_lost bandını bireysel düzeye taşır.
Futbolcu sakatlık sonrası performans düşüş bandı taşıyor mu? Bu soru, major\\\_injury tetikleyicisinin bireysel etkisini okur.

FUTBOLCU KARTI — ETİKET KATALOĞU
timestamp\\\_utc,player\\\_ref,team\\\_ref,country\\\_ref,league\\\_ref,season\\\_id,competition\\\_type,season\\\_phase,player\\\_early\\\_card\\\_risk\\\_band,player\\\_pressure\\\_error\\\_band,player\\\_red\\\_card\\\_risk\\\_band,player\\\_critical\\\_event\\\_involvement\\\_band,player\\\_post\\\_decision\\\_mental\\\_band,player\\\_closing\\\_stamina\\\_band,player\\\_critical\\\_weight\\\_band,player\\\_referee\\\_adaptation\\\_band,player\\\_control\\\_loss\\\_risk\\\_band,player\\\_injury\\\_recovery\\\_band,player\\\_early\\\_card\\\_risk\\\_band yalnız şu değerleri alır:

low, medium, high,player\\\_pressure\\\_error\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_red\\\_card\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_critical\\\_event\\\_involvement\\\_band yalnız şu değerleri alır:
 
low, medium, high,player\\\_post\\\_decision\\\_mental\\\_band yalnız şu değerleri alır: stable, unstable,player\\\_closing\\\_stamina\\\_band yalnız şu değerleri alır: strong, normal, weak,player\\\_critical\\\_weight\\\_band yalnız şu değerleri alır: normal, high,player\\\_referee\\\_adaptation\\\_band yalnız şu değerleri alır.

strong, normal, weak,player\\\_control\\\_loss\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_injury\\\_recovery\\\_band yalnız şu değerleri alır: strong, normal, weak,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive


FAZ-26
BASKETBOL — KÜTÜPHANE + ETİKETLİ KARTLAR + MARKET/BOOKMAKER + RAPOR ŞABLONLARI | ARŞİV PAKETİ (NİHAİ / KODCUYA VERİLECEK / TEK DOSYA)
Aşağıdaki metin yoruma kapalı, bağlayıcı ve birebir uygulanması zorunlu uygulama promptudur. Bu metinde yazan her adım, her sıra, her rol, her yapı ve her isimlendirme değiştirilemez. Kod yazarı “daha iyisi olur”, “şöyle yapalım”, “şunu çıkaralım”, “bunu ekleyelim” gibi hiçbir yorum, öneri ve alternatif üretmez. Metinde olmayan hiçbir özellik eklenmez. Metinde olan hiçbir özellik çıkarılmaz. Yalnızca teknik olarak imkânsızlık varsa “şu madde teknik olarak imkânsız” cümlesiyle bildirir ve uygulama durdurulur. Çözüm önerisi getirilmez, soru sorulmaz, fikir üretilmez. Bu paket bir taslak değildir. Tamamlanmış ve kilitlenmiş sistem mimarisidir. Bu proje “bahis sitesi” kurmaz. Bu proje “bahse yönlendirme” yapmaz. Bu proje sadece istatistiksel analiz üretir ve gösterir. Her çıktı “istatistiksel değerlendirme” olarak kalacaktır. Bu sistemin tüm çıktıları “tahmin”, “öneri”, “yönlendirme”, “kesin sonuç” değildir. “Kesin kazanır, banko, tek” gibi dil yasaktır. Sistemin adı: Spor Anomali \\\& Örüntü Motoru (n8n tabanlı). Sistemin amacı: basketbol için haber + piyasa/oran + maç içi olay verilerini tek hiyerarşide toplamak, örüntü üretmek ve olağan akışa aykırı sapmaları “anomali” olarak işaretlemektir. Sistemin ürettiği şeyler: kütüphanelere işlenmiş ham veri, kütüphanelere işlenmiş etiketli veri, örüntü kütüphanesine yazılmış örüntü haritaları, anomali skoru + geçmiş etki oranı ve opsiyonel yönetici alarm kayıtlarıdır. Veri deposu teknolojisi JSON dosya tabanlı kütüphane deposudur. Kullanılacak formatlar JSON (kalıcı dosyalar) ve JSONL (büyük zaman serileri ve event/log akışları) olacaktır. Kod yazarı SQL/NoSQL/Postgres/MongoDB/Redis kullanmaz; yalnız dosya sistemi üzerinde JSON/JSONL üretir, okur ve günceller. Dosya yolu zorunludur: tüm dosyalar n8n proje dizininde ./library/ altında tutulur; absolute path yoktur, sadece relative path vardır. JSON dosyaları sınırsız büyütülmez; ham veri günlük dosyalara yazılır (YYYY-MM-DD.json), eskiler ./library/archive altına taşınır; index dosyaları her çalıştırma sonunda yeniden üretilir. Kütüphane hiyerarşisi sabittir ve bozulmaz: spor türü → ülke → lig → takım → sezon → dönem → maç → zaman bağlamı. Dönem tanımı sabittir: sezon başı / sezon ortası / sezon sonu; sezon ortası sabiti: devre arası son 3 hafta + ikinci devre başı ilk 3 hafta (“sezon ortası kritik pencere” etiketi). Sistem evreleri iki evredir: Evre-1 bootstrap (geçmiş veri çek, yerleştir, etiketle, örüntü haritaları üret, kalibrasyonu sabitle) + Evre-2 live (yeni maçları işle, kütüphaneyi büyüt, örüntü duvarını güncelle, anomali çıktıları üret). Veri giriş katmanı 3 ana kaynaktır: haber (newsapi.org) + piyasa/oran (oddsapi.io) + canlı event (basketbol live scores + match events ayrı API). Live event kaynağı newsapi/oddsapi değildir, ayrı kaynaktır. Gizli bilgiler manuel girilir; kod yazarı anahtar istemez, değer uydurmaz, sadece alan açar. 

ZORUNLU KONFİGÜRASYON DOSYASI: 
./library/config.json | alanlar: newsapi\\\_key, oddsapi\\\_key, live\\\_event\\\_api\\\_key, live\\\_event\\\_provider\\\_name, live\\\_event\\\_endpoint\\\_base, odds\\\_snapshot\\\_interval\\\_minutes, odds\\\_required\\\_markets, listed\\\_sports, basketbol\\\_league\\\_allowlist, cup\\\_allowlist, reference\\\_dictionary\\\_source, mode(public\\\_only/vip\\\_enabled). config.json boşsa sistem pasif modda kırılmadan çalışır. Kimlik/registry standardı zorunludur: ./library/basketball\\\_index.json içinde reference\\\_dictionary bloğu bulunur, tüm etiketleme sadece bu sözlükten yapılır. Eşleşmeyen kayıtlar unmapped rafına yazılır; yakın eşleştirme ile zorla atama yapılmaz. Maçlar sistem match\\\_id ile sabitlenir; modüller yalnız match\\\_id üzerinden bağlanır. Bootstrap kapsamı: zorunlu minimum son 3 tamamlanmış sezon indirilir ve kütüphanelere işlenir; API destekliyorsa daha fazlası çekilebilir ama minimum 3 sezondur. Basketbol modülü raf seti sabittir: basketbol kütüphanesi + haber kütüphanesi + oran/piyasa kütüphanesi + örüntü kütüphanesi + kupa kütüphanesi. Sosyal medya yoktur, dış yayın kanalı yoktur; çıktılar yalnız kütüphane dosyalarına ve index dosyalarına yazılır. Haber kütüphanesi ham sinyaldir, yorum yoktur: raf sırası = spor → ülke → lig → takım → sezon → dönem → zaman bağlamı → haber kaynağı → haber türü → haber tonu → haber metni. Haber tonu zorunlu: pozitif/nötr/negatif. Zaman bağlamı zorunlu: maç öncesi/maç günü-maç anı/maç sonrası/maçtan sonraki günler. Haber türü zorunlu: ajans/köşe/röportaj/yorum/sızıntı. Oran/piyasa kütüphanesi kolektif beklenti kaydıdır, tahmin değildir. Bookmaker seti sabittir: bet365, pinnacle, william hill, betfair, unibet, bwin, 888sport. Raf sırası = spor → ülke → lig → takım → sezon → dönem → maç → timestamp → bookmaker → market → line → odds\\\_set. Snapshot aralığı odds\\\_snapshot\\\_interval\\\_minutes ile zorunludur; odds\\\_required\\\_markets boş bırakılamaz (en az 1 market). Snapshot < 2 ise oran sapması hesaplanmaz; sapma skoru “hesaplanamadı/veri yetersiz” bandında kalır ve “anomali yok” yazılamaz. Maç/saha kütüphanesi maç içi olayları kaydeder: periyot skorları, faul sayıları, teknik faul, diskalifiye, top kaybı kümeleri, run, timeout, momentum kırılımları, son periyot kırılma noktaları. Hakem rafı ölçüm taşır (faul standardı/düdük yoğunluğu/bonus giriş/teknik faul eğilimi/maç sonu düdük profili), yorum ve suçlama dili taşımaz. Örüntü kütüphanesi 3 girdiyi birleştirir: basın/haber + oran/piyasa + maç içi olay. Çıktı: örüntü kodu + tekrar sayısı + geçmiş etki oranı + anomaly\\\_score. Raflar: ana örüntü rafı + bayraklı/anomali örüntü rafı. Bu raf “şike” olarak adlandırılamaz; yalnız “olağan dışı sapma”dır. Örüntü üretimi 2 aşamalıdır, sıra değişmez: Aşama-1 (topla/ayrıştır/yerleştir/index üret) + Aşama-2 (geriye dönük tarama/örüntü çıkar/normal davranış referansı/anomaly\\\_score kalibrasyonu). Aşama-2 kalibrasyonu bootstrap son 5 sezon verisi üzerinden sabitlenir; kod yazarı elle formül uydurmaz. Anomali skor formülü sabittir: anomaly\\\_score = (basın tonu sapması puanı) + (oran sapması puanı) + (maç içi kritik olay puanı). Bu 3 puanın 0–100 normalizasyonu ve ağırlıkları Aşama-2 tarafından üretilir ve sabitlenir. Aşama-2 tamamlanmadan anomalies boş veya “henüz hesaplanmadı” olabilir, bu hata değildir. Canlı event: bu sistemde insan canlı izleyici yoktur; event verisi API’den gelir. Live event yoksa maç içi kritik olay puanı 0 kalır ve sistem kırılmaz. Live event aktifse JSONL event alanları: match\\\_id, sport\\\_type, event\\\_type, event\\\_minute, team\\\_ref, timestamp. Bu modülde runtime “soru üreten motor” yoktur; arşivden import edilse bile runtime sözleşmesine dahil edilmez. Soru adedi hedefi yoktur; kapsama prensiple kilitlenir. low/medium/high bantları sadece basketbol bağlamında kullanılır; ganyan dili basketbola taşınmaz; “pist/mesafe/binici” etiketleri basket modülünde kullanılmaz. 

Zorunlu index dosyaları her çalıştırmada üretilir: 
./library/basketball\\\_index.json, ./library/basketball\\\_summary.json, ./library/basketball\\\_today\\\_matches.json, ./library/basketball\\\_anomalies\\\_public.json, ./library/basketball\\\_anomalies\\\_vip.json. Dosyalar boş olabilir ama üretimi zorunludur. 
“Anomali yok” yalnız sapma skoru hesaplanmış ve eşik altında kalmış durumda kullanılabilir; veri eksikliği “anomali yok” yazılamaz. Log/denetim zorunludur: hangi veri çekildi, hangi kütüphaneye yazıldı, hangi örüntü eşleşti, hangi anomali bayrağı yandı, hangi kayıt unmapped kaldı, hangi data\\\_quality\\\_badge uygulandı. Bu promptta tanımlanan yapı tamamlanmış ve kilitlenmiş bir basketbol sistem mimarisidir. Kod yazarı metni yorumlamaz; ekleme/çıkarma yapmaz; sırayı bozmaz; isimleri değiştirmez; branş dışı etiket üretmez; veri yoksa uydurmaz.\*\*

FAZ-27
BASKETBOL/FUTBOL — KİMLİK KARTI ÖZEL KİMLİK ÜRETİM STANDARDI (KİLİT / PROVIDER ID DRIFT KORUMASI) |
provider ID değişebilir; bu nedenle tüm varlık kartları provider ID ile tek başına yaşamaz; her kartta ayrıca sabit canonical\\\_identity\\\_key zorunludur; canonical\\\_identity\\\_key deterministik bileşenlerden üretilir, veri yoksa unknown yazılır, uydurma yapılmaz; takım kartı takım rafında kalır, kadro takımda snapshot olabilir ama oyuncu kimliği oyuncu kartında yaşar; oyuncu kartı oyuncunun peşinde taşınır ve geçmişten geleceğe oyunculuk hayatı boyunca tek kartta birikir; koç kartı koçun peşinde taşınır ve kariyeri boyunca tek kartta birikir; hakem kartı hakemin peşinde taşınır ve kariyeri boyunca tek kartta birikir; bu kimlik drift kontrolü içindir, tahmin/öneri üretmez. 

Takım Kartı Kimliği 
(TEAM\\\_CANON\\\_ID) | ülke + lig + takım adı + şehir + renk + varsa stat ismi + kuruluş tarihi(GGAAYY) + cinsiyet(male/female/mixed/unknown) + sayaç(00001–10000, auto) birleşimidir; sayaç elle yazılmaz. 

Oyuncu Kartı Kimliği 
(PLAYER\\\_CANON\\\_ID) | ad soyad + doğum tarihi + pozisyon + ilk lisans aldığı takım + başladığı yıl + uyruk + cinsiyet(male/female/unknown) + en son oynadığı takım + sayaç(000001–100000, auto) birleşimidir; sayaç elle yazılmaz. 

Hoca Kartı Kimliği 
(COACH\\\_CANON\\\_ID) | ad soyad + doğum tarihi + uyruk + cinsiyet(male/female/unknown) + başladığı kulüp + başladığı yıl + sayaç(00001–10000, auto) birleşimidir; sayaç elle yazılmaz. 

Hakem Kartı Kimliği 
(REFEREE\\\_CANON\\\_ID) | ad soyad + doğum tarihi + uyruk + cinsiyet(male/female/unknown) + başladığı yıl + statüsü + sayaç(000001–100000, auto) birleşimidir; sayaç elle yazılmaz; statü veri yoksa unknown yazılır. Kimlik Drift Tespiti (Kilit Davranış) | yeni provider ID geldiğinde canonical\\\_identity\\\_key eşleşiyorsa sistem same\\\_entity\\\_id\\\_drift\\\_detected işaretler, provider\\\_id günceller, canonical kimliği değiştirmez; canonical\\\_identity\\\_key üretilemeyecek kadar eksik veri varsa kayıt data\\\_quality\\\_badge ile güvenli saklanır, zorla eşleştirme yapılmaz.\*\*


BASKETBOL — CANLI İZLEME / RAPORLAMA / KÜTÜPHANEYE YAZIM | OTOMASYON EKİBİ ÇALIŞMA TALİMATI (GENİŞ SÜRÜM / ROL TABLOSU GÖMÜLÜ / KODCUYA VERİLECEK)
Bu sistemde canlı insan yoktur. Watcher/Reporter/Analyst/Librarian/Decision Engine rollerinin tamamı otomasyon ajanlarıdır. Tek insan operatör kullanıcıdır; operatör yalnız manuel tetikleme yapar. Sistem bahis sistemi değildir; maç sonucu veya bahis önerisi üretmez; çıktılar yalnız istatistiksel ölçüm, zaman hizası ve bant sapması işaretidir. ROL TABLOSU | Watcher Agents: 14 | Reporter Agents: 4 | Analyst Agents: 1 | Librarian: 1 | Decision Engine: 1 | Toplam: 21 | Tek Operatör: 1 | Not: “14 izleyici + 4 raportör + 1 analist + 1 kütüphaneci” sabittir; Decision Engine bağımsız modüldür ve bahis önerisi üretmeden yalnız skor/tempo/şema sapmasını karar etiketi olarak işaretler.
 
SİSTEMİN YAPTIĞI İŞ |
canlı olay izlerini toplar, tekilleştirir, çelişkiyi çözmeden işaretler, deterministik şemada kütüphaneye işler; veri eksikse “anomali yok” denmez, data\\\_quality\\\_badge düşürülür; basın rafı bağlamdır, maç içi eksik event basınla tamamlanamaz.

KİMLİK/REFERENCE POLİTİKASI | 
serbest metin kimlik yoktur; team\\\_ref/league\\\_ref/country\\\_ref/person\\\_ref yalnız reference\\\_dictionary’den gelir; unmapped zorla eşlenmez; reference\\\_dictionary dışında benzer isim eşlemesi yapılmaz; unmapped kayıtlar güvenlik bandıdır ve korunur.
 
BOŞ BIRAKMA / UYDURMA YASAĞI |
veri yokken alan boş bırakılmaz; unknown/none/inactive/unmapped bantları deterministik kullanılır; “anomali yok” hükmü veri eksikliğiyle yazılamaz.
 
ROL SETİ | 
Watcher: ham iz toplar, yorum yazmaz, paket dışı kayıt girmez, karar motoruna yazmaz | Reporter: tekilleştirir, çelişkiyi işaretler, yorum yazmaz | Analyst: paketleri birleştirir, informed\\\_by kurar, ölçüm bandı üretir, tahmin/bahis önerisi üretmez | Librarian: tek yazıcıdır, şema dışına çıkamaz, serbest metin kimlik kullanamaz, unmapped zorlamaz, eksikleri örtmez, append\\\_only çalışır | Decision Engine: yalnız Analyst raporundan beslenir, ham veri değiştiremez, bahis önerisi vermez, karar etiketleri üretir, kütüphaneye yazmaz. 

ZAMANLAMA / KAYIT MODELİ |
olay-anı bazlıdır; otomatik timestamp\\\_utc alınır; 30 saniyelik indeks bandı otomatik atanır; manuel band seçimi/düzeltmesi yoktur; olay yoksa no\\\_event ile veri doldurulmaz, olay yokluğu yalnız kapsama haritasında gösterilir. 30s indeks bandı | Q1\\\_00:00-00:29, Q1\\\_00:30-00:59 … Q4\\\_39:30-39:59 | ek bantlar: clutch\\\_02:00, clutch\\\_01:00, clutch\\\_00:30. 

PAKETLEME | 4 paket | Watcher dağılımı 4+4+3+3 | her paket 1 Reporter | Analyst üst birleştirici | Librarian nihai yazıcı. PAKET-1(BP1)

SKOR/RUN/MOMENTUM | 
score\\\_run\\\_start, score\\\_run\\\_end, lead\\\_change, tie\\\_game, momentum\\\_shift, quarter\\\_close\\\_behavior, clutch\\\_run.
 
PAKET-2(BP2) FAUL/HAKEM/FT |
team\\\_foul\\\_cluster, star\\\_foul\\\_trouble, bonus\\\_entered, technical\\\_foul, flagrant\\\_foul, free\\\_throw\\\_swing, referee\\\_line\\\_shift\\\_soft, referee\\\_line\\\_shift\\\_hard. 

PAKET-3(BP3) ROTASYON/5’Lİ/KOÇ |
timeout\\\_called, timeout\\\_run\\\_break, lineup\\\_change, closing\\\_lineup\\\_set, early\\\_bench\\\_injection, coach\\\_adjustment\\\_visible.
 
PAKET-4(BP4) ŞUT/3PT/TOP KAYBI | 
three\\\_point\\\_streak\\\_hit, three\\\_point\\\_streak\\\_miss, shot\\\_quality\\\_drop, paint\\\_attack\\\_shift, turnover\\\_cluster, live\\\_ball\\\_turnover\\\_fastbreak, pace\\\_spike, pace\\\_drop.
 
WATCHER HAM İZ (ZORUNLU ŞEMA) |
watch\\\_trace\\\_ref:AUTO | match\\\_ref:REQUIRED | timestamp\\\_utc:REQUIRED | index\\\_band\\\_auto\\\_30s:REQUIRED | package\\\_id:REQUIRED(BP1/BP2/BP3/BP4) | watcher\\\_id:REQUIRED | event\\\_type:REQUIRED | event\\\_subtype:OPTIONAL | team\\\_side:home/away/none | team\\\_ref:OPTIONAL | person\\\_ref:OPTIONAL(none) | league\\\_ref:OPTIONAL | country\\\_ref:OPTIONAL | confidence\\\_band:low/medium/high | evidence\\\_level:low/medium/high | source\\\_type:live\\\_feed/stats\\\_feed/odds\\\_feed | data\\\_quality\\\_badge:low/medium/high | note:kısa deterministik açıklama(yorum yok).
 
REPORTER PAKET RAPORU (ZORUNLU ŞEMA) |
package\\\_report\\\_ref:AUTO | match\\\_ref:REQUIRED | package\\\_id:REQUIRED | reporter\\\_id:REQUIRED | event\\\_sequence:REQUIRED | deduplication\\\_map:REQUIRED | conflict\\\_list:REQUIRED | unknown\\\_fields\\\_map:REQUIRED | package\\\_data\\\_quality\\\_badge:low/medium/high.

ANALYST TEK MAÇ RAPORU (ZORUNLU ŞEMA) |
match\\\_report\\\_ref:AUTO | match\\\_ref:REQUIRED | merged\\\_packages:REQUIRED(BP1..BP4) | final\\\_conflict\\\_resolution:mark\\\_only | overall\\\_data\\\_quality\\\_badge:low/medium/high | anomaly\\\_flags:none/weak\\\_signal/strong\\\_signal | informed\\\_by:match\\\_card\\\_ref|match\\\_events\\\_ref|odds\\\_timeline\\\_ref | delivery\\\_policy:no\\\_prediction|no\\\_betting\\\_advice | kural:evidence\\\_level/confidence\\\_band yüksek olsa bile data\\\_quality\\\_badge düşükse çözüm yapılmaz, yalnız mark\\\_only. 

LIBRARIAN YAZIM KURALLARI (SERT) |
deterministik raflara yazar | serbest metin kimlik yok | reference\\\_dictionary dışı eşleme yok | unmapped zorla map yok | basın rafı maç içi rafları doldurmaz | veri yoksa boş bırakmaz unknown/none/inactive | eksik örtmez data\\\_quality\\\_badge düşürür | silmez append\\\_only | aynı match\\\_ref güncellenirse sürümleme yapar. 

DECISION ENGINE |
yalnız Analyst raporundan beslenir | ham veriyi üretemez/değiştiremez | tahmin/bahis önerisi vermez | deterministik karar etiketleri üretir | kütüphaneye yazmaz karar\\\_motoru rafında saklar | decision\\\_tags: run\\\_instability\\\_high, foul\\\_risk\\\_high, clutch\\\_control\\\_low, turnover\\\_spike\\\_high, three\\\_point\\\_variance\\\_high, rotation\\\_disruption\\\_high, referee\\\_line\\\_shift\\\_detected, tempo\\\_control\\\_shifted. Kapanış Notu | Basketbol Canlı İzleme + Kütüphane Yazım Talimatı — geniş sürüm + rol tablosu + 30s indeksleme tamamlandı / tek dosya olarak kullanılacak.

BASKETBOL — MARKET KÜTÜPHANESİ (ANA TAHTA + YAN TAHTA) | FAZ-1 TESLİMİ (Kart + Etiket Duvarı + Soru Kütüphanesi / TEK PARÇA BİRLEŞİK)
library\\\_ref:BASKETBALL\\\_MARKET\\\_LIBRARY\\\_V1 | kart\\\_durumu:FAZ-1\\\_SKELETON\\\_ACTIVE | politika: market listesi deterministik/sabit; market\\\_ref ile yaşar; isim serbest metin değildir; provider map ile bağlanır; unmapped korunur; eksik veri inactive/unknown bantlarıyla taşınır; bahis önerisi yok; zaman hizası ve bant sapması ölçer | not: ana tahta + yan tahta market rafı kurulur; odds akışı ve BOOKMAKER\\\_ALLOWLIST Faz-2’de marketlere bağlanır.

BASKETBOL — ANA TAHTA MARKETLER (30 ANA MARKET / DETERMINİSTİK LİSTE)
BB\\\_MKT\\\_001 | Moneyline(Match Winner) | group:core\\\_result | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_002 | Point Spread(Handicap) | group:spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_003 | Total Points(O/U) | group:totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_004 | 1st Half Winner | group:halftime | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_005 | 1st Half Spread | group:halftime\\\_spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_006 | 1st Half Total Points | group:halftime\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_007 | 1st Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_008 | 1st Quarter Spread | group:quarter\\\_spread 

| required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_009 | 1st Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_010 | 2nd Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_011 | 2nd Quarter Spread | group:quarter\\\_spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_012 | 2nd Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_013 | 3rd Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_014 | 3rd Quarter Spread | group:quarter\\\_spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_015 | 3rd Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_016 | 4th Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_017 | 4th Quarter Spread | group:quarter\\\_spread | required:line,home\\\_price,away\\\_price | status:active 

| BB\\\_MKT\\\_018 | 4th Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_019 | Team Total Points | group:team\\\_totals | required:team\\\_side,line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_020 | Race To X Points | group:race | required:target\\\_points,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_021 | Winning Margin | group:margin | required:margin\\\_price\\\_map | status:active | BB\\\_MKT\\\_022 | Highest Scoring Quarter | group:quarter\\\_meta | required:q1\\\_price,q2\\\_price,q3\\\_price,q4\\\_price | status:active | BB\\\_MKT\\\_023 | Lowest Scoring Quarter | group:quarter\\\_meta | required:q1\\\_price,q2\\\_price,q3\\\_price,q4\\\_price | status:active | BB\\\_MKT\\\_024 | Team To Score First(First Points) | group:first\\\_event | required:home\\\_price,away\\\_price | status:active 

| BB\\\_MKT\\\_025 | Total Points Odd/Even | group:totals\\\_parity | required:odd\\\_price,even\\\_price | status:active | BB\\\_MKT\\\_026 | Both Teams Over X(Alt Combo) | group:combo | required:line\\\_a,line\\\_b,yes\\\_price,no\\\_price | status:active | BB\\\_MKT\\\_027 | Total 3PT Made(O/U) | group:three\\\_point | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_028 | Team Total 3PT Made | group:team\\\_three\\\_point | required:team\\\_side,line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_029 | Player Points(O/U) | group:player\\\_points | required:player\\\_ref,line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_030 | Player Rebounds(O/U) | group:player\\\_rebounds | required:player\\\_ref,line,over\\\_price,under\\\_price | status:active

BASKETBOL — YAN TAHTA MARKETLER (30 EXTENDED / NİŞ RAF)
BB\\\_XMKT\\\_001 | Player Assists(O/U) | group:player\\\_assists | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_002 | Player Steals(O/U) | group:player\\\_steals | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_003 | Player Blocks(O/U) | group:player\\\_blocks | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_004 

| Player Turnovers(O/U) | group:player\\\_turnovers | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_005 | Player 3PT Made(O/U) | group:player\\\_three\\\_point | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_006 | Player Double-Double | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_007 | Player Triple-Double | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_008 | Team Total Rebounds | group:team\\\_rebounds | required:team\\\_side,line,over\\\_price,under\\\_price 

| status:inactive | BB\\\_XMKT\\\_009 | Team Total Assists | group:team\\\_assists | required:team\\\_side,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_010 | Team Total Turnovers | group:team\\\_turnovers | required:team\\\_side,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_011 | Player PRA(P+R+A) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_012 | Player PA(P+A) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_013 | Player PR(P+R) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_014 | Player RA(R+A) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_015 | Player Points 1st Half | group:player\\\_points\\\_split 

| required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_016 | Player Points 1st Quarter | group:player\\\_points\\\_split | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_017 | Player Rebounds 1st Half | group:player\\\_rebounds\\\_split | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_018 | Player Assists 1st Half | group:player\\\_assists\\\_split | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_019 | Player To Score 20+ | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive 

| BB\\\_XMKT\\\_020 | Player To Score 25+ | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_021 | Player To Score 30+ | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_022 | First Basket Scorer | group:first\\\_event | required:player\\\_ref,yes\\\_price | status:inactive | BB\\\_XMKT\\\_023 | Last Basket Scorer | group:last\\\_event | required:player\\\_ref,yes\\\_price | status:inactive | BB\\\_XMKT\\\_024 | First Team To Make 5 Threes | group:team\\\_race | required:home\\\_price,away\\\_price | status:inactive | BB\\\_XMKT\\\_025 | Total Free Throws Made(O/U) 

| group:free\\\_throws | required:line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_026 | Team Total Free Throws Made | group:team\\\_free\\\_throws | required:team\\\_side,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_027 | Total Turnovers(Match) | group:turnovers | required:line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_028 | Alternative Spread(Alt Handicap) | group:alt\\\_spread | required:line,home\\\_price,away\\\_price | status:inactive | BB\\\_XMKT\\\_029 | Alternative Totals(Alt O/U) | group:alt\\\_totals | required:line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_030 | Player Points+3PT Combo | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive


BASKETBOL — MARKET ETİKET DUVARI (FAZ-1 DETERMINİSTİK) | unknown:veri\\\_yok/doğrulanmadı | none:alan\\\_geçerli\\\_içerik\\\_yok | inactive:provider\\\_yok/market\\\_kapalı | unmapped:provider\\\_eşleşmesi\\\_yok | active:takipte | inactive\\\_market:market\\\_verisi\\\_yok/pasif | market\\\_group: core\\\_result|spread|totals|halftime|halftime\\\_spread|halftime\\\_totals|quarter|quarter\\\_spread|quarter\\\_totals|team\\\_totals|race|margin|quarter\\\_meta|first\\\_event|totals\\\_parity|combo|three\\\_point|team\\\_three\\\_point|player\\\_points|player\\\_rebounds|player\\\_assists|player\\\_steals|player\\\_blocks|player\\\_turnovers|player\\\_milestones|team\\\_rebounds

|team\\\_assists|team\\\_turnovers|player\\\_combo|player\\\_points\\\_split|player\\\_rebounds\\\_split|player\\\_assists\\\_split|team\\\_race|free\\\_throws|team\\\_free\\\_throws|alt\\\_spread|alt\\\_totals|turnovers | market\\\_status:active|inactive|inactive\\\_market | required\\\_fields\\\_completeness:low|medium|high | provider\\\_mapping\\\_status:unmapped|mapped | odds\\\_update\\\_speed\\\_band:unknown|slow|medium|fast | market\\\_latency\\\_band:unknown|low|medium|high | inplay\\\_availability\\\_band:unknown|low|medium|high | suspension\\\_tendency\\\_band:unknown|low|medium|high | closing\\\_line\\\_integrity\\\_band:unknown|low|medium|high | Kapanış: Market Kütüphanesi tamamlandı.

BOOKMAKER KÜTÜPHANESİ — FAZ-1 TESLİMİ
(Kart + Etiket Duvarı + Soru Kütüphanesi) 
library\\\_ref:BOOKMAKER\\\_LIBRARY\\\_V1 | kart\\\_durumu:FAZ-1\\\_SKELETON\\\_ACTIVE | politika: bahis önerisi yok; bookmaker\\\_ref reference\\\_dictionary’den gelir; unmapped zorla eşlenmez; eksik veri unknown/none/inactive ile korunur. 

BOOKMAKER KARTI (FAZ-1 İSKELET) 
bookmaker\\\_ref:UNKNOWN\\\_BOOKMAKER\\\_REF | bookmaker\\\_name:unknown | brand\\\_variants:none | license\\\_country\\\_ref:unknown | service\\\_regions:unknown | feed\\\_provider\\\_ref:unknown | supported\\\_sports:unknown | supported\\\_leagues\\\_scope:unknown | tier\\\_support\\\_band:unknown | odds\\\_feed\\\_status:inactive | data\\\_quality\\\_badge:low 
| Coverage(core\\\_markets\\\_supported:unknown,extended\\\_markets\\\_supported:unknown,player\\\_props\\\_supported:unknown,inplay\\\_supported:unknown,market\\\_depth\\\_band:unknown,alt\\\_lines\\\_supported:unknown) 
| UpdateLatency(odds\\\_update\\\_speed\\\_band:unknown,market\\\_latency\\\_band:unknown,timestamp\\\_integrity\\\_band:unknown,suspension\\\_tendency\\\_band:unknown,reopen\\\_behavior\\\_band:unknown) | PricingLine(line\\\_shift\\\_frequency\\\_band:unknown,price\\\_shift\\\_frequency\\\_band:unknown,line\\\_vs\\\_price\\\_preference:unknown,opening\\\_line\\\_style\\\_band:unknown,closing\\\_line\\\_style\\\_band:unknown,risk\\\_rebalance\\\_style\\\_band:unknown) | Drift(divergence\\\_vs\\\_pack\\\_band:unknown,persistent\\\_drift\\\_band:unknown,spike\\\_anomaly\\\_tendency\\\_band:unknown,sharp\\\_following\\\_band:unknown,contrarian\\\_band:unknown) 
| Integrity(void\\\_cancel\\\_policy\\\_band:unknown,limit\\\_restriction\\\_band:unknown,market\\\_freeze\\\_pattern\\\_band:unknown,outage\\\_incident\\\_band:unknown,feed\\\_gap\\\_band:unknown) | InformedBy(odds\\\_market\\\_timeline:none,market\\\_library\\\_ref:none,match\\\_ref:none,league\\\_ref:none). 

BOOKMAKER ETİKET DUVARI (FAZ-1) |
unknown:veri\\\_yok/doğrulanmadı | none:alan\\\_geçerli\\\_içerik\\\_yok | inactive:feed\\\_yok/pasif | unmapped:reference\\\_dictionary\\\_eşleşmesi\\\_yok | weak\\\_signal:tekil\\\_zayıf\\\_kaynak | strong\\\_signal:çoklu\\\_kaynak\\\_teyidi | odds\\\_feed\\\_status:inactive|active | tier\\\_support\\\_band:unknown|tier1\\\_only|tier1\\\_tier2 | market\\\_depth\\\_band:unknown|shallow|medium|deep | player\\\_props\\\_supported:unknown|low|medium|high | inplay\\\_supported:unknown|low|medium|high | alt\\\_lines\\\_supported:unknown|low|medium|high | odds\\\_update\\\_speed\\\_band:unknown|slow|medium|fast | market\\\_latency\\\_band:unknown|low|medium|high 

| timestamp\\\_integrity\\\_band:unknown|low|medium|high | suspension\\\_tendency\\\_band:unknown|low|medium|high | reopen\\\_behavior\\\_band:unknown|stable|jumpy | line\\\_shift\\\_frequency\\\_band:unknown|low|medium|high | price\\\_shift\\\_frequency\\\_band:unknown|low|medium|high | line\\\_vs\\\_price\\\_preference:unknown|line\\\_first|price\\\_first|mixed | opening\\\_line\\\_style\\\_band:unknown|conservative|balanced|aggressive | closing\\\_line\\\_style\\\_band:unknown|tight|loose | risk\\\_rebalance\\\_style\\\_band:unknown|smooth|stepwise|abrupt | divergence\\\_vs\\\_pack\\\_band:unknown|low|medium|high | persistent\\\_drift\\\_band:unknown|low|medium|high 

| spike\\\_anomaly\\\_tendency\\\_band:unknown|low|medium|high | sharp\\\_following\\\_band:unknown|low|medium|high | contrarian\\\_band:unknown|low|medium|high | void\\\_cancel\\\_policy\\\_band:unknown|strict|balanced|lenient | limit\\\_restriction\\\_band:unknown|low|medium|high | market\\\_freeze\\\_pattern\\\_band:unknown|low|medium|high | outage\\\_incident\\\_band:unknown|low|medium|high | feed\\\_gap\\\_band:unknown|low|medium|high | BOOKMAKER SORU KÜTÜPHANESİ (FAZ-1) | | Kapanış: Bookmaker Kütüphanesi tamamlandı.

BASKETBOL — ARŞİV PAKETİ (NİHAİ) | Tamamlandı / dosyalanabilir tek çıktı | Bitti.

KİLİT BEYANI | 
Bu metin “BASKETBOL — ARŞİV PAKETİ (NİHAİ / KODCUYA VERİLECEK /)” olarak kilitlenmiştir. 


FAZ-31
DOSYA-1: BASKETBALL\\\_MODULE\\\_IMPLEMENTATION\\\_PROMPT\\\_FINAL.txt\

BASKETBOL MODÜLÜ — 5 YIL DAYANIKLILIK REVİZESİ + 3 PROBLEM DÜZELTİLMİŞ NİHAİ UYGULAMA PROMPTU\*\*
Aşağıdaki metin yoruma kapalı, bağlayıcı ve birebir uygulanması zorunlu “uygulama promptu”dur. Bu metinde yazan her adım, her sıra, her rol, her yapı, her isimlendirme ve her kural değiştirilemez. Kod yazarı “daha iyisi olur”, “şöyle yapalım”, “şunu çıkaralım”, “bunu ekleyelim” gibi hiçbir yorum, öneri ve alternatif üretmez. Metinde olmayan hiçbir özellik eklenmez. Metinde olan hiçbir özellik çıkarılmaz. Yalnızca teknik olarak imkânsızlık varsa sadece “şu madde teknik olarak uygulanamıyor” cümlesiyle bildirir ve uygulama durdurulur. Çözüm önerisi getirilmez, soru sorulmaz, fikir üretilmez. Bu prompt bir taslak değildir. Tamamlanmış ve kilitlenmiş sistem mimarisidir. Bu proje “bahis sitesi” kurmaz. Bu proje “bahse yönlendirme” yapmaz. Bu proje kupon oluşturmaz. Bu proje ödeme almaz. Bu proje yalnız istatistiksel ölçüm, zaman hizası ve bant sapması üretir. “Kesin kazanır, banko, tek” gibi dil yasaktır.\*\*

Sistemin adı:
Spor Anomali \\\& Örüntü Motoru (n8n tabanlı). Bu modül basketbol içindir ve ana omurgadan ayrı değildir; aynı sistemin basketbol dalıdır. Sistemin amacı: basketbol için haber + piyasa/oran + maç içi olay verilerini tek hiyerarşide toplamak, örüntü üretmek ve olağan akışa aykırı sapmaları “anomali” olarak işaretlemektir. Sistem çıktıları tahmin değildir; yalnız kütüphanelere işlenmiş ham veri, kütüphanelere işlenmiş etiketli veri, örüntü kütüphanesine yazılmış örüntü haritaları, anomali skoru + geçmiş etki oranı ve yönetici alarm kayıtlarıdır. Bu modülde sosyal medya dağıtımı yoktur. Telegram/Instagram/TikTok/YouTube Shorts yoktur. Çıktılar yalnız kütüphane dosyalarına ve index dosyalarına yazılır.

Bu projede veri deposu teknolojisi zorunlu mimari kuraldır. Veri deposu teknoloji olarak JSON dosya tabanlı kütüphane deposudur. Kullanılacak formatlar JSON (kalıcı dosyalar) ve JSONL (büyük zaman serileri ve event/log akışları) olacaktır. Kod yazarı SQL / NoSQL / Postgres / MongoDB / Redis kullanmaz. Kod yazarı yalnız dosya sistemi üzerinde JSON/JSONL üretir, okur ve günceller. Tüm dosyalar n8n proje dizininde ./library/ altında tutulur. Absolute path kullanılmaz. Sadece relative path kullanılır. JSON dosyalarının sınırsız büyümesine izin verilmez. Ham veri dosyaları günlük dosyalara yazılır ve dosya adı YYYY-MM-DD.json formatındadır. Eski ham veri dosyaları ./library/archive altına taşınır. Index dosyaları her çalıştırma sonunda tekrar üretilir ve güncel özet tutulur; tüm tarihçe tek dosyada biriktirilmez.her dosya spor branşının kendi adıyla balaşar.

Ana kural: 

tüm kütüphaneler aynı hiyerarşiyi kullanır ve bu sıra hiçbir yerde bozulmaz. Sıra her zaman şu şekildedir: spor türü → ülke → lig → takım → sezon → dönem → maç → zaman bağlamı. Dönem tanımı zorunludur ve her kütüphanede aynıdır. Her sezon üç döneme ayrılır: sezon başı, sezon ortası, sezon sonu. Sezon ortası zamansal sabiti devre arası son 3 hafta + ikinci devre başı ilk 3 haftadır ve “sezon ortası kritik pencere” etiketi olarak ortak uygulanır.

Sistem evreleri iki evredir ve net olarak ayrılacaktır. Evre-1 bootstrap (faaliyet öncesi) amacı geçmiş veriyi çekmek, kütüphanelere yerleştirmek, etiketlemek, örüntü haritalarını üretmek ve kalibrasyonu sabitlemektir. Evre-2 live (faaliyet sonrası) amacı yeni maçları aynı sistemle işlemek, kütüphaneyi büyütmek, örüntü duvarını güncellemek ve anomali çıktıları üretmektir. Bootstrap kapsamı sabit kuraldır: sistem zorunlu olarak son 3 tamamlanmış sezonu indirir ve basketbol kütüphanelerine işler. API daha fazla sezon destekliyorsa sistem daha fazlasını çekebilecek şekilde tasarlanır; ancak zorunlu minimum son 3 tamamlanmış sezondur.

Veri giriş katmanı bu sistemde üç ana veri kaynağı kullanır: haber verisi kaynağı (newsapi.org), piyasa/oran verisi kaynağı (oddsapi.io), canlı maç olay verisi kaynağı (basketbol live scores + match events destekleyen ayrı bir API). Live event kaynağı newsapi ve oddsapi ile sağlanmaz, mutlaka ayrı kaynaktır. Bu kaynaklara erişim için gereken tüm gizli bilgiler (api key, token, webhook url, kanal id) otomasyon kurulumunda manuel olarak girilir. Kod yazarı bu bilgileri talep etmez, beklemez, içerik üretmez; sadece bu gizli bilgilerin girileceği alanları hazırlar.

Zorunlu manuel konfigürasyon dosyası 

./library/config.json olacaktır ve şu alanları zorunlu taşır: 
newsapi\\\_key, oddsapi\\\_key, live\\\_event\\\_api\\\_key, live\\\_event\\\_provider\\\_name, live\\\_event\\\_endpoint\\\_base, odds\\\_snapshot\\\_interval\\\_minutes, odds\\\_required\\\_markets, listed\\\_sports, basketbol\\\_league\\\_allowlist, cup\\\_allowlist, reference\\\_dictionary\\\_source, mode (public\\\_only / vip\\\_enabled). Kod yazarı bu dosyayı uydurma değerlerle doldurmaz, sadece alanları açar. Bu dosya boşsa sistem pasif modda çalışır ve kırılmaz.

Kimlik / registry standardı zorunludur. 

API’lerde takım isimleri, lig isimleri ve maç id’leri farklı gelebilir. Bu problem nedeniyle ./library/index.json içinde reference\\\_dictionary bloğu zorunlu olarak bulunur ve tüm etiketleme sadece bu sözlükten yapılır. Eşleşemeyen haberler ve eşleşemeyen kayıtlar unmapped durumuyla ayrı raf’a yazılır. Yakın eşleştirmeyle zorla atama yapılmaz. Sistem maçları “sistem match\\\_id” ile sabitler ve tüm modüller sadece bu match\\\_id üzerinden bağlanır. reference\\\_dictionary kapsama oranı sistem sağlığı göstergesidir; kapsama düşüşü ayrı alarm kaydı olarak saklanır.

Bu basketbol modülü içinde toplam kütüphane seti sabittir ve branşlar karıştırılamaz. Basketbol kapsamındaki mantıksal raflar şunlardır: basketbol kütüphanesi, haber kütüphanesi, oran/piyasa kütüphanesi, örüntü kütüphanesi, kupa kütüphanesi. Bu modülde soru üreten motor yoktur; runtime sözleşmesine dahil edilmez ve çalışma sırasında soru motoru çalıştırılmaz. Bu modülde sayısal soru adedi hedefi bulunmaz; kapsama prensip ile kilitlenir. Bu modülde branş dışı etiket üretimi yoktur; ganyan dili basketbola taşınamaz.

Haber kütüphanesi ham sinyalin kaynağıdır. Haber kütüphanesinde yorum yoktur. Haberler sadece raf düzeniyle saklanır. Haber rafı şu sırayı taşır: spor → ülke → lig → takım → sezon → dönem → zaman bağlamı → haber kaynağı → haber türü → haber tonu → haber metni. Haber tonu zorunludur ve pozitif / nötr / negatif olarak tutulur. Zaman bağlamı zorunludur: maç öncesi, maç günü/maç anı, maç sonrası, maçtan sonraki günler. Haber türü zorunludur: ajans / köşe / röportaj / yorum / sızıntı. Gazeteci/yazar varsa saklanır. 

Oran/piyasa kütüphanesi kolektif beklenti kaydıdır ve tahmin değildir. Bookmaker seti sabittir: bet365, pinnacle, william hill, betfair, unibet, bwin, 888sport. Oran/piyasa kütüphanesinde maç bazlı oranlar şu raf sırasıyla dizilir: spor → ülke → lig → takım → sezon → dönem → maç → timestamp → bookmaker → market → line → odds\\\_set. Odds zaman serisi snapshot standardı zorunludur. Snapshot aralığı odds\\\_snapshot\\\_interval\\\_minutes ile belirlenir ve boş bırakılamaz. odds\\\_required\\\_markets boş bırakılamaz ve en az 1 market içermelidir. Snapshot sayısı iki adetten azsa oran sapması hesabı yapılmaz ve sapma skoru “hesaplanamadı/veri yetersiz” bandında kalır; “anomali yok” yazılamaz.

Basketbol maç/saha kütüphanesi maç içi olayları kaydeder. Basketbol maç rafı şu ana olayları taşır: periyot skorları, faul sayıları, teknik faul, diskalifiye, top kaybı kümeleri, seri koşular (run), molalar (timeout), momentum kırılımları, son periyot kırılma noktaları. Basketbol hakem rafı faul standardı, düdük yoğunluğu, bonus giriş zamanlaması, teknik faul eğilimi ve maç sonu düdük profili gibi ölçümler taşır; yorum ve suçlama dili taşımaz.

Örüntü kütüphanesi üç ana girdiyi birleştirir: 

basın/haber örüntüsü, oran/piyasa örüntüsü, maç içi olay örüntüsü. Örüntü çıktıları örüntü kodu, tekrar sayısı, geçmiş etki oranı ve anomali skorunu taşır. Bu kütüphane iki raf taşır: ana örüntü rafı ve bayraklı/anomali örüntü rafı. Bu raf “şike” olarak adlandırılamaz; yalnız “olağan dışı sapma” olarak adlandırılır.

Örüntü üretimi iki aşamalı çalışır ve sıra değiştirilemez. Aşama-1 sadece veri toplar, ayrıştırır, hiyerarşiye yerleştirir ve index dosyalarını üretir. Aşama-2 sadece geriye dönük tarama ile örüntüleri çıkarır, normal davranış referanslarını üretir ve anomaly\\\_score kalibrasyonunu hesaplar. Aşama-2 kalibrasyonu son 3 sezon bootstrap verisi üzerinden yapılır. Kod yazarı elle formül uydurmaz ve puanlama tahmin etmez. Anomali skor formülü sabittir: anomaly\\\_score = (basın tonu sapması puanı) + (oran sapması puanı) + (maç içi kritik olay puanı). Bu üç puanın 0–100 normalizasyonu ve ağırlıklandırılması Aşama-2 tarafından üretilir ve sabitlenir. Aşama-2 tamamlanmadan anomalies çıktısı boş veya “henüz hesaplanmadı” durumunda kalabilir ve bu hata değildir.

Canlı maç olayları veri gerçekliği şu şekildedir: bu sistemde insan canlı izleyici kadrosu yoktur. Canlı maç olayları API üzerinden gelen canlı event verileriyle beslenir. Canlı event aktif değilse maç içi kritik olay puanı 0 olarak kalır ve sistem kırılmaz. Canlı event feed aktif olduğunda event kayıtları match\\\_id, sport\\\_type, event\\\_type, event\\\_minute, team\\\_ref, timestamp alanlarıyla JSONL olarak yazılır. Event akışında olağan dışı yoğunluk veya olağan dışı sessizlik ayrı bir teknik durumdur ve event\\\_stream\\\_health\\\_band altında saklanır; bu bant maç verisinden bağımsızdır ve sessizce yok sayılmaz.

Zorunlu index dosyaların tümü her spor branşı adıyla başlar,örnek,football\\\_anomaly.json,football\\\_library.json,football\\\_public.json

basket\\\_anomaly.json,basket\\\_library.json,ganyan\\\_anomaly.json

ganyan\\\_library.json

Zorunlu index dosyaları her çalıştırmada üretilir: ./library/index.json, ./library/summary.json, ./library/today\\\_matches.json, ./library/anomalies\\\_public.json, ./library/anomalies\\\_vip.json. Bu dosyalar boş olabilir ancak dosyanın kendisi üretilmek zorundadır. Index üretimi atomik çalışır; yeni index doğrulama kontrollerinden geçmeden mevcut index üzerine yazılmaz. Hatalı üretimde önceki index korunur ve yönetici alarmına yazılır. “Anomali yok” ifadesi yalnız sapma skoru hesaplanmış ve eşik altında kalmış durumda kullanılabilir; veri eksikliği durumları “anomali yok” olarak yazılamaz.

Bu sistemde uzun vadeli sessiz çürüme engellenir. Her reference\\\_dictionary coverage düşüşü, unmapped oranı artışı, data\\\_quality\\\_badge sürekli low kalması ve event\\\_stream\\\_health\\\_band bozulması rolling sağlık göstergesi olarak saklanır. Sistem çalışmaya devam eder; ancak bu durumlar sessizce geçiştirilemez ve yönetici alarm kayıtlarına yazılır. Bu alarm kayıtları karar üretmez, tahmin üretmez; yalnız sistem sağlığı kaydıdır.

Log ve denetim zorunludur. Her adım loglanır: hangi veri çekildi, hangi kütüphaneye yazıldı, hangi örüntü eşleşti, hangi anomali bayrağı yandı, hangi kayıt unmapped kaldı, hangi data\\\_quality\\\_badge uygulandı, hangi index üretimi başarılı/başarısız oldu, hangi event\\\_stream\\\_health\\\_band oluştu.

Bu promptta tanımlanan yapı tamamlanmış ve kilitlenmiş bir basketbol sistem mimarisidir. Kod yazarı bu metni yorumlamaz. Metinde olmayan hiçbir şeyi eklemez. Metinde olan hiçbir şeyi çıkarmaz. Metindeki sırayı bozmaz. Metindeki isimlendirmeleri değiştirmez. Branş dışı etiket üretmez. Veri yoksa uydurmaz. Bu modül ana omurganın basketbol dalıdır ve ondan bağımsız sistem olarak ele alınamaz.

FAZ-36
BASKETBOL ANALİZ EĞİTİM KATALOĞU (SORU KATALOĞU) — FUTBOL BENZERİ DİSİPLİN, SPORA ÖZEL
Bu katalog, basketbol branşında analistin neyi, hangi sırayla ve hangi kanıt penceresinde okuyacağını standardize eder. Bu sorular etiket değildir; soru katalogları değerlendirme çerçevesidir. Değer notu sorunun varlığına göre değil, sorunun kanıt zinciriyle doğrulanmış cevabına göre üretilir.

KONTEKST DUVARI VE ADRESLEME SORULARI
Bu maç hangi ülke, lig, sezon, sezon fazı ve organizasyon tipinde oynanıyor? Bu soru, yanlış raf adreslemesini engeller ve periyot davranışlarının sezon fazına göre değişip değişmediğini okumayı mümkün kılar.
Bu maç normal lig maçı mı, kupa benzeri eleme mi, yoksa play-off/klasman maçı mı? Bu soru, maçın “baskı bandını” sabitler. Aynı takım normal sezonda farklı, elemede farklı refleks gösterebilir.
Bu maçın saat dilimi ve timestamp standardı UTC ile hizalı mı? Bu soru, fiş, event ve odds akışını aynı zaman çizgisine oturtur. Zaman hizası bozuksa analiz bozulur.
Bu maçın veri türü fiş katmanı mı, event katmanı mı, yoksa ikisi birlikte mi? Bu soru, veri kalitesini ve yorum bandını kilitler. Event yoksa “tam analiz” yapılmış gibi davranılamaz.
Bu maç için data\\\_quality\\\_badge nedir ve “anomali yok” ile karışıyor mu? Bu soru, eksik veri ile normal bantı ayırır. Eksik veri varsa hüküm kurulmaz.

PERİYOT / SEGMENT OKUMA SORULARI
Bu takım maçın ilk periyotunda nasıl başlıyor ve bu başlangıç profili tekrar ediyor mu? Bu soru, erken tempo ve erken ritim kırılmalarını yakalar. Basketbolda ilk periyot refleksi güçlü DNA sinyalidir.
İkinci periyot geçişlerinde bench etkisi var mı ve skor dengesi kayıyor mu? Bu soru, rotasyon farkını ölçer. Basketbolda periyot değişimi çoğu zaman yedek katkısıyla belirlenir.
Üçüncü periyot dönüş refleksi nedir ve devre arası ayarlama etkisi görülüyor mu? Bu soru, koç etkisini ve yarı arası uyarlama gücünü ölçer. Üçüncü periyot DNA’sı kritik banddır.
Dördüncü periyot kapanış refleksi nedir ve clutch bandı stabil mi? Bu soru, maçın final karar anlarını ölçer. Kapanış DNA’sı tekrar ediyorsa değer notu motorunu besler.
Periyot bazında tempo değişimi var mı, yoksa tempo maç boyu sabit mi? Bu soru, pace swing’i yakalar. Tempo salınımı varsa turnover, faul ve run davranışları buna bağlanır.

RUN / SKOR KIRILMA SORULARI
Maçta run oluştu mu ve run’lar hangi periyotlarda kümelendi? Bu soru, momentum kırılma bantlarını çıkarır. Run’lar rastgele değilse takım karakteridir.
Run başladığında tetikleyici neydi (turnover, hızlı hücum, üçlük serisi, foul-trouble)? Bu soru, run motorunu anlamak içindir. Run tetikleyicisi sabitse takım DNA’sı belirgindir.
Run bitişi nasıl oluyor (timeout, savunma sertleşmesi, tempo düşüşü, serbest atış)? Bu soru, rakibin run kesme refleksini ölçer. Timeout kullanımı ve savunma adaptasyonu burada okunur.
Skor kopuşu hangi eşikte gerçekleşiyor ve tekrar eden bir eşik var mı? Bu soru, “kırılma barajını” çıkarır. Aynı takımın kopuş eşiği tekrar ediyorsa karar hızlanır.
Hakem çizgisi sertleştiğinde run sıklığı artıyor mu? Bu soru, faul bandının run üretimine etkisini ölçer. Faul bandı run’ı büyütebilir veya boğabilir.

FAUL / HAKEM / FOUL-TROUBLE SORULARI
İlk periyotta faul eşiği erken mi oluştu yoksa geç mi oluştu? Bu soru, maçın hakem bandını erken işaretler. Erken faul eşiği maçın bütün ritmini değiştirir.
Takım faul sayıları periyotlara nasıl dağılıyor ve kümelenme var mı? Bu soru, disiplin ve kontrol bandını ölçer. Kümelenme varsa kırılma noktası yakalanır.
Teknik faul veya unsportsmanlike faul geldi mi ve neyi tetikledi? Bu soru, psikolojik kırılma izini çıkarır. Teknik faul çoğu zaman momentum flip yaratır.  
Foul-trouble yaşayan kritik oyuncu var mı ve bu durum rotasyonu bozdu mu? Bu soru, kadro planının kırılıp kırılmadığını gösterir. Kritik oyuncu faul problemine girince maç DNA’sı değişir.
Hakem çizgisi maç içinde değişti mi (ilk yarı serbest, ikinci yarı sert)? Bu soru, “aynı oyun, farklı düdük” etkisini ölçer. Bu değişim tekrar ediyorsa lig/hakem profili çıkar.

SERBEST ATIŞ / FT SWING SORULARI
Serbest atış hacmi normal bantta mı yoksa sapma var mı? Bu soru, maçın serbest atış üzerinden mi yürüdüğünü ölçer. FT hacmi oyunun doğasını değiştirir.
Kritik anlarda serbest atış kaçırmaları skor kaderine etki etti mi? Bu soru, clutch hassasiyeti ölçer. FT swing, basketbolun en deterministik kırılma yeridir.
Son 2 dakikada bonus durumu oyunu yavaşlattı mı ve tempo bandı düştü mü? Bu soru, oyun akışının dur-kalk’a dönmesini ölçer. Bu dönüş clutch kararları etkiler.

TURNOVER / TOP KAYBI SORULARI
Turnover run ile eşleşiyor mu? Bu soru, top kaybının direkt skor kırılmasına dönüşüp dönüşmediğini ölçer.
Top kaybı periyot bazında artıyor mu yoksa maç boyunca dengeli mi? Bu soru, yorgunluk ve baskı altında karar kalitesini ölçer.
Arka arkaya turnover zinciri var mı ve momentum flip yarattı mı? Bu soru, “geri dönüş” veya “kopuş” anlarını çıkarır.
Tempo spike dönemlerinde turnover artıyor mu? Bu soru, hızlı oyunun maliyetini ölçer. Takım hızlı oynarken hata yapıyorsa karakter bandı oluşur.

PICK-AND-ROLL / SET OYUN / HÜCUM KARARLARI (KANIT BANDI)
Takım set hücumda mı daha stabil, yoksa transition’da mı? Bu soru, takımın hangi oyun tipinde daha güvenli olduğunu belirler.
Kritik anlarda aynı hücum setine tekrar tekrar dönüyor mu? Bu soru, koçun ve oyuncunun “güvenli şablonunu” ölçer.
Rakip savunma adaptasyonundan sonra takım planı çözüldü mü? Bu soru, ayarlama savaşını ölçer. Plan çözülüyorsa ikinci yarı DNA’sı zayıf kabul edilir.

SAVUNMA / RİM KORUMA / ÜÇLÜK SAVUNMA (ÖLÇÜM DİLİ)
Takımın savunma sertliği periyot bazında dalgalanıyor mu? Bu soru, savunma stabilitesini ölçer. Stabil değilse run’lara kapı açılır.
Üçlük serilerine izin veriliyor mu ve bu seri aynı oyunculardan mı geliyor? Bu soru, savunma zaafı haritası çıkarır.
Rim koruma zayıflığı veya faul problemine dönüşen bir iç savunma kırılması var mı? Bu soru, boyalı alanın çöktüğü senaryoyu yakalar.

KRİTİK OYUNCU / YILDIZ BAĞIMLILIĞI / BENCH FARKI
Takımın skor üretimi bir-iki oyuncuya mı bağımlı yoksa dağılıyor mu? Bu soru, yıldız bağımlılığını ölçer. Bağımlılık varsa kritik oyuncu kartı ana anahtardır.
Kritik oyuncu kenardayken takımın net tempo ve skor bandı düşüyor mu? Bu soru, “on/off etkisini” ölçer. Bench ile kapanmıyorsa bağımlılık serttir.
Bench katkısı run başlatıyor mu yoksa yalnız kapatma mı yapıyor? Bu soru, bench’in rolünü belirler. Bazı takımlar bench ile maçı kazanır, bazıları bench ile maçı kaybetmez.
Kritik oyuncu faul problemine girince koç paniğe mi gidiyor yoksa yönetebiliyor mu? Bu soru, koçun kriz yönetimini ölçer.

TIMEOUT / CHALLENGE / OYUN DURMASI
Timeout kullanımı run kesiyor mu yoksa geç mi kalıyor? Bu soru, koçun müdahale zamanlamasını ölçer. Geç timeout tekrar ediyorsa DNA’dır.
Challenge/itiraz zinciri oyunu dur-kalk ritmine sokuyor mu? Bu soru, late-game disruption bandını ölçer. Dur-kalk ritmi, tempo ve mental kırılma üretir.
Son 2 dakikada mola trafiği aşırı mı ve oyun akışı parçalanıyor mu? Bu soru, kapanışın “basketbol değil hakem/serbest atış maçına” dönüp dönmediğini ölçer.

CLUTCH BANDI (SON 5 DAKİKA)
Son 5 dakikada takımın hücum kararı stabil mi yoksa panik mi? Bu soru, clutch DNA’sını ölçer. Panik tekrar ediyorsa düşük güven bandı oluşur.
Son 5 dakikada top kaybı artıyor mu? Bu soru, baskı altında karar kalitesini ölçer.
Son 5 dakikada faul ve teknik faul artışı var mı? Bu soru, mental stabiliteyi ölçer. Artış varsa disiplin kırılması kartlaşır.
Son 5 dakikada serbest atış çizgisi kader belirliyor mu? Bu soru, FT swing’in clutch’a etkisini ölçer.

VERİ UYUŞMAZLIĞI / DOĞRULAMA (SESSİZ BOZULMA KİLİDİ)
 İzleyici raporları ile event akışı çelişiyor mu? Bu soru, yedek/doğrulama rolünün tetikleme sebebidir. Çelişki varsa data\\\_quality düşürülür.
Fiş verisi ile play-by-play temel olay türleri uyuşuyor mu? Bu soru, veri sağlayıcı hatasını yakalar. Uyuşmazlık varsa hüküm yoktur.
Event akışı eksikse hangi periyotlar boş kaldı? Bu soru, analiz bandını sınırlar. Eksik periyot varsa “tam okuma” yapılamaz.

BASKETBOL ETİKET KATALOĞU (KÜTÜPHANE SÖZLÜĞÜ) — ÇEKİRDEK + PERİYOT + RUN + FAUL + CLUTCH
Bu katalog dışı etiket üretilemez. Etiketler serbest metin değildir; sabit ad ve sabit değer bantlarıyla çalışır.

KONTEKST / DUVAR ETİKETLERİ (ZORUNLU)
timestamp\\\_utc,country\\\_ref,league\\\_ref,season\\\_id,season\\\_phase,competition\\\_type,cup\\\_flag,team\\\_ref,context\\\_scope,context\\\_window\\\_type
season\\\_phase yalnız şu değerleri alır: pre\\\_season, season\\\_start, season\\\_mid, season\\\_end, off\\\_season,competition\\\_type yalnız şu değerleri alır: league, cup, continental, national\\\_team
cup\\\_flag yalnız şu değerleri alır: true, false,context\\\_scope yalnız şu değerleri alır: team, match, league
context\\\_window\\\_type yalnız şu değerleri alır: pre\\\_match\\\_window, in\\\_match\\\_window, post\\\_match\\\_window, off\\\_season\\\_weekly

MAÇ ADRESİ (ZORUNLU)
match\\\_ref,kickoff\\\_time\\\_utc,home\\\_team\\\_ref,away\\\_team\\\_ref,venue\\\_type,is\\\_home\\\_team\\\_context,referee\\\_ref,data\\\_layer\\\_status,venue\\\_type yalnız şu değerleri alır: home, away, neutral,is\\\_home\\\_team\\\_context yalnız şu değerleri alır: true, false,data\\\_layer\\\_status yalnız şu değerleri alır: slip\\\_only, events\\\_only, slip\\\_plus\\\_events

PERİYOT SEGMENT ETİKETLERİ (ZORUNLU)
period\\\_1\\\_band,period\\\_2\\\_band,period\\\_3\\\_band,period\\\_4\\\_band,overtime\\\_band
Her periyot alanı yalnız şu değerleri alır: normal\\\_band, tempo\\\_up, tempo\\\_down, run\\\_against, run\\\_for, control\\\_lost, control\\\_gained, foul\\\_spike, turnover\\\_spike

TEMPO / RİTİM (ZORUNLU)
pace\\\_band\\\_overall,pace\\\_profile\\\_shape,rhythm\\\_disruption\\\_band,pace\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high,pace\\\_profile\\\_shape yalnız şu değerleri alır: flat, rising, falling, volatile,rhythm\\\_disruption\\\_band yalnız şu değerleri alır: none, minor, major

RUN / MOMENTUM (ZORUNLU)
run\\\_presence,run\\\_major\\\_count\\\_band,run\\\_trigger\\\_primary,run\\\_stop\\\_method\\\_primary,run\\\_presence yalnız şu değerleri alır: none, present,run\\\_major\\\_count\\\_band yalnız şu değerleri alır: none, 1, 2, 3\\\_plus,run\\\_trigger\\\_primary yalnız şu değerleri alır: none, turnover\\\_run, three\\\_point\\\_run, fastbreak\\\_run, foul\\\_trouble\\\_run, defensive\\\_stop\\\_run,run\\\_stop\\\_method\\\_primary yalnız şu değerleri alır: none, timeout, defensive\\\_adjustment, free\\\_throws, pace\\\_drop

FAUL / HAKEM (ZORUNLU)
foul\\\_threshold\\\_early\\\_flag,foul\\\_band\\\_overall,technical\\\_foul\\\_flag,unsportsmanlike\\\_flag,foul\\\_trouble\\\_flag,foul\\\_threshold\\\_early\\\_flag yalnız şu değerleri alır: none, present,foul\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high,technical\\\_foul\\\_flag yalnız şu değerleri alır: none, present,unsportsmanlike\\\_flag yalnız şu değerleri alır: none, present,foul\\\_trouble\\\_flag yalnız şu değerleri alır: none, present

SERBEST ATIŞ / FT SWING (ZORUNLU)
ft\\\_volume\\\_band,ft\\\_swing\\\_flag,bonus\\\_late\\\_game\\\_flag,ft\\\_volume\\\_band yalnız şu değerleri alır: low, medium, high,ft\\\_swing\\\_flag yalnız şu değerleri alır: none, present,bonus\\\_late\\\_game\\\_flag yalnız şu değerleri alır: none, present

TURNOVER (ZORUNLU)
turnover\\\_band\\\_overall,turnover\\\_cluster\\\_period,turnover\\\_run\\\_link\\\_flag,turnover\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high,turnover\\\_cluster\\\_period yalnız şu değerleri alır: none, period\\\_1, period\\\_2, period\\\_3, period\\\_4, overtime,turnover\\\_run\\\_link\\\_flag yalnız şu değerleri alır: none, present

CLUTCH / SON 5 DAKİKA (ZORUNLU)
clutch\\\_band,late\\\_game\\\_disruption\\\_flag,late\\\_game\\\_panic\\\_flag,clutch\\\_band yalnız şu değerleri alır: stable, unstable,late\\\_game\\\_disruption\\\_flag yalnız şu değerleri alır: none, present,late\\\_game\\\_panic\\\_flag yalnız şu değerleri alır: none, present

BENCH / YILDIZ BAĞIMLILIĞI (ZORUNLU)
star\\\_dependency\\\_band,bench\\\_impact\\\_band,critical\\\_player\\\_foul\\\_trouble\\\_flag,star\\\_dependency\\\_band yalnız şu değerleri alır: low, medium, high,bench\\\_impact\\\_band yalnız şu değerleri alır: low, medium, high,critical\\\_player\\\_foul\\\_trouble\\\_flag yalnız şu değerleri alır: none, present

DATA QUALITY (ZORUNLU)
data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive


FAZ-31
DOSYA-1: BASKETBALL\\\_MODULE\\\_IMPLEMENTATION\\\_PROMPT\\\_FINAL.txt\

BASKETBOL MODÜLÜ — 5 YIL DAYANIKLILIK REVİZESİ + 3 PROBLEM DÜZELTİLMİŞ NİHAİ UYGULAMA PROMPTU\*\*
Aşağıdaki metin yoruma kapalı, bağlayıcı ve birebir uygulanması zorunlu “uygulama promptu”dur. Bu metinde yazan her adım, her sıra, her rol, her yapı, her isimlendirme ve her kural değiştirilemez. Kod yazarı “daha iyisi olur”, “şöyle yapalım”, “şunu çıkaralım”, “bunu ekleyelim” gibi hiçbir yorum, öneri ve alternatif üretmez. Metinde olmayan hiçbir özellik eklenmez. Metinde olan hiçbir özellik çıkarılmaz. Yalnızca teknik olarak imkânsızlık varsa sadece “şu madde teknik olarak uygulanamıyor” cümlesiyle bildirir ve uygulama durdurulur. Çözüm önerisi getirilmez, soru sorulmaz, fikir üretilmez. Bu prompt bir taslak değildir. Tamamlanmış ve kilitlenmiş sistem mimarisidir. Bu proje “bahis sitesi” kurmaz. Bu proje “bahse yönlendirme” yapmaz. Bu proje kupon oluşturmaz. Bu proje ödeme almaz. Bu proje yalnız istatistiksel ölçüm, zaman hizası ve bant sapması üretir. “Kesin kazanır, banko, tek” gibi dil yasaktır.\*\*

Sistemin adı:
Spor Anomali \\\& Örüntü Motoru (n8n tabanlı). Bu modül basketbol içindir ve ana omurgadan ayrı değildir; aynı sistemin basketbol dalıdır. Sistemin amacı: basketbol için haber + piyasa/oran + maç içi olay verilerini tek hiyerarşide toplamak, örüntü üretmek ve olağan akışa aykırı sapmaları “anomali” olarak işaretlemektir. Sistem çıktıları tahmin değildir; yalnız kütüphanelere işlenmiş ham veri, kütüphanelere işlenmiş etiketli veri, örüntü kütüphanesine yazılmış örüntü haritaları, anomali skoru + geçmiş etki oranı ve yönetici alarm kayıtlarıdır. Bu modülde sosyal medya dağıtımı yoktur. Telegram/Instagram/TikTok/YouTube Shorts yoktur. Çıktılar yalnız kütüphane dosyalarına ve index dosyalarına yazılır.

Bu projede veri deposu teknolojisi zorunlu mimari kuraldır. Veri deposu teknoloji olarak JSON dosya tabanlı kütüphane deposudur. Kullanılacak formatlar JSON (kalıcı dosyalar) ve JSONL (büyük zaman serileri ve event/log akışları) olacaktır. Kod yazarı SQL / NoSQL / Postgres / MongoDB / Redis kullanmaz. Kod yazarı yalnız dosya sistemi üzerinde JSON/JSONL üretir, okur ve günceller. Tüm dosyalar n8n proje dizininde ./library/ altında tutulur. Absolute path kullanılmaz. Sadece relative path kullanılır. JSON dosyalarının sınırsız büyümesine izin verilmez. Ham veri dosyaları günlük dosyalara yazılır ve dosya adı YYYY-MM-DD.json formatındadır. Eski ham veri dosyaları ./library/archive altına taşınır. Index dosyaları her çalıştırma sonunda tekrar üretilir ve güncel özet tutulur; tüm tarihçe tek dosyada biriktirilmez.her dosya spor branşının kendi adıyla balaşar.

Ana kural: 

tüm kütüphaneler aynı hiyerarşiyi kullanır ve bu sıra hiçbir yerde bozulmaz. Sıra her zaman şu şekildedir: spor türü → ülke → lig → takım → sezon → dönem → maç → zaman bağlamı. Dönem tanımı zorunludur ve her kütüphanede aynıdır. Her sezon üç döneme ayrılır: sezon başı, sezon ortası, sezon sonu. Sezon ortası zamansal sabiti devre arası son 3 hafta + ikinci devre başı ilk 3 haftadır ve “sezon ortası kritik pencere” etiketi olarak ortak uygulanır.

Sistem evreleri iki evredir ve net olarak ayrılacaktır. Evre-1 bootstrap (faaliyet öncesi) amacı geçmiş veriyi çekmek, kütüphanelere yerleştirmek, etiketlemek, örüntü haritalarını üretmek ve kalibrasyonu sabitlemektir. Evre-2 live (faaliyet sonrası) amacı yeni maçları aynı sistemle işlemek, kütüphaneyi büyütmek, örüntü duvarını güncellemek ve anomali çıktıları üretmektir. Bootstrap kapsamı sabit kuraldır: sistem zorunlu olarak son 3 tamamlanmış sezonu indirir ve basketbol kütüphanelerine işler. API daha fazla sezon destekliyorsa sistem daha fazlasını çekebilecek şekilde tasarlanır; ancak zorunlu minimum son 3 tamamlanmış sezondur.

Veri giriş katmanı bu sistemde üç ana veri kaynağı kullanır: haber verisi kaynağı (newsapi.org), piyasa/oran verisi kaynağı (oddsapi.io), canlı maç olay verisi kaynağı (basketbol live scores + match events destekleyen ayrı bir API). Live event kaynağı newsapi ve oddsapi ile sağlanmaz, mutlaka ayrı kaynaktır. Bu kaynaklara erişim için gereken tüm gizli bilgiler (api key, token, webhook url, kanal id) otomasyon kurulumunda manuel olarak girilir. Kod yazarı bu bilgileri talep etmez, beklemez, içerik üretmez; sadece bu gizli bilgilerin girileceği alanları hazırlar.

Zorunlu manuel konfigürasyon dosyası 

./library/config.json olacaktır ve şu alanları zorunlu taşır: 
newsapi\\\_key, oddsapi\\\_key, live\\\_event\\\_api\\\_key, live\\\_event\\\_provider\\\_name, live\\\_event\\\_endpoint\\\_base, odds\\\_snapshot\\\_interval\\\_minutes, odds\\\_required\\\_markets, listed\\\_sports, basketbol\\\_league\\\_allowlist, cup\\\_allowlist, reference\\\_dictionary\\\_source, mode (public\\\_only / vip\\\_enabled). Kod yazarı bu dosyayı uydurma değerlerle doldurmaz, sadece alanları açar. Bu dosya boşsa sistem pasif modda çalışır ve kırılmaz.

Kimlik / registry standardı zorunludur. 

API’lerde takım isimleri, lig isimleri ve maç id’leri farklı gelebilir. Bu problem nedeniyle ./library/index.json içinde reference\\\_dictionary bloğu zorunlu olarak bulunur ve tüm etiketleme sadece bu sözlükten yapılır. Eşleşemeyen haberler ve eşleşemeyen kayıtlar unmapped durumuyla ayrı raf’a yazılır. Yakın eşleştirmeyle zorla atama yapılmaz. Sistem maçları “sistem match\\\_id” ile sabitler ve tüm modüller sadece bu match\\\_id üzerinden bağlanır. reference\\\_dictionary kapsama oranı sistem sağlığı göstergesidir; kapsama düşüşü ayrı alarm kaydı olarak saklanır.

Bu basketbol modülü içinde toplam kütüphane seti sabittir ve branşlar karıştırılamaz. Basketbol kapsamındaki mantıksal raflar şunlardır: basketbol kütüphanesi, haber kütüphanesi, oran/piyasa kütüphanesi, örüntü kütüphanesi, kupa kütüphanesi. Bu modülde soru üreten motor yoktur; runtime sözleşmesine dahil edilmez ve çalışma sırasında soru motoru çalıştırılmaz. Bu modülde sayısal soru adedi hedefi bulunmaz; kapsama prensip ile kilitlenir. Bu modülde branş dışı etiket üretimi yoktur; ganyan dili basketbola taşınamaz.

Haber kütüphanesi ham sinyalin kaynağıdır. Haber kütüphanesinde yorum yoktur. Haberler sadece raf düzeniyle saklanır. Haber rafı şu sırayı taşır: spor → ülke → lig → takım → sezon → dönem → zaman bağlamı → haber kaynağı → haber türü → haber tonu → haber metni. Haber tonu zorunludur ve pozitif / nötr / negatif olarak tutulur. Zaman bağlamı zorunludur: maç öncesi, maç günü/maç anı, maç sonrası, maçtan sonraki günler. Haber türü zorunludur: ajans / köşe / röportaj / yorum / sızıntı. Gazeteci/yazar varsa saklanır. 

Oran/piyasa kütüphanesi kolektif beklenti kaydıdır ve tahmin değildir. Bookmaker seti sabittir: bet365, pinnacle, william hill, betfair, unibet, bwin, 888sport. Oran/piyasa kütüphanesinde maç bazlı oranlar şu raf sırasıyla dizilir: spor → ülke → lig → takım → sezon → dönem → maç → timestamp → bookmaker → market → line → odds\\\_set. Odds zaman serisi snapshot standardı zorunludur. Snapshot aralığı odds\\\_snapshot\\\_interval\\\_minutes ile belirlenir ve boş bırakılamaz. odds\\\_required\\\_markets boş bırakılamaz ve en az 1 market içermelidir. Snapshot sayısı iki adetten azsa oran sapması hesabı yapılmaz ve sapma skoru “hesaplanamadı/veri yetersiz” bandında kalır; “anomali yok” yazılamaz.

Basketbol maç/saha kütüphanesi maç içi olayları kaydeder. Basketbol maç rafı şu ana olayları taşır: periyot skorları, faul sayıları, teknik faul, diskalifiye, top kaybı kümeleri, seri koşular (run), molalar (timeout), momentum kırılımları, son periyot kırılma noktaları. Basketbol hakem rafı faul standardı, düdük yoğunluğu, bonus giriş zamanlaması, teknik faul eğilimi ve maç sonu düdük profili gibi ölçümler taşır; yorum ve suçlama dili taşımaz.

Örüntü kütüphanesi üç ana girdiyi birleştirir: 

basın/haber örüntüsü, oran/piyasa örüntüsü, maç içi olay örüntüsü. Örüntü çıktıları örüntü kodu, tekrar sayısı, geçmiş etki oranı ve anomali skorunu taşır. Bu kütüphane iki raf taşır: ana örüntü rafı ve bayraklı/anomali örüntü rafı. Bu raf “şike” olarak adlandırılamaz; yalnız “olağan dışı sapma” olarak adlandırılır.

Örüntü üretimi iki aşamalı çalışır ve sıra değiştirilemez. Aşama-1 sadece veri toplar, ayrıştırır, hiyerarşiye yerleştirir ve index dosyalarını üretir. Aşama-2 sadece geriye dönük tarama ile örüntüleri çıkarır, normal davranış referanslarını üretir ve anomaly\\\_score kalibrasyonunu hesaplar. Aşama-2 kalibrasyonu son 3 sezon bootstrap verisi üzerinden yapılır. Kod yazarı elle formül uydurmaz ve puanlama tahmin etmez. Anomali skor formülü sabittir: anomaly\\\_score = (basın tonu sapması puanı) + (oran sapması puanı) + (maç içi kritik olay puanı). Bu üç puanın 0–100 normalizasyonu ve ağırlıklandırılması Aşama-2 tarafından üretilir ve sabitlenir. Aşama-2 tamamlanmadan anomalies çıktısı boş veya “henüz hesaplanmadı” durumunda kalabilir ve bu hata değildir.

Canlı maç olayları veri gerçekliği şu şekildedir: bu sistemde insan canlı izleyici kadrosu yoktur. Canlı maç olayları API üzerinden gelen canlı event verileriyle beslenir. Canlı event aktif değilse maç içi kritik olay puanı 0 olarak kalır ve sistem kırılmaz. Canlı event feed aktif olduğunda event kayıtları match\\\_id, sport\\\_type, event\\\_type, event\\\_minute, team\\\_ref, timestamp alanlarıyla JSONL olarak yazılır. Event akışında olağan dışı yoğunluk veya olağan dışı sessizlik ayrı bir teknik durumdur ve event\\\_stream\\\_health\\\_band altında saklanır; bu bant maç verisinden bağımsızdır ve sessizce yok sayılmaz.

Zorunlu index dosyaların tümü her spor branşı adıyla başlar,örnek,football\\\_anomaly.json,football\\\_library.json,football\\\_public.json

basket\\\_anomaly.json,basket\\\_library.json,ganyan\\\_anomaly.json

ganyan\\\_library.json

Zorunlu index dosyaları her çalıştırmada üretilir: ./library/index.json, ./library/summary.json, ./library/today\\\_matches.json, ./library/anomalies\\\_public.json, ./library/anomalies\\\_vip.json. Bu dosyalar boş olabilir ancak dosyanın kendisi üretilmek zorundadır. Index üretimi atomik çalışır; yeni index doğrulama kontrollerinden geçmeden mevcut index üzerine yazılmaz. Hatalı üretimde önceki index korunur ve yönetici alarmına yazılır. “Anomali yok” ifadesi yalnız sapma skoru hesaplanmış ve eşik altında kalmış durumda kullanılabilir; veri eksikliği durumları “anomali yok” olarak yazılamaz.

Bu sistemde uzun vadeli sessiz çürüme engellenir. Her reference\\\_dictionary coverage düşüşü, unmapped oranı artışı, data\\\_quality\\\_badge sürekli low kalması ve event\\\_stream\\\_health\\\_band bozulması rolling sağlık göstergesi olarak saklanır. Sistem çalışmaya devam eder; ancak bu durumlar sessizce geçiştirilemez ve yönetici alarm kayıtlarına yazılır. Bu alarm kayıtları karar üretmez, tahmin üretmez; yalnız sistem sağlığı kaydıdır.

Log ve denetim zorunludur. Her adım loglanır: hangi veri çekildi, hangi kütüphaneye yazıldı, hangi örüntü eşleşti, hangi anomali bayrağı yandı, hangi kayıt unmapped kaldı, hangi data\\\_quality\\\_badge uygulandı, hangi index üretimi başarılı/başarısız oldu, hangi event\\\_stream\\\_health\\\_band oluştu.

Bu promptta tanımlanan yapı tamamlanmış ve kilitlenmiş bir basketbol sistem mimarisidir. Kod yazarı bu metni yorumlamaz. Metinde olmayan hiçbir şeyi eklemez. Metinde olan hiçbir şeyi çıkarmaz. Metindeki sırayı bozmaz. Metindeki isimlendirmeleri değiştirmez. Branş dışı etiket üretmez. Veri yoksa uydurmaz. Bu modül ana omurganın basketbol dalıdır ve ondan bağımsız sistem olarak ele alınamaz.


FAZ-36
BASKETBOL ANALİZ EĞİTİM KATALOĞU (SORU KATALOĞU) — FUTBOL BENZERİ DİSİPLİN, SPORA ÖZEL
Bu katalog, basketbol branşında analistin neyi, hangi sırayla ve hangi kanıt penceresinde okuyacağını standardize eder. Bu sorular etiket değildir; soru katalogları değerlendirme çerçevesidir. Değer notu sorunun varlığına göre değil, sorunun kanıt zinciriyle doğrulanmış cevabına göre üretilir.

KONTEKST DUVARI VE ADRESLEME SORULARI
Bu maç hangi ülke, lig, sezon, sezon fazı ve organizasyon tipinde oynanıyor? Bu soru, yanlış raf adreslemesini engeller ve periyot davranışlarının sezon fazına göre değişip değişmediğini okumayı mümkün kılar.
Bu maç normal lig maçı mı, kupa benzeri eleme mi, yoksa play-off/klasman maçı mı? Bu soru, maçın “baskı bandını” sabitler. Aynı takım normal sezonda farklı, elemede farklı refleks gösterebilir.
Bu maçın saat dilimi ve timestamp standardı UTC ile hizalı mı? Bu soru, fiş, event ve odds akışını aynı zaman çizgisine oturtur. Zaman hizası bozuksa analiz bozulur.
Bu maçın veri türü fiş katmanı mı, event katmanı mı, yoksa ikisi birlikte mi? Bu soru, veri kalitesini ve yorum bandını kilitler. Event yoksa “tam analiz” yapılmış gibi davranılamaz.
Bu maç için data\\\_quality\\\_badge nedir ve “anomali yok” ile karışıyor mu? Bu soru, eksik veri ile normal bantı ayırır. Eksik veri varsa hüküm kurulmaz.

PERİYOT / SEGMENT OKUMA SORULARI
Bu takım maçın ilk periyotunda nasıl başlıyor ve bu başlangıç profili tekrar ediyor mu? Bu soru, erken tempo ve erken ritim kırılmalarını yakalar. Basketbolda ilk periyot refleksi güçlü DNA sinyalidir.
İkinci periyot geçişlerinde bench etkisi var mı ve skor dengesi kayıyor mu? Bu soru, rotasyon farkını ölçer. Basketbolda periyot değişimi çoğu zaman yedek katkısıyla belirlenir.
Üçüncü periyot dönüş refleksi nedir ve devre arası ayarlama etkisi görülüyor mu? Bu soru, koç etkisini ve yarı arası uyarlama gücünü ölçer. Üçüncü periyot DNA’sı kritik banddır.
Dördüncü periyot kapanış refleksi nedir ve clutch bandı stabil mi? Bu soru, maçın final karar anlarını ölçer. Kapanış DNA’sı tekrar ediyorsa değer notu motorunu besler.
Periyot bazında tempo değişimi var mı, yoksa tempo maç boyu sabit mi? Bu soru, pace swing’i yakalar. Tempo salınımı varsa turnover, faul ve run davranışları buna bağlanır.

RUN / SKOR KIRILMA SORULARI
Maçta run oluştu mu ve run’lar hangi periyotlarda kümelendi? Bu soru, momentum kırılma bantlarını çıkarır. Run’lar rastgele değilse takım karakteridir.
Run başladığında tetikleyici neydi (turnover, hızlı hücum, üçlük serisi, foul-trouble)? Bu soru, run motorunu anlamak içindir. Run tetikleyicisi sabitse takım DNA’sı belirgindir.
Run bitişi nasıl oluyor (timeout, savunma sertleşmesi, tempo düşüşü, serbest atış)? Bu soru, rakibin run kesme refleksini ölçer. Timeout kullanımı ve savunma adaptasyonu burada okunur.
Skor kopuşu hangi eşikte gerçekleşiyor ve tekrar eden bir eşik var mı? Bu soru, “kırılma barajını” çıkarır. Aynı takımın kopuş eşiği tekrar ediyorsa karar hızlanır.
Hakem çizgisi sertleştiğinde run sıklığı artıyor mu? Bu soru, faul bandının run üretimine etkisini ölçer. Faul bandı run’ı büyütebilir veya boğabilir.

FAUL / HAKEM / FOUL-TROUBLE SORULARI
İlk periyotta faul eşiği erken mi oluştu yoksa geç mi oluştu? Bu soru, maçın hakem bandını erken işaretler. Erken faul eşiği maçın bütün ritmini değiştirir.
Takım faul sayıları periyotlara nasıl dağılıyor ve kümelenme var mı? Bu soru, disiplin ve kontrol bandını ölçer. Kümelenme varsa kırılma noktası yakalanır.
Teknik faul veya unsportsmanlike faul geldi mi ve neyi tetikledi? Bu soru, psikolojik kırılma izini çıkarır. Teknik faul çoğu zaman momentum flip yaratır.  
Foul-trouble yaşayan kritik oyuncu var mı ve bu durum rotasyonu bozdu mu? Bu soru, kadro planının kırılıp kırılmadığını gösterir. Kritik oyuncu faul problemine girince maç DNA’sı değişir.
Hakem çizgisi maç içinde değişti mi (ilk yarı serbest, ikinci yarı sert)? Bu soru, “aynı oyun, farklı düdük” etkisini ölçer. Bu değişim tekrar ediyorsa lig/hakem profili çıkar.

SERBEST ATIŞ / FT SWING SORULARI
Serbest atış hacmi normal bantta mı yoksa sapma var mı? Bu soru, maçın serbest atış üzerinden mi yürüdüğünü ölçer. FT hacmi oyunun doğasını değiştirir.
Kritik anlarda serbest atış kaçırmaları skor kaderine etki etti mi? Bu soru, clutch hassasiyeti ölçer. FT swing, basketbolun en deterministik kırılma yeridir.
Son 2 dakikada bonus durumu oyunu yavaşlattı mı ve tempo bandı düştü mü? Bu soru, oyun akışının dur-kalk’a dönmesini ölçer. Bu dönüş clutch kararları etkiler.

TURNOVER / TOP KAYBI SORULARI
Turnover run ile eşleşiyor mu? Bu soru, top kaybının direkt skor kırılmasına dönüşüp dönüşmediğini ölçer.
Top kaybı periyot bazında artıyor mu yoksa maç boyunca dengeli mi? Bu soru, yorgunluk ve baskı altında karar kalitesini ölçer.
Arka arkaya turnover zinciri var mı ve momentum flip yarattı mı? Bu soru, “geri dönüş” veya “kopuş” anlarını çıkarır.
Tempo spike dönemlerinde turnover artıyor mu? Bu soru, hızlı oyunun maliyetini ölçer. Takım hızlı oynarken hata yapıyorsa karakter bandı oluşur.

PICK-AND-ROLL / SET OYUN / HÜCUM KARARLARI (KANIT BANDI)
Takım set hücumda mı daha stabil, yoksa transition’da mı? Bu soru, takımın hangi oyun tipinde daha güvenli olduğunu belirler.
Kritik anlarda aynı hücum setine tekrar tekrar dönüyor mu? Bu soru, koçun ve oyuncunun “güvenli şablonunu” ölçer.
Rakip savunma adaptasyonundan sonra takım planı çözüldü mü? Bu soru, ayarlama savaşını ölçer. Plan çözülüyorsa ikinci yarı DNA’sı zayıf kabul edilir.

SAVUNMA / RİM KORUMA / ÜÇLÜK SAVUNMA (ÖLÇÜM DİLİ)
Takımın savunma sertliği periyot bazında dalgalanıyor mu? Bu soru, savunma stabilitesini ölçer. Stabil değilse run’lara kapı açılır.
Üçlük serilerine izin veriliyor mu ve bu seri aynı oyunculardan mı geliyor? Bu soru, savunma zaafı haritası çıkarır.
Rim koruma zayıflığı veya faul problemine dönüşen bir iç savunma kırılması var mı? Bu soru, boyalı alanın çöktüğü senaryoyu yakalar.

KRİTİK OYUNCU / YILDIZ BAĞIMLILIĞI / BENCH FARKI
Takımın skor üretimi bir-iki oyuncuya mı bağımlı yoksa dağılıyor mu? Bu soru, yıldız bağımlılığını ölçer. Bağımlılık varsa kritik oyuncu kartı ana anahtardır.
Kritik oyuncu kenardayken takımın net tempo ve skor bandı düşüyor mu? Bu soru, “on/off etkisini” ölçer. Bench ile kapanmıyorsa bağımlılık serttir.
Bench katkısı run başlatıyor mu yoksa yalnız kapatma mı yapıyor? Bu soru, bench’in rolünü belirler. Bazı takımlar bench ile maçı kazanır, bazıları bench ile maçı kaybetmez.
Kritik oyuncu faul problemine girince koç paniğe mi gidiyor yoksa yönetebiliyor mu? Bu soru, koçun kriz yönetimini ölçer.

TIMEOUT / CHALLENGE / OYUN DURMASI
Timeout kullanımı run kesiyor mu yoksa geç mi kalıyor? Bu soru, koçun müdahale zamanlamasını ölçer. Geç timeout tekrar ediyorsa DNA’dır.
Challenge/itiraz zinciri oyunu dur-kalk ritmine sokuyor mu? Bu soru, late-game disruption bandını ölçer. Dur-kalk ritmi, tempo ve mental kırılma üretir.
Son 2 dakikada mola trafiği aşırı mı ve oyun akışı parçalanıyor mu? Bu soru, kapanışın “basketbol değil hakem/serbest atış maçına” dönüp dönmediğini ölçer.

CLUTCH BANDI (SON 5 DAKİKA)
Son 5 dakikada takımın hücum kararı stabil mi yoksa panik mi? Bu soru, clutch DNA’sını ölçer. Panik tekrar ediyorsa düşük güven bandı oluşur.
Son 5 dakikada top kaybı artıyor mu? Bu soru, baskı altında karar kalitesini ölçer.
Son 5 dakikada faul ve teknik faul artışı var mı? Bu soru, mental stabiliteyi ölçer. Artış varsa disiplin kırılması kartlaşır.
Son 5 dakikada serbest atış çizgisi kader belirliyor mu? Bu soru, FT swing’in clutch’a etkisini ölçer.

VERİ UYUŞMAZLIĞI / DOĞRULAMA (SESSİZ BOZULMA KİLİDİ)
 İzleyici raporları ile event akışı çelişiyor mu? Bu soru, yedek/doğrulama rolünün tetikleme sebebidir. Çelişki varsa data\\\_quality düşürülür.
Fiş verisi ile play-by-play temel olay türleri uyuşuyor mu? Bu soru, veri sağlayıcı hatasını yakalar. Uyuşmazlık varsa hüküm yoktur.
Event akışı eksikse hangi periyotlar boş kaldı? Bu soru, analiz bandını sınırlar. Eksik periyot varsa “tam okuma” yapılamaz.

BASKETBOL ETİKET KATALOĞU (KÜTÜPHANE SÖZLÜĞÜ) — ÇEKİRDEK + PERİYOT + RUN + FAUL + CLUTCH
Bu katalog dışı etiket üretilemez. Etiketler serbest metin değildir; sabit ad ve sabit değer bantlarıyla çalışır.

KONTEKST / DUVAR ETİKETLERİ (ZORUNLU)
timestamp\\\_utc,country\\\_ref,league\\\_ref,season\\\_id,season\\\_phase,competition\\\_type,cup\\\_flag,team\\\_ref,context\\\_scope,context\\\_window\\\_type
season\\\_phase yalnız şu değerleri alır: pre\\\_season, season\\\_start, season\\\_mid, season\\\_end, off\\\_season,competition\\\_type yalnız şu değerleri alır: league, cup, continental, national\\\_team
cup\\\_flag yalnız şu değerleri alır: true, false,context\\\_scope yalnız şu değerleri alır: team, match, league
context\\\_window\\\_type yalnız şu değerleri alır: pre\\\_match\\\_window, in\\\_match\\\_window, post\\\_match\\\_window, off\\\_season\\\_weekly

MAÇ ADRESİ (ZORUNLU)
match\\\_ref,kickoff\\\_time\\\_utc,home\\\_team\\\_ref,away\\\_team\\\_ref,venue\\\_type,is\\\_home\\\_team\\\_context,referee\\\_ref,data\\\_layer\\\_status,venue\\\_type yalnız şu değerleri alır: home, away, neutral,is\\\_home\\\_team\\\_context yalnız şu değerleri alır: true, false,data\\\_layer\\\_status yalnız şu değerleri alır: slip\\\_only, events\\\_only, slip\\\_plus\\\_events

PERİYOT SEGMENT ETİKETLERİ (ZORUNLU)
period\\\_1\\\_band,period\\\_2\\\_band,period\\\_3\\\_band,period\\\_4\\\_band,overtime\\\_band
Her periyot alanı yalnız şu değerleri alır: normal\\\_band, tempo\\\_up, tempo\\\_down, run\\\_against, run\\\_for, control\\\_lost, control\\\_gained, foul\\\_spike, turnover\\\_spike

TEMPO / RİTİM (ZORUNLU)
pace\\\_band\\\_overall,pace\\\_profile\\\_shape,rhythm\\\_disruption\\\_band,pace\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high,pace\\\_profile\\\_shape yalnız şu değerleri alır: flat, rising, falling, volatile,rhythm\\\_disruption\\\_band yalnız şu değerleri alır: none, minor, major

RUN / MOMENTUM (ZORUNLU)
run\\\_presence,run\\\_major\\\_count\\\_band,run\\\_trigger\\\_primary,run\\\_stop\\\_method\\\_primary,run\\\_presence yalnız şu değerleri alır: none, present,run\\\_major\\\_count\\\_band yalnız şu değerleri alır: none, 1, 2, 3\\\_plus,run\\\_trigger\\\_primary yalnız şu değerleri alır: none, turnover\\\_run, three\\\_point\\\_run, fastbreak\\\_run, foul\\\_trouble\\\_run, defensive\\\_stop\\\_run,run\\\_stop\\\_method\\\_primary yalnız şu değerleri alır: none, timeout, defensive\\\_adjustment, free\\\_throws, pace\\\_drop

FAUL / HAKEM (ZORUNLU)
foul\\\_threshold\\\_early\\\_flag,foul\\\_band\\\_overall,technical\\\_foul\\\_flag,unsportsmanlike\\\_flag,foul\\\_trouble\\\_flag,foul\\\_threshold\\\_early\\\_flag yalnız şu değerleri alır: none, present,foul\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high,technical\\\_foul\\\_flag yalnız şu değerleri alır: none, present,unsportsmanlike\\\_flag yalnız şu değerleri alır: none, present,foul\\\_trouble\\\_flag yalnız şu değerleri alır: none, present

SERBEST ATIŞ / FT SWING (ZORUNLU)
ft\\\_volume\\\_band,ft\\\_swing\\\_flag,bonus\\\_late\\\_game\\\_flag,ft\\\_volume\\\_band yalnız şu değerleri alır: low, medium, high,ft\\\_swing\\\_flag yalnız şu değerleri alır: none, present,bonus\\\_late\\\_game\\\_flag yalnız şu değerleri alır: none, present

TURNOVER (ZORUNLU)
turnover\\\_band\\\_overall,turnover\\\_cluster\\\_period,turnover\\\_run\\\_link\\\_flag,turnover\\\_band\\\_overall yalnız şu değerleri alır: low, medium, high,turnover\\\_cluster\\\_period yalnız şu değerleri alır: none, period\\\_1, period\\\_2, period\\\_3, period\\\_4, overtime,turnover\\\_run\\\_link\\\_flag yalnız şu değerleri alır: none, present

CLUTCH / SON 5 DAKİKA (ZORUNLU)
clutch\\\_band,late\\\_game\\\_disruption\\\_flag,late\\\_game\\\_panic\\\_flag,clutch\\\_band yalnız şu değerleri alır: stable, unstable,late\\\_game\\\_disruption\\\_flag yalnız şu değerleri alır: none, present,late\\\_game\\\_panic\\\_flag yalnız şu değerleri alır: none, present

BENCH / YILDIZ BAĞIMLILIĞI (ZORUNLU)
star\\\_dependency\\\_band,bench\\\_impact\\\_band,critical\\\_player\\\_foul\\\_trouble\\\_flag,star\\\_dependency\\\_band yalnız şu değerleri alır: low, medium, high,bench\\\_impact\\\_band yalnız şu değerleri alır: low, medium, high,critical\\\_player\\\_foul\\\_trouble\\\_flag yalnız şu değerleri alır: none, present

DATA QUALITY (ZORUNLU)
data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive

FAZ-26
BASKETBOL — KÜTÜPHANE + ETİKETLİ KARTLAR + MARKET/BOOKMAKER + RAPOR ŞABLONLARI | ARŞİV PAKETİ (NİHAİ / KODCUYA VERİLECEK / TEK DOSYA)
Aşağıdaki metin yoruma kapalı, bağlayıcı ve birebir uygulanması zorunlu uygulama promptudur. Bu metinde yazan her adım, her sıra, her rol, her yapı ve her isimlendirme değiştirilemez. Kod yazarı “daha iyisi olur”, “şöyle yapalım”, “şunu çıkaralım”, “bunu ekleyelim” gibi hiçbir yorum, öneri ve alternatif üretmez. Metinde olmayan hiçbir özellik eklenmez. Metinde olan hiçbir özellik çıkarılmaz. Yalnızca teknik olarak imkânsızlık varsa “şu madde teknik olarak imkânsız” cümlesiyle bildirir ve uygulama durdurulur. Çözüm önerisi getirilmez, soru sorulmaz, fikir üretilmez. Bu paket bir taslak değildir. Tamamlanmış ve kilitlenmiş sistem mimarisidir. Bu proje “bahis sitesi” kurmaz. Bu proje “bahse yönlendirme” yapmaz. Bu proje sadece istatistiksel analiz üretir ve gösterir. Her çıktı “istatistiksel değerlendirme” olarak kalacaktır. Bu sistemin tüm çıktıları “tahmin”, “öneri”, “yönlendirme”, “kesin sonuç” değildir. “Kesin kazanır, banko, tek” gibi dil yasaktır. Sistemin adı: Spor Anomali \\\& Örüntü Motoru (n8n tabanlı). Sistemin amacı: basketbol için haber + piyasa/oran + maç içi olay verilerini tek hiyerarşide toplamak, örüntü üretmek ve olağan akışa aykırı sapmaları “anomali” olarak işaretlemektir. Sistemin ürettiği şeyler: kütüphanelere işlenmiş ham veri, kütüphanelere işlenmiş etiketli veri, örüntü kütüphanesine yazılmış örüntü haritaları, anomali skoru + geçmiş etki oranı ve opsiyonel yönetici alarm kayıtlarıdır. Veri deposu teknolojisi JSON dosya tabanlı kütüphane deposudur. Kullanılacak formatlar JSON (kalıcı dosyalar) ve JSONL (büyük zaman serileri ve event/log akışları) olacaktır. Kod yazarı SQL/NoSQL/Postgres/MongoDB/Redis kullanmaz; yalnız dosya sistemi üzerinde JSON/JSONL üretir, okur ve günceller. Dosya yolu zorunludur: tüm dosyalar n8n proje dizininde ./library/ altında tutulur; absolute path yoktur, sadece relative path vardır. JSON dosyaları sınırsız büyütülmez; ham veri günlük dosyalara yazılır (YYYY-MM-DD.json), eskiler ./library/archive altına taşınır; index dosyaları her çalıştırma sonunda yeniden üretilir. Kütüphane hiyerarşisi sabittir ve bozulmaz: spor türü → ülke → lig → takım → sezon → dönem → maç → zaman bağlamı. Dönem tanımı sabittir: sezon başı / sezon ortası / sezon sonu; sezon ortası sabiti: devre arası son 3 hafta + ikinci devre başı ilk 3 hafta (“sezon ortası kritik pencere” etiketi). Sistem evreleri iki evredir: Evre-1 bootstrap (geçmiş veri çek, yerleştir, etiketle, örüntü haritaları üret, kalibrasyonu sabitle) + Evre-2 live (yeni maçları işle, kütüphaneyi büyüt, örüntü duvarını güncelle, anomali çıktıları üret). Veri giriş katmanı 3 ana kaynaktır: haber (newsapi.org) + piyasa/oran (oddsapi.io) + canlı event (basketbol live scores + match events ayrı API). Live event kaynağı newsapi/oddsapi değildir, ayrı kaynaktır. Gizli bilgiler manuel girilir; kod yazarı anahtar istemez, değer uydurmaz, sadece alan açar. 

ZORUNLU KONFİGÜRASYON DOSYASI: 
./library/config.json | alanlar: newsapi\\\_key, oddsapi\\\_key, live\\\_event\\\_api\\\_key, live\\\_event\\\_provider\\\_name, live\\\_event\\\_endpoint\\\_base, odds\\\_snapshot\\\_interval\\\_minutes, odds\\\_required\\\_markets, listed\\\_sports, basketbol\\\_league\\\_allowlist, cup\\\_allowlist, reference\\\_dictionary\\\_source, mode(public\\\_only/vip\\\_enabled). config.json boşsa sistem pasif modda kırılmadan çalışır. Kimlik/registry standardı zorunludur: ./library/basketball\\\_index.json içinde reference\\\_dictionary bloğu bulunur, tüm etiketleme sadece bu sözlükten yapılır. Eşleşmeyen kayıtlar unmapped rafına yazılır; yakın eşleştirme ile zorla atama yapılmaz. Maçlar sistem match\\\_id ile sabitlenir; modüller yalnız match\\\_id üzerinden bağlanır. Bootstrap kapsamı: zorunlu minimum son 3 tamamlanmış sezon indirilir ve kütüphanelere işlenir; API destekliyorsa daha fazlası çekilebilir ama minimum 3 sezondur. Basketbol modülü raf seti sabittir: basketbol kütüphanesi + haber kütüphanesi + oran/piyasa kütüphanesi + örüntü kütüphanesi + kupa kütüphanesi. Sosyal medya yoktur, dış yayın kanalı yoktur; çıktılar yalnız kütüphane dosyalarına ve index dosyalarına yazılır. Haber kütüphanesi ham sinyaldir, yorum yoktur: raf sırası = spor → ülke → lig → takım → sezon → dönem → zaman bağlamı → haber kaynağı → haber türü → haber tonu → haber metni. Haber tonu zorunlu: pozitif/nötr/negatif. Zaman bağlamı zorunlu: maç öncesi/maç günü-maç anı/maç sonrası/maçtan sonraki günler. Haber türü zorunlu: ajans/köşe/röportaj/yorum/sızıntı. Oran/piyasa kütüphanesi kolektif beklenti kaydıdır, tahmin değildir. Bookmaker seti sabittir: bet365, pinnacle, william hill, betfair, unibet, bwin, 888sport. Raf sırası = spor → ülke → lig → takım → sezon → dönem → maç → timestamp → bookmaker → market → line → odds\\\_set. Snapshot aralığı odds\\\_snapshot\\\_interval\\\_minutes ile zorunludur; odds\\\_required\\\_markets boş bırakılamaz (en az 1 market). Snapshot < 2 ise oran sapması hesaplanmaz; sapma skoru “hesaplanamadı/veri yetersiz” bandında kalır ve “anomali yok” yazılamaz. Maç/saha kütüphanesi maç içi olayları kaydeder: periyot skorları, faul sayıları, teknik faul, diskalifiye, top kaybı kümeleri, run, timeout, momentum kırılımları, son periyot kırılma noktaları. Hakem rafı ölçüm taşır (faul standardı/düdük yoğunluğu/bonus giriş/teknik faul eğilimi/maç sonu düdük profili), yorum ve suçlama dili taşımaz. Örüntü kütüphanesi 3 girdiyi birleştirir: basın/haber + oran/piyasa + maç içi olay. Çıktı: örüntü kodu + tekrar sayısı + geçmiş etki oranı + anomaly\\\_score. Raflar: ana örüntü rafı + bayraklı/anomali örüntü rafı. Bu raf “şike” olarak adlandırılamaz; yalnız “olağan dışı sapma”dır. Örüntü üretimi 2 aşamalıdır, sıra değişmez: Aşama-1 (topla/ayrıştır/yerleştir/index üret) + Aşama-2 (geriye dönük tarama/örüntü çıkar/normal davranış referansı/anomaly\\\_score kalibrasyonu). Aşama-2 kalibrasyonu bootstrap son 5 sezon verisi üzerinden sabitlenir; kod yazarı elle formül uydurmaz. Anomali skor formülü sabittir: anomaly\\\_score = (basın tonu sapması puanı) + (oran sapması puanı) + (maç içi kritik olay puanı). Bu 3 puanın 0–100 normalizasyonu ve ağırlıkları Aşama-2 tarafından üretilir ve sabitlenir. Aşama-2 tamamlanmadan anomalies boş veya “henüz hesaplanmadı” olabilir, bu hata değildir. Canlı event: bu sistemde insan canlı izleyici yoktur; event verisi API’den gelir. Live event yoksa maç içi kritik olay puanı 0 kalır ve sistem kırılmaz. Live event aktifse JSONL event alanları: match\\\_id, sport\\\_type, event\\\_type, event\\\_minute, team\\\_ref, timestamp. Bu modülde runtime “soru üreten motor” yoktur; arşivden import edilse bile runtime sözleşmesine dahil edilmez. Soru adedi hedefi yoktur; kapsama prensiple kilitlenir. low/medium/high bantları sadece basketbol bağlamında kullanılır; ganyan dili basketbola taşınmaz; “pist/mesafe/binici” etiketleri basket modülünde kullanılmaz. 

Zorunlu index dosyaları her çalıştırmada üretilir: 
./library/basketball\\\_index.json, ./library/basketball\\\_summary.json, ./library/basketball\\\_today\\\_matches.json, ./library/basketball\\\_anomalies\\\_public.json, ./library/basketball\\\_anomalies\\\_vip.json. Dosyalar boş olabilir ama üretimi zorunludur. 

“Anomali yok” yalnız sapma skoru hesaplanmış ve eşik altında kalmış durumda kullanılabilir; veri eksikliği “anomali yok” yazılamaz. Log/denetim zorunludur: hangi veri çekildi, hangi kütüphaneye yazıldı, hangi örüntü eşleşti, hangi anomali bayrağı yandı, hangi kayıt unmapped kaldı, hangi data\\\_quality\\\_badge uygulandı. Bu promptta tanımlanan yapı tamamlanmış ve kilitlenmiş bir basketbol sistem mimarisidir. Kod yazarı metni yorumlamaz; ekleme/çıkarma yapmaz; sırayı bozmaz; isimleri değiştirmez; branş dışı etiket üretmez; veri yoksa uydurmaz.\*\*

FAZ-27
BASKETBOL/FUTBOL — KİMLİK KARTI ÖZEL KİMLİK ÜRETİM STANDARDI (KİLİT / PROVIDER ID DRIFT KORUMASI) |
provider ID değişebilir; bu nedenle tüm varlık kartları provider ID ile tek başına yaşamaz; her kartta ayrıca sabit canonical\\\_identity\\\_key zorunludur; canonical\\\_identity\\\_key deterministik bileşenlerden üretilir, veri yoksa unknown yazılır, uydurma yapılmaz; takım kartı takım rafında kalır, kadro takımda snapshot olabilir ama oyuncu kimliği oyuncu kartında yaşar; oyuncu kartı oyuncunun peşinde taşınır ve geçmişten geleceğe oyunculuk hayatı boyunca tek kartta birikir; koç kartı koçun peşinde taşınır ve kariyeri boyunca tek kartta birikir; hakem kartı hakemin peşinde taşınır ve kariyeri boyunca tek kartta birikir; bu kimlik drift kontrolü içindir, tahmin/öneri üretmez. 

Takım Kartı Kimliği 
(TEAM\\\_CANON\\\_ID) | ülke + lig + takım adı + şehir + renk + varsa stat ismi + kuruluş tarihi(GGAAYY) + cinsiyet(male/female/mixed/unknown) + sayaç(00001–10000, auto) birleşimidir; sayaç elle yazılmaz. 
Oyuncu Kartı Kimliği 
(PLAYER\\\_CANON\\\_ID) | ad soyad + doğum tarihi + pozisyon + ilk lisans aldığı takım + başladığı yıl + uyruk + cinsiyet(male/female/unknown) + en son oynadığı takım + sayaç(000001–100000, auto) birleşimidir; sayaç elle yazılmaz. 

Hoca Kartı Kimliği 
(COACH\\\_CANON\\\_ID) | ad soyad + doğum tarihi + uyruk + cinsiyet(male/female/unknown) + başladığı kulüp + başladığı yıl + sayaç(00001–10000, auto) birleşimidir; sayaç elle yazılmaz. 
Hakem Kartı Kimliği 
(REFEREE\\\_CANON\\\_ID) | ad soyad + doğum tarihi + uyruk + cinsiyet(male/female/unknown) + başladığı yıl + statüsü + sayaç(000001–100000, auto) birleşimidir; sayaç elle yazılmaz; statü veri yoksa unknown yazılır. Kimlik Drift Tespiti (Kilit Davranış) | yeni provider ID geldiğinde canonical\\\_identity\\\_key eşleşiyorsa sistem same\\\_entity\\\_id\\\_drift\\\_detected işaretler, provider\\\_id günceller, canonical kimliği değiştirmez; canonical\\\_identity\\\_key üretilemeyecek kadar eksik veri varsa kayıt data\\\_quality\\\_badge ile güvenli saklanır, zorla eşleştirme yapılmaz.\*\*


BASKETBOL — CANLI İZLEME / RAPORLAMA / KÜTÜPHANEYE YAZIM | OTOMASYON EKİBİ ÇALIŞMA TALİMATI (GENİŞ SÜRÜM / ROL TABLOSU GÖMÜLÜ / KODCUYA VERİLECEK)
Bu sistemde canlı insan yoktur. Watcher/Reporter/Analyst/Librarian/Decision Engine rollerinin tamamı otomasyon ajanlarıdır. Tek insan operatör kullanıcıdır; operatör yalnız manuel tetikleme yapar. Sistem bahis sistemi değildir; maç sonucu veya bahis önerisi üretmez; çıktılar yalnız istatistiksel ölçüm, zaman hizası ve bant sapması işaretidir. ROL TABLOSU | Watcher Agents: 14 | Reporter Agents: 4 | Analyst Agents: 1 | Librarian: 1 | Decision Engine: 1 | Toplam: 21 | Tek Operatör: 1 | Not: “14 izleyici + 4 raportör + 1 analist + 1 kütüphaneci” sabittir; Decision Engine bağımsız modüldür ve bahis önerisi üretmeden yalnız skor/tempo/şema sapmasını karar etiketi olarak işaretler.
 
SİSTEMİN YAPTIĞI İŞ |
canlı olay izlerini toplar, tekilleştirir, çelişkiyi çözmeden işaretler, deterministik şemada kütüphaneye işler; veri eksikse “anomali yok” denmez, data\\\_quality\\\_badge düşürülür; basın rafı bağlamdır, maç içi eksik event basınla tamamlanamaz.

KİMLİK/REFERENCE POLİTİKASI | 
serbest metin kimlik yoktur; team\\\_ref/league\\\_ref/country\\\_ref/person\\\_ref yalnız reference\\\_dictionary’den gelir; unmapped zorla eşlenmez; reference\\\_dictionary dışında benzer isim eşlemesi yapılmaz; unmapped kayıtlar güvenlik bandıdır ve korunur.
 
BOŞ BIRAKMA / UYDURMA YASAĞI |
veri yokken alan boş bırakılmaz; unknown/none/inactive/unmapped bantları deterministik kullanılır; “anomali yok” hükmü veri eksikliğiyle yazılamaz.
 
ROL SETİ | 
Watcher: ham iz toplar, yorum yazmaz, paket dışı kayıt girmez, karar motoruna yazmaz | Reporter: tekilleştirir, çelişkiyi işaretler, yorum yazmaz | Analyst: paketleri birleştirir, informed\\\_by kurar, ölçüm bandı üretir, tahmin/bahis önerisi üretmez | Librarian: tek yazıcıdır, şema dışına çıkamaz, serbest metin kimlik kullanamaz, unmapped zorlamaz, eksikleri örtmez, append\\\_only çalışır | Decision Engine: yalnız Analyst raporundan beslenir, ham veri değiştiremez, bahis önerisi vermez, karar etiketleri üretir, kütüphaneye yazmaz. 

ZAMANLAMA / KAYIT MODELİ |
olay-anı bazlıdır; otomatik timestamp\\\_utc alınır; 30 saniyelik indeks bandı otomatik atanır; manuel band seçimi/düzeltmesi yoktur; olay yoksa no\\\_event ile veri doldurulmaz, olay yokluğu yalnız kapsama haritasında gösterilir. 30s indeks bandı | Q1\\\_00:00-00:29, Q1\\\_00:30-00:59 … Q4\\\_39:30-39:59 | ek bantlar: clutch\\\_02:00, clutch\\\_01:00, clutch\\\_00:30. 

PAKETLEME | 4 paket | Watcher dağılımı 4+4+3+3 | her paket 1 Reporter | Analyst üst birleştirici | Librarian nihai yazıcı. PAKET-1(BP1)

SKOR/RUN/MOMENTUM | 
score\\\_run\\\_start, score\\\_run\\\_end, lead\\\_change, tie\\\_game, momentum\\\_shift, quarter\\\_close\\\_behavior, clutch\\\_run.
 
PAKET-2(BP2) FAUL/HAKEM/FT |
team\\\_foul\\\_cluster, star\\\_foul\\\_trouble, bonus\\\_entered, technical\\\_foul, flagrant\\\_foul, free\\\_throw\\\_swing, referee\\\_line\\\_shift\\\_soft, referee\\\_line\\\_shift\\\_hard. 

PAKET-3(BP3) ROTASYON/5’Lİ/KOÇ |
timeout\\\_called, timeout\\\_run\\\_break, lineup\\\_change, closing\\\_lineup\\\_set, early\\\_bench\\\_injection, coach\\\_adjustment\\\_visible.
 
PAKET-4(BP4) ŞUT/3PT/TOP KAYBI | 
three\\\_point\\\_streak\\\_hit, three\\\_point\\\_streak\\\_miss, shot\\\_quality\\\_drop, paint\\\_attack\\\_shift, turnover\\\_cluster, live\\\_ball\\\_turnover\\\_fastbreak, pace\\\_spike, pace\\\_drop.
 
WATCHER HAM İZ (ZORUNLU ŞEMA) |
watch\\\_trace\\\_ref:AUTO | match\\\_ref:REQUIRED | timestamp\\\_utc:REQUIRED | index\\\_band\\\_auto\\\_30s:REQUIRED | package\\\_id:REQUIRED(BP1/BP2/BP3/BP4) | watcher\\\_id:REQUIRED | event\\\_type:REQUIRED | event\\\_subtype:OPTIONAL | team\\\_side:home/away/none | team\\\_ref:OPTIONAL | person\\\_ref:OPTIONAL(none) | league\\\_ref:OPTIONAL | country\\\_ref:OPTIONAL | confidence\\\_band:low/medium/high | evidence\\\_level:low/medium/high | source\\\_type:live\\\_feed/stats\\\_feed/odds\\\_feed | data\\\_quality\\\_badge:low/medium/high | note:kısa deterministik açıklama(yorum yok).
 
REPORTER PAKET RAPORU (ZORUNLU ŞEMA) |
package\\\_report\\\_ref:AUTO | match\\\_ref:REQUIRED | package\\\_id:REQUIRED | reporter\\\_id:REQUIRED | event\\\_sequence:REQUIRED | deduplication\\\_map:REQUIRED | conflict\\\_list:REQUIRED | unknown\\\_fields\\\_map:REQUIRED | package\\\_data\\\_quality\\\_badge:low/medium/high.

ANALYST TEK MAÇ RAPORU (ZORUNLU ŞEMA) |
match\\\_report\\\_ref:AUTO | match\\\_ref:REQUIRED | merged\\\_packages:REQUIRED(BP1..BP4) | final\\\_conflict\\\_resolution:mark\\\_only | overall\\\_data\\\_quality\\\_badge:low/medium/high | anomaly\\\_flags:none/weak\\\_signal/strong\\\_signal | informed\\\_by:match\\\_card\\\_ref|match\\\_events\\\_ref|odds\\\_timeline\\\_ref | delivery\\\_policy:no\\\_prediction|no\\\_betting\\\_advice | kural:evidence\\\_level/confidence\\\_band yüksek olsa bile data\\\_quality\\\_badge düşükse çözüm yapılmaz, yalnız mark\\\_only. 

LIBRARIAN YAZIM KURALLARI (SERT) |
deterministik raflara yazar | serbest metin kimlik yok | reference\\\_dictionary dışı eşleme yok | unmapped zorla map yok | basın rafı maç içi rafları doldurmaz | veri yoksa boş bırakmaz unknown/none/inactive | eksik örtmez data\\\_quality\\\_badge düşürür | silmez append\\\_only | aynı match\\\_ref güncellenirse sürümleme yapar. 

DECISION ENGINE |
yalnız Analyst raporundan beslenir | ham veriyi üretemez/değiştiremez | tahmin/bahis önerisi vermez | deterministik karar etiketleri üretir | kütüphaneye yazmaz karar\\\_motoru rafında saklar | decision\\\_tags: run\\\_instability\\\_high, foul\\\_risk\\\_high, clutch\\\_control\\\_low, turnover\\\_spike\\\_high, three\\\_point\\\_variance\\\_high, rotation\\\_disruption\\\_high, referee\\\_line\\\_shift\\\_detected, tempo\\\_control\\\_shifted. Kapanış Notu | Basketbol Canlı İzleme + Kütüphane Yazım Talimatı — geniş sürüm + rol tablosu + 30s indeksleme tamamlandı / tek dosya olarak kullanılacak.

BASKETBOL — MARKET KÜTÜPHANESİ (ANA TAHTA + YAN TAHTA) | FAZ-1 TESLİMİ (Kart + Etiket Duvarı + Soru Kütüphanesi / TEK PARÇA BİRLEŞİK)
library\\\_ref:BASKETBALL\\\_MARKET\\\_LIBRARY\\\_V1 | kart\\\_durumu:FAZ-1\\\_SKELETON\\\_ACTIVE | politika: market listesi deterministik/sabit; market\\\_ref ile yaşar; isim serbest metin değildir; provider map ile bağlanır; unmapped korunur; eksik veri inactive/unknown bantlarıyla taşınır; bahis önerisi yok; zaman hizası ve bant sapması ölçer | not: ana tahta + yan tahta market rafı kurulur; odds akışı ve BOOKMAKER\\\_ALLOWLIST Faz-2’de marketlere bağlanır.

BASKETBOL — ANA TAHTA MARKETLER (30 ANA MARKET / DETERMINİSTİK LİSTE)
BB\\\_MKT\\\_001 | Moneyline(Match Winner) | group:core\\\_result | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_002 | Point Spread(Handicap) | group:spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_003 | Total Points(O/U) | group:totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_004 | 1st Half Winner | group:halftime | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_005 | 1st Half Spread | group:halftime\\\_spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_006 | 1st Half Total Points | group:halftime\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_007 | 1st Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_008 | 1st Quarter Spread | group:quarter\\\_spread 

| required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_009 | 1st Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_010 | 2nd Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_011 | 2nd Quarter Spread | group:quarter\\\_spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_012 | 2nd Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_013 | 3rd Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_014 | 3rd Quarter Spread | group:quarter\\\_spread | required:line,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_015 | 3rd Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_016 | 4th Quarter Winner | group:quarter | required:home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_017 | 4th Quarter Spread | group:quarter\\\_spread | required:line,home\\\_price,away\\\_price | status:active 

| BB\\\_MKT\\\_018 | 4th Quarter Total Points | group:quarter\\\_totals | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_019 | Team Total Points | group:team\\\_totals | required:team\\\_side,line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_020 | Race To X Points | group:race | required:target\\\_points,home\\\_price,away\\\_price | status:active | BB\\\_MKT\\\_021 | Winning Margin | group:margin | required:margin\\\_price\\\_map | status:active | BB\\\_MKT\\\_022 | Highest Scoring Quarter | group:quarter\\\_meta | required:q1\\\_price,q2\\\_price,q3\\\_price,q4\\\_price | status:active | BB\\\_MKT\\\_023 | Lowest Scoring Quarter | group:quarter\\\_meta | required:q1\\\_price,q2\\\_price,q3\\\_price,q4\\\_price | status:active | BB\\\_MKT\\\_024 | Team To Score First(First Points) | group:first\\\_event | required:home\\\_price,away\\\_price | status:active 

| BB\\\_MKT\\\_025 | Total Points Odd/Even | group:totals\\\_parity | required:odd\\\_price,even\\\_price | status:active | BB\\\_MKT\\\_026 | Both Teams Over X(Alt Combo) | group:combo | required:line\\\_a,line\\\_b,yes\\\_price,no\\\_price | status:active | BB\\\_MKT\\\_027 | Total 3PT Made(O/U) | group:three\\\_point | required:line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_028 | Team Total 3PT Made | group:team\\\_three\\\_point | required:team\\\_side,line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_029 | Player Points(O/U) | group:player\\\_points | required:player\\\_ref,line,over\\\_price,under\\\_price | status:active | BB\\\_MKT\\\_030 | Player Rebounds(O/U) | group:player\\\_rebounds | required:player\\\_ref,line,over\\\_price,under\\\_price | status:active

BASKETBOL — YAN TAHTA MARKETLER (30 EXTENDED / NİŞ RAF)
BB\\\_XMKT\\\_001 | Player Assists(O/U) | group:player\\\_assists | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_002 | Player Steals(O/U) | group:player\\\_steals | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_003 | Player Blocks(O/U) | group:player\\\_blocks | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_004 

| Player Turnovers(O/U) | group:player\\\_turnovers | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_005 | Player 3PT Made(O/U) | group:player\\\_three\\\_point | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_006 | Player Double-Double | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_007 | Player Triple-Double | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_008 | Team Total Rebounds | group:team\\\_rebounds | required:team\\\_side,line,over\\\_price,under\\\_price 

| status:inactive | BB\\\_XMKT\\\_009 | Team Total Assists | group:team\\\_assists | required:team\\\_side,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_010 | Team Total Turnovers | group:team\\\_turnovers | required:team\\\_side,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_011 | Player PRA(P+R+A) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_012 | Player PA(P+A) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_013 | Player PR(P+R) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_014 | Player RA(R+A) | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_015 | Player Points 1st Half | group:player\\\_points\\\_split 

| required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_016 | Player Points 1st Quarter | group:player\\\_points\\\_split | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_017 | Player Rebounds 1st Half | group:player\\\_rebounds\\\_split | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_018 | Player Assists 1st Half | group:player\\\_assists\\\_split | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_019 | Player To Score 20+ | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive 

| BB\\\_XMKT\\\_020 | Player To Score 25+ | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_021 | Player To Score 30+ | group:player\\\_milestones | required:player\\\_ref,yes\\\_price,no\\\_price | status:inactive | BB\\\_XMKT\\\_022 | First Basket Scorer | group:first\\\_event | required:player\\\_ref,yes\\\_price | status:inactive | BB\\\_XMKT\\\_023 | Last Basket Scorer | group:last\\\_event | required:player\\\_ref,yes\\\_price | status:inactive | BB\\\_XMKT\\\_024 | First Team To Make 5 Threes | group:team\\\_race | required:home\\\_price,away\\\_price | status:inactive | BB\\\_XMKT\\\_025 | Total Free Throws Made(O/U) 

| group:free\\\_throws | required:line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_026 | Team Total Free Throws Made | group:team\\\_free\\\_throws | required:team\\\_side,line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_027 | Total Turnovers(Match) | group:turnovers | required:line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_028 | Alternative Spread(Alt Handicap) | group:alt\\\_spread | required:line,home\\\_price,away\\\_price | status:inactive | BB\\\_XMKT\\\_029 | Alternative Totals(Alt O/U) | group:alt\\\_totals | required:line,over\\\_price,under\\\_price | status:inactive | BB\\\_XMKT\\\_030 | Player Points+3PT Combo | group:player\\\_combo | required:player\\\_ref,line,over\\\_price,under\\\_price | status:inactive


BASKETBOL — MARKET ETİKET DUVARI (FAZ-1 DETERMINİSTİK) | unknown:veri\\\_yok/doğrulanmadı | none:alan\\\_geçerli\\\_içerik\\\_yok | inactive:provider\\\_yok/market\\\_kapalı | unmapped:provider\\\_eşleşmesi\\\_yok | active:takipte | inactive\\\_market:market\\\_verisi\\\_yok/pasif | market\\\_group: core\\\_result|spread|totals|halftime|halftime\\\_spread|halftime\\\_totals|quarter|quarter\\\_spread|quarter\\\_totals|team\\\_totals|race|margin|quarter\\\_meta|first\\\_event|totals\\\_parity|combo|three\\\_point|team\\\_three\\\_point|player\\\_points|player\\\_rebounds|player\\\_assists|player\\\_steals|player\\\_blocks|player\\\_turnovers|player\\\_milestones|team\\\_rebounds

|team\\\_assists|team\\\_turnovers|player\\\_combo|player\\\_points\\\_split|player\\\_rebounds\\\_split|player\\\_assists\\\_split|team\\\_race|free\\\_throws|team\\\_free\\\_throws|alt\\\_spread|alt\\\_totals|turnovers | market\\\_status:active|inactive|inactive\\\_market | required\\\_fields\\\_completeness:low|medium|high | provider\\\_mapping\\\_status:unmapped|mapped | odds\\\_update\\\_speed\\\_band:unknown|slow|medium|fast | market\\\_latency\\\_band:unknown|low|medium|high | inplay\\\_availability\\\_band:unknown|low|medium|high | suspension\\\_tendency\\\_band:unknown|low|medium|high | closing\\\_line\\\_integrity\\\_band:unknown|low|medium|high | Kapanış: Market Kütüphanesi tamamlandı.

BOOKMAKER KÜTÜPHANESİ — FAZ-1 TESLİMİ
(Kart + Etiket Duvarı + Soru Kütüphanesi) 
library\\\_ref:BOOKMAKER\\\_LIBRARY\\\_V1 | kart\\\_durumu:FAZ-1\\\_SKELETON\\\_ACTIVE | politika: bahis önerisi yok; bookmaker\\\_ref reference\\\_dictionary’den gelir; unmapped zorla eşlenmez; eksik veri unknown/none/inactive ile korunur. 

BOOKMAKER KARTI (FAZ-1 İSKELET) 
bookmaker\\\_ref:UNKNOWN\\\_BOOKMAKER\\\_REF | bookmaker\\\_name:unknown | brand\\\_variants:none | license\\\_country\\\_ref:unknown | service\\\_regions:unknown | feed\\\_provider\\\_ref:unknown | supported\\\_sports:unknown | supported\\\_leagues\\\_scope:unknown | tier\\\_support\\\_band:unknown | odds\\\_feed\\\_status:inactive | data\\\_quality\\\_badge:low 
| Coverage(core\\\_markets\\\_supported:unknown,extended\\\_markets\\\_supported:unknown,player\\\_props\\\_supported:unknown,inplay\\\_supported:unknown,market\\\_depth\\\_band:unknown,alt\\\_lines\\\_supported:unknown) 
| UpdateLatency(odds\\\_update\\\_speed\\\_band:unknown,market\\\_latency\\\_band:unknown,timestamp\\\_integrity\\\_band:unknown,suspension\\\_tendency\\\_band:unknown,reopen\\\_behavior\\\_band:unknown) | PricingLine(line\\\_shift\\\_frequency\\\_band:unknown,price\\\_shift\\\_frequency\\\_band:unknown,line\\\_vs\\\_price\\\_preference:unknown,opening\\\_line\\\_style\\\_band:unknown,closing\\\_line\\\_style\\\_band:unknown,risk\\\_rebalance\\\_style\\\_band:unknown) | Drift(divergence\\\_vs\\\_pack\\\_band:unknown,persistent\\\_drift\\\_band:unknown,spike\\\_anomaly\\\_tendency\\\_band:unknown,sharp\\\_following\\\_band:unknown,contrarian\\\_band:unknown) 
| Integrity(void\\\_cancel\\\_policy\\\_band:unknown,limit\\\_restriction\\\_band:unknown,market\\\_freeze\\\_pattern\\\_band:unknown,outage\\\_incident\\\_band:unknown,feed\\\_gap\\\_band:unknown) | InformedBy(odds\\\_market\\\_timeline:none,market\\\_library\\\_ref:none,match\\\_ref:none,league\\\_ref:none). 

BOOKMAKER ETİKET DUVARI (FAZ-1) |
unknown:veri\\\_yok/doğrulanmadı | none:alan\\\_geçerli\\\_içerik\\\_yok | inactive:feed\\\_yok/pasif | unmapped:reference\\\_dictionary\\\_eşleşmesi\\\_yok | weak\\\_signal:tekil\\\_zayıf\\\_kaynak | strong\\\_signal:çoklu\\\_kaynak\\\_teyidi | odds\\\_feed\\\_status:inactive|active | tier\\\_support\\\_band:unknown|tier1\\\_only|tier1\\\_tier2 | market\\\_depth\\\_band:unknown|shallow|medium|deep | player\\\_props\\\_supported:unknown|low|medium|high | inplay\\\_supported:unknown|low|medium|high | alt\\\_lines\\\_supported:unknown|low|medium|high | odds\\\_update\\\_speed\\\_band:unknown|slow|medium|fast | market\\\_latency\\\_band:unknown|low|medium|high 

| timestamp\\\_integrity\\\_band:unknown|low|medium|high | suspension\\\_tendency\\\_band:unknown|low|medium|high | reopen\\\_behavior\\\_band:unknown|stable|jumpy | line\\\_shift\\\_frequency\\\_band:unknown|low|medium|high | price\\\_shift\\\_frequency\\\_band:unknown|low|medium|high | line\\\_vs\\\_price\\\_preference:unknown|line\\\_first|price\\\_first|mixed | opening\\\_line\\\_style\\\_band:unknown|conservative|balanced|aggressive | closing\\\_line\\\_style\\\_band:unknown|tight|loose | risk\\\_rebalance\\\_style\\\_band:unknown|smooth|stepwise|abrupt | divergence\\\_vs\\\_pack\\\_band:unknown|low|medium|high | persistent\\\_drift\\\_band:unknown|low|medium|high 

| spike\\\_anomaly\\\_tendency\\\_band:unknown|low|medium|high | sharp\\\_following\\\_band:unknown|low|medium|high | contrarian\\\_band:unknown|low|medium|high | void\\\_cancel\\\_policy\\\_band:unknown|strict|balanced|lenient | limit\\\_restriction\\\_band:unknown|low|medium|high | market\\\_freeze\\\_pattern\\\_band:unknown|low|medium|high | outage\\\_incident\\\_band:unknown|low|medium|high | feed\\\_gap\\\_band:unknown|low|medium|high | BOOKMAKER SORU KÜTÜPHANESİ (FAZ-1) | | Kapanış: Bookmaker Kütüphanesi tamamlandı.

BASKETBOL — ARŞİV PAKETİ (NİHAİ) | Tamamlandı / dosyalanabilir tek çıktı | Bitti.

KİLİT BEYANI | 
Bu metin “BASKETBOL — ARŞİV PAKETİ (NİHAİ / KODCUYA VERİLECEK /)” olarak kilitlenmiştir.


FAZ-37
BASKETBOL HAKEM KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı hakemi “iyi/kötü” diye etiketlemek değildir. Amaç, hakemin maç ritmini, faul eşiğini ve son periyot yönetimini tekrar eden bantlarla okumaktır. Hüküm kurulmaz, suçlama dili yoktur. Sadece davranış bandı çıkarılır.

Hakemin faul eşiği erken mi oluşuyor, geç mi oluşuyor? Bu soru, maçın ritminin serbest mi sert mi akacağını belirleyen ilk ana kilittir.
Hakem ilk periyotta mı, yoksa üçüncü/dördüncü periyotta mı çizgiyi sertleştiriyor? Bu soru, hakemin maç içi çizgi değişimini ölçer. Çizgi değişiyorsa run ve tempo kırılır.
Hakemin teknik faul toleransı hangi bantta? Bu soru, maçın psikolojik kırılma riskini ölçer. Teknik faul bandı yüksekse mental kırılma artar.
Hakem unsportsmanlike faul kararlarını sık mı veriyor? Bu soru, sertlik bandını ve kritik skor anlarında oyunun yön değiştirme riskini ölçer.

Hakem “bonus” dönemlerinde oyunu daha mı çok durduruyor? Bu soru, son periyot dur-kalk ritmini ve FT swing ihtimalini yükselten hakem davranışını ölçer.
Hakem son 2 dakikada düdük yoğunluğunu artırıyor mu azaltıyor mu? Bu soru, clutch bandın “oyuncu kararı” mı yoksa “çizgi kararı” mı olduğuna dair bağlam üretir.
Hakemin itiraz ve bench tepkilerine toleransı nasıl? Bu soru, koç kartı ve takım mental bandıyla kesişir. Tolerans düşükse teknik faul riski artar.

Hakemin faul dağılımı tek tarafa mı yığılıyor yoksa dengeli mi? Bu soru, suçlama üretmez; yalnız “dağılım bandı” çıkarır. Tek tarafa yığılma tekrar ediyorsa işaretlenir.
Hakemin maç başına ortalama faul hacmi lig normuna göre sapıyor mu? Bu soru, hakemin lig içi profilini sabitler. Sapma varsa maç okumasında bu bant dikkate alınır.
Hakem ile belirli lig/organizasyon tiplerinde daha sık ritim kırılması eşleşiyor mu? Bu soru, hakem profili ile lig profili kesişimini ölçer.

BASKETBOL HAKEM KARTI — ETİKET KATALOĞU
timestamp\\\_utc,referee\\\_ref,country\\\_ref,league\\\_refseason\\\_id,competition\\\_type,season\\\_phase,referee\\\_foul\\\_threshold\\\_band,referee\\\_line\\\_shift\\\_band,referee\\\_tech\\\_tolerance\\\_band,referee\\\_unsportsmanlike\\\_band,referee\\\_bonus\\\_whistle\\\_band,referee\\\_clutch\\\_whistle\\\_band,referee\\\_distribution\\\_balance\\\_band,referee\\\_rhythm\\\_disruption\\\_band,referee\\\_foul\\\_threshold\\\_band yalnız şu değerleri alır: early, normal, late,referee\\\_line\\\_shift\\\_band yalnız şu değerleri alır: none, soft\\\_to\\\_hard, hard\\\_to\\\_soft, volatile,referee\\\_tech\\\_tolerance\\\_band yalnız şu değerleri alır: low, medium, high,referee\\\_unsportsmanlike\\\_band yalnız şu değerleri alır: low, medium, high,referee\\\_bonus\\\_whistle\\\_band yalnız şu değerleri alır: low, medium, high,referee\\\_clutch\\\_whistle\\\_band yalnız şu değerleri alır: low, medium, high,referee\\\_distribution\\\_balance\\\_band yalnız şu değerleri alır: balanced, mild\\\_skew, heavy\\\_skew,referee\\\_rhythm\\\_disruption\\\_band yalnız şu değerleri alır: none, minor, major,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive

BASKETBOL KOÇ (TEKNİK DİREKTÖR) KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı koçu “iyi/kötü” diye sınıflamak değildir. Amaç, koçun müdahale zamanlamasını, run kesme refleksini, foul-trouble yönetimini ve clutch karar bandını tekrar eden örüntülerle kartlaştırmaktır.
Koç timeout’u run başında mı, run büyüyünce mi alıyor? Bu soru, koçun kriz refleks hızını ölçer. Geç timeout tekrar ediyorsa risk bandı artar.
Koç timeout sonrası run’ı kesiyor mu, yoksa aynı problem devam ediyor mu? Bu soru, timeout’un “işlevsel” olup olmadığını ölçer. Timeout alıp kesemiyorsa plan etkisi düşüktür.
Koç foul-trouble yaşayan kritik oyuncuyu nasıl yönetiyor? Bu soru, risk yönetimini ölçer. Kritik oyuncuyu erken koruma veya sahada tutma stratejisi kartlaşır.

Koç bench rotasyonuyla ikinci periyotta avantaj mı kayıp mı üretiyor? Bu soru, bench planının net çıktısını ölçer. Rotasyon bandı DNA sinyalidir.
Koç devre arası (3. periyot) ayarlama gücü gösteriyor mu? Bu soru, strateji uyarlama kapasitesini ölçer. Üçüncü periyot refleksi koç kartının ana çekirdeğidir.
Koç son 5 dakikada kararlarını sade mi tutuyor yoksa panik dalgalanması mı var? Bu soru, clutch yönetimini ölçer. Panik tekrar ediyorsa kapanış bandı zayıftır.
Koç hakem çizgisi değişiminde oyunu sakinleştiriyor mu yoksa teknik faul riski büyüyor mu? Bu soru, koçun hakemle temas yönetimini ölçer. Teknik faul riski koç kartına yazılır.

Koç skor öndeyken oyunu yavaşlatıp koruyor mu, yoksa tempo bozuluyor mu? Bu soru, skor yönetimi stratejisini ölçer. Koruma bandı tekrar ediyorsa kartlaşır.
Koç gerideyken kontrollü geri dönüş mü, yoksa panik hücum mu üretiyor? Bu soru, geri dönüş stratejisinin stabilitesini ölçer. Panik hücum turnover riskini artırır.
Koçun oyun planı bir-iki oyuncuya mı bağımlı, yoksa dağıtık mı? Bu soru, yıldız bağımlılığına koçun katkısını ölçer.

BASKETBOL KOÇ KARTI — ETİKET KATALOĞU
timestamp\\\_utc.coach\\\_ref,team\\\_ref,country\\\_ref,league\\\_ref,season\\\_id,competition\\\_type,season\\\_phase,coach\\\_timeout\\\_timing\\\_band,coach\\\_timeout\\\_effect\\\_band,coach\\\_rotation\\\_band
coach\\\_halftime\\\_adjustment\\\_band,coach\\\_foul\\\_trouble\\\_management\\\_band,coach\\\_clutch\\\_management\\\_band,coach\\\_referee\\\_interaction\\\_risk\\\_band,coach\\\_lead\\\_protection\\\_band\
coach\\\_comeback\\\_strategy\\\_band,coach\\\_star\\\_dependency\\\_band,coach\\\_timeout\\\_timing\\\_band yalnız şu değerleri alır: early, normal, late,coach\\\_timeout\\\_effect\\\_band yalnız şu değerleri alır:

effective, partial, ineffective,coach\\\_rotation\\\_band yalnız şu değerleri alır: strong, normal, weak,coach\\\_halftime\\\_adjustment\\\_band yalnız şu değerleri alır: strong, normal, weak,coach\\\_foul\\\_trouble\\\_manageme
\\\_band yalnız şu değerleri alır.

stable, unstable,coach\\\_clutch\\\_management\\\_band yalnız şu değerleri alır: stable, unstable,coach\\\_referee\\\_interaction\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high
coach\\\_lead\\\_protection\\\_band yalnız şu değerleri alır: stable, unstable,coach\\\_comeback\\\_strategy\\\_band yalnız şu değerleri alır: controlled, chaotic
coach\\\_star\\\_dependency\\\_band yalnız şu değerleri alır: low, medium, high,data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive.


BASKETBOL OYUNCU KARTI — ANALİZ EĞİTİM SORU KATALOĞU
Bu kartın amacı oyuncuya “iyi/kötü” etiketi koymak değildir. Amaç, oyuncunun baskı altında karar kalitesini, foul-trouble riskini, clutch stabilitesini ve momentum kırılmalarındaki rolünü kartlaştırmaktır. Oyuncu kartı kulüp değişse bile kimliği taşır.

Oyuncu maç başlangıcında stabil mi yoksa dalgalı mı başlıyor?,Bu soru, erken ritim bandını ölçer. Bazı oyuncular maçın ilk 5 dakikasında düşük stabilite gösterir.
Oyuncu top kaybı üretme eğilimini tempo artışında yükseltiyor mu?,Bu soru, pace ile karar kalitesi ilişkisidir. Hız artınca hata artıyorsa band belirgindir.
Oyuncu foul-trouble riskine erken mi giriyor, geç mi giriyor?,Bu soru, oyuncunun savunma disiplinini ölçer. Erken foul-trouble takımı bozar.

Oyuncu kritik anlarda teknik faul/itiraz riskine giriyor mu?,Bu soru, mental stabiliteyi ölçer. Teknik risk kartlaşır.
Oyuncu serbest atışta clutch bandı stabil mi?,Bu soru, FT swing riskini oyuncu düzeyinde ölçer. Son 2 dakika kaçırma trendi önemli sinyaldir.
Oyuncu run başlatan mı, run bitiren mi, run yiyen mi? Bu soru, momentum etkisini ölçer. Oyuncunun run içindeki rolü stabilse kartın ana parçasıdır.

Oyuncu savunmada hedef oluyor mu ve bu periyotlara göre değişiyor mu? Bu soru, rakibin saldırdığı zayıf halka davranışını ölçer. Periyot bazlı hedeflenme görülür.
Oyuncu bench’e çıktığında takım performansı düşüyor mu? Bu soru, oyuncunun takım bağımlılığını ölçer. On/off etkisi yüksekse kritik oyuncudur.
Oyuncu son periyot kararlarında panik mi, kontrollü mü? Bu soru, clutch karar kalitesini ölçer. Panik turnover ve kötü şut seçimine bağlanır.
Oyuncu hakem çizgisi sertleşince oyununu adapte ediyor mu? Bu soru, hakem bandına adaptasyon becerisini ölçer. Adaptasyon yoksa foul-trouble artar.

BASKETBOL OYUNCU KARTI — ETİKET KATALOĞU
timestamp\\\_utc,player\\\_ref,team\\\_ref,country\\\_ref,league\\\_ref,season\\\_id,competition\\\_type,season\\\_phase
player\\\_start\\\_stability\\\_band,player\\\_turnover\\\_under\\\_pace\\\_band,player\\\_foul\\\_trouble\\\_risk\\\_band,player\\\_tech\\\_risk\\\_band,player\\\_ft\\\_clutch\\\_band,player\\\_momentum\\\_role\\\_band
player\\\_defensive\\\_target\\\_band,player\\\_on\\\_off\\\_dependency\\\_band,player\\\_clutch\\\_decision\\\_band,player\\\_referee\\\_adaptation\\\_band
player\\\_start\\\_stability\\\_band yalnız şu değerleri alır: stable, unstable,player\\\_turnover\\\_under\\\_pace\\\_band yalnız şu değerleri alır: low, medium, high

player\\\_foul\\\_trouble\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_tech\\\_risk\\\_band yalnız şu değerleri alır: low, medium, high
player\\\_ft\\\_clutch\\\_band yalnız şu değerleri alır: stable, unstable,player\\\_momentum\\\_role\\\_band yalnız şu değerleri alır: neutral, run\\\_starter, run\\\_stopper, run\\\_against
player\\\_defensive\\\_target\\\_band yalnız şu değerleri alır: low, medium, high,player\\\_on\\\_off\\\_dependency\\\_band yalnız şu değerleri alır: low, medium, high
player\\\_clutch\\\_decision\\\_band yalnız şu değerleri alır: controlled, chaotic,player\\\_referee\\\_adaptation\\\_band yalnız şu değerleri alır: strong, normal, weak
data\\\_quality\\\_badge,data\\\_quality\\\_badge yalnız şu değerleri alır: normal, incomplete, low, inactive text


FAZ-28 GANYAN BÖLÜM BAŞLANGICI-
GANYAN — KİLİTLİ RAF SÖZLEŞMESİ + ANALİST EĞİTİM KİTAPÇIĞI + NAVİGASYON + ORTAK ETİKET SÖZLÜĞÜ + PROFİL/ÖRÜNTÜ OMURGA + ÖRÜNTÜ DUVARI + ŞART PAKETİ + DENETİM AKIŞI + TAKVİM RAFI + KOŞU GÜNÜ KOMPOZİSYON KÜTÜĞÜ + KÜTÜPHANECİ KARTI + KİMLİK STANDARTLARI (NİHAİ KİLİTLİ BİRLEŞİK METİN v1.2) | 
Bu ganyan bölümü yalnız at yarışı ganyan içindir, futbol doğasıyla karıştırılamaz, basketbol doğasıyla karıştırılamaz, bu blok kupon üretmez, tahmin üretmez, banko üretmez, yönlendirme yapmaz, bu blok raf-kütüphane sisteminin veri standardını ve deterministik navigasyonunu kilitler, bu blok değiştirilemez, yorumlanamaz, parça parça bölünemez, aynı anlamı taşıyan ikinci bir blok açılamaz, isimleri değiştirilemez, etiketler yeniden adlandırılamaz, amaç Analist’in kanıt zincirini kırmadan veri raflarını eksiksiz büyütmek ve şehir kütüphanesi mantığında arama/filtreleme yapılabilir yapı kurmaktır, sistem deterministiktir, etiket uydurulmaz, eşleşmeyen veri zorla map edilmez, eksik veri otomatik tamamlanmaz, data\\\_quality\\\_badge incomplete veya low zorunludur, kütüphaneci analiz yapmaz değer notu vermez klasman notu vermez hüküm cümlesi kurmaz yalnız ham kaydı tekilleştirir sözlüğe map eder eksikleri boş bırakır, Analist kesinlik dili kullanamaz “kesin kazanır, banko, tek” yazamaz, yalnız ölçüm dili üretir ve “uyumsuz” kelimesini kullanmaz, yalnız “pist uyumu düşük, mesafe uyumu düşük, binici uyumu düşük” gibi yumuşak ölçüm diliyle konuşur, “hüküm” tanımı sabittir: kesin sonuç iddiası, kazanç iddiası, banko/tek/favori kesinliği üreten dildir, “etiket/ölçüm” tanımı sabittir: bant, risk seviyesi, profil seviyesi, eksik veri işareti ve ölçümsel tespit bilgisidir, olumsuz dil kaçakları serbest değildir; “olmaz, tutmaz, çöp, sil, berbat” yerine yalnız ölçüm dili kullanılır ve risk/uyum bandına çevrilir, sistem “tezgâh/manipülasyon/şike/mafya/dış el” gibi suçlayıcı hüküm üretmez; yalnız geçmiş tekrar ve şart bağımlılığı üzerinden “olağan bant sapması” işaretler, tek olayla hüküm kurmaz, tekrar ve şart bağımlılığı arar

ÇALIŞMA AKIŞI (KİLİT SIRA) | 
Sıra sabittir ve değiştirilemez: bülten → kimlik bağlama → karttan temel not → şart paketi → koşuya uyumlu not + etiket kırılımı → iç sıralama → örüntü duvarıyla tutarlılık kontrolü, bu akışın hiçbir yerinde “tahmin” yoktur, önce ölçüm vardır sonra koşula göre uyarlama vardır en sonda tutarlılık denetimi vardır, bülten çıktısı korunur bülten sıralaması bozulmadan yanına sistem çıktısı yazılabilir, sistem ayrıca kendi iç denetimi için “iç sıralama” üretir ve bu iç sıralama uygulama içinde saklanır, halka açık dil olarak kullanılmaz, kupon dili değildir,

ŞART PAKETİ (KİLİT) | 
“Şart paketi oturdu, karar verdik” yaklaşımı yasaktır, şart paketi tek başına karar değildir, tek katmana yaslanan sistem yanlış güven üretir, bu sistemde tek bir şart paketi yoktur; şart paketi hem katmanlı hem bileşenli olarak okunur, ŞART PAKETİ 3 KATMAN KİLİDİ (MAKRO-MİKRO AYRIMI): At şart paketi (atın kartından gelen yatkınlıklar ve kırılganlıklar: pist, mesafe, kilo, jokey, kalabalık, kulvar, ekipman, bitiriş gücü, istikrar, mücadele mührü), Ayak şart paketi (o gün koşunun somut şartları: hipodrom, zemin, pist durumu, mesafe, sınıf/handikap, at sayısı, ödül bandı, beklenen tempo), Kupon günü şart paketi (altılı gününün toplam dokusu: gün stabil mi dalgalı mı, sürpriz riski yüksek mi, ödül bandı dağılımı, favori yoğunluğu, ilk 4 kesit profili), sistem karar vermez bu üç paketi çarpıştırır; at paketi ayağa oturuyor ama gün dokusu dalgalıysa güven bandı düşer, at paketi zayıf ama ayak paketi tam uyumluysa koşuya uyumlu değer notu yükselir, gün paketi sürpriz ağırlıklıysa Analist etiket kırılımlarına daha sert bakar tek sebeple kimseyi yukarı çekmez, ŞART PAKETİ 4 BİLEŞEN KİLİDİ (VARLIK PAKETLERİ + ORTAM PAKETİ): At şart paketi + Jokey şart paketi + Patron şart paketi + Ayak/Ortam şart paketi (hipodrom + zemin + pist durumu + mesafe + sınıf + kalabalık + ödül bandı + beklenen tempo), Patron paketi tek başına hüküm değildir ancak masadan kalkmaz; diğer paketlerle birlikte tutarlıysa ağırlık kazanır tutarlı değilse alarm üretir.

DEĞER NOTU (KİLİT) | 
Bu sistemin tek sayısal çıktısı “Değer Notu (10x)”dur, bu not bir öneri değildir bir ölçümdür, değer notu yanında kırılım etiketi zorunludur ve etiket dili yumuşak ölçüm dilinde kalır, “uyumsuz” kelimesi yasaktır, örnek etiket dili: pist uyumu düşük, mesafe uyumu düşük, jokey uyumu düşük, kilo uyumu düşük, kalabalık uyumu düşük, kulvar uyumu düşük, ekipman uyumu düşük, start stabilitesi düşük, finiş stabilitesi düşük, bu değer notları geçmiş koşu örgüsünden türetilmiş profil ölçümüdür; bugünkü ve sonraki koşular için sonuç taahhüdü değildir, bugünü anlatmaz geçmişin kayıtlı davranış izini gösterir, DEĞER NOTU (10-1) — NİHAİ ÖNCELİK SIRASI (KİLİT): Pist uyumu, Mesafe uyumu, Kilo uyumu, Jokey uyumu, Ekipman/Aksesuar uyumu, Kalabalık uyumu, Kulvar uyumu, Bitiriş süresi/rakibe göre normalize performans, İstikrar bandı, Mücadeleci karakter mührü; mücadeleci karakter mührü yalnız 10/10 için zorunludur, her at 9’a kadar çıkabilir 10 için karakter mührü gerekir.

KLASMAN NOTU ÜRETİMİ (KİLİT) | 
Klasman Notu resmi yarış sınıfı içinde 10–1 bandında uzun vadeli profil seviyesidir, değer notu değildir kupon dili değildir tek koşu sonucu üretmez, çoklu kanıt birleşimiyle verilir tek veriyle karar verilmez, rakip sınıfı dayanımı mesafe esnekliği pist tipi/pist durumu esnekliği kilo dayanımı/hassasiyeti kalabalık dayanımı start stabilitesi enerji dağılımı/sprint profili finiş stabilitesi/tekrar edebilirlik jokey bağımlılığı/esnekliği mücadele iştahı/y yarış bırakmama disiplinine göre okunur, format sabittir “Grup 2/8”, değer notu formatına çevrilemez.

KOŞU GÜNÜ DEĞER NOTU (KİLİT) | 
Yalnız o günkü koşu şartlarında atın ayağa oturuş uygunluğunu 10 üzerinden ölçer, klasman notundan ayrıdır, tek veriyle yükselmez, kanıt zinciri tamamlanmadan yükseltilmez, çıktı dili sabittir “Değer Notu: 10 üzerinden X”, kupon dili değildir banko dili değildir kesinlik iddiası değildir, veri yoksa incomplete/low ile güvenli kalır.

JOKEY PUAN AYRIMI (KİLİT) | 
Jokey Klasman Notu J-1…J-10 uzun vadeli sürüş disiplinidir değer notu değildir, Jokey Koşu Günü Uygunluk Notu yalnız o günkü eşleşmenin 10 üzerinden uygunluğudur, tek veriyle yükseltilmez, jokey değerlendirmesi atla eşleşme ve atın jokeye bağımlılığıyla birlikte okunur.

PATRON/SAHİP PUAN AYRIMI (KİLİT) | 
Patron Profil Notu P-1…P-10 uzun vadeli katılım ve dağılım karakteridir güç/otorite notu değildir, Patron Koşu Günü Dağılım Etkisi yalnız o günün koşusunda 10 üzerinden dağılım ağırlığıdır suçlama değildir dış el/şike/mafya dili yasaktır, Patron etkisi atın koşu günü değer notunu override edemez yalnız eşitlik kırıcı ikinci katmandır.

ÖRÜNTÜ DUVARI (KİLİT) | 
Örüntü duvarı ham kayıt değildir, ham rafların üzerinde çalışan tekrar eden imzaları tekilleştiren ve geçmişten geleceğe okunur hale getiren üst katmandır, kupon dili konuşmaz tahmin üretmez yalnız bant ve imza taşır, Analist’in mikro kararlarını devirmez mikro kararların üstüne “kapsama genişliği” ve “sapma alarmı” bindirir, append-only çalışır revizyon eklenir eski silinmez geriye dönük iz kaybolmaz.

MAKRO DENETİM — MİKRO KARAR (KİLİT) | 
Ayak ayak yapılan okuma mikro karardır: at+jokey+patron ve koşu şartında kim doğal avantaj topluyor kim nereden kırılıyor okunur, altılı bütününe bakmak makro denetimdir: gün stabil mi dalgalı mı sürpriz riski yükseliyor mu favori yoğunluğu nasıl ödül bandı dağılımı nasıl geçmişte benzer günlerde sapma olmuş mu okunur, makro denetim ayak kararını sıfırdan yazmaz ayak kararının güven bandını ayarlar sapma günlerinde kapsama genişliğini belirler.

SAPMA GÜNLERİNDE ANALİSTİN ÜST GÖREVİ (KİLİT) | 
Makro örüntü “bu at gelir” dedirtmez, “bu ayakta kapsama dar mı normal mi geniş mi olmalı”yı belirler, sistem ayak başına “Kapsama Önerisi Bandı” üretir: dar/normal/geniş, dayanak takvim örüntüsü ödül bandı patron döngüsü imzalarıdır, rastgele genişleme yapılmaz, sapma günlerinde gelen kesitlerin dağılımı izlenir sapma 1–2’de mi 3–4’te mi görülüyor bilgisi kapsama bandının sınırını belirler.

KESİT STANDARDI (KİLİT) | 
Örüntü duvarında kesit standardı “ilk 4” üzerinden kilitlenmiştir, kesit örüntüleri duvara asılırken bağlam alanları sabittir: zaman/takvim, hipodrom, jokey havuzu, patron havuzu, ödül bandı; eksik bırakılamaz, bazıları var bazıları yok karışıklığına izin verilmez.

TAKVİM RAFI (KİLİT) | 
Örüntü yakalamak için takvim rafı zorunludur, üç seviyede kırılır: yıl+ay, haftanın günü, ayın haftası; dönemsel/haftalık/periyodik döngüler aynı anda yakalanır, kart çoğaltmak için değil aynı kartı farklı raf adreslerinden referanslamak için kullanılır.

KOŞU GÜNÜ KOMPOZİSYON ÖRÜNTÜ KARTI (KİLİT) | 
Aynı gün koşulan tüm ayakların gün dokusunu tek bakışta gösteren ölçüm kartıdır, tahmin üretmez kupon dili konuşmaz hüküm kurmaz, zorunlu alanlar: günün güç düzeyi bandı, saha kalitesi bandı, favori yoğunluğu bandı, tempo baskısı bandı, sürpriz riski bandı, gün içi dalgalanma bandı, tekilleştirilir append-only revizyonla güncellenir, aynı gün kimliği üzerinden takvim rafına dağıtılır: yıl/ay, haftanın günü, ayın haftası zorunludur.

JOKEY ÖRÜNTÜ KARTI (KİLİT BANT SETİ) | İstikrar bandı, Taşıma bandı (1–2–3–4 kesit taşıma), Kalabalık yönetim bandı (çok atlı/normal), Tempo bandı (yüksek/normal/düşük), Uyum bandı (bu koşul örgüsüne uyum yüksek/normal/düşük), tempo ve uyum aynı banda sıkıştırılmaz tempo ayrı eksen uyum ayrı eksendir.

PATRON ÖRÜNTÜ KARTI (KİLİT BANT SETİ) | 
Katılım bandı, Hedef bandı, Taşıma bandı (1–2–3–4), Jokey tercih imzası, İstikrar bandı, Kesit eğilimi bandı (1’e mi 2–3’e mi 4’e mi yığılır), iddia üretmez yalnız dağılım haritası taşır.

PİYASA/ORAN ÖRÜNTÜ KARTI (KİLİT BANT SETİ) | 
Oran görünürlük bandı, Kapanış oranı bandı, Sabitlenen oran bandı, Oran–kesit eşleşmesi bandı, suçlama dili üretmez yalnız ölçüm bandı taşır.

ANTRENÖR/TRAINER ÖRÜNTÜ KARTI (OPSİYONEL BEST-EFFORT) | 
Çekirdek 6 karta dahil değildir, best-effort ek karttır, veri gelirse işlenir veri gelmezse boş kalır ve karar akışını etkilemez sistemi kilitlemez.

ÖDÜL BANDI (KİLİT / ZAMANDAN BAĞIMSIZ / KIYAFET ÖLÇEĞİ) | 
0–50.000: XS, 50.001–100.000: S, 100.001–150.000: M, 150.001–200.000: L, 200.001–300.000: XL, 300.001–500.000: XXL, 500.001–1.000.000: 3XL, 1.000.001+: 4XL, veri yoksa band boş kalır.

MİKRO SEGMENT STANDARDI (KİLİT) | 
Sistem son 600/400/200 ana bandlarını taşır, ayrıca 150/100/50 bandı da tutulur, finişte “pota bandı” kırılması ayrıca işaretlenir.

FAZ-29
GANYAN ANALİST EĞİTİM KİTAPÇIĞI (SORU OMURGA) — KİLİTLİ | 
Bu kitapçık Analist’in ezbersiz doğru soruyu sormasını ve kanıt zinciri kurmasını zorunlu kılar, her soru geçmiş veriyle doğrulanır, hiçbir soru tek başına hüküm kurdurmaz, hiçbir cevap tek başına karar vermez, kupon dili değildir tahmin dili değildir yalnız ölçüm ve kanıt toplama disiplinidir, üretilen tüm çıktılar etiketlenebilir alanlara bağlanır, kütüphaneci alan dışına çıkamaz veri yoksa alan boş kalır, at kartı bağlam zorunluları: race\\\_date\\\_utc track\\\_name surface\\\_type surface\\\_condition distance\\\_m race\\\_class\\\_official race\\\_no horse\\\_id (eksikse data\\\_quality\\\_badge incomplete), resmi sınıf+klasman notu formatı “Grup 2/8” (değer notu değildir), koşu günü değer notu formatı “Değer Notu: 10 üzerinden X” (kupon dili değildir), zemin-mesafe-kilo üçlüsü ayrılmaz, aynı mesafe+benzer zeminde farklı kilo ile bitiriş süresi taşıma kapasitesini gösterir, zemin bandı çim/kum/sentetik ve pist durumu hızlı/normal/ağır/çamur, mesafe bantları kısa/orta/uzun ve 1200–1400 ile 2000–2400 ayrı profildir, enerji dağılımı start-çıkış ilk bölüm orta bölüm viraj son600 son400 son200 finiş segmentleriyle okunur, start refleksi hızlı/normal/geç/oyalanma ve hızlı çıkış her zaman iyi değildir, kalabalık toleransı grup içinde rahat/sıkışma/grup dışına kaçış/içe kapanma/dışa açılma, kulvar iç/orta/dış tek başına hüküm değildir kalabalık+trafikle okunur, stil önde kaçan/pres yapan/bekleyen/sprintçi/tempo kırıcı, tempo uyumu yüksek tempoda stabil/erken biten düşük tempoda patlayan/etkisiz, viraj davranışı akışkan/balans bozan/yol arayan/sıkışan, finiş stabilitesi finişte diri/düşen/tekrar açılan, mücadele karakteri yarış iştahı yüksek/düşük mücadeleyi bırakmayan/kolay vazgeçen, stabilite bandı stabil/dalgalı/kırılgan, ekipman gözlük/dilbağı/kulaklık ayrı kaydedilir ekipman değişimi tek başına sebep ilan edilmez, rakip normalize aynı sınıf/üst sınıf/alt sınıf, form düşüşü aynı mesafe+benzer zemin+benzer sınıfta süre kötüleşmesi ana kanıt tek yarışla hüküm olmaz tekrar aranır, jokey etkisi jokey-at uyumu ve jokeyin genel formu ile ayrıştırılır, trafik kırığı bayrakları zorunludur (yol buldu/yol bulamadı/sıkıştı/açıldı/erken çıkış/geç çıkış) trafik varsa süre bozulması doğrudan form düşüşü sayılmaz, sprint tetikleme son600/son400/son200 açamayan bantları, erken yüklenme riski erken yaktı/kontrollü yaktı/geç yaktı, beklenen-çıkan sapma beklenen bant içinde/üstü/altı, öngörülebilirlik riski düşük/normal/yüksek, hassasiyet iç kulvar toleransı düşük/dış kulvar toleransı düşük/grup toleransı düşük/ekipman toleransı düşük, hipodrom uyumu yüksek/normal/düşük, koşu sıklığı toleransı kısa aralıkta tolerans yüksek/düşük, kapanış hızlanması son200 güçlü/zayıf, baskı altında reaksiyon toparlıyor/dağılıyor/kaçıyor, rakip geçtiğinde cevap veriyor/veremiyor/geç tepki, düzlüğe çıkış ön grupta/orta grupta/geride, baş-boy farkı tek başına kalite sayılmaz sınıf+zeminle normalize edilir, saha dışı veri yoksa padok/yürüyüş boş bırakılır data\\\_quality\\\_badge incomplete olur hüküm üretilmez, hedef koşu varsayımı hüküm değildir yalnız tekrar eden kasıtlı tutma izleri varsa “olası hazırlık davranışı” etiketi, tek potansiyeli yalnız tam kanıt zinciri sonrası yazılır, yorum yasağı kesindir “kesin kazanır banko tek” yazılamaz veri eksikse “anomali yok” denemez yalnız eksik yazılır.

GANYAN KÜTÜPHANE NAVİGASYONU (RAF SİSTEMİ) — KİLİTLİ | 
Bu sistem şehir kütüphanesi mantığıyla çalışır, her veri raflara ayrılır raflar arası veri karışmaz, her kayıt deterministik şekilde aynı raflara iner, etiketler tekilleştirilir isim değiştirilmez yeni etiket uydurulmaz aynı anlama gelen ikinci etiket açılmaz, veri yoksa boş bırakılır tahminle doldurulmaz, RAF alanları ham kayıt raflarıdır, Kimlik Kartları türetilmiş raflardır, Analist çıktısı çalışma rafıdır, bu üçü birbirine karıştırılamaz, RAF NAVİGASYONU (RAF-0…RAF-13): RAF-0 bağlayıcılık kilidi ve veri eksikse güvenli kalma, RAF-1 koşu kimliği ve bağlam, RAF-2 varlık kimlikleri (at-jokey-patron), RAF-3 koşu içi metrikler ve splitler, RAF-4 trafik ve trip olayları, RAF-5 start ve yerleşim, RAF-6 kalabalık ve kulvar davranışı, RAF-7 pist ve mesafe tercihleri, RAF-8 form döngüsü ve fitness, RAF-9 jokey sürüş karakteri ve eşleşme, RAF-10 patron dağılım ve katılım haritası, RAF-11 koşu günü kompozisyonu, RAF-12 piyasa ve oran hareketi, RAF-13 veri kalitesi ve mapleme.

RAF-0 SİSTEM BAĞLAYICILIĞI | Kurallar değiştirilemez, veri eksikse sistem güvenli kalır, eksik veri normal sayılmaz otomatik tamamlanmaz, karar üretimi yalnız kanıt birikimiyle yapılır, kesin kazanır banko tek dili üretilmez, ölçüm dili kullanılır, “uyumsuz” kelimesi kullanılmaz yumuşak ölçüm dili zorunludur.

RAF-1 KOŞU KİMLİĞİ VE BAĞLAMI | 
race\\\_id ana anahtardır, race\\\_date\\\_utc track\\\_name race\\\_no distance\\\_m surface\\\_type surface\\\_condition field\\\_size race\\\_class\\\_official zorunludur, bunlardan biri eksikse data\\\_quality\\\_badge incomplete olur ve kayıt karar üretimine uygun sayılmaz.

RAF-2 VARLIK KİMLİKLERİ | 
horse\\\_id jockey\\\_id owner\\\_id tekilleştirilmiş ana anahtarlardır, aynı varlık farklı yazımlarla tekrar açılmaz, alias varsa alias alanına eklenir ana kimlik değiştirilmez, external id varsa ilgili external\\\_ids alanına eklenir yoksa boş bırakılır, eşleşmeyen entity unmapped kalır zorla map edilmez.

RAF-3 KOŞU İÇİ METRİKLER | 
split süreleri ve pozisyonları taşır, segmentler sabittir start-çıkış ilk bölüm orta bölüm viraj son600 son400 son200 finiş, segment süresi yoksa segment notu üretilmez yalnız gelen splitler işlenir gelmeyen veri tahmin edilmez.

RAF-4 TRAFİK VE TRİP OLAYLARI | 
yalnız olay bayraklarını işler neden-sonuç açıklaması eklemez, trafik kırığı varsa süre bozulması doğrudan form düşüşü sayılmaz bu yalnız veri notudur.

RAF-5 START VE YERLEŞİM | 
start reaksiyonu ve ilk yerleşim disiplinini taşır, hızlı çıkış her zaman iyi değildir uzun mesafede erken bitme riskidir, lead alınması/pres/bekleme bayrakları burada tutulur.

RAF-6 KALABALIK VE KULVAR DAVRANIŞI | 
grup içinde rahatlık/sıkışma/grup dışına kaçış/içe kapanma/dışa açılma bantları, kulvar tek başına hüküm değildir kalabalık toleransı ve trafik kırığı ile birlikte okunur.

RAF-7 PİST VE MESAFE TERCİHLERİ | 
çim/kum/sentetik ve pist durumu bandı, zemin yorumu tek yarışla yapılmaz, mesafe bantları kısa-orta-uzun, 1200–1400 ile 2000–2400 ayrı profildir.

RAF-8 FORM DÖNGÜSÜ VE FİTNES | 
form\\\_cycle\\\_stage ve form\\\_trend alanları, form düşüşü tek cümleyle yazılmaz yalnız tekrar ve şart bağımlılığıyla işaretlenir, layoff\\\_days ve fitness\\\_band burada tutulur.

RAF-9 JOKEY SÜRÜŞ KARAKTERİ VE EŞLEŞME | 
jokeyin stilini tempo yönetimini finiş zamanlamasını kalabalık içinde yol bulmasını taşır, jokey iyi ifadesi tek başına hüküm değildir atla eşleşme ve atın jokeye bağımlılığı ile birlikte okunur.

RAF-10 PATRON DAĞILIM VE KATILIM HARİTASI | 
ödül bandı katılım sıklığı kazanım periyot dağılımı uzun süre kazanmama kırılması strateji yayılımı jokey tercih korelasyonu gibi örüntüler, suçlama üretmez dış el şike mafya yasaktır yalnız istatistiksel dağılım haritası üretir.

RAF-11 KOŞU GÜNÜ KOMPOZİSYONU | 
ayak içi alan gücü/alan kalitesi/favori yoğunluğu/tempo baskısı/sürpriz riski/yarış varyansı bantları, tek başına karar değildir kanıt zincirini destekleyen ikinci katmandır.

RAF-12 PİYASA VE ORAN HAREKETİ | 
public\\\_rank odds\\\_open odds\\\_close odds\\\_movement bandları, oran hareketi tek başına hüküm değildir yalnız kanıt hattına eklenir.

RAF-13 VERİ KALİTESİ VE MAPLEME | 
source\\\_name source\\\_timestamp\\\_utc mapping\\\_status unmapped\\\_entities validation\\\_errors missing\\\_fields data\\\_quality\\\_badge, veri eksikse badge incomplete veya low olur, veri eksikliği normal sayılmaz sistem güvenli kalır.

FAZ-30
ORTAK ETİKET SÖZLÜĞÜ (KİLİTLİ) | 
Kütüphaneci bu sözlük dışına çıkamaz, isim değiştiremez yeni etiket açamaz aynı anlama gelen ikinci etiket açamaz, eksik veri standardı sabittir: boolean null, numeric null, string null, list boş liste \\\[], missing\\\_fields her zaman liste, tahminle doldurma yasaktır, sözlük alan seti: race\\\_id, race\\\_date\\\_local, race\\\_date\\\_utc, track\\\_name, city, country, season\\\_id, meeting\\\_id, race\\\_no, race\\\_class\\\_official, race\\\_type, distance\\\_m, surface\\\_type, surface\\\_condition, rail\\\_position, weather, temperature\\\_c, humidity\\\_pct, wind\\\_kmh, wind\\\_dir, start\\\_time\\\_local, start\\\_time\\\_utc, starting\\\_method, field\\\_size, scratchings\\\_count, race\\\_purse\\\_total, race\\\_purse\\\_breakdown, handicap\\\_type, weight\\\_handicap\\\_rule, pace\\\_projection, race\\\_shape\\\_projection, draw\\\_bias\\\_note, horse\\\_id, horse\\\_name, horse\\\_age, horse\\\_sex, horse\\\_color, sire\\\_name, dam\\\_name, owner\\\_id, owner\\\_name, trainer\\\_id, trainer\\\_name, jockey\\\_id, jockey\\\_name, stable\\\_id, stable\\\_name, breeder\\\_name, horse\\\_external\\\_ids, horse\\\_aliases, jockey\\\_external\\\_ids, jockey\\\_aliases, owner\\\_external\\\_ids, owner\\\_aliases, gate\\\_no, draw\\\_position, assigned\\\_weight\\\_kg, carried\\\_weight\\\_kg, weight\\\_change\\\_from\\\_last\\\_kg, jockey\\\_change\\\_flag, equipment\\\_blinkers, equipment\\\_visors, equipment\\\_tongue\\\_tie, equipment\\\_shadow\\\_roll, equipment\\\_hood, equipment\\\_earplugs, equipment\\\_bar\\\_shoes, equipment\\\_special\\\_notes, shoeing\\\_notes, finish\\\_pos, finish\\\_time, finish\\\_time\\\_sec, win\\\_margin\\\_len, beaten\\\_margin\\\_len, last\\\_600m\\\_sec, last\\\_400m\\\_sec, last\\\_200m\\\_sec, first\\\_200m\\\_sec, first\\\_400m\\\_sec, first\\\_600m\\\_sec, mid\\\_race\\\_position, early\\\_position, final\\\_turn\\\_position, late\\\_run\\\_strength, stride\\\_quality\\\_note, kick\\\_timing\\\_note, pace\\\_band, early\\\_speed\\\_band, mid\\\_speed\\\_band, late\\\_speed\\\_band, energy\\\_distribution\\\_profile, closing\\\_section\\\_profile, acceleration\\\_profile, deceleration\\\_profile, sustained\\\_speed\\\_profile, trip\\\_in\\\_running, traffic\\\_events, wide\\\_run\\\_meters, boxed\\\_in\\\_flag, checked\\\_flag, bumped\\\_flag, forced\\\_wide\\\_flag, held\\\_up\\\_flag, clear\\\_run\\\_flag, rail\\\_run\\\_flag, start\\\_reaction\\\_band, break\\\_quality, gate\\\_behavior\\\_note, early\\\_settling\\\_band, lead\\\_taken\\\_flag, stalking\\\_flag, midpack\\\_flag, backmarker\\\_flag, crowd\\\_tolerance\\\_band, pack\\\_running\\\_preference, inside\\\_running\\\_preference, outside\\\_running\\\_preference, overtaking\\\_behavior\\\_band, pressure\\\_response\\\_band, head\\\_to\\\_head\\\_behavior\\\_band, surface\\\_preference\\\_band, distance\\\_preference\\\_band, track\\\_preference\\\_band, condition\\\_preference\\\_band, slope\\\_preference\\\_band, form\\\_cycle\\\_stage, form\\\_trend\\\_3, form\\\_trend\\\_5, peak\\\_form\\\_flag, decline\\\_form\\\_flag, rebound\\\_form\\\_flag, layoff\\\_days, fitness\\\_band, trial\\\_result\\\_note, jockey\\\_horse\\\_synergy\\\_band, horse\\\_jockey\\\_dependency\\\_band, jockey\\\_style\\\_band, jockey\\\_aggression\\\_band, jockey\\\_patience\\\_band, jockey\\\_closing\\\_skill\\\_band, jockey\\\_pace\\\_judgement\\\_band, jockey\\\_pressure\\\_management\\\_band, owner\\\_purse\\\_appetite\\\_band, owner\\\_frequency\\\_band, owner\\\_rotation\\\_band, owner\\\_targeting\\\_band, owner\\\_distribution\\\_pattern, owner\\\_repeat\\\_win\\\_pattern, owner\\\_long\\\_dry\\\_spell\\\_flag, composition\\\_strength\\\_band, field\\\_quality\\\_band, favorite\\\_density\\\_band, pace\\\_pressure\\\_density\\\_band, upset\\\_risk\\\_band, race\\\_variance\\\_band, public\\\_rank, public\\\_odds\\\_open, public\\\_odds\\\_close, public\\\_odds\\\_low, public\\\_odds\\\_high, odds\\\_movement\\\_band, late\\\_support\\\_flag, drifting\\\_flag, data\\\_quality\\\_badge, missing\\\_fields, source\\\_name, source\\\_timestamp\\\_utc, mapping\\\_status, unmapped\\\_entities, validation\\\_errors

KÜTÜPHANECİ KARTI (UYGULAMA TALİMATI) — KİLİTLİ | 
Kütüphaneci arşivleme terminalidir analiz yapmaz yorum yapmaz değer notu üretmez klasman notu üretmez hüküm kurmaz, her kayıt için önce koşu kimliğini kurar sonra varlık kimliklerini bağlar sonra koşu içi metrikleri işler sonra veri kalitesini işaretler, race\\\_id race\\\_date\\\_utc country track\\\_name race\\\_no distance\\\_m surface\\\_type surface\\\_condition field\\\_size race\\\_class\\\_official zorunludur eksikse data\\\_quality\\\_badge incomplete, horse\\\_id jockey\\\_id owner\\\_id tekilleştirilir external\\\_ids varsa eklenir yoksa boş bırakılır alias varsa eklenir ana kimlik değişmez, koşu içi metrikler yalnız kaynaktan geldiyse işlenir gelmeyen üretilmez, padok/yürüyüş yoksa boş bırakılır, trafik olaylarında yalnız bayrak işlenir açıklama eklenmez, missing\\\_fields source\\\_name source\\\_timestamp\\\_utc mapping\\\_status validation\\\_errors zorunludur, eksik alanlar doldurulmaz yalnız null/\\\[] standardıyla bırakılır tahmin yasaktır.

KİMLİK STANDARDI (KİLİT) | 
Tüm varlıklar benzersiz referans kimlikle tutulur, dış kaynak ID’leri bu kimliğin yerine geçmez yalnız external\\\_ids alanında saklanır, isimle arama yalnız alias üzerinden kimliğe bağlanır, alias sözlüğü yoksa eşleşmeyen isimler unmapped\\\_candidates rafına düşer sistem kırılmaz, kimlik kartı varlık peşinde taşınır ve profil geçmişten geleceğe varlık hayatı boyunca bu kartta birikir.

AT KİMLİK STANDARDI (KİLİT) | 
At kimliği sırası kilitlidir: Orijin → At Adı → Sahip → Yaş → Renk → Kayıt Tarihi (YYYY/MM/DD) → Otomatik Sayaç, otomatik sayaç 10.000’den başlar otomatik artar elle yazılmaz, dış kaynak ID’ler yerine geçmez yalnız external\\\_ids alanında tutulur.

AT KİMLİK KARTI (HORSE IDENTITY CARD) — KİLİTLİ ŞEMA | 
Horse kimlik kartı profil varlığıdır tek yarış sonucu değildir yorum değildir kupon değildir, horse\\\_id tek anahtar horse\\\_name görünen ad aliaslar ayrı tutulur aynı at farklı yazımla tekrar açılmaz, zorunlu alanlar: horse\\\_id horse\\\_name horse\\\_age horse\\\_sex horse\\\_color sire\\\_name dam\\\_name breeder\\\_name stable\\\_id stable\\\_name owner\\\_id\\\_current trainer\\\_id\\\_current horse\\\_external\\\_ids horse\\\_aliases, resmi sınıf+klasman notu alanı: race\\\_class\\\_official\\\_current ve class\\\_note\\\_current formatı “Grup 2/8” sabittir değer notu değildir, koşu günü değer notu kimlik kartında tutulmaz, profil çekirdeği: distance\\\_preference\\\_band surface\\\_preference\\\_band condition\\\_preference\\\_band weight\\\_sensitivity\\\_band start\\\_stability\\\_band crowd\\\_tolerance\\\_band traffic\\\_tolerance\\\_band energy\\\_distribution\\\_profile sprint\\\_trigger\\\_band finish\\\_stability\\\_band pace\\\_band style\\\_band volatility\\\_band, segment profilleri banttır first\\\_600m\\\_profile last\\\_600m\\\_profile last\\\_400m\\\_profile last\\\_200m\\\_profile tek yarışla sabitlenmez örüntüyle güncellenir, ekipman profilleri equipment\\\_blinkers\\\_profile equipment\\\_visors\\\_profile equipment\\\_tongue\\\_tie\\\_profile equipment\\\_hood\\\_profile equipment\\\_earplugs\\\_profile equipment\\\_bar\\\_shoes\\\_profile, jokey bağımlılığı horse\\\_jockey\\\_dependency\\\_band, jokey değişimi reaksiyonu jockey\\\_change\\\_reaction\\\_band, mücadele iştahı fight\\\_willingness\\\_band, tek potansiyeli yalnız tek\\\_potential\\\_band ve yalnız tam kanıt zinciri sonrası, kart her güncellemede profile\\\_version last\\\_update\\\_utc data\\\_quality\\\_badge taşır veri eksikse low/incomplete

JOKEY KİMLİK KARTI (JOCKEY IDENTITY CARD) — KİLİTLİ ŞEMA | 
Jokey kimlik kartı sürüş karakteri varlığıdır tek koşu sonucu değildir yorum değildir kupon değildir, zorunlu alanlar: 
jockey\\\_id jockey\\\_name jockey\\\_age\\\_band jockey\\\_weight\\\_band jockey\\\_external\\\_ids jockey\\\_aliases jockey\\\_agent\\\_or\\\_stable\\\_link, profil alanı jockey\\\_class\\\_note\\\_current “J-1…J-10” bandıdır değer notu değildir, çekirdek alanlar: jockey\\\_style\\\_band jockey\\\_aggression\\\_band jockey\\\_patience\\\_band jockey\\\_pace\\\_judgement\\\_band jockey\\\_closing\\\_skill\\\_band jockey\\\_pressure\\\_management\\\_band jockey\\\_lane\\\_choice\\\_band jockey\\\_inside\\\_skill\\\_band jockey\\\_outside\\\_skill\\\_band jockey\\\_pack\\\_navigation\\\_band jockey\\\_finish\\\_timing\\\_band, overdrive örüntüsü jockey\\\_overdrive\\\_band suçlama değildir, ödül davranışı jockey\\\_purse\\\_appetite\\\_band yargı değildir yalnız strateji/risk yoğunluğu profilidir, at eşleşmesi jockey\\\_horse\\\_synergy\\\_band ve synergy\\\_matrix\\\_by\\\_horse\\\_type, kısa dönem form jockey\\\_recent\\\_form\\\_band tek koşuyla hüküm olmaz, kart her güncellemede profile\\\_version last\\\_update\\\_utc data\\\_quality\\\_badge taşır veri eksikse low/incomplete

PATRON/SAHİP KİMLİK KARTI (OWNER IDENTITY CARD) — KİLİTLİ ŞEMA | 
Patron kimlik kartı katılım ve dağılım profili varlığıdır tek koşu sonucu değildir yorum değildir kupon değildir, suçlama üretmek için kullanılmaz yalnız ödül dağılım haritası ve katılım karakterini ölçer, zorunlu alanlar: 
owner\\\_id owner\\\_name owner\\\_external\\\_ids owner\\\_aliases stable\\\_id\\\_links trainer\\\_id\\\_links, profil alanı owner\\\_profile\\\_note\\\_current “P-1…P-10” bandıdır değer notu değildir, çekirdek alanlar: owner\\\_frequency\\\_band owner\\\_rotation\\\_band owner\\\_targeting\\\_band owner\\\_distribution\\\_pattern owner\\\_repeat\\\_win\\\_pattern owner\\\_long\\\_dry\\\_spell\\\_flag owner\\\_surface\\\_distance\\\_bias owner\\\_jockey\\\_preference\\\_map owner\\\_trainer\\\_preference\\\_map owner\\\_multi\\\_runner\\\_strategy\\\_band, owner\\\_purse\\\_appetite\\\_band ahlaki yargı değildir strateji yoğunluğudur, patron kartı dış el/şike/mafya dili üretmez sapma yalnız istatistiksel tekrar ve şart bağımlılığıyla işaretlenir hüküm üretilmez, koşu gününde patron etkisi gerekiyorsa yalnız koşu kartında “Patron Koşu Günü Dağılım Etkisi: 10 üzerinden X” olarak üretilir kimlik kartına yazılmaz, kart her güncellemede profile\\\_version last\\\_update\\\_utc data\\\_quality\\\_badge taşır veri eksikse low/incomplete

GANYAN — KÜTÜPHANE TEMELLİ PROFİL/ÖRÜNTÜ SİSTEMİ 
(İŞ PROMPTU / BAŞTAN SONA KİLİTLİ OMURGA) | 
Sen bir “Ganyan Profil ve Örüntü Motoru”sun, görev kupon önerisi yapmak değildir, sistem at yarışı ekosisteminde yalnız geçmiş veriden türetilen profil-kayıt-kütüphane düzeniyle çalışır, yeni yarış geldiğinde atın jokeyin patronun geçmiş performans örgüsüne göre değer üretir, çıktı yönlendirici dil içermez yalnız ölçüm diliyle Değer Notu (10x) ve kırılım etiketi üretir, ham veri eksik gelebilir isimler değişebilir sistem kırılmaz eşleşmeyen veri unmapped kalır zorla uydurulmaz, fuzzy-match/LLM isim uydurma yasaktır, kütüphaneler kilitlidir ve karıştırılamaz: Ham Veri Kütüphanesi, At Performans Kütüphanesi, Jokey Kütüphanesi, Patron Kütüphanesi, Ham Veri tek giriş kapısıdır tüm veri önce buraya iner standardize edilir etiketlenir sonra diğer kütüphanelere dağıtılır, diğer kütüphaneler ham veri tutmaz yalnız işlenmiş profil ve örüntü agregeleri tutar, her yarış günü aynı akış yeniden çalışır yeni yarış ham veri olarak iner aynı standartlarla etiketlenir profillere eklenir, hedef tek yarış tahmini değil geçmişten geleceğe büyüyen kalıcı profil duvarıdır geriye dönük tutarlılık korunur.

KOŞU GÜNÜ KOMPOZİSYON KÜTÜPHANESİ VE ALTILI KÜTÜĞÜ 
(KİLİTLİ ÇALIŞMA BLOĞU) | 
At/jokey/patron kütüphaneleri tek başına yeterli değildir, ganyan örüntüsü koşu gününde varlıkların nasıl bir araya geldiği ayakların nasıl dizildiği ve altılı bütününün nasıl bittiği ile görünür olur, bu nedenle sistem “koşu günü kompozisyonunu” ayrı bir varlık olarak kaydeder ve bu kayıt at/jokey/patron kartlarının içine karıştırılmaz, iki bülten kavramı kilitlenir: Koşu Öncesi Bülten (planlanan dizilim) ve Koşu Sonrası Doğal Bülten (bitmiş gerçeklik), sistem bu iki belgeyi tek kayıtta ezmez her ikisi ayrı kayıt olarak saklanır ve yalnız internal\\\_meeting\\\_id/internal\\\_race\\\_day\\\_id ile bağlanır, sistem günün tüm atlarını tek liste yapmaz her at kaydı zorunlu olarak bir ayak kimliğine bağlıdır ve bağlantı kaybolmaz, her koşu günü için ayak haritası deterministik üretilir ayakların iç yapısı ayrı alt kayıt alanıdır, altılı/ikili/üçlü sistem tarafından tahmin olarak değil yalnız gerçekleşmiş kombinasyon sonuç kaydı olarak ele alınır, sistem kupon üretmez kupon önermez bahis tavsiyesi vermez ancak resmi sonuçlardan altılı bütününün nasıl bittiğini ve ayak sıralamalarının altılı sonucuna nasıl yansıdığını kütüğe geçirir, tarih bilgisi omurgadır koşu günleri kronolojik taşınır farklı kütüphane çizgileri aynı tarih ekseninde buluşur, bu blok sadeleştirilemez ayak bağlantıları kaldırılamaz altılı sonuçları “gereksiz” diye çıkarılamaz ve bu kütük at/jokey/patron kartlarına karıştırılamaz.

UYGULAMA AÇILIŞ BİLGİLENDİRME METNİ (KİLİT) | 
Bu uygulama at yarışı ekosistemindeki geçmiş koşu verilerinden türetilen kayıtlar etiketler ve örüntü frekansları üzerinden çalışır, üretilen çıktılar at jokey hipodrom koşu şartları ve ödül bandı gibi bileşenlerin geçmişte nasıl tekrar ettiğini görünür kılar, bu veriler geçmişin haritasıdır bugün için garanti kesinlik veya sonuç iddiası üretmez, uygulama kupon dili kullanmaz ve herhangi bir sonuç yönlendirmesi yapmaz, sunulan değer notları yalnız belirli koşu şartlarında geçmiş performans örgüsünün ölçümsel karşılığını ifade eder, at yarışı canlı bir dinamiktir atın/jokeyin anlık fiziksel durumu psikolojisi yarış içi trafik ve koşu akışı sonucu belirgin şekilde değiştirebilir, burada görülen ölçümler nihai karar değildir karar sürecini daha bilinçli ve veri temelli kurmaya yardımcı çerçevedir, bu değer notları geçmiş koşu örgüsünden türetilmiş profil ölçümüdür bugünkü ve sonraki koşular için sonuç taahhüdü değildir bugünü anlatmaz geçmişin kayıtlı davranış izini gösterir.
KİLİT BEYANI | Bu metin “GANYAN — Nihai Kilitli Birleşik Metin v1.2” olarak kilitlenmiştir, yeniden yazılmaz parçalanmaz sadeleştirilmez anlamı bozulmaz.


FAZ-38
GANYAN — KİLİTLİ RAF SÖZLEŞMESİ + ANALİST EĞİTİM KİTAPÇIĞI + NAVİGASYON + ORTAK ETİKET SÖZLÜĞÜ + PROFİL/ÖRÜNTÜ OMURGA + ÖRÜNTÜ DUVARI + ŞART PAKETİ + DENETİM AKIŞI + TAKVİM RAFI + KOŞU GÜNÜ KOMPOZİSYON KÜTÜĞÜ + KÜTÜPHANECİ KARTI + KİMLİK STANDARTLARI (NİHAİ KİLİTLİ BİRLEŞİK METİN v1.2) |
Bu ganyan bölümü yalnız at yarışı ganyan içindir, futbol doğasıyla karıştırılamaz, basketbol doğasıyla karıştırılamaz, bu blok kupon üretmez, tahmin üretmez, banko üretmez, yönlendirme yapmaz, bu blok raf-kütüphane sisteminin veri standardını ve deterministik navigasyonunu kilitler, bu blok değiştirilemez, yorumlanamaz, parça parça bölünemez, aynı anlamı taşıyan ikinci bir blok açılamaz, isimleri değiştirilemez, etiketler yeniden adlandırılamaz, amaç Analist’in kanıt zincirini kırmadan veri raflarını eksiksiz büyütmek ve şehir kütüphanesi mantığında arama/filtreleme yapılabilir yapı kurmaktır, sistem deterministiktir, etiket uydurulmaz, eşleşmeyen veri zorla map edilmez, eksik veri otomatik tamamlanmaz, data\\\_quality\\\_badge incomplete veya low zorunludur, kütüphaneci analiz yapmaz değer notu vermez klasman notu vermez hüküm cümlesi kurmaz yalnız ham kaydı tekilleştirir sözlüğe map eder eksikleri boş bırakır, Analist kesinlik dili kullanamaz “kesin kazanır, banko, tek” yazamaz, yalnız ölçüm dili üretir ve “uyumsuz” kelimesini kullanmaz, yalnız “pist uyumu düşük, mesafe uyumu düşük, binici uyumu düşük” gibi yumuşak ölçüm diliyle konuşur, “hüküm” tanımı sabittir: kesin sonuç iddiası, kazanç iddiası, banko/tek/favori kesinliği üreten dildir, “etiket/ölçüm” tanımı sabittir: bant, risk seviyesi, profil seviyesi, eksik veri işareti ve ölçümsel tespit bilgisidir, olumsuz dil kaçakları serbest değildir; “olmaz, tutmaz, çöp, sil, berbat” yerine yalnız ölçüm dili kullanılır ve risk/uyum bandına çevrilir, sistem “tezgâh/manipülasyon/şike/mafya/dış el” gibi suçlayıcı hüküm üretmez; yalnız geçmiş tekrar ve şart bağımlılığı üzerinden “olağan bant sapması” işaretler, tek olayla hüküm kurmaz, tekrar ve şart bağımlılığı arar

ÇALIŞMA AKIŞI (KİLİT SIRA) |
Sıra sabittir ve değiştirilemez: bülten → kimlik bağlama → karttan temel not → şart paketi → koşuya uyumlu not + etiket kırılımı → iç sıralama → örüntü duvarıyla tutarlılık kontrolü, bu akışın hiçbir yerinde “tahmin” yoktur, önce ölçüm vardır sonra koşula göre uyarlama vardır en sonda tutarlılık denetimi vardır, bülten çıktısı korunur bülten sıralaması bozulmadan yanına sistem çıktısı yazılabilir, sistem ayrıca kendi iç denetimi için “iç sıralama” üretir ve bu iç sıralama uygulama içinde saklanır, halka açık dil olarak kullanılmaz, kupon dili değildir

ŞART PAKETİ (KİLİT) |
“Şart paketi oturdu, karar verdik” yaklaşımı yasaktır, şart paketi tek başına karar değildir, tek katmana yaslanan sistem yanlış güven üretir, bu sistemde tek bir şart paketi yoktur; şart paketi hem katmanlı hem bileşenli olarak okunur, ŞART PAKETİ 3 KATMAN KİLİDİ (MAKRO-MİKRO AYRIMI): At şart paketi (atın kartından gelen yatkınlıklar ve kırılganlıklar: pist, mesafe, kilo, jokey, kalabalık, kulvar, ekipman, bitiriş gücü, istikrar, mücadele mührü), Ayak şart paketi (o gün koşunun somut şartları: hipodrom, zemin, pist durumu, mesafe, sınıf/handikap, at sayısı, ödül bandı, beklenen tempo), Kupon günü şart paketi (altılı gününün toplam dokusu: gün stabil mi dalgalı mı, sürpriz riski yüksek mi, ödül bandı dağılımı, favori yoğunluğu, ilk 4 kesit profili), sistem karar vermez bu üç paketi çarpıştırır; at paketi ayağa oturuyor ama gün dokusu dalgalıysa güven bandı düşer, at paketi zayıf ama ayak paketi tam uyumluysa koşuya uyumlu değer notu yükselir, gün paketi sürpriz ağırlıklıysa Analist etiket kırılımlarına daha sert bakar tek sebeple kimseyi yukarı çekmez, ŞART PAKETİ 4 BİLEŞEN KİLİDİ (VARLIK PAKETLERİ + ORTAM PAKETİ): At şart paketi + Jokey şart paketi + Patron şart paketi + Ayak/Ortam şart paketi (hipodrom + zemin + pist durumu + mesafe + sınıf + kalabalık + ödül bandı + beklenen tempo), Patron paketi tek başına hüküm değildir ancak masadan kalkmaz; diğer paketlerle birlikte tutarlıysa ağırlık kazanır tutarlı değilse alarm üretir.

DEĞER NOTU (KİLİT) |
Bu sistemin tek sayısal çıktısı “Değer Notu (10x)”dur, bu not bir öneri değildir bir ölçümdür, değer notu yanında kırılım etiketi zorunludur ve etiket dili yumuşak ölçüm dilinde kalır, “uyumsuz” kelimesi yasaktır, örnek etiket dili: pist uyumu düşük, mesafe uyumu düşük, jokey uyumu düşük, kilo uyumu düşük, kalabalık uyumu düşük, kulvar uyumu düşük, ekipman uyumu düşük, start stabilitesi düşük, finiş stabilitesi düşük, bu değer notları geçmiş koşu örgüsünden türetilmiş profil ölçümüdür; bugünkü ve sonraki koşular için sonuç taahhüdü değildir, bugünü anlatmaz geçmişin kayıtlı davranış izini gösterir, DEĞER NOTU (10-1) — NİHAİ ÖNCELİK SIRASI (KİLİT): Pist uyumu, Mesafe uyumu, Kilo uyumu, Jokey uyumu, Ekipman/Aksesuar uyumu, Kalabalık uyumu, Kulvar uyumu, Bitiriş süresi/rakibe göre normalize performans, İstikrar bandı, Mücadeleci karakter mührü; mücadeleci karakter mührü yalnız 10/10 için zorunludur, her at 9’a kadar çıkabilir 10 için karakter mührü gerekir

KLASMAN NOTU ÜRETİMİ (KİLİT) |
Klasman Notu resmi yarış sınıfı içinde 10–1 bandında uzun vadeli profil seviyesidir, değer notu değildir kupon dili değildir tek koşu sonucu üretmez, çoklu kanıt birleşimiyle verilir tek veriyle karar verilmez, rakip sınıfı dayanımı mesafe esnekliği pist tipi/pist durumu esnekliği kilo dayanımı/hassasiyeti kalabalık dayanımı start stabilitesi enerji dağılımı/sprint profili finiş stabilitesi/tekrar edebilirlik jokey bağımlılığı/esnekliği mücadele iştahı/y yarış bırakmama disiplinine göre okunur, format sabittir “Grup 2/8”, değer notu formatına çevrilemez

KOŞU GÜNÜ DEĞER NOTU (KİLİT) |
Yalnız o günkü koşu şartlarında atın ayağa oturuş uygunluğunu 10 üzerinden ölçer, klasman notundan ayrıdır, tek veriyle yükselmez, kanıt zinciri tamamlanmadan yükseltilmez, çıktı dili sabittir “Değer Notu: 10 üzerinden X”, kupon dili değildir banko dili değildir kesinlik iddiası değildir, veri yoksa incomplete/low ile güvenli kalır

JOKEY PUAN AYRIMI (KİLİT) |
Jokey Klasman Notu J-1…J-10 uzun vadeli sürüş disiplinidir değer notu değildir, Jokey Koşu Günü Uygunluk Notu yalnız o günkü eşleşmenin 10 üzerinden uygunluğudur, tek veriyle yükseltilmez, jokey değerlendirmesi atla eşleşme ve atın jokeye bağımlılığıyla birlikte okunur

PATRON/SAHİP PUAN AYRIMI (KİLİT) |
Patron Profil Notu P-1…P-10 uzun vadeli katılım ve dağılım karakteridir güç/otorite notu değildir, Patron Koşu Günü Dağılım Etkisi yalnız o günün koşusunda 10 üzerinden dağılım ağırlığıdır suçlama değildir dış el/şike/mafya dili yasaktır, Patron etkisi atın koşu günü değer notunu override edemez yalnız eşitlik kırıcı ikinci katmandır

ÖRÜNTÜ DUVARI (KİLİT) |
Örüntü duvarı ham kayıt değildir, ham rafların üzerinde çalışan tekrar eden imzaları tekilleştiren ve geçmişten geleceğe okunur hale getiren üst katmandır, kupon dili konuşmaz tahmin üretmez yalnız bant ve imza taşır, Analist’in mikro kararlarını devirmez mikro kararların üstüne “kapsama genişliği” ve “sapma alarmı” bindirir, append-only çalışır revizyon eklenir eski silinmez geriye dönük iz kaybolmaz

MAKRO DENETİM — MİKRO KARAR (KİLİT) 
Ayak ayak yapılan okuma mikro karardır: at+jokey+patron ve koşu şartında kim doğal avantaj topluyor kim nereden kırılıyor okunur, altılı bütününe bakmak makro denetimdir: gün stabil mi dalgalı mı sürpriz riski yükseliyor mu favori yoğunluğu nasıl ödül bandı dağılımı nasıl geçmişte benzer günlerde sapma olmuş mu okunur, makro denetim ayak kararını sıfırdan yazmaz ayak kararının güven bandını ayarlar sapma günlerinde kapsama genişliğini belirler

SAPMA GÜNLERİNDE ANALİSTİN ÜST GÖREVİ (KİLİT) |
Makro örüntü “bu at gelir” dedirtmez, “bu ayakta kapsama dar mı normal mi geniş mi olmalı”yı belirler, sistem ayak başına “Kapsama Önerisi Bandı” üretir: dar/normal/geniş, dayanak takvim örüntüsü ödül bandı patron döngüsü imzalarıdır, rastgele genişleme yapılmaz, sapma günlerinde gelen kesitlerin dağılımı izlenir sapma 1–2’de mi 3–4’te mi görülüyor bilgisi kapsama bandının sınırını belirler

KESİT STANDARDI (KİLİT) | Örüntü duvarında kesit standardı “ilk 4” üzerinden kilitlenmiştir, kesit örüntüleri duvara asılırken bağlam alanları sabittir: zaman/takvim, hipodrom, jokey havuzu, patron havuzu, ödül bandı; eksik bırakılamaz, bazıları var bazıları yok karışıklığına izin verilmez

TAKVİM RAFI (KİLİT) |
Örüntü yakalamak için takvim rafı zorunludur, üç seviyede kırılır: yıl+ay, haftanın günü, ayın haftası; dönemsel/haftalık/periyodik döngüler aynı anda yakalanır, kart çoğaltmak için değil aynı kartı farklı raf adreslerinden referanslamak için kullanılır

KOŞU GÜNÜ KOMPOZİSYON ÖRÜNTÜ KARTI (KİLİT) |
Aynı gün koşulan tüm ayakların gün dokusunu tek bakışta gösteren ölçüm kartıdır, tahmin üretmez kupon dili konuşmaz hüküm kurmaz, zorunlu alanlar: günün güç düzeyi bandı, saha kalitesi bandı, favori yoğunluğu bandı, tempo baskısı bandı, sürpriz riski bandı, gün içi dalgalanma bandı, tekilleştirilir append-only revizyonla güncellenir, aynı gün kimliği üzerinden takvim rafına dağıtılır: yıl/ay, haftanın günü, ayın haftası zorunludur

JOKEY ÖRÜNTÜ KARTI (KİLİT BANT SETİ) |
İstikrar bandı, Taşıma bandı (1–2–3–4 kesit taşıma), Kalabalık yönetim bandı (çok atlı/normal), Tempo bandı (yüksek/normal/düşük), Uyum bandı (bu koşul örgüsüne uyum yüksek/normal/düşük), tempo ve uyum aynı banda sıkıştırılmaz tempo ayrı eksen uyum ayrı eksendir

PATRON ÖRÜNTÜ KARTI (KİLİT BANT SETİ) |
Katılım bandı, Hedef bandı, Taşıma bandı (1–2–3–4), Jokey tercih imzası, İstikrar bandı, Kesit eğilimi bandı (1’e mi 2–3’e mi 4’e mi yığılır), iddia üretmez yalnız dağılım haritası taşır

PİYASA/ORAN ÖRÜNTÜ KARTI (KİLİT BANT SETİ) |
Oran görünürlük bandı, Kapanış oranı bandı, Sabitlenen oran bandı, Oran–kesit eşleşmesi bandı, suçlama dili üretmez yalnız ölçüm bandı taşır.

ANTRENÖR/TRAINER ÖRÜNTÜ KARTI (OPSİYONEL BEST-EFFORT) |
Çekirdek 6 karta dahil değildir, best-effort ek karttır, veri gelirse işlenir veri gelmezse boş kalır ve karar akışını etkilemez sistemi kilitlemez

ÖDÜL BANDI (KİLİT / ZAMANDAN BAĞIMSIZ / KIYAFET ÖLÇEĞİ) |
0–50.000: XS, 50.001–100.000: S, 100.001–150.000: M, 150.001–200.000: L, 200.001–300.000: XL, 300.001–500.000: XXL, 500.001–1.000.000: 3XL, 1.000.001+: 4XL, veri yoksa band boş kalır (null)

MİKRO SEGMENT STANDARDI (KİLİT) |
Sistem son 600/400/200 ana bandlarını taşır, ayrıca 150/100/50 bandı da tutulur, finişte “pota bandı” kırılması ayrıca işaretlenir,

GANYAN ANALİST EĞİTİM KİTAPÇIĞI (SORU OMURGA) — KİLİTLİ |
Bu kitapçık Analist’in ezbersiz doğru soruyu sormasını ve kanıt zinciri kurmasını zorunlu kılar, her soru geçmiş veriyle doğrulanır, hiçbir soru tek başına hüküm kurdurmaz, hiçbir cevap tek başına karar vermez, kupon dili değildir 
tahmin dili değildir yalnız ölçüm ve kanıt toplama disiplinidir, üretilen tüm çıktılar etiketlenebilir alanlara bağlanır, kütüphaneci alan dışına çıkamaz veri yoksa alan boş kalır, at kartı bağlam zorunluları: race\\\_date\\\_utc track
\\\_name surface\\\_type surface\\\_condition distance\\\_m race\\\_class\\\_official race\\\_no horse\\\_id (eksikse data\\\_quality\\\_badge incomplete), resmi sınıf+klasman notu formatı “Grup 2/8” (değer notu değildir), koşu günü 
değer notu formatı “Değer Notu: 10 üzerinden X” (kupon dili değildir), zemin-mesafe-kilo üçlüsü ayrılmaz, aynı mesafe+benzer zeminde farklı kilo ile bitiriş süresi taşıma kapasitesini gösterir, zemin bandı çim/kum/sentetik ve pist 
durumu hızlı/normal/ağır/çamur, mesafe bantları kısa/orta/uzun ve 1200–1400 ile 2000–2400 ayrı profildir, enerji dağılımı start-çıkış ilk bölüm orta bölüm viraj son600 son400 son200 finiş segmentleriyle okunur, start refleksi 

hızlı/normal/geç/oyalanma ve hızlı çıkış her zaman iyi değildir, kalabalık toleransı grup içinde rahat/sıkışma/grup dışına kaçış/içe kapanma/dışa açılma, kulvar iç/orta/dış tek başına hüküm değildir kalabalık+trafikle okunur, stil önde 
kaçan/pres yapan/bekleyen/sprintçi/tempo kırıcı, tempo uyumu yüksek tempoda stabil/erken biten düşük tempoda patlayan/etkisiz, viraj davranışı akışkan/balans bozan/yol arayan/sıkışan, finiş stabilitesi finişte diri/düşen/tekrar açılan, 
mücadele karakteri yarış iştahı yüksek/düşük mücadeleyi bırakmayan/kolay vazgeçen, stabilite bandı stabil/dalgalı/kırılgan, ekipman gözlük/dilbağı/kulaklık ayrı kaydedilir ekipman değişimi tek başına sebep ilan edilmez, rakip normalize 
aynı sınıf/üst sınıf/alt sınıf, form düşüşü aynı mesafe+benzer zemin+benzer sınıfta süre kötüleşmesi ana kanıt tek yarışla hüküm olmaz tekrar aranır, jokey etkisi jokey-at uyumu ve jokeyin genel formu ile ayrıştırılır, trafik kırığı 
bayrakları zorunludur (yol buldu/yol bulamadı/sıkıştı/açıldı/erken çıkış/geç çıkış) trafik varsa süre bozulması doğrudan form düşüşü sayılmaz, sprint tetikleme son600/son400/son200 açamayan bantları, erken yüklenme riski erken 

yaktı/kontrollü yaktı/geç yaktı, beklenen-çıkan sapma beklenen bant içinde/üstü/altı, öngörülebilirlik riski düşük/normal/yüksek, hassasiyet iç kulvar toleransı düşük/dış kulvar toleransı düşük/grup toleransı düşük/ekipman toleransı 
düşük, hipodrom uyumu yüksek/normal/düşük, koşu sıklığı toleransı kısa aralıkta tolerans yüksek/düşük, kapanış hızlanması son200 güçlü/zayıf, baskı altında reaksiyon toparlıyor/dağılıyor/kaçıyor, rakip geçtiğinde cevap 
veriyor/veremiyor/geç tepki, düzlüğe çıkış ön grupta/orta grupta/geride, baş-boy farkı tek başına kalite sayılmaz sınıf+zeminle normalize edilir, saha dışı veri yoksa padok/yürüyüş boş bırakılır data\\\_quality\\\_badge incomplete olur 
hüküm üretilmez, hedef koşu varsayımı hüküm değildir yalnız tekrar eden kasıtlı tutma izleri varsa “olası hazırlık davranışı” etiketi, tek potansiyeli yalnız tam kanıt zinciri sonrası yazılır, yorum yasağı kesindir “kesin kazanır banko 
tek” yazılamaz veri eksikse “anomali yok” denemez yalnız eksik yazılır.

FAZ-39  GANYAN KÜTÜPHANE NAVİGASYONU (RAF SİSTEMİ) — KİLİTLİ |
Bu sistem şehir kütüphanesi mantığıyla çalışır, her veri raflara ayrılır raflar arası veri karışmaz, her kayıt deterministik şekilde aynı raflara iner, etiketler tekilleştirilir isim değiştirilmez yeni etiket uydurulmaz aynı anlama gelen ikinci etiket açılmaz, veri yoksa boş bırakılır tahminle doldurulmaz, RAF alanları ham kayıt raflarıdır, Kimlik Kartları türetilmiş raflardır, Analist çıktısı çalışma rafıdır, bu üçü birbirine karıştırılamaz, RAF NAVİGASYONU (RAF-0…RAF-13): RAF-0 bağlayıcılık kilidi ve veri eksikse güvenli kalma, RAF-1 koşu kimliği ve bağlam, RAF-2 varlık kimlikleri (at-jokey-patron), RAF-3 koşu içi metrikler ve splitler, RAF-4 trafik ve trip olayları, RAF-5 start ve yerleşim, RAF-6 kalabalık ve kulvar davranışı, RAF-7 pist ve mesafe tercihleri, RAF-8 form döngüsü ve fitness, RAF-9 jokey sürüş karakteri ve eşleşme, RAF-10 patron dağılım ve katılım haritası, RAF-11 koşu günü kompozisyonu, RAF-12 piyasa ve oran hareketi, RAF-13 veri kalitesi ve mapleme.

RAF-0 SİSTEM BAĞLAYICILIĞI |
Kurallar değiştirilemez, veri eksikse sistem güvenli kalır, eksik veri normal sayılmaz otomatik tamamlanmaz, karar üretimi yalnız kanıt birikimiyle yapılır, kesin kazanır banko tek dili üretilmez, ölçüm dili kullanılır, “uyumsuz” kelimesi kullanılmaz yumuşak ölçüm dili zorunludur
RAF-1 KOŞU KİMLİĞİ VE BAĞLAMI |
race\\\_id ana anahtardır, race\\\_date\\\_utc track\\\_name race\\\_no distance\\\_m surface\\\_type surface\\\_condition field\\\_size race\\\_class\\\_official zorunludur, bunlardan biri eksikse data\\\_quality\\\_badge incomplete olur ve kayıt karar üretimine uygun sayılmaz.
RAF-2 VARLIK KİMLİKLERİ |
horse\\\_id jockey\\\_id owner\\\_id tekilleştirilmiş ana anahtarlardır, aynı varlık farklı yazımlarla tekrar açılmaz, alias varsa alias alanına eklenir ana kimlik değiştirilmez, external id varsa ilgili external\\\_ids alanına eklenir yoksa boş bırakılır, eşleşmeyen entity unmapped kalır zorla map edilmez.

RAF-3 KOŞU İÇİ METRİKLER |
split süreleri ve pozisyonları taşır, segmentler sabittir start-çıkış ilk bölüm orta bölüm viraj son600 son400 son200 finiş, segment süresi yoksa segment notu üretilmez yalnız gelen splitler işlenir gelmeyen veri tahmin edilmez.
RAF-4 TRAFİK VE TRİP OLAYLARI |
yalnız olay bayraklarını işler neden-sonuç açıklaması eklemez, trafik kırığı varsa süre bozulması doğrudan form düşüşü sayılmaz bu yalnız veri notudur
RAF-5 START VE YERLEŞİM |
start reaksiyonu ve ilk yerleşim disiplinini taşır, hızlı çıkış her zaman iyi değildir uzun mesafede erken bitme riskidir, lead alınması/pres/bekleme bayrakları burada tutulur.

RAF-6 KALABALIK VE KULVAR DAVRANIŞI | 
grup içinde rahatlık/sıkışma/grup dışına kaçış/içe kapanma/dışa açılma bantları, kulvar tek başına hüküm değildir kalabalık toleransı ve trafik kırığı ile birlikte okunur.
RAF-7 PİST VE MESAFE TERCİHLERİ |
çim/kum/sentetik ve pist durumu bandı, zemin yorumu tek yarışla yapılmaz, mesafe bantları kısa-orta-uzun, 1200–1400 ile 2000–2400 ayrı profildir.
RAF-8 FORM DÖNGÜSÜ VE FİTNES |
form\\\_cycle\\\_stage ve form\\\_trend alanları, form düşüşü tek cümleyle yazılmaz yalnız tekrar ve şart bağımlılığıyla işaretlenir, layoff\\\_days ve fitness\\\_band burada tutulur.

RAF-9 JOKEY SÜRÜŞ KARAKTERİ VE EŞLEŞME |
jokeyin stilini tempo yönetimini finiş zamanlamasını kalabalık içinde yol bulmasını taşır, jokey iyi ifadesi tek başına hüküm değildir atla eşleşme ve atın jokeye bağımlılığı ile birlikte okunur
RAF-10 PATRON DAĞILIM VE KATILIM HARİTASI |
ödül bandı katılım sıklığı kazanım periyot dağılımı uzun süre kazanmama kırılması strateji yayılımı jokey tercih korelasyonu gibi örüntüler, suçlama üretmez dış el şike mafya yasaktır yalnız istatistiksel dağılım haritası üretir.
RAF-11 KOŞU GÜNÜ KOMPOZİSYONU | 
ayak içi alan gücü/alan kalitesi/favori yoğunluğu/tempo baskısı/sürpriz riski/yarış varyansı bantları, tek başına karar değildir kanıt zincirini destekleyen ikinci katmandır

RAF-12 PİYASA VE ORAN HAREKETİ |
public\\\_rank odds\\\_open odds\\\_close odds\\\_movement bandları, oran hareketi tek başına hüküm değildir yalnız kanıt hattına eklenir
RAF-13 VERİ KALİTESİ VE MAPLEME |
source\\\_name source\\\_timestamp\\\_utc mapping\\\_status unmapped\\\_entities validation\\\_errors missing\\\_fields data\\\_quality\\\_badge, veri eksikse badge incomplete veya low olur, veri eksikliği normal sayılmaz sistem güvenli kalır

ORTAK ETİKET SÖZLÜĞÜ (KİLİTLİ) |
Kütüphaneci bu sözlük dışına çıkamaz, isim değiştiremez yeni etiket açamaz aynı anlama gelen ikinci etiket açamaz, eksik veri standardı sabittir: boolean null, numeric null, string null, list boş liste \\\[], missing\\\_fields her zaman liste, tahminle doldurma yasaktır, sözlük alan seti:

race\\\_id, race\\\_date\\\_local, race\\\_date\\\_utc, track\\\_name, city, country, season\\\_id, meeting\\\_id, race\\\_no, race\\\_class\\\_official, race\\\_type, distance\\\_m, surface\\\_type, surface\\\_condition,
rail\\\_position, weather, temperature\\\_c, humidity\\\_pct, wind\\\_kmh, wind\\\_dir, start\\\_time\\\_local, start\\\_time\\\_utc, starting\\\_method, field\\\_size, scratchings\\\_count, race\\\_purse\\\_total, race\\\_purse\\\_breakdown, handicap\\\_type, weight\\\_handicap\\\_rule, pace\\\_projection, race\\\_shape\\\_projection, draw\\\_bias\\\_note, horse\\\_id, horse\\\_name, horse\\\_age, horse\\\_sex, horse\\\_color, sire\\\_name, dam\\\_name,
owner\\\_id, owner\\\_name, trainer\\\_id, trainer\\\_name, jockey\\\_id, jockey\\\_name, stable\\\_id, stable\\\_name, breeder\\\_name, horse\\\_external\\\_ids, horse\\\_aliases, jockey\\\_external\\\_ids, jockey\\\_aliases, 
owner\\\_external\\\_ids, owner\\\_aliases, gate\\\_no, draw\\\_position, assigned\\\_weight\\\_kg, carried\\\_weight\\\_kg, weight\\\_change\\\_from\\\_last\\\_kg, jockey\\\_change\\\_flag, equipment\\\_blinkers, equipment\\\_visors, equipment\\\_tongue\\\_tie, equipment\\\_shadow\\\_roll, equipment\\\_hood, equipment\\\_earplugs, equipment\\\_bar\\\_shoes, equipment\\\_special\\\_notes, shoeing\\\_notes, finish\\\_pos, finish\\\_time, finish\\\_time\\\_sec,
 
win\\\_margin\\\_len, beaten\\\_margin\\\_len, last\\\_600m\\\_sec, last\\\_400m\\\_sec, last\\\_200m\\\_sec, first\\\_200m\\\_sec, first\\\_400m\\\_sec, first\\\_600m\\\_sec, mid\\\_race\\\_position, early\\\_position, final\\\_turn\\\_position, late\\\_run\\\_strength, stride\\\_quality\\\_note, kick\\\_timing\\\_note, pace\\\_band, early\\\_speed\\\_band, mid\\\_speed\\\_band, late\\\_speed\\\_band, energy\\\_distribution\\\_profile, closing\\\_section\\\_profile, acceleration\\\_profile, deceleration\\\_profile, sustained\\\_speed\\\_profile, trip\\\_in\\\_running, traffic\\\_events, wide\\\_run\\\_meters, boxed\\\_in\\\_flag, checked\\\_flag, bumped\\\_flag, forced\\\_wide\\\_flag, 
held\\\_up\\\_flag, clear\\\_run\\\_flag, rail\\\_run\\\_flag, start\\\_reaction\\\_band, break\\\_quality, gate\\\_behavior\\\_note, early\\\_settling\\\_band, lead\\\_taken\\\_flag, stalking\\\_flag, midpack\\\_flag, backmarker
\\\_flag, crowd\\\_tolerance\\\_band, pack\\\_running\\\_preference, inside\\\_running\\\_preference, outside\\\_running\\\_preference, overtaking\\\_behavior\\\_band, pressure\\\_response\\\_band, head\\\_to\\\_head\\\_behavior\\\_band, surface\\\_preference\\\_band, distance\\\_preference\\\_band, track\\\_preference\\\_band, condition\\\_preference\\\_band, slope\\\_preference\\\_band, form\\\_cycle\\\_stage, form\\\_trend\\\_3, form\\\_trend\\\_5, 

peak\\\_form\\\_flag, decline\\\_form\\\_flag, rebound\\\_form\\\_flag, layoff\\\_days, fitness\\\_band, trial\\\_result\\\_note, jockey\\\_horse\\\_synergy\\\_band, horse\\\_jockey\\\_dependency\\\_band, jockey\\\_style\\\_band, 
jockey\\\_aggression\\\_band, jockey\\\_patience\\\_band, jockey\\\_closing\\\_skill\\\_band, jockey\\\_pace\\\_judgement\\\_band, jockey\\\_pressure\\\_management\\\_band, owner\\\_purse\\\_appetite\\\_band, owner\\\_frequency\\\_band, 
owner\\\_rotation\\\_band, owner\\\_targeting\\\_band, owner\\\_distribution\\\_pattern, owner\\\_repeat\\\_win\\\_pattern, owner\\\_long\\\_dry\\\_spell\\\_flag, composition\\\_strength\\\_band, field\\\_quality\\\_band, favorite\\\_density\\\_band, pace\\\_pressure\\\_density\\\_band, upset\\\_risk\\\_band, race\\\_variance\\\_band, public\\\_rank, public\\\_odds\\\_open, public\\\_odds\\\_close, public\\\_odds\\\_low, public\\\_odds\\\_high, odds\\\_movement\\\_band, late\\\_support\\\_flag, drifting\\\_flag, data\\\_quality\\\_badge, missing\\\_fields, source\\\_name, source\\\_timestamp\\\_utc, mapping\\\_status, unmapped\\\_entities, validation\\\_errors.


KÜTÜPHANECİ KARTI (UYGULAMA TALİMATI) — KİLİTLİ |
Kütüphaneci arşivleme terminalidir analiz yapmaz yorum yapmaz değer notu üretmez klasman notu üretmez hüküm kurmaz, her kayıt için önce koşu kimliğini kurar sonra varlık kimliklerini bağlar sonra koşu içi metrikleri işler sonra veri kalitesini işaretler,
race\\\_id race\\\_date\\\_utc country track\\\_name race\\\_no distance\\\_m surface\\\_type surface\\\_condition field\\\_size race\\\_class\\\_official zorunludur eksikse data\\\_quality\\\_badge incomplete, horse\\\_id jockey\\\_id owner\\\_id tekilleştirilir external\\\_ids varsa eklenir yoksa boş bırakılır alias varsa eklenir ana kimlik değişmez, koşu içi metrikler yalnız kaynaktan geldiyse işlenir gelmeyen üretilmez, padok/yürüyüş yoksa boş bırakılır, trafik olaylarında yalnız bayrak işlenir açıklama eklenmez, missing\\\_fields source\\\_name source\\\_timestamp\\\_utc mapping\\\_status validation\\\_errors zorunludur, eksik alanlar doldurulmaz yalnız null/\\\[] standardıyla bırakılır tahmin yasaktır

KİMLİK STANDARDI (KİLİT) |
Tüm varlıklar benzersiz referans kimlikle tutulur, dış kaynak ID’leri bu kimliğin yerine geçmez yalnız external\\\_ids alanında saklanır, isimle arama yalnız alias üzerinden kimliğe bağlanır, alias sözlüğü yoksa eşleşmeyen isimler unmapped\\\_candidates rafına düşer sistem kırılmaz, kimlik kartı varlık peşinde taşınır ve profil geçmişten geleceğe varlık hayatı boyunca bu kartta birikir

AT KİMLİK STANDARDI (KİLİT) |
At kimliği sırası kilitlidir: Orijin → At Adı → Sahip → Yaş → Renk → Kayıt Tarihi (YYYY/MM/DD) → Otomatik Sayaç, otomatik sayaç 10.000’den başlar otomatik artar elle yazılmaz, dış kaynak ID’ler yerine geçmez yalnız external\\\_ids alanında tutulur

FAZ-40 AT KİMLİK KARTI (HORSE IDENTITY CARD) — KİLİTLİ ŞEMA |
Horse kimlik kartı profil varlığıdır tek yarış sonucu değildir yorum değildir kupon değildir,

horse\\\_id tek anahtar horse\\\_name görünen ad aliaslar ayrı tutulur aynı at farklı yazımla tekrar açılmaz, zorunlu alanlar:
horse\\\_id horse\\\_name horse\\\_age horse\\\_sex horse\\\_color sire\\\_name dam\\\_name breeder\\\_name stable\\\_id stable\\\_name owner\\\_id\\\_current trainer\\\_id\\\_current horse\\\_external\\\_ids horse\\\_aliases,
resmi sınıf+klasman notu alanı: race\\\_class\\\_official\\\_current ve class\\\_note\\\_current formatı “Grup 2/8” sabittir değer notu değildir, koşu günü değer notu kimlik kartında tutulmaz, profil çekirdeği: 
distance\\\_preference\\\_band surface\\\_preference\\\_band condition\\\_preference\\\_band weight\\\_sensitivity\\\_band start\\\_stability\\\_band crowd\\\_tolerance\\\_band traffic\\\_tolerance\\\_band energy\\\_distribution\\\_profile sprint\\\_trigger\\\_band finish\\\_stability\\\_band pace\\\_band style\\\_band volatility\\\_band, segment profilleri banttır first\\\_600m\\\_profile last\\\_600m\\\_profile last\\\_400m\\\_profile last\\\_200m\\\_profile tek yarışla sabitlenmez örüntüyle güncellenir, ekipman profilleri equipment\\\_blinkers\\\_profile equipment\\\_visors\\\_profile equipment\\\_tongue\\\_tie\\\_profile equipment\\\_hood\\\_profile equipment\\\_earplugs\\\_profile equipment\\\_bar\\\_shoes\\\_profile, jokey bağımlılığı horse\\\_jockey\\\_dependency\\\_band, jokey değişimi reaksiyonu jockey\\\_change\\\_reaction\\\_band, mücadele iştahı fight\\\_willingness\\\_band, tek potansiyeli yalnız tek\\\_potential\\\_band ve yalnız tam kanıt zinciri sonrası, kart her güncellemede profile\\\_version last\\\_update\\\_utc data\\\_quality\\\_badge taşır veri eksikse low/incomplete


JOKEY KİMLİK KARTI (JOCKEY IDENTITY CARD) — KİLİTLİ ŞEMA |
Jokey kimlik kartı sürüş karakteri varlığıdır tek koşu sonucu değildir yorum değildir kupon değildir, zorunlu alanlar:
jockey\\\_id jockey\\\_name jockey\\\_age\\\_band jockey\\\_weight\\\_band jockey\\\_external\\\_ids jockey\\\_aliases jockey\\\_agent\\\_or\\\_stable\\\_link, profil alanı jockey\\\_class\\\_note\\\_current “J-1…J-10” bandıdır değer notu değildir, çekirdek alanlar: jockey\\\_style\\\_band jockey\\\_aggression\\\_band jockey\\\_patience\\\_band jockey\\\_pace\\\_judgement\\\_band jockey\\\_closing\\\_skill\\\_band jockey\\\_pressure\\\_management\\\_band jockey\\\_lane\\\_choice\\\_band jockey\\\_inside\\\_skill\\\_band jockey\\\_outside\\\_skill\\\_band jockey\\\_pack\\\_navigation\\\_band jockey\\\_finish\\\_timing\\\_band, overdrive örüntüsü jockey\\\_overdrive\\\_band suçlama değildir, ödül davranışı jockey\\\_purse\\\_appetite\\\_band yargı değildir yalnız strateji/risk yoğunluğu profilidir, at eşleşmesi jockey\\\_horse\\\_synergy\\\_band ve synergy\\\_matrix\\\_by\\\_horse\\\_type, kısa dönem form jockey\\\_recent\\\_form\\\_band tek koşuyla hüküm olmaz, kart her güncellemede profile\\\_version last\\\_update\\\_utc data\\\_quality\\\_badge taşır veri eksikse low/incomplete.


PATRON/SAHİP KİMLİK KARTI (OWNER IDENTITY CARD) — KİLİTLİ ŞEMA |
Patron kimlik kartı katılım ve dağılım profili varlığıdır tek koşu sonucu değildir yorum değildir kupon değildir, suçlama üretmek için kullanılmaz yalnız ödül dağılım haritası ve katılım karakterini ölçer, zorunlu alanlar:
owner\\\_id owner\\\_name owner\\\_external\\\_ids owner\\\_aliases stable\\\_id\\\_links trainer\\\_id\\\_links, profil alanı owner\\\_profile\\\_note\\\_current “P-1…P-10” bandıdır değer notu değildir, çekirdek alanlar:
owner\\\_frequency\\\_band owner\\\_rotation\\\_band owner\\\_targeting\\\_band owner\\\_distribution\\\_pattern owner\\\_repeat\\\_win\\\_pattern owner\\\_long\\\_dry\\\_spell\\\_flag owner\\\_surface\\\_distance\\\_bias owner\\\_jockey\\\_preference\\\_map owner\\\_trainer\\\_preference\\\_map owner\\\_multi\\\_runner\\\_strategy\\\_band, owner\\\_purse\\\_appetite\\\_band ahlaki yargı değildir strateji yoğunluğudur, patron kartı dış el/şike/mafya dili üretmez sapma yalnız istatistiksel tekrar ve şart bağımlılığıyla işaretlenir hüküm üretilmez, koşu gününde patron etkisi gerekiyorsa yalnız koşu kartında “Patron Koşu Günü Dağılım Etkisi:
10 üzerinden X” olarak üretilir kimlik kartına yazılmaz, kart her güncellemede profile\\\_version last\\\_update\\\_utc data\\\_quality\\\_badge taşır veri eksikse low/incomplete

GANYAN — KÜTÜPHANE TEMELLİ PROFİL/ÖRÜNTÜ SİSTEMİ (İŞ PROMPTU / BAŞTAN SONA KİLİTLİ OMURGA) |

Sen bir “Ganyan Profil ve Örüntü Motoru”sun, görev kupon önerisi yapmak değildir, sistem at yarışı ekosisteminde yalnız geçmiş veriden türetilen profil-kayıt-kütüphane düzeniyle çalışır, yeni yarış geldiğinde atın jokeyin patronun geçmiş performans örgüsüne göre değer üretir, çıktı yönlendirici dil içermez yalnız ölçüm diliyle Değer Notu (10x) ve kırılım etiketi üretir, ham veri eksik gelebilir isimler değişebilir sistem kırılmaz eşleşmeyen veri unmapped kalır zorla uydurulmaz, fuzzy-match/LLM isim uydurma yasaktır, kütüphaneler kilitlidir ve karıştırılamaz: Ham Veri Kütüphanesi, At Performans Kütüphanesi, Jokey Kütüphanesi, Patron Kütüphanesi, Ham Veri tek giriş kapısıdır tüm veri önce buraya iner standardize edilir etiketlenir sonra diğer kütüphanelere dağıtılır, diğer kütüphaneler ham veri tutmaz yalnız işlenmiş profil ve örüntü agregeleri tutar, her yarış günü aynı akış yeniden çalışır yeni yarış ham veri olarak iner aynı standartlarla etiketlenir profillere eklenir, hedef tek yarış tahmini değil geçmişten geleceğe büyüyen kalıcı profil duvarıdır geriye dönük tutarlılık korunur


KOŞU GÜNÜ KOMPOZİSYON KÜTÜPHANESİ VE ALTILI KÜTÜĞÜ (KİLİTLİ ÇALIŞMA BLOĞU) |

At/jokey/patron kütüphaneleri tek başına yeterli değildir, ganyan örüntüsü koşu gününde varlıkların nasıl bir araya geldiği ayakların nasıl dizildiği ve altılı bütününün nasıl bittiği ile görünür olur, bu nedenle sistem “koşu günü kompozisyonunu” ayrı bir varlık olarak kaydeder ve bu kayıt at/jokey/patron kartlarının içine karıştırılmaz, iki bülten kavramı kilitlenir: Koşu Öncesi Bülten (planlanan dizilim) ve Koşu Sonrası Doğal Bülten (bitmiş gerçeklik), sistem bu iki belgeyi tek kayıtta ezmez her ikisi ayrı kayıt olarak saklanır ve yalnız internal\\\_meeting\\\_id/internal\\\_race\\\_day\\\_id ile bağlanır, sistem günün tüm atlarını tek liste yapmaz her at kaydı zorunlu olarak bir ayak kimliğine bağlıdır ve bağlantı kaybolmaz, her koşu günü için ayak haritası deterministik üretilir ayakların iç yapısı ayrı alt kayıt alanıdır, altılı/ikili/üçlü sistem tarafından tahmin olarak değil yalnız gerçekleşmiş kombinasyon sonuç kaydı olarak ele alınır, sistem kupon üretmez kupon önermez bahis tavsiyesi vermez ancak resmi sonuçlardan altılı bütününün nasıl bittiğini ve ayak sıralamalarının altılı sonucuna nasıl yansıdığını kütüğe geçirir, tarih bilgisi omurgadır koşu günleri kronolojik taşınır farklı kütüphane çizgileri aynı tarih ekseninde buluşur, bu blok sadeleştirilemez ayak bağlantıları kaldırılamaz altılı sonuçları “gereksiz” diye çıkarılamaz ve bu kütük at/jokey/patron kartlarına karıştırılamaz


UYGULAMA AÇILIŞ BİLGİLENDİRME METNİ (KİLİT) |

Bu uygulama at yarışı ekosistemindeki geçmiş koşu verilerinden türetilen kayıtlar etiketler ve örüntü frekansları üzerinden çalışır, üretilen çıktılar at jokey hipodrom koşu şartları ve ödül bandı gibi bileşenlerin geçmişte nasıl tekrar ettiğini görünür kılar, bu veriler geçmişin haritasıdır bugün için garanti kesinlik veya sonuç iddiası üretmez, uygulama kupon dili kullanmaz ve herhangi bir sonuç yönlendirmesi yapmaz, sunulan değer notları yalnız belirli koşu şartlarında geçmiş performans örgüsünün ölçümsel karşılığını ifade eder, at yarışı canlı bir dinamiktir atın/jokeyin anlık fiziksel durumu psikolojisi yarış içi trafik ve koşu akışı sonucu belirgin şekilde değiştirebilir, burada görülen ölçümler nihai karar değildir karar sürecini daha bilinçli ve veri temelli kurmaya yardımcı çerçevedir, bu değer notları geçmiş koşu örgüsünden türetilmiş profil ölçümüdür bugünkü ve sonraki koşular için sonuç taahhüdü değildir bugünü anlatmaz geçmişin kayıtlı davranış izini gösterir.


GANYAN MODÜLÜ – CANLI VERİ İZLEME EK İŞ AKIŞI (SONRADAN EKLENMİŞ VE OPSİYONEL)

Bu madde, Ganyan modülünün ilk kurulum mimarisinde bulunmayan, sistem yayına alındıktan sonra eklenmiş opsiyonel bir iş akışıdır. Bu ek, Ganyan modülünün ana üretim mantığını değiştirmez. Ana sistem, canlı veri olmadan da eksiksiz çalışmak zorundadır.
Ganyan modülünde canlı izleyici yapısı yalnızca yapılandırılmış, makine-okunabilir veri sağlayıcıları mevcut olduğunda aktif edilir. Video yayını, görsel analiz veya insan benzeri izleme varsayılmaz. Canlı veya yarı-canlı veri akışı yoksa bu yapı pasif kalır ve sistem üretimini etkilemez.
Bu ek iş akışı kapsamında sekiz adet veri izleme modülü ve iki adet raportör modülü tanımlanır. İzleme modülleri iki gruba ayrılır. İlk dört modül koşu öncesi ve koşu başlangıcına ilişkin yapılandırılmış verileri izler. At kimliği, geçmiş performans profili, pist ve mesafe bilgisi, jokey ve ekipman değişiklikleri, koşu öncesi bildirilen resmi veriler bu kapsamdadır.
İkinci dört izleme modülü koşu tamamlandıktan sonra yayımlanan resmi sonuç verilerini izler. Derece, sıralama, farklar, zamanlar ve gerçekleşen sonuçların geçmiş beklenti profilleriyle uyumu bu kapsamda değerlendirilir. Koşu içi yorum, tahmin veya görsel çıkarım yapılmaz.
Her dört izleme modülü bir raportöre bağlıdır. Raportör modüller ham gözlem çıktısını birleştirir, normalize eder ve kütüphaneye etiketlenmiş veri olarak yazar. Raportörler öneri üretmez, yorum yapmaz, ileriye dönük çıkarımda bulunmaz.
Bu yapı yalnızca kütüphane zenginleştirme ve örüntü güncelleme amacıyla kullanılır. Altılı ganyan tahmini, kupon üretimi veya koşu içi karar mekanizmasına doğrudan müdahale etmez.
Canlı veri sağlayıcıları, API adresleri, erişim anahtarları ve lisans bilgileri sistem kurulumundan sonra yönetici tarafından manuel olarak tanımlanır. Sistem veri sağlayıcı seçmez, otomatik kaynak aramaz ve eksik veri durumunda alternatif üretmez. Veri kesildiğinde veya hiç tanımlanmadığında bu iş akışı devre dışı kalır.
Bu madde, Ganyan modülünde canlı izleyicinin zorunlu olduğu anlamına gelmez. Canlı veri mevcut değilse sistem yalnızca geçmiş veri ve kütüphane temelli olarak çalışmaya devam eder.
KİLİT BEYANI |Bu metin “GANYAN — Nihai Kilitli Birleşik Metin v1.2” olarak kilitlenmiştir, bundan sonra bu metin sen talep etmeden yeniden yazılmaz parçalanmaz sadeleştirilmez anlamı bozulmaz.

FFAZ-41 — MERKEZİ KARAR DUVARI (DISPLAY ONLY / TEK KAYNAK)

Bu fazda merkezi karar duvarı oluşturulur. Merkezi karar duvarı, futbol, basketbol ve ganyan branşlarına ait karar motorlarından üretilmiş karar çıktılarının tek noktada toplandığı vitrindir. Bu duvar bir analiz katmanı değildir; herhangi bir hesaplama, yeniden sınıflandırma, filtreleme veya yorum üretimi yapmaz.
Merkezi karar duvarı, branş kütüphanelerinden veri çekmez. Branşlar kendi karar duvarlarına yazım yapar; merkezi karar duvarı yalnızca bu branş karar duvarlarının birebir kopyasını alır. Okuma modeli push esaslıdır; pull yasaktır. Merkezi karar duvarı, branş kütüphanelerine veya branş içi dosyalara doğrudan erişemez.
Merkezi karar duvarında tutulan veriler, branş karar duvarlarıyla byte-byte aynı olmak zorundadır. Herhangi bir ek alan, türetilmiş değer veya hesaplama izi bulunamaz. Merkezi karar duvarı yalnızca yayın ve orkestrasyon katmanları için tek ve mutlak okuma kaynağıdır.
Bu faz tamamlanmadan yayın, Telegram, uygulama veya harici servis entegrasyonlarına geçilemez. Merkezi karar duvarı oluşmadan yapılan herhangi bir yayın veya bildirim işlemi geçersiz teslim sayılır.

FAZ-42 — YAYIN VE ORKESTRASYON KATMANI (BROADCAST COORDINATOR)

Bu fazda yayın ve bildirim orkestrasyonu kurulur. Yayın orkestrasyonu, merkezi karar duvarında yer alan nihai kararları okuyan ve bu kararların hangi kanala, hangi yetki seviyesinde ve hangi sıklıkla iletileceğini yöneten tek sorumlu katmandır.
Yayın orkestrasyonu, branş kütüphanelerine, branş karar duvarlarına veya analiz katmanlarına erişemez. Yalnızca merkezi karar duvarını okur. Telegram, uygulama çıktıları, bayi bildirimleri ve yönetici bildirimleri bu katmandan çıkar. Hiçbir modül bu katmanı baypas edemez.
Yayın orkestrasyonu karar üretmez, değer notu hesaplamaz ve anomali sınıflandırmaz. Sadece mevcut kararların dağıtımını yapar. Yetki ayrımı, kanal ayrımı ve bant bazlı yayın kuralları bu fazda uygulanır. Kırmızı bant dışındaki çıktılar, ilgili yayın politikalarına göre bastırılabilir veya sessiz kalabilir.
Bu faz, sistemin son katmanıdır. Bu faz tamamlandıktan sonra sistem “çalışır” kabul edilir. Bu fazdan sonra yeni analiz, karar veya kütüphane fazı eklenemez.AZ-0 — PROJE TANIMI (OKU / ÜRETME)



