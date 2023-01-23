# AndroidAPS 2.6'dan güncelleme sonrası gerekli kontroller

- AAPS 2.7'ye geçilirken program kodu önemli ölçüde değiştirildi.
- Bu nedenle güncellemeden sonra bazı değişiklikler yapmanız veya ayarları kontrol etmeniz önemlidir.
- Yeni ve genişletilmiş özelliklerle ilgili ayrıntılar için lütfen [sürüm notlarına](../Installing-AndroidAPS/Releasenotes#version-2-7-0) bakın.

## KŞ kaynağını kontrol edin

- Güncellemeden sonra KŞ kaynağının doğru olup olmadığını kontrol edin.
- Özellikle [xDrip+](../Configuration/xdrip.md) kullanıldığında KŞ kaynağının Dexcom uygulaması (yamalı) olarak değiştirilmiş olabilir.
- [Konfigürasyon ayarları\<../Configuration/Config-Builder#bg-source>][konfigürasyon ayarları<../configuration/config-builder.md#bg-source>] açın (ana ekranın sol üst tarafında hamburger menüsü)
- "KŞ kaynağı"na ilerleyin.
- Değişiklik gerekliyse doğru KŞ kaynağını seçin.

```{image} ../images/ConfBuild_BG.png
:alt: "K\u015E kayna\u011F\u0131"
```

## Sınavı bitir

- AAPS 2.7, otomasyon \<../Usage/Automation.md>" için yeni görev 11'i (sonraki sürümlerde hedef 10 olarak yeniden numaralandırılmıştır!) içerir.

- 11.Görevi [tamamlamak için de](../Usage/Objectives#objective-10-automation) sınavı bitirmiş olmanız ([3. ve 4. görev](../Usage/Objectives.md#objective-3-prove-your-knowledge)) gerekir.

- Örneğin, [3.görev](../Usage/Objectives#objective-3-prove-your-knowledge) içindeki sınavı henüz bitirmediyseniz, \` 11.hedefe \<../Usage/Objectives.md#objective-10-automation>\`\_ başlamadan önce sınavı tamamlamanız gerekir.

- Bu, daha önce tamamladığınız diğer görevleri etkilemeyecektir. Tüm tamamlanmış görevler korunacaktır!

## Ana parola tanımlama

- Sürüm 2.7'den itibaren şifreli oldukları için [ayarları](../Usage/ExportImportSettings.md) dışa aktarabilmek için gereklidir.
- Tercihleri Açın (ana ekranın sağ üst köşesindeki üç noktalı menü)
- "Genel" altındaki üçgeni tıklayın
- "Ana-Parola" ya tıklayın
- Parolayı girin, onaylayın ve Tamam'a tıklayın.

```{image} ../images/MasterPW.png
:alt: "Ana parola tan\u0131mlama"
```

## Dışa aktarma ayarları

- AAPS 2.7, yeni bir şifreli yedekleme formatı kullanır.
- 2.7 sürümüne güncelledikten sonra [ayarlarınızı](../Usage/ExportImportSettings.md) dışa aktarmalısınız.
- Önceki sürümlerdeki ayar dosyaları yalnızca AAPS 2.7'de içe aktarılabilir. Dışa aktarma yeni formatta olacaktır.
- Dışa aktarılan ayarlarınızı yalnızca telefonunuzda değil, aynı zamanda güvenli bir yerde (bilgisayarınız, bulut depolama...) sakladığınızdan emin olun.
- AAPS 2.7 apk'yi Android studio ile önceki sürümlerle aynı anahtar deposuyla kurarsanız, önceki sürümü silmeden yeni sürümü yükleyebilirsiniz.
- Tüm ayarlar ve tamamlanan görevler önceki sürümde olduğu gibi kalacaktır.
- Anahtar deponuzu kaybetmeniz ve 2.7 versiyonunu yeni anahtar deponuzla oluşturmanız durumunda, önceki sürümden içe aktarma ayarları ile nasıl kurulumun yapılabileceğini [sorun giderme bölümünde](../Installing-AndroidAPS/troubleshooting_androidstudio#lost-keystore) bulabilirsiniz.

## Otoduyarlılık (İpucu - herhangi bir işlem gerekmez)

- otoduyarlılık, referans tasarımı kopyalayan dinamik bir anahtarlama modeliyle değiştirildi.
- Otoduyarlılık artık hassasiyeti hesaplamak için 24 ve 8 saatlik bir aralıkta geçiş yapacak. Hangisinin daha hassas olduğunu kendi seçecektir.
- Kullanıcılar oref1'den geldiyse, 24 veya 8 saatlik hassasiyetin değişmesi nedeniyle muhtemelen sistemin değişikliklere karşı daha az dinamik olabileceğini fark edeceklerdir.

## Dana RS için Pompa Parolasını Ayarlayın (Dana RS kullanılıyorsa)

- [Dana RS](../Configuration/DanaRS-Insulin-Pump.md) için pompa şifresi önceki sürümlerde kontrol edilmedi.
- Tercihleri Açın (ana ekranın sağ üst köşesindeki üç noktalı menü)
- Aşağı kaydırın ve "Dana RS" yanındaki üçgene tıklayın.
- "Pompa şifresi (yalnızca v1)"e tıklayın
- Pompa şifresini girin ([Varsayılan şifre](../Configuration/DanaRS-Insulin-Pump#default-password) aygıt yazılımı sürümüne göre değişir) ve Tamam'ı tıklayın.

```{image} ../images/DanaRSPW.png
:alt: "Dana RS \u015Fifresini ayarlay\u0131n"
```

Dana RS'de şifreyi değiştirmek için `DanaRS sayfasındaki <../Configuration/DanaRS-Insulin-Pump#change-password-on-pump>`'daki talimatları izleyin.