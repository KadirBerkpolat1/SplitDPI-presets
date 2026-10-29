# SplitDPI-presets

[English](README.md)

[SplitDPI](https://github.com/KadirBerkpolat1/SplitDPI) için hazır ayar
verisi: her sağlayıcı ve ülke için hangi zapret2 stratejilerinin deneneceği,
hangi alan adlarının hangi uygulamaya ait olduğu ve hangi alan adlarına hiç
dokunulmayacağı.

SplitDPI bu verinin bir kopyasını kendi içinde taşır. `sudo splitdpi presets update`
buradaki son sürümden `presets.tar.gz` dosyasını indirir, her dosyayı denetler
ve yerleşik kopya yerine onu kullanır. Ardından `splitdpi scan` önce
sağlayıcınızın, sonra ülkenizin, en son da genel stratejileri dener.

Her sürüm, `VERSION` dosyasındaki tarihle etiketlenir. Denetimden geçemeyen bir
dosya atlanır, asla kullanılmaz.

Sağlayıcı eklemek, bir stratejiyi düzeltmek ya da bir uygulamanın alan adlarını
genişletmek için [CONTRIBUTING.md](CONTRIBUTING.md) dosyasını okuyun. Veri MIT
lisanslıdır; kaynaklar [NOTICE](NOTICE) dosyasında belirtilir.
