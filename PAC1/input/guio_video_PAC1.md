# Guió PAC1

Pauta d’assaig ajustada a les instruccions de la cel·la 59. Durada objectiu: 2 min 25 s, amb 5 s de marge. Cada exercici disposa de 30 s. Els temps inclouen els canvis de pantalla; cal comprovar-los assajant amb cronòmetre.

## 0:00–0:10 · Presentació

*Mostra el notebook obert, amb totes les sortides ja calculades.*

«En aquesta pràctica he caracteritzat xarxes reals i he comprovat què poden explicar els models sintètics.»

## 0:10–0:40 · Exercici 1: xarxa real i models nuls

*Mostra la figura de comparació dels models nuls i assenyala el clustering de la xarxa real i del model amb graus fixats.*

«He comparat una xarxa d’interaccions amb dos models nuls: un conserva nodes i arestes, i l’altre també els graus. El clustering passa de 0,50 a aproximadament 0,14 amb graus fixats. Per tant, els graus no expliquen tot l’agrupament. A més, eliminar prop del cinc per cent dels nodes no ha fragmentat la xarxa en els experiments realitzats.»

## 0:40–1:10 · Exercici 2: Watts–Strogatz

*Mostra una única figura: el mapa de paràmetres del 2.2. Assenyala els punts compatibles amb k=10.*

«Amb deu veïns inicials, els valors mostrejats de beta entre 0,06 i 0,10 són compatibles amb la xarxa segons el criteri definit. El mapa mostra que combinen bé clustering i longitud mitjana dels camins. No he identificat un beta únic: diferents paràmetres poden donar distàncies semblants, i cal combinar mètriques.»

## 1:10–1:40 · Exercici 3: Barabási–Albert generalitzat

*Mostra una única taula: la comparació del 3.3. Assenyala alfa=0,5, les mètriques comparades i l’error E=0,1322.*

«En Barabási–Albert generalitzat, alfa igual a 0,5 és el millor dels cinc valors provats. Reprodueix millor conjuntament el grau màxim, l’heterogeneïtat i el clustering, amb un error relatiu mitjà del tretze per cent. Això suggereix una preferència pels nodes connectats més suau que en el model clàssic, però no demostra que l’alfa real sigui exactament aquest.»

## 1:40–2:10 · Exercici 4: xarxa de Renfe

*Mostra primer el mapa geogràfic mentre expliques la construcció; passa a la distribució de graus quan comentis el 65 %.*

«Per a Renfe, he connectat parades consecutives i he comptat els trajectes diferents com a pes de cada connexió. La distribució mostra que un seixanta-cinc per cent de les estacions tenen dos veïns, coherent amb corredors ferroviaris. El model de graus fixats conserva aquesta distribució, però no la geografia, el clustering ni les distàncies.»

## 2:10–2:25 · Aprenentatge global

*Mantén l’última gràfica a la pantalla.*

«He après que cal combinar mètriques, repetir simulacions i interpretar cada resultat segons les hipòtesis i les limitacions del model.»

## Recordatoris per a l’assaig

- L’enunciat demana una única presa, amb l’estudiant i la pantalla visibles. El guió és una pauta per preparar les idees: no es pot llegir durant l’enregistrament.
- Els models nuls no garanteixen conservar la connexitat. En aquestes realitzacions s’ha mantingut; les condicions imposades són els nodes i les arestes, i també els graus en el segon model.
- Els beta indicats són punts mostrejats compatibles segons el criteri del 2.2, no un interval de confiança ni tots els valors d’un interval continu.
- L’error del tretze per cent resumeix les desviacions relatives de les mètriques triades; no és una probabilitat ni un percentatge de nodes diferents.
- Assaja les xifres i prepara les sortides per no haver de buscar-les o executar codi durant el vídeo.
