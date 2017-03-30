#   lspci -v   =  voir vos info drivers! 

#   00:19.0 Ethernet controller: Intel Corporation 82577LM Gigabit Network Connection (rev 06)
  Subsystem: Lenovo Device 2153
  Flags: bus master, fast devsel, latency 0, IRQ 44
  Memory at f2400000 (32-bit, non-prefetchable) [size=128K]
  Memory at f2425000 (32-bit, non-prefetchable) [size=4K]
  I/O ports at 1820 [size=32]
  Capabilities: <access denied>
  Kernel driver in use: e1000e


#   03:00.0 Network controller: Intel Corporation Centrino Wireless-N 1000 [Condor Peak]
  Subsystem: Intel Corporation Centrino Wireless-N 1000 BGN
  Flags: bus master, fast devsel, latency 0, IRQ 46
  Memory at f2000000 (64-bit, non-prefetchable) [size=8K]
  Capabilities: <access denied>
  Kernel driver in use: iwlwifi
                          
                                     INFO
//wiki.debian.org/fr/iwlwifi


Ajoutez la source "non-free" à votre fichier /etc/apt/sources.list, par exemple :

# Debian 8 "Jessie"
deb http://httpredir.debian.org/debian/ jessie main contrib non-free

Mettez à jour la liste des paquets disponibles et installez le paquet firmware-iwlwifi :

# apt-get update && apt-get install firmware-iwlwifi

Comme le module iwlagn est automatiquement chargé pour les périphériques pris en charge, vous devez le recharger pour qu'il puisse accéder au firmware que vous avez installé :

# modprobe -r iwlwifi ; modprobe iwlwifi

Configurez l'interface de votre réseau sans fil. 
