---
title: Panoramica gestione trasporto
description: In questo articolo viene fornita una panoramica della funzionalità di gestione del trasporto in Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "30251"
- intro-internal
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12f870c95f28e752c3c3b3dd4161d82815b9954a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897460"
---
# <a name="transportation-management-overview"></a>Panoramica gestione trasporto

[!include [banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica della funzionalità di gestione del trasporto in Supply Chain Management.

Gestione trasporto consente di utilizzare il trasporto della società e di identificare soluzioni fornitori e percorsi di trasferimento per gli ordini in ingresso e in uscita. Ad esempio, è possibile identificare il ciclo di lavorazione più veloce o la tariffa più economica per una spedizione. Nella tabella seguente vengono descritti gli scenari principali per l'uso di Gestione trasporto.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Utilità di Gestione trasporto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utilizzare i provider di servizi logistici esterni per le attività di trasporto.</td>
<td>Utilizzare Gestione trasporto per il trasporto in uscita e/o in ingresso.</td>
</tr>
<tr class="even">
<td>La flotta della società è disponibile per la consegna/prelievo e le spese di consegna vengono passate ai clienti.</td>
<td>Per i processi in uscita, è possibile utilizzare Gestione trasporto per determinare le spese di trasporto e passarle ai clienti. Tuttavia, il processo di riconciliazione fattura vettore non è obbligatorio.</td>
</tr>
<tr class="odd">
<td>La flotta specifica della società è disponibile per la consegna/prelievo, ma le spese di consegna non vengono passate ai clienti perché i prezzi dei prodotti includono il trasporto.</td>
<td>Molte delle funzionalità di gestione trasporto non sono necessarie. È tuttavia possibile utilizzare Gestione trasporto per determinare le tariffe di trasporto e modificare di conseguenza il prezzo di vendita.</td>
</tr>
<tr class="even">
<td>Il servizio di logistica viene fornito da un'altra persona giuridica della stessa società.</td>
<td><ul>
<li>È possibile utilizzare Gestione trasporto trattando l'altra persona giuridica come qualsiasi altro vettore di spedizione. Non è possibile automatizzare le transazioni economiche tra persone giuridiche. Di conseguenza, è necessario gestire le transazioni manualmente, creando, ad esempio, un ordine fornitore.</li>
<li>Nella persona giuridica che fornisce i servizi di logistica, la funzionalità Gestione trasporto può essere utilizzata per determinare le tariffe di trasporto.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a>Pianificazione del trasporto in Supply Chain Management
In Gestione trasporto, la pianificazione del trasporto può essere basata sugli ordini o sulle spedizioni create in base a tali ordini. Le spedizioni sono sempre presenti in un determinato momento, ma non sono necessarie per la pianificazione del trasporto. Gli ordini di trasferimento fanno parte dello scenario in uscita e possono essere pianificati insieme agli ordini cliente. 

![Emissione del carico.](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Trasporto in uscita
Quando si ordinano gli articoli da un fornitore e gli articoli devono essere consegnati al proprio magazzino, è consigliabile organizzare il trasporto degli articoli personalmente. È possibile utilizzare Supply Chain Management per pianificare il trasporto e la ricezione del carico in entrata. Nella seguente figura viene illustrato il flusso del processo aziendale per pianificare il trasporto per un carico in entrata. 

![Flusso di processo aziendale per il trasporto del carico in ingresso.](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Trasporto in uscita
È possibile pianificare ed elaborare un carico in uscita per spedire articoli specifici dal magazzino di una società a un cliente. È possibile utilizzare Supply Chain Management per pianificare il trasporto e la spedizione di un carico in uscita. Nella seguente figura viene illustrato il flusso del processo aziendale per la pianificazione e l'elaborazione di carichi in uscita da spedire. 

![Pianificazione ed elaborazione dei carichi in uscita.](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Allestimento del carico
Supply Chain Management offre una strategia di allestimento del carico denominata strategia di allestimento del carico basata sul volume. Questa strategia consente di utilizzare i valori massimi specificati per l'altezza e il peso nel modello di carico o di sostituire le impostazioni con nuovi valori. Per utilizzare questa strategia, selezionarla nel campo **Strategia di allestimento del carico** nella scheda dettaglio **Impostazioni** della pagina **Workbench di allestimento del carico**. Inoltre, è possibile aggiungere strategie di allestimento del carico personalizzate creando una nuova classe nella struttura a oggetti applicativi (AOT).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]