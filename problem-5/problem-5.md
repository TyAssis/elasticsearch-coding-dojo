Objetivo da Semana:

Dominar a implementação e utilização de consultas baseadas em geolocalização no Elasticsearch, capacitando os participantes a realizar buscas geográficas complexas e eficientes.

Problema Proposto:

A empresa deseja otimizar seu processo de recrutamento ao permitir que os recrutadores busquem candidatos com base na localização geográfica. Isso pode incluir encontrar candidatos próximos a um escritório específico da empresa, identificar candidatos dentro de uma cidade ou região específica, ou analisar a distribuição geográfica dos candidatos para planejar eventos de recrutamento.

Buscas:

Encontre candidatos que estejam a no máximo 50km de São Paulo.

Identifique candidatos localizados dentro do território da cidade Rio de Janeiro.

Liste candidatos que possuem habilidades em Python ou Java e estão localizados em um polígono que inclui São Paulo, Rio de Janeiro, e Belo Horizonte.

Qual a distribuição de candidatos por distância de Brasília?

Resultado Esperado:

Capacidade de realizar consultas geolocalizadas eficientes no Elasticsearch, aproveitando os recursos de geolocalização para melhorar o processo de recrutamento.

Desenvolver a compreensão de como os dados geoespaciais são indexados e consultados no Elasticsearch, e como essas consultas podem ser aplicadas para resolver problemas reais de negócios.

Conteúdo Teórico:

Introdução à Geolocalização no Elasticsearch:

Revisão dos tipos de dados geoespaciais.

Entendimento de como indexar dados geoespaciais.

Consultas Geoespaciais:

Aprender a realizar consultas por proximidade para encontrar candidatos dentro de uma distância específica de um local.

Explorar consultas em áreas delimitadas para identificar candidatos dentro de regiões geográficas definidas.

Entender como utilizar agregações baseadas em localização para análises geográficas.

Assets



// João Silva - Localizado em São Paulo, perto do ponto central
PUT /candidatos/_doc/1
{
  "nome": "João Silva",
  "habilidades": ["Python", "Django", "JavaScript"],
  "localizacao": {
    "lat": -23.550520,
    "lon": -46.633308
  }
}
// Maria Fernanda - Localizada no Rio de Janeiro 
PUT /candidatos/_doc/2
{
  "nome": "Maria Fernanda",
  "habilidades": ["Java", "Spring Boot", "Angular"],
  "localizacao": {
    "lat": -22.9068467,
    "lon": -43.1728965
  }
}
// Carlos Eduardo - Localizado em Belo Horizonte
PUT /candidatos/_doc/3
{
  "nome": "Carlos Eduardo",
  "habilidades": ["C#", ".NET", "React"],
  "localizacao": {
    "lat": -19.919068,
    "lon": -43.938575
}
//Ana Beatriz - Localizada em Brasília
PUT /candidatos/_doc/4
{
  "nome": "Ana Beatriz",
  "habilidades": ["Python", "Flask", "SQL"],
  "localizacao": {
    "lat": -15.793404,
    "lon": -47.882317
  }