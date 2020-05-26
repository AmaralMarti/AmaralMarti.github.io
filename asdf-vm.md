## ASDF VM

Com o ASDF é possível instalar e gerenciar facilmente várias versões de ambientes de desenvolvimento (linguagens de programação, bancos de dados entre outros). Por exemplo, é possível ter várias versões do PHP instaladas simultâneamente no seu ambiente, alternar facilmente entre elas conforme precisar e até definir uma versão específica para um diretório.

Os ambientes são instalados em forma de plungins, a lista de plugins é muito extensa e possui nomes conhecidos como:

* Python
* PHP
* Node.JS
* Deno
* .Net Core
* Erlang
* Elixir
* Rust
* Heskell

A lista completa de plugins pode ser acessada [aqui](https://asdf-vm.com/#/plugins-all).

### Como instalar (no Ubuntu)

É possível ver os detalhes de instalação diretamente na página do projeto [nesse link](https://asdf-vm.com/#/core-manage-asdf-vm), mas para ser mais objetivo vou deixar o passo a passo para instalação no **Ubuntu**.

**1 - Clone o repositório**
```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf
cd ~/.asdf
git checkout "$(git describe --abbrev=0 --tags)"
```

**2 - Adicione a configuração abaixo no arquivo** `~/.bashrc`
```bash
. $HOME/.asdf/asdf.sh
. $HOME/.asdf/completions/asdf.bash
```

**3 - Recarregue as configurações**
```bash
source ~/.bashrc
```

### Como usar (usando Go Lang como exemplo)

Acesse a página de plugins disponíveis e selecione o que desejar, aqui vou usar o Go Lang como um exemplo

**1 - Adicionar o plugin**
 
```bash
asdf plugin-add golang https://github.com/kennyp/asdf-golang.git
```

**2 - Listar as versões disponíveis para instalação**

```bash
asdf list-all golang
```
**Atenção:** Será exibida uma lista com todas as versões disponíveis para instalação

**3 - Instalar as versões escolhidas**

```bash
# instalação da versão 1.13.11
asdf install golang 1.13.11

## instalação da versão 1.14.3
asdf install golang 1.14.3
```

**4 - Ativar a versão desejada**

```bash
# ativação da versão 1.13.11 de forma global no sistema
asdf global golang 1.13.11
```

```bash
# ativação da versão 1.14.3 no diretório ~/golang-14

mkdir ~/golang-14
cd ~/golang-14
asdf local golang 1.14.3
```
**Atenção:** quando uma versão é definida de forma local são criados arquivos e diretórios com a parametrização da versão. Independente da versão definida globalmente, dentro do diretório a versão disponível será aquela definida localmente, inclusive o pacotes e libs instalados serão instalados apenas no ambiente dentro do diretório.
