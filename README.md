# WhiteHat Linux 1.0

![Base](https://shields.io)
![Interface](https://shields.io)
![License](https://shields.io)
![Containers](https://shields.io)

Distribuição Linux minimalista em modo texto, baseada nos pacotes oficiais do Fedora Server, projetada para ser enxuta, rodar diretamente em memória RAM ou instalada em disco, e contar com gerenciador de pacotes nativo.

[![Download ISO](https://shields.io)](https://github.com)

---

## Recursos Principais

* **100% Modo Texto (CLI):** Boot ultrarrápido sem interface gráfica.
* **Gerenciador de Pacotes:** Suporte nativo ao `dnf5` para atualizações online (`sudo dnf update`).
* **Primeiro Boot Interativo:** Assistente de criação de usuário comum com validação de senha em 2 etapas e elevação via `sudo`.
* **Containers:** Suporte nativo a `podman` e emulação completa via comando `docker`.
* **Instalador Permanente:** Script `whitehat-install` embutido para gravação em disco rígido ou pendrive.
* **Identidade Customizada:** Comando `whitefetch` integrado para exibir informações do sistema.

---

## Como Testar (VirtualBox / VMware / QEMU)

1. Baixe o arquivo **`WhiteHat-1.0-x86_64.iso`** clicando no botão verde acima.
2. Crie uma máquina virtual **Linux / Fedora (64-bit)** com pelo menos **1 GB de RAM** (2 GB recomendados para usar containers).
3. Aponte a ISO no leitor óptico virtual e inicie a máquina.
4. Na primeira inicialização, siga o assistente na tela para criar seu **usuário comum** e senha.

---

## Credenciais Padrão (Acesso Administrativo)

* **Usuário Root:** `root`
* **Senha Root:** `whitehat`
* **Elevação de privilégios:** Use `sudo su` ou `sudo dnf update` a partir do seu usuário comum.
