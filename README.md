# GEADAS
![images](https://github.com/user-attachments/assets/7dd46eb3-fb0a-42b7-95af-abce3ba0930a)

### Projetos Aprendizado
Cidades com as Menores Temperaturas Registradas
Este projeto utiliza a biblioteca Plotly para criar um gráfico de dispersão geográfica interativo, exibindo as temperaturas mínimas registradas em bairros da cidade de São Paulo.

### Descrição do Projeto
O objetivo deste projeto é visualizar as temperaturas mínimas registradas em diversos bairros da cidade de São Paulo, utilizando um gráfico de dispersão geográfica. As temperaturas são representadas por círculos, cujo tamanho é proporcional à intensidade da temperatura mínima registrada.

## Bibliotecas Utilizadas
Pandas: Para manipulação de dados.
Plotly Express: Para a criação de gráficos interativos.
Estrutura do Código
Definição dos Dados:

## Lista de bairros de São Paulo com suas respectivas temperaturas mínimas registradas.
Coordenadas geográficas (latitude e longitude) para cada bairro.
Criação do DataFrame:

Utilizamos a biblioteca Pandas para organizar os dados em um DataFrame.
Criação do Gráfico de Dispersão Geográfica:

O gráfico é criado utilizando plotly.express.scatter_geo.
As temperaturas mínimas são representadas por núcleos, e o tamanho dos marcadores é escalado de acordo com a magnitude da temperatura.
Ajuste do Layout:

O layout dos gráficos é ajustado para centralizar o mapa em São Paulo.
Código
python
Copiar código
import plotly.express as px
import pandas as pd

## Lista de bairros de São Paulo com suas menores temperaturas registradas e coordenadas
bairros_sp = [
    {"bairro": "Parelheiros-Marsilac", "temperatura_minima": -3.0, "latitude": -23.7697, "longitude": -47.0003},
    {"bairro": "Santo Amaro", "temperatura_minima": -2.5, "latitude": -23.6446, "longitude": -46.7275},
    {"bairro": "Mooca", "temperatura_minima": -1.8, "latitude": -23.5567, "longitude": -46.6213},
    {"bairro": "Itaim Bibi", "temperatura_minima": -1.5, "latitude": -23.5943, "longitude": -46.6905},
    {"bairro": "Pinheiros", "temperatura_minima": -1.2, "latitude": -23.5563, "longitude": -46.6944},


## Mostrar o gráfico
fig.show()
Você pode acessar o projeto no Google Colab aqui.

https://github.com/EDVADMBD/GEADAS/blob/main/Geadas_pynb.ipynb





