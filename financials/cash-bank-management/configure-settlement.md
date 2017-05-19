---
title: Configurare una liquidazione
description: "Il modo e il momento in cui le transazioni vengono liquidate possono essere argomenti complessi, pertanto è essenziale che capire e definire in modo corretto i parametri per soddisfare i requisiti aziendali. Questo articolo descrive i parametri utilizzati per la liquidazione sia per la contabilità fornitori che per la contabilità clienti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: dd10b2ebe1871f5845b1f245e259c8647a4408c1
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="configure-settlement"></a>Configurare una liquidazione

[!include[banner](../includes/banner.md)]


Il modo e il momento in cui le transazioni vengono liquidate possono essere argomenti complessi, pertanto è essenziale che capire e definire in modo corretto i parametri per soddisfare i requisiti aziendali. Questo articolo descrive i parametri utilizzati per la liquidazione sia per la contabilità fornitori che per la contabilità clienti. 

I seguenti parametri influiscono su come vengono elaborate le liquidazioni in Microsoft Dynamics 365 for Operations. La liquidazione è il processo di facilitazione di una fattura rispetto a un pagamento o una nota di accredito. Questi parametri sono situati nell'area **Liquidazione** delle pagine **Parametri contabilità clienti** e **Parametri contabilità fornitori**.

-   **Liquidazione automatica**: impostare questa opzione su **Sì** se una transazione deve essere liquidata automaticamente rispetto ad altre transazioni aperte al momento della registrazione. Se l'opzione è impostata su **No**, gli utenti possono liquidare manualmente le transazioni quando immettono i pagamenti o successivamente mediante la pagina **Liquida transazioni**.
-   **Applicazione sconto di cassa**: specifica come uno [sconto di cassa viene gestito se la fattura viene pagata in eccedenza](cash-discount-handling-overpayments.md). Per un'eccedenza di pagamento, lo sconto di cassa può essere ridotto, può essere gestito come differenza, oppure può rimanere nel conto del fornitore o il cliente.
    -   **Non specifico**: l'importo dello sconto di cassa viene ridotto dell'importo dell'eccedenza di pagamento. Questo comportamento viene utilizzato sempre, indipendentemente dal fatto che l'importo dell'eccedenza di pagamento sia superiore o inferiore all'importo immesso nel campo **Massima eccedenza/insufficienza pagamento**.
    -   **Specifico**: l'importo dell'eccedenza di pagamento viene registrato in un conto CoGe relativo alla differenza di sconto di cassa o rimane un saldo sul conto cliente o fornitore. Il comportamento specifico varia a seconda che l'importo dell'eccedenza di pagamento sia compreso tra 0,00 e l'importo immesso nel campo **Massima eccedenza/insufficienza pagamento** o che sia superiore all'importo indicato in **Massima eccedenza/insufficienza pagamento**.
-   **Differenza massima in centesimi**: immettere la differenza massima in centesimi consentita per le transazioni liquidate. Se la differenza è uguale o inferiore a quella immessa in questo campo, verrà registrata nel conto CoGe relativo alla differenza in centesimi specificato nella pagina **Conti per transazioni automatiche**.
-   **Massima eccedenza/insufficienza pagamento**: immettere l'importo accettato come eccedenza e insufficienza di pagamento. Per calcolare l'imposta sulle eccedenze o sulle insufficienze di pagamento, nella pagina **Parametri di contabilità generale**, fare clic su **IVA**, quindi selezionare l'opzione **IVA su eccedenza/insufficienza pagamento**.
    -   Se l'eccedenza o l'insufficienza di pagamento genera una differenza inferiore a quella specificata nel campo **Differenza massima in centesimi**, l'importo della differenza in centesimi verrà registrato nell'apposito conto.
    -   Se l'eccedenza o l'insufficienza di pagamento genera una differenza superiore a quella specificata nel campo **Differenza massima in centesimi**, l'importo della differenza verrà registrato nell'apposito conto selezionato per il tipo di registrazione **Sconto di cassa cliente** o **Sconto di cassa fornitore** nella pagina **Conti per transazioni automatiche**.
-   **Calcola sconti di cassa per pagamenti parziali**: impostare questa opzione su **Sì** per abilitare il calcolo automatico degli sconti di cassa per pagamenti parziali.
    -   L'effetto di questa opzione dipende dal valore del campo **Utilizzare lo sconto di cassa** nella pagina **Liquida transazioni**. Se l'opzione è impostata su **Sì**, lo sconto viene applicato quando il campo **Utilizzare lo sconto di cassa** è impostato su **Normale**. Quando il campo **Utilizzare lo sconto di cassa** è impostato su **Sempre**, lo sconto di cassa viene applicato sempre, indipendentemente dall'impostazione del campo. Quando il campo **Utilizzare lo sconto di cassa** è impostato su **Mai**, lo sconto di cassa non viene mai applicato, indipendentemente dall'impostazione del campo.
    -   Se questa opzione è impostata su **Sì** e un utente cambia il valore nel campo **Importo da liquidare** nella pagina **Liquida transazioni**, lo sconto viene calcolato automaticamente e visualizzato come voce predefinita nel campo **Importo sconto di cassa da applicare**.
    -   Se questa opzione è impostata su **No** e un utente cambia il valore nel campo **Importo da liquidare** nella pagina **Liquida transazioni**, la voce predefinita nel campo **Importo sconto di cassa da applicare** è **0** (zero).
-   **Calcola sconti di cassa per note di accredito**: impostare questa opzione su **Sì** per calcolare automaticamente uno sconto di cassa per le note di accredito. In Contabilità clienti, una transazione di nota di accredito è una transazione negativa con un valore nel campo **Fattura** nella pagina **Fattura a testo libero** o un reso nella pagina **Ordine cliente**.
    -   L'effetto di questa opzione dipende dal valore del campo **Utilizzare lo sconto di cassa** nella pagina **Liquida transazioni**. Se l'opzione è impostata su **Sì**, lo sconto viene applicato quando il campo ****Utilizzare lo sconto di cassa**** è impostato su **Normale**. Quando il campo  ****Utilizzare lo sconto di cassa **** è impostato su **Sempre**, lo sconto di cassa viene applicato sempre, indipendentemente dall'impostazione del campo. Quando il campo  ****Utilizzare lo sconto di cassa**** è impostato su **Mai**, lo sconto di cassa non viene mai applicato, indipendentemente dall'impostazione del campo.
    -   Se questa opzione è impostata su **Sì** e viene contrassegnata una nota di accredito nella pagina **Liquida transazioni**, lo sconto viene calcolato automaticamente e visualizzato come voce predefinita nel campo **Importo sconto di cassa da applicare**.
    -   Se questa opzione è impostata su **No** e viene contrassegnata una nota di accredito nella pagina **Liquida transazioni**, la voce predefinita del campo **Importo sconto di cassa da applicare** è **0** (zero).
-   **Conti di contropartita sconti (solo Contabilità fornitori)**: definire il conto CoGe per sconti di cassa predefinito da utilizzare per la voce contabile per sconti di cassa.
    -   **Conto principale per sconti fornitore**: lo sconto di cassa viene registrato nel conto principale definito nella pagina **Impostazione sconto di cassa**.
    -   **Conti nelle righe fattura**: lo sconto di cassa è registrato nei conti CoGe nella fattura originale.
-   **Contrassegna righe su fatture a testo libero e note d'interesse (solo Contabilità clienti)**: impostare questa opzione su **Sì** per abilitare il pulsante **Contrassegna righe fattura** nelle pagine **Pagamenti cliente**, **Giustificativo giornale di registrazione per pagamento** e **Liquida transazioni**. Questo pulsante consente agli utenti di contrassegnare singole righe per la liquidazione.
-   **Assegna priorità a liquidazione (solo Contabilità clienti)**: impostare questa opzione su **Sì** per abilitare il pulsante **Contrassegna in base a priorità** nelle pagine **Pagamenti cliente** e **Liquida transazioni**. Il pulsante consente agli utenti di assegnare l'ordine di liquidazione predeterminato alle transazioni.  Dopo aver applicato l'ordine di liquidazione a una transazione, è possibile modificare l'allocazione dell'ordine e del pagamento prima della registrazione.
-   **Utilizza priorità per liquidazioni automatiche**: impostare questa opzione su **Sì** per utilizzare l'ordine di priorità definito quando le transazioni vengono liquidate automaticamente. Questo campo è disponibile solo se le opzioni **Assegna priorità a liquidazione** e **Liquidazione automatica**  sono impostate su **Sì**.





