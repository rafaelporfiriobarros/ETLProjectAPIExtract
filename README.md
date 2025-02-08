# ETL Project - API Data Extraction

Este projeto é um script Python que extrai, transforma e carrega (ETL) dados de preços do Bitcoin a partir da API da Coinbase e os armazena em um banco de dados PostgreSQL. O processo é executado em intervalos de 15 segundos e inclui logs via Logfire para monitoramento.

## Requisitos

Antes de executar o script, certifique-se de ter os seguintes requisitos instalados:

- Python 3.8+
- PostgreSQL
- Bibliotecas Python necessárias (listadas abaixo):
    altair                                   5.5.0      
    attrs                                    24.3.0     
    blinker                                  1.9.0      
    cachetools                               5.5.0      
    certifi                                  2024.12.14 
    charset-normalizer                       3.4.0      
    click                                    8.1.7      
    colorama                                 0.4.6      
    Deprecated                               1.2.15     
    executing                                2.1.0
    gitdb                                    4.0.11
    GitPython                                3.1.43
    googleapis-common-protos                 1.66.0
    greenlet                                 3.1.1
    idna                                     3.10
    importlib_metadata                       8.5.0
    Jinja2                                   3.1.4
    jsonschema                               4.23.0
    jsonschema-specifications                2024.10.1
    logfire                                  2.9.0
    markdown-it-py                           3.0.0
    MarkupSafe                               3.0.2
    mdurl                                    0.1.2
    narwhals                                 1.19.0
    numpy                                    2.2.0
    opentelemetry-api                        1.29.0
    opentelemetry-exporter-otlp-proto-common 1.29.0
    opentelemetry-exporter-otlp-proto-http   1.29.0
    opentelemetry-instrumentation            0.50b0
    opentelemetry-proto                      1.29.0
    opentelemetry-sdk                        1.29.0
    opentelemetry-semantic-conventions       0.50b0
    packaging                                24.2
    pandas                                   2.2.3
    pillow                                   11.0.0
    pip                                      24.2
    protobuf                                 5.29.2
    psycopg2-binary                          2.9.10
    pyarrow                                  18.1.0
    pydeck                                   0.9.1
    Pygments                                 2.18.0
    python-dateutil                          2.9.0.post0
    python-dotenv                            1.0.1
    pytz                                     2024.2
    referencing                              0.35.1
    requests                                 2.32.3
    rich                                     13.9.4
    rpds-py                                  0.22.3
    six                                      1.17.0
    smmap                                    5.0.1
    SQLAlchemy                               2.0.36
    streamlit                                1.41.1
    tenacity                                 9.0.0
    tinydb                                   4.8.2
    toml                                     0.10.2
    tornado                                  6.4.2
    typing_extensions                        4.12.2
    tzdata                                   2024.2
    urllib3                                  2.2.3
    watchdog                                 6.0.0
    wrapt                                    1.17.0
    zipp                                     3.21.0


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









