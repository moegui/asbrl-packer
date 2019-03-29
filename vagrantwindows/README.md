# Create Vagrant Box from Packer

## Requirements
+  Packer version 1.3.5 or higher. (https://www.packer.io/downloads.html)
+ VirtualBox version 6.0.4 or higher (https://www.virtualbox.org/wiki/Downloads)
+ Modify parameter "iso_url" on ws16base.json with correct location of your Windows Server 2016 Standard ISO.
+ Modify parameters iso_checksum_type and iso_checksum with correct value. If you don't have a checksum ISO, you can use the following command to recreate it:

```bash
md5 /folderexample/windowsserver2016.iso
```

After that, copy result into parameter iso_checksum and put "md5" into iso_checksum_type.

## How to Run

sudo packer build -only=virtualbox-iso -force ws16base.json 
