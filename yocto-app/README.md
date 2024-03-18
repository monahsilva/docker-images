# Construindo um contêiner para gerar uma imagem Linux usando Yocto Project

## Descrição
Este repositório contém um Dockerfile que permite construir um contêiner Docker para gerar imagens Linux usando o Yocto Project.

## Pré-requisitos
Certifique-se de ter o Docker instalado em sua máquina. Você pode baixá-lo em [Docker's website](https://www.docker.com/get-started).

## Instalação e Uso

### 1. Clonar o Repositório e entre na branch
```bash
git clone https://github.com/monahsilva/docker-images.git
cd docker-images
git checkout docker-yocto-project
cd yocto-app
```

### 2. Construir a Imagem
Dentro do diretório clonado, execute o seguinte comando:
```bash
docker build -t yocto-container .
```

### 3. Executar o Contêiner
Após a construção da imagem, execute o contêiner:
```bash
docker run -it yocto-container
```
## Uso do Contêiner
Dentro do contêiner, você estará no diretório do projeto Yocto e poderá executar os comandos do Yocto, como bitbake, para gerar a imagem desejada. Lembre-se de que você pode precisar ajustar o Dockerfile conforme necessário para atender às especificidades do seu projeto Yocto.

## Modificações nas Camadas e Receitas
Se precisar realizar modificações nas camadas e receitas, entre no contêiner:
```bash
docker exec -it yocto-container /bin/bash
```
Este comando iniciará um shell interativo dentro do contêiner yocto-container e você poderá executar o bitbake ou outros comandos conforme necessário.


Este README.md fornecerá informações claras e concisas sobre como clonar, construir e usar o contêiner Docker para gerar imagens Linux usando o Yocto Project.


