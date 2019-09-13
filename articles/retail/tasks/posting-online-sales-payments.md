---
title: Registrazione di vendite e pagamenti online
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.
author: psimolin
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d42b585a61214628980cd45a859215443ed55b5
ms.sourcegitcommit: c461758290d7ddc19f0b60701368937c35ef78b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864155"
---
# <a name="posting-of-online-sales-and-payments"></a>Registrazione di vendite e pagamenti online

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.

La registrazione di vendite e pagamenti online è un processo a due fasi.

- Pull dei dati transazione di vendita al dettaglio online nella sede centrale.
- Sincronizzazione di ordini per creare ordini cliente nella sede centrale.

Il pull dei dati transazione di vendita al dettaglio online può essere effettuato eseguendo manualmente il P-Job o creando un processo batch ricorrente.

### <a name="manually-running-the-p-job"></a>Esecuzione manuale del P-job

1. Andare a Tutte le aree di lavoro > Vendita al dettaglio IT.
2. Fare clic su Programmazione della distribuzione.
3. Selezionare P-0001.
4. Modificare i gruppi di database canale, se necessario.
5. Fare clic su Esegui adesso.
6. Fare clic su Sì.

### <a name="scheduling-a-recurring-p-job"></a>Programmazione di un P-job ricorrente

1. Andare a Tutte le aree di lavoro > Vendita al dettaglio IT.
2. Fare clic su Programmazione della distribuzione.
3. Selezionare P-0001.
4. Fare clic su Crea processo batch.
5. Fare clic su Esecuzione in background.
5. Abilitare Elaborazione batch.
6. Fare clic su Ricorrenza.
7. Selezionare l'opzione Nessuna data di fine.
8. Nel campo Conteggio, immettere un intervallo in minuti tra le esecuzioni. In genere il valore è 5-10.
9. Fare clic su OK.
10. Fare clic su OK.

Gli ordini possono essere sincronizzati eseguendo manualmente il processo "Sincronizza ordini" o creando un processo batch ricorrente.

### <a name="manually-running-order-synchronization"></a>Esecuzione manuale della sincronizzazione degli ordini 

Seguire questi passaggi per eseguire manualmente il processo "Sincronizza ordini" una volta.

1. Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.
2. Fare clic su Sincronizza ordini.
3. Nel campo Gerarchia organizzativa, selezionare "Punti vendita al dettaglio per area"
    * Selezionare un punto vendita online specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.  
    * Fare clic sulla freccia per aggiungere la selezione.  
4. Fare clic sulla scheda Esecuzione in background.
5. Disabilitare Elaborazione batch.
6. Fare clic su Ricorrenza.
7. Selezionare l'opzione Fine dopo.
8. Nel campo Fine dopo, immettere 1.
9. Fare clic su OK.
10. Fare clic su OK.

### <a name="scheduling-recurring-order-synchronization"></a>Programmazione della sincronizzazione di ordini ricorrenti

In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.
2. Fare clic su Sincronizza ordini.
3. Nel campo Gerarchia organizzativa, selezionare "Punti vendita al dettaglio per area"
    * Selezionare un punto vendita online specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.  
    * Fare clic sulla freccia per aggiungere la selezione.  
4. Fare clic sulla scheda Esecuzione in background.
5. Abilitare Elaborazione batch.
6. Fare clic su Ricorrenza.
7. Selezionare l'opzione Nessuna data di fine.
8. Nel campo Conteggio, immettere un intervallo in minuti tra le esecuzioni. In genere il valore è 2-20.
9. Fare clic su OK.
10. Fare clic su OK.

## <a name="data-entities-involved-in-the-process"></a>Entità di dati coinvolte nel processo

- RetailTransactionTable
- RetailTransactionAddressTrans
- RetailTransactionInfocodeTrans
- RetailTransactionTaxTrans
- RetailTransactionSalesTrans
- RetailTransactionTaxMeasure
- RetailTransactionDiscountTrans
- RetailTransactionTaxTransGTE
- RetailTransactionMarkupTrans
- RetailTransactionPaymentTrans
- RetailTransactionAttributeTrans
