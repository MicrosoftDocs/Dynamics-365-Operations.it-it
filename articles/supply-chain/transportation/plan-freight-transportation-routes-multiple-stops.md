---
title: Pianificare percorsi di trasporto di carichi con più fermate
description: In questo articolo vengono descritti i vari elementi utilizzati per pianificare i percorsi di trasporto in Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate, TMSRouteSchedule, TMSRouteRateDetail
audience: Application User
ms.reviewer: kamaybac
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e3d316b5bed67e84fdd5cec8b518069c053436d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671593"
---
# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>Pianificare percorsi di trasporto di carichi con più fermate

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti i vari elementi utilizzati per pianificare i percorsi di trasporto in Dynamics 365 Supply Chain Management.

È possibile utilizzare piani e guide di percorsi per percorsi di trasporto complessi che hanno più fermate. Se verrà utilizzato lo stesso percorso a intervalli regolari, è possibile impostare un percorso programmato.

## <a name="route-plans"></a>Piani ciclo di lavorazione
Un piano di percorso contiene segmenti di percorso che forniscono informazioni sulle fermate visitate e i vettori utilizzati per ciascun segmento. È necessario definire le fermate nel percorso come hub. Un hub può essere un fornitore, un magazzino, un cliente o semplicemente un luogo di ricaricamento in cui si cambia vettore. Per ogni segmento, è possibile definire "tariffe correnti" per spese varie. Di seguito sono riportati alcuni esempi.

-   Spese di viaggio verso i segmenti specificati
-   Spese per un prelievo di merci
-   Spese per la consegna di merci

Ogni piano di percorso deve essere associato a una guida di percorso.

## <a name="route-guides"></a>Guide ciclo di lavorazione
Una guida di percorso definisce i criteri per abbinare un carico a un piano di percorso specifico. Ad esempio, è possibile specificare un hub di origine e un hub di destinazione, i limiti per il volume del contenitore o peso e un vettore di spedizione, servizio o gruppo. Le guide di percorso sono disponibili nella pagina **'Tariffa workbench ciclo di lavorazione**, i dove carichi possono essere abbinati ai percorsi manualmente o automaticamente. Se la guida di percorso si riferisce a un percorso programmato, è disponibile anche nella pagina **Workbench di allestimento del carico**.

## <a name="scheduled-routes"></a>Cicli di lavorazione programmati
Un percorso programmato è un piano di percorso predefinito che dispone di una programmazione per le date di spedizione. I percorsi programmati e non programmati differiscono nel modo in cui i carichi vengono assegnati. Se si assegna un percorso non programmato utilizzando la tariffa workbench ciclo di lavorazione, solo il carico e la guida di percoso sono convalidati. Se si assegna un percorso programmato, le date e gli indirizzi di ordini ei hub e la data sul piano di percorso vengono anche considerati. Non è necessario utilizzare la pagina Tariffa workbench ciclo di lavorazione per assegnare manualmente i carichi a un percorso programmato. Al contrario, è possibile utilizzare il Workbench di allestimento del carico per suggerire che i carichi vengano generati in base agli indirizzi dei clienti e alle date di consegna degli ordini cliente per un dato percorso programmato. Per i percorsi programmati, il piano di percorso avrò hub di origine e destinazione fissi. In genere, il vettore e il servizio di spedizionesaranno gli stessi per tutti i segmenti, ma possono differire. Gli hub di destinazione vengono creati utilizzando i codici postali dei clienti visitati nel percorso. È possibile definire diverse programmazioni di percorso per piano di percorso. Il piano di percorso deve essere associato a una guida di percorso. Tuttavia, per i percorsi programmati, il piano può essere associato a una sola guida di percorso. La programmazione dei percorsi viene utilizzata solo per creare i percorsi effettivi nella pagina **Programmazione ciclo di lavorazione**. È possibile utilizzare il modello di carico predefinito per proporre carichi nel workbench di allestimeno del carico.

## <a name="load-building-workbench"></a>Workbench di allestimento del carico
Il workbench di allestimento del carico utilizza gli indirizzi dei clienti e le date di consegna di ordini cliente e i percorsi programmati disponibili, per proporre un carico. Per impostazione predefinita, i valori dal percorso vengono immessi nel workbench. Tuttavia, è possibile selezionare una data "da" precedente alla data "da" nel percorso. Quando viene proposto un carico, l'indirizzo di consegna e data di consegna di tutti gli ordini cliente aperti vengono controllati. Se il codice postale dell'indirizzo di consegna corrisponde al codice postale di un hub nel piano di percorso e la data di consegna è compresa nell'intervallo selezionato nei criteri, l'ordine cliente viene proposto per il carico. Viene considerata anche la capacità del modello di carico. Viene proposto un solo carico alla volta. Se si dispone di un ordine cliente che non è incluso, può essere necessario utilizzare un modello di carico diverso (ad esempio, un modello di carico per un autocarro o un contenitore più grande) o pianificare un'ulteriore consegna.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]