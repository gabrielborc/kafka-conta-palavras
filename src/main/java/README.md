# Conta Palavras

## Requisitos

- Java 11
- Docker
- Docker Compose

## Executar


Subir ambiente do kafka, na raiz do projeto execute o seguinte comando:

```
$ docker-compose up
```

Ainda na raiz do projeto execute a aplicação em spring boot com o seguinte comando, no seu terminal:

```
$ ./mwvn clean spring-boot:run
```

Agora para testar na raiz do projeto execute o seguinte comando abaixo, então escreva as palavras que irão gerar os eventos

```
$ docker-compose exec kafka kafka-console-producer --bootstrap-server localhost:9092 --topic entrada
>teste teste algo
>alguma coisa
>
```

Para finalizar, para consultar os resultados rode na raiz do projeto o seguinte comando:

```
$ docker-compose exec kafka kafka-console-consumer --bootstrap-server localhost:9092 --topic resultado --from-beginning
```
