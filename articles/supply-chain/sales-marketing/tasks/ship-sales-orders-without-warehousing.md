--- 
title: Spedire gli ordini cliente senza immagazzinaggio
description: La guida dimostra come aggiornare un ordine cliente quando i prodotti vengono spediti al cliente.
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: a98e58b26432ee01e62d60f81a768f14568e34e4
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="ship-sales-orders-without-warehousing"></a>Spedire gli ordini cliente senza immagazzinaggio

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

La guida dimostra come aggiornare un ordine cliente quando i prodotti vengono spediti al cliente. La guida è applicabile al flusso di evasione non impostato per gestione magazzino (né immagazzinaggio di base né avanzato) e pertanto non richiede la registrazione del prelievo prodotto prima della spedizione. È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF. In entrambi i casi, prima di iniziare questa attività, creare un ordine cliente per un prodotto inventariato con una quantità maggiore di 1. Per evitare un errore di registrazione, è necessario verificare che la quantità disponibile del prodotto nel sito e nel magazzino selezionato nell'ordine copra la quantità dell'ordine.


## <a name="post-packing-slip-for-an-order"></a>Registrare il documento di trasporto per un ordine
1. Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.
2. Nell'elenco, trovare e selezionare l'ordine creato per l'attività.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel riquadro azioni fare clic su Preleva e imballa.
5. Fare clic su Registra documento di trasporto.
6. Espandere o comprimere la sezione Parametri.
7. Nel campo Quantità selezionare "Tutto".
    * Altre opzioni sono Consegna ora e Prelevato. Se la riga ordine deve essere spedita parzialmente e il campo Consegna ora nella riga ordine contiene una quantità, selezionare Consegna ora. Se il flusso di evasione dell'organizzazione include il prelievo come processo separato che viene gestito da e registrato con una distinta di prelievo, selezionare Prelevato.  
    * Verificare che l'opzione Registrazione sia impostata su Sì.  
8. Impostare l'opzione Stampa documento di trasporto su Sì.
    * La scheda Panoramica contiene un elenco dei documenti di trasporto da generare nella registrazione corrente. Se si spedisce un singolo ordine, in genere ci sarà un solo documento di trasporto. Tuttavia, se le righe di tale ordine devono essere spedite da siti diversi, la registrazione automaticamente verrà suddivisa nel numero appropriato dei documenti. È una condizione obbligatoria che non può essere modificata. In modo analogo, la registrazione verrà divisa in più documenti se le righe dell'ordine devono essere spedite a indirizzi di consegna diversi e i criteri di spedizione sono impostati per richiedere una divisione.  
9. Nella scheda Righe, selezionare la riga per la riga ordine da spedire.
10. Nel campo Aggiornamento, immettere un numero più basso della quantità originale.
11. Fare clic su OK.
12. Fare clic su Sì.
13. Chiudere la pagina.
14. Nel riquadro azioni fare clic su Opzioni.
15. Fare clic su Cambia visualizzazione.
16. Fare clic su Visualizzazione intestazione.
    * Se tutte le righe dell'ordine sono state completamente spedite, lo stato dell'ordine cambia da Aperto a Consegnato.  
    * In questo esempio, la riga ordine è stata spedita parzialmente. Ecco perché lo stato dell'ordine rimane Aperto.     
    * Il campo Stato documento è impostato su Documento di trasporto poiché almeno una riga ordine è stata spedita.  
17. Nel riquadro azioni fare clic su Generale.
18. Fare clic su Quantità riga.
19. Chiudere la pagina.
20. Nel riquadro azioni fare clic su Preleva e imballa.
21. Fare clic su Documento di trasporto.
    * La pagina Giornale di registrazione documenti di trasporto contiene tutti i documenti di trasporto generati per l'ordine. È possibile esaminare i dettagli di ogni documento e stamparli, se necessario.  


