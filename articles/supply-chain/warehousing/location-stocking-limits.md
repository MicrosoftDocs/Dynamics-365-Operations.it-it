---
title: Limiti stoccaggio ubicazione
description: Questo argomento descrive la funzionalità per i limiti di stoccaggio dell'ubicazione.
author: perlynne
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e0adb9d05f0db9bbfe6bfbe72564a4e5e839f163
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004578"
---
# <a name="location-stocking-limits"></a>Limiti stoccaggio ubicazione

[!include [banner](../includes/banner.md)]

Usare la pagina **Limiti di stoccaggio ubicazione** (**Gestione magazzino \> Impostazione \> Magazzino \> Limiti di stoccaggio ubicazione**) per controllare la capacità di carico nelle ubicazioni di magazzino senza dover utilizzare i processi più avanzati per i calcoli volumetrici dei prodotti fisici.

Lo scopo dei limiti di stoccaggio delle ubicazioni è valutare la quantità massima che un'ubicazione può contenere. È possibile impostare la funzione su uno qualsiasi dei tre livelli, ognuno dei quali ha la propria scheda nella pagina **Limiti di stoccaggio ubicazione**:

- Prodotti
- Varianti prodotto
- Tipi di contenitore

Per ogni livello è possibile definire diversi valori di campo. Il sistema valuterà quindi la capacità di una ubicazione specifica, in base ai valori **Quantità** e **Unità** per ogni riga. Selezionerà prima il record di corrispondenza più dettagliato. Ad esempio, una riga che ha un valore nel campo **ID profilo ubicazione** verrà valutato prima di una riga che ha un valore solo nel campo **Magazzino**. Sarà valutata anche la capacità residua, sulla base del valore **Quantità** per il record del limite di stoccaggio dell'ubicazione utilizzato.

Nella sezione **Prodotti** della pagina, è possibile definire i seguenti valori di campo per la ricerca dei limiti di stoccaggio dell'ubicazione:

- Magazzino
- ID profilo ubicazione
- Posizione
- ID categoria dimensioni collo
- Numero articolo
- Unità

> [!NOTE]
> Non è necessario definire un valore **Unità** per ogni record del limite di stoccaggio dell'ubicazione. I calcoli della capacità di ubicazione saranno basati sulle quantità di unità di inventario. Se non viene definita alcuna conversione di unità per un valore utilizzato, il record del limite di stoccaggio dell'ubicazione verrà ignorato, come se un altro valore **Numero articolo** fosse definito per esso.

## <a name="example--purchase-order-receiving"></a>Esempio di ricevimento riga ordine acquisto

Questo esempio si basa su un set di dati dimostrativi *USMF* vuoto dove i seguenti valori sono impostati nella scheda **Varianti di prodotto** della pagina **Limiti di stoccaggio ubicazione**.

| Magazzino | ID profilo ubicazione | Numero articolo | Dimensioni | Quantità | Unità |
|-----------|---------------------|-------------|------|----------|------|
| 24        | FLOOR               | D0013       | L    | 300      | Cadauno   |
| 24        | FLOOR               | D0013       | L    | 240      | Cadauno   |
| 24        | FLOOR               | D0013       | D    | 360      | Cadauno   |

Varianti di prodotto per unità di misura diverse sono impostate per i prodotti. Queste varianti sono allineate con i limiti di stoccaggio dell'ubicazione per tre pallet (PL):

- **Taglia M:** 1 PL = 100 ciascuno (Cadauno)
- **Taglia L:** 1 PL = 80 Cadauno
- **Taglia S:** 1 PL = 120 Cadauno

Pertanto, ogni ubicazione in cui il valore **ID profilo ubicazione** è impostato su *FLOOR* può trasportare *3* *PL* del numero di articolo *D0013*.

### <a name="prepare-for-the-example"></a>Prepararazione per l'esempio

In questo esempio, verrà eseguito un flusso di ricezione dell'ordine fornitore per due righe. Tuttavia, è necessario prima aggiornare i dati della demo nel modo seguente per assicurarsi che le ubicazioni consentano il trasporto di articoli misti, solo le ubicazioni vuote da *FL-002* a *FL-004* vengono utilizzate e non sono presenti lavori in entrata aperti.

1. Per l'ubicazione *FL-001*, modificare il valore del campo **Profilo di ubicazione** da *FLOOR* a *FLOOR-05*.
1. Per il profilo di ubicazione *FLOOR* impostare l'opzione **Consenti articoli misti** su *Sì*.
1. Creare un ordine fornitore con le seguenti due righe.

    | Magazzino | Numero articolo | Dimensioni | Quantità | Unità |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | D    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Eseguire l'esempio

Si riceve prima una quantità di *4* unità *PL* nella taglia *S* e rivedere le ubicazioni della riga di stoccaggio per il lavoro creato. Si riceve poi una quantità di *4* unità *PL* nella taglia *L* e rivedere le ubicazioni della riga di stoccaggio per il lavoro creato.

1. Nell'app del magazzino accedere utilizzando *24* come ID utente e *1* come password.
1. Selezionare **In entrata** \> **Entrata acquisto**.
1. Ricevere *4* *PL* del numero di articolo *D0013* nella taglia *S*.
1. Rivedere il lavoro di stoccaggio che è stato creato. Si dovrebbero vedere i seguenti risultati:

    - 3 PL -\> FL-002
    - 1 PL -\> FL-003

1. Ricevere *4* *PL* del numero di articolo *D0013* nella taglia *L*.
1. Rivedere il lavoro di stoccaggio che è stato creato. Si dovrebbero vedere i seguenti risultati:

    - 1 PL -\> FL-003
    - 3 PL -\> FL-004

In base ai risultati, si potrebbe concludere che il sistema non è riuscito ad allocare le ubicazioni di stoccaggio corrette. Altrimenti, perché il sistema ha aggiunto solo *1* *PL* di taglia *L* all'ubicazione *FL-003* nell'ultimo passaggio e no *2* *PL*? Cioè, perché non c'è un totale di *3* *PL* per lo stoccaggio in quella ubicazione?

Per spiegare questo apparente fallimento, è necessario comprendere i criteri di selezione per i limiti di stoccaggio dell'ubicazione. Il sistema seleziona il record di corrispondenza più dettagliato. In questo esempio, il record di corrispondenza più dettagliato è la riga in cui il valore **Taglia** è *L*, il valore **Quantità** è *240* e il valore **Unità** è *Cadauno*. Perché è già presente un lavoro aperto dal precedente ricevimento di una quantità di *120* *Cadauno* di taglia *S*, la capacità rimanente viene calcolata come *240* - *120* = *120* *Ea*. Pertanto, la capacità rimanente può trasportare solo *1* *PL* di *80* *Cadauno*.

> [!NOTE]
> Non è possibile utilizzare i limiti di stoccaggio dell'ubicazione per controllare, ad esempio, il rifornimento di articoli con quantità diverse nella stessa ubicazione. In questo caso, usare un *modello di rifornimento*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]