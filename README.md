# MMC-AI-agent
an AI agent project for a client with really interesting needs.
# Desenvolvimento de Agente IA para Acesso Automatizado a Contas de Energia ENEL

## Contexto e Objetivo Principal

Desenvolver uma solução robusta de agente IA capaz de:
- Acessar automaticamente o portal web da ENEL Ceará (https://www.enel.com.br/pt-ceara/login.html)
- Contornar sistemas de autenticação e CAPTCHA
- Extrair informações detalhadas de contas de energia elétrica
- Processar e estruturar dados para análise e automação

## Especificações Técnicas da Conta Analisada

### Dados Identificados na Fatura:
- **Tipo de Cliente**: Residencial/Comercial (Baixa Tensão - Conv. Comercial)
- **Número da Instalação**: 27300594
- **Código do Cliente**: 51420776
- **Consumo Mensal**: 28 kWh (período 06/03/2025 - 03/04/2025)
- **Valor Total**: R$ 303,31
- **Dados de Medição**: Leitura anterior, atual, próxima leitura
- **Tributos e Taxas**: ICMS, PIS/COFINS, Contribuição Municipal
- **Informações de Pagamento**: Código de barras, PIX, dados bancários

## Requisitos Funcionais do Agente IA

### 1. Módulo de Autenticação Avançada
- **Bypass de CAPTCHA**: Implementar soluções para diferentes tipos de CAPTCHA
- **Gerenciamento de Sessão**: Manter sessões ativas e renovar tokens
- **Multi-autenticação**: Suporte a login tradicional, Google, Facebook, Apple
- **Detecção de Bloqueios**: Identificar e contornar bloqueios temporários

### 2. Módulo de Extração de Dados
- **Parsing Inteligente**: Extrair informações estruturadas das páginas
- **OCR Avançado**: Processar PDFs e imagens de faturas
- **Validação de Dados**: Verificar consistência das informações extraídas
- **Histórico Temporal**: Coletar dados de múltiplos períodos

### 3. Módulo de Processamento e Análise
- **Estruturação de Dados**: Organizar informações em formatos padronizados
- **Análise de Tendências**: Identificar padrões de consumo
- **Alertas Inteligentes**: Notificar sobre anomalias ou vencimentos
- **Integração de APIs**: Conectar com sistemas externos

## Arquitetura Técnica Proposta

### Stack Tecnológico Principal
```
Frontend: React.js + TypeScript
Backend: Node.js + Express + Python (para ML)
Database: PostgreSQL + Redis (cache)
Queue System: Bull.js + Redis
Containerização: Docker + Docker Compose
```

### Componentes Especializados

#### 1. Web Scraping Engine
```javascript
// Tecnologias sugeridas
- Puppeteer/Playwright para automação de browser
- Selenium WebDriver para casos complexos
- Cheerio para parsing HTML
- Axios para requisições HTTP diretas
```

#### 2. CAPTCHA Solving Solutions
```python
# Alternativas Open Source
- pytesseract + OpenCV para OCR básico
- YOLO/TensorFlow para detecção de objetos em CAPTCHA
- Modelos pre-treinados do Hugging Face

# Serviços Comerciais (Backup)
- 2captcha API
- Anti-Captcha
- CapMonster
```

#### 3. Data Processing Pipeline
```python
# Bibliotecas Python
- pandas para manipulação de dados
- BeautifulSoup para parsing HTML
- PyPDF2/pdfplumber para extração de PDF
- regex para parsing de padrões específicos
```

## Projetos Open Source Recomendados

### 1. Frameworks de Web Scraping
- **Scrapy** (Python): Framework robusto para scraping em larga escala
- **Crawlee** (Node.js): Biblioteca moderna para web crawling
- **Selenium Grid**: Para execução distribuída de testes automatizados

### 2. Soluções de CAPTCHA
- **CapSolver Open Source**: Modelos ML para resolução de CAPTCHA
- **DeepCaptcha**: Rede neural para breaking CAPTCHA
- **Undetected Chrome Driver**: Versão modificada do ChromeDriver

### 3. Processamento de Documentos
- **Tesseract OCR**: Engine OCR mais utilizado mundialmente
- **Apache Tika**: Extração texto de diversos formatos
- **Camelot/Tabula**: Extração de tabelas de PDFs

### 4. Machine Learning & IA
- **Transformers (Hugging Face)**: Modelos de linguagem para NLP
- **OpenCV**: Processamento de imagem
- **Scikit-learn**: Algoritmos de ML para análise de padrões

## Metodologia de Desenvolvimento

### Fase 1: Prototipagem e Pesquisa (2-3 semanas)
- Análise detalhada do sistema de autenticação ENEL
- Desenvolvimento de POCs para bypass de CAPTCHA
- Testes de diferentes estratégias de scraping
- Definição da arquitetura final

### Fase 2: Desenvolvimento Core (4-6 semanas)
- Implementação do engine de scraping
- Desenvolvimento dos módulos de autenticação
- Criação do sistema de processamento de dados
- Implementação de APIs REST

### Fase 3: Otimização e Segurança (2-3 semanas)
- Implementação de proxy rotation
- Sistema de retry e error handling
- Criptografia de credenciais
- Logging e monitoramento

### Fase 4: Interface e Integração (2-3 semanas)
- Dashboard React para visualização
- APIs para integração externa
- Documentação completa
- Testes de carga e performance

## Considerações de Segurança e Compliance

### Medidas de Proteção
- **Proxy Rotation**: Múltiplos IPs para evitar detecção
- **User-Agent Rotation**: Simular diferentes browsers
- **Request Throttling**: Controlar velocidade de requisições
- **Headless Detection Bypass**: Evitar detecção de automação

### Aspectos Legais
- Implementar rate limiting respeitoso
- Adicionar delays humanizados entre ações
- Respeitar robots.txt quando aplicável
- Documentar uso ético da ferramenta

## Produtos e Serviços Complementares

### Soluções Comerciais para CAPTCHA
1. **2captcha.com**: API robusta, suporte a múltiplos tipos
2. **Anti-Captcha.com**: Especializado em reCAPTCHA v2/v3
3. **CapMonster Cloud**: Baseado em ML, alta precisão

### Infraestrutura Cloud
1. **Proxy Services**: ProxyMesh, Bright Data, Oxylabs
2. **Browser Automation**: BrowserStack, Sauce Labs
3. **ML Platforms**: AWS SageMaker, Google AI Platform

### Monitoramento e Analytics
1. **Elasticsearch + Kibana**: Para logging e análise
2. **Grafana + Prometheus**: Métricas de performance
3. **Sentry**: Error tracking e alertas

## Estrutura de Dados de Saída

### JSON Schema para Fatura Processada
```json
{
  "cliente": {
    "numero_instalacao": "27300594",
    "codigo_cliente": "51420776",
    "nome": "MARCOS CANAARY",
    "endereco": "RUA ARAGAEM SILVA 00178...",
    "tipo_fornecimento": "MONOFASICO"
  },
  "periodo": {
    "data_leitura_anterior": "06/03/2025",
    "data_leitura_atual": "03/04/2025",
    "dias_consumo": 28,
    "proxima_leitura": "05/05/2025"
  },
  "consumo": {
    "kwh_consumido": 28,
    "valor_total": 303.31,
    "detalhes_tarifarios": [...],
    "impostos": [...]
  },
  "pagamento": {
    "vencimento": "15/04/2025",
    "codigo_barras": "...",
    "chave_pix": "...",
    "dados_bancarios": {...}
  }
}
```

## Métricas de Sucesso

### KPIs Técnicos
- Taxa de sucesso de login: >95%
- Tempo médio de extração: <30 segundos
- Precisão de dados extraídos: >99%
- Disponibilidade do sistema: >99.5%

### KPIs de Negócio
- Redução de tempo manual: >80%
- Economia de custos operacionais: >60%
- Satisfação do usuário: >4.5/5
- ROI em 6 meses: >200%

## Cronograma de Entregas

### Sprint 1-2: Fundação (2 semanas)
- Setup do ambiente de desenvolvimento
- Análise reversa do sistema ENEL
- POC de bypass de autenticação

### Sprint 3-4: Core Development (2 semanas)
- Engine de scraping funcional
- Módulo de processamento básico
- Testes unitários fundamentais

### Sprint 5-6: Otimização (2 semanas)
- Sistema de CAPTCHA solving
- Error handling robusto
- Performance optimization

### Sprint 7-8: Interface e Integração (2 semanas)
- Dashboard React completo
- APIs REST documentadas
- Testes de integração

### Sprint 9-10: Deploy e Documentação (2 semanas)
- Ambiente de produção
- Documentação técnica completa
- Treinamento de usuários

## Recursos Necessários

### Equipe Mínima
- 1 Desenvolvedor Full Stack (React/Node.js)
- 1 Especialista em Web Scraping/Python
- 1 DevOps Engineer
- 1 Product Owner/Tester

### Infraestrutura
- Servidores cloud (AWS/GCP/Azure)
- Proxies rotativos
- Serviços de CAPTCHA solving
- Monitoramento e logging

### Orçamento Estimado
- Desenvolvimento: R$ 80.000 - 120.000
- Infraestrutura (mensal): R$ 2.000 - 5.000
- Serviços terceiros: R$ 500 - 1.500/mês
- Manutenção (anual): 20% do valor de desenvolvimento

Este prompt fornece uma base sólida para desenvolver uma solução completa e profissional para automação de acesso a contas ENEL, considerando todos os aspectos técnicos, legais e operacionais necessários.