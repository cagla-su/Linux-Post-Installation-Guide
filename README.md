# Linux Post-Installation Guide
# Table of Contents
- [Using Custom DNS](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#using-custom-dns)
- [Gaming](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#gaming)
- [Laptops](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#laptops)
- [Use Android on Linux](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#use-android-on-linux)
- [Disabling NetworkManager-wait-online.service](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#disabling-networkmanager-wait-onlineservice)
- [Terminal Configuration](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#terminal-configuration)
  - [Fish Configuration](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#fish-configuration)
  - [fastfetch Configuration](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#fastfetch-configuration)
- [Conclusion](https://github.com/cagla-su/Linux-Post-Installation-Guide?tab=readme-ov-file#conclusion)
## Türkçe Çeviri 🇹🇷
> [!NOTE]
> Rehberin [Türkçe çevirisi buradadır](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/T%C3%BCrk%C3%A7e%20%C3%87eviri.md). Birebir çeviri değildir ama içerik aynıdır.
## Distribution-Specific Guides
- **Arch Linux -** [Arch Linux Post-Installation Guide](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/Distro-Specific/Arch-Linux.md)
    - 🇹🇷 **Türkçe Çevirisi -** [Arch Linux Kurulum Sonrası Rehberi](https://github.com/cagla-su/Linux-Post-Installation-Guide/blob/main/Da%C4%9F%C4%B1t%C4%B1ma%20%C3%96zel/Arch-Linux-TR.md)
# Using Custom DNS
```
sudo systemctl enable --now systemd-resolved
```
- After enabling `systemd-resolved`, follow the instructions of custom DNS you want to use. My suggestions are listed below:
- [Cloudflare DNS](https://developers.cloudflare.com/1.1.1.1/setup/linux/)
    - **The fastest** but **weak** when it comes to **privacy**.
- [NextDNS](https://nextdns.io/)
    - **The second fastest** after Cloudflare but **really good** when it comes to **privacy**.
- [Mullvad DNS](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls)
    - **Not bad** in terms of **speed** but **the best** when it comes to **privacy**. 
# Gaming
I have a separate guide about **gaming on Linux**. You can check the guide [from here](https://github.com/cagla-su/Linux-Gaming-Guide).
# Laptops
I have a separate optimization guide for **laptops** but **mainly for Thinkpads**. You can check the guide [from here](https://github.com/cagla-su/Thinkpad-Linux-Optimization-Guide).
# Use Android on Linux
I have a separate guide about **using Android on Linux**. You can check the guide [from here](https://github.com/cagla-su/Waydroid-Guide).
# Disabling NetworkManager-wait-online.service
For a **faster boot time**, disable `NetworkManager-wait-online.service`:
```
sudo systemctl disable NetworkManager-wait-online.service
```
# Terminal Configuration
## Fish Configuration
If you would like your terminal to **predict what you are going to type**, I suggest that you use [Fish](https://fishshell.com/) for your terminal.
```
sudo pacman -S fish
```
```
chsh -s /usr/bin/fish # you should reboot after running the command
```
> [!NOTE]
> - If terminal tells you that the **process has failed**, try `chsh -s /bin/fish` instead.
> - Additionally, if you would like to see **fastfetch every time you launch terminal**, you should **execute the commands below**:
```
  function fish_greeting
  fastfetch
  end
```
```
funcsave fish_greeting
```
## fastfetch Configuration
> [!WARNING]
> - Fastfetch's default theme is *usually useful* but if you would like to **try my** fastfetch **theme**, you should **execute the commands below**.
> - The picture below is an **example** of how **my** fastfetch theme looks like. If you did not like it, please **skip this step**.
<img width="806" height="461" alt="image" src="https://github.com/user-attachments/assets/2b634fa9-a59b-42b7-bac5-80796dc2174b" />

```
sudo mkdir ~/.config/fastfetch/ && sudo nano ~/.config/fastfetch/config.jsonc
```
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
# Conclusion
This guide was about Linux post-installation! I hope the guide has been useful. Thank you for reading!
