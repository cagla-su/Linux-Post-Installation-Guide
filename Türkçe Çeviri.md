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
<img width="722" height="343" alt="image" src="https://github.com/user-attachments/assets/51ac5587-8963-4017-83b2-d78b2aa588b0" />

```
sudo mkdir ~/.config/fastfetch/ && sudo nano ~/.config/fastfetch/config.jsonc
```
```
{
  "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
"logo": {
"type": "small",
"padding": {
        "top": 6,
        "left": 3
    },
"color": {
"1": "blue",
"2": "blue"
}
},
"modules": [
    // Title
    {
      "type": "title",
      "format": "{#1}╭───────────────────"
    },
    // System Information
    {
      "type": "custom",
      "format": "{#1}│ {#}>^^< System Information >^^<"
    },
{
      "type": "host",
      "key": "│ Computer Model",
      "keyColor": "white"
    },
    {
      "type": "os",
      "key": "│ Operating System",
      "keyColor": "white"
    },
    {
      "type": "kernel",
      "key": "│ Kernel",
      "keyColor": "white"
    },
{
      "type": "packages",
      "key": "│ Packages",
      "keyColor": "white"
    },
    {
      "type": "custom",
      "format": "{#1}│"
    },
    // Desktop
    {
      "type": "custom",
      "format": "{#1}│ {#}>^^< Desktop >^^<",
    },
    {
      "type": "de",
      "key": "│ Desktop Environment",
      "keyColor": "magenta"
    },
    {
      "type": "wm",
      "key": "│ Window Manager",
      "keyColor": "magenta"
    },
    {
      "type": "shell",
      "key": "│ Shell",
      "keyColor": "magenta"
    },
    {
      "type": "custom",
      "format": "{#1}│"
    },
    // Hardware Information
    {
      "type": "custom",
      "format": "{#1}│ {#}>^^< Hardware Information >^^<",
    },
    {
      "type": "cpu",
      "key": "│ Processor",
      "keyColor": "cyan"
    },
    {
      "type": "gpu",
      "key": "│ Graphics Card",
      "keyColor": "cyan"
    },
    {
      "type": "memory",
      "key": "│ Memory",
      "keyColor": "cyan"
    },
    {
      "type": "disk",
      "key": "│ Disk",
      "keyColor": "cyan"
    },
    {
      "type": "custom",
      "format": "{#1}│"
    },
    // Colors
    {
      "type": "colors",
      "key": "{#separator}│",
      "symbol": "circle"
    },
    // Footer
    {
      "type": "custom",
      "format": "{#1}╰───────────────────"
    }
  ]
}
```
# Kapanış
Bu rehber Linux kurulum sonrası hakkındaydı! Umarım rehber faydalı olmuştur. Okuduğunuz için teşekkürler!

