# Tabela de Ocorrencias

Script para criar uma tabela de ocorrencias para disciplina de F129 da Unicamp.

Previsão para criação de histogramas: 26/09 :)

## Como usar:

Note que este tutorial é voltado para usuários de distribuições do Linux,
portanto algumas passagens podem ser diferentes caso você use outro SO.

Pré-requisitos: `python3`, `pip`, `pandas`, `plotly`, `orca` (ver seção de instalações)

1. Baixe os arquivos desse repositório para seu computador.

2. Vá para o diretório onde os arquivos estão (extraia os arquivos, se necessário).

3. Execute a seguinte linha em seu terminal:
```bash
$ python3 tabela_ocorrencias.py
```
4. A partir desse momento, você deve seguir os passos mostrados na tela de seu terminal.

## Instalações:

### Ubuntu (Debian):

Python3: `$ sudo apt-get install python3`

pip: `$ sudo apt-get install python3-pip`

plotly: `$ pip install plotly`

pandas: `$ pip install pandas`

psutil: `$ pip install psutil`

#### Orca:

1. Siga [este link](https://docs.conda.io/en/latest/miniconda.html) e baixe o pacote Miniconda para `python3` de acordo com seu SO e arquitetura.
2. Navegue para o diretório onde está o executável do Miniconda e digite a seguinte linha em seu terminal:
> Substitua `<executavel_miniconda.sh>` pelo nome do executável do Miniconda
```bash
$ sudo chmod -x <executavel_miniconda.sh>
```
3. Execute o instalador do Miniconda: `./<executavel_miniconda.sh>`
4. Após instalar o Miniconda, feche a janela de seu terminal e abra-a novamente.
5. Finalmente, para instalar a A.P.I. orca, digite a seguinte linha em seu terminal:
```bash
$ conda install -c plotly plotly-orca
```
Caso você encontre erros do tipo `No module named ***** found`, tente instalar `plotly`, `pandas` e `psutil`
através do comando `pip3 install <nome_do_pacote>` em vez de `pip install <nome_do_pacote>`

### Fedora (nos computadores do IC):

No lab do IC, `python3` e `pip` já estão instalados, portanto bastar instalar as bibliotecas `plotly` e `orca`.
Devemos utilizar a *flag* `--user` no final do comando `pip`, pois não temos permissão de administrador no IC.

plotly: `$ python3 -m pip install plotly --user`

Para criar a imagem com a tabela, você precisará da api orca. Para instalar essa api, primeiramente
vamos ter que configurar o *packet manager* `npm` do IC. Para isso, digite os seguintes comandos em seu terminal:
```bash
$ mkdir "${HOME}/.npm-packages"
```
```bash
$ npm config set prefix "${HOME}/.npm-packages"
```
Agora abra seu o arquivo `.bashrc` com seu editor de texto favorito e adicione as seguintes linhas:
> Não sabe o que é o arquivo `.bashrc`? Descubra o que ele é e como acessá-lo na próxima seção!
```bash
export PATH=$PATH:/$HOME/.local/bin

NPM_PACKAGES="${HOME}/.npm-packages"

export PATH="$PATH:$NPM_PACKAGES/bin"

\# Preserve MANPATH if you already defined it somewhere in your config.
\# Otherwise, fall back to `manpath` so we can inherit from `/etc/manpath`.
export MANPATH="${MANPATH-$(manpath)}:$NPM_PACKAGES/share/man"
```
> Lembre-se de usar o comando `source ~/.bashrc` para as mudanças no arquivo `.bashrc` tomarem efeito!
Após configurar o `npm`, use o seguinte comando para instalar a api orca:
```bash
$ npm install -g electron@1.8.4 orca
```
### Bashrc:

Para acessá-lo, digite em seu terminal:
```bash
$ <seu_editor_de_texto> ~/.bashrc
```
Se você não souber o que é o arquivo `.bashrc` e quiser ter uma noção básica de seus usos, acesse [este link](https://www.maketecheasier.com/what-is-bashrc/) e descubra!

## Observações:

Exemplos dos dados de entrada podem ser vistos na pasta "Exemplos de Entrada".

A tabela de ocorrências é gerada de acordo com as recomendações da disciplina F129 ministrada
no segundo semestre de 2019 na Unicamp.

Para quaisquer erros, dúvidas ou feedbacks, me contatar através do e-mail: m242096@dac.unicamp.br
