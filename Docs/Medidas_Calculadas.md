| NAME                            | Expression                                                                                         |
| ------------------------------- | -------------------------------------------------------------------------------------------------- |
| Fecha de Actualización          | <br>CALCULATE(<br>    MAX( MII_CALIDAD[FECHA] ),<br>    ALL( MII_CALIDAD )<br>)<br>                |
| Fecha de Actualización Empalmes | <br>CALCULATE(<br>    MAX( Empalmes[DATA_MOVIMIENTO] ),<br>    ALL( Empalmes )<br>)                |
| Bobinas Producidas              | <br>DISTINCTCOUNT ( Empalmes[LOTE] )<br>                                                           |
| Lotes con Empalme               | <br>CALCULATE(<br>    DISTINCTCOUNT ( Empalmes[LOTE] ),<br>    Empalmes[EMPALME] <> 0<br>)<br><br> |
| % Bobinas con Empalme           | <br>DIVIDE(<br>    [Lotes con Empalme],<br>    [Bobinas Producidas],<br>    0<br>)<br>             |
| Lotes con +1 Empalme            | <br>CALCULATE(<br>    DISTINCTCOUNT ( Empalmes[LOTE] ),<br>    Empalmes[EMPALME] > 1<br>)<br>      |
