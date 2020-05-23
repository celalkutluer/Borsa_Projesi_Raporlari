1_KODLAR 

***Kayıt Sayfası : Öncelikle sitede işlem yapılabilmesi için kayıt işlemi gerçekleşmektedir. Bu kısımda ad,soyad,email,doğum tarihi,telefon ve şifre istenmektedir.
Kayıt işlemi tamamlanması için email adresine gelen doğrulama koduyla kayıt işlemi gerçekleşmektedir.  


<? Php
içerir  "inc / header.php" ;
?>

    < section  class = " gövde işareti " >
        < div  class = " center-sign " >
            < div  class = " panel panel-sign " >
                < div  class = " panel-title-sign mt-xl text-right " >
                    < h2  class = " başlık metni-büyük harf metin-ağırlık-kalın m-none " > < i  class = " fa fa-user mr-xs " > </ i > Kayıt </ h2 >
                </ div >
                < div  class = " panel-body " >
                    <! - UYARI ->
                    < div  id = " ykayitAlert " > </ div >
                    <! - UYARI ->
                    < form   id = " frmKayit " yöntemi = " yazı " >
                        < div  class = " form-group mb-none " >
                            < div  class = " row " >
                                < div  class = " col-sm-6 mb-lg " >
                                    < label > Reklam </ label >
                                    < input  id = " frmKayitAd " name = " frmKayitAd " type = " metin " class = " form-kontrol input-lg " />
                                </ div >
                                < div  class = " col-sm-6 mb-lg " >
                                    < label > Soyad </ label >
                                    < input  id = " frmKayitSoyad " name = " frmKayitSoyad " type = " metin " sınıf = " form-kontrol input-lg " />
                                </ div >
                            </ div >
                        </ div >
                        < div  class = " form-group mb-lg " >
                            < label > E-Posta </ label >
                            < input  id = " frmKayitEmail " name = " frmKayitEmail " type = " e-posta " class = " form-kontrol input-lg " />
                        </ div >
                        < div  class = " form-group mb-none " >
                            < div  class = " row " >
                                < div  class = " col-sm-6 mb-lg " >
                                    < label > Şifre </ label >
                                    < input  id = " frmKayitSifre " name = " frmKayitSifre "   name = " pwd " type = " şifre " class = " form-kontrol input-lg " />
                                </ div >
                                < div  class = " col-sm-6 mb-lg " >
                                    < label > Yeniden Şifre </ label >
                                    < input   id = " frmKayitSifreconfirm " name = " frmKayitSifreconfirm "   type = " şifre " class = " form-kontrol input-lg " />
                                </ div >
                            </ div >
                        </ div >
                        < div  class = " form-group mb-none " >
                            < div  class = " row " >
                                < div  class = " col-sm-6 mb-lg " >
                                    < label > Doğum Tarihi </ label >
                                    < input  id = " frmKayitDogum_tar " name = " frmKayitDogum_tar " type = " tarih " class = " form-kontrol input-lg " />
                                </ div >
                                < div  class = " col-sm-6 mb-lg " >
                                    < label > Cep Telefon No </ label >
                                    < input  id = " frmKayitCepTelNo " name = " frmKayitCepTelNo " type = " metin " veri-eklentisi-maskeli-girdi  data-input-mask = " (999) 999-9999 " yer tutucu = " (555) 555-5555 " class = " form-kontrol girişi-lg " />
                                </ div >
                            </ div >
                        </ div >
                        < div  class = " form-group mb-lg " >
                            < div  class = " clearfix " >
                                <? Php
                                $ S1 = rand ( 1 , 9 );
                                $ S2 = rand ( 1 , 9 );
                                $ t = $ s1 + $ s2 ;
                                $ y = md5 ( $ t );
                                ?>
                                < label  class = " pull-left " id = " frmKayitgiris_dogrulama_text " >
                                    <? Php
                                    echo  "$ s1 + $ s2 sayılarının toplamını girin." ;
                                    ?>
                                </ label >
                                < label  class = " pull-right " > Doğrulama </ label >
                                < input  id = " frmKayitgiris_dogrulama_input " class = " form-kontrol form-control-lg " type = " gizli "
                                       değer = " <? php  echo  $ y ; ?> " name = " frmKayittoplam " >
                            </ div >
                            < div  class = " input-group input-group-icon " >
                                < input  name = " frmKayitdkodu " type = " text " class = " form-denetim input-lg " />
                                < span  class = " input-group-addon " >
										< span  class = " icon icon-lg " >
											< i  class = " fa fa-lock " > </ i >
										</ span >
								</ span >
                            </ div >
                        </ div >
                        < div  class = " row " >
                            < div  class = " col-sm-8 " >
                                < div  class = " onay kutusu-özel onay kutusu-varsayılan " >
                                    < input  id = " frmKayitSozlesme " name = " frmKayitSozlesme " type = " onay kutusu " />
                                    < Label  için = " frmKayitSozlesme " > < a  href =" # " > Üyelik Sözleşmesi </ a > ni Kabul Ediyorum. </ label >
                                </ div >
                            </ div >
                            < div  class = " col-sm-4 text-right " >
                                < düğme  türü = " düğme " tür = " gönder " id = " btnfrmKayit " class = " btn btn-birincil btn-blok " > Kayıt </ düğmesi >
                            </ div >
                        </ div >
                    </ form >
                </ div >
            </ div >
        </ div >
    </ bölüm >

<? php?  içermektedir  "inc / footer.php" ; ?>


***Kayıt Doğrulama Kodu
  
<? Php
içerir  "inc / header.php" ;

$ veri = $ db -> hazırlayın ( 'SELECT kul_eposta, kul_eposta_dogrulama_kod KULLANICILARI NEREDEN kul_eposta_dogrulama_kod =?' );
$ veri -> execute ( dizi ( g ( 'dogrulama' )));
$ v = $ veri -> fetchAll ( PDO :: FETCH_ASSOC );
$ say = $ veri -> rowCount ();
if ( $ say ) {
    foreach ( $ V  olarak  $ kullanici );
    $ guncelle = $ db -> hazırlayın ( "UPDATE kullanicilar SET kul_eposta_dogrulama = 1 NEREDE kul_eposta =?" );

    $ guncelleme = $ guncelle -> execute ( dizi ( $ kullanici [ 'kul_eposta' ]));
    if ( $ guncelleme ) {
        echo  "<div class = 'alert alert-success'> E-posta adresiniz onaylanmıştır. </div>" ;
    }
}

içerir  "inc / footer.php" ; ?>


***Kayıt sonrasında şifre unutulduğu durumda şifre unutma butonu yardımıyla düzenleme gerçekleşir.
<? Php
içerir  "inc / header.php" ;
?>

    < section  class = " gövde işareti " >
    < div  class = " center-sign " >
        < div  class = " panel panel-sign " >
            < div  class = " panel-title-sign mt-xl metin merkezi " >
                < h4  class = " renk-birincil yazı tipi-ağırlık-yarım metin-4 metin-büyük harf mb-0 " > Şifrenizimi içindir? </ h4 >
            </ div >
            < div  class = " panel-body " >
                < p  class = " text-2 opacity-7 " > Boyut şifresi sıfırlanmıştır için bir bağlantı göndereceğiz. </ Br > Lütfen e-posta adresinizi giriniz. </ p >
                < form  action = " / " id = " frmLostPassword " method = " post " class = " ihtiyaç doğrulama " >
                    < div  class = " form-row " >
                        < div  class = " form-group col " >
                            < label  class = " font-weight-bold text-info text-2 " > E-posta Adresi </ label >
                            < input  type = " text " value = "" class = " form-kontrol form-control-lg " gerekli >
                        </ div >
                    </ div >
                    <! - Doğrulama ->
                    < div  class = " form-row " >
                        < div  class = " form-group col " >
                            <? Php
                            $ S1 = rand ( 1 , 9 );
                            $ S2 = rand ( 1 , 9 );
                            $ t = $ s1 + $ s2 ;
                            $ y = md5 ( $ t );
                            ?>
                            < label  for = " password "
                                   class = " font-weight-bold metni-bilgi metni-2 " >
                                <? Php
                                echo  "$ s1 + $ s2 sayılarının toplamını girin" ;
                                ?>
                            </ label >
                            < input  class = " form-kontrol form-control-lg " tür = " gizli "
                                   value = " <? php  echo  $ y ; ?> " name = " toplam " >
                        </ div >
                    </ div >
                    < div  class = " input-group input-group-icon " >
                        < input  type = " text " value = "" name = " dkodu " class = " form-kontrol form-control-lg " gerekli >
                    </ div >
                    < Br >
                    <! - Doğrulama ->
                    < div  class = " form-row " >
                        < div  class = " form-group " >
                            < düğme  türü = " düğme "   id = " btnSifre_Unuttum " type = " gönder " class = " btn btn-birincil btn-modern btn-lg btn-blok gizli-xs " > Gönder </ düğmesi >
                            < düğme  türü = " düğme "   id = " btnSifre_Unuttum " type = " gönder " class = " btn btn-birincil btn-modern btn-blok btn-lg visible-xs mt-lg " > Gönder </ düğme >
                        </ div >  </ div >
                    </ div >
                </ form >
            </ div >
        </ div >
    </ div >
    </ bölüm >


<? php?  içermektedir  "inc / footer.php" ; ?>
 



***Giriş Sayfası : Kayıt işlemleri gerçekleştikten sonra giriş sayfasından anasayfaya yönelim gerçekleşir.
<? Php
içerir  "inc / header.php" ;
?>

    < section  class = " gövde işareti " >
        < div  class = " center-sign " >
            < div  class = " panel panel-sign " >
                < div  class = " panel-title-sign mt-xl text-right " >
                    < h2  class = " başlık metni-büyük harf metin-ağırlık-kalın m-none " > < i  class = " fa fa-user mr-xs " > </ i > Giriş </ h2 >
                </ div >
                < div  class = " panel-body " >
                    <! - UYARI ->
                    < div  id = " ygirisAlert " > </ div >

                    <! - UYARI ->
                    < form   id = " frmSignIn " method = " yazı " >
                        < div  class = " form-group mb-lg " >
                            < label > E-posta Adresi </ label >
                            < div  class = " input-group input-group-icon " >
                                < input  name = " eposta " type = " text " class = " form-kontrol input-lg "
                                <? php  if ( isset ( $ _COOKIE [ 'eposta' ])) {   echo  "value = '" . $ _COOKIE [ 'eposta' ]. "'" ; } ?> />
                                < span  class = " input-group-addon " >
										< span  class = " icon icon-lg " >
											< i  class = " fa fa-user " > </ i >
										</ span >
									</ span >
                            </ div >
                        </ div >
                        < div  class = " form-group mb-lg " >
                            < div  class = " clearfix " >
                                < label  class = " pull-left " > Şifre </ label >
                                < Bir  href = " -sifremi unuttum.php " class =" pull-sağ " > Şifreni mi unuttun? </ a >
                            </ div >
                            < div  class = " input-group input-group-icon " >
                                < İnput  adı = " sifre " tipi =" password " class =" form-kontrol girişi-lg " />
                                < span  class = " input-group-addon " >
										< span  class = " icon icon-lg " >
											< i  class = " fa fa-lock " > </ i >
										</ span >
									</ span >
                            </ div >
                        </ div >
                        < div  class = " form-group mb-lg " >
                            < div  class = " clearfix " >
                                <? Php
                                $ S1 = rand ( 1 , 9 );
                                $ S2 = rand ( 1 , 9 );
                                $ t = $ s1 + $ s2 ;
                                $ y = md5 ( $ t );
                                ?>
                                < label  class = " pull-left " id = " giris_dogrulama_text " >
                                    <? Php
                                    echo  "$ s1 + $ s2 sayılarının toplamını girin." ;
                                    ?>
                                </ label >
                                < label  class = " pull-right " > Doğrulama </ label >
                                < input  id = " giris_dogrulama_input " class = " form-denetim form-denetim-lg " type = " gizli "
                                       value = " <? php  echo  $ y ; ?> " name = " toplam " >
                            </ div >
                            < div  class = " input-group input-group-icon " >
                                < input  name = " dkodu " type = " text " class = " form-kontrol input-lg " />
                                < span  class = " input-group-addon " >
										< span  class = " icon icon-lg " >
											< i  class = " fa fa-lock " > </ i >
										</ span >
									</ span >
                            </ div >
                        </ div >
                        < div  class = " row " >
                            < div  class = " col-sm-8 " >
                                < div  class = " onay kutusu-özel onay kutusu-varsayılan " >
                                    < input  name = " rememberme " type = " onay kutusu " />
                                    < label  for = " RememberMe " > Hatırla </ label >
                                </ div >
                            </ div >
                            < div  class = " col-sm-4 text-right " >
                                < düğme  türü = " düğme "   id = " btnSignIn " type = " gönder " class = " btn btn-birincil btn-block " > Giriş </ düğmesi >
                            </ div >

                        </ div >
                    </ form >
                </ div >
            </ div >
        </ div >
    </ bölüm >

<? php?  içermektedir  "inc / footer.php" ; ?>

***Anasayfa : Anasyafadaki içerik kısımların butonların ve görsellerin işlevselliği kodlanmıştır.

<? php?  içermektedir  "inc / header.php" ;
if ( isset ( $ _SESSION [ 'yetki' ]))) {
    $ bakiye_sorgula = $ db -> hazırlayın ( 'SELECT kul_bakiye KULLANICILARI NEREDEN kul_id =?' );
    $ bakiye_sorgula -> execute ( dizi ( $ _SESSION [ 'kul_id' ]));
    $ V = $ bakiye_sorgula -> fetchAll ( PDO :: FETCH_ASSOC );
    foreach ( $ V  olarak  $ kul_bilgilerim );
    $ _SESSION [ 'bakiye' ] = $ kul_bilgilerim [ 'kul_bakiye' ];
} // sayfa açtığında bakiyemizi gerekiyoruz

$ link = "http://bigpara.hurriyet.com.tr/borsa/canli-borsa/" ;
$ İcerik = file_get_contents ( $ linki );
$ icerik = preg_replace ( '~ [\ r \ n] ~' , '' , $ icerik );
$ icerik = preg_replace ( '~ [] ~' , '' , $ icerik );
///
$ h_td_sembol = dizi ();
$ h_td_sembol = ara ( 'target = "_ blank">' , '</a>' , $ icerik ); // hisse adlarının dizisi [0] - [99] arası 100 hisse
$ tum_hisse_dizileri = dizi ();
///
$ komisyon = 1.003 ;

?>
< section  role = " ana " sınıf = " içerik-gövde " >
    < section  class = " section bg-color-quy " >
    < section  class = " section bg-renk-kuaterner özel dolgu-4 border-0 my-0 " >
            < div  class = " container " >
                < div  class = " satır mb-3 " >
                    < div  class = " col " >

                        < div  class = " satır hizalama öğeleri merkezi " >
                            < div  class = " col-lg-6 " >
                                <! - masa duyarlı-lg ->
                                < table  class = " table table-bordered table-strip table-sm mb-0 " >
                                    < h3  class = " özel-birincil-yazı tipi metin merkezi özel-yazı tipi boyutu-3 yazı tipi-ağırlık-normal "
                                    > En Çok Yükselenler </ h3 >
                                    < Thead >
                                    < tr >
                                        < th  class = " metin merkezi " scope = " col " > Menkul Adı </ th >
                                        < th  class = " text-center " scope = " col " > Durum </ th >
                                        < th  class = " text-center " scope = " col " > Son Değeri </ th >
                                        < th  class = " text-center " scope = " col " > (%) Fark </ th >
                                    </ tr >
                                    </ thead >
                                    < tbody >
                                    <? Php
                                    için ( $ sayi = 0 ; $ sayi < 100 ; $ sayi ++) {
                                        $ tum_hiss = dizi ();
                                        $ hisse_tekil_yuzde = ara ( 'h_td_yuzde_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                                        $ hisse_tekil_fiyat = ara ( 'h_td_fiyat_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                                        array_push ( $ tum_hiss , $ h_td_sembol [ $ sayi ], convert_virgül_nokta ( $ hisse_tekil_yuzde [ 0 ]), convert_virgül_nokta ( $ hisse_tekil_fiyat [ 0 ]));
                                        array_push ( $ tum_hisse_dizileri , $ tum_hiss );

                                    }
                                    $ sıralanmış = val_sort ( $ tum_hisse_dizileri , 1 ); // 1 = Yüzde
                                    için ( $ sayi = 99 ; $ sayi > 94 ; $ sayi -) {
                                        ?>
                                        < tr >
                                            < td  class = " metin merkezi "
                                                id = " hisse_yukselen_sembol_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ sıralanmış [ $ sayi ] [ 0 ]; ?> </ td >
                                            < td  class = " text-center " > < i  id = " hisse_yukselen_durum_ <? php  echo  $ sayi ; ?> "
                                                                       class = " <? php
                                                                       if ( convert_virgül_nokta ( $ sıralanmış [ $ sayi ] [ 1 ])> 0 ) {
                                                                           echo  "fas fa-ok-daire-yukarı metin-başarı" ;
                                                                       } elseif ( convert_virgül_nokta ( $ sıralanmış [ $ sayi ] [ 1 ]) == 0 ) {
                                                                           echo  "fas fa-minus text-info" ;
                                                                       } başka {
                                                                           echo  "fas fa-arrow-circle-down metin tehlikesi" ;
                                                                       }
                                                                       ?> " > </ i > </ td >
                                            < td  class = " metin merkezi "
                                                id = " hisse_yukselen_son_deger_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ sıralanmış [ $ sayi ] [ 2 ]; ?> </ td >
                                            < td  class = " metin merkezi "
                                                id = " hisse_yukselen_fark_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ sıralanmış [ $ sayi ] [ 1 ]; ?> </ td >
                                        </ tr >
                                    <? php } ?>
                                    </ tbody >
                                </ tablo >
                            </ div >
                            < div  class = " col-lg-6 " >
                                < table  class = " table table-bordered table-strip table-sm mb-0 " >
                                    < h3  class = " özel-birincil-yazı tipi metin merkezi özel-yazı tipi boyutu-3 yazı tipi-ağırlık-normal "
                                    > En Çok Düşenler </ h3 >
                                    < Thead >
                                    < tr >
                                        < th  class = " metin merkezi " scope = " col " > Menkul Adı </ th >
                                        < th  class = " text-center " scope = " col " > Durum </ th >
                                        < th  class = " text-center " scope = " col " > Son Değeri </ th >
                                        < th  class = " text-center " scope = " col " > (%) Fark </ th >
                                    </ tr >
                                    </ thead >
                                    < tbody >
                                    <? Php
                                    için ( $ sayi = 0 ; $ sayi < 5 ; $ sayi ++) {
                                        ?>
                                        < tr >
                                            < td  class = " metin merkezi "
                                                id = " hisse_dusen_sembol_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ sıralanmış [ $ sayi ] [ 0 ]; ?> </ td >
                                            < td  class = " text-center " > < i  id = " hisse_dusen_durum_ <? php  echo  $ sayi ; ?> "
                                                                       class = " <? php
                                                                       if ( convert_virgül_nokta ( $ sıralanmış [ $ sayi ] [ 1 ])> 0 ) {
                                                                           echo  "fas fa-ok-daire-yukarı metin-başarı" ;
                                                                       } elseif ( convert_virgül_nokta ( $ sıralanmış [ $ sayi ] [ 1 ]) == 0 ) {
                                                                           echo  "fas fa-minus text-info" ;
                                                                       } başka {
                                                                           echo  "fas fa-arrow-circle-down metin tehlikesi" ;
                                                                       }
                                                                       ?> " > </ i > </ td >
                                            < td  class = " metin merkezi "
                                                id = " hisse_dusen_son_deger_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ sıralanmış [ $ sayi ] [ 2 ]; ?> </ td >
                                            < td  class = " metin merkezi "
                                                id = " hisse_dusen_fark_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ sıralanmış [ $ sayi ] [ 1 ]; ?> </ td >
                                        </ tr >
                                    <? php } ?>
                                    </ tbody >
                                </ tablo >
                            </ div >
                        </ div >
                    </ div >
                </ div >
            </ div >
        </ bölüm >
    < section  class = " section bg-renk-kuaterner özel dolgu-4 border-0 my-0 " >
        < div  class = " table-active " >
            < h2  class = " özel-birincil-yazı tipi metin merkezi özel-yazı tipi boyutu -3 yazı tipi-ağırlık-normal " > BİST100 Hisse Verileri </ h2 >
            < table  class = " table tablo-bordered tablo-çizgili mb-none " id = " datatable-default " >
                < Thead >
                < tr >
                    < th  scope = " col " > Menkul </ th >
                    < th  class = " text-center " scope = " col " > Durum </ th >
                    < th  class = " text-center " scope = " col " > Değeri </ th >
                    < th  class = " text-center hidden-xs " scope = " col " > Fark </ th >
                    < th  class = " text-center " scope = " col " > (%) Fark </ th >
                    < th  class = " text-center hidden-xs " scope = " col " > En Düşük </ th >
                    < th  class = " text-center hidden-xs " scope = " col " > En Yüksek </ th >
                    < th  class = " text-center hidden-xs " scope = " col " > Hacim (Parti) </ th >
                    < th  class = " text-center hidden-xs " scope = " col " > Hacim (TL) </ th >
                    < th  class = " text-center hidden-xs " scope = " col " > Zaman </ th >
                    <? Php
                    if ( isset ( $ _SESSION [ 'yetki' ]))) {
                        echo  "<th class = 'metin merkezi' scope = 'col'> Alış </th>
                              <th class = 'text-center' scope = 'col'> Satış </th> " ;
                    }
                    ?>
                </ tr >
                </ thead >
                < tbody >
                <? Php
                için ( $ sayi = 0 ; $ sayi < 100 ; $ sayi ++) {
                ///
                $ h_td_yuzde_id_deger = ara ( 'h_td_yuzde_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_fiyat_id_deger = ara ( 'h_td_fiyat_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_farktl_id_deger = ara ( 'h_td_farktl_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_dusuk_id_deger = ara ( 'h_td_dusuk_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_yuksek_id_deger = ara ( 'h_td_yuksek_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_hacimlot_id_deger = ara ( 'h_td_hacimlot_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_hacimtl_id_deger = ara ( 'h_td_hacimtl_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                $ h_td_saat_id_deger = ara ( 'h_td_saat_id_' . $ h_td_sembol [ $ sayi ]. '">' , '</li>' , $ icerik );
                ///
                ?>
                < tr >
                    < td  class = " metin merkezi "
                        id = " hisse_sembol_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_sembol [ $ sayi ]; ?> </ td >
                    < td  class = " text-center " > < i  id = " hisse_durum_ <? php  echo  $ sayi ; ?> " class = "
                        <? Php
                        if ( convert_virgül_nokta ( $ h_td_yuzde_id_deger [ 0 ])> 0 ) {
                            echo  "fas fa-ok-daire-yukarı metin-başarı" ;
                        } elseif ( convert_virgül_nokta ( $ h_td_yuzde_id_deger [ 0 ]) == 0 ) {
                            echo  "fas fa-minus text-info" ;
                        } başka {
                            echo  "fas fa-arrow-circle-down metin tehlikesi" ;
                        }
                        ?> " > </ i > </ td >
                    < td  class = " metin merkezi "
                        id = " hisse_son_deger_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_fiyat_id_deger [ 0 ]; ?> </ td >
                    < td  class = " center hidden-xs "
                        id = " hisse_fark_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_farktl_id_deger [ 0 ]; ?> </ td >
                    < td  class = " metin merkezi "
                        id = " hisse_fark_yuzde_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_yuzde_id_deger [ 0 ]; ?> </ td >
                    < td  class = " center hidden-xs "
                        id = " hisse_en_dusuk_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_dusuk_id_deger [ 0 ]; ?> </ td >
                    < td  class = " center hidden-xs "
                        id = " hisse_en_yuksek_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_yuksek_id_deger [ 0 ]; ?> </ td >
                    < td  class = " center hidden-xs "
                        id = " hisse_hacim_lot_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_hacimlot_id_deger [ 0 ]; ?> </ td >
                    < td  class = " center hidden-xs "
                        id = " hisse_hacim_tl_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_hacimtl_id_deger [ 0 ]; ?> </ td >
                    < td  class = " center hidden-xs "
                        id = " hisse_zaman_ <? php  echo  $ sayi ; ?> " > <? php  echo  $ h_td_saat_id_deger [ 0 ]; ?> </ td >
                    <? php  if ( isset ( $ _SESSION [ 'yetki' ]))) {
                        echo  "
                            <td class = 'text-center' id = 'hisse_alis_ " . $ sayi . "'>
                                <button id = 'btn_hisse_alis_ " . $ sayi . "' type = 'button' class = 'btn btn-başarı' form ile modal-form 'href =' # modalAlForm " . $ sayi . " '> AL </button>
                                
                                <div class = 'modal-blok modal-başlık-renk modal-blok-başarı mfp-hide' id = 'modalAlForm " . $ sayi . "'>
                                    <section class = 'panel'>
                                            <header class = 'panel heading'>
                                                <h4 class = 'panel-title' id = 'formModalLabel'> Satın Al </h4>
                                            </ Pompa çıkışı>
                                            <div class = 'panel-body'>
                                                <! - UYARI ->
                                                <div id = 'hisse_alim_alert'> </div>
                                                <! - UYARI ->
                                                <form id = 'hisse_alim_form_ " . $ sayi . "' class = 'mb-4' novalidate = 'novalidate'>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Hisse Adı: </label>
                                                        <label id = 'hisse_alim_form_sembol_ " . $ sayi . "' class = 'col-sm-7 metin merkezi mb-0'> " . $ h_td_sembol [ $ sayi ]. " </label>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Alış Tutarı: </label>
                                                        <label id = 'hisse_deger_alim_ " . $ sayi . "' class = 'col-sm-7 metin merkezi mb-0'> " . convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ]). " </label>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Bakiyeniz: </label>
                                                        <label class = 'col-sm-4 metin-sağ mb-0'> " . $ _SESSION [ 'bakiye' ]. " </label> <span class = 'col-sm-4 metin-sol mb-0' > & # x20BA; </ span>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Alınmak İstenen Belirt: </label>
                                                        <div class = 'col-sm-7 metin merkezi'>
                                                            <input id = 'range_ " . $ sayi . "' type = 'range' min = '1' max = '" . intval ( $ _SESSION [ ' bakiye ' ]) / ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ]) ) * $ komisyon ). "'onchange =' alis_hesapla" . $ sayi . "() '/>
                                                            <output id = 'rangevalue " . $ sayi . "'> " ;
                        if (( intval ( $ _SESSION [ 'bakiye' ]) / ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) * $ komisyon ) * 0.5 )> = 1 ) {
                            $ range_ = intval ( intval ( $ _SESSION [ 'bakiye' ]) / ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) * $ komisyon ) * 0.5 );
                        } elseif ( $ _SESSION [ 'bakiye' ]> convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) { $ range_ = 1 ;} başka { $ range_ = 0 ;}
                        yankı  "" . $ range_ . "</ çıkış>
                                                        </ Div>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Komisyon (Binde 3): </label>
                                                        <label id = 'komisyon " . $ sayi . "' class = 'col-sm-4 text-right mb-0'> " . round ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) * ( $ komisyon - 1 ) *   $ range_ , 2 ). "</label> <span class = 'col-sm-4 metin-sol mb-0'> & # x20BA; </span>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Toplam Ödenecek Tutar: </label>
                                                        <label id = 'toplam_odenecek_alim_tutar " . $ sayi . "' class = 'col-sm-4 metin-sağ mb-0'>
                                                        " . round ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) * ( $ komisyon ) * $ range_ , 2 ). "
                                                       </ Label>
                                                       <Script>
                                                        işlev alis_hesapla " . $ sayi . " () {
                                                            var alis = $ ('# hisse_deger_alim_ " . $ sayi . "') .text ();
                                                            var miktar = $ ('# range_ " . $ sayi . "') .val ();
                                                            $ ('# rangevalue " . $ sayi . "') .text ($ ('# range_ " . $ sayi . "') .val ());
                                                            $ ('# komisyon " . $ sayi . "') .text ((alis * miktar * (" . $ komisyon . " -1)). toFixed (2));
                                                            $ ('# toplam_odenecek_alim_tutar " . $ sayi . "') .text ((alis * miktar * (" . $ komisyon . ")). toFixed (2));
                                                        }
                                                        </ Script>
                                                       <span class = 'col-sm-4 metin-sol mb-0'> & # x20BA; </span>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-12 metin merkezi mb-0'>    
                                                        " ;
                        if ( $ range_ == 0 ) { echo  "Yeterli Bakiyeniz Bulunmaktadır." ; }
                        echo  "                                                    
                                                        </ Label>
                                                    </ Div>
                                                </ Form>
                                            </ Div>
                                            <div class = 'panel-footer'>
                                                <div class = 'row'>
                                                    <div class = 'col-md-12 metin-sağ'>
                                                        <düğme türü = 'düğme' sınıf = 'btn btn-light modal-dismiss'> Kapat </button>
                                                        <button type = 'button' id = 'hisse_al_btn_ " . $ sayi . "' type = 'gönder' sınıf = 'btn btn-success' " ;
                        eğer ( $ range_ == 0 ) { echo  "özürlü" ; }
                        echo  "> Satın Al </button>
                                                    </ Div>
                                                </ Div>
                                            </ Div>
                                    </ Section>
                                </ Div>
                            </td> " ;


                        echo  "
                            <td class = 'text-center' id = 'hisse_satis_ " . $ sayi . "'>
                                <button id = 'btn_hisse_satis_ " . $ sayi . "' type = 'button' class = 'btn btn-tehlikeli' href = '# modalSatForm "biçimiyle . $ sayi . "'> SAT </button>
                                
                                <div class = 'modal-blok modal-başlık-renk modal-blok-tehlike mfp-hide' id = 'modalSatForm " . $ sayi . "'>
                                    <section class = 'panel'>
                                            <header class = 'panel heading'>
                                                <h4 class = 'panel-title' id = 'formModalLabel'> Cts </h4>
                                            </ Pompa çıkışı>
                                            <div class = 'panel-body'>
                                                <form id = 'demo-form' class = 'mb-4' novalidate = 'novalidate'>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Hisse Adı: </label>
                                                        <label class = 'col-sm-7 metin merkezi mb-0'> " . $ h_td_sembol [ $ sayi ]. " </label>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Satış Tutarı: </label>
                                                        <label id = 'hisse_deger_satim_ " . $ sayi . "' class = 'col-sm-7 metin merkezi mb-0' onchange = 'satis_hesapla " . $ sayi . " ()'> " . convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ]). "</label>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Portföyümdeki Hisse Adedi: </label>
                                                        <label id = 'hisse_varlik_elde_ " . $ sayi . "' class = 'col-sm-4 text-right mb-0'> " ;
                                                    $ veri = $ db -> hazırlayın ( 'SELECT varlik_elde FROM varliklar NEREDE varlik_kul_id =? ve varlik_hisse_sembol =?' );
                                                    $ veri -> execute ( dizi ( $ _SESSION [ 'kul_id' ], $ h_td_sembol [ $ sayi ]));
                                                    $ v = $ veri -> fetchAll ( PDO :: FETCH_ASSOC );
                                                    foreach ( $ v  ,  $ varlik_elde olarak );
                                                    echo  $ varlik_elde [ 'varlik_elde' ];
                                                    echo  "</label>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Satilmak İstenen Şart: </label>
                                                        <div class = 'col-sm-7 metin merkezi'>
                                                            <input id = 'range_satim " . $ sayi . "' type = 'range' min = '1' max = '" . $ varlik_elde [ ' varlik_elde ' ]. "' onchange = 'satis_hesapla " . $ sayi . " () '/>
                                                            <output id = 'rangevaluesatim " . $ sayi . "'> 1 </output>
                                                        </ Div>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Komisyon (Binde 3): </label>
                                                        <label id = 'komisyonsatim " . $ sayi . "' class = 'col-sm-4 text-right mb-0'> " . round ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) * ( $ komisyon - 1 ) * 50 , 2 ). "</label> <span class = 'col-sm-4 metin-sol mb-0'> & # x20BA; </span>
                                                    </ Div>
                                                    <div class = 'form-grup satırı align-items-center'>
                                                        <label class = 'col-sm-4 metin-sol metin-sm-sağ mb-0'> Toplam Alinacak Tutarı: </label>
                                                        <label id = 'toplam_odenecek_satim_tutar " . $ sayi . "' class = 'col-sm-4 metin-sağ mb-0'>
                                                        <Script>
                                                            fonksiyon satis_hesapla " . $ sayi . " () {
                                                                var satis = $ ('# hisse_deger_satim_ " . $ sayi . "') .text ();
                                                                var miktar_satis = $ ('# range_satim " . $ sayi . "') .val ();
                                                                $ ('# rangevaluesatim " . $ sayi . "') .text ($ ('# range_satim " . $ sayi . "') .val ());
                                                                $ ('# komisyonsatim " . $ sayi . "') .text ((satis * miktar_satis * (" . $ komisyon . " -1)). toFixed (2));
                                                                $ ('# toplam_odenecek_satim_tutar " . $ sayi . "') .text ((satis * miktar_satis * (" . $ komisyon . ")). toFixed (2));
                                                            }
                                                        </ Script>
                                                        " . round ( floatval ( convert_virgül_nokta ( $ h_td_fiyat_id_deger [ 0 ])) * ( $ komisyon ) * 50 , 2 ). "
                                                       </ Label>
                                                       <span class = 'col-sm-4 metin-sol mb-0'> & # x20BA; </span>
                                                    </ Div>
                                                </ Form>
                                            </ Div>
                                            <div class = 'panel-footer'>
                                                <div class = 'row'>
                                                    <div class = 'col-md-12 metin-sağ'>
                                                        <düğme türü = 'düğme' sınıf = 'btn btn-light modal-dismiss'> Kapat </button>
                                                        <düğme türü = 'düğme' sınıf = 'btn btn-danger modal-confirm'> Cts </button>
                                                    </ Div>
                                                </ Div>
                                            </ Div>
                                    </ Section>
                                </ Div>
                            </td> " ;
                    } başka {
                    } ?>
                    <? php } ?>
                </ tbody >
            </ tablo >
        </ div >
    </ bölüm >
</ bölüm >
<? php?  içermektedir  "inc / footer.php" ; ?>


***Geçmiş alım-satım tabloların gösterildiği kod kısmıdır.

<? Php
içerir  "inc / header.php" ;
kullanicikontrol ();
?>

    < section  role = " ana " sınıf = " içerik-gövde " >
        < div  class = " conteiner " >
            < div  class = " col-md " >
                < section  class = " panel panel-danger " >
                    < header  class = " panel-heading " >
                        < h2  class = " panel-title " > Geçmiş Alım-Satımlarım </ h2 >
                        < div  class = " panel-actions " >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon geçiş " veri panel mafsallı > </ a >
                        </ div >
                    </ header >
                    < div  class = " panel-body " >
                        < table  class = " table tablo-bordered tablo-çizgili mb-none " id = " datatable-default " >
                            < Thead >
                            < tr >
                                < th > * </ th >
                                < th > * </ th >
                                < th > * </ th >
                                < th  class = " hidden-xs " > ** </ th >
                                < th  class = " hidden-xs " > * </ th >
                            </ tr >
                            </ thead >
                            < tbody >
                            < tr >
                                < td > *** </ td >
                                < td > *** </ td >
                                < td > *** </ td >
                                < td  class = " center hidden-xs " > ****** </ td >
                                < td  class = " center hidden-xs " > ****** </ td >
                            </ tr >
                            </ tbody >
                        </ tablo >
                    </ div >
                </ bölüm >
            </ div >
        </ div >
    </ bölüm >
    <! - KODLAR BURAYA ->


<? php?  içermektedir  "inc / footer.php" ; ?>

***Liglerin gösterildiği kod kısmıdır.
<? Php
içerir  "inc / header.php" ;
kullanicikontrol ();
?>
    < section  role = " ana " sınıf = " içerik-gövde " >
        < div  class = " conteiner " >
            < div  class = " col-md " >
                < section  class = " panel panel-info " >
                    < header  class = " panel-heading " >
                        < h2  class = " panel-title " > Ligler </ h2 >
                        < div  class = " panel-actions " >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon geçiş " veri panel mafsallı > </ a >
                        </ div >
                    </ header >
                    < div  class = " panel-body " >
                        < table  class = " table tablo-bordered tablo-çizgili mb-none " id = " datatable-default " >
                            < Thead >
                            < tr >
                                < th > * </ th >
                                < th > * </ th >
                                < th > * </ th >
                                < th > * </ th >
                                < th > Lige Gir </ th >
                            </ tr >
                            </ thead >
                            < tbody >
                            < tr >
                                < td > *** </ td >
                                < td > *** </ td >
                                < td > *** </ td >
                                < td > ****** </ td >
                                < td > ****** </ td >
                            </ tr >
                            </ tbody >
                        </ tablo >
                    </ div >
                </ bölüm >
            </ div >
        </ div >
    </ bölüm >
    <! - KODLAR BURAYA ->
<? php?  içermektedir  "inc / footer.php" ; ?>


***Log kayıtlarının gerçekleştiği kod kısmıdır.
<? Php
içerir  "inc / header.php" ;
yoneticikontrol ();
?>
    < section  role = " ana " sınıf = " içerik-gövde " >
        < div  class = " conteiner " >
            < div  class = " col-md " >
                < section  class = " panel panel-karanlık " >
                    < header  class = " panel-heading " >
                        < h2  class = " panel-title " > Günlük Kayıtları </ h2 >
                        < div  class = " panel-actions " >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon geçiş " veri panel mafsallı > </ a >
                        </ div >
                    </ header >
                    < div  class = " panel-body " >
                        < table  class = " table tablo-bordered tablo-çizgili mb-none " id = " datatable-default " >
                            < Thead >
                            < tr >
                                < th > Kimlik </ th >
                                < th > Reklam </ th >
                                < th > Soyad </ th >
                                < th > Eylem </ th >
                                < th > Açıklama </ th >
                                < th > Zamanı </ th >
                            </ tr >
                            </ thead >
                            < tbody >
                            <? Php
                            işlev  günlüğü ()
                            {
                                küresel  $ db ;
                                $ veri = $ db -> hazırlayın ( "SELECT log.log_id, kullanicilar.kul_Ad, kullanicilar.kul_Soyad, log.log_eylem, log.log_aciklama, log.log_zaman FROM log iç birleştirmek log.log_kul_id = kullanicilar.kul_Id" );
                                $ veri -> execute ( dizi ());
                                $ v = $ veri -> fetchAll (pdo :: FETCH_ASSOC );
                                $ say = $ veri -> rowCount ();
                                if ( $ say ) {
                                    foreach ( $ v  as  $ tum_kullanicilar ) {
                                        ?>
                                        < tr >
                                            < Td > <? Php?  Echo  $ tum_kullanicilar [ 'log_id' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_kullanicilar [ 'kul_Ad' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_kullanicilar [ 'kul_Soyad' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_kullanicilar [ 'log_eylem' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_kullanicilar [ 'log_aciklama' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_kullanicilar [ 'log_zaman' ]; ?> </ td >
                                        </ tr >
                                        <? Php
                                    }
                                }
                            }

                            loglar ();
                            ?>
                            </ tbody >
                        </ tablo >
                    </ div >
                </ bölüm >
            </ div >
        </ div >
    </ bölüm >
    <! - KODLAR BURAYA ->


<? php?  içermektedir  "inc / footer.php" ; ?>

*** Gerekli işlemler yapan kullanıcının profil ekranın kod kısmı şu şekildedir:
<? Php
içerir  "inc / header.php" ;
kullanicikontrol ();
?>

< section   role = " ana " sınıf = " içerik-gövde " >
    < div  class = " container " >
        < div  class = " row " >
            < div  class = " col-md-4 col-lg-3 " >
                < section  class = " panel " >
                    < div  class = " panel-body " >

                        < div  class = " row " >
                            < div  class = " küçük-12 orta-2 büyük-2 sütun " >
                                < div  class = " circle " >
                                    <! - Kullanıcı Profili Resmi ->
                                    < img  class = " profile-picture " src = " img /! log-user.jpg " width = " 250 " height = " 250 " >

                                    <! - Varsayılan Resim ->
                                    <! - <i class = "fa fa-kullanıcı fa-5x"> </i> ->
                                </ div >
                                < div  class = " p-image " >
                                    < i  class = " fa fa-camera upload-button " > </ i >
                                    < input  class = " dosya yükleme " type = " dosya " kabul et = " image / * " />
                                </ div >
                            </ div >
                        </ div >

                    </ div >
                </ bölüm >
                < section  class = " panel " >
                    < header  class = " panel-heading " >
                        < div  class = " panel-actions " >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon geçiş " veri panel mafsallı > </ a >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon kapatmak " veri panel kapatmak > </ a >
                        </ div >
                        < h2  class = " panel-title " > Bilgiler </ h2 >
                    </ header >
                    < div  class = " panel-body " >
                        < ul  class = " basit kayıt sonrası " >
                            < li >
                                < div  class = " post-info " >
                                    < div  > Son Çevrimiçi Olunan Tarih </ div >
                                    < div  class = " text-center " > 02/01/2020 </ div >
                                </ div >
                            </ li >
                            < li >

                            </ li >
                            < li >

                            </ li >
                        </ ul >
                    </ div >
                </ bölüm >
            </ div >
            < div  class = " col-md-8 col-lg-6 " >
                < div  class = " tabs " >
                    < ul  class = " nav nav-tabs sekmeleri-birincil " >
                        < li  class = " active " >
                            < Bir  href = " #overview " veri geçiş =" sekme " > Kullanıcı Bilgileri </ a >
                        </ li >
                    </ ul >
                    < div  class = " sekme içeriği " >
                        < div  id = " genel bakış " class = " sekme bölmesi etkin " >
                            < form  class = " form-horizontal " yöntem = " get " >
                                < alan kümesi >
                                    < div  class = " form-group " >
                                        < Label  class = " col-md-3 kontrol etiketli " için =" profileFirstName " > Reklam </ label >
                                        < div  class = " col-md-8 " >
                                            < input  type = " text " class = " form-control " id = " profileFirstName " >
                                        </ div >
                                    </ div >
                                    < div  class = " form-group " >
                                        < Label  class = " col-md-3 kontrol etiketi " için =" profileLastName " > Soyad </ etiket >
                                        < div  class = " col-md-8 " >
                                            < input  type = " text " class = " form-control " id = " profileLastName " >
                                        </ div >
                                    </ div >
                                    < div  class = " form-group " >
                                        < Etiket  sınıfı = " col-MD-3 kontrol etiketli " için =" profileAddress " > e-posta </ etiket >
                                        < div  class = " col-md-8 " >
                                            < input  type = " email " sınıf = " form kontrolü " id = " profileAddress " >
                                        </ div >
                                    </ div >
                                    < div  class = " form-group " >
                                        < Label  class = " col-md-3 kontrol etiketi " için =" ProfiliŞirket " > Cep teleonu </ label >
                                        < div  class = " col-md-8 " >
                                            < input  type = " text " class = " form-control " id = " profileCompany " >
                                        </ div >
                                    </ div >
                                    < div  class = " form-group " >
                                        < Label  class = " col-md-3 kontrol etiketi " için =" ProfiliŞirket " > Doğum Tarihi </ label >
                                        < div  class = " col-md-8 " >
                                            < input  type = " date " class = " form-kontrol " id = " profileCompany " >
                                        </ div >
                                    </ div >
                                </ fieldset >
                                < hr  class = " dotted tall " >
                                < h4  class = " mb-xlg " > Şifre girişi </ h4 >
                                < fieldset  sınıfı = " mb-xl " >
                                    < div  class = " form-group " >
                                        < Label  class = " col-md-3 kontrol etiketi " için =" profileNewPassword " > Yeni Şifre </ label >
                                        < div  class = " col-md-8 " >
                                            < input  type = " text " class = " form-control " id = " profileNewPassword " >
                                        </ div >
                                    </ div >
                                    < div  class = " form-group " >
                                        < Label  class = " col-md-3 kontrol etiketi " için =" profileNewPasswordRepeat " > Yei Şifre Tekrar </ label >
                                        < div  class = " col-md-8 " >
                                            < input  type = " text " class = " form-control " id = " profileNewPasswordRepeat " >
                                        </ div >
                                    </ div >
                                </ fieldset >
                                < div  class = " panel-footer " >
                                    < div  class = " konteyner sıvısı " >
                                        < div  class = " col-md " >
                                            < düğme  türü = " gönder " sınıf = " btn btn-birincil btn-blok " > Kaydet </ button >
                                        </ div >
                                    </ div >
                                </ div >

                            </ form >

                        </ div >
                    </ div >
                </ div >
            </ div >
            < div  class = " col-md-12 col-lg-3 " >

                < h4  class = " mb-md " > Mali Bilgiler </ h4 >
                < ul  class = " basit kart listesi mb-xlg " >
                    < li  class = " info " >
                        < H3 > 12503,20 & # x20BA; </ h3 >
                        < p > Toplam Varlığım </ p >
                    </ li >
                    < li  class = " birincil " >
                        < h3 > 488 </ h3 >
                        < p > Elimdeki Lot </ p >
                    </ li >
                    < li  class = " warning " >
                        < h3  class = " fa fa-arrow-down " > % -4,36 </ h3 >
                        < p > Elimdeki Lotların Kar-Zarar Durumu </ p >
                    </ li >
                    < li  class = " success " >
                        < h3 > % 16 </ h3 >
                        < p > Son 1 aydaki Kar-Zarar Durumum </ p >
                    </ li >
                    < li  class = " dark " >
                        < h3 > % 1,025 </ h3 >
                        < p > Genel Kar-Zarar Durumum </ p >
                    </ li >
                </ ul >
            </ div >
        </ div >
        <! - end: sayfa ->

    </ div >
</ bölüm >

<? php?  içermektedir  "inc / footer.php" ; ?>

***Profil ekranın gösterilen mali durum bilgilerinin gösterilmesini sağlayan kod kısmıdır.

<? Php
içerir  "inc / header.php" ;
yoneticikontrol ();
?>
    < section  role = " ana " sınıf = " içerik-gövde " >
        < div  class = " conteiner " >
            < div  class = " col-md " >
                < section  class = " panel panel uyarısı " >
                    < header  class = " panel-heading " >
                        < h2  class = " panel-title " > Mali Durum </ h2 >
                        < div  class = " panel-actions " >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon geçiş " veri panel mafsallı > </ a >
                        </ div >
                    </ header >
                    < div  class = " panel-body " >
                        < table  class = " table tablo-bordered tablo-çizgili mb-none " id = " datatable-default " >
                            < Thead >
                            < tr >
                                < th > Kimlik </ th >
                                < th > Gelir Türü </ th >
                                < th > İşlem Adedi </ th >
                                < th > Gelir </ th >
                            </ tr >
                            </ thead >
                            < tbody >
                            < tr >
                                <? Php
                                işlev  alimlar ()
                                {
                                küresel  $ db ;
                                $ veri = $ db -> hazırlayın ( "SELECT COUNT (alim_hisse_komisyon) AS adet, SUM (alim_hisse_komisyon) AS toplam FROM alim" );
                                $ veri -> execute ( dizi ());
                                $ v = $ veri -> fetchAll (pdo :: FETCH_ASSOC );
                                $ say = $ veri -> rowCount ();
                                if ( $ say ) {
                                foreach ( $ v  ,  $ tum_alimlar olarak ) {
                                ?>
                            < tr >
                                < td > 1 </ td >
                                < td > Hisse Alım </ td >
                                < Td > <? Php?  Echo  $ tum_alimlar [ 'adet' ]; ?> </ td >
                                < td  class = " center " > <? php  echo  $ tum_alimlar [ 'toplam' ]; ?> < span > & # x20BA; </ span > </ td >
                                <? Php
                            }
                            }
                            }
                                alimlar ();
                            ?>
                            </ tr >
                            < tr >
                                <? Php
                                fonksiyon  satimlar ()
                                {
                                küresel  $ db ;
                                $ veri = $ db -> hazırlayın ( "SELECT COUNT (satim_hisse_komisyon) AS adet, SUM (satim_hisse_komisyon) AS toplam FROM satim" );
                                $ veri -> execute ( dizi ());
                                $ v = $ veri -> fetchAll (pdo :: FETCH_ASSOC );
                                $ say = $ veri -> rowCount ();
                                if ( $ say ) {
                                foreach ( $ v  as  $ tum_satimlar ) {
                                ?>
                            < tr >
                                < td > 2 </ td >
                                < td > Hisse Satım </ td >
                                < Td > <? Php?  Echo  $ tum_satimlar [ 'adet' ]; ?> </ td >
                                < td  class = " center " > <? php  echo  $ tum_satimlar [ 'toplam' ]; ?> < span > & # x20BA; </ span > </ td >
                                <? Php
                                }
                                }
                                }
                                satimlar ();
                                ?>
                            </ tr >
                            </ tbody >
                        </ tablo >
                    </ div >
                </ bölüm >
            </ div >
        </ div >
    </ bölüm >
    <! - KODLAR BURAYA ->


<? php?  içermektedir  "inc / footer.php" ; ?>


***Kullanıcının aktif varlıklarının gösterildiği kod kısmıdır.
<? Php
içerir  "inc / header.php" ;
kullanicikontrol ();
?>

    < section  role = " ana " sınıf = " içerik-gövde " >
        < div  class = " conteiner " >
            < div  class = " col-md " >
                < section  class = " panel panel başarısı " >
                    < header  class = " panel-heading " >
                        < h2  class = " panel-title " > Aktif Varlıklarım </ h2 >
                        < div  class = " panel-actions " >
                            < Bir  href = " # " sınıfı =" panel aksiyon panel aksiyon geçiş " veri panel mafsallı > </ a >
                        </ div >
                    </ header >
                    < div  class = " panel-body " >
                        < table  class = " table tablo-bordered tablo-çizgili mb-none " id = " datatable-default " >
                            < Thead >
                            < tr >
                                < th > * </ th >
                                < th > * </ th >
                                < th > * </ th >
                                < th  class = " hidden-xs " > ** </ th >
                                < th  class = " hidden-xs " > * </ th >
                            </ tr >
                            </ thead >
                            < tbody >
                            <? Php
                            işlev  aktif_varliklar ()
                            {
                                küresel  $ db ;
                                $ veri = $ db -> hazırla ( "SELECT * FROM varliklar" );
                                $ veri -> execute ( dizi ());
                                $ v = $ veri -> fetchAll (pdo :: FETCH_ASSOC );
                                $ say = $ veri -> rowCount ();
                                if ( $ say ) {
                                    foreach ( $ v  as  $ tum_aktif_varliklar ) {
                                        ?>
                                        < tr >
                                            < Td > <? Php?  Echo  $ tum_aktif_varliklar [ 'kul_Id' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_aktif_varliklar [ 'kul_Ad' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_aktif_varliklar [ 'kul_Soyad' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_aktif_varliklar [ 'kul_Eposta' ]; ?> </ td >
                                            < Td > <? Php?  Echo  $ tum_aktif_varliklar [ 'kul_Son_Giris_Tar' ]; ?> </ td >
                                        </ tr >
                                        <? Php
                                    }
                                }
                            }

                            aktif_varliklar ();
                            ?>
                            </ tbody >
                        </ tablo >
                    </ div >
                </ bölüm >
            </ div >
        </ div >
    </ bölüm >
    <! - KODLAR BURAYA ->


<? php?  içermektedir  "inc / footer.php" ; ?>


***İşlemler gerçekleştirildikten sonra günlük, haftalık ve aylık şekilde en çok yükselen ve en çok kaybeden özelliklerinin gösterildiği kod kısmıdır.
  
<?php
include "inc/header.php";
?>


    <section role="main" class="content-body">
        <div class="conteiner">
            <div class="tabs ">
                <ul class="nav nav-tabs nav-justified">
                    <li class="active">
                        <a href="#lig" data-toggle="tab" class="text-center" >LİG SIRALAMASI</a>
                    </li>
                    <li>
                        <a href="#kullanici" data-toggle="tab" class="text-center">KULLANICI SIRALAMASI</a>
                    </li>
                </ul>
                <div class="tab-content">
                    <div id="lig" class="tab-pane active">
                        <div class="tabs tabs-success">
                            <ul class="nav nav-tabs nav-justified">
                                <li>
                                    <a href="#lig_hafta" data-toggle="tab" class="text-center">HAFTALIK</a>
                                </li>
                                <li>
                                    <a href="#lig_ay" data-toggle="tab" class="text-center">AYLIK</a>
                                </li>
                                <li>
                                    <a href="#lig_genel" data-toggle="tab" class="text-center">GENEL</a>
                                </li>
                            </ul>
                            <div class="tab-content  tabs-danger">
                                <div id="lig_hafta" class="tab-pane active">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kazanç</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kazananlar_gun_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kazananlar_gun_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kazananlar_gun_TL_" . $sayi . "'>TL</td>
                                                    </tr> 
                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                                <div id="lig_ay" class="tab-pane">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kazanç</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kazananlar_hafta_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kazananlar_hafta_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kazananlar_hafta_TL_" . $sayi . "'>TL</td>
                                                                </tr> 
                                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>

                                </div>
                                <div id="lig_genel" class="tab-pane ">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kazanç</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kazananlar_ay_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kazananlar_ay_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kazananlar_ay_TL_" . $sayi . "'>TL</td>
                                                                </tr> 
                                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div id="kullanici" class="tab-pane">
                        <div class="tabs tabs-danger">
                            <ul class="nav nav-tabs nav-justified">
                                <li class="active">
                                    <a href="#kullanici_gun" data-toggle="tab" class="text-center">GÜNLÜK</a>
                                </li>
                                <li>
                                    <a href="#kullanici_hafta" data-toggle="tab" class="text-center">HAFTALIK</a>
                                </li>
                                <li>
                                    <a href="#kullanici_ay" data-toggle="tab" class="text-center">AYLIK</a>
                                </li>
                                <li>
                                    <a href="#kullanici_genel" data-toggle="tab" class="text-center">GENEL</a>
                                </li>
                            </ul>
                            <div class="tab-content  tabs-danger">
                                <div id="kullanici_gun" class="tab-pane active">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kayıp</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kaybedenler_gun_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kaybedenler_gun_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kaybedenler_gun_TL_" . $sayi . "'>TL</td>
                                                                </tr> 
                                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                                <div id="kullanici_hafta" class="tab-pane">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kayıp</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kaybedenler_hafta_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kaybedenler_hafta_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kaybedenler_hafta_TL_" . $sayi . "'>TL</td>
                                                                </tr> 
                                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                                <div id="kullanici_ay" class="tab-pane ">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kayıp</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kaybedenler_ay_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kaybedenler_ay_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kaybedenler_ay_TL_" . $sayi . "'>TL</td>
                                                                </tr> 
                                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                                <div id="kullanici_genel" class="tab-pane">
                                    <section class="panel">
                                        <div class="panel-body">
                                            <div class="table-responsive">
                                                <table class="table table-bordered">
                                                    <thead>
                                                    <tr>
                                                        <th class="text-center">Sıra</th>
                                                        <th class="text-center">Ad</th>
                                                        <th class="text-center">Soyad</th>
                                                        <th class="text-center">Kayıp</th>
                                                    </tr>
                                                    </thead>
                                                    <tbody>
                                                    <?php
                                                    for ($sayi = 0; $sayi < 10; $sayi++) {
                                                        echo
                                                            "<tr>
                                                        <td class='text-center'>" . ($sayi + 1) . "</td>
                                                        <td class='text-center' id='kaybedenler_yil_Ad_" . $sayi . "'>Ad</td>
                                                        <td class='text-center' id='kaybedenler_yil_Soyad_" . $sayi . "'>Soyad</td>
                                                        <td class='text-center' id='kaybedenler_yil_TL_" . $sayi . "'>TL</td>
                                                                </tr> 
                                                                ";
                                                    }
                                                    ?>
                                                    </tbody>
                                                </table>
                                            </div>
                                        </div>
                                    </section>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </section>


<?php include "inc/footer.php"; ?>