# Curso Full Cycle 3.0 - Módulo Observabilidade

<div>
    <img alt="Criado por Alcir Junior [Caju]" src="https://img.shields.io/badge/criado%20por-Alcir Junior [Caju]-%23f08700">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-%23f08700">
</div>

---

## Descrição

O Curso Full Cycle é uma formação completa para fazer com que pessoas desenvolvedoras sejam capazes de trabalhar em projetos expressivos sendo capazes de desenvolver aplicações de grande porte utilizando de boas práticas de desenvolvimento.

---

## Repositório Pai
https://github.com/alcir-junior-caju/study-full-cycle-3-0

---

## Visualizar o projeto na IDE:

Para quem quiser visualizar o projeto na IDE clique no teclado a tecla `ponto`, esse recurso do GitHub é bem bacana

---

### Observabilidade

Na teroria de controle, a observabilidade é definida como uma medida de quão bem os estados internos de um sistema podem ser inferidos a partir do conhecimento das saídas externas desse sistema. Simplificando, observabilidade é quão bem você pode entender seu sistema complexo.

### Observabilidade x Monitoramento

- Monitoramento nos mostra que há algo errado;
- Monitoramento se baseia em saber com antecedência quais sinais você deseja monitora;
- Observabilidade nos permite perguntar o porque está errado;

### Os 3 pilares da Observabilidade

- Métricas;
- Logs;
- Tracing;

### Elastic Stack

- (E)lasticsearch - Search Engine e Analytics;
- (L)ogstash - Processador de dados através de pipelines que consegue receber, transformar e enviar dados simultanneamente;
- (K)ibana - Permite usuários a visualizarem os dados do Elasticsearch em diversas perspectivas;

### Elasticsearch

- Search Engine e Analytics;
- Apache Lucene;
- 2010 - Elasticsearch N.V (Elastic);
- Rápido;
- Escalável;
- API Rest;
- Análise e visualização geoespacial;
- Application, website e enterprise search;
- Logging e analytics;
- Trabalha de forma distribuída através de shards que possuem redundância de dados;
- Pode escalar milhares de servidores e manipular petabyte de dados;

### Logstash

- Engine coletora de dados em tempo real;
- Iniciou como manipulador de logs;
- Trabalha com pipelines;
- Recebe dados de múltiplas fontes;
- Normaliza e transforma dados;
- Envia dados para múltiplas fontes;
- Plugins;

### Kibana

- Ferramenta de visualização e exploração de dados;
- Usada com: Logs, Análise de séries, Monitoramento de aplicações, e inteligência operacional;
- Integrado com Elasticsearch;
- Agregadores e filtragem de dados;
- Dashboards;
- Gráficos interativos;
- Mapas;

### Qual a diferença entre ELK Stack e Elastic Stack?

É a entrada do Beats, que é a forma mais moderna do ELK Stack que se tornou o Elastic Stack:

- Beats;
    - Beats foi anunciado em 2015;
    - “Lightweight data shipper”;
    - Agente coletor de dados;
    - Integrado facilmente com Elasticsearch ou lostash;
    - Logs, Métricas, Network data, Audit Data, Uptime Monitoring;
    - Você pode construir seu próprio Beat;

### Elastic

- Empresa por trás das soluções;
- Cloud Solution;
- Oferecem plugins e recursos licenciados;
- Produtos:
    - APM;
    - Maps;
    - Site Search;
    - Enterprise search;
    - App Search;
    - Infrastructure;

### Prometheus

- É um Toolkit de monitoramento e alertas de sistema open-source;
- Criado pela SoundCloud;
- Faz parte da Cloud Native Computing Foundation;
- Captura Dados Dimensionais;
- Consultas poderosas;
- Fácil visualização dos dados em conjunto com Grafana;
- Storage eficiente;
- Simples;
- Alerta inteligente;
- Diversidade de clients e integrações;

### Informações relevantes ao negócio

- Quantidade de compras;
- Tempo de resposta no processo de compra;
- Quantidade de usuários logados;
- Utilização de feature X;
- Busca específica no site;

### E quando  não foi você que desenvolveu

- MySQL;
- Nginx / Apache;
- Servidor Linux;
- Etc…

### Exporters

- Exportes é um interface para ficar entre o Prometheus e a aplicação;

### Armazenamento

- TSDB (Time series Database);
- Armazenamento de dados que mudam conforme o tempo;
- Labels para propriedades específicas de uma determinada métrica (error_type=500);
- Otimização específica para esse caso de uso, garantido mais performance do que bancos de dados convecionais;
- Quanto mais novos os dados, mais precisão;

### Métricas: Counter

- Valor incremental;
- Prometheus consegue absorver falhas no caso esse número tenha uma eventual reset;
- Exemplos:
    - Quantidade de visitas em um site;
    - Quantidade de vendas;
    - Quantidade de errors;

### Métricas: Gauge

- Valor pode possuir variações com o tempo;
- Aumenta / Diminuir / Estabilizar;
- Exemplos:
    - Quantidade de usuários online;
    - Quantidade de servidores ativos;

### Métricas: Histogram

- Distribuição de frequência;
- Medição é baseado em amostras;
- Consegue agregar valores;

### Métricas: Summary

- Muito similar ao histogram;
- Com o summary os valores são calculados no servidor de aplicação e não no prometheus;
- Bom para aproximação de vendas;
- Exemplo:
    - Tempo de duração de uma resquest;
- De forma geral, é muito mais comum utilizar o histogram;

### PromQL

- Prometheus Query Language (SQL do Prometheus);
- Exemplo:
    - http_requests_total;
    - rate (http_requests_total[5m]);
    - http_requests_total{status!~”4..”}
