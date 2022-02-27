# Booting up in win11
>https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-secure-boot
>https://docs.microsoft.com/zh-CN/windows/security/information-protection/
## Boot sequence
After the PC is turned on, the signature databases are each checked against the platform key.
If the firmware is not trusted, the UEFI firmware must initiate OEM-specific recovery to restore trusted firmware.
If there is a problem with Windows Boot Manager, the firmware will attempt to boot a backup copy of Windows Boot Manager. If this also fails, the firmware must initiate OEM-specific remediation.
After Windows Boot Manager has started running, if there is a problem with the drivers or NTOS kernel, Windows Recovery Environment (Windows RE) is loaded so that these drivers or the kernel image can be recovered.
Windows loads antimalware software.
Windows loads other kernel drivers and initializes the user mode processes.
## BitLocker automatic device encryption
>https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-bitlocker#bitlocker-automatic-device-encryption
>https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-secure-boot
### bitlocker countermeasures
>https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-countermeasures
### Disable BitLocker automatic device encryption
OEMs can choose to disable device encryption and instead implement their own encryption technology on a device. To disable BitLocker automatic device encryption, you can use an Unattend file and set PreventDeviceEncryption to True. Alternately, you can update this registry key: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\BitLocker Value: PreventDeviceEncryption equal to True (1).