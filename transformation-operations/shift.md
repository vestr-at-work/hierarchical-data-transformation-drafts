# Shift operace

Tato operace se využívá pro posun konkrétních hodnot nebo celých podstromů na výstup. Skládá se z pole objektů, které mají klíče "input-path" a klíč "output-path". "input-path" obsahuje JSONPointer k hodnotě na vstupu a "output-path" obsahuje buďto cestu nebo pole cest ve výstupním objektu do kterých se posune vstupní entita. Nezmíněné entity se na výstup nekopírují.

Základní shift operace může vypadat následovně.

```json
{
    "operation": "shift",
    "comment": "Posuň hodnotu name z objektu person do objektu human",
    "specs": [
        {
            "input-path": "/person/name",
            "output-path": "/human/name"
        }
    ]
}
```

Výstup operace:

```json
{
    "human": {
        "name": "Ailish"
    }
}
```

---

Pro vložení entit na konec pole se v cestě využívá symbol "[]".

```json
{
    "operation": "shift",
    "comment": "Posuň hodnotu name z objektu person do pole names v objektu human",
    "specs": [
        {
            "input-path": "/person/name",
            "output-path": "/human/names/[]"
        }
    ]
}
```

Výstup operace:

```json
{
    "human": {
        "names": ["Ailish"]
    }
}
```

---

Skutečná síla operace se projeví až po využití pojmenovaných proměnných. Ty se automaticky nahradí jakýmkoli klíčem pro který bude po nahrazení cesta do vstupní entity platná.

```json
{
    "operation": "shift",
    "comment": "Posuň hodnotu name z jakéhokoli objektu do pole names v objektu entity",
    "specs": [
        {
            "input-path": "/@var:named-entity:/name",
            "output-path": "/entity/names/[]"
        }
    ]
}
```

Výstup operace:

```json
{
    "entity": {
        "names": ["Ailish"]
    }
}
```

---

Následně lze také hodnota nahrazené proměnné využít i v cestách ve výstupní entitě.

```json
{
    "operation": "shift",
    "comment": "Posuň hodnotu name z jakéhokoli objektu do objektu stejného jména a klíče called",
    "specs": [
        {
            "input-path": "/@var:named-entity:/name",
            "output-path": "/@var:named-entity:/called"
        }
    ]
}
```

Výstup operace:

```json
{
    "human": {
        "called": "Ailish"
    }
}
```

---

A to i dokonce jen jako část klíče. Části před a po @var:jmeno-promenne: budou přeneseny na výstup.

```json
{
    "operation": "shift",
    "comment": "Posuň hodnotu name z jakéhokoli objektu do objektu stejného jména s předponou named- a klíče called",
    "specs": [
        {
            "input-path": "/@var:named-entity:/name",
            "output-path": "/named-@var:named-entity:/called"
        }
    ]
}
```

Výstup operace:

```json
{
    "named-person": {
        "called": "Ailish"
    }
}
```

---
