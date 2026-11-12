# WhiteHat Linux 1.0

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
Utilize o `dnf` com a flag `--use-host-config` para usar os reposit
