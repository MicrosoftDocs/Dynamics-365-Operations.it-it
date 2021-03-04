---
title: Modificare e controllare le transazioni cash-and-carry e di gestione di cassa
description: In questo argomento viene descritto come modificare e controllare le transazioni cash-and-carry e di gestione di cassa in Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: c809f379dbd6824542d0b1768cfbf44f37461f4c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010201"
---
# <a name="edit-and-audit-cash-and-carry-and-cash-management-transactions"></a>Modificare e controllare le transazioni cash-and-carry e di gestione di cassa

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come modificare e controllare le transazioni cash-and-carry e di gestione di cassa in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I clienti Dynamics 365 Commerce utilizzano un'applicazione POS del produttore oltre che applicazioni POS di terze parti. Nel caso dell'applicazione POS del produttore, le transazioni vengono inserite in Commerce Headquarters dai canali mediante un processo batch. Nel caso di applicazioni di terze parti, le transazioni vengono inserite in Commerce Headquarters tramite integrazione. In entrambi i casi, dopo che le transazioni sono state inserite in Commerce Headquarters, è necessario eseguire un processo di verifica della coerenza. Tale processo esegue diverse convalide sulle transazioni, in modo che solo le transazioni convalidate correttamente vengano inserite nel rendiconto da registrare in Commerce Headquarters.

Le transazioni di Commerce non superano la convalida per diversi motivi. Un bug nel codice di integrazione o nell'applicazione POS può causare dati incoerenti. In alternativa, un errore dell'utente potrebbe causare dati incoerenti. Ad esempio, un utente elimina un prodotto dopo che è stato sincronizzato con il canale oppure chiude un periodo fiscale senza registrare le transazioni per quel periodo. Sebbene queste transazioni vengano contrassegnate ed escluse dai rendiconti, possono interrompere il processo di registrazione quotidiana delle vendite nella contabilità finanziaria di un cliente. In Commerce, è possibile modificare le transazioni che non superano la convalida e allo stesso tempo gestire il controllo di tutte le modifiche.

## <a name="edit-transactions"></a>Modificare le transazioni

In Commerce versione 10.0.5, le uniche transazioni che possono essere modificate sono le transazioni cash-and-carry, come vendite e resi. Gli ordini dei clienti e gli ordini online non possono essere modificati. In Commerce versione 10.0.6 e successive, è possibile modificare anche le transazioni di gestione di cassa.

Per modificare le transazioni in Commerce Headquarters, seguire questi passaggi.

1. Installare [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. In Commerce Headquarters, aprire l'area di lavoro **Dati finanziari punto vendita**. Il riquadro **Errori di convalida transazioni** fornisce una visualizzazione pre-filtrata della pagina della transazione che non ha soddisfatto una o più regole di convalida.
1. Aprire la pagina della transazione, selezionare il record che non ha superato la convalida, selezionare **Componente aggiuntivo per Office** e quindi selezionare **Modifica transazione selezionata**. Viene aperto un file Excel che mostra i dettagli della transazione selezionata. Questo file contiene i seguenti fogli di lavoro:

    - **Righe**: questo foglio di lavoro contiene le righe di intestazione e di prodotto per la transazione e i dati correlati della transazione.
    - **Pagamenti**: questo foglio di lavoro contiene i dettagli delle righe di pagamento della transazione.
    - **Sconti**: questo foglio di lavoro contiene i dettagli relativi agli sconti della transazione.
    - **Imposte**: questo foglio di lavoro contiene i dettagli relativi alle imposte della transazione.
    - **Spese**: questo foglio di lavoro contiene i dati relativi alle spese della transazione.

1. Nel file di Excel, modificare i campi appropriati, quindi caricare i dati nuovamente in Commerce Headquarters utilizzando la funzionalità di pubblicazione del componente aggiuntivo Dynamics Excel. Una volta pubblicati i dati, le modifiche si rifletteranno nel sistema. Durante la pubblicazione non viene effettuata alcuna convalida delle modifiche apportate dagli utenti.
1. È possibile visualizzare un audit trail completo delle modifiche selezionando **Visualizza audit trail** nell'intestazione **Transazione di vendita al dettaglio** per le modifiche a livello di intestazione e nella sezione e nel record pertinenti nella pagina della transazione appropriata. Ad esempio, tutte le modifiche relative alle righe di vendita verranno visualizzate nella pagina **Transazioni di vendita**, mentre tutte le modifiche relative ai pagamenti verranno visualizzate nella pagina **Transazioni di pagamento**. I seguenti dettagli del controllo vengono mantenuti per le modifiche:

    - Data e ora modifica
    - Campo
    - Valore precedente
    - Nuovo valore
    - Autore modifica

1. Dopo che le modifiche sono state apportate e pubblicate, eseguire l'opzione **Convalida transazioni punto vendita** per verificare che le modifiche siano coerenti e valide.

> [!NOTE]
> È possibile modificare solo le transazioni che non hanno superato la convalida. Per modificare una transazione che ha superato la convalida, cambiare lo stato di convalida della transazione in **Errore** o **Nessuno**, quindi pubblicare la modifica. È quindi possibile modificare i dati nell'intestazione o in qualsiasi altro record figlio della transazione e pubblicare l'intestazione o i record.

## <a name="bulk-edit-transactions-that-are-linked-to-a-statement"></a>Modificare in blocco le transazioni collegate a un rendiconto

Commerce versione 10.0.6 e successive supportano l'opzione per la modifica in blocco delle transazioni a livello di rendiconto.

Per modificare in blocco le transazioni collegate a un rendiconto in Commerce Headquarters, effettuare le seguenti operazioni:

1. Aprire la pagina **Rendiconti** e selezionare il rendiconto che contiene le transazioni da modificare.
1. Selezionare il pulsante **Apri in Microsoft Office**.
1. A seconda di cosa deve essere modificato, selezionare una delle seguenti opzioni:

    - **Modifica transazioni cash-and-carry**: questa opzione consente di modificare tutte le transazioni cash-and-carry incluse nel rendiconto. Sono disponibili i seguenti fogli di lavoro di Excel:

        - **Transazione**: questo foglio di lavoro contiene tutte le informazioni a livello di intestazione delle transazioni di vendita.
        - **Transazione di vendita**: questo foglio di lavoro contiene tutte le informazioni a livello di riga delle transazioni di vendita.
        - **Transazioni di pagamento**: questo foglio di lavoro contiene tutte le informazioni delle righe di pagamento delle transazioni di vendita.
        - **Transazioni di sconto**: questo foglio di lavoro contiene tutte le informazioni delle righe di sconto delle transazioni di vendita.
        - **Transazioni fiscali**: questo foglio di lavoro contiene tutte le informazioni delle righe di imposta delle transazioni di vendita.
        - **Transazioni spese**: questo foglio di lavoro contiene tutte le informazioni delle righe addebiti delle transazioni di vendita.

    - **Modifica transazioni gestione di cassa**: questa opzione consente di modificare tutte le transazioni di gestione di cassa incluse nel rendiconto. Sono disponibili i seguenti fogli di lavoro di Excel:

        - **Transazione**: questo foglio di lavoro contiene tutte le informazioni a livello di intestazione delle transazioni di gestione di cassa.
        - **Transazioni metodo di pagamento bancario**: questo foglio di lavoro contiene tutti i dettagli delle transazioni di deposito bancario.
        - **Transazioni di pagamento in cassaforte**: questo foglio di lavoro contiene tutti i dettagli delle transazioni di deposito in cassaforte.
        - **Riepilogo incassi**: questo foglio di lavoro contiene tutti i dettagli delle transazioni di riepilogo incassi.
        - **Transazione ricavi/spese**: questo foglio di lavoro contiene tutti i dettagli delle righe delle transazioni ricavi/spese.
        - **Transazioni di pagamento**: questo foglio di lavoro contiene tutte le informazioni correlate ai pagamenti per l'operazione **Paga fattura** e alla transazione ricavi/spese.

1. Modificare le transazioni richieste.

    > [!NOTE]
    > Le convalide non vengono eseguite durante la pubblicazione delle transazioni modificate in blocco. È necessario assicurarsi che tutte le modifiche siano accurate e la fedeltà dei dati in tutti i fogli di lavoro venga mantenuta. Ad esempio, se si desidera modificare la data delle transazioni per gestire scenari in cui è chiuso il periodo fiscale o di inventario per le transazioni aperte, sarà necessario modificare la data in tutti i fogli di lavoro di Excel che includono la colonna **Data attività**. Per convalidare le transazioni dopo che sono state modificate, è possibile selezionare **Riconvalida transazioni** nella pagina **Rendiconti**. Attendere il completamento del processo di convalida prima di registrare il rendiconto.

1. Se l'aggregazione è già stata generata, aprire la pagina **Transazioni aggregate** e selezionare **Rigenera xml ordine cliente**.

## <a name="bulk-edit-transactions-that-arent-linked-to-a-statement"></a>Modificare in blocco le transazioni non collegate a un rendiconto

Commerce versione 10.0.10 e successive supportano l'opzione la modifica in blocco delle transazioni che non superano la convalida ma non sono collegate a un rendiconto.

Per modificare in blocco le transazioni non collegate a un rendiconto in Commerce Headquarters, effettuare le seguenti operazioni:

1. Aprire la pagina **Tutti i punti vendita** e selezionare il punto vendita per il quale devono essere modificate le transazioni.
1. Selezionare il pulsante **Apri in Microsoft Office**, quindi selezionare **Modifica transazioni cash-and-carry**.
1. Modificare le transazioni richieste e quindi pubblicarle.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni](edit-order-trans.md)

[Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio](edit-financial-dim.md)

[Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](create-excel-edit.md)

[Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](add-fields-excel.md)
