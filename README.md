# Edad de mortalidad en México
Este proyecto analiza los datos de defunción de la base de datos del 2020 obtenida de:
http://www.dgis.salud.gob.mx/descargas/datosabiertos/excesoMortalidad/Exceso_Mortalidad_MX_2020_Historico.zip?v=2022.11.04

La base de datos tiene varios comprimidos, usamos el que dice Exceso_Mortalidad_MX_2020_quincena001_SE41 y la tabla que contiene dentro

Cargamos el archivo csv en MySQL cambiando el nombre de las columnas de la siguiente manera:

FECHA_ACTUALIZACION: fecha_actualizacion
ID_REGISTRO: id_registro (primary key)
ENTIDAD_REG: estado
MUNICIPIO_REG: municipio
FECHA_DEFUNCION: fecha_defuncion
SEXO: sexo

Las librerias necesarias en este proyecto son las siguientes:
import mysql.connector
import pandas as pd
import matplotlib.pyplot as plt
from tabulate import tabulate

El proyecto analiza las edades de defunción de manera simple, los clasifica por edad y estado. 
Cada número de estado corresponde a un estado en orden alfabético de acuerdo a la siguiente página:
https://www.agricultura.gob.mx/sites/default/files/sagarpa/document/2018/07/17/8/180717115914/entidades-federativas.pdf

Se hacen pequeñas consultas como edades mínimas y maximas agrupandolas por estado y sexo, se calcula el promedio de edad de defunción y
finalmente se hace un histograma de las edades de defunción para tener un idea de la probabilidad de tener una nueva defunción a cierta edad.
