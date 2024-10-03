import pandas as pd
import numpy as np

# Rutas y ficheros

path = '/'
path2 = '/'
file1 = '.xlsx'
file2 = '.xlsx'
mes = 'MES 1'
m = 'octubre'



# Maquetas indicadores de estación
def maquetas(indicador,path,file1):
    maquetas = pd.read_excel(path + file1, sheet_name='maquetas')
    lineas = ['1','2','3','4','5','6','7','14','8','9','17','10','13','11','12','16','15']
    tipo_dia = ['laborable','laborable','laborable','sabado','sabado','sabado','festivo','festivo','festivo']
    turno = ['mañana','tarde','noche']*3
    ind_ = maquetas.loc[maquetas['Unnamed: 0']==indicador].index[0]
    maqueta_ = maquetas.loc[ind_+1:ind_+9,['Unnamed: 2', 'Unnamed: 3', 'Unnamed: 4', 'Unnamed: 5', 'Unnamed: 6',
           'Unnamed: 7', 'Unnamed: 8', 'Unnamed: 9', 'Unnamed: 10', 'Unnamed: 11',
           'Unnamed: 12', 'Unnamed: 13', 'Unnamed: 14', 'Unnamed: 15',
           'Unnamed: 16', 'Unnamed: 17', 'Unnamed: 18']].reset_index(drop=True)
    maqueta_ = maqueta_.rename(columns={col:linea for linea, col in zip(lineas,maqueta_.columns)})
    df_cols = pd.DataFrame(zip(tipo_dia,turno),columns=['tipo_dia','turno'])
    matriz = df_cols.join(maqueta_)
    return matriz
