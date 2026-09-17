# İçindekiler
- [Özel DNS Kullanma](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#%C3%B6zel-dns-kullanma)
- [Oyun Oynama](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#oyun-oynama)
- [Dizüstü Bilgisayarlar](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#diz%C3%BCst%C3%BC-bilgisayarlar)
- [Linux'ta Android Kullanma](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#linuxta-android-kullanma)
- [NetworkManager-wait-online.service Hizmetini Devre Dışı Bırakma](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#networkmanager-wait-onlineservice-hizmetini-devre-d%C4%B1%C5%9F%C4%B1-b%C4%B1rakma)
- [Terminal Yapılandırması](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#terminal-yap%C4%B1land%C4%B1rmas%C4%B1)
  - [Fish Yapılandırması](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#fish-yap%C4%B1land%C4%B1rmas%C4%B1)
  - [fastfetch Yapılandırması](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#fastfetch-yap%C4%B1land%C4%B1rmas%C4%B1)
- [Kapanış](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md#kapan%C4%B1%C5%9F)
# Dağıtıma Özel Rehberler
- **Arch Linux -** [Arch Linux Kurulum Sonrası Rehberi](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/Da%C4%9F%C4%B1t%C4%B1ma%20%C3%96zel/Arch-Linux-TR.md)
# Özel DNS Kullanma
```
sudo systemctl enable --now systemd-resolved
```
- `systemd-resolved` hizmetini etkinleştirdikten sonra, kullanmak istediğiniz özel DNS'in adımlarını takip edin. Benim tavsiyelerim aşağıdadır:
- [Cloudflare DNS](https://developers.cloudflare.com/1.1.1.1/setup/linux/)
    - **En hızlısıdır** fakat **gizlilik** konusunda **en zayıfıdır**.
- [NextDNS](https://nextdns.io/)
    - Cloudflare'den sonra **en hızlı ikinci** DNS'tir fakat **gizlilik** konusunda **oldukça iyidir**.
- [Mullvad DNS](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls)
    - **Hız** konusunda **fena değildir** fakat **gizlilik** konusunda **en iyisidir**.
# Oyun Oynama
**Linux'ta oyun oynama** hakkında ayrı bir rehberim mevcuttur. Rehbere [buradan ulaşabilirsiniz](https://github.com/cagla-su/Linux-Gaming-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri/linuxta-oyun-oynama-rehberi.md).
# Dizüstü Bilgisayarlar
**Dizüstü bilgisayarlar** ama **esas olarak Thinkpad bilgisayarlar için** ayrı bir rehberim mevcuttur. Rehbere [buradan ulaşabilirsiniz](https://github.com/cagla-su/Thinkpad-Linux-Optimization-Guide).
# Linux'ta Android Kullanma
**Linux'ta Android kullanma** hakkında ayrı bir rehberim mevcuttur. Rehbere [buradan ulaşabilirsiniz](https://github.com/cagla-su/Waydroid-Guide/blob/main/Waydroid-Rehberi.md).
# NetworkManager-wait-online.service Hizmetini Devre Dışı Bırakma
**Daha çabuk başlatma zamanı** için, `NetworkManager-wait-online.service` hizmetini devre dışı bırakın:
```
sudo systemctl disable NetworkManager-wait-online.service
```
# Terminal Yapılandırması
## Fish Yapılandırması
Eğer terminalinizin **ne yazacağınızı tahmin etmesini** isterseniz, [Fish](https://fishshell.com/) kullanmanızı tavsiye ederim.
```
sudo pacman -S fish
```
```
chsh -s /usr/bin/fish # komutu çalıştırdıktan sonra bilgisayarınızı yeniden başlatın
```
> [!NOTE]
> - Eğer terminaliniz size **işlemin başarısız olduğunu** söylerse, `chsh -s /bin/fish`'i deneyin.
> - Ek olarak, **terminali her çalıştırdığınızda** **fastfetch**'i görmek isterseniz, **aşağıdaki komutları çalıştırmalısınız**:
```
  function fish_greeting
  fastfetch
  end
```
```
funcsave fish_greeting
```
## fastfetch Yapılandırması
> [!WARNING]
> - Fastfetch'in varsayılan teması *genellikle kullanışlıdır* fakat **benim** fastfetch **temamı denemek** isterseniz, **aşağıda bulunan komutları çalıştırmalısınız**.
> - Aşağıda **kendi** fastfetch temamın bir **örneği** bulunmaktadır. Beğenmediyseniz lütfen **bu adımı atlayın**.
<img width="806" height="461" alt="image" src="https://github.com/user-attachments/assets/81756f30-7a60-4d57-bbd1-440f1e9d543f" />

```
{
"logo": {
"type": "small",
"padding": {
        "top": 11,
        "left": 3
    },
"color": {
"1": "35",
"2": "35",
}
},
    "modules": [
        "break",
                {
      "type": "custom",
      "format": "{#35}╭──────────────────────╮"
    },
    "break",
    {
      "type": "title",
      "format": "{#35}| {#37}Hardware Information {#35}|"
    },
        "break",
        {
      "type": "custom",
      "format": "{#35}╰──────────────────────╯"
    },
        "break",
        {
            "type": "host",
            "format": "{5} {1}({2})",
            "key": "{#31} {#35}> {#31}Motherboard ",
        },
        {
            "type": "cpu",
            "format": "{1} ({3}) @ {7}",
            "key": "{#35} {#31}> {#35}Processor ",
        },
        {
            "type": "gpu",
            "key": "{#31}󰢮 {#35}> {#31}Graphics Card ",
        },
        {
            "type": "memory",
            "key": "{#35} {#31}> {#35}Memory ",
        },
        {
            "type": "swap",
            "key": "{#31}󰓡 {#35}> {#31}Swap ",
        },
        {
            "type": "disk",
            "key": "{#35}󰋊 {#31}> {#35}Storage ",
        },
        {
            "type": "monitor",
            "key": "{#31} {#35}> {#31}Display ",
        },
        "break",
                        {
      "type": "custom",
      "format": "{#35}╭──────────────────────╮"
    },
    "break",
        {
      "type": "title",
      "format": "{#35}| {#37}Software Information {#35}|"
        },
        "break",
        {
      "type": "custom",
      "format": "{#35}╰──────────────────────╯"
    },
            "break",
            {
            "type": "os",
            "key": "{#31} {#35}> {#31}Operating System ",
        },
        {
            "type": "kernel",
            "key": "{#35} {#31}> {#35}Kernel ",
        },
        {
            "type": "packages",
            "key": "{#31}󰏖 {#35}> {#31}Packages ",
        },
        {
            "type": "wm",
            "key": "{#35} {#31}> {#35}Window Manager ",
        },
        {
            "type": "wmtheme",
            "key": "{#31}󰉼 {#35}> {#31}Window Manager Theme ",
        },
        {
            "type": "icons",
            "key": "{#35}󰀻 {#31}> {#35}Icon Theme ",
        },
        {
            "type": "cursor",
            "key": "{#31} {#35}> {#31}Cursor Theme ",
        },
	{
            "type": "shell",
            "key": "{#35} {#31}> {#35}Shell ",
        },

        {
            "type": "terminal",
            "key": "{#31} {#35}> {#31}Terminal ",
        },
    ]
}
```
# Kapanış
Bu rehber Linux kurulum sonrası hakkındaydı! Umarım rehber faydalı olmuştur. Okuduğunuz için teşekkürler!

