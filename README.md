# Documentação: Executando o Aplicativo da Calculadora Localmente com a CLI do React Native

Esta documentação fornece instruções passo a passo sobre como executar o aplicativo da calculadora desenvolvido com a CLI do React Native em sua máquina local. Siga as etapas abaixo para iniciar o aplicativo em um ambiente de desenvolvimento.

## Pré-requisitos

Antes de prosseguir, certifique-se de ter as seguintes dependências instaladas em sua máquina:

- [Node.js](https://nodejs.org) (versão 14 LTS ou superior)
- [Yarn](https://yarnpkg.com) (opcionalmente você pode usar o npm)

Além disso, você precisará configurar o ambiente de desenvolvimento do Android, incluindo a instalação do Android SDK e a configuração das variáveis de ambiente necessárias. Certifique-se de seguir as instruções apropriadas para o seu sistema operacional.

## Passo 1: Clonando o Repositório

1. Abra um terminal e navegue até o diretório onde deseja clonar o repositório.
2. Execute o seguinte comando para clonar o repositório:

```shell
git clone <URL_DO_REPOSITÓRIO>
```

Substitua `<URL_DO_REPOSITÓRIO>` pela URL do repositório Git da calculadora.

## Passo 2: Instalando as Dependências

1. Navegue para o diretório do projeto executando o seguinte comando:

```shell
cd reactnative-calculator
```

2. Instale as dependências do projeto executando um dos seguintes comandos, dependendo do gerenciador de pacotes que você está usando:

Com Yarn:

```shell
yarn install
```

Com npm:

```shell
npm install
```

Isso instalará todas as dependências necessárias para o projeto.

## Passo 3: Configurando o Android SDK

Se você ainda não configurou o Android SDK em sua máquina, siga as etapas apropriadas para o seu sistema operacional. Caso contrário, pule para o próximo passo.

### Configurando o `sdk.dir` (caminho do SDK) no Android

Para que o React Native possa encontrar o SDK do Android em sua máquina, você precisa definir a variável de ambiente `ANDROID_SDK_ROOT` ou configurar o caminho `sdk.dir` manualmente no arquivo `local.properties`. Siga as etapas abaixo, dependendo do seu sistema operacional:

#### Windows:

1. Abra o arquivo `local.properties` localizado na pasta `android` do projeto.
2. Adicione a seguinte linha ao arquivo:

```
sdk.dir = C:\\Users\\<nome_do_usuário>\\AppData\\Local\\Android\\Sdk
```

Substitua `<nome_do_usuário>` pelo nome do usuário do seu sistema.

#### macOS:

1. Abra o arquivo `local.properties` localizado na pasta `android` do projeto.
2. Adicione a seguinte linha ao arquivo:

```
sdk.dir = /Users/<nome_do_usuário>/Library/Android/sdk
```

Substitua `<nome_do_usuário>` pelo nome do usuário do seu sistema.

#### Linux:

1. Abra o arquivo `local.properties` localizado na pasta `android` do projeto.
2. Adicione a seguinte linha ao arquivo:

```
sdk.dir = /home/<nome_do_usuário>/Android/Sdk
```

Substitua `<nome_do_usuário>` pelo nome do usuário do seu sistema.

Certifique-se de substituir `<nome_do_usuário>` pelo nome correto do usuário em seu sistema. Além disso, verifique se o caminho fornecido para `sdk.dir` está correto e aponta para a instalação do SDK do Android em sua máquina.

## Passo 4: Gerando a Keystore de Depuração (Debug Keystore)

A keystore de depuração é necessária para compilar o aplicativo para Android. Se você já possui uma keystore de depuração, pule para o próximo passo. Caso contrário, siga as etapas abaixo para gerar uma keystore de depuração:

1. Abra um terminal e navegue até o diretório `android/app` do projeto.
2. Execute o seguinte comando para gerar uma nova keystore de depuração:

```shell
keytool -genkey -v -keystore debug.keystore -storepass android -alias androiddebugkey -keypass android -keyalg RSA -keysize 2048 -validity 10000
```

Este comando irá gerar um novo arquivo `debug.keystore` com as configurações fornecidas. Certifique-se de lembrar a senha que você definiu durante esse processo.

## Passo 5: Iniciando o Servidor de Desenvolvimento

1. Abra um terminal e navegue até o diretório do projeto, se ainda não estiver nele.
2. Execute o seguinte comando para iniciar o servidor de desenvolvimento:

```shell
yarn start
```

Isso iniciará o Metro Bundler, que é responsável por empacotar e servir o código JavaScript do aplicativo.

## Passo 6: Compilando e Executando o Aplicativo no Android

1. Abra outro terminal e navegue até o diretório do projeto, se ainda não estiver nele.
2. Execute o seguinte comando para compilar e executar o aplicativo no emulador ou dispositivo Android conectado:

```shell
yarn android
```

Este comando irá compilar o aplicativo Android e iniciá-lo no emulador ou dispositivo conectado.

Após a execução bem-sucedida desses comandos, o aplicativo da calculadora será iniciado no emulador ou dispositivo Android.

Parabéns! Agora você conseguiu executar o aplicativo da calculadora desenvolvido com a CLI do React Native em sua máquina local.

Observação: Para a execução do aplicativo no iOS, você precisará seguir etapas adicionais e ter o ambiente de desenvolvimento do iOS configurado corretamente em sua máquina.

