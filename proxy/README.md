# Serviço Proxy

## Sobre
O servidor proxy atua como intermediário entre uma rede local e a Internet. O objetivo desse trabalho é implantar esse serviço.
Utilizaremos o  Proxy-Web Privoxy. Os passos descritos são para implantação do serviço nas distribuições Debian e Ubuntu. 

- Para instalação/configuração em outras plataformas consulte o [site oficial](https://www.privoxy.org).
- [Apresentação Proxy](http://prezi.com/um-iqhoie4rv/?utm_campaign=share&utm_medium=copy)

## Instalação
Instalação nas distribuições Debian e Ubuntu:
```bash
$ sudo apt-get install privoxy
```

## Configuração
Após a instalação, deve-se alterar o arquivo de configuração do Privoxy para que ele responda à sua necessidade.

Meu cenário:
- Rede local 172.16.200.0/24
- 1 computador com acesso externo.

### Configuração do Servidor
Abrindo o arquivo de configuração
```bash
$ gedit /etc/privoxy/config &
```

O O Privoxy contém uma documentação muito completa e bem especificada. No arquivo de configuração os comandos estão bem especificados e exemplificados.

#### Comandos utilizados

- **listen-address**: definindo o IP e a Porta do Servidor Proxy (por onde ele irá escutar as requisições dos clientes).
      Exemplo: Rede local 172.16.200.0. Configurando a máquina 172.16.200.1 para escutar os clientes na porta 8118:
      ```listen-adress 172.16.200.1:8118``` 
- **permit-access**: define os IPs que podem acessar o Proxy.
    Exemplo: Todos os computadores da rede local 172.16.200.0
  ```permit-access 172.16.200.0/24```

### Configuração dos Clientes

Após configurar o servidor, é preciso configurar os clientes, essa configuração é feita no navegador de cada máquina.


## Referências
- [Privoxy](https://www.privoxy.org).
