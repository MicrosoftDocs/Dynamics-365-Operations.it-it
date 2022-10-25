---
title: Dashboard della soluzione Invoice Capture
description: Questo articolo descrive la dashboard della soluzione Invoice Capture.
author: sunfzam
ms.date: 10/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690122"
---
# <a name="invoice-capture-solution-dashboard"></a>Dashboard della soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In Invoice Capture, la dashboard include grafici che forniscono una panoramica delle fatture che sono state importate. Questi grafici possono aiutare il responsabile della contabilità fornitori (AP) ad analizzare le prestazioni del processo di generazione delle fatture. Il responsabile della contabilità fornitori può visualizzare lo stato del processo di generazione della fattura e, applicando diversi filtri, può anche visualizzare i dettagli.

## <a name="available-charts"></a>Grafici disponibili

I seguenti grafici sono disponibili nella dashboard:

- **Tutte le fatture acquisite in base allo stato** – Questo grafico mostra i seguenti stati per una fattura acquisita. Selezionando uno stato, gli utenti possono filtrare le fatture acquisite nell'elenco dettagliato.

    - Acquisito
    - Completa
    - In revisione
    - Obsoleto

- **Volume totale fatture acquisite** – Questo grafico mostra il numero di fatture acquisite per periodo. Gli utenti possono modificare il periodo utilizzando l'elenco a discesa.
- **Fatture acquisite dai fornitori principali** – Questo grafico mostra il numero totale di fatture acquisite per fornitore. In alto vengono visualizzati i fornitori che hanno il maggior numero di fatture.
- **Giorni per il completamento per fattura con eccezioni** – Questo grafico mostra il numero medio di giorni necessari per acquisire una fattura. Queste informazioni possono aiutare il responsabile della contabilità fornitori ad analizzare il tempo necessario per elaborare una fattura quando è richiesto un intervento manuale. Se c'è una tendenza al rialzo, gli utenti possono rivedere i dettagli del processo e regolare le impostazioni per ridurre il numero di giorni necessari.
- **Fatture incomplete per ora in sospeso** – Questo grafico mostra il numero di giorni in cui una fattura acquisita non è stata generata nel sistema ERP (Enterprise Resource Planning). Maggiore è il numero di giorni in sospeso, più lungo sarà il processo di generazione della fattura. Il responsabile della contabilità fornitori può approfondire le fatture acquisite dettagliate e generare fatture nel sistema ERP.
