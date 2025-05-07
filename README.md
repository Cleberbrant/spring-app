
# WEMOB Fleet Station

  

WEMOB Fleet Station is a WEG project for managing charging stations.

  

## Getting Started

  

###  Clone the Repository

  

`git clone https://gitlab.weg.net/wdi/eldorado/wemob-fleet-station.git`

`cd wemob-fleet-station`

  

## Configuration

Prepare environment to work with [Angular v12.2.17](https://www.npmjs.com/package/@angular/cli/v/12.2.17)

### Required

- [Node v16.20.0](https://nodejs.org/en/blog/release/v16.20.0) or earlier.

- [Angular CLI v12.2.17](https://www.npmjs.com/package/@angular/cli/v/12.2.17)

Install the project dependencies:

`npm install`

_Ignore warnings related to Angular version. If you encounter errors during dependency installation, try:_

`npm install --force`

## Server

Run `ng serve -c {environment}` or `npm run start:{environment}` (_e.g.: `ng serve -c dev`/`npm run start:dev`_) to start the server.

### Server environments:

**dev,  stg, prod, test**

Navigate to `http://localhost:4200/`.

_The app will automatically reload if you change any of the source files._

## Build

Run `ng build -c {environment}` or `npm run build:{environment}` (_e.g.: `ng build -c dev`/`npm run build:dev`_) to build the project.

### Build environments:

**prd1, prd2, prod, dev, uat, stage, test, test2, test3, stats**

The build artifacts will be stored in the `dist/` directory.

## Unit tests

Run `ng test` or `npm run test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Comissionar uma Estação de Recarga

**Para comissionar uma estação de recarga pelo simulador, entre no [Colab](https://colab.research.google.com/drive/11KldWVq9n7QA0PgX7pj0Yi-JBo08x6A3#scrollTo=JUvVo8xPK4eQ) destinado a criação e simulação de uma estação de recarga, e faça uma cópia do Colab em seu Google Drive.**

Após isso, ache o tópico **Rotina Principal e Inicialização da Estação de recarga** e siga na configuração para respectivo uso:

> Abaixo temos a principal parte de configuração do simulador, as seguintes variáveis de cp podem ser alteradas para seu ambiente teste:

- **chageboxId:** Identificador da estação, muito utilizado para localizar a estação no SFM
- **vendor:** Fabricante da estação
- **model:** Modelo da estação
- **firmware:** Firmware da estação
- **numberOfConnectors:** Número de conectores da estação
- **power:** Força da estação
- **voltage:** Voltagem da estação
- **url:** Ambiente em que a sua estação será simulada (Comuns: PRD2 e DEV)

```
chargeboxId = 'teste-chagebox'

cp = ChargeBox(id = chargeboxId,
              vendor = 'WEG-WEMOB',
              model = 'P-023-1T',
              #firmware = 'OuLoadBalancer.1.2 | Ocpp.1.2 | Modbus.1.2',
              firmware = '4.2.0',
              numberOfConnectors = 1,
              power = 2350,
              voltage = 220,

              # url = 'ws://ocpp.weg.net/ocpp/chargebox/',                                                 #PRD - RELEASE,
              # url = 'ws://wemobv3base-ocpp-prd1.sa-east-1.elasticbeanstalk.com/ocpp/chargebox/',         #PRD1,
              # url = 'ws://wemobv3base-ocpp-prd2.sa-east-1.elasticbeanstalk.com/ocpp/chargebox/',          #PRD2 - AMBIENTE DE HOMOLOGAÇÂO
              # url = 'wss://ocpp-dev.weg.net/ocpp-dev/chargebox/',          #DEV
              # url = 'ws://WEMOBDevALBOcpp-577945721.sa-east-1.elb.amazonaws.com/ocpp-dev/chargebox/',
              # url = 'ws://WEMOBDevALBOcpp-577945721.sa-east-1.elb.amazonaws.com/ocpp-dev/chargebox/',        #DEV - PARALELO
              # url = 'ws://wemobdev-ocpp-dev.sa-east-1.elasticbeanstalk.com/ocpp-dev/chargebox/',

              serialNumber = chargeboxId,
              cbSerialNumber = chargeboxId,
              freeMode = True,
              autoMode = True
              )
 ```

> [!CAUTION]
> - Crie uma cópia do simulador no seu drive antes de utilizar para os testes.

> [!WARNING]
> - Sempre rode todas as células ao executar o programa pela primeira vez (Ctrl + F9)
> - Para garantir o funcionamento correto, encerre o programa com a entrada de texto 'X', dessa forma, é necessário rodar apenas a última célula para comissionar uma nova estação.
> - Caso o programa não tenha sido encerrado corretamente e apresente problemas, basta reiniciar o ambiente de execução no menu 'Ambiente de execução' > 'Reiniciar ambiente de execução'.
