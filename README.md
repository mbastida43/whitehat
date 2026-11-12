# WhiteHat Linux 1.0

**Base:** Fedora Server 45 | **Interface:** 100% CLI (Modo Texto) | **Containers:** Podman & Docker | **Licenca:** GNU GPL v3.0

Distribuicao Linux minimalista em modo texto, baseada nos pacotes oficiais do Fedora Server, projetada para ser enxuta, rodar diretamente em memoria RAM ou instalada em disco, e contar com gerenciador de pacotes nativo.

---

## Download Oficial

* **[Baixar WhiteHat Linux 1.0 (x86_64 ISO - 291 MB)](../../releases/download/v1.0/WhiteHat-1.0-x86_64.iso)**
* **[Acessar Pagina de Releases e Versoes](../../releases)**

---

## Recursos Principais

* **100% Modo Texto (CLI):** Boot ultrarrapido sem interface grafica.
* **Gerenciador de Pacotes:** Suporte nativo ao `dnf5` para atualizacoes online (`sudo dnf update`).
* **Primeiro Boot Interativo:** Assistente de criacao de usuario comum com validacao de senha em 2 etapas e elevacao via `sudo`.
* **Containers:** Suporte nativo a `podman` e emulacao completa via comando `docker`.
* **Instalador Permanente:** Script `whitehat-install` embutido para gravacao em disco rigido ou pendrive.
* **Identidade Customizada:** Comando `whitefetch` integrado para exibir informacoes do sistema.

---

## Como Testar em Maquina Virtual (ISO)

1. Baixe o arquivo **`WhiteHat-1.0-x86_64.iso`** no link da secao **Download Oficial** acima.
2. Crie uma maquina virtual **Linux / Fedora (64-bit)** com pelo menos **1 GB de RAM** (2 GB recomendados para usar containers).
3. Aponte a ISO no leitor optico virtual e inicie a maquina.
4. Na primeira inicializacao, siga o assistente na tela para criar seu **usuario comum** e senha.

---

## Como Criar e Instalar uma Versao `.wsl` (Windows 11 / WSL2)

O formato moderno **`.wsl`** permite distribuir e instalar a WhiteHat no Windows com apenas um clique duplo (ou via comando `wsl --install --from-file`), sem precisar de maquina virtual ou kernel proprio.

### 1. Gerar o pacote `WhiteHat.wsl` (a partir de um Linux/Fedora)

Em um ambiente Fedora, extraia a base minima sem o kernel (pois o WSL2 usa o kernel do Windows) e adicione os arquivos de configuracao do WSL:

    mkdir -p ~/whitehat-wsl/rootfs/etc

    sudo dnf install -y --installroot=$HOME/whitehat-wsl/rootfs --use-host-config --releasever=45 --nogpgcheck --setopt=install_weak_deps=False fedora-release-server fedora-repos fedora-gpg-keys dnf5 rpm bash coreutils util-linux procps-ng iproute iputils ca-certificates nano ncurses hostname shadow-utils sudo podman podman-docker git python3 nmap curl

    printf "[boot]\nsystemd=false\n\n[user]\ndefault=root\n" | sudo tee ~/whitehat-wsl/rootfs/etc/wsl.conf > /dev/null

    printf "[oobe]\ndefaultUid = 0\ndefaultName = WhiteHat\n" | sudo tee ~/whitehat-wsl/rootfs/etc/wsl-distribution.conf > /dev/null

    sudo rm -rf ~/whitehat-wsl/rootfs/var/cache/* ~/whitehat-wsl/rootfs/usr/share/{doc,man,info}
    cd ~/whitehat-wsl/rootfs
    sudo tar --numeric-owner -czvf /mnt/c/WhiteHat/WhiteHat-1.0.wsl *

### 2. Instalar no Windows

Com o arquivo **`WhiteHat-1.0.wsl`** gerado, voce pode instala-lo de duas formas no Windows:

* **Instalacao Visual (Clique Duplo):** De um clique duplo sobre o arquivo `WhiteHat-1.0.wsl` no Explorador de Arquivos do Windows.
* **Via PowerShell:** `wsl --install --from-file C:\WhiteHat\WhiteHat-1.0.wsl`
* **Para iniciar a distro:** `wsl -d WhiteHat`

---

## Credenciais Padrao (ISO)

* **Usuario Root:** `root`
* **Senha Root:** `whitehat`
* **Elevacao de privilegios:** Use `sudo su` ou `sudo dnf update` a partir do seu usuario comum.
