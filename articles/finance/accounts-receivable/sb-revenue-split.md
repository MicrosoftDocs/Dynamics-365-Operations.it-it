---
title: Modelli di suddivisione ricavi in Fatturazione abbonamento
description: Questo argomento spiega come impostare i modelli di suddivisione ricavi per gli articoli venduti in aggregazioni.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 5c2eb6c8e18770eb149c445f662ab7a90aad81a7
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660455"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Modelli di suddivisione ricavi in Fatturazione abbonamento

Usa la pagina **Modello di suddivisione ricavi** per impostare i modelli per la suddivisione dei ricavi. La suddivisione dei ricavi è costituita da un articolo padre con articoli figlio. Questo tipo di articolo viene spesso venduto ai clienti come articolo singolo o aggregazione.

Ad esempio, un articolo computer può essere creato nel modo seguente:

- **Articolo padre:** Abbonamento Argento
- **Articoli figlio:**

    - Supporto
    - Gestione
    - Licenza

Quando crei un articolo padre, tieni a mente le seguenti restrizioni:

- Un articolo può essere specificato come articolo padre una sola volta.
- L'articolo padre può essere selezionato come articolo figlio nello stesso modello.
- Un modello valido richiede almeno un articolo figlio.
- Un articolo può essere specificato come articolo figlio per più di un articolo di aggregazione.
- Ogni relazione padre-figlio deve essere univoca.

## <a name="create-a-parent-item-that-has-child-items"></a>Creare un articolo padre con articoli figlio

Attieniti alla seguente procedura per creare un articolo padre con articoli figlio.

1. Sulla pagina **Modello di suddivisione ricavi** seleziona **Nuovo**.
1. Nel campo **Articolo padre** seleziona un articolo padre. Il campo **Numero variante** viene aggiornato automaticamente. Puoi modificare il valore come necessario.
1. Nel campo **Metodo di allocazione** seleziona un metodo di allocazione.
1. Nell'elenco **Articoli componenti** seleziona **Aggiungi** per aggiungere gli articoli figlio.
1. Se hai selezionato **Percentuale** nel campo **Metodo di allocazione**, specifica la percentuale nel campo **Percentuale**.

    - Se hai selezionato **Pari importo** nel campo **Metodo di allocazione**, il campo **Percentuale** viene aggiornato automaticamente in modo che ogni articolo abbia una percentuale uguale.
    - Se hai selezionato **Importo variabile**, **Importo padre a zero**, o **Importo a zero** nel campo **Metodo di allocazione**, il valore del campo **Percentuale** rimane **0** (zero) e non può essere modificato.

1. Seleziona **Salva**.

## <a name="fields"></a>Campi

La pagina **Modello di suddivisione ricavi** contiene i seguenti campi.

| Campo | Description |
|-------|-------------|
| Articolo padre | Seleziona il numero articolo. Questo articolo diventa l'articolo padre per l'articolo di aggregazione creato. |
| Nome prodotto | Il nome del prodotto. |
| Metodo di allocazione | <p>Seleziona il metodo di allocazione:</p><ul><li>**Importo uguale** – Le percentuali di allocazione vengono calcolate automaticamente e suddivise equamente tra tutti gli articoli nel modello.</li><li>**Percentuale** – Puoi specificare un importo percentuale per l'allocazione. La somma di tutte le percentuali deve essere 100.</li><li>**Importo variabile** – Gli articoli figlio aggiunti hanno un importo netto di 0 (zero). Il prezzo degli articoli figlio deve essere specificato a livello di transazione.</li><li>**Importo a zero** – L'articolo padre conserva il prezzo unitario e l'importo netto. Tutti gli articoli figlio hanno un importo netto di 0 (zero).</li><li>**Importo padre a zero** – L'articolo padre ha un importo netto fisso pari a 0 (zero). Tutti gli articoli figlio vengono trattati come articoli standard. Non viene eseguita alcuna convalida per verificare che la somma degli importi dell'articolo figlio sia uguale all'importo dell'articolo padre.</li></ul> |
| **Articoli componente** | |
| Articolo componente | Seleziona il numero articolo. Questo articolo è un articolo figlio. |
| Numero variante | Seleziona il numero di variante dell'articolo. |
| Nome prodotto | Il nome del prodotto. |
| Percentuale | <p>La percentuale di allocazione per la fase.</p><ul><li>Se il campo **Metodo di allocazione** è impostato su **Percentuale**, puoi specificare la percentuale.</li><li>Se il campo **Metodo di allocazione** è impostato su **Importo uguale**, la percentuale viene calcolata automaticamente in modo che ogni articolo nel modello abbia una percentuale uguale.</li><li>Se il campo **Metodo di allocazione** è impostato su **Importo variabile**, **Importo padre a zero**, o **Importo a zero**, la percentuale è 0 (zero) e non può essere modificata.</li></ul><p>Il valore di questo campo può essere qualsiasi numero positivo compreso tra 0 (zero) e 100. La somma di tutte le percentuali deve essere 100.</p> |
| Percentuale totale | <p>La somma dei valori della colonna **Percentuale**.</p><ul><li>Se il campo **Metodo di allocazione** è impostato su **Pari importo** o **Percentuale**, la somma di tutte le percentuali deve essere 100.</li><li>Se il campo **Metodo di allocazione** è impostato su **Importo variabile**, **Importo padre a zero**, o **Importo a zero**, la percentuale totale è 0 (zero).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Suddivisione dei ricavi in un ordine cliente

Per creare un ordine cliente con un articolo impostato per la suddivisione dei ricavi, attieniti alla seguente procedura.

1. Nella pagina **Ordine cliente**, crea un ordine cliente.
2. Nella riga di ogni articolo impostato per la suddivisione dei ricavi seleziona la casella di controllo **Suddivisione ricavi**. Quell'articolo diventa l'articolo padre. Se il modello è già impostato, gli articoli figlio vengono visualizzati automaticamente nell'elenco.
3. Per aggiungere altri articoli figlio, seleziona **Aggiungi suddivisione ricavi figlio** e seleziona l'articolo figlio che desideri aggiungere.
4. Salva l'ordine.

## <a name="revenue-split-with-billing-schedules"></a>Suddivisionen dei ricavi con i programmi di fatturazione

Per creare un programma di fatturazione con un articolo impostato per la suddivisione dei ricavi, attieniti alla seguente procedura.

1. Nella pagina **Tutti i programmi di fatturazione o Programmi di fatturazione attivi** crea un programma di fatturazione.
2. Nella riga di ogni articolo impostato per la suddivisione dei ricavi seleziona la casella di controllo **Suddivisione ricavi**. Quell'articolo diventa l'articolo padre. Se il modello è già impostato, gli articoli figlio vengono visualizzati automaticamente nell'elenco.
3. Per aggiungere altri articoli figlio, seleziona **Aggiungi suddivisione ricavi figlio** e seleziona l'articolo figlio che desideri aggiungere.
4. Continua con i passaggi per lavorare con il programma di fatturazione.

> [!NOTE]
> Se l'opzione **Crea automaticamente suddivisione ricavi** è impostata su **sì** nella pagina **Parametri di fatturazione contratto ricorrente** si verificano le seguenti azioni:
>
> - La casella di controllo **Suddivisione ricavi** è automaticamente selezionata se la voce è impostata come articolo padre nel modello di suddivisione dei ricavi.
> - Gli articoli figlio vengono inseriti automaticamente nell'ordine cliente o nella riga del programma di fatturazione.
>
> Se l'opzione **Crea automaticamente suddivisione dei ricavi** è impostata su **No**, il comportamento è come spiegato in precedenza.
