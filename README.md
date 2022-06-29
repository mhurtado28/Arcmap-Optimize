## OPTIMIZACIÓN DE MULTIPLES GEOPROCESOS DE INTERSECCIÓN  :earth_americas:

ANTES DE USAR ESTAS LINEAS DE CODIGO, SE DEBEN CARGAR LOS POLIGONOS QUE VAS A USAR EN LA TABLA DE CONTENIDO Y LOS NOMBRES DEBEN COINCIDIR CON LOS NOMBRES EN EL CODIGO.

##### Despues, Colocar el poligono sobre el que realizarás el geoproceso (El polígono del predio o área de interes)
*in_feature =  "nombre_primera capa #; nombre_segundaCapa #"* 

##### Colocar la dirección de la carpeta en donde quieres alojar el resultado y terminar con el nombre que le quieres dar al archivo resultante de la intersección. 

*out_feature_class = "Direccion_carpeta/Nombre_del_poligono_resultante"* 

Nota : NO REPETIR NOMBRES PARA LAS CAPAS A GENERAR

```sh
import arcpy

#intersect geoprocess 
arcpy.Intersect_analysis(in_features=" RAMSAR_2018 #; ecohostel #", out_feature_class="C:/Users/UNIMAG/OneDrive - Universidad del Magdalena/Documentos/ArcGIS/Default.gdb/RAMSAR_ecohostel",join_attributes="ALL", cluster_tolerance="-1 Unknown", output_type="INPUT")

arcpy.Intersect_analysis(in_features=" RECUPERACIONMAG #; ecohostel #", out_feature_class="C:/Users/UNIMAG/OneDrive - Universidad del Magdalena/Documentos/ArcGIS/Default.gdb/RECUPERACION_MAG_ecohostel", join_attributes="ALL", cluster_tolerance="-1 Unknown", output_type="INPUT")

#To save
featurelist = ["RAMSAR_ecohostel", "RECUPERACION_MAG_ecohostel"]
outpath = r"C:/RADICADOS_CORPAMAG/python_aia/output"
arcpy.FeatureClassToShapefile_conversion(featurelist, outpath)
```
