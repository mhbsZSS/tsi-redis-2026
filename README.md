@mhbsZSS ➜ /workspaces/tsi-redis-2026 (main) $ docker compose up -d
[+] Running 1/1
 ✔ Container redis-aula  Started                                                                                                       0.4s 
@mhbsZSS ➜ /workspaces/tsi-redis-2026 (main) $ redis-cli
bash: redis-cli: command not found
@mhbsZSS ➜ /workspaces/tsi-redis-2026 (main) $ docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED       STATUS          PORTS                                         NAMES
469abedd1dc0   redis:latest   "docker-entrypoint.s…"   3 weeks ago   Up 39 seconds   0.0.0.0:6379->6379/tcp, [::]:6379->6379/tcp   redis-aula
@mhbsZSS ➜ /workspaces/tsi-redis-2026 (main) $ docker exec -it redis-aula redis-cli
127.0.0.1:6379> SET usuario "Carlos"
OK
127.0.0.1:6379> GET usuario
"Carlos"
127.0.0.1:6379> SET usuario "Carlos Silva"
OK
127.0.0.1:6379> GET usuario
"Carlos Silva"
127.0.0.1:6379> MSET produto "Notebook" preco "3500" estoque "15"
OK
127.0.0.1:6379> MGET produto preco estoque
1) "Notebook"
2) "3500"
3) "15"
127.0.0.1:6379> SETNX admin "admin"
(integer) 1
127.0.0.1:6379> SETNX admin "admin"
(integer) 0
127.0.0.1:6379> SET nome "Maria"
OK
127.0.0.1:6379> GET nome
"Maria"
127.0.0.1:6379> APPEND nome " Oliveira"
(integer) 14
127.0.0.1:6379> STRLEN nome
(integer) 14
127.0.0.1:6379> GET nome
"Maria Oliveira"
127.0.0.1:6379> GETRANGE nome 0 5
"Maria "
127.0.0.1:6379> SET cidade "Campinas"
OK
127.0.0.1:6379> SETRANGE cidade 0 "São "
(integer) 8
127.0.0.1:6379> GET cidade
"S\xc3\xa3o nas"
127.0.0.1:6379> SET cidade "Campinas"
OK
127.0.0.1:6379> STRANGE cidade 0 "Sao "
(error) ERR unknown command 'STRANGE', with args beginning with: 'cidade' '0' 'Sao ' 
127.0.0.1:6379> SETRANGE cidade 0 "Sao "
(integer) 8
127.0.0.1:6379> GET cidade
"Sao inas"
127.0.0.1:6379> SET cidade "Campinas"
OK
127.0.0.1:6379> SETRANGE cidade 0 "São "
(integer) 8
127.0.0.1:6379> GET cidade
"S\xc3\xa3o nas"
127.0.0.1:6379> SET cidade "Campinas"
OK
127.0.0.1:6379> SETRANGE cidade 0 "Sao "
(integer) 8
127.0.0.1:6379> GET cidade
"Sao inas"
127.0.0.1:6379> SET pontos 10
OK
127.0.0.1:6379> GET pontos
"10"
127.0.0.1:6379> INCR pontos
(integer) 11
127.0.0.1:6379> INCRBY pontos 5
(integer) 16
127.0.0.1:6379> DECRBY pontos 3
(integer) 13
127.0.0.1:6379> GET pontos
"13"
127.0.0.1:6379> SET saldo 100.50
OK
127.0.0.1:6379> INCRBYFLOAT saldo 25.75
"126.25"
127.0.0.1:6379> GET saldo
"126.25"
127.0.0.1:6379> SETEX token 60 "123mh"
OK
127.0.0.1:6379> TTL token
(integer) 49
127.0.0.1:6379> PERSIST token
(integer) 1
127.0.0.1:6379> EXISTIS token
(error) ERR unknown command 'EXISTIS', with args beginning with: 'token' 
127.0.0.1:6379> EXISTS token
(integer) 1
127.0.0.1:6379> DEL token
(integer) 1
127.0.0.1:6379> SETEX token 60 "123mh"
OK
127.0.0.1:6379> TTL token
(integer) 55
127.0.0.1:6379> PERSIST token
(integer) 1
127.0.0.1:6379> EXISTS token
(integer) 1
127.0.0.1:6379> GET token
"123mh"
127.0.0.1:6379> SET sessao "sessao"
OK
127.0.0.1:6379> PEXPIRE sessao 5000
(integer) 1
127.0.0.1:6379> PTTL sessao
(integer) -2
127.0.0.1:6379> 

Atualização das atividades

docker compose up -d

docker ps

docker exec -it redis-aula redis-cli