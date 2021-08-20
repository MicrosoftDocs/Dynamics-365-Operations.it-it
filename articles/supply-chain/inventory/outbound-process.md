---
title: Panoramica del processo in uscita
description: In questo argomento viene fornita una panoramica del processo in uscita in Gestione articoli.
author: perlynne
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: fa80610f35bd46ed130a99abd4448ab51ac6ccfd3fb77f55dbbab0cd1734446d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780628"
---
# <a name="outbound-process-overview"></a>Panoramica del processo in uscita

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica del processo in uscita in Gestione articoli.

## <a name="output-orders"></a>Ordini di uscita

Gli ordini di uscita vengono utilizzati per collegare righe di ordini cliente e righe di ordini di trasferimento ai processi di prelievo in uscita che utilizzano le distinte di prelievo.

Quando le distinte di prelievo vengono generate a partire da ordini cliente o ordini di trasferimento, gli ordini di uscita e le spedizioni vengono creati automaticamente. Una distinta di prelievo ha una relazione uno-a-uno con una spedizione. La spedizione degli ordini di trasferimento o il documento di trasporto degli ordini cliente possono essere elaborati dalla spedizione. 

Il diagramma seguente mostra una panoramica del processo per gli ordini di uscita. 

[![Panoramica del processo dell'ordine di uscita.](./media/outbound-order.png)](./media/outbound-order.png)

È possibile impostare regole in uscita per definire la modalità con cui il programma deve gestire il processo in uscita. È possibile utilizzare queste regole per controllare il processo di spedizione. In particolare, è possibile utilizzare le regole per determinare durante quale fase del processo è possibile inviare le spedizioni. Le impostazioni seguenti definiscono il modo in cui i processi in uscita sono gestiti.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>Stato ciclo di prelievo per ordini cliente e di trasferimento 

Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**, quindi nella scheda **Aggiornamenti**, selezionare un valore nel campo **Stato ciclo di prelievo**.

[![Campo Stato ciclo di prelievo per ordini cliente.](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

Se il campo **Stato ciclo di prelievo** è impostato su **Completato**, il processo di prelievo viene eseguito automaticamente durante il processo di generazione delle distinte di prelievo. Se il campo è impostato su **Attivato**, le righe della distinta di prelievo devono essere aggiornate manualmente.

La stessa impostazione si applica agli ordini di trasferimento. Andare a **Gestione articoli** \> **Impostazioni** \> **Parametri di gestione articoli e magazzino**, quindi nella scheda **Trasporto**, selezionare un valore nel campo **Stato ciclo di prelievo**.

[![Campo Stato ciclo di prelievo per ordini di trasferimento.](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>Termina ordine di magazzino in uscita

Andare a **Gestione articoli** \> **Impostazioni** \> **Parametri di gestione articoli e magazzino**, quindi nella scheda **Generale**, impostare l'opzione **Termina ordine di magazzino in uscita**.

[![Opzione Termina ordine di magazzino in uscita.](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

Quando il lavoratore di magazzino riduce le quantità della distinta di prelievo, le quantità dell'ordine di magazzino corrispondenti verranno rimosse dalla spedizione. Quando la distinta di prelievo viene aggiornata, le quantità rimanenti vengono registrate di nuovo nell'ordine se l'opzione **Termina ordine di magazzino in uscita** è impostata su **Sì**. Se l'opzione **Termina ordine di magazzino in uscita** è impostata su **No**, le quantità rimanenti vengono mantenute come quantità dell'ordine di uscita aperto e devono essere aggiunte a una nuova distinta di prelievo come parte della funzionalità **Ordini di uscita aperti**. 

[![Comando Ordini di uscita aperti nel menu Funzioni.](./media/open-output-order.png)](./media/open-output-order.png)

[![Menu Funzioni nella pagina Ordini di uscita aperti.](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>Riduci quantità

Il terzo parametro che è possibile utilizzare durante il processo di generazione di distinte di prelievo è **Riduci quantità**. Questo parametro viene utilizzato con l'impostazione **Prenotazione** che attiva un processo di prenotazione durante il rilascio al magazzino.

[![Parametro Riduci quantità.](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>Esempio di un processo in uscita per un ordine cliente

Per questo esempio, si ha un ordine cliente per due articoli. Durante la generazione della distinta di prelievo, si seleziona il parametro **Riduci quantità**. Pertanto, si rilasciano e si creano righe di prelievo solo per le scorte disponibili. Il prelievo deve essere registrato mediante un processo di registrazione per le distinte di prelievo (**Stato ciclo di prelievo** = **Attivato**).

Le scorte che non sono ancora state prenotate lo sono durante la generazione della distinta di prelievo. Le scorte non disponibili possono essere eliminate dall'ordine cliente o rilasciate al magazzino per l'elaborazione in uscita in seguito, quando le scorte sono disponibili per il prelievo.

[![Aggiornare la distinta di prelievo.](./media/update-picking-list.png)](./media/update-picking-list.png)

Non appena tutte le righe di prelievo sono state selezionate nella pagina **Registrazione distinta di prelievo**, la spedizione associata viene completata. Il processo per i documenti di trasporto degli ordini cliente può quindi essere inizializzato in base alle scorte prelevate.

[![Aggiornare spedizioni in uscita.](./media/outbound-shipments.png)](./media/outbound-shipments.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]