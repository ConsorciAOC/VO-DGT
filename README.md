# VO-DGT





# Índex

1. [Introducció](#1)
2. [Transmissions de dades disponibles](#2)
3. [Missatgeria dels serveis](#3)
   1. [Consulta de dades d’un vehicle (DGT_DADES_VEHICLE)](#3.1)
      1. [3.1.1 Petició – dades específiques](#3.1.1)
      2. [3.1.2 Resposta – dades específiques](#3.1.2)
   2. [3.2	Consulta de dades d’un vehicle per a sancions (DGT_DADES_VEHICLE_SANCIONS)](#3.2)
      1. [3.2.1 Petició – dades específiques](#3.2.1)
      2. [3.2.2 Resposta – dades específiques](#3.2.2)
   3. [3.3	Consulta dels permisos de conduir d’un titular (DGT_PERMISOS_CONDUCTOR)](#3.3)
      1. [3.3.1 Petició – dades específiques](#3.3.1)
      2. [3.3.2 Resposta – dades específiques](#3.3.2)
   4. [3.4 Consulta de dades de l’assegurança d’un vehicle (DGT_TITULAR_VIA)](#3.4)
      1. [3.4.1 Petició – dades específiques](#3.4.1)
      2. [3.4.2 Resposta – dades específiques](#3.4.2)
   5. [3.5 Consulta de sancions d’un conductor (DGT_SANCIONS_CONDUCTOR)](#3.4)
      1. [3.4.1 Petició – dades específiques](#3.5.1)
      2. [3.4.2 Resposta – dades específiques](#3.5.2)
   6. [3.6 Consulta de vehicles d’un conductor (DGT_VEHICLES_CONDUCTOR)](#3.4)
      1. [3.4.1 Petició – dades específiques](#3.6.1)
      2. [3.4.2 Resposta – dades específiques](#3.6.2)
 


# 1. Introducció <a name="1"></a>

Aquest document detalla la missatgeria associada al servei de consulta d’informació del registre de vehicles i conductors de la Dirección General de Tráfico (en endavant DGT).

Per poder realitzar la integració cal conèixer prèviament la següent documentació:
•	Document de Missatgeria Genèrica de la PCI del Consorci AOC.

# 2 Transmissions de dades disponibles <a name="2"></a>

Les dades disponibles a través del servei són les que es presenten a continuació:

| **EMISSOR** |
| --- |
| DGT (Dirección General de Tráfico) |

| **PRODUCTE** | **MODALITAT** | **DESCRIPCIO** |
| --- | --- | --- |
| **DGT** | DGT	DGT_DADES_VEHICLE | Consulta de dades d’un vehicle. |
| **DGT** | DGT_DADES_VEHICLE_SANCIONS | Consulta de dades d’un vehicle per a sancions. |
| **DGT** | DGT_PERMISOS_CONDUCTOR | onsulta de dades dels permisos de conduir d'un conductor. |
| **DGT** | DGT_TITULAR_VIA | Consulta de dades d'un vehicle per part del titular de la via. |
| **DGT** | DGT_SANCIONS_CONDUCTOR | Consulta de sancions, vigències i condemnes penals d'un conductor. |
| **DGT** | DGT_VEHICLES_CONDUCTOR | Consulta dels vehicles enregistrats a la DGT per a un propietari. |


# 3 Missatgeria dels serveis <a name="3"></a>

A continuació es detalla la missatgeria corresponent al bloc de dades específiques de les modalitats de consum del producte DGT.


## 3.1 CConsulta de dades d’un vehicle (DGT_DADES_VEHICLE) <a name="3.1"></a>

Consulta de les dades d’un vehicle a partir de la matrícula, número de bastidor o NIVE.

Aquesta consulta requereix disposar de conveni amb la DGT.
 
### 3.1.1 Petició <a name="3.1.1"></a>

| _Element_ | _Descripció_ |
| --- | --- |
| peticioConsultaVehicle/matricula| Matrícula del vehicle. |
| peticioConsultaVehicle/bastidor	| Bastidor del vehicle. |
| peticioConsultaVehicle/nive	| NIVE del vehicle. |

![image](https://user-images.githubusercontent.com/32306731/145855951-db9dfd14-bf9d-478a-a434-20c62e2c1b8a.png)

============================== CONTINUAR A PARTIR D'AQUI

3.1.2	Resposta – dades específiques



Element	Descripció
respostaConsultaVehicle/ peticioConsultaVehicle	Bloc de dades corresponent a la petició que origina la resposta.
respostaConsultaVehicle/resposta/	Dades del vehicle consultat.
 


Element	Descripció
DatosVehiculo	
respostaConsultaVehicle/resultat/ codiResultat	Codi de resultat de la consulta:
•	0: consulta realitzada correctament.
•	1: vehicle sense antecedents.
•	0502: error realitzant la consulta.
respostaConsultaVehicle/resultat/ descripcio	Descripció del resultat.

3.1.2.1	Dades d’un vehicle

Element	Descripció
Dades generals
DatosVehiculo/DatosGenerales	Bloc de dades corresponent a les dades generals del vehicle.
//DatosGenerales/DescripcionVehiculo	Bloc de dades corresponent a la descripció del vehicle.
//DescripcionVehiculo/Bastidor	Número de bastidor del vehicle.
//DescripcionVehiculo/NIVE	NIVE del vehicle.
//DescripcionVehiculo/Marca/Codigo	Marca del vehicle.
//DescripcionVehiculo/Marca/Descripcion	
//DescripcionVehiculo/Modelo	Model del vehicle.
//DescripcionVehiculo/Servicio/Codigo	Servei al que està destinat el vehicle.
//DescripcionVehiculo/Servicio/Descripcion	
//DescripcionVehiculo/TipoIndustria
/Codigo	Tipus definit per indústria.
//DescripcionVehiculo/TipoIndustria
/Descripcion	
//DescripcionVehiculo/TipoVehiculo
/Codigo	Tipus de vehicle.
//DescripcionVehiculo/TipoVehiculo
/Descripcion	
//DatosGenerales/DomicilioVehiculoDGT	Bloc de dades corresponent al domicili del vehicle a la DGT.
//DomicilioVehiculoDGT/Calle	Adreça.
//DomicilioVehiculoDGT/CodigoPostal	Codi postal.
//DomicilioVehiculoDGT/Municipio	Municipi.
//DomicilioVehiculoDGT/Provincia/Codigo	Província.
//DomicilioVehiculoDGT/Provincia/Nombre	
//DomicilioVehiculoDGT/Localidad	Localitat.
 


Element	Descripció
	
//DatosGenerales/DomicilioVehiculoINE	Bloc de dades corresponent al domicili de residència del titular del vehicle a l’INE.
//DomicilioVehiculoINE/Bloque	Bloc.
//DomicilioVehiculoINE/CodigoPostal	Codi postal.
//DomicilioVehiculoINE/Escalera	Escala.
//DomicilioVehiculoINE/Hectometro	Hectòmetre.
//DomicilioVehiculoINE/Kilometro	Quilòmetre.
//DomicilioVehiculoINE/Municipio	Municipi.
//DomicilioVehiculoINE/NumeroVia	Número de via.
//DomicilioVehiculoINE/Planta	Planta.
//DomicilioVehiculoINE/Portal	Portal.
//DomicilioVehiculoINE/Provincia/Codigo	Província.
//DomicilioVehiculoINE/Provincia
/Descripcion	
//DomicilioVehiculoINE/Localidad	Localitat.
//DomicilioVehiculoINE/Puerta	Porta.
//DomicilioVehiculoINE/TipoVia	Codi de via.
//DomicilioVehiculoINE/NombreVia	Nom de la via.
//Indicadores/BajaTemporal	Indicador de la baixa temporal del vehicle.
//Indicadores/BajaDefinitiva	Indicador de la baixa definitiva del vehicle.
//Matriculacion/FechaPrimeraMatriculacion	Data de la primera matriculació.
//Matriculacion/FechaMatriculacion	Data de matriculació.
//Matriculacion/Matricula	Matrícula.
//DatosGenerales/Titular	Bloc de dades corresponent a les dades del titular del vehicle.
//Titular/DomicilioDGT	Bloc de dades corresponent al domicili del titular del vehicle a la DGT.
//DomicilioDGT/NombreVia	Adreça.
//DomicilioDGT/CodigoPostal	Codi postal.
//DomicilioDGT/Municipio	Municipi.
//DomicilioDGT/Provincia/Codigo	Província.
 


Element	Descripció
//DomicilioDGT/Provincia/Nombre	
//DomicilioDGT/Localidad	Localitat.
//Titular/DomicilioINE	Bloc de dades corresponent al domicili del titular del vehicle a l’INE.
//DomicilioINE/Bloque	Bloc.
//DomicilioINE/CodigoPostal	Codi postal.
//DomicilioINE/Escalera	Escala.
//DomicilioINE/Hectometro	Hectòmetre.
//DomicilioINE/Kilometro	Quilòmetre.
//DomicilioINE/Municipio	Municipi.
//DomicilioINE/NumeroVia	Número de via.
//DomicilioINE/Planta	Planta.
//DomicilioINE/Portal	Portal.
//DomicilioINE/Provincia/Codigo	Província.
//DomicilioINE/Provincia/Descripcion	
//DomicilioINE/Localidad	Localitat.
//DomicilioINE/Puerta	Porta.
//DomicilioINE/TipoVia	Codi de via.
//DomicilioINE/NombreVia	Nom de la via.
Dades tècniques
DatosVehiculo/DatosTecnicos	Bloc de dades corresponent a les dades tècniques del vehicle.
//DatosTecnicos/NivelEmisiones	Nivell d’emissions del vehicle.
//DatosTecnicos/Masas	Dades de les masses del vehicle.
//DatosTecnicos/Masas/MasaMaximaTecnica	Massa màxima tècnica.
//DatosTecnicos/Masas/MasaMaxima	Massa màxima.
//DatosTecnicos/Masas/MasaServicio	Massa de servei.
//DatosTecnicos/Masas/Tara	Tara.
//DatosTecnicos/Plazas	Dades de les places del vehicle.
//DatosTecnicos/Plazas/Mixtas	Número de places mixtes.
//DatosTecnicos/Plazas/Normales	Número de places normals.
 


Element	Descripció
//DatosTecnicos/Plazas/NumeroPlazasPie	Número de places de peu.
//DatosTecnicos/Potencias	Dades de les potències.
//DatosTecnicos/Potencias/Cilindrada	Cilindrada.
//DatosTecnicos/Potencias/PotenciaFiscal	Potència fiscal.
//DatosTecnicos/Potencias
/PotenciaNetaMaxima	Potència neta.
//DatosTecnicos/Potencias
/RelacionPotenciaPeso	Relació potència pes.
Dades de tràmits
//DatosTramites/ListaBajas/Baja	Bloc de dades corresponent a cadascuna de les baixes enregistrades pel vehicle.
//Baja/TipoBaja/Codigo	Tipus de baixa.
//Baja/TipoBaja/Descripcion	
//Baja/FechaInicio	Data d’inici de la baixa.
//Baja/FechaFin	Data de fi de la baixa en cas que no sigui definitiva.
//Baja/CausaBaja/Codigo	Motiu de la baixa.
//Baja/CausaBaja/Descripcion	
//Baja/Jefatura/Codigo	Prefectura.
//Baja/Jefatura/Descripcion	
//Baja/Sucursal/Codigo	Sucursal.
//Baja/Sucursal/Descripcion	
//DatosTramites/ListaTransferencias
/Transferencia	Bloc de dades corresponent a cadascuna de les transferències enregistrades pel vehicle.
//Transferencia/FechaTransferencia	Data de la transferència.
//Transferencia/DocumentacionAnterior	Document d’identitat del titular anterior del vehicle (CIF, NIF o NIE).
//Transferencia/Jefatura/Codigo	Prefectura.
//Transferencia/Jefatura/Descripcion	
//Transferencia/Sucursal/Codigo	Sucursal.
//Transferencia/Sucursal/Descripcion	
//DatosTramites/ListaDuplicados
/Duplicado	Bloc de dades corresponent a cadascun dels duplicats de permisos de circulació expedits pel vehicle.
 


Element	Descripció
//Duplicado/FechaDuplicado	Data del duplicat.
//Duplicado/Jefatura/Codigo	Prefectura.
//Duplicado/Jefatura/Descripcion	
//Duplicado/Sucursal/Codigo	Sucursal.
//Duplicado/Sucursal/Descripcion	
//Duplicado/RazonDuplicado/Codigo	Motiu d’expedició del duplicat.
//Duplicado/RazonDuplicado/Descripcion	
Dades administratives
//DatosAdministrativos/ListaImpagos
/Impago	Bloc de dades corresponent a un impagament del vehicle consultat.
//Impago/AnioImpago	Any de l’impagament.
//Impago/Documentacion	Documentació de l’impagament.
//Impago/Provincia/Codigo	Província.
//Impago/Provincia/Descripcion	
//Impago/Municipio/Codigo	Municipi.
//Impago/Municipio/Descripcion	
//DatosAdministrativos/ListaEmbargos
/Embargo	Bloc de dades corresponent a un embargament del vehicle consultat.
//Embargo/Autoridad/Codigo	Autoritat que porta a terme l’embargament.
//Embargo/Autoridad/Descripcion	
//Embargo/Expediente	Número d’expedient associat al tràmit.
//Embargo/FechaMaterializacion	Data en que es va efectuar l’embargament.
//Embargo/FechaTramite	Data d’inici del tràmit.
Dades ITVs
//DatosITVs/Itv	Bloc de dades corresponent a cadascuna de les ITVs que ha passat el vehicle.
//Itv/Anotacion	Anotació.
//Itv/CuentaHoras	Compta hores.
//Itv/Estacion	Estació on es va passar la ITV.
//Itv/FechaCaducidad	Data de caducitat.
//Itv/FechaFinAnterior	Data de caducitat de l’anterior ITV.
//Itv/FechaItv	Data ITV.
 


Element	Descripció
//Itv/Kilometraje	Quilometratge.
//Itv/MotivoItv/Codigo	Motiu.
//Itv/MotivoItv/Descripcion	
//Itv/Provincia/Codigo	Província.
//Itv/Provincia/Descripcion	
//Itv/ResultadoItv/Codigo	Resultat de l’ITV.
//Itv/ResultadoItv/Descripcion	
//Itv/DefectosITV/DefectoITV	Bloc de dades corresponent a un defecte trobat en la inspecció.
//DefectoITV/GravedadDefectoItv/Codigo	Gravetat del defecte.
//DefectoITV/GravedadDefectoItv
/Descripcion	
//DefectoITV/TipoDefectoItv/Codigo	Tipus de defecte.
//DefectoITV/TipoDefectoItv/Descripcion	
Dades titular
//DatosTitular	Bloc de dades corresponent al titular del vehicle.
//DatosTitular/TipoDocumentacion	Tipus de documentació.
//DatosTitular/Documentacion	Documentació.
//DatosTitular/NombreCompleto	Nom complert.
//DatosTitular/Nombre	Nom.
//DatosTitular/Apellido1	Primer cognom.
//DatosTitular/Apellido2	Segon cognom.


3.2	Consulta	de	dades	d’un	vehicle	per	a	sancions (DGT_DADES_VEHICLE_SANCIONS)
Consulta de les dades d’un vehicle per a sancions a partir de la matrícula, número de bastidor o NIVE.


3.2.1	Petició – dades específiques


Element	Descripció
peticioConsultaVehicleSancions/matricula	Matrícula del vehicle.
peticioConsultaVehicleSancions/bastidor	Bastidor del vehicle.
 


Element	Descripció
	
peticioConsultaVehicleSancions/nive	NIVE del vehicle.

3.2.2	Resposta – dades específiques


Element	Descripció
respostaConsultaVehicleSancions/ peticioConsultaVehicleSancions	Bloc de dades corresponent a la petició que origina la resposta.
respostaConsultaVehicleSancions/ resposta/DatosVehiculo	Dades del vehicle consultat.
respostaConsultaVehicleSancions/ resultat/codiResultat	Codi de resultat de la consulta:
•	0: consulta realitzada correctament.
•	1: vehicle sense antecedents.
•	2: el vehicle existeix però no té dades.
•	0502: error realitzant la consulta.
respostaConsultaVehicleSancions/ resultat/descripcio	Descripció del resultat.


 


3.2.2.1	Dades d’un vehicle

Element	Descripció
Dades generals
DatosVehiculo/DatosGenerales	Bloc de dades corresponent a les dades generals del vehicle.
//DatosGenerales/DescripcionVehiculo	Bloc de dades corresponent a la descripció del vehicle.
//DescripcionVehiculo/Bastidor	Número de bastidor del vehicle.
//DescripcionVehiculo/NIVE	NIVE del vehicle.
//DescripcionVehiculo/Marca/Codigo	Marca del vehicle.
//DescripcionVehiculo/Marca/Descripcion	
//DescripcionVehiculo/Modelo	Model del vehicle.
//DescripcionVehiculo/Servicio/Codigo	Servei al que està destinat el vehicle.
//DescripcionVehiculo/Servicio/Descripcion	
//DescripcionVehiculo/TipoIndustria
/Codigo	Tipus definit per indústria.
//DescripcionVehiculo/TipoIndustria
/Descripcion	
//DescripcionVehiculo/TipoVehiculo
/Codigo	Tipus de vehicle.
//DescripcionVehiculo/TipoVehiculo
/Descripcion	
//Matriculacion/FechaMatriculacion	Data de matriculació.
//Matriculacion/Matricula	Matrícula.
//DatosGenerales/Titular	Bloc de dades corresponent a les dades del titular del vehicle.
//Titular/DomicilioDGT	Bloc de dades corresponent al domicili del titular del vehicle a la DGT.
//DomicilioDGT/NombreVia	Adreça.
//DomicilioDGT/CodigoPostal	Codi postal.
//DomicilioDGT/Municipio	Municipi.
//DomicilioDGT/Provincia/Codigo	Província.
//DomicilioDGT/Provincia/Nombre	
//DomicilioDGT/Localidad	Localitat.
//Titular/DomicilioINE	Bloc de dades corresponent al domicili del titular del vehicle a l’INE.
//DomicilioINE/Bloque	Bloc.
 


Element	Descripció
	
//DomicilioINE/CodigoPostal	Codi postal.
//DomicilioINE/Escalera	Escala.
//DomicilioINE/Hectometro	Hectòmetre.
//DomicilioINE/Kilometro	Quilòmetre.
//DomicilioINE/Municipio	Municipi.
//DomicilioINE/NumeroVia	Número de via.
//DomicilioINE/Planta	Planta.
//DomicilioINE/Portal	Portal.
//DomicilioINE/Provincia/Codigo	Província.
//DomicilioINE/Provincia/Descripcion	
//DomicilioINE/Localidad	Localitat.
//DomicilioINE/Puerta	Porta.
//DomicilioINE/TipoVia	Codi de via.
//DomicilioINE/NombreVia	Nom de la via.
//FechaCaducidadITV	Data de caducitat ITV.
Dades tècniques
DatosVehiculo/DatosTecnicos	Bloc de dades corresponent a les dades tècniques del vehicle.
//DatosTecnicos/Plazas	Dades de les places del vehicle.
//DatosTecnicos/Plazas/Mixtas	Número de places mixtes.
//DatosTecnicos/Plazas/Normales	Número de places normals.
//DatosTecnicos/Plazas/NumeroPlazasPie	Número de places de peu.
//DatosTecnicos/Potencias	Dades de les potències.
//DatosTecnicos/Potencias
/PotenciaNetaMaxima	Potència neta.
//DatosTecnicos/Potencias
/RelacionPotenciaPeso	Relació potència pes.
Dades de responsables
//DatosResponsables/ListaArrendatarios
/Arrendatario	Bloc de dades corresponent a cadascun dels arrendataris del vehicle consultat.
//Arrendatario/FechaInicio	Data d’inici de l’arrendament.
//Arrendatario/FechaFin	Data de fi de l’arrendament.
 


Element	Descripció
//Arrendatario/Documentacion	Documentació.
//Arrendatario/Filiacion	Dades de filiació de l’arrendatari.
//DatosResponsables/ListaConductoresHabituales
/ConductorHabitual	Bloc de dades corresponent a cadascun conductors habituals del vehicle consultat.
//ConductorHabitual/FechaInicio	Data d’inici del conductor habitual.
//ConductorHabitual/FechaFin	Data de fi del conductor habitual.
//ConductorHabitual/Documentacion	Documentació.
//ConductorHabitual/Filiacion	Dades de filiació del conductor habitual.
//DatosResponsables/ListaTutores/Tutor	Bloc de dades corresponent a cadascun dels tutors que han sol·licitat tràmits sobre el vehicle consultat en nom del titular que és menor d’edat o discapacitat.
//Tutor/Documentacion	Documentació.
//Tutor/Filiacion	Dades de filiació del tutor.
//Tutor/Tramite	Tràmit en que va ser tutor.
//Tutor/FechaTramite	Data en la qual es va realitzar el tràmit.
//DatosResponsables/ListaPoseedores/Poseedor	Bloc de dades corresponent a cadascun dels posseïdors del vehicle consultat.
//Poseedor/Anotacion	Anotació.
//Poseedor/Filiacion	Dades de filiació del posseïdor.
//Poseedor/Documentacion	Documentació.
//Poseedor/FechaPosesion	Data de possessió.
//Poseedor/Situacion/Codigo	Situació de la possessió del vehicle.
//Poseedor/Situacion/Descripcion	
//Poseedor/DomicilioDGT	Bloc de dades corresponent al domicili del titular del vehicle a la DGT (vegeu definicions anteriors).
//Poseedor/DomicilioINE	Bloc de dades corresponent al domicili del titular del vehicle a l’INE (vegeu definicions anteriors).
//Poseedor/Jefatura/Codigo	Prefectura.
//Poseedor/Jefatura/Descripcion	
//Poseedor/Sucursal/Codigo	Sucursal.
//Poseedor/Sucursal/Descripcion	
 


Element	Descripció
	
//Poseedor/Tipo	Tipus de posseïdor.
Dades de tràmits
//DatosTramites/ListaBajas/Baja	Bloc de dades corresponent a cadascuna de les baixes enregistrades pel vehicle.
//Baja/TipoBaja/Codigo	Tipus de baixa.
//Baja/TipoBaja/Descripcion	
//Baja/FechaInicio	Data d’inici de la baixa.
//Baja/FechaFin	Data de fi de la baixa en cas que no sigui definitiva.
//Baja/CausaBaja/Codigo	Motiu de la baixa.
//Baja/CausaBaja/Descripcion	
//Baja/Jefatura/Codigo	Prefectura.
//Baja/Jefatura/Descripcion	
//Baja/Sucursal/Codigo	Sucursal.
//Baja/Sucursal/Descripcion	
//DatosTramites/ListaTransferencias
/Transferencia	Bloc de dades corresponent a cadascuna de les transferències enregistrades pel vehicle.
//Transferencia/FechaTransferencia	Data de la transferència.
//Transferencia/DocumentacionAnterior	Document d’identitat del titular anterior del vehicle (CIF, NIF o NIE).
//Transferencia/Jefatura/Codigo	Prefectura.
//Transferencia/Jefatura/Descripcion	
//Transferencia/Sucursal/Codigo	Sucursal.
//Transferencia/Sucursal/Descripcion	
Dades administratives
//DatosAdministrativos/ListaPrecintos
/Precinto	Bloc de dades corresponent a un precinte del vehicle consultat.
//Precinto/Autoridad/Codigo	Autoritat que porta a terme el precinte.
//Precinto/Autoridad/Descripcion	
//Precinto/Expediente	Número d’expedient associat al tràmit.
//Precinto/FechaMaterializacion	Data en que es va efectuar el precinte.
//Precinto/FechaTramite	Data d’inici del tràmit.
 


Element	Descripció
	
Assegurança
//Seguro	Dades de l’assegurança del vehicle consultat.
//Seguro/ContratoSeguro/Codigo	Dades del contracte de l’assegurança del vehicle.
//Seguro/ContratoSeguro/Descripcion	
//Seguro/Entidad/Codigo	Entitat asseguradora del vehicle.
//Seguro/Entidad/Descripcion	
//Seguro/FechaInicio	Data d’inici de l’assegurança.
//Seguro/FechaFin	Data de fi de l’assegurança.
Dades titular
//DatosTitular	Bloc de dades corresponent al titular del vehicle.
//DatosTitular/TipoDocumentacion	Tipus de documentació.
//DatosTitular/Documentacion	Documentació.
//DatosTitular/NombreCompleto	Nom complert.
//DatosTitular/Nombre	Nom.
//DatosTitular/Apellido1	Primer cognom.
//DatosTitular/Apellido2	Segon cognom.



3.3	Consulta	dels	permisos	de	conduir	d’un	titular (DGT_PERMISOS_CONDUCTOR)
Consulta el permisos de conduir d’un titular a partir del seu document identificador.


3.3.1	Petició – dades genèriques


Element	Descripció
//DatosGenericos/Titular/TipoDocumentacion	Tipus de documentació (DNI o NIE).
//DatosGenericos/Titular/Documentacion	Documentació.
 



3.3.2	Resposta – dades específiques



Element	Descripció
respostaPermisosConductor/resposta/ DatosTitular	Bloc de dades corresponent a les dades del titular.
//DatosTitular	Bloc de dades corresponent al titular del vehicle.
//DatosTitular/TipoDocumentacion	Tipus de documentació.
//DatosTitular/Documentacion	Documentació.
//DatosTitular/NombreCompleto	Nom complert.
//DatosTitular/Nombre	Nom.
//DatosTitular/Apellido1	Primer cognom.
//DatosTitular/Apellido2	Segon cognom.
respostaPermisosConductor/resposta/ DatosConductor	Bloc de dades corresponent a les dades del conductor.
//DatosConductor/FechaNacimiento	Data de naixement.
//DatosConductor/ListaPermisosVigentes
/Permiso	Bloc de dades corresponent a un permís de conduir del titular.
//Permiso/TipoPermiso/Codigo	Tipus de permís.
//Permiso/TipoPermiso/Descripcion	
//Permiso/FechaInicio	Data d’inici del permís.
//Permiso/FechaFin	Data de fi del permís.
respostaPermisosConductor/resultat/ codiResultat	Codi de resultat de la consulta:
•	0: consulta realitzada correctament.
•	1: sense antecedents.
•	2: sense permisos vigents.
•	0502: error realitzant la consulta.
 


Element	Descripció
respostaPermisosConductor/resultat/ descripcio	Descripció del resultat.


3.4	Consulta	de	dades	de	l’assegurança	d’un	vehicle (DGT_TITULAR_VIA)
Consulta de dades d'un vehicle per part del titular de la via a partir de la matrícula, número de bastidor o NIVE.


3.4.1	Petició – dades específiques


Element	Descripció
peticioConsultaTitularVia/matricula	Matrícula del vehicle.
peticioConsultaTitularVia/bastidor	Bastidor del vehicle.
peticioConsultaTitularVia/nive	NIVE del vehicle.



3.4.2	Resposta – dades específiques


Element	Descripció
respostaConsultaAssegurancaVehicle/ peticioConsultaAssegurancaVehicle	Bloc de dades corresponent a la petició que origina la resposta.
respostaConsultaAssegurancaVehicle/ resposta/DomicilioNotificacionTitular	Dades del domicili de notificació del titular del vehicle per a remissió de sancions.
respostaConsultaAssegurancaVehicle/ resposta/DatosSeguro	Dades de l’assegurança del vehicle consultat.
respostaConsultaAssegurancaVehicle/ resultat/codiResultat	Codi de resultat de la consulta:
•	0: consulta realitzada correctament.
•	1: vehicle sense antecedents.
•	2: el vehicle existeix però no té dades.
•	0502: error realitzant la consulta.
respostaConsultaAssegurancaVehicle
/resultat/descripcio	Descripció del resultat.
Dades del domicili del titular
 


Element	Descripció
//DomicilioNotificacionTitular
/DomicilioDGT	Bloc de dades corresponent al domicili del titular del vehicle a la DGT.
//DomicilioDGT/NombreVia	Adreça.
//DomicilioDGT/CodigoPostal	Codi postal.
//DomicilioDGT/Municipio	Municipi.
//DomicilioDGT/Provincia/Codigo	Província.
//DomicilioDGT/Provincia/Nombre	
//DomicilioDGT/Localidad	Localitat.
// DomicilioNotificacionTitular
/DomicilioINE	Bloc de dades corresponent al domicili del titular del vehicle a l’INE.
//DomicilioINE/Bloque	Bloc.
//DomicilioINE/CodigoPostal	Codi postal.
//DomicilioINE/Escalera	Escala.
//DomicilioINE/Hectometro	Hectòmetre.
//DomicilioINE/Kilometro	Quilòmetre.
//DomicilioINE/Municipio	Municipi.
//DomicilioINE/NumeroVia	Número de via.
//DomicilioINE/Planta	Planta.
//DomicilioINE/Portal	Portal.
//DomicilioINE/Provincia/Codigo	Província.
//DomicilioINE/Provincia/Descripcion	
//DomicilioINE/Localidad	Localitat.
//DomicilioINE/Puerta	Porta.
//DomicilioINE/TipoVia	Codi de via.
//DomicilioINE/NombreVia	Nom de la via.
Dades de l’assegurança
//DatosSeguro/ContratoSeguro/Codigo	Dades del contracte de l’assegurança del vehicle.
//DatosSeguro/ContratoSeguro/Descripcion	
//DatosSeguro/Entidad/Codigo	Entitat asseguradora del vehicle.
//DatosSeguro/Entidad/Descripcion	
//DatosSeguro/FechaInicio	Data d’inici de l’assegurança.
 


Element	Descripció
//DatosSeguro/FechaFin	Data de fi de l’assegurança.
Dades titular
//DatosTitular	Bloc de dades corresponent al titular del vehicle.
//DatosTitular/TipoDocumentacion	Tipus de documentació.
//DatosTitular/Documentacion	Documentació.
//DatosTitular/NombreCompleto	Nom complert.
//DatosTitular/Nombre	Nom.
//DatosTitular/Apellido1	Primer cognom.
//DatosTitular/Apellido2	Segon cognom.





3.5	Consulta	de	sancions	d’un	conductor (DGT_SANCIONS_CONDUCTOR)
Consulta de sancions, vigències i condemnes penals d'un conductor.


3.5.1	Petició – dades genèriques
 


Element	Descripció
//DatosGenericos/Titular/TipoDocumentacion	Tipus de documentació (DNI, NIE o NIF).
//DatosGenericos/Titular/Documentacion	Documentació.

3.5.2	Resposta – dades específiques


Element	Descripció
respostaSancionsConductor/resposta/ DatosTitular	Bloc de dades corresponent a les dades del titular.
//DatosTitular	Bloc de dades corresponent al titular del vehicle.
//DatosTitular/TipoDocumentacion	Tipus de documentació.
//DatosTitular/Documentacion	Documentació.
//DatosTitular/NombreCompleto	Nom complert.
//DatosTitular/Nombre	Nom.
//DatosTitular/Apellido1	Primer cognom.
//DatosTitular/Apellido2	Segon cognom.
respostaSancionsConductor/resposta/ DatosConductor	Bloc de dades corresponent a les dades del conductor.
//DatosConductor/FechaNacimiento	Data de naixement.
//DatosConductor/Sexo	V (home) / M (dona)
//DatosConductor/Indicadores	Bloc de dades corresponent als indicadors del conductor consultat.
//Indicadores/AutorizadoMercanciasPeligrosas	Indica si el conductor està autoritzat per transportar mercaderies perilloses.
//Indicadores/CondicionRestrictiva	Indica si el conductor té alguna condició restrictiva que l'incapacita per conduir llevat de fer-ho amb adaptacions, restriccions o limitacions.
//Indicadores/DireccionElectronicaVial	Indica si el conductor disposa de dirección electrónica vial.
//Indicadores/Lentes	Indica si el conductor necessita ulleres per a la conducció.
//DatosConductor/DomicilioDGT	Bloc de dades corresponent al domicili del titular del vehicle a la DGT.
//DomicilioDGT/NombreVia	Adreça.
//DomicilioDGT/CodigoPostal	Codi postal.
 


Element	Descripció
	
//DomicilioDGT/Municipio	Municipi.
//DomicilioDGT/Provincia/Codigo	Província.
//DomicilioDGT/Provincia/Nombre	
//DomicilioDGT/Localidad	Localitat.
//DatosConductor/ListaIncidencias/Incidencia	Bloc de dades corresponent a una incidència del conductor consultat.
//Incidencia/Anotacion	Descripció del motiu de la incidència.
//Incidencia/Documento	Documentació associada a la incidència.
//Incidencia/Fecha	Data de la incidència (AAAA-MM-DD).
//Incidencia/Jefatura/Codigo	Prefectura.
//Incidencia/Jefatura/Descripcion	
//Incidencia/Sucursal/Codigo	Sucursal.
//Incidencia/Sucursal/Descripcion	
//Incidencia/Tipo/Codigo	Tipus d’incidència.
//Incidencia/Tipo/Descripcion	
//DatosConductor/ListaPermisosVigentes
/Permiso	Bloc de dades corresponent a un permís de conduir del titular.
//Permiso/TipoPermiso/Codigo	Tipus de permís.
//Permiso/TipoPermiso/Descripcion	
//Permiso/FechaInicio	Data d’inici del permís.
//Permiso/FechaFin	Data de fi del permís.
//DatosConductor/ListaSanciones/Sancion	Bloc de dades corresponent a una sanció.
//Sancion/AutoridadSancionadora/Codigo	Autoritat sancionadora.
//Sancion/AutoridadSancionadora/Descripcion	
//Sancion/Expediente	Expedient.
//Sancion/Fecha	Data de la sanció.
//Sancion/FechaFin	Data de finalització de la validesa de la sanció.
//Sancion/TipoSancion/Codigo	Tipus de sanció.
//Sancion/TipoSancion/Descripcion	
respostaSancionsConductor/resultat/ codiResultat	Codi de resultat de la consulta:
•	0: consulta realitzada correctament.
•	1: sense antecedents.
 


Element	Descripció
	•	2: sense permisos vigents.
•	0502: error realitzant la consulta.
respostaSancionsConductor/resultat/ descripcio	Descripció del resultat.



 


3.6	Consulta	de	vehicles	d’un	conductor (DGT_VEHICLES_CONDUCTOR)
Consulta dels vehicles enregistrats a la DGT per a un propietari.


3.6.1	Petició – dades genèriques


Element	Descripció
//DatosGenericos/Titular/TipoDocumentacion	Tipus de documentació (NIF o NIE).
//DatosGenericos/Titular/Documentacion	Documentació.

3.6.2	Resposta – dades específiques





Element	Descripció
respostaVehiclesConductor/resposta/ DatosTitular	Bloc de dades corresponent a les dades del titular.
//DatosTitular	Bloc de dades corresponent al titular del vehicle.
//DatosTitular/TipoDocumentacion	Tipus de documentació.
//DatosTitular/Documentacion	Documentació.
//DatosTitular/NombreCompleto	Nom complert.
//DatosTitular/Nombre	Nom.
//DatosTitular/Apellido1	Primer cognom.
//DatosTitular/Apellido2	Segon cognom.
respostaVehiclesConductor/resposta
/ListaVehiculos/Vehiculo/Matricula	Matrícula. Únicament es retornaran els primers 499 resultats trobats però pot ser que el titular consultat tingui mes vehicles al seu nom.
respostaVehiclesConductor/resultat/ codiResultat	Codi de resultat de la consulta:
•	0: consten vehicles a nom del titular.
 


Element	Descripció
	•	1: sense antecedents.
•	2: no consten vehicles a nom de l’interessat.
•	0502: error realitzant la consulta.
respostavehiclesConductor/resultat/ descripcio	Descripció del resultat.

