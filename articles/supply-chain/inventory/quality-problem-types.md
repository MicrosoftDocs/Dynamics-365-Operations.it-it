---
title: Tipi di problemi per non conformità
description: Questo argomento descrive come creare e utilizzare i tipi di problemi per le non conformità.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26705dd12f478f4ca6046c7265d4ae3cb1d08c69
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568809"
---
# <a name="problem-types-for-nonconformances"></a>Tipi di problemi per non conformità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come creare e utilizzare i tipi di problemi per le non conformità.

Utilizzare la pagina **Tipi di problemi** per definire una classificazione dei problemi relativi alla qualità che possono verificarsi per i vari tipi di non conformità. Per ogni tipo di problema creato, è necessario specificare i tipi di non conformità con cui può essere utilizzato il tipo di problema. È possibile impostare i seguenti tipi di non conformità:

- **Interno** - Le non conformità di questo tipo sono correlate alle scorte disponibili (ad esempio, ordini di controllo qualità o ordini di quarantena).
- **Cliente** - Non conformità di questo tipo sono correlate agli ordini cliente.
- **Fornitore** - Non conformità di questo tipo sono correlate agli ordini fornitore.
- **Richiesta di assistenza** - Non conformità di questo tipo sono correlate agli ordini di assistenza.
- **Produzione** - Non conformità di questo tipo sono correlate agli ordini batch o di produzione.
- **Produzione co-prodotti** - Non conformità di questo tipo sono correlate agli ordini batch per co-prodotti.

Quando crei un nuovo tipo di problema, seleziona **Tipi di non conformità** nel riquadro azioni per creare un elenco di uno o più tipi di non conformità autorizzati per il tipo di problema. Un tipo di problema riguardante un codice di articolo difettoso potrebbe ad esempio essere applicato a tutti i tipi di non conformità. Tuttavia, un tipo di problema correlato ai reclami dei clienti potrebbe applicarsi solo ai tipi di non conformità **Cliente** e **Richiesta di assistenza**.

## <a name="examples-of-problem-types"></a>Esempi di tipi di problemi:

Di seguito sono riportati alcuni esempi di scenari per i tipi di problemi che possono essere utilizzati con i diversi tipi di non conformità:

- **Cliente:** Un cliente ha presentato un reclamo, un cliente ha effettuato un reso o le specifiche di qualità non sono state soddisfatte.
- **Fornitore:** Il prodotto è stato danneggiato, le specifiche di qualità non sono state soddisfatte o è stato ricevuto il prodotto sbagliato.
- **Richiesta di assistenza:** Le specifiche di qualità non sono state soddisfatte, un cliente ha presentato un reclamo o è necessaria la manutenzione di una macchina.
- **Produzione:** Le specifiche di qualità non sono state soddisfatte, è necessaria la manutenzione della macchina o il prodotto è stato danneggiato.
- **Produzione co-prodotti:** Le specifiche di qualità non sono state soddisfatte, è necessaria la manutenzione della macchina o il prodotto è stato danneggiato.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Creare un tipo di problema e assegnarlo ai tipi di non conformità

1. Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Tipi di problema**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Tipo di problema** - Immettere un ID o un nome univoco per il tipo di problema.
    - **Descrizione** - Immettere una descrizione dettagliata del tipo di problema.

1. Mentre la nuova riga è ancora selezionata, seleziona **Tipi di non conformità** nel riquadro azioni.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi, per la nuova riga, imposta il campo **Tipo di non conformità** sul tipo di non conformità che si desidera consentire per il tipo di problema.
1. Ripetere il passaggio precedente per ogni tipo di non conformità aggiuntivo che si desidera autorizzare per il tipo di problema.
1. Chiudere le pagine.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Lavoratori responsabili dell'approvazione delle non conformità](quality-responsible-workers.md)
- [Aree di quarantena per non conformità](quality-quarantine-zones.md)
- [Tipi di diagnostica per non conformità](quality-diagnostic-types.md)
- [Spese di gestione qualità per non conformità](quality-charges.md)
- [Operazioni per non conformità](quality-operations.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
