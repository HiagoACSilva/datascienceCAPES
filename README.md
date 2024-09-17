# datascienceCAPES
Repositório para receber, guardar e atualizar o projeto de ciência de dados que será utilizado como Trabalho de Conclusão de Curso.

* [Configurando o Ambiente de Trabalho](https://github.com/HiagoACSilva/datascienceCAPES?tab=readme-ov-file#configurando-o-ambiente-de-trabalho)
* [Instalando o WSL](https://github.com/HiagoACSilva/datascienceCAPES?tab=readme-ov-file#instalando-o-wsl)
* [Instalando as dependencias pelo WSL](https://github.com/HiagoACSilva/datascienceCAPES?tab=readme-ov-file#instalando-as-dependencias-pelo-wsl-usando-poetry)
* [Instalando o MinIO](https://github.com/HiagoACSilva/datascienceCAPES?tab=readme-ov-file#instalando-o-minio)
* [Baixando a pasta jars](https://github.com/HiagoACSilva/datascienceCAPES?tab=readme-ov-file#baixando-a-pasta-jars)
* [Executando o Projeto](https://github.com/HiagoACSilva/datascienceCAPES?tab=readme-ov-file#executando-o-projeto)

# Configurando o Ambiente de Trabalho
Nesse tópico será especificado como configurar o Ambiente de Trabalho, desde a instalação do WSL até as versões utilizadas das bibliotecas.

## Instalando o WSL
 
1. Abra o Windows PowerShell em modo Administrador
2. Execute o comando: ```wsl --install```

_Não é necessário uma versão específica do Ubuntu, pode-se instalar a versão mais atual._

## Instalando as dependencias pelo WSL usando Poetry

O projeto usa o Poetry para gerenciar as dependencias do projeto, logo para instalá-lo:

1. Abra o terminal do WSL
2. Digite o comando: ```pip install poetry```

Após instalar o **Poetry** já é possível instalar as dependências específicas utilizadas no projeto:

1. No terminal do WSL, faça o **clone** do projeto: ```git clone https://github.com/HiagoACSilva/datascienceCAPES.git```
2. Logo após entre no Diretório: ```cd datascienceCAPES```
3. Por fim execute o comando do Poetry para instalar as dependências específicas do Projeto: ```poetry install```

## Instalando o MinIO

Esse projeto utiliza o MinIO para armazenar os Bancos de Dados e também para dividir as etapas em buckets.
Para instalar execute os passos:

1. Abra o Terminal do WSL
2. Digite o seguinte código: ```wget https://dl.min.io/server/minio/release/linux-amd64/archive/minio_20240826153307.0.0_amd64.deb -O minio.deb```
3. Logo após: ```sudo dpkg -i minio.deb```
4. Por fim crie a pasta do MinIO: ```mkdir  ~/minio```

_Tutorial retirado do site oficial do MinIO: https://min.io/docs/minio/linux/index.html_

## Baixando a pastar jars

O projeto usa dois jars para execução, para baixá-los, os disponibilizei em meu Drive: _https://drive.google.com/drive/folders/1dkyoh3ErMhGAn6VeWh9Hia-SDnHv31yG?usp=sharing_
Faça download da pasta e coloque na pasta raiz do projeto, os dois arquivos precisam estar dentro da pasta para que a configuração do spark consiga localizá-los.

## Executando o Projeto

Concluído a instalação do **MinIO, Poetry** e das **dependências**, para executar o projeto execute os passos:

1. Abra duas abas do terminal do WSL
   * Para abrir uma nova guia aperte **ctrl**+**shift**+**4**
2. Na primeira aba inicie o MinIO.
   * Abra o diretório do MinIO: ```cd minio```
   * Execute o comando: ```minio server ~/minio --console-address :9001```
   * _Para abrir o MinIO, segurando o **Ctrl** aperte no segundo link que aparece após iniciar para abrir no seu navegador._
3. Na segunda aba abra o diretório do projeto: ```cd datascienceCAPES```
4. Após entrar no diretório, inicie o **Poetry**: ```poetry shell```
5. Por fim inicie o **Jupyter Notebook**: ```jupyter lab```
   * _Para abrir o **Jupyter Notebook** no seu navegador, segurando o **Ctrl** clique em qualquer um dos dois links que aparecem após iniciá-lo._

_Certifique-se que instalou todas as dependências do projeto usando o ```poetry install```, pois sem a execução desse trecho o comando de inicialização do Jupyter não funcionará_
