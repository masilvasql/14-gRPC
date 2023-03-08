# Iniciando com o GRPC no GO

### Instalar Protocol Buffer Compiler -> Fonte: https://grpc.io/docs/protoc-installation/
* Instalar no WSL2 (usar APT GET)
* No windows seguir os passos a baixo:
    * acessar o link : https://github.com/protocolbuffers/protobuf/releases
    * Baixar o protoc-22.0-win64.zip
    * Extrair
    * acessar a pasta bin
    * criar uma pasta chamada "protoc" no disco local C
    * copiar o arquivo protoc.exe para esta pasta
    * Editar as variáveis de ambiente
    * Criar um novo registro na variável PATH com o valor C:\protoc\protoc.exe
    

### Instalar depenências no GO -> Fonte: https://grpc.io/docs/languages/go/quickstart/

* go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28 
    * Gera as interfaces/Entidades   
* go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2
    * Gera todas as interfaces de comunicação


### comando para gerar o build baseado no protofile
* protoc --go_out=. --go-grpc_out=. proto/course_category.proto


### Arquivos
* course_category_grpc.pb.go
    * Analisar as interfaces do Server e do cliente, neste caso "UnsafeCategoryServiceServer" e "CategoryServiceClient"    

### Utilizando EVANS
* instalação
    * No CMD -> go install github.com/ktr0731/evans@latest
    * Após instalado, basta rodar -> evans -r repl 

### Terminal do Evans
* Caso você tenha mais de um service registrado, deverá digitar -> service NomeDoService
* call CreateCategory (ENTER)
    * Irá aparecer os campos do serviço para ser enviado, com base no PROTOC

### SQLITE3
sqlite3 .\db.sqlite (nome do arquivo sqlite que vc criou)
create table categories (id string, name string, description string);