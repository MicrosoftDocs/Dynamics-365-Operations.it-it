---
title: Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni
description: In questo argomento viene descritto come modificare e controllare le transazioni di ordini online e ordini cliente asincroni in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 0fee5ef7ad61e9581e7b2797bb1bd26b1a48ddbd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221776"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come modificare e controllare le transazioni di ordini online e ordini cliente asincroni in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Tra le versioni 10.0.5 e 10.0.6 di Commerce è stato aggiunto il supporto per la modifica delle transazioni cash-and-carry (come vendite e resi) e transazioni di gestione di cassa (come l'immissione del fondo cassa e la rimozione del metodo di pagamento). In Commerce versione 10.0.7 è stato aggiunto il supporto per la modifica delle transazioni degli ordini online e delle transazioni degli ordini cliente asincroni.

## <a name="edit-and-audit-order-transactions"></a>Modificare e controllare le transazioni degli ordini

Per modificare e controllare le transazioni di ordini in Commerce Headquarters, seguire questi passaggi.

1. Installare [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. Nella pagina **Parametri di vendita al dettaglio**, nella scheda **Ordini cliente**, nella Scheda dettaglio **Ordine**, specificare un codice sospensione per **Codice sospensione per errori di sincronizzazione dell'ordine**.
1. Aprire l'area di lavoro **Dati finanziari punto vendita**. I riquadri **Errori di sincronizzazione ordini online** ed **Errori di sincronizzazione ordini cliente** forniscono una visualizzazione prefiltrata della pagina delle transazioni di vendita al dettaglio. Ciascuno mostra i record delle transazioni che non hanno completato la sincronizzazione per il tipo di ordine corrispondente.
1. Aprire la pagina **Errori di sincronizzazione ordini online** o la pagina **Errori di sincronizzazione ordini cliente**. Selezionare un record per visualizzare i dettagli dell'errore di sincronizzazione. La Scheda dettaglio **Stato sincronizzazione** fornisce i seguenti dettagli sull'errore:

    - Stato ordine in sospeso
    - Dettagli errori ordini
    - Data e ora modifica
    - Conteggio tentativi

1. Se i dettagli sull'errore indicano che il record deve essere corretto, selezionare **Componente aggiuntivo per Office** e quindi selezionare **Modifica transazione selezionata**. Viene aperto un file Excel che mostra i dettagli della transazione selezionata.

    - Se la transazione che viene modificata è una transazione di ordine online, il file Excel contiene i seguenti fogli di lavoro:

        - **Transazione**: questo foglio di lavoro contiene i dettagli dell'intestazione per la transazione.
        - **Transazione di vendita**: questo foglio di lavoro contiene i dettagli delle righe per la transazione.
        - **Transazioni di pagamento**: questo foglio di lavoro contiene i dettagli delle righe di pagamento della transazione.
        - **Transazioni di sconto**: questo foglio di lavoro contiene i dettagli relativi agli sconti della transazione.
        - **Transazioni fiscali**: questo foglio di lavoro contiene i dettagli relativi alle imposte della transazione.
        - **Transazioni spese**: questo foglio di lavoro contiene i dati relativi alle spese della transazione.

    - Se la transazione che viene modificata è una transazione di ordine cliente asincrono, il file Excel contiene i seguenti fogli di lavoro:

        - **Righe**: questo foglio di lavoro contiene i dettagli delle righe e dell'intestazione per la transazione.
        - **Pagamenti**: questo foglio di lavoro contiene i dettagli delle righe di pagamento della transazione.
        - **Sconti**: questo foglio di lavoro contiene i dettagli relativi agli sconti della transazione.
        - **Imposte**: questo foglio di lavoro contiene i dettagli relativi alle imposte della transazione.
        - **Spese**: questo foglio di lavoro contiene i dati relativi alle spese della transazione.

1. Nel file Excel, nel campo **Stato ordine in sospeso**, immetti **Modifica** e quindi pubblica la modifica. In questo modo, impedisci che il processo **Sincronizza ordine** in esecuzione in modalità batch ignori questo record durante l'elaborazione.
1. Nel file di Excel, modificare i campi appropriati, quindi caricare i dati nuovamente in Commerce Headquarters utilizzando la funzionalità di pubblicazione del componente aggiuntivo Dynamics Excel. Una volta pubblicati i dati, le modifiche si rifletteranno nel sistema. Durante la pubblicazione non viene effettuata alcuna convalida delle modifiche apportate dagli utenti.
1. È possibile visualizzare un audit trail completo delle modifiche selezionando **Visualizza audit trail** nell'intestazione **Transazione di vendita al dettaglio** per le modifiche a livello di intestazione e nella sezione e nel record pertinenti nella pagina della transazione appropriata. Ad esempio, tutte le modifiche relative alle righe di vendita verranno visualizzate nella pagina **Transazioni di vendita**, mentre tutte le modifiche relative ai pagamenti verranno visualizzate nella pagina **Transazioni di pagamento**. I seguenti dettagli del controllo vengono mantenuti per le modifiche:

    - Data e ora modifica
    - Campo
    - Valore precedente
    - Nuovo valore
    - Autore modifica

1. Dopo aver apportato e pubblicato le modifiche, selezionare **Sincronizza ordine** per avviare immediatamente il processo di sincronizzazione. In alternativa, è possibile attendere che il processo di sincronizzazione in esecuzione in modalità batch elabori la transazione.

Per impostazione predefinita, dopo che gli ordini sono stati sincronizzati, vengono messi in uno stato di sospensione, in base al codice di sospensione definito nei parametri di Commerce. La sospensione sugli ordini deve essere rimossa prima che gli ordini possano essere ulteriormente elaborati per l'evasione o altre operazioni.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa](edit-cash-trans.md)

[Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio](edit-financial-dim.md)

[Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](create-excel-edit.md)

[Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]