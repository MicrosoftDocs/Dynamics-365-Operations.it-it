---
title: Spedire gli ordini cliente senza immagazzinaggio
description: In questo argomento viene descritto come aggiornare un ordine cliente quando i prodotti vengono spediti al cliente.
author: omulvad
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bd90767af741760b1fbd3fd5c2b4cbbae95a477
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146401"
---
# <a name="ship-sales-orders-without-warehousing"></a>Spedire gli ordini cliente senza immagazzinaggio

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come aggiornare un ordine cliente quando i prodotti vengono spediti al cliente. La guida è applicabile al flusso di evasione non impostato per gestione magazzino (né immagazzinaggio di base né avanzato) e pertanto non richiede la registrazione del prelievo prodotto prima della spedizione. È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF. In entrambi i casi, prima di iniziare questa attività, creare un ordine cliente per un prodotto inventariato con una quantità maggiore di 1. Per evitare un errore di registrazione, è necessario verificare che la quantità disponibile del prodotto nel sito e nel magazzino selezionato nell'ordine copra la quantità dell'ordine.

## <a name="post-packing-slip-for-an-order"></a>Registrare il documento di trasporto per un ordine
1. Nel pannello di navigazione, andare a **Moduli > Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
2. Nell'elenco, trovare e selezionare l'ordine creato per l'attività.
3. Nel riquadro azioni selezionare **Preleva e imballa**.
4. Selezionare **Registra documento di trasporto**.
5. Espandere o comprimere la sezione **Parametri**.
6. Nel campo **Quantità** selezionare **Tutto**.
    - Altre opzioni includono **Consegna ora** e **Prelevato**. Se la riga ordine deve essere spedita parzialmente e il campo **Consegna ora** nella riga ordine contiene una quantità, selezionare **Consegna ora**. Se il flusso di evasione dell'organizzazione include il prelievo come processo separato che viene gestito da e registrato con una distinta di prelievo, selezionare **Prelevato**.  
    - Verificare che l'opzione **Registrazione** sia impostata su **Sì**.  
7. Impostare l'opzione **Stampa documento di trasporto** su **Sì**. La scheda **Panoramica** contiene un elenco dei documenti di trasporto da generare nella registrazione corrente. Se si spedisce un singolo ordine, in genere ci sarà un solo documento di trasporto. Tuttavia, se le righe di tale ordine devono essere spedite da siti diversi, la registrazione automaticamente verrà suddivisa nel numero appropriato dei documenti. È una condizione obbligatoria che non può essere modificata. In modo analogo, la registrazione verrà divisa in più documenti se le righe dell'ordine devono essere spedite a indirizzi di consegna diversi e i criteri di spedizione sono impostati per richiedere una divisione.  
8. Nella scheda **Righe**, selezionare la riga per la riga ordine da spedire.
9. Nel campo **Aggiornamento**, immettere un numero più basso della quantità originale.
10. Selezionare **OK**.
11. Selezionare **Sì**.
12. Chiudere la pagina.
13. Nel riquadro azioni selezionare **Opzioni**.
14. Selezionare **Cambia visualizzazione**.
15. Selezionare **Visualizzazione intestazione**.
    - Se tutte le righe dell'ordine sono state completamente spedite, lo stato dell'ordine cambia da Aperto a Consegnato.  
    - In questo esempio, la riga ordine è stata spedita parzialmente. Ecco perché lo stato dell'ordine rimane Aperto.     
    - Il campo **Stato documento** è impostato su Documento di trasporto poiché almeno una riga ordine è stata spedita.  
16. Nel riquadro azioni fare clic su **Generale**.
17. Selezionare **Quantità riga**.
18. Chiudere la pagina.
19. Nel riquadro azioni selezionare **Preleva e imballa**.
20. Selezionare **Documento di trasporto**. La pagina **Giornale di registrazione documenti di trasporto** contiene tutti i documenti di trasporto generati per l'ordine. È possibile esaminare i dettagli di ogni documento e stamparli, se si desidera.  

