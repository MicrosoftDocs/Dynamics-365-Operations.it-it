---
title: Modificare e controllare transazioni punto vendita al dettaglio
description: In questo argomento vengono descritte le funzionalità per la modifica e il controllo delle transazioni punto vendita al dettaglio.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: b0201d31cd83b4360f96a7d8e2113caf9d913715
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622529"
---
# <a name="edit-and-audit-retail-store-transactions"></a>Modificare e controllare transazioni punto vendita al dettaglio

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

I clienti Dynamics 365 Retail utilizzano l'applicazione POS del produttore oltre che applicazioni POS di terze parti. Con l'applicazione POS del produttore, le transazioni punto vendita al dettaglio vengono inserite in Retail Headquarters dai canali mediante un processo batch. Con le applicazioni di terze parti, le transazioni vengono inserite in Retail Headquarters tramite integrazione. In entrambi i casi, dopo l'inserimento delle transazioni in Retail Headquarters, è necessario effettuare un processo di verifica della coerenza che esegue diverse convalide sulle transazioni, in modo che solo le transazioni convalidate correttamente vengano inserite nel rendiconto da registrare in Retail Headquarters. 

Le transazioni di vendita al dettaglio non superano la convalida per diversi motivi. Ad esempio, un errore nel codice di integrazione o un errore nell'applicazione POS può causare dati incoerenti; un errore dell'utente, come l'eliminazione di un prodotto dopo la sincronizzazione con il canale o la chiusura di un periodo fiscale senza registrare le transazioni di vendita al dettaglio per il periodo, può causare dati incoerenti.

Anche se queste transazioni vengono contrassegnate ed escluse dai rendiconti, possono interrompere il processo di registrazione quotidiana delle vendite al dettaglio nella contabilità finanziaria di un cliente.

In Retail, è possibile modificare le specifiche transazioni di vendita al dettaglio che non superano la convalida e allo stesso tempo gestire il controllo di tutte le modifiche. 

## <a name="edit-and-audit-transactions"></a>Modificare e controllare le transazioni

In Retail versione 10.0.5, le transazioni cash-and-carry, come vendite e resi, sono le sole transazioni che possono essere modificate. La modifica degli ordini cliente o degli ordini online non è supportata. In Retail versione 10.0.6 e successive, è supportata anche la modifica delle transazioni di gestione di cassa.

1. Installare il componente aggiuntivo Dynamics Excel.

2. Passare all'area di lavoro **Dati finanziari punto vendita al dettaglio**. Il riquadro **Errori di convalida transazioni** fornisce una visualizzazione pre-filtrata del modulo Transazione di vendita al dettaglio che non ha soddisfatto una o più regole di convalida.
 
3. Aprire il modulo. Fare clic sul record che non ha superato la convalida, selezionare **Componente aggiuntivo per Office**, quindi fare clic su **Modifica transazione selezionata**. Verrà aperto un file di Excel contenente i dettagli della transazione selezionata, con i seguenti fogli di lavoro:

    - Righe: questo foglio di lavoro contiene le righe di intestazione e di prodotto e i dati correlati della transazione.
    - Pagamenti: questo foglio di lavoro contiene i dettagli delle righe di pagamento della transazione.
    - Sconti: questo foglio di lavoro contiene i dettagli relativi agli sconti della transazione.
    - Imposte: questo foglio di lavoro contiene i dettagli relativi alle imposte della transazione.
    - Spese: questo foglio di lavoro contiene i dati relativi alle spese della transazione.

4. Nel file di Excel, modificare i campi appropriati, quindi caricare i dati nuovamente in Retail Headquarters utilizzando la funzionalità di pubblicazione del componente aggiuntivo Dynamics Excel. Una volta pubblicate, le modifiche verranno riflesse nel sistema. Durante la pubblicazione non viene effettuata alcuna convalida delle modifiche apportate dagli utenti.

5. Un audit trail completo delle modifiche può essere visualizzato facendo clic su **Visualizza audit trail** nell'intestazione **Transazione di vendita al dettaglio** per le modifiche a livello di intestazione e nella sezione e nel record pertinenti nella pagina della transazione appropriata. Ad esempio, tutte le modifiche relative alle righe di vendita saranno visibili nella pagina **Transazioni di vendita**, le modifiche relative ai pagamenti saranno visibili nella pagina **Transazioni di pagamento** e così via. I dettagli di controllo che vengono gestiti per le modifiche sono i seguenti.

   - Data e ora modifica
   - Campo 
   - Valore precedente
   - Nuovo valore
   - Autore modifica

6. Dopo che le modifiche sono state apportate e pubblicate, eseguire nuovamente l'opzione **Convalida transazioni punto vendita** per verificare che le modifiche siano coerenti e valide.

> [!NOTE]
> È possibile modificare solo le transazioni che non hanno superato la convalida. Per modificare le transazioni che hanno superato la convalida, cambiare lo stato di convalida della transazione che si desidera modificare in **Errore** o **Nessuno**. Sarà quindi possibile modificarla. 


## <a name="bulk-edit-transactions"></a>Modificare in blocco le transazioni

In Retail versione 10.0.6 e successive è supportata l'opzione di modificare in blocco le transazioni di vendita al dettaglio a livello di rendiconto. 

1. Utilizzare il componente aggiuntivo di Excel per aprire un rendiconto che contiene le transazioni da modificare, utilizzando i passaggi 1-3 precedenti.

2. Scegliere una delle opzioni seguenti.

    - **Modifica transazioni cash-and-carry**. Questa opzione consente di modificare tutte le transazioni cash-and-carry incluse nel rendiconto. Sono disponibili i seguenti fogli di lavoro di Excel.
    
       - **Transazione**: questo foglio di lavoro contiene tutte le informazioni a livello di intestazione delle transazioni di vendita.
       - **Transazione di vendita**: questo foglio di lavoro contiene tutte le informazioni a livello di riga delle transazioni di vendita.
       - **Transazioni di pagamento**: questo foglio di lavoro contiene tutte le informazioni delle righe di pagamento delle transazioni di vendita.
       - **Transazioni di sconto**: questo foglio di lavoro contiene tutte le informazioni delle righe di sconto delle transazioni di vendita.
       - **Transazioni fiscali**: questo foglio di lavoro contiene tutte le informazioni delle righe di imposta delle transazioni di vendita.
       - **Transazioni spese**: questo foglio di lavoro contiene tutte le informazioni delle righe addebiti delle transazioni di vendita.

    - **Modifica transazioni gestione di cassa**. Questa opzione consente di modificare tutte le transazioni di gestione di cassa incluse nel rendiconto. Sono disponibili i seguenti fogli di lavoro di Excel.
     
       - **Transazione**: questo foglio di lavoro contiene tutte le informazioni a livello di intestazione delle transazioni di gestione di cassa.
       - **Transazioni metodo di pagamento bancario**: questo foglio di lavoro contiene tutti i dettagli delle transazioni di deposito bancario.
       - **Transazioni di pagamento in cassaforte**: questo foglio di lavoro contiene tutti i dettagli delle transazioni di deposito in cassaforte.
       - **Riepilogo incassi**: questo foglio di lavoro contiene tutti i dettagli delle transazioni di riepilogo incassi.
       - **Transazione ricavi/spese**: questo foglio di lavoro contiene tutti i dettagli delle righe delle transazioni ricavi/spese.
       - **Transazioni di pagamento**: questo foglio di lavoro contiene tutte le informazioni correlate ai pagamenti per l'operazione **Paga fattura**, oltre alla transazione ricavi/spese.

3.  Le convalide non vengono eseguite durante la pubblicazione delle transazioni modificate in blocco. È necessario assicurarsi che tutte le modifiche siano accurate e la fedeltà dei dati in tutti i fogli di lavoro venga mantenuta. Ad esempio, se si desidera modificare la data delle transazioni per gestire scenari in cui è chiuso il periodo fiscale o di inventario per le transazioni di vendita al dettaglio aperte, sarà necessario modificare la data in tutti i fogli di lavoro di Excel che includono la colonna **Data attività**. Per convalidare le transazioni dopo che sono state modificate, è possibile utilizzare **Riconvalida transazioni** nella pagina **Rendiconti di vendita al dettaglio**.
