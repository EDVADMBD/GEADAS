# GEADAS
![images](https://github.com/user-attachments/assets/7dd46eb3-fb0a-42b7-95af-abce3ba0930a)

# Projetos Aprendizado

## Cidades com as Menores Temperaturas Registradas

Este projeto utiliza a biblioteca Plotly para criar um gráfico de dispersão geográfica interativa, exibindo as temperaturas mínimas registradas em bairros da cidade de São Paulo.

### Descrição do Projeto

O projeto tem como objetivo visualizar as temperaturas registradas em diversos bairros da cidade de São Paulo, utilizando um gráfico de dispersão geográfica. As temperaturas são representadas por círculos, e o tamanho do círculo é proporcional à intensidade da temperatura mínima registrada.

### Bibliotecas Utilizadas

- **Pandas**: Para manipulação de dados.
- **Plotly Express**: Para a criação de gráficos interativos.

### Estrutura do Código

1. **Definição dos Dados**:
   - Lista de bairros de São Paulo com suas respectivas temperaturas mínimas registradas.
   - Coordenadas geográficas (latitude e longitude) para cada bairro.

2. **Criação do DataFrame**:
   - Utilizamos a biblioteca Pandas para organizar os dados em um DataFrame.

3. **Criação do Gráfico de Dispersão Geográfica**:
   - O gráfico é criado utilizando `plotly.express.scatter_geo`.
   - As temperaturas mínimas são representadas por núcleos, e o tamanho dos marcadores é escalado de acordo com a magnitude da temperatura.

4. **Ajuste do Layout**:
   - O layout dos gráficos é ajustado para centralizar o mapa em São Paulo.

### Código

```python
import plotly.express as px
import pandas as pd

# Lista de bairros de São Paulo com suas menores temperaturas registradas e coordenadas
bairros_sp = [
    {"bairro": "Parelheiros-Marsilac", "temperatura_minima": -3.0, "latitude": -23.7697, "longitude": -47.0003},
    {"bairro": "Santo Amaro", "temperatura_minima": -2.5, "latitude": -23.6446, "longitude": -46.7275},
    {"bairro": "Mooca", "temperatura_minima": -1.8, "latitude": -23.5567, "longitude": -46.6213},
    {"bairro": "Itaim Bibi", "temperatura_minima": -1.5, "latitude": -23.5943, "longitude": -46.6905},
    {"bairro": "Pinheiros", "temperatura_minima": -1.2, "latitude": -23.5563, "longitude": -46.6944},
    {"bairro": "Vila Mariana", "temperatura_minima": -1.0, "latitude": -23.5826, "longitude": -46.6341},
    {"bairro": "Centro", "temperatura_minima": -0.8, "latitude": -23.5505, "longitude": -46.6333},
]

# Criar um DataFrame a partir dos dados
df_bairros = pd.DataFrame(bairros_sp)

# Adicionar uma coluna para o tamanho dos marcadores
df_bairros['size'] = abs(df_bairros['temperatura_minima']) * 5  # Escalar o tamanho dos marcadores

# Criar o gráfico de dispersão interativo
fig = px.scatter_geo(df_bairros,
                     lat='latitude',
                     lon='longitude',
                     text='bairro',
                     size='size',  # Usar a coluna 'size' para o tamanho dos marcadores
                     color='temperatura_minima',
                     hover_name='bairro',
                     hover_data={'temperatura_minima': True},
                     color_continuous_scale='Viridis',
                     title='Menores Temperaturas Registradas em Bairros de São Paulo')

# Ajustar o layout
fig.update_layout(
    geo=dict(
        scope='south america',
        projection_type='mercator',
        center=dict(lat=-23.5505, lon=-46.6333),  # Centralizar o mapa em São Paulo
    ),
    title='Menores Temperaturas Registradas em Bairros de São Paulo',
    title_x=0.5
)

# Mostrar o gráfico
fig.show()

Você pode acessar o projeto no Google Colab aqui
https://colab.research.google.com/drive/1gnOMEdbQFjk_dlestqDDjI61jSN9eQux#scrollTo=hd1ov_iA0MIR
