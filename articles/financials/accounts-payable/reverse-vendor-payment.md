---
title: Stornare un pagamento fornitore
description: Questo articolo descrive le differenze tra lo storno, l'eliminazione, l'annullamento e il rifiuto di un pagamento. Inoltre, illustra i due metodi per stornare un assegno fornitore.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6587505fc5a729ffd82ab65aca7d5aa6ca4a265
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837254"
---
# <a name="reverse-a-vendor-payment"></a>Stornare un pagamento fornitore

[!include [banner](../includes/banner.md)]

Questo articolo descrive le differenze tra lo storno, l'eliminazione, l'annullamento e il rifiuto di un pagamento. Inoltre, illustra i due metodi per stornare un assegno fornitore. 

Occasionalmente, dopo che un pagamento fornitore è stato registrato, il pagamento deve essere stornato. Lo storno è diverso da eliminare, annullare o rifiutare un pagamento. È possibile eliminare un pagamento solo se ha lo stato di **Creato**. Questo stato indica che il pagamento è stato creato ma non è ancora stato generato. Questa limitazione si applica sempre, indipendentemente dal metodo di pagamento. È possibile annullare gli assegni non registrati dopo che sono stati generati ma prima che siano stati registrati. Se il pagamento generato viene eseguito come bonifico (EFT), è possibile rifiutare il pagamento prima che venga registrato. Per rifiutare un pagamento, cambiare il valore **Stato pagamento**. Un pagamento che è stata annullato o rifiutato può essere rigenerato dopo che il valore **Stato pagamento** viene reimpostato su **Nessuno**. 

Dopo che un pagamento viene registrato, gli storni vengono utilizzati. I pagamenti effettuati elettronicamente non possono essere stornati dopo che sono stati registrati. Invece, una nuova transazione deve essere creata per l'importo del pagamento per ottenere la passività di nuovo sul conto del fornitore. Sono disponibili due metodi per stornare assegni registrati. In un metodo gli storni vengono registrati immediatamente quando si fa clic su **Storno di pagamento** nella pagina **Assegno**. Con l'altro metodo, quando si fa clic su **Storno di pagamento** nella pagina **Assegno** lo storno viene inviato al giornale di registrazione storno assegni in Gestione cassa e banche, dove un revisore può quindi registrare o rifiutare lo storno. 

Per conoscere il metodo utilizzato dall'organizzazione, visualizzare la pagina **Parametri di gestione cassa e banche**. Se l'opzione **Usa processo di revisione per storni di pagamenti** è impostata su **Sì**, gli storni vengono inviati al giornale di registrazione storno assegni per la revisione. Nella tabella seguente vengono descritte le differenze dei metodi di storno assegni.

| Se l'organizzazione non esamina gli storni assegni prima della registrazione                                                                                                                                  | Se l'organizzazione esamina gli storni assegni prima della registrazione                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| L'assegno viene immediatamente stornato quando si fa clic su **OK** nella pagina **Assegno**.                                                                                                                      | Lo storno non viene eseguito immediatamente. Viene creato un giornale di registrazione storno assegni per la revisione. Se questo giornale viene eliminato, l'assegno può essere stornato di nuovo.                                                                                                                                                                                                                                                                |
| Le voci contabili per l'assegno originale vengono stornate.                                                                                                                                         | Il conto CoGe della voce contabile dell'assegno originale non può essere registrato. Le dimensioni finanziarie del giornale di registrazione dell'assegno originale vengono usate come le dimensioni finanziarie predefinite nel giornale di registrazione storno assegni. I valori predefiniti possono essere modificati. Quando il giornale di registrazione storno assegni viene registrato, i conti principali per la contabilità fornitori vengono inseriti automaticamente tramite i profili registrazione, che possono essere cambiati. |
| Le strutture contabili utilizzate al momento della registrazione dell'assegno originale vengono utilizzate per stornare l'assegno, anche se la struttura dei conti è stata modificata. La combinazione di conti non viene convalidata. | Se una struttura dei conti è stata modificata dopo la registrazione dell'assegno originale, è possibile che sia necessaria una nuova dimensione finanziaria per lo storno dell'assegno. È possibile che questa dimensione finanziaria non venga immessa automaticamente tramite il giornale di registrazione del pagamento originale. La combinazione di conti viene convalidata al momento della registrazione dello storno assegni.                                                                                                        |
| Le dimensioni fisse non vengono applicate allo storno, per garantire che gli stessi conti CoGe siano stornati.                                                                                      | Vengono applicate al giornale di registrazione storno assegni durante la registrazione. Il valore della dimensione finanziaria non può essere presente nella voce contabile dell'assegno originale, a seconda del momento della definizione della dimensione fissa.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Stornare assegni registrati senza rivederli
Se l'organizzazione desidera registrare gli storni assegni subito dopo che è stato fatto clic su **Storno di pagamento** nella pagina **Assegni**, attenersi alla procedura che segue. Nella pagina **Parametri di gestione cassa e banche** impostare l'opzione **Usa processo di revisione per storni di pagamenti** su **No**. Nella pagina **Assegni** è possibile selezionare l'assegno da stornare e scegliere **Storno di pagamento**. È possibile quindi immettere la data e selezionare una causale per lo storno.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>Stornare assegni registrati dopo che sono stati rivisti nel giornale di registrazione storni assegni
Se l'organizzazione desidera esaminare gli storni assegni prima della registrazione, creare un giornale di registrazione storno assegni per la revisione e nella pagina **Parametri di gestione cassa e banche** impostare l'opzione **Usa processo di revisione per storni di pagamenti** su **Sì**. Nella pagina **Assegni** è possibile selezionare l'assegno da stornare e scegliere **Storno di pagamento**. È possibile quindi immettere la data e selezionare una causale per lo storno. È inoltre necessario selezionare un nome di giornale di registrazione per creare un giornale di registrazione nel giornale di registrazione storno assegni.

### <a name="review-a-reversal"></a>Effettuare la revisione di uno storno

Se si è un utente che deve esaminare gli storni, è possibile approvare e registrare il giornale di registrazione o rifiutare lo storno eliminando il giornale di registrazione. Nella pagina **Giornale di registrazione storno assegni** è possibile selezionare il giornale di registrazione dello storno da esaminare e quindi fare clic su **Righe**. È possibile esaminare l'assegno stornato e selezionare una delle opzioni di approvazione indicate di seguito:

-   Per approvare e registrare il giornale di registrazione storno, fare clic su **Registra** o **Registra e trasferisci**.
-   Per rifiutare lo storno, eliminare il giornale di registrazione storno.

> [!NOTE]
> Se si elimina il giornale di registrazione, lo storno viene rimosso dal sistema, ma l'assegno originale rimane nella pagina **Assegno**. Lo stato dell'assegno non è più **In attesa di annullamento**.

## <a name="results-of-posting-a-reversal"></a>Risultati della registrazione di uno storno
Quando si registra lo storno di un assegno, si verificano i seguenti eventi:

-   Lo stato dell'assegno viene aggiornato allo stato **Annullamento**.
-   Se l'opzione **Riconcilia** è stata selezionata nella pagina dello storno durante lo storno, l'assegno viene riconciliato ( l'opzione **Riconciliato** è selezionata) e non viene visualizzato nella pagina **Riconciliazione estratti conto**.
-   Il giustificativo dello storno viene registrato sul conto bancario da cui è stato emesso l'assegno, per incrementare il saldo del conto stesso.
-   Il giustificativo viene registrato nella contabilità generale.
-   I dettagli della modifica vengono aggiornati nel gruppo di campi **Storico** della pagina **Assegno**.

> [!NOTE] 
> Quando si storna un assegno emesso per una transazione di commercio interaziendale, le voci di contropartita provengono dall'impostazione contabile per il commercio interaziendale anziché dalla transazione originale. Se l'assegno stornato è stato emesso per un pagamento fornitore, si verificano anche i seguenti eventi:

-   Il pagamento originale della fattura a fronte della quale è stato liquidato il pagamento non viene applicato (la liquidazione viene stornata).
-   Una transazione viene registrata nel conto fornitore per lo storno del pagamento e il pagamento stornato viene liquidato a fronte del pagamento originale. Il campo **Ultimo giustificativo di liquidazione** della pagina **Transazioni fornitore** relativo all'esborso fornitore originale viene aggiornato in base al numero di giustificativi della transazione stornata.

Se l'assegno stornato è stato emesso per un rimborso al cliente, si verificano anche gli eventi che seguono:

-   Una transazione viene registrata nel conto cliente per lo storno del pagamento, mentre viene stornato il saldo tra il pagamento originale e il documento a fronte del quale il pagamento è stato liquidato originariamente (viene creato un pagamento negativo).
-   Uno storno di pagamento viene applicato al pagamento originale. Il campo **Ultimo giustificativo di liquidazione** della pagina **Transazioni cliente** relativo al pagamento originale del cliente viene aggiornato in base al numero di giustificativi della transazione stornata.




