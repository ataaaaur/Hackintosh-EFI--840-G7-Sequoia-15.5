<h1 align="center">  macOS Sequoia on HP EliteBook 840 G7 </h1>

<p align="center">
  <img src="https://github.com/ataaaaur/Hackintosh-EFI--840-G7-Sequoia-15.5/blob/main/840%20g7%2015.5.png" alt="840 G7 Sequoia 15.5">
</p>

<h4 align="center"> OpenCore config for Hackintosh HP EliteBook 840 G7 </h4>

<p align="center">
  <a href="https://www.apple.com/macos/sequoia/">
    <img alt="macOS Sequoia 15.5" src="https://img.shields.io/badge/macOS-Sequoia_15.5-000000?style=for-the-badge&logo=apple&logoColor=white" />
  </a>
  <a href="https://github.com/acidanthera/OpenCorePkg/releases">
    <img alt="OpenCore 1.0.5" src="https://img.shields.io/badge/OpenCore-1.0.5-154a94?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://github.com/ataaaaur/Hackintosh-EFI--840-G7-Sequoia-15.5/releases">
    <img alt="Latest Release" src="https://img.shields.io/github/v/release/ataaaaur/Hackintosh-EFI--840-G7-Sequoia-15.5?style=for-the-badge&logo=github" />
  </a>
  <a href="https://github.com/ataaaaur/Hackintosh-EFI--840-G7-Sequoia-15.5/issues">
    <img alt="Issues" src="https://img.shields.io/github/issues/ataaaaur/Hackintosh-EFI--840-G7-Sequoia-15.5?style=for-the-badge&logo=github" />
  </a>
</p>

## Contents
- [Original Hardware 💻](#original-hardware-)  
- [What's working 💻](#whats-working-)  
- [What's not working 💻](#whats-not-working-)  
- [What you have to do 💻](#what-you-have-to-do-)  
- [Credits](#credits)  
- [Manual fix for disable sleep](#manual-fix-for-disable-sleep)  

## Original Hardware  💻

_Type_ | _Spec_ | _Status_
:---------|:---------|:----------
**Model Name**      | HP EliteBook 840 G7 | ✅  
**CPU**             | Intel Core i5-10210U @ 1.60 GHz (up to 4.20 GHz) | ✅  
**RAM**             | 8 GB 2400 MHz DDR4 | ✅  
**Graphics**        | Intel UHD 620 | ✅  
**Wi-Fi**           | Intel AX200 (apply OCLP patch immediately after install for native support) | ✅  
**Bluetooth**       | Intel AX200 | ✅  
**Audio**           | Realtek ALC285 | ✅  

## What's working  💻

_Type_ | _Status_
:---------|:---------
Turbo Boost & CPU frequency  | ✅  
Intel UHD 620 graphics       | ✅  
Brightness control (use Fn +C and Fn + W to adjust)          | ✅  
HDMI output                  | ✅  
Audio in/out                 | ✅  
Wi-Fi & Bluetooth            | ✅  
USB 3.0 (with port map)      | ✅  
Touchpad (14 gestures)       | ✅  
Battery status & sensors     | ✅  
Camera / FaceTime            | ✅  
Shutdown / Reboot            | ✅  
Fn-keys & shortcuts          | ✅  
Sleep (S3)                   | ✅ (see manual fix below)  

## What's not working  💻

_Type_ | _Status_
:---------|:---------
Built-in microphone      | ❌  (never supported due to SST limitation)
Fingerprint reader       | ❌  

## What you have to do  💻

_Type_ | _Info_ | _Status_
:---------|:---------|:----------
SMBIOS & iCloud setup        | Use [GenSMBIOS] to set MBP16,2 & ROM (en0 MAC) for iCloud services | ⚠️  
OCLP patch for Wi-Fi         | Download OCLP from [Here](https://github.com/dortania/OpenCore-Legacy-Patcher/releases) then run “Install Root Patches” | ✅  

## Credits

- [Dortania](https://dortania.github.io) – OpenCore Install Guide  
- [Acidanthera](https://github.com/acidanthera) – Bootloader & kexts  
- [Apple](https://www.apple.com) – macOS  
- Hackintosh community contributors  

## Manual fix for disable sleep

In Terminal, run:

```bash
sudo pmset -a sleep 0
sudo pmset -a hibernatemode 0
sudo pmset -a disablesleep 1
