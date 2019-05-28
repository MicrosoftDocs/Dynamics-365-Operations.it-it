---
title: Flusso di lavoro delle spese
description: Questo argomento descrive come è possibile utilizzare il sistema del flusso di lavoro in Microsoft Dynamics 365 for Finance and Operations per impostare un processo di verifica delle note spese in Gestione spese.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 037a6ae00b7d559f79860901f0cb2ad6ddddd7aa
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545974"
---
# <a name="expense-workflow"></a>Flusso di lavoro delle spese

[!include [banner](../includes/banner.md)]

È possibile utilizzare il sistema del flusso di lavoro in Microsoft Dynamics 365 for Finance and Operations per impostare un processo di verifica delle note spese in Gestione spese. È possibile impostare un flusso di lavoro che utilizza i seguenti criteri per determinare il responsabile dell'approvazione delle note spese:

- Relazioni gerarchiche tra i dipendenti e limiti di approvazione predefiniti
- Approvazione multilivello che supporta gli approvatori provvisori e un approvatore finale
- Dimensioni finanziarie e responsabilità dei progetti
- Assegnazione a utenti o gruppi di utenti specifici

È possibile creare approvazioni del flusso di lavoro per note spese, richieste di viaggio, anticipo contanti e recupero dell'imposta sul valore aggiunto (IVA).

**Esempio**

Il processo riportato di seguito è un esempio di flusso di lavoro di gestione delle spese per una nota spese.

1. Un dipendente crea e salva una nota spese.
2. Il dipendente invia la nota spese per l'approvazione. L'approvatore è identificato in base alle regole definite durante l'impostazione del flusso di lavoro.
3. L'approvatore riceve una notifica che lo informa che una nota spese è pronta per l'approvazione. L'approvatore rivede la nota spese e verifica che le seguenti condizioni siano soddisfatte:

    - Le spese non violano alcun criterio di spesa. Se una spesa viola i criteri, l'approvatore verifica che nella nota spese sia inclusa una motivazione aziendale valida.
    - Le ricevute elettroniche sono allegate alla nota spese.

4. L'approvatore approva la nota spese.
5. La nota spese viene assegnata al coordinatore della contabilità fornitori per la registrazione.
6. Una delle seguenti azioni viene eseguita a seconda che la registrazione automatica è configurata o meno:

    - Se la registrazione automatica è configurata, la nota spese viene elaborata per il pagamento e il relativo stato viene aggiornato.
    - In caso contrario, il coordinatore della contabilità fornitori verifica che tutte le ricevute originali siano state inviate e che siano allineate alle spese nella nota spese. È inoltre necessario verificare che tutti i codici imposta immessi nella nota spese siano corretti.

In seguito alla verifica dei requisiti, la nota spese viene registrata.

Dopo la registrazione della nota spese, il pagamento viene autorizzato e il dipendente viene rimborsato.
