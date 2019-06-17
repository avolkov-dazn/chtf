# chtf
Install and manage multiple versions of [Hashicorp terraform](https://www.terraform.io).

## Installation
Copy script to a directory in your `$PATH`, i.e. `/usr/local/bin`. Set permissions to allow execution:
```bash
sudo cp chtf /usr/local/bin/
chmod 0755 /usr/local/bin/chtf
```
Test by executing *chtf* in your favourite terminal emulator. You should see usage example come up:
```bash
$ chtf
Usage: chtf 0.12.2
```

## Usage
The script takes terraform version as an argument. If the version does not exist locally it will download the version specified from [Hashicorp release page](https://releases.hashicorp.com/terraform/). The `sha256sum` is verified and the binary is unpacked to `/usr/local/bin` with a version number appended. A symbolic link is then created.

If the binary already exists, a symbolic link will be changed.

You should see a confirmation of the version installed when the process is finished:
```bash
$ chtf 0.12.2
[sudo] password for user:
Terraform v0.12.2 is good to go
```

Sudo is required to operate on `/usr/local/bin/`.