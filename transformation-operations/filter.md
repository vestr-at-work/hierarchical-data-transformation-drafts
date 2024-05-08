# Filter operace

Tato operace slouží k jednoduchému filtrování hodnot. Operace se zapisuje jako pole objektů s klíči "path" a "predicate". Klíč "path" uchovává cestu ke filtrovanému klíči ve vstupní entitě a klíč "predicate" uchovává podmínku (predikát), kterou musí hodnota filtrovaného klíče splňovat, aby se ocitla na výstupu. Výstup operace je tedy entita s všemi klíči a hodnotami, které splňují podmínky predikátů a nebo nebyly v operaci nijak zmíněny.

Predikáty jsou dvojího typu. Buďto se vztahují k samotné hodnotě a nebo k jejímu typu. Značí se (ne náhodou) stejně jako v Unifikované reprezentaci "@value" respektive "@type". V zápisu predikátu po nich vždy následuje znaménko >, >=, <, <=, == (pouze některá jsou validní u určitých typů, např. typ boolean podporuje jen ==). Na pravé straně znaménka je potom samotná hodnota vůči které porovnáváme.

Základní filter operace může vypadat například takto.

```json
{
    "operation": "filter",
    "comment": "Filtrování literálu podle hodnoty",
    "specs": [
        {
            "path": "/person/name",
            "predicate": "@value == Ailish"
        }
    ]
}
```

Predikát se nemusí vyskytovat jen u literálu. Porovnávat hodnotu u jiných než literálních hodnot, ale povoleno není.

```json
{
    "operation": "filter",
    "comment": "Filtrování s porovnáním typu entity u neliterálu",
    "specs": [
        {
            "path": "/person",
            "predicate": "@type == object"
        }
    ]
}
```

Operace filter také podporuje pojmenované proměnné.

```json
{
    "operation": "filter",
    "comment": "Filtrování s porovnáním typu entity u literálu a využitím pojmenované proměnné",
    "specs": [
        {
            "path": "/var:named-entity:/name",
            "predicate": "@type == string"
        }
    ]
}
```

Nápady: Umožnit uživatelstvu, aby mohlo nějakým způsobem řetězit víc predikátů s jednou cestou. Nějak podporovat AND a OR.
