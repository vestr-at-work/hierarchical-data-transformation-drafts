# Remove operace

Tato operace slouží k odstranění klíčů a jejich hodnot (ať už literálů, či celých objektů). Zapisuje se jako pole objektů s klíčem "path" držící cestu ke klíči k odstranění ve vstupní entitě. Výstupem je tedy vstupní entita bez všech klíčů (a jejich hodnot) zmíněných v operaci. Když se odstraní poslední klíč z objektu, tak na výstupu objekt zůstává (jen je prázdný).

Základní remove operace může vypadat třeba takto.

```json
{
    "operation": "remove",
    "comment": "Odstraň klíč name v objektu person",
    "specs": [
        {
            "path": "/person/name"
        }
    ]
}
```

Operace remove jako ostatní základní operace podporuje pojmenované proměnné.

```json
{
    "operation": "remove",
    "comment": "Odstraň klíč name v jakémkoli objektu splňujícím cestu",
    "specs": [
        {
            "path": "/var:named-entity:/name"
        }
    ]
}
```
