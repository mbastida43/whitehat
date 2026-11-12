# WhiteHat Linux 1.0 🇧🇷

[![Download Oficial ISO](https://img.shields.io/badge/Download_Oficial-ISO-238636?style=for-the-badge&logo=linux&logoColor=white)](https://github.com/mbastida43/whitehat/releases/download/v1.0/WhiteHat-1.0-x86_64.iso)

**Base:** Fedora Server 45 | **Interface:** 100% CLI | **Licença:** GNU GPL v3.0

Distribuição Linux minimalista em modo texto baseada no Fedora Server. Consulte o repositório para obter o guia completo de instalação via ISO ou o empacotamento WSL2 (`.wsl`).

---

## 📦 Empacotamento para WSL2 (.wsl)

Para compilar e gerar a imagem do WhiteHat Linux 1.0 para o Windows Subsystem for Linux (WSL2), você precisará estar em um ambiente host Fedora (ou outra distribuição compatível com o gerenciador de pacotes `dnf`).

### Instruções de Compilação

**1. Clonar o repositório:**
```bash
git clone [https://github.com/mbastida43/whitehat.git](https://github.com/mbastida43/whitehat.git)
cd whitehat
```

**2. Criar o diretório para o sistema de arquivos (RootFS):**
```bash
mkdir -p rootfs
```

**3. Instalar o sistema base:**
Utilize o `dnf` com a flag `--use-host-config` para usar os repositórios do host para baixar e construir o sistema base no novo diretório.
```bash
sudo dnf --installroot=$(pwd)/rootfs --releasever=40 --use-host-config install -y fedora-release dnf bash coreutils systemd passwd iproute util-linux
```

**4. Aplicar as configurações do WhiteHat:**
Copie os arquivos de configuração personalizados do repositório para o novo RootFS recém-criado.
```bash
sudo cp -r config/* rootfs/etc/
```

**5. Gerar o arquivo .wsl:**
Empacote o sistema de arquivos em um arquivo `tar` com a extensão `.wsl`, que é o formato nativo reconhecido pelo Windows para importação.
```bash
sudo tar -czpf whitehat-linux-1.0.wsl -C rootfs .
```

---

## 🚀 Importação e Instalação no Windows

Após gerar o arquivo `whitehat-linux-1.0.wsl`, mova-o para o sistema de arquivos do Windows (ex: copiando do WSL para `/mnt/c/Downloads/`). 

Abra o **PowerShell** no Windows e execute os comandos abaixo para importar a distribuição:

```powershell
# 1. Criar a pasta onde a máquina virtual será armazenada (exemplo)
mkdir C:\WSL\WhiteHat

# 2. Importar o arquivo .wsl
wsl --import WhiteHat C:\WSL\WhiteHat C:\Downloads\whitehat-linux-1.0.wsl

# 3. Iniciar a sua nova distribuição
wsl -d WhiteHat
```

<br>

---

<br>

# WhiteHat Linux 1.0 🇺🇸

[![Official ISO Download](https://img.shields.io/badge/Official_Download-ISO-238636?style=for-the-badge&logo=linux&logoColor=white)](https://github.com/mbastida43/whitehat/releases/download/v1.0/WhiteHat-1.0-x86_64.iso)

**Base:** Fedora Server 45 | **Interface:** 100% CLI | **License:** GNU GPL v3.0

Minimalist text-mode Linux distribution based on Fedora Server. Check the repository for the complete ISO installation guide or the WSL2 packaging (`.wsl`).

---

## 📦 Packaging for WSL2 (.wsl)

To compile and generate the WhiteHat Linux 1.0 image for the Windows Subsystem for Linux (WSL2), you will need to be in a Fedora host environment (or another distribution compatible with the `dnf` package manager).

### Build Instructions

**1. Clone the repository:**
```bash
git clone [https://github.com/mbastida43/whitehat.git](https://github.com/mbastida43/whitehat.git)
cd whitehat
```

**2. Create the file system directory (RootFS):**
```bash
mkdir -p rootfs
```

**3. Install the base system:**
Use `dnf` with the `--use-host-config` flag to use the host's repositories to download and build the base system in the new directory.
```bash
sudo dnf --installroot=$(pwd)/rootfs --releasever=40 --use-host-config install -y fedora-release dnf bash coreutils systemd passwd iproute util-linux
```

**4. Apply WhiteHat configurations:**
Copy the custom configuration files from the repository to the newly created RootFS.
```bash
sudo cp -r config/* rootfs/etc/
```

**5. Generate the .wsl file:**
Package the file system into a `tar` archive with the `.wsl` extension, which is the native format recognized by Windows for import.
```bash
sudo tar -czpf whitehat-linux-1.0.wsl -C rootfs .
```

---

## 🚀 Import and Installation on Windows

After generating the `whitehat-linux-1.0.wsl` file, move it to the Windows file system (e.g., copying from WSL to `/mnt/c/Downloads/`). 

Open **PowerShell** on Windows and run the commands below to import the distribution:

```powershell
# 1. Create the folder where the virtual machine will be stored (example)
mkdir C:\WSL\WhiteHat

# 2. Import the .wsl file
wsl --import WhiteHat C:\WSL\WhiteHat C:\Downloads\whitehat-linux-1.0.wsl

# 3. Start your new distribution
wsl -d WhiteHat
```
wsl --import WhiteHat C:\WSL\WhiteHat C:\Downloads\whitehat-linux-1.0.wsl

# 3. Iniciar a sua nova distribuição
wsl -d WhiteHat
```
