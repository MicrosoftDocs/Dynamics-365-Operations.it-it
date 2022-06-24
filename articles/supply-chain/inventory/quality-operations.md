---
title: Operazioni per non conformità
description: Questo articolo descrive come creare e utilizzare le operazioni per le non conformità.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2e63156dd2b230da7f1ea89e2c2006c1b4f3eeb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847993"
---
# <a name="operations-for-nonconformances"></a>Operazioni per non conformità

[!include [banner](../includes/banner.md)]

Questo articolo descrive come creare e utilizzare le operazioni per le non conformità.

Puoi Utilizzare la pagina **Operazioni** per definire classificazioni del lavoro che è possibile eseguire per una non conformità approvata. Quando si assegna un'operazione correlata a una non conformità, è possibile fornire informazioni dettagliate, ad esempio sul materiale associato, sulle ore di manodopera e sulle spese varie, necessarie per l'esecuzione dell'operazione. Queste informazioni vengono utilizzate dal sistema per calcolare un costo stimato per l'operazione. Le informazioni dettagliate e i costi stimati vengono forniti a scopo di riferimento. Le operazioni correlate del controllo qualità sono diverse da quelle che è possibile definire per un ciclo di lavorazione produzione.

> [!NOTE]
> Sebbene sia possibile tenere traccia dei costi, del tempo e degli articoli utilizzati in un'operazione correlata a una non conformità, i dati immessi sono solo informativi. Non vengono integrati automaticamente con la contabilità generale, la contabilità secondaria di magazzino o il modulo **Orario e presenze**.

## <a name="examples-of-operations"></a>Esempi di operazioni

Lavori per un'azienda manifatturiera. È stata creata e approvata una non conformità per gli articoli che non hanno superato un test di controllo qualità. È stata creata una correzione per indicare che il problema era correlato a un cuscinetto difettoso su una macchina. Sono necessari diversi passaggi per sostituire il cuscinetto e la responsabilità di ciascuna operazione viene monitorata. Ad esempio, potrebbero essere necessari i seguenti passaggi:

1. La linea di produzione viene arrestata e viene eseguita la routine di pulizia.
1. Il personale di manutenzione sostituisce il cuscinetto.
1. Il personale addetto al controllo qualità ispeziona la macchina prima che venga riaccesa.

Per questo esempio, possono essere create le seguenti operazioni per rappresentare il lavoro che deve essere fatto:

- Fermare la linea di produzione.
- Pulisci la linea di produzione.
- Effettuare la manutenzione della macchina.
- Ispeziona la macchina.

## <a name="create-an-operation"></a>Creare un'operazione

1. Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Operazioni**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Operazione** – Immetti un ID o nome univoco per l'operazione.
    - **Descrizione** - Immettere una descrizione dettagliata della operazione.
    - **Tipo** - Se l'operazione può essere utilizzata solo con non conformità correlate a un tipo specifico di ordine, selezionare il tipo di ordine (*Ordine fornitore* o *Ordine cliente*).

1. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Creare ed elaborare non conformità](tasks/create-process-non-conformance.md)
- [Lavoratori responsabili dell'approvazione delle non conformità](quality-responsible-workers.md)
- [Aree di quarantena per non conformità](quality-quarantine-zones.md)
- [Tipi di diagnostica per non conformità](quality-diagnostic-types.md)
- [Spese di gestione qualità per non conformità](quality-charges.md)
- [Tipi di problemi per non conformità](quality-operations.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
