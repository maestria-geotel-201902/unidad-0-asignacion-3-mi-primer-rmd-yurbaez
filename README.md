
<!-- Este .md fue generado a partir del .Rmd homónimo. Edítese el .Rmd -->
Mi primer RMarkdown
===================

Si estás leyendo este documento, seguramente ya aceptaste la invitación que recibiste por correo. Si por el contrario no has aceptado la invitación o no la has recibido aún, acéptala o pide al profesor que te la reenvíe, para que leas desde tu propio repo.

Por otra parte, clona tu repo localmente usando RStudio. Si no te acuerdas de cómo hacerlo, usa como referencia la guía [¿Cómo realizar una asignación?](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/como-hacer-una-asignacion.md)

Posteriormente, estudia la [Guía mínima de RMarkdown](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/guia-minima-de-rmarkdown.md). Puedes echarle un vistazo general a la guía, y luego utilizarla como referencia mientras vas realizando esta asignación.

Tu número aleatorio asignado
----------------------------

En la tabla a continuación verás las direcciones de correo electrónico de cada estudiante de la maestría, abreviadas usando sus 5 primeros caracteres (se excluyen los caracteres '.' y '\_'). Localiza tu abreviatura y toma nota de tu número aleatorio asignado, porque lo usarás para cumplir los mandatos que verás en este mismo documento.

``` r
 # abreviatura aleatorios
 #       acade        144
 #       agrie         79
 #       aleir        118
 #       arqco         77
 #       cindy         94
 #       franc         17
 #       geora        151
 #       hoyod        176
 #       ingan         26
 #       ingdi         15
 #       itac9        101
 #       ivanv        143
 #       lbine        116
 #       leona          9
 #       magda         92
 #       maryj         87
 #       masue         31
 #       mmvol        160
 #       naui2        127
 #       rober         98
 #       wilne         54
 #       yoenn        115
```

Archivo `README.Rmd`
--------------------

A partir de este punto, necesitarás editar el archivo `README.Rmd` desde RStudio (recalco, el archivo que termina en `.Rmd`), porque tendrás que colocar tus respuestas en dicho archivo.

-   **Abre el archivo `README.Rmd`** (recalco, el archivo que termina en `.Rmd`) y mantenlo abierto hasta finalizar la asignación. Se te solicitará escribir código de R en este archivo, y deberás ejecutarlo en la consola para comprobar que no hay errores. Coloca tu respuesta sustituyendo los puntos suspensivos (`...`) que encontrarás dentro de los bloques de código. Un bloque comienza por algo tal que esto ```` ```{r} ```` y termina con esto ```` ``` ````.

-   Tal como explica la [Guía mínima de RMarkdown](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/guia-minima-de-rmarkdown.md), asegúrate que la **opción `Chunk Output in Console` de la rueda dentada está marcada** con un aspa (cotejo).

Conjunto de datos `worldbank_df`
--------------------------------

`worldbank_df` es un conjunto de datos globales en forma de un `data.frame`, disponible en R mediante el paquete `spData`, que contiene información de los países recopilada por el Banco Mundial. Cada fila corresponde a un país (177), y cada columna es un atributo o variable (7)

-   **Carga el paquete `spData`**. Recuerda que R es sensible a las mayúsculas.

``` r
library(spData) #Borra los ... (ni más ni menos) y escribe el nombre del paquete.
## To access larger datasets in this package, install the spDataLarge
## package with: `install.packages('spDataLarge',
## repos='https://nowosad.github.io/drat/', type='source')`
```

> El símbolo `#` **dentro los bloques de código** precede comentarios. R ignora lo escrito a partir de `#`. Verás que ocasionalmente usaré `#` para colocar pistas sobre lo solicitado.

> Tal como explica la [Guía mínima de RMarkdown](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/guia-minima-de-rmarkdown.md), prueba tu código línea a línea. Configura la ejecución de código en la consola de R, marcando la opción `Chunk Output in Console` de la rueda dentada (barra de herramientas de archivo `.Rmd`). Así, cuando presiones *Run&gt;Run Selected Line(s)* (o `Ctrl+Enter`) para ejecutar la o las líneas seleccionadas. Tu código se ejecutará en la consola de R y en ésta verás los resultados.

-   **Carga el conjunto de datos `worldbank_df` a memoria**.

``` r
data("worldbank_df")
```

-   **Imprime en pantalla `worldbank_df`**. Escribe el nombre del objeto para que se despliegue. No olvides ejecutarlo en la consola para probar que funciona.

``` r
worldbank_df
##                                    name iso_a2   HDI urban_pop
## 1                           Afghanistan     AF    NA   8609463
## 2                                Angola     AO 0.504  11649562
## 3                               Albania     AL    NA   1629715
## 4                  United Arab Emirates     AE    NA   7734365
## 5                             Argentina     AR    NA  39372787
## 6                               Armenia     AM    NA   1825455
## 7                            Antarctica     AQ    NA        NA
## 8   French Southern and Antarctic Lands     TF    NA        NA
## 9                             Australia     AU    NA  20986610
## 10                              Austria     AT    NA   5630521
## 11                           Azerbaijan     AZ    NA   5182792
## 12                              Burundi     BI 0.352   1163373
## 13                              Belgium     BE    NA  10964475
## 14                                Benin     BJ 0.434   4476160
## 15                         Burkina Faso     BF 0.340   5104154
## 16                           Bangladesh     BD    NA  53426273
## 17                             Bulgaria     BG    NA   5318697
## 18                              Bahamas     BS    NA    316440
## 19               Bosnia and Herzegovina     BA    NA   1412707
## 20                              Belarus     BY    NA   7226873
## 21                               Belize     BZ    NA    155181
## 22                              Bolivia     BO    NA   7193570
## 23                               Brazil     BR    NA 174465406
## 24                    Brunei Darussalam     BN    NA    316547
## 25                               Bhutan     BT    NA    294258
## 26                             Botswana     BW 0.634   1240142
## 27             Central African Republic     CF 0.348   1795275
## 28                               Canada     CA    NA  29014612
## 29                          Switzerland     CH    NA   6046826
## 30                                Chile     CL    NA  15738985
## 31                                China     CN    NA 742299307
## 32                        Cote d'Ivoire     CI 0.426  12049541
## 33                             Cameroon     CM 0.492  11969294
## 34     Democratic Republic of the Congo     CD 0.299  30945908
## 35                    Republic of Congo     CG 0.531   3164121
## 36                             Colombia     CO    NA  36398797
## 37                           Costa Rica     CR    NA   3611713
## 38                                 Cuba     CU    NA   8805189
## 39                      Northern Cyprus   <NA>    NA        NA
## 40                               Cyprus     CY    NA    772266
## 41                       Czech Republic     CZ    NA   7685503
## 42                              Germany     DE    NA  60812999
## 43                             Djibouti     DJ 0.442    704756
## 44                              Denmark     DK    NA   4938153
## 45                   Dominican Republic     DO    NA   8122906
## 46                              Algeria     DZ 0.711  27429775
## 47                              Ecuador     EC    NA  10101021
## 48                                Egypt     EG 0.661  39542754
## 49                              Eritrea     ER 0.346        NA
## 50                                Spain     ES    NA  36884904
## 51                              Estonia     EE    NA    888922
## 52                             Ethiopia     ET 0.392  18526950
## 53                              Finland     FI    NA   4592367
## 54                                 Fiji     FJ    NA    472613
## 55                     Falkland Islands     FK    NA        NA
## 56                               France     FR    NA  52593947
## 57                                Gabon     GA 0.679   1630370
## 58                       United Kingdom     GB    NA  53205707
## 59                              Georgia     GE    NA   1992752
## 60                                Ghana     GH 0.553  14395852
## 61                               Guinea     GN 0.352   4330261
## 62                           The Gambia     GM 0.440   1131820
## 63                        Guinea-Bissau     GW 0.364    837849
## 64                    Equatorial Guinea     GQ 0.551    449014
## 65                               Greece     GR    NA   8461009
## 66                            Greenland     GL    NA     48439
## 67                            Guatemala     GT    NA   8139327
## 68                               Guyana     GY    NA    217254
## 69                             Honduras     HN    NA   4769045
## 70                              Croatia     HR    NA   2486069
## 71                                Haiti     HT    NA   6072402
## 72                              Hungary     HU    NA   6982598
## 73                            Indonesia     ID    NA 135227145
## 74                                India     IN    NA 418770499
## 75                              Ireland     IE    NA   2906635
## 76                                 Iran     IR    NA  57126401
## 77                                 Iraq     IQ    NA  24280567
## 78                              Iceland     IS    NA    307880
## 79                               Israel     IL    NA   7564688
## 80                                Italy     IT    NA  41835694
## 81                              Jamaica     JM    NA   1561440
## 82                               Jordan     JO    NA   7351102
## 83                                Japan     JP    NA 118393408
## 84                           Kazakhstan     KZ    NA   9213427
## 85                                Kenya     KE 0.515  11596730
## 86                           Kyrgyzstan     KG    NA   2076563
## 87                             Cambodia     KH    NA   3132650
## 88                    Republic of Korea     KR    NA  41794948
## 89                               Kosovo   <NA>    NA        NA
## 90                               Kuwait     KW    NA   3719132
## 91                              Lao PDR     LA    NA   2469503
## 92                              Lebanon     LB    NA   4912395
## 93                              Liberia     LR 0.381   2164985
## 94                                Libya     LY 0.725   4861477
## 95                            Sri Lanka     LK    NA   3805247
## 96                              Lesotho     LS 0.456    574834
## 97                            Lithuania     LT    NA   1950669
## 98                           Luxembourg     LU    NA    499975
## 99                               Latvia     LV    NA   1344228
## 100                             Morocco     MA 0.589  20487552
## 101                             Moldova     MD    NA   1597711
## 102                          Madagascar     MG 0.483   8130933
## 103                              Mexico     MX    NA  98099040
## 104                           Macedonia     MK    NA   1184775
## 105                                Mali     ML 0.347   6639767
## 106                             Myanmar     MM    NA  17421082
## 107                          Montenegro     ME    NA    396914
## 108                            Mongolia     MN    NA   2082457
## 109                          Mozambique     MZ 0.322   8690002
## 110                          Mauritania     MR 0.464   2408076
## 111                              Malawi     MW 0.415   2748424
## 112                            Malaysia     MY    NA  22371755
## 113                             Namibia     NA 0.606   1083022
## 114                       New Caledonia     NC    NA    186697
## 115                               Niger     NE 0.297   3536485
## 116                             Nigeria     NG 0.467  82834089
## 117                           Nicaragua     NI    NA   3515723
## 118                         Netherlands     NL    NA  15163329
## 119                              Norway     NO    NA   4120471
## 120                               Nepal     NP    NA   5167009
## 121                         New Zealand     NZ    NA   3889661
## 122                                Oman     OM    NA   3056963
## 123                            Pakistan     PK    NA  71069783
## 124                              Panama     PA    NA   2588030
## 125                                Peru     PE    NA  24247490
## 126                         Philippines     PH    NA  44533489
## 127                    Papua New Guinea     PG    NA   1007089
## 128                              Poland     PL    NA  23022948
## 129                         Puerto Rico     PR    NA   3309915
## 130                     Dem. Rep. Korea     KP    NA  15249400
## 131                            Portugal     PT    NA   6543100
## 132                            Paraguay     PY    NA   3893283
## 133                           Palestine     PS    NA   3222128
## 134                               Qatar     QA    NA   2354450
## 135                             Romania     RO    NA  10829091
## 136                  Russian Federation     RU    NA 106317250
## 137                              Rwanda     RW 0.429   3158661
## 138                      Western Sahara     EH    NA        NA
## 139                        Saudi Arabia     SA    NA  25521904
## 140                               Sudan     SD 0.419  12688618
## 141                         South Sudan     SS    NA   2143723
## 142                             Senegal     SN 0.471   6311994
## 143                     Solomon Islands     SB    NA    125897
## 144                        Sierra Leone     SL 0.348   2801791
## 145                         El Salvador     SV    NA   4161602
## 146                          Somaliland   <NA>    NA        NA
## 147                             Somalia     SO    NA   5280659
## 148                              Serbia     RS    NA   3954261
## 149                            Suriname     SR    NA    362098
## 150                            Slovakia     SK    NA   2912903
## 151                            Slovenia     SI    NA   1024701
## 152                              Sweden     SE    NA   8306173
## 153                           Swaziland     SZ 0.536    276050
## 154                               Syria     SY    NA  10994729
## 155                                Chad     TD 0.336   3031548
## 156                                Togo     TG 0.455   2853180
## 157                            Thailand     TH    NA  33643263
## 158                          Tajikistan     TJ    NA   2232184
## 159                        Turkmenistan     TM    NA   2716066
## 160                         Timor-Leste     TL    NA    389689
## 161                 Trinidad and Tobago     TT    NA    115809
## 162                             Tunisia     TN 0.710   7426857
## 163                              Turkey     TR    NA  56148395
## 164                              Taiwan     TW    NA        NA
## 165                            Tanzania     TZ 0.470  16141097
## 166                              Uganda     UG 0.454   6122464
## 167                             Ukraine     UA    NA  31455854
## 168                             Uruguay     UY    NA   3253766
## 169                       United States     US    NA 259460378
## 170                          Uzbekistan     UZ    NA  11158278
## 171                           Venezuela     VE    NA  27339021
## 172                             Vietnam     VN    NA  30494475
## 173                             Vanuatu     VU    NA     66827
## 174                               Yemen     YE    NA   8930838
## 175                        South Africa     ZA 0.625  35067853
## 176                              Zambia     ZM 0.443   6322121
## 177                            Zimbabwe     ZW 0.387   5008948
##     unemployment  pop_growth literacy
## 1             NA  3.18320146       NA
## 2             NA  3.48541253 66.03011
## 3          17.49 -0.20704700       NA
## 4             NA  0.71476252       NA
## 5           7.27  1.03270928       NA
## 6          17.50  0.43833153       NA
## 7             NA          NA       NA
## 8             NA          NA       NA
## 9           6.08  1.53587885       NA
## 10          5.62  0.73086728       NA
## 11          4.91  1.24820900 99.78899
## 12          1.57  2.99226469 61.56973
## 13          8.52  0.23437084       NA
## 14            NA  2.78228713       NA
## 15          6.50  2.96197794 34.59940
## 16            NA  1.15718803       NA
## 17         11.42 -0.56838926       NA
## 18            NA  1.29813295       NA
## 19         27.52 -1.08764131       NA
## 20          0.50  0.08990256       NA
## 21         11.57  2.15937976       NA
## 22          2.01  1.54465177       NA
## 23          6.85  0.88756333 91.72943
## 24          6.97  1.46512371       NA
## 25          2.63  1.49048211       NA
## 26            NA  1.86485526       NA
## 27            NA  0.34917221       NA
## 28          6.91  1.08358781       NA
## 29          4.83  1.22010397       NA
## 30          6.66  0.85992460       NA
## 31          4.10  0.50631159       NA
## 32            NA  2.53976657 43.90842
## 33          4.32  2.66187609       NA
## 34            NA  3.31917586       NA
## 35            NA  2.48821514       NA
## 36          8.58  0.94378271 94.18625
## 37          9.06  1.08145876       NA
## 38          2.70  0.24155516       NA
## 39            NA          NA       NA
## 40         16.09  0.73277757       NA
## 41          6.11  0.10527758       NA
## 42          4.98  0.41687736       NA
## 43            NA  1.71118230       NA
## 44          6.59  0.50705328       NA
## 45          6.40  1.20412493 91.76376
## 46         10.60  2.00066646       NA
## 47          3.48  1.53063409 94.22264
## 48         13.10  2.20814281       NA
## 49            NA          NA       NA
## 50         24.44 -0.29895106 98.09372
## 51          7.35 -0.26225618       NA
## 52         17.64  2.57906831       NA
## 53          8.66  0.41356021       NA
## 54          6.17  0.68999736       NA
## 55            NA          NA       NA
## 56         10.30  0.50386891       NA
## 57            NA  3.16529286       NA
## 58          6.11  0.75334950       NA
## 59         12.35 -1.30616278 99.58619
## 60            NA  2.31233605       NA
## 61            NA  2.30403964 32.00386
## 62            NA  3.09928290       NA
## 63            NA  2.59749832 45.58116
## 64            NA  4.12842100       NA
## 65         26.49 -0.66611329       NA
## 66         10.30 -0.33339867       NA
## 67          2.91  2.07715182 81.28590
## 68            NA  0.69827307 85.63973
## 69          5.49  1.73395300 87.19753
## 70         17.29 -0.40734318       NA
## 71            NA  1.33965419       NA
## 72          7.73 -0.26937877       NA
## 73          4.05  1.22204863 95.11622
## 74            NA  1.18932821       NA
## 75         11.26  0.41085101       NA
## 76         10.57  1.25215632 84.70524
## 77            NA  3.26040676       NA
## 78          4.90  1.11250476       NA
## 79          5.89  1.91954380       NA
## 80         12.68  0.91750410       NA
## 81         13.74  0.35982505       NA
## 82         11.90  4.59753829       NA
## 83          3.58 -0.13269422       NA
## 84          5.06  1.47972230       NA
## 85            NA  2.63611636 78.73304
## 86          8.05  2.00610790       NA
## 87          0.18  1.63799953       NA
## 88          3.53  0.62814986       NA
## 89            NA          NA       NA
## 90            NA  4.98868141       NA
## 91            NA  1.25225855       NA
## 92            NA  6.01643946       NA
## 93            NA  2.40753043       NA
## 94            NA  0.13125726       NA
## 95          4.40  0.89951279       NA
## 96            NA  1.33349509 76.63520
## 97         10.70 -0.85982734       NA
## 98          5.85  2.35697870       NA
## 99         10.85 -0.94174335       NA
## 100         9.70  1.44790425       NA
## 101         3.86 -0.06097010       NA
## 102           NA  2.70109745       NA
## 103         4.81  1.36624560 94.55588
## 104        28.03  0.08456061       NA
## 105         6.38  2.90103101       NA
## 106           NA  0.92092177       NA
## 107        18.00  0.09702201       NA
## 108         4.80  1.89161420       NA
## 109        25.30  2.90069573       NA
## 110           NA  2.94025368       NA
## 111           NA  2.92294017 65.14537
## 112         2.88  1.73957921       NA
## 113        18.52  2.32423734       NA
## 114        14.59  1.88329483       NA
## 115           NA  3.84268093       NA
## 116         4.56  2.65955070       NA
## 117         4.52  1.14134117       NA
## 118         7.42  0.35982817       NA
## 119         3.48  1.12773668       NA
## 120         3.00  1.20029747       NA
## 121         5.38  1.51033949       NA
## 122           NA  6.50465955 91.98120
## 123         1.83  2.08779243 56.97715
## 124         4.82  1.69263169       NA
## 125         5.71  1.32482978 93.70795
## 126         3.60  1.63281925       NA
## 127           NA  2.12300260       NA
## 128         8.99 -0.07484623       NA
## 129        13.91 -1.63312833       NA
## 130           NA  0.52048386       NA
## 131        13.89 -0.53919047       NA
## 132         7.83  1.33420075 94.61672
## 133        26.95  2.95799495 96.42839
## 134         0.19  5.36123596 97.74669
## 135         6.80 -0.37457550       NA
## 136         5.16  0.21770010       NA
## 137         1.17  2.50079653       NA
## 138           NA          NA       NA
## 139         5.72  2.74137582       NA
## 140           NA  2.38118456       NA
## 141           NA  3.11346114       NA
## 142           NA  2.97087780       NA
## 143           NA  2.10557753       NA
## 144         4.68  2.24393811       NA
## 145         4.16  0.48535177       NA
## 146           NA          NA       NA
## 147           NA  2.85828598       NA
## 148        19.22 -0.46948929       NA
## 149         6.94  0.98820760       NA
## 150        13.18  0.09704542       NA
## 151         9.67  0.09835192       NA
## 152         7.92  0.99221973       NA
## 153           NA  1.84228953       NA
## 154           NA -3.10722942       NA
## 155           NA  3.26470637       NA
## 156           NA  2.60621232       NA
## 157         0.58  0.40086071       NA
## 158           NA  2.23624562       NA
## 159           NA  1.84568053       NA
## 160           NA  2.37356691       NA
## 161         2.22  0.46212427       NA
## 162           NA  1.16751285 79.03643
## 163         9.88  1.62719411 95.43963
## 164           NA          NA       NA
## 165         2.12  3.10757242       NA
## 166           NA  3.35065035       NA
## 167         9.27 -0.47961593       NA
## 168         6.55  0.33807176 98.43593
## 169         6.17  0.74312426       NA
## 170           NA  1.68690036 99.98055
## 171         6.95  1.37753896       NA
## 172         1.26  1.13799857       NA
## 173           NA  2.22981472       NA
## 174        13.47  2.58590538       NA
## 175        24.90  1.42592504 94.13990
## 176           NA  3.04021077       NA
## 177        11.32  2.34479907 88.69342
```

Si lograste ver un `data.frame` con varias columnas y filas, significa que conseguiste cargar e "imprimir" correctamente el objeto `worldbank_df`.

-   Para conocer más sobre un objeto en R, usa la función `str` (*structure*). **Explora la estructura de `worldbank_df`**.

``` r
str(worldbank_df)
## Classes 'tbl_df', 'tbl' and 'data.frame':    177 obs. of  7 variables:
##  $ name        : chr  "Afghanistan" "Angola" "Albania" "United Arab Emirates" ...
##  $ iso_a2      : chr  "AF" "AO" "AL" "AE" ...
##  $ HDI         : num  NA 0.504 NA NA NA NA NA NA NA NA ...
##  $ urban_pop   : num  8609463 11649562 1629715 7734365 39372787 ...
##  $ unemployment: num  NA NA 17.49 NA 7.27 ...
##  $ pop_growth  : num  3.183 3.485 -0.207 0.715 1.033 ...
##  $ literacy    : num  NA 66 NA NA NA ...
```

Varios filtros a `worldbank_df`
-------------------------------

-   **Filtra `worldbank_df` mostrando sólo la fila (país) que corresponde a tu número aleatorio**.

> `worldbank_df` es un `data.frame` y, por lo tanto, como cualquier tabla, es susceptible de filtrado ("extraer" filas/columnas). A continuación te explico brevemente cómo funciona el filtrado de un `data.frame` en R. Denominemos `x` a un `data.frame`. Podemos filtrar a `x` mediante índices de extracción de filas `i` y columnas `j`, de la siguiente manera: `x[i,j]`. Como ves, el índice de filas corresponde a la primera parte dentro de los corchetes, y el índice de columnas a la segunda. Así, si necesitas la fila 1 de `x`, con todas sus columnas, escribes `x[1,]`, e igualmente con la columna 1 y todas las filas x\[,1\]; si sólo necesitas la "celda" que ocupa la fila 1 columna 1, ejecutas `x[1,1]`.

``` r
worldbank_df[ 115 , ] 
##      name iso_a2   HDI urban_pop unemployment pop_growth literacy
## 115 Niger     NE 0.297   3536485           NA   3.842681       NA
```

-   La columna de **población urbana ocupa la posición 4**. Puedes recuperar dicha columna escribiendo su posición en el índice de columnas. Escribe el código necesario para mostrar la **población urbana del país que te tocó usando posición de columna**.

``` r
worldbank_df[ 115 , 4 ] 
## [1] 3536485
```

-   Puedes usar el nombre de la columna alternativamente, en lugar de su posición. Por ejemplo, la columna de población urbana se denomina **`urban_pop`**. Si escribes dicho nombre entre apóstrofos dentro del índice de columnas, la recuperarías al igual que en el caso anterior. Escribe el código necesario para mostrar la **población urbana del país que te tocó usando nombre de columna**.

``` r
worldbank_df[ 115 , 'urban_pop' ] 
## [1] 3536485
```

Tejido del documento
--------------------

-   Lee la [sección **"Antes de tejer"**](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/guia-minima-de-rmarkdown.md#antes-de-tejer) y la [sección **"Teje"**](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/guia-minima-de-rmarkdown.md#teje) de la Guía Mínima de RMarkdown.

-   Cuando estés preparado/a, **teje tu `.Rmd`**. Generarás un `.md` nuevo, que contendrá los cambios que hayas hecho, incluyendo los resultados que produzca tu código.

> Como pone la Guía, "Debes estar pendiente a los errores...", porque si el código no se ejecuta correctamente, no se podrá generar el `.md`. Por ello es muy importante que, antes de tejer, hayas ejecutado tu código en la consola y comprobado que genera resultados sin errores.

Tarea final: *commit*&gt;*push*
-------------------------------

-   Usa la guía [¿Cómo realizar una asignación?](https://github.com/maestria-geotel-201902/material-de-apoyo/blob/master/ref/como-hacer-una-asignacion.md) para **sincronizar con tu repo remoto**.

Si llegaste hasta aquí sin fallos, pasaste varios mundos. Sin embargo, las probabilidades de que encuentres tropiezos son de más de un 60%. Tropiezos, errores, fallos, "da error" conllevarán aprendizajes.
