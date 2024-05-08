# Default operace

Tato operace slouží k nastavení výchozích hodnot pro nové klíče. Pokud ve vstupní entitě už hodnota pro tento klíč existuje nic se nenastavuje. Operace je pole objektů s klíči "path" a "value". "path" obsahuje cestu ke klíči, kterému chce uživatel nastavit hodnotu "value". Výstupem operace je tedy vstupní entita rozšířená o výchozí hodnoty nastavené při operaci.

Základní default operace může vypadat třeba takto.

```json
{
    "operation": "default",
    "comment": "Nastav výchozí hodnotu pro klíč name v objektu person",
    "specs": [
        {
            "path": "/person/name",
            "value": "Bilish"
        }
    ]
}
```

Samozřejmě operace také podporuje pojmenovanné proměnné.

```json
{
    "operation": "default",
    "comment": "Nastav výchozí hodnotu pro klíč name v jakémkoli objektu (splňujícím cestu)",
    "specs": [
        {
            "path": "/@var:named-entity:/name",
            "value": "Bilish"
        }
    ]
}
```

A i využívání hodnot proměnných ve "value" klíči.

```json
{
    "operation": "default",
    "comment": "Nastav výchozí hodnotu pro klíč name v jakémkoli objektu (splňujícím cestu)",
    "specs": [
        {
            "path": "/@var:named-entity:/name",
            "value": "var:named-entity:"
        }
    ]
}
```
