# ETL Project - API Data Extraction

Este projeto é um script Python que extrai, transforma e carrega (ETL) dados de preços do Bitcoin a partir da API da Coinbase e os armazena em um banco de dados PostgreSQL. O processo é executado em intervalos de 15 segundos e inclui logs via Logfire para monitoramento.

## Requisitos

Antes de executar o script, certifique-se de ter os seguintes requisitos instalados:

- Python 3.8+
- PostgreSQL

## Instalação

1. Clone este repositório:
   ```sh
   git clone https://github.com/rafaelporfiriobarros/ETLProjectAPIExtract.git
   cd ETLProjectAPIExtract
   ```

2. Crie e ative um ambiente virtual (opcional, mas recomendado):
   ```sh
   python -m venv venv
   source venv/bin/activate  # No Windows, use: venv\Scripts\activate
   ```

3. Instale as dependências:
   ```sh
   pip install -r requirements.txt
   ```

4. Configure as variáveis de ambiente no arquivo `.env`:
   ```ini
   POSTGRES_USER=seu_usuario
   POSTGRES_PASSWORD=sua_senha
   POSTGRES_HOST=localhost
   POSTGRES_PORT=5432
   POSTGRES_DB=seu_banco
   ```

## Estrutura do Código

O script realiza as seguintes operações:

1. **Carrega variáveis de ambiente** do arquivo `.env`.
2. **Configura o banco de dados PostgreSQL** usando SQLAlchemy.
3. **Extrai dados** da API da Coinbase.
4. **Transforma os dados**, adicionando um timestamp.
5. **Armazena os dados** no banco de dados PostgreSQL.
6. **Registra logs** via Logfire para monitoramento.
7. **Executa o processo continuamente** a cada 15 segundos.

## Como Executar

1. Certifique-se de que o PostgreSQL está rodando e configurado corretamente.
2. Execute o script:
   ```sh
   python pipeline_03.py
   ```
3. Para interromper a execução, pressione `CTRL + C`.

## Monitoramento

Os logs são registrados usando Logfire e podem ser visualizados diretamente no console.









