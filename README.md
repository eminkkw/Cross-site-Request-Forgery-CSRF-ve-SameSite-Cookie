# Cross-site-Request-Forgery-ve-SameSite-Cookie<br>
Siteler arası istek sahteciliği anlamına gelen CSRF zafiyeti, tarayıcının cookie’yi ekleme davranışını kötüye kullanan bir güvenlik açığıdır.CSRF zafiyeti ile 
kullanıcının oturumunun aktif olduğu uygulama üzerinde bilgisi dahilinde olmayan işlemler tetiklenebilir. Bu zafiyet, görüldüğü yere göre kritik etkilere sebep olabilir. 
Örneğin, admin yetkilerinde kullanıcı oluşturabilme veya kullanıcı bilgilerinin değiştirilebilmesi gibi…<br>
<br>
Örneğin bir istemci düşünelim bu istemciyide kullanıcının tarayıcısı olarak düşünebiliriz.<br>
<br>
1.İlk adımda, kullanıcı example.com adresine kullanıcı bilgileri ile giriş yapar.<br>
<br>
2.İkinci adımda, sunucu tarafında kullanıcı bilgileri kontrol edilir ve doğru ise kullanıcı için bir oturum oluşturularak bu oturuma referans eden kimlik bilgisi “Set-
Cookie” başlık bilgisi üzerinden tarayıcıya kaydedilir. Tarayıcı bu bilgiyi kendi veri tabanında saklar.<br>
<br>
3.Oturumu açık olan kullanıcı, örnek olarak profil sayfasını görüntülemek istediğinde tarayıcı tarafından cookie bilgisi de HTTP isteğine otomatik olarak eklenir ve bu 
isteği karşılayan web uygulaması, cookie üzerinden kullanıcının kim olduğunu bildiği için isteği onun oturumunda işletir.<br>
<br>
Buraya kadar her şey normal akışta olduğu gibi ilerliyor. Tarayıcı kendi üzerine kaydettiği cookie bilgisini bundan sonra kaydettirilen domaine yapılan isteklere 
otomatik olarak dahil edecek. Tarayıcının bu cookie ekleme davranışı da kötüye kullanılarak CSRF (Cross-site Request Forgery) adı verilen güvenlik açığının oluşmasına 
zemin hazırlamaktadır.<br>
