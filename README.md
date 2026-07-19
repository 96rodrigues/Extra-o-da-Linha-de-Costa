# Extra-o-da-Linha-de-Costa
Extração da linha de costa apartir de imagens de satélite Sentinel 2.

Extração Automática da Linha de Costa com MNDWI

Este script foi desenvolvido em Python, no ambiente Google Colab, para realizar a extração automática de linhas de costa a partir de imagens multiespectrais em formato GeoTIFF. O método utiliza o índice MNDWI (Modified Normalized Difference Water Index), amplamente empregado para a distinção entre superfícies de água e áreas terrestres, permitindo o monitoramento temporal da dinâmica costeira.

O processamento é realizado utilizando bibliotecas de geoprocessamento e análise espacial, como Rasterio, GeoPandas, Shapely e Scikit-Image. Inicialmente, as imagens são importadas diretamente do Google Drive, e as bandas espectrais correspondentes ao verde (Green) e ao infravermelho de ondas curtas (SWIR) são utilizadas para o cálculo do MNDWI:

MNDWI=Green+SWIR/Green−SWIR
	​


Após o cálculo do índice, é aplicado um limiar (threshold) para separar água e terra. Em seguida, algoritmos de detecção de contornos identificam automaticamente a interface entre esses ambientes, convertendo-a em geometrias vetoriais do tipo LineString, representando as linhas de costa.

O script também possui funcionalidades adicionais, como:

Processamento em lote de múltiplas imagens .tif;
Extração automática das datas a partir do nome dos arquivos;
Seleção da linha de costa principal, eliminando feições secundárias;
Recorte das linhas de costa utilizando um shapefile da área de estudo;
Reprojeção automática de sistemas de coordenadas (CRS) quando necessário;
Exportação dos resultados em formato GeoJSON;
Geração de mapas temáticos, permitindo visualizar a evolução temporal da linha de costa com cores distintas para cada período analisado.

A metodologia pode ser aplicada em estudos de Geografia Física, Geomorfologia Costeira, monitoramento de erosão e progradação, análise de dinâmica sedimentar, além de investigações relacionadas às interações entre ondas, ventos e variações da linha de costa.

Bibliotecas utilizadas
Rasterio – leitura e processamento de imagens raster;
GeoPandas – manipulação de dados vetoriais;
Shapely – criação e edição de geometrias;
Scikit-Image – detecção de contornos;
Matplotlib – visualização e geração de mapas;
NumPy – cálculos matriciais e processamento numérico.
