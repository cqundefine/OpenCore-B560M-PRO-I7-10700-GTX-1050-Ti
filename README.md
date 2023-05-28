## OpenCore EFI B560M-PRO + i7-10700 + GTX 1050 Ti

### Important PC Specification:
- Motherboard: MSI B560M-PRO
- CPU: Intel I7-10700
- GPU: Gigabyte NVIDIA GTX 1050 Ti
- LAN: Realtek 2.5 Gb Ethernet

### EFI Info:
- OpenCore version: 0.9.0
- Graphical boot enabled
- SMBIOS: iMac20,1 (⚠️ You have to generate it yourself using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS))

### What works:
| Function | Status |
| ------------- | ------------- |
| NVIDIA GPU Acceletarion | ✅ |
| IGPU Acceleration | ⚠️ No video output, connector less framebuffer enabled, but video decoding support not checked. |
| Onboard Audio | ⛔ (USB Audio devices still work) |
| USB | ✅ |
| iServices | ⛔ |

### NVIDIA Setup
All required boot arguments all already setup, if you don't have an NVIDIA GPU you should restore the default SIP (remove NVRAM -> Delete -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> csr-active-config) and remove these arguments:
- amfi_get_out_of_my_way=0x1
- ngfxcompat=1
- ngfxgl=1
- nvda_drv_vrl=1

Note that because of the 500 series motherboard you won't get acceleration from the Intel IGPU.

If you have an NVIDIA GPU you need to install [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) and patch your system to enable NVIDIA support.