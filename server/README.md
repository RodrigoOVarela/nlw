1 Instalar node via package manager através do chocolatey
    -  https://chocolatey.org/   > install now 
    - Run Get-ExecutionPolicy. If it returns Restricted, then run Set-ExecutionPolicy AllSigned or Set-ExecutionPolicy Bypass -Scope Process. 
    - Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
    - no powershell como admin executar choco para validar se foi isntalado

2 Instalar node via choco
    - cinst nodejs or choco install-lts 
    - versão node e npm instalada

3 Criar pasta server e abrir com vscode com o comando code . dentro da pasta
    - npm install express instalar dependencias do express
    - Ao importar expresso em caso de erro  npm install @types/express ou npm install @types/express -D  o menos D para que essa dependencia seja utilizada apenas em dev e não em prod.


4 Node só entende Javascript para entender o typescript é necessário instalar dependencia
    - npm install typescript -D instalar typescript
    - npm install ts-node -D instalar dependecias do typescript para que o node entenda ele
    - npx tsc --init arquivo de configuração do typescript
    - npx ts-node src/server.ts executar aplicação
    - npm install ts-node-dev -D  comando para que não seja necessário sempre que fazer uma alteração parar o server e executar de novo assim sempre atualizará em tempo de dev
    -  npx ts-node-dev src/server.ts executar para que seja sempre atualziado automaticamente

5 Instalar knex para utilizar escrita de banco de dados com javascript
    - npm install knex

6 Instalar SQLite3
    - npm install sqlite3

7 Rodar migrations e criar banco
    - npx knex migrate:latest --knexfile knexfile.ts migrate:latest
    - visualizar db no vscode usar extensão sqlite, ctrl + shift + p digitar sqlite  e selecionar opção open database e selecionar o banco, após isso acessar o sqlite explorer canto inferior esquerdo do vscode
    - Utilziar os seeds para popular a base com dados default

8 Habilitar CORS
    - npm install cors
    - npm install @types/cors   instalando dependências do CORS 


OBS:
//Request Param: Parâmetros que vem na própria rota que identificam um recurso
// Query Param: Parâmetros opcionais para executar filtros, paginação
// Request Body: Parâmetros para criação e atualização de informação