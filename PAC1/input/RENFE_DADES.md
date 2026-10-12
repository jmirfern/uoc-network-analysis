# Dades i resultats de Renfe — exercici 4.1

Descàrrega: **12/10/2026**. El notebook utilitza la còpia local del GTFS i no torna a descarregar-la quan s'executa la cel·la 48.

Font: [Renfe Data — Horarios de alta velocidad, larga distancia y media distancia](https://data.renfe.com/dataset/horarios-de-alta-velocidad-larga-distancia-y-media-distancia). Llicència **Creative Commons Attribution 4.0**. El catàleg indica que aquest conjunt exclou Cercanías i FEVE.

- `renfe_google_transit.zip`: arxiu original descarregat del recurs oficial.
- `agency.txt`, `routes.txt`, `trips.txt`, `stops.txt`, `stop_times.txt`, `calendar.txt` i `calendar_dates.txt`: fitxers originals extrets.
- `renfe_metadades_ckan.json`: resposta del catàleg CKAN de Renfe.
- `renfe_procedencia.json`: URLs, data de descàrrega i SHA-256 de l'arxiu original.
- `renfe_dataset.html`: pàgina del conjunt de dades.
- `gtfs_schedule_reference.html`: còpia de la [referència oficial GTFS](https://gtfs.org/documentation/schedule/reference/).
- `natural_earth_50m_countries.geojson`: fons cartogràfic de països de Natural Earth, de domini públic.

## Criteri de construcció

Els nodes són els `stop_id` de `stops.txt`. Aquest feed no té agrupacions `parent_station`; tots els nodes tenen coordenades vàlides i apareixen als trajectes. Els identificadors es llegeixen com a text, conservant zeros inicials. Es netegen els espais al final de les capçaleres i dels valors.

Es processen les files de `stop_times.txt` per `trip_id` i per `stop_sequence` numèric. Cada parada es connecta amb la següent del mateix trajecte. Els números de seqüència no han de ser consecutius. Les parelles es consideren no dirigides i el pes compta els **trip_id diferents** que fan cada connexió, com a màxim una vegada per trajecte i parella.

No s'aplica cap data de servei ni es multipliquen els trajectes pels dies del calendari. El pes no representa freqüència diària, passatgers, distància ni temps. Els calendaris de la còpia descarregada abasten del **2026-10-11 al 2027-09-29**; això no implica servei diari de totes les connexions.

## Resultats verificats

**1.006 nodes, 1.422 connexions i 9.043 trip_id**, amb una sola component connexa i cap node aïllat. Els pesos van d'1 a 605. S'han comprovat la integritat del ZIP, les claus, els identificadors referenciats, les coordenades i la concordança dels pesos amb els trajectes.

- `renfe_xarxa_geografica.png` i `renfe_xarxa_geografica.svg`: figura amb coordenades geogràfiques i detalls de Madrid i Barcelona.
- `renfe_mapa_interactiu.html`: mapa amb zoom, capes i informació de totes les estacions i connexions. Necessita Internet per carregar Leaflet i les tessel·les d'OpenStreetMap; la figura PNG/SVG utilitza un fons cartogràfic local.
- `renfe_xarxa.graphml`: graf amb noms, latituds, longituds i pesos.
- `renfe_arestes.csv` i `renfe_estacions.csv`: taules exportades.

Les línies del mapa uneixen parades consecutives dels serveis i poden saltar estacions on el tren no s'atura. **No són el traçat físic exacte de les vies**. La figura estàtica utilitza longitud/latitud amb una correcció aproximada de l'aspecte al paral·lel central; no s'ha de fer servir per mesurar distàncies amb precisió.

La cel·la 48 inclou les referències i la declaració d'ús de GPT en el format del notebook. Folium s'utilitza per afegir zoom i informació emergent; el graf es construeix amb pandas i NetworkX. `G_renfe` queda disponible per a l'exercici 4.2.
