1. Computer Hardware Components

 Cel
Poznać podstawowe komponenty komputera i ich rolę oraz zebrać informacje sprzętowe z moich VM (Windows 11 + Kali).

 Teoria – najważniejsze rzeczy (po jednym zdaniu)
- Motherboard (płyta główna): łączy wszystkie komponenty i zapewnia komunikację między nimi.
- Chipset: obsługuje I/O (USB, SATA, część PCIe, audio, LAN) poza bezpośrednią kontrolą CPU.
- VRM (Voltage Regulator Module): stabilizuje i obniża napięcie dla CPU/RAM; słaby VRM = restarty/BSOD pod obciążeniem.
- Firmware UEFI/BIOS: startuje sprzęt i uruchamia bootloader; przejęcie = kontrola poniżej OS.
- CPU (Central Processing Unit): wykonuje instrukcje programów; ma rdzenie, wątki i cache.
- Cache L1/L2/L3: pamięć podręczna CPU, żeby nie czekał na RAM.
- Ringi (Ring 0 / Ring 3): poziomy uprawnień CPU – kernel vs aplikacje.
- VT-x / AMD-V: wsparcie wirtualizacji sprzętowej.
- RAM (Random Access Memory): ulotna pamięć robocza na uruchomione programy i dane.
- Dual-channel: dwa równoległe kanały RAM zwiększające przepustowość.
- Storage: HDD vs SATA SSD vs NVMe SSD (różnice w szybkości i opóźnieniach).
- IOPS (Input/Output Operations Per Second): miara wydajności małych losowych operacji dysku – kluczowa dla OS/VM.
- TBW (Terabytes Written): żywotność SSD w zapisie.
- GPU (Graphics Processing Unit): obliczenia równoległe; przydatne do crackingu hashy (np. Hashcat).
- NIC (Network Interface Card): karta sieciowa; ma MAC (Media Access Control) w warstwie 2.
- PSU (Power Supply Unit): stabilne zasilanie całego komputera; słaby PSU = losowe restarty/korupcja danych.
- Magistrale: PCIe (szybkie urządzenia), SATA (dyski), USB (peryferia).
- Przepływ danych: dysk → RAM → CPU → RAM → dysk/NIC.

 Lab – Windows 11 VM

 Podsumowanie sprzętu
- Boot mode: UEFI (msinfo32)
- CPU: Intel Core i7-10510U @ 1.80GHz  
  vCPU w VM: 2 rdzenie / 2 wątki
- RAM: ~4 GB (TotalPhysicalMemory ≈ 3.98 GiB)
- Disk: VBOX HARDDISK ~80 GB  
  Kontroler: SATA / AHCI (potwierdzone w Kali)


 Lab – Kali Linux VM

 Podsumowanie sprzętu
- CPU: 2 vCPU (Intel i7-10510U widoczny w VM)
- RAM: 5.6 GiB
- Disk: sda 80.1G VBOX HARDDISK  
  Kontroler: SATA controller (AHCI mode)
- NIC: Intel 82540EM Gigabit Ethernet Controller  
  Driver: e1000  
  Interfejs: eth0
- GPU: VMware SVGA II Adapter


 Wnioski bezpieczeństwa
1. Przejęcie firmware/UEFI daje trwałość ataku poniżej systemu i omija zabezpieczenia OS.
2. Hasła/tokeny/klucze pojawiają się w RAM → malware często celuje w pamięć.
3. Brak szyfrowania dysku oznacza utratę danych przy kradzieży sprzętu.
4. GPU znacząco przyspiesza cracking offline hashy.
5. USB oraz DMA po PCIe to realne wektory fizycznych ataków.


Next: Connection Types and their function
