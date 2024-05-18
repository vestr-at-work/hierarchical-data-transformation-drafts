# Unified representation path neboli UrPath

Operace našeho transformačního nástroje potřebují často ukazovat na entity Unifikované reprezentace nebo nové entity v Ur tvořit. A přesně k tomu slouží UrPath, kterou představíme v této části. Hodně zjednodušeně si můžeme UrPath představit jako JSONPointer upravený tak, aby mohl "ukazovat" i do neexistujících (právě tvořených) entit.  

Stejně jako JSONPointer, každá validní UrPath musí začínat dopředným lomítkem. Jedno dopředné lomítko ukazuje na celou kořenovou entitu Ur. Dopředná lomítka symbolizují postup do dětské entity Unifikované reprezentace (v její JSON reprezentaci se prakticky jedná o vstup do prvního objektu v poli). Po lomítku může následovat buďto klíč objektu nebo otevírajicí a zavírající hranatá závorka potenciálně s číslem těsně mezi nimi. Závorky ukazují, že se jedná o pole a číslo mezi nimi je index do tohoto pole. Prázdné závorky ukazují na prvek těsně po posledním prvku pole a používají se jen ve výstupních cestách při tvoření nových polí. V případě použití prázdných závorek ve vstupní cestě se jedná vždy o chybu, neboť prvek po posledním prvku pole neexistuje.

Pro příklady budeme využívat Ur JSON dokumentu používaném u předvedení operací.

```json
{
    "@type": ["object"],
    "person": [{
        "@type": ["object"],
        "name": [{
            "@type": ["string"],
            "@value": ["Ailish"]
        }]
    }]
}
```

TODO