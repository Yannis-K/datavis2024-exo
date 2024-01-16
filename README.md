# datavis2024-exo

Cette exercice utilise la requête suivante (générer via wikidata) : 

#defaultView:Timeline
SELECT ?pièce_de_théâtre ?pièce_de_théâtreLabel ?date_de_la_première_représentation ?image WHERE {
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
  ?pièce_de_théâtre wdt:P7937 wd:Q25379.
  OPTIONAL { ?pièce_de_théâtre wdt:P1476 ?titre. }
  OPTIONAL { ?pièce_de_théâtre wdt:P577 ?date_de_la_première_représentation. }
  OPTIONAL { ?pièce_de_théâtre wdt:P18 ?image. }
  ?pièce_de_théâtre wdt:P50 wd:Q687.
  FILTER EXISTS {?pièce_de_théâtre wdt:P18 [] }
  
}
LIMIT 100
