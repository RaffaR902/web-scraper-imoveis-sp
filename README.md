# Web Scraper de Imóveis - Nova São Paulo

Este projeto realiza a extração automatizada (web scraping) de anúncios de imóveis do site [Nova São Paulo Imóveis](https://www.novasaopaulo.com.br/).

---

## Funcionalidades

- Coleta dados de imóveis a partir de páginas de listagem no site Nova São Paulo (url, tipo, bairro, cidade, preço, área, quartos, suítes, vagas, etc).
- Suporte para coletar imóveis com diferentes tipos, como apartamentos, casas, sobrados, terrenos, etc.
- Detecção de tipo de imóvel com base em título.
- Suporte para detecção de imóveis duplicados (por URL).
- Armazenamento dos dados coletados em um arquivo CSV (`imoveis.csv`).
- Respeita o `/robots.txt` do site.

---

## Tecnologias utilizadas

- Python 3.10.6
- Selenium
- Pandas
- Webdriver Manager
- Chrome WebDriver

---

## Estrutura dos Dados
Cada linha no CSV contém os seguintes campos:

`url`: URL do imóvel
`tipo`: Tipo de imóvel (ex: Apartamento, Cobertura)
`bairro`: Bairro onde o imóvel está localizado
`cidade`: Cidade onde o imóvel está localizado
`objetivo`: Venda ou Locação
`preco`: Valor numérico do imóvel
`area_util`: Área útil (em m²)
`quartos`: Quantidade de dormitórios
`suites`: Quantidade de suítes
`vagas`: Quantidade de vagas na garagem

---

## Configurações

É possivel alterar os seguintes parâmetros diretamente no código `scraper.py`:

```python
URL_BASE = '' # URL base do site que será extraido os dados de imóveis

DELAY = 10  # Tempo (em segundos) que o scraper espera após carregar cada nova página antes de extrair os dados — simula o comportamento humano e respeita o crawl-delay do site.

LIMITE_NOVOS_IMOVEIS = 10000  # Limite de imóveis que serão coletados

ARQUIVO_CSV = 'imoveis.csv'  # Nome do arquivo de saída
```

---

## URLs definidas

Você pode escolher qual tipo de imóvel deseja coletar:

- **Somente imóveis para venda:**  
    `https://www.novasaopaulo.com.br/imoveis?home=home&opcao=comprar&page={}`

- **Somente imóveis para locação (aluguel):**  
    `https://www.novasaopaulo.com.br/imoveis?home=home&opcao=alugar&page={}`

Basta alterar a variável `URL_BASE` no script `scraper.py` para a opção desejada.

---

## Avisos

Este projeto é apenas para fins educacionais.

Respeite os termos de uso do site alvo.

O scraper simula um navegador real, o que pode ser bloqueado em certos casos.

---

## Instalação e Execução

1. Clone o repositório:

```bash
git clone https://github.com/RaffaR902/webscraper-imoveis-sp
cd webscraper-imoveis
```

2. Crie umm ambiente virtual (opcional).

3. Instale as dependências:

```bash
pip install -r requirements.txt
```

4. Edite a URL base no `scraper.py` conforme o tipo de imóvel desejado.

5. Execute o script principal:

```bash
python scraper.py
```
