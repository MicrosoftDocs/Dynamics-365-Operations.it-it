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
ms.openlocfilehash: e3bac0cab764436a618fa570901c84ab720dbc86
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140786"
---
# <a name="posting-of-online-sales-and-payments"></a>Registrazione di vendite e pagamenti online

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di creare ordini cliente e pagamenti per le transazioni punto vendita online.

La registrazione di vendite e pagamenti online è un processo a due fasi.

- Pull dei dati transazione di commercio nella sede centrale.
- Sincronizzazione di ordini per creare ordini cliente nella sede centrale.

Il pull dei dati transazione online può essere effettuato eseguendo manualmente il P-Job o creando un processo batch ricorrente.

### <a name="manually-running-the-p-job"></a>Esecuzione manuale del P-job

1. Passare a Tutte le aree di lavoro > Vendita al dettaglio e commercio IT.
2. Fare clic su Programmazione della distribuzione.
3. Selezionare P-0001.
4. Modificare i gruppi di database canale, se necessario.
5. Fare clic su Esegui adesso.
6. Fare clic su Sì.

### <a name="scheduling-a-recurring-p-job"></a>Programmazione di un P-job ricorrente

1. Passare a Tutte le aree di lavoro > Vendita al dettaglio e commercio IT.
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
3. Nel campo Gerarchia organizzativa, selezionare "Punti vendita per area".
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
3. Nel campo Gerarchia organizzativa, selezionare "Punti vendita per area".
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
