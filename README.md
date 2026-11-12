# WhiteHat Linux 1.0

Distribuição Linux minimalista em modo texto, baseada nos pacotes oficiais do Fedora Server, projetada para ser mais enxuta que o Alpine Linux em ambiente CLI e rodar diretamente em memória RAM ou instalada em disco.

## Recursos Principais
* **100% Modo Texto (CLI):** Boot ultrarrápido sem interface gráfica.
* **Gerenciador de Pacotes:** Suporte nativo ao `dnf5` para atualizações online (`sudo dnf update`).
* **Primeiro Boot Interativo:** Assistente de criação de usuário comum com validação de senha em 2 etapas e elevação via `sudo`.
* **Containers:** Suporte nativo a `podman` e emulação via comando `docker`.
* **Instalador Permanente:** Script `whitehat-install` embutido para gravação em disco rígido ou pendrive.
* **Identidade Customizada:** Comando `whitefetch` integrado.

## Credenciais Padrão (Caso acesse como Root)
* **Usuário:** `root`
* **Senha:** `whitehat`
