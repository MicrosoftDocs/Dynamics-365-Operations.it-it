---
title: Blocco scorte
description: "Questo articolo fornisce una panoramica del blocco scorte, che fa parte del processo di ispezione qualità in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. È possibile utilizzare il blocco scorte per impedire l'elaborazione o il consumo degli articoli."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7d00aaa272de32d4ef2082bf1822125800ca8a1e
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="inventory-blocking"></a>Blocco scorte

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica del blocco scorte, che fa parte del processo di ispezione qualità in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. È possibile utilizzare il blocco scorte per impedire l'elaborazione o il consumo degli articoli.

È possibile bloccare gli articoli di magazzino in uno dei modi seguenti.
-   Manualmente
-   Creando un ordine di controllo qualità
-   Utilizzando un processo che genera un ordine di controllo qualità
-   Utilizzando il bloccaggio stato di magazzino

## <a name="blocking-items-manually"></a>Blocco manuale degli articoli
È possibile bloccare una quantità di un articolo creando una transazione nella pagina **Blocco scorte**. È possibile bloccare manualmente solo gli articoli presenti come scorte disponibili. Per le quantità bloccate manualmente, è necessario decidere se nelle attività di pianificazione devono essere incluse le entrate previste come quantità disponibile prevista. Le entrate previste sono articoli bloccati che si prevedono come scorte disponibili al termine dell'ispezione. È possibile gestire la data prevista. Per impostazione predefinita, l'opzione **Entrate previste** è selezionata per gli articoli bloccati tramite un ordine di controllo qualità. È possibile annullare il blocco manuale di una quantità eliminando la transazione nella pagina **Blocco scorte**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Blocco degli articoli tramite un ordine di controllo qualità
È possibile specificare gli articoli che devono essere controllati tramite un ordine di controllo qualità nella pagina **Ordini di controllo qualità**. Quando si crea un ordine di controllo qualità, viene bloccata la quantità specificata per un articolo. il piano di campionamento associato all'ordine di controllo qualità controlla solo la quantità di articoli che devono essere sottoposti a ispezione, non quelli bloccati. La quantità immessa nell'ordine di controllo qualità è quella bloccata, indipendentemente dalla quantità da sottoporre a ispezione in base a quanto specificato dal piano di campionamento.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Blocco degli articoli mediante un processo che genera un ordine di controllo qualità
Se un processo di controllo qualità indica che un articolo deve essere sottoposto a ispezione, una quantità di tale articolo viene bloccata automaticamente. Pertanto, quando viene generato automaticamente un ordine di controllo qualità, il piano di campionamento articoli associato all'ordine di controllo qualità controlla sia la quantità di articoli bloccata che quella sottoposta a ispezione. Se l'opzione **Bloccaggio totale** nella pagina **Campionamento articoli** è selezionata, durante l'ispezione viene bloccata, ad esempio, l'intera quantità di una riga dell'ordine fornitore indipendentemente dalla quantità di campionamento articoli.
### <a name="example"></a>Esempio

Nell'esempio seguente viene generato un ordine di controllo qualità quando viene registrato un documento di trasporto dell'ordine fornitore. Nel modulo **Associazioni di controllo qualità** la registrazione di un documento di trasporto dell'ordine fornitore viene specificata come il processo che attiva l'ordine di controllo qualità.

|Impostazione                                                                     |Azione utente                 |Risultato             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| Un'associazione di controllo qualità specifica che al momento della registrazione di un documento di trasporto dell'ordine fornitore deve essere generato un ordine di controllo qualità. L'impostazione del campionamento articoli dell'ordine di controllo qualità specifica che deve essere sottoposto a ispezione il 10% della quantità della riga dell'ordine fornitore. Se è selezionata la casella di controllo **Bloccaggio totale**, l'impostazione del campionamento articoli indica inoltre che durante l'ispezione deve essere bloccata l'intera quantità delle riga dell'ordine fornitore indipendentemente dalla quantità da sottoporre a ispezione. | Viene registrato il documento di trasporto. | Viene generato un ordine di controllo qualità. Viene sottoposto a ispezione il 10% della quantità nell'ordine fornitore dell'articolo. Viene bloccata l'intera quantità della riga dell'ordine fornitore. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Blocco degli articolo tramite il blocco dello stato di magazzino
È possibile specificare quali stati delle scorte sono stati di blocco tramite il parametro **Blocco scorte** nella pagina **Stati inventario**.  Non è possibile utilizzare gli stati di magazzino come stati di blocco per ordini di produzione, ordini cliente, ordini di trasferimento, transazioni in uscita o integrazioni di progetto. Per il lavoro in uscita, utilizzare articoli con uno stato inventario disponibile. Se si dispone di articoli con stato **Rotto** e la pianificazione generale viene eseguita su tali articoli, questi vengono considerati mancanti e l'inventario viene automaticamente rifornito.



<a name="see-also"></a>Vedere anche
--------

[Creare e gestire un blocco scorte (Guida attività)](/dynamics365/unified-operations/supply-chain/inventory/tasks/create-maintain-inventory-blocking)

[Processi di gestione qualità](quality-management-processes.md)

[Verificare la qualità delle merci (Guida attività)](/dynamics365/unified-operations/supply-chain/inventory/tasks/inspect-quality-goods)




