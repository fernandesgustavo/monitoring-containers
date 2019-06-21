# monitoring-containers

Projeto de monitoramento baseado em containers.

# Serviços

- Zabbix server (futuro)
- Zabbix web (futuro)
- Grafana (em andamento)

# Primeiros passos

Clonar o projeto:

- git clone https://github.com/fernandesgustavo/monitoring-containers.git

Criar o arquivo .env:

- Copiar ou renomear o arquivo "example.env" para ".env"

# Instalação do Docker

- curl -fsSL https://get.docker.com | sh

# Arquivo .env

Configure os valores para os serviços de acordo com o seu ambiente:

#### - Zabbix server (futuro)
#### - Zabbix web (futuro)

#### - Grafana (em andamento):
- Documentação oficial https://grafana.com/docs/installation/docker/
- Os locais de armazenamento são default, caso queira customizar, atualize as variáveis na seção GRAFANA > Paths, de acordo com a documentação
- Os parâmetros do arquivo defaults.ini são default, caso queira customizar, atualize as variáveis na seção GRAFANA > Defaults.ini
- O container vem com os plugins default, caso precise instalar outro, adicione os nomes a variável GF_INSTALL_PLUGINS, separados por vírgula
- Para qualquer alteração anterior, se faz necessário adicionar a variável de ambiente na seção grafana > environment, do arquivo docker-compose.yml
- Caso já possua um banco de dados, em sqlite por exemplo, copie o arquivo grafana.db para /var/lib/grafana no host, o mesmo será mapeado para /var/lib/grafana no container
- Por default os Logs serão salvos em /var/log/grafana no host, pois o mesmo será mapeado em /var/log/grafana no container
- Por default o Grafana será executado na porta 3000 do host, caso queira customizar, atualize a variável GRAFANA_PORT
- Por default o container terá o nome "empresa-grafana-latest", caso queira customizar, atualize a variável GRAFANA_CONTAINER
- Por default o container terá a última versão do Grafana disponível, caso queira customizar, utilize a variável GRAFANA_VERSION
    
# Arquivo docker-composer.yml

- Arquivo de configuração dos serviços

# Construir e Executar

Para executar todos os serviços:

- docker-compose up -d 

Para executar alguns serviços:

- docker-compose up -d grafana

# Excluir e Limpar

Para excluir e limpar todos os serviços:

- docker-compose down

Para excluir e limpar alguns serviços:

- docker-compose down grafana

# Iniciar

Iniciar todos os serviços:

- docker-compose start

Iniciar alguns serviços:

- docker-compose start grafana

# Parar sem excluir

Parar todos os serviços:

- docker-compose stop

Parar alguns serviços:

- docker-compose stop grafana
