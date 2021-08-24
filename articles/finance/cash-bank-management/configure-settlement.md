---
title: Configurare una liquidazione
description: Il modo e il momento in cui le transazioni vengono liquidate possono essere argomenti complessi, pertanto è essenziale che capire e definire in modo corretto i parametri per soddisfare i requisiti aziendali. Questo argomento descrive i parametri utilizzati per la liquidazione sia per la contabilità fornitori che per la contabilità clienti.
author: kweekley
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 323a1e6d426208a880a72dd89f7be04bacbf13a8e6c5d8ab7599217cfc18f2c0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720576"
---
# <a name="configure-settlement"></a>Configurare una liquidazione

[!include [banner](../includes/banner.md)]

Il modo e il momento in cui le transazioni vengono liquidate possono essere argomenti complessi, pertanto è essenziale che capire e definire in modo corretto i parametri per soddisfare i requisiti aziendali. Questo argomento descrive i parametri utilizzati per la liquidazione sia per la contabilità fornitori che per la contabilità clienti. 

I seguenti parametri influiscono su come vengono elaborate le liquidazioni in Microsoft Dynamics 365 Finance. La liquidazione è il processo di facilitazione di una fattura rispetto a un pagamento o una nota di accredito. Questi parametri sono situati nell'area **Liquidazione** delle pagine **Parametri contabilità clienti** e **Parametri contabilità fornitori**.

- **Liquidazione automatica**: impostare questa opzione su **Sì** se una transazione deve essere liquidata automaticamente rispetto ad altre transazioni aperte al momento della registrazione. Se l'opzione è impostata su **No**, gli utenti possono liquidare manualmente le transazioni quando immettono i pagamenti o successivamente mediante la pagina **Liquida transazioni**.
- **Applicazione sconto di cassa**: specifica come uno [sconto di cassa viene gestito se la fattura viene pagata in eccedenza](cash-discount-handling-overpayments.md). Per un'eccedenza di pagamento, lo sconto di cassa può essere ridotto, può essere gestito come differenza, oppure può rimanere nel conto del fornitore o il cliente.
  -   **Non specifico**: l'importo dello sconto di cassa viene ridotto dell'importo dell'eccedenza di pagamento. Questo comportamento viene utilizzato sempre, indipendentemente dal fatto che l'importo dell'eccedenza di pagamento sia superiore o inferiore all'importo immesso nel campo **Massima eccedenza/insufficienza pagamento**.
  -   **Specifico**: l'importo dell'eccedenza di pagamento viene registrato in un conto CoGe relativo alla differenza di sconto di cassa o rimane un saldo sul conto cliente o fornitore. Il comportamento specifico varia a seconda che l'importo dell'eccedenza di pagamento sia compreso tra 0,00 e l'importo immesso nel campo **Massima eccedenza/insufficienza pagamento** o che sia superiore all'importo indicato in **Massima eccedenza/insufficienza pagamento**.
- **Differenza massima in centesimi**: immettere la differenza massima in centesimi consentita per le transazioni liquidate. Se la differenza è uguale o inferiore a quella immessa in questo campo, verrà registrata nel conto CoGe relativo alla differenza in centesimi specificato nella pagina **Conti per transazioni automatiche**.
- **Massima eccedenza/insufficienza pagamento**: immettere l'importo accettato come eccedenza e insufficienza di pagamento. Per calcolare l'imposta sulle eccedenze o sulle insufficienze di pagamento, nella pagina **Parametri di contabilità generale**, fare clic su **IVA**, quindi selezionare l'opzione **IVA su eccedenza/insufficienza pagamento**.
  -   Se l'eccedenza o l'insufficienza di pagamento genera una differenza inferiore a quella specificata nel campo **Differenza massima in centesimi**, l'importo della differenza in centesimi verrà registrato nell'apposito conto.
  -   Se l'eccedenza o l'insufficienza di pagamento genera una differenza superiore a quella specificata nel campo **Differenza massima in centesimi**, l'importo della differenza verrà registrato nell'apposito conto selezionato per il tipo di registrazione **Sconto di cassa cliente** o **Sconto di cassa fornitore** nella pagina **Conti per transazioni automatiche**.
- **Calcola sconti di cassa per pagamenti parziali**: impostare questa opzione su **Sì** per abilitare il calcolo automatico degli sconti di cassa per pagamenti parziali.
  -   L'effetto di questa opzione dipende dal valore del campo **Utilizzare lo sconto di cassa** nella pagina **Liquida transazioni**. Se l'opzione è impostata su **Sì**, lo sconto viene applicato quando il campo **Utilizzare lo sconto di cassa** è impostato su **Normale**. Quando il campo **Utilizzare lo sconto di cassa** è impostato su **Sempre**, lo sconto di cassa viene applicato sempre, indipendentemente dall'impostazione del campo. Quando il campo **Utilizzare lo sconto di cassa** è impostato su **Mai**, lo sconto di cassa non viene mai applicato, indipendentemente dall'impostazione del campo.
  -   Se questa opzione è impostata su **Sì** e un utente cambia il valore nel campo **Importo da liquidare** nella pagina **Liquida transazioni**, lo sconto viene calcolato automaticamente e visualizzato come voce predefinita nel campo **Importo sconto di cassa da applicare**.
  -   Se questa opzione è impostata su **No** e un utente cambia il valore nel campo **Importo da liquidare** nella pagina **Liquida transazioni**, la voce predefinita nel campo **Importo sconto di cassa da applicare** è **0** (zero).
- **Calcola sconti di cassa per note di accredito**: impostare questa opzione su **Sì** per calcolare automaticamente uno sconto di cassa per le note di accredito. In Contabilità clienti, una transazione di nota di accredito è una transazione negativa con un valore nel campo **Fattura** nella pagina **Fattura a testo libero** o un reso nella pagina **Ordine cliente**.
  - L'effetto di questa opzione dipende dal valore del campo <strong>Utilizzare lo sconto di cassa</strong> nella pagina <strong>Liquida transazioni</strong>. Se l'opzione è impostata su <strong>Sì</strong>, lo sconto viene applicato quando il campo *<strong><em>Utilizzare lo sconto di cassa</em></strong>* viene impostato su <strong>Normale</strong>. Quando il campo *<strong><em>Utilizzare lo sconto di cassa</em></strong>* è impostato su <strong>Sempre</strong>, lo sconto di cassa viene applicato sempre, indipendentemente dall'impostazione del campo. Quando il campo *<strong><em>Utilizzare lo sconto di cassa</em></strong>* è impostato su <strong>Mai</strong>, lo sconto di cassa non viene mai applicato, indipendentemente dall'impostazione del campo.
  - Se questa opzione è impostata su **Sì** e viene contrassegnata una nota di accredito nella pagina **Liquida transazioni**, lo sconto viene calcolato automaticamente e visualizzato come voce predefinita nel campo **Importo sconto di cassa da applicare**.
  - Se questa opzione è impostata su **No** e viene contrassegnata una nota di accredito nella pagina **Liquida transazioni**, la voce predefinita del campo **Importo sconto di cassa da applicare** è **0** (zero).

- **Conti di contropartita sconti (solo Contabilità fornitori)**: definire il conto CoGe per sconti di cassa predefinito da utilizzare per la voce contabile per sconti di cassa.
  -   **Conto principale per sconti fornitore**: lo sconto di cassa viene registrato nel conto principale definito nella pagina **Impostazione sconto di cassa**.
  -   **Conti nelle righe fattura**: lo sconto di cassa è registrato nei conti CoGe nella fattura originale.
- **Contrassegna righe su fatture a testo libero e note d'interesse (solo Contabilità clienti)**: impostare questa opzione su **Sì** per abilitare il pulsante **Contrassegna righe fattura** nelle pagine **Pagamenti cliente**, **Giustificativo giornale di registrazione per pagamento** e **Liquida transazioni**. Questo pulsante consente agli utenti di contrassegnare singole righe per la liquidazione.
- **Assegna priorità a liquidazione (solo Contabilità clienti)**: impostare questa opzione su **Sì** per abilitare il pulsante **Contrassegna in base a priorità** nelle pagine **Pagamenti cliente** e **Liquida transazioni**. Il pulsante consente agli utenti di assegnare l'ordine di liquidazione predeterminato alle transazioni.  Dopo aver applicato l'ordine di liquidazione a una transazione, è possibile modificare l'allocazione dell'ordine e del pagamento prima della registrazione.
- **Utilizza priorità per liquidazioni automatiche**: impostare questa opzione su **Sì** per utilizzare l'ordine di priorità definito quando le transazioni vengono liquidate automaticamente. Questo campo è disponibile solo se le opzioni **Assegna priorità a liquidazione** e **Liquidazione automatica**  sono impostate su **Sì**.

## <a name="fixed-dimensions-on-accounts-receivableaccounts-payable-main-accounts"></a>Dimensioni fisse sui conti principali Contabilità fornitori/contabilità clienti

Quando le dimensioni fisse vengono utilizzate nel conto principale Contabilità fornitori o Contabilità clienti, voci contabili aggiuntive e due transazioni di fornitore aggiuntive verranno registrate dal processo di liquidazione. La liquidazione confronta il conto CoGe Contabilità fornitori o Contabilità clienti con la fattura e il pagamento.  Quando il pagamento e la liquidazione vengono completati insieme, che è lo scenario tipico, la voce contabile de pagamento non viene registrata nella contabilità generale fino a quando non viene completato il processo di liquidazione. A causa dell'ordine di eventi di elaborazione, la liquidazione non è in grado di determinare il conto CoGe di contabilità fornitori/contabilità clienti effettivo dalla voce contabile del pagamento. La liquidazione ricostruisce ciò che il conto CoGe sarà per il pagamento. Questa impostazione diventa un problema quando una dimensione fissa viene utilizzata per il conto principale Contabilità fornitori e Contabilità clienti.

Per ricostruire il conto CoGe, il conto principale Contabilità fornitori o Contabilità clienti viene recuperato dal profilo di registrazione e le dimensioni finanziarie vengono recuperate dal record di transazione fornitore per il pagamento, così come definito nel giornale di registrazione pagamenti. Le dimensioni fisse non sono predefinite nei giornali di registrazione pagamenti. Vengono invece applicate al conto principale come ultimo passaggio del processo di registrazione. Di conseguenza, il valore di dimensione fissa probabilmente non è contenuto nella transazione fornitore, a meno che venga predefinito da un'altra origine, ad esempio il fornitore. Il conto ricostruito non includerà la dimensione fissa. L'elaborazione della liquidazione determinerà la necessità di creare un voce di rettifica, a differenza della fattura registrata con il valore di dimensioni fissa e del conto pagamenti ricostruito.  Poiché la liquidazione continua con la registrazione della voce di rettifica, l'ultimo passaggio nella registrazione riguarda l'applicazione della dimensione fissa. Aggiungendo la dimensione alla voce di rettifica, viene registrata con un importo in Dare e in Avere nello stesso conto CoGe. La liquidazione non può eseguire il rollback della voce contabile.

Per evitare le voci contabili aggiuntive, il debito e il credito nello stesso conto CoGe, è possibile considerare le soluzioni alternative seguenti, in base alle proprie esigenze aziendali. 

-   Le organizzazioni utilizzano spesso dimensioni fisse per compilare con zero una dimensione finanziaria che non è richiesta. È il caso in genere dei conti dello stato patrimoniale, ad esempio contabilità clienti/contabilità fornitori. Le strutture dei conti possono essere utilizzate per non tenere traccia delle dimensioni finanziarie che sono in genere completate con zeri.  È possibile rimuovere la dimensione finanziaria per i conti dello stato patrimoniale, eliminando la necessità di utilizzare dimensioni fisse.
-   Se l'organizzazione richiede dimensioni fisse nel conto principale contabilità fornitori/contabilità clienti, trovare un modo per impostare come valore predefinito la dimensione fissa nel pagamento, in modo che il valore di dimensione fissa sia memorizzato nella transazione fornitore per il pagamento. Ciò permetterà al sistema di ricostruire il conto principale contabilità fornitori/contabilità clienti per includere i valori di dimensione fissa. Il valore di dimensione fissa può essere definito come valore predefinito sui fornitori o il nome del giornale di registrazione pagamenti.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]