[PYTHON__BADGE]:https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54
[SELENIUM__BADGE]:https://img.shields.io/badge/Selenium-43B02A?logo=Selenium&logoColor=white
[PANDAS__BADGE]:https://img.shields.io/badge/-Pandas-333333?style=flat&logo=pandas

<h1 align="center" style="font-weight: bold;">Web Scraper de Imóveis - Nova São Paulo</h1>

![python][PYTHON__BADGE]
![selenium][SELENIUM__BADGE]
![pandas][PANDAS__BADGE]

<p align="center">
    <a href="#funcionalidades">Funcionalidades</a> | 
    <a href="#tecnologiasUtilizadas">Tecnologias Utilizadas</a> |
    <a href="#estruturaCsv">Estrutura do CSV</a> |
    <a href="#configuracoes">Configurações</a> |
    <a href="definicaoUrl">Definição da URl</a> |
    <a href="avisos">Avisos</a> |
    <a href="instalacao">Instalação</a> |
    <a href="execucao">Execução</a>
</p>

<p align="center">Este projeto realiza a extração automatizada (web scraping) de anúncios de imóveis do site Nova São Paulo Imóveis(https://www.novasaopaulo.com.br/).</p>

---

<h2 id="funcionalidades">Funcionalidades</h2>

- Coleta dados de imóveis a partir de páginas de listagem no site Nova São Paulo (url, tipo, bairro, cidade, objetivo, preço, área útil, quartos, suítes e vagas de garagem).
- Suporte para coletar imóveis com diferentes tipos, como apartamentos, casas, sobrados, terrenos, etc.
- Detecção de tipo de imóvel com base em título.
- Suporte para detecção de imóveis duplicados (por URL).
- Armazenamento dos dados coletados em um arquivo CSV (`imoveis.csv`).
- Respeita o `/robots.txt` do site.

---

<h2 id="tecnologiasUtilizadas">Tecnologias Utilizadas</h2>

- Python 3.10.6
- Selenium
- Pandas
- Webdriver Manager
- Chrome WebDriver

---

<h2 id="estruturaCsv">Estrutura do CSV</h2>

Cada linha no CSV contém os seguintes campos:

- `url`: URL do imóvel
- `tipo`: Tipo de imóvel (ex: Apartamento, Cobertura)
- `bairro`: Bairro onde o imóvel está localizado
- `cidade`: Cidade onde o imóvel está localizado
- `objetivo`: Venda ou Locação
- `preco`: Valor numérico do imóvel
- `area_util`: Área útil (em m²)
- `quartos`: Quantidade de dormitórios
- `suites`: Quantidade de suítes
- `vagas`: Quantidade de vagas na garagem

---

<h2 id="configuracoes">Configurações</h2>

É possivel alterar os seguintes parâmetros diretamente no código `scraper.py`:

```python
URL_BASE = '' # URL base do site que será extraido os dados de imóveis

# Tempo (em segundos) que o scraper espera após carregar cada página antes de extrair os dados
# Simula o comportamento humano e respeita o crawl-delay do site.
DELAY = 10  

LIMITE_NOVOS_IMOVEIS = 10000  # Limite de imóveis que serão coletados

ARQUIVO_CSV = 'imoveis.csv'  # Nome do arquivo de saída
```

---

<h2 id="definicaoUrl">Definição da URL</h2>

Você pode escolher qual tipo de imóvel deseja coletar:

- **Somente imóveis para venda:**  
    `https://www.novasaopaulo.com.br/imoveis?home=home&opcao=comprar&page={}`

- **Somente imóveis para locação:**  
    `https://www.novasaopaulo.com.br/imoveis?home=home&opcao=alugar&page={}`

Basta alterar a variável `URL_BASE` no script `scraper.py` para a opção desejada.

---

<h2 id="avisos">Avisos</h2>

Este projeto é apenas para fins educacionais.

Respeite os termos de uso do site alvo.

O scraper simula um navegador real, o que pode ser bloqueado em certos casos.

---

<h2 id="instalacao">Instalação</h2>

1. Clone o repositório:

```bash
git clone https://github.com/RaffaR902/web-scraper-imoveis-sp
cd web-scraper-imoveis-sp
```

2. Crie um ambiente virtual (opcional).

3. Instale as dependências:

```bash
pip install -r requirements.txt
```

---

<h2 id="execucao">Execução</h2>

1. Edite a URL base no `scraper.py` conforme a URL desejada.

2. Execute o script principal:

```bash
python scraper.py
```
