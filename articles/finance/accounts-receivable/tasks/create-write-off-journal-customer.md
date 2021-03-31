---
title: Creare un giornale di registrazione annullamento per un cliente
description: Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 182afb5b105fec6dcac323b4f98db5fb7b3e0d68
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220277"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Creare un giornale di registrazione annullamento per un cliente

[!include [banner](../../includes/banner.md)]

Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente. In questa attività viene utilizzata la società dimostrativa USMF.


## <a name="set-up-the-write-off-parameters"></a>Impostare i parametri di annullamento
1. Andare a **Pannello di navigazione > Moduli > Crediti e riscossioni > Impostazione > Parametri contabilità clienti**.
2. Fare clic sulla scheda **Riscossioni**.
3. Espandere o comprimere la sezione **Annullamento**
    - Il **giornale di registrazione annullamento** è il giornale di registrazione generale che contiene le transazioni di annullamento create.  
    - È possibile collegare un codice motivo a ogni annullamento. È possibile sovrascrivere questo valore predefinito al momento dell'annullamento.  
    - Impostare **IVA separata** su Sì se si desidera separare l'IVA dalla transazione originale nell'annullamento.  
4. Chiudere la pagina.
5. Andare a **Crediti e riscossioni > Impostazione > Profili di registrazione cliente**. Il conto di annullamento verrà utilizzato come rettifica del conto spese o di prenotazione nel giornale di registrazione generale.
6. Chiudere la pagina.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Annullare il saldo di un cliente dalla pagina dei saldi con aging
1. Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.
2. Contrassegnare la riga per il cliente per cui si desidera eseguire l'annullamento. Ad esempio, contrassegnare la riga con Birch Company.
3. Nel **riquadro azioni** fare clic su **Raccolta**.
4. Fare clic su **Annullare**.
5. Fare clic su **OK**.
6. Chiudere la pagina.
7. Andare a **Pannello di navigazione > Moduli > Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**.
8. Selezionare il numero batch del giornale di registrazione contenente l'annullamento. Una riga viene creata per stornare il saldo del cliente. Una o più righe vengono create per registrare l'annullamento nel conto relativo.  
9. Chiudere la pagina.
10. Chiudere la pagina.

## <a name="write-off-transactions-from-the-collections-form"></a>Annullare transazioni nel modulo delle riscossioni.
1. Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.
2. Selezionare il nome del cliente a cui sono associate le transazioni che si desidera annullare. Ad esempio, selezionare Cave Wholesales (US-004).
3. Contrassegnare la riga per la prima transazione.
4. Contrassegnare la riga per la seconda transazione.
5. Fare clic su **Annullare**.
6. Nel campo **Commento motivo** digitare "Crediti inesigibili".
7. Fare clic su **OK**.
8. Chiudere la pagina.
9. Chiudere la pagina.
10. Fare clic su **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.
11. Selezionare il numero batch del giornale di registrazione contenente l'annullamento. Una riga viene creata per stornare il saldo del cliente. Una o più righe vengono create per registrare l'annullamento nel conto relativo.  
12. Chiudere la pagina.
13. Chiudere la pagina.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Annullare una fattura nella pagina Fatture cliente aperte
1. Andare a **Pannello di navigazione > Moduli > Contabilità clienti > Fatture > Fatture cliente aperte**.
2. Contrassegnare la riga per una fattura. Ad esempio, contrassegnare la riga per CIV-000667.
3. Nel **riquadro azioni** fare clic su **Fattura**.
4. Fare clic su **Annulla**.
5. Fare clic su **OK**.
6. Chiudere la pagina.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Annullare un saldo cliente dalla pagina clienti
1. Andare a **Contabilità clienti > Clienti > Tutti i clienti**.
2. Selezionare un account cliente. Ad esempio, selezionare US-001 (Contoso Retail San Diego).
3. Nel **riquadro azioni** fare clic su **Raccolta**.
4. Fare clic su **Annulla**.
5. Fare clic su **OK**.
6. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]