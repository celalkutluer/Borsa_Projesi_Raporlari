4_VERİ TOPLAMA:

https://github.com/roottoror/Borsa_Projesi


yonetim.php kodumuz

<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

siralama.php

<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

satinal.php

<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

sat.php
<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

profil.php
<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

portfoy.php
<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>


kayit.php
<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

index.php

<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
    <span class="col-lg"></span>
    <div class="conteiner ">
        <div class=" row ">
            <div class="col-sm-6">
                <div class="table col-sm">
                    <table class="table table-bordered bg-light">
                        <span class="h6">En Çok Yükselenler</span>
                        <thead>
                        <tr>
                            <th scope="col">Sembol</th>
                            <th scope="col">Fiyat</th>
                            <th scope="col">(%)Fark</th>
                        </tr>
                        </thead>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                    </table>
                </div>
            </div>
            <div class="col-sm-6">
                <div class="table col-sm">
                    <table class="table table-bordered bg-light">
                        <span class="h6">En Çok Düşenler</span>
                        <thead>
                        <tr>
                            <th scope="col">Sembol</th>
                            <th scope="col">Fiyat</th>
                            <th scope="col">(%)Fark</th>
                        </tr>
                        </thead>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                        <tbody>
                        <td>*</td>
                        <td>*</td>
                        <td>*</td>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
<span class="col-md"></span>
    <div class="conteiner col-sm-12">
        <div class=" row ">
            <div class="table col-sm">
                <table class="table table-bordered bg-light">
                    <thead>
                    <tr>
                        <th scope="col">Sembol</th>
                        <th scope="col">Şirket</th>
                        <th scope="col">Durum</th>
                        <th scope="col">Fiyat</th>
                        <th scope="col">(%)Fark</th>
                        <th scope="col">Zaman</th>
                        <th scope="col">Alış</th>
                        <th scope="col">Satış</th>
                    </tr>
                    </thead>
                    <tbody>
                    <?php
                    function hisse()
                    {
                        Global $db;
                        $veri = $db->prepare("SELECT * FROM borsa_bilgi LEFT JOIN borsa_anlik ON borsa_bilgi.Sembol=borsa_anlik.Sembol");
                        $veri->execute(array());
                        $v = $veri->fetchAll(pdo::FETCH_ASSOC);
                        $say = $veri->rowCount();
                        if ($say) {
                            foreach ($v as $tum_hisseler) {
                                ?>
                                <tr>
                                    <td><?php echo $tum_hisseler['Sembol']; ?></td>
                                    <td><?php echo $tum_hisseler['Tam_Ad']; ?></td>
                                    <td>*</td>
                                    <td><?php echo $tum_hisseler['Fiyat']; ?></td>
                                    <td>*</td>
                                    <td><?php echo $tum_hisseler['Zaman']; ?></td>
                                    <td>
                                        <button type="button" class="btn btn-success">ALIŞ</button>
                                    </td>
                                    <td>
                                        <button type="button" class="btn btn-danger">SATIŞ</button>
                                    </td>
                                </tr>
                                <?php
                            }
                        }
                    }

                    hisse();
                    ?>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
<?php include "inc/footer.php"; ?>

giris.php
<?php
include "settings/baglantilar.php";
//include "settings/fonksiyonlar.php";
include "inc/header.php";
?>
<?php include "inc/footer.php"; ?>

baglantilar.php
<?php
$host="localhost";
$dbname="borsa";
$kullanici="root";
$sifre="";

try
{
    $db=new PDO("mysql:host=$host;dbname=$dbname;charset=utf8","$kullanici","$sifre");
}
catch (PDOException $e)
{
    print $e->getMessage();
}
//error_reporting(0);
session_start();
ob_start();

fonksiyonlar.php
<?php
function g($par)
{
    $par = temiz(@$_GET[$par]);
    return $par;
}
function p($par)
{
    $par = htmlspecialchars(addslashes(trim($_POST[$par])));
    return $par;
}
///////////////////////SESSİON
function s($par)
{
    $session = $_SESSION[$par];
    return $session;
}
///////////////////////YONETİCİ
/*function yoneticikontrol()
{
    if (!$_SESSION || !$_SESSION['yetki'] == '1') {
        header("Location:giris.php");
    }
}
function kullanicikontrol()
{
    if ($_SESSION || $_SESSION['yetki'] == '1'||$_SESSION['yetki'] == '2'||$_SESSION['yetki'] == '3') {
    }
    else
    {
        header("Location:giris.php");
    }
}*/
?>

header.php

<?php ?>
<!doctype html>
<html lang="en">
<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <link rel="stylesheet" type="text/css" href="assets/css/font-awesome.min.css"/>
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" type="text/css" href="assets/css/bootstrap.min.css"/>
    <link rel="stylesheet" type="text/css" href="assets/css/bootstrap-grid.min.css"/>
    <link rel="stylesheet" type="text/css" href="assets/css/bootstrap-reboot.min.css"/>
    <link rel="stylesheet" type="text/css" href="assets/css/main.css"/>

    <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
    <title>BORSA</title>
</head>
<body>

    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <a class="navbar-brand" href="index.php">BORSA</a>
        <button class="navbar-toggler " type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <div class="collapse navbar-collapse " id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item active"><a class="nav-link" href="yonetim.php">Yönetim <span class="sr-only">(current)</span></a>
                </li>
                <li class="nav-item active"><a href="siralama.php" class="nav-link">Liderlik</a></li>
                <li class="nav-item active"><a href="portfoy.php" class="nav-link">Portföyüm</a></li>
            </ul>
            <ul class="nav navbar-nav navbar-right ml-auto">
                <li class="nav-item"><a href="giris.php" class="nav-link">Giriş</a></li>
                <li class="nav-item"><a href="kayit.php" class="nav-link">Kayıt</a></li>
                <li class="nav-item"><a href="profil.php" class="nav-link">Profilim</a></li>
            </ul>
        </div>
    </nav>

footer.php
<?php
?>
<!-- Optional JavaScript -->
<!-- jQuery first, then Popper.js, then Bootstrap JS -->
<script src="assets/js/jquery-3.4.1.min.js"></script>
<script src="assets/js/bootstrap.bundle.min.js"></script>
<script src="assets/js/bootstrap.min.js"></script>
<script src="assets/js/popper.min.js"></script>
<script src="assets/js/main.js"></script>
<!-- Copyright -->
<div class="footer-copyright text-center py-3">© 2020 Copyright:<a href="index.php"> BORSA</a></div>
<!-- Copyright -->
</body>
</html>



Veri tabanı:

alim tablosu
CREATE TABLE `alim` (
  `alim_id` int(11) NOT NULL,
  `alim_kul_id` int(11) DEFAULT NULL,
  `alim_hisse_sembol` varchar(10) COLLATE utf8_turkish_ci DEFAULT NULL,
  `alim_hisse_deger` decimal(10,2) DEFAULT NULL,
  `alim_hisse_komisyon` decimal(7,2) DEFAULT NULL,
  `alim_hisse_lot` int(11) DEFAULT NULL,
  `alim_hisse_toplam_tutar` decimal(10,2) DEFAULT NULL,
  `alim_zaman` datetime DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_turkish_ci;

INSERT INTO `alim` (`alim_id`, `alim_kul_id`, `alim_hisse_sembol`, `alim_hisse_deger`, `alim_hisse_komisyon`, `alim_hisse_lot`, `alim_hisse_toplam_tutar`, `alim_zaman`) VALUES
(9, 1, 'AEFES', 17.02, 29.87, 585, 9986.57, '2020-03-23 18:29:25'),
(10, 1, 'AFYON', 3.96, 0.01, 1, 3.97, '2020-03-23 18:56:14'),
(11, 1, 'KLGYO', 1.78, 0.01, 1, 1.79, '2020-03-23 18:57:02'),
(12, 1, 'ZOREN', 0.96, 0.00, 1, 0.96, '2020-03-23 18:57:15'),
(13, 1, 'TKNSA', 4.02, 0.01, 1, 4.03, '2020-03-23 18:57:23'),
(14, 1, 'PRKME', 2.17, 0.01, 1, 2.18, '2020-03-23 18:57:46'),
(15, 1, 'IHLAS', 0.39, 0.06, 1, 0.39, '2020-03-23 19:39:15'),
(18, 1, 'AEFES', 17.02, 0.87, 17, 290.21, '2020-03-23 19:46:06'),

Kullanicilar tablosu
CREATE TABLE `kullanicilar` (
  `kul_Id` int(11) NOT NULL,
  `kul_Ad` varchar(20) COLLATE utf8_turkish_ci DEFAULT NULL,
  `kul_Soyad` varchar(20) COLLATE utf8_turkish_ci DEFAULT NULL,
  `kul_Eposta` tinytext COLLATE utf8_turkish_ci DEFAULT NULL,
  `kul_CepNo` tinytext COLLATE utf8_turkish_ci DEFAULT NULL,
  `kul_DogumTar` date DEFAULT NULL,
  `kul_Sifre` tinytext COLLATE utf8_turkish_ci DEFAULT NULL,
  `kul_Bakiye` decimal(10,2) DEFAULT 10000.00,
  `kul_Eposta_Dogrulama_Kod` tinytext COLLATE utf8_turkish_ci DEFAULT NULL,
  `kul_Eposta_Dogrulama` enum('0','1') COLLATE utf8_turkish_ci DEFAULT '0',
  `kul_Uyelik_Tarih` datetime DEFAULT current_timestamp(),
  `kul_Son_Giris_Tar` datetime DEFAULT NULL,
  `kul_lig_id` int(11) DEFAULT NULL,
  `kul_Yetki` varchar(45) COLLATE utf8_turkish_ci DEFAULT '0',
  `kul_Pasif_Durum` enum('0','1') COLLATE utf8_turkish_ci DEFAULT '1',
  `kul_Pasif_Tarih` datetime DEFAULT NULL,
  `kul_Pasif_Sure` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_turkish_ci;


INSERT INTO `kullanicilar` (`kul_Id`, `kul_Ad`, `kul_Soyad`, `kul_Eposta`, `kul_CepNo`, `kul_DogumTar`, `kul_Sifre`, `kul_Bakiye`, `kul_Eposta_Dogrulama_Kod`, `kul_Eposta_Dogrulama`, `kul_Uyelik_Tarih`, `kul_Son_Giris_Tar`, `kul_lig_id`, `kul_Yetki`, `kul_Pasif_Durum`, `kul_Pasif_Tarih`, `kul_Pasif_Sure`) VALUES
(1, 'CELAL', 'KUTLUER', 'celal', '+905075091032', '0000-00-00', '4a7d1ed414474e4033ac29ccb8653d9b', 7419.35, NULL, '1', '2020-03-23 17:28:39', NULL, 1, '1', '1', NULL, NULL),
(3, 'haydar', 'bulut', 'haydar', '5556', '2020-09-04', '4a7d1ed414474e4033ac29ccb8653d9b', 10000.00, 'c5903bd6edb28d2e9a78f37d48bc42d89cbe9a17', '0', '2020-09-04 14:50:55', NULL, 1, '0', '1', NULL, NULL),
(4, 'Celal', 'KUTLUER', 'celalkutluer@gmail.com', '5075091032', '1989-01-21', '4a7d1ed414474e4033ac29ccb8653d9b', 9982.72, '72e5b2e74f73b0dbf531133032f796a5ffa5b47a', '0', '2020-03-31 19:40:47', NULL, NULL, '0', '1', NULL, NULL),
(5, 'a', 'a', 'a', 'a', '2020-04-15', '0cc175b9c0f1b6a831c399e269772661', 10000.00, '6f9b0a55df8ac28564cb9f63a10be8af6ab3f7c2', '0', '2020-04-01 21:07:40', NULL, NULL, '0', '1', NULL, NULL),
(6, 'asd', 'asd', 'asdasd@asd.com', '444444', '5858-05-25', '25f9e794323b453885f5181f1b624d0b', 10000.00, '6f5f61af70e7f4215957691ebc0008c9d11416d4', '0', '2020-04-13 15:41:04', NULL, NULL, '0', '1', NULL, NULL),
(7, 'beyza', 'nur', 'beyzataskopru09@gmail.com', '5555555555', '1998-05-01', '4a7d1ed414474e4033ac29ccb8653d9b', 10000.00, 'a3c48f9ee1fc434049485234ce7312c528cea896', '0', '2020-04-29 22:32:08', NULL, NULL, '0', '1', NULL, NULL),
(8, 'Tarık', 'Erden', '16008116048@ogr.bozok.edu.tr', '555555555', '1999-06-16', 'e10adc3949ba59abbe56e057f20f883e', 2220.37, '598f5629c2048431615fd991ed9b6f853f4fef2d', '0', '2020-05-02 09:26:47', NULL, NULL, '0', '1', NULL, NULL),
(9, 'cankat', 'ateş', 'jenkaat@gmail.com', '55555555', '1997-12-12', 'e10adc3949ba59abbe56e057f20f883e', 10000.00, '9c17af7a9831d1c823c85d02d77d0851c7faff4a', '0', '2020-05-02 10:44:19', NULL, NULL, '0', '1', NULL, NULL),
(10, '.', '.', 'asdf@gmail.com', '5555555555', '1990-05-07', '912ec803b2ce49e4a541068d495ab570', 10000.00, 'a1cc6a9a434026fc884bab8b3c7994dfeb05a084', '0', '2020-05-02 11:57:42', NULL, NULL, '0', '1', NULL, NULL);

Ligler tablosu

CREATE TABLE `ligler` (
  `lig_id` int(11) NOT NULL,
  `lig_baslik` text COLLATE utf8_turkish_ci DEFAULT NULL,
  `lig_duyuru` text COLLATE utf8_turkish_ci DEFAULT NULL,
  `lig_uye_1` int(11) DEFAULT NULL,
  `lig_uye_2` int(11) DEFAULT NULL,
  `lig_uye_3` int(11) DEFAULT NULL,
  `lig_uye_4` int(11) DEFAULT NULL,
  `lig_yonetici_id` int(11) DEFAULT NULL,
  `lig_son_siralama` tinyint(4) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_turkish_ci;

log tablosu

CREATE TABLE `log` (
  `log_id` int(11) NOT NULL,
  `log_kul_id` int(11) DEFAULT NULL,
  `log_eylem` tinytext COLLATE utf8_turkish_ci DEFAULT NULL,
  `log_aciklama` text COLLATE utf8_turkish_ci DEFAULT 'CURRENT_TIMESTAMP',
  `log_zaman` datetime DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_turkish_ci;
Satım tablosu
CREATE TABLE `satim` (
  `satim_id` int(11) NOT NULL,
  `satim_kul_id` int(11) DEFAULT NULL,
  `satim_hisse_sembol` varchar(10) COLLATE utf8_turkish_ci DEFAULT NULL,
  `satim_hisse_deger` decimal(10,2) DEFAULT NULL,
  `satim_hisse_komisyon` decimal(7,2) DEFAULT NULL,
  `satim_hisse_lot` int(11) DEFAULT NULL,
  `satim_hisse_toplam_tutar` decimal(10,2) DEFAULT NULL,
  `satim_zaman` datetime DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_turkish_ci;
Varlıklar tablosu

CREATE TABLE `varliklar` (
  `varlik_id` int(11) NOT NULL,
  `varlik_kul_id` int(11) DEFAULT NULL,
  `varlik_hisse_sembol` varchar(10) COLLATE utf8_turkish_ci DEFAULT NULL,
  `varlik_alim_adet` int(11) DEFAULT NULL,
  `varlik_satim_adet` int(11) DEFAULT NULL,
  `varlik_degisim_zaman` datetime NOT NULL DEFAULT current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_turkish_ci;


Dökümü yapılmış tablolar için indeksler



Tablo için indeksler `alim`

ALTER TABLE `alim`
  ADD PRIMARY KEY (`alim_id`);


 Tablo için indeksler `kullanicilar`

ALTER TABLE `kullanicilar`
  ADD PRIMARY KEY (`kul_Id`);


 Tablo için indeksler `ligler`

ALTER TABLE `ligler`
  ADD PRIMARY KEY (`lig_id`);


 Tablo için indeksler `log`

ALTER TABLE `log`
  ADD PRIMARY KEY (`log_id`);


 Tablo için indeksler `satim`

ALTER TABLE `satim`
  ADD PRIMARY KEY (`satim_id`);


 Tablo için indeksler `varliklar`

ALTER TABLE `varliklar`
  ADD PRIMARY KEY (`varlik_id`);


 Dökümü yapılmış tablolar için AUTO_INCREMENT değeri


 Tablo için AUTO_INCREMENT değeri `alim`

ALTER TABLE `alim`
  MODIFY `alim_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=60;


 Tablo için AUTO_INCREMENT değeri `kullanicilar`

ALTER TABLE `kullanicilar`
  MODIFY `kul_Id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;


 Tablo için AUTO_INCREMENT değeri `ligler`

ALTER TABLE `ligler`
  MODIFY `lig_id` int(11) NOT NULL AUTO_INCREMENT;


 Tablo için AUTO_INCREMENT değeri `log`

ALTER TABLE `log`
  MODIFY `log_id` int(11) NOT NULL AUTO_INCREMENT;


Tablo için AUTO_INCREMENT değeri `satim`

ALTER TABLE `satim`
  MODIFY `satim_id` int(11) NOT NULL AUTO_INCREMENT;


 Tablo için AUTO_INCREMENT değeri `varliklar`

ALTER TABLE `varliklar`
  MODIFY `varlik_id` int(11) NOT NULL AUTO_INCREMENT;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;


