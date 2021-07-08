---
title: Ignorare il principio di prenotazione predefinito per i materiali in produzione
description: In questo argomento viene descritto come impostare un principio di prenotazione predefinito per ogni gruppo di modelli di articolo, in modo che possano essere applicati automaticamente principi di prenotazione diversi per ogni articolo che fa parte di una distinta base di produzione (BOM) o di una formula di ordine batch.
author: johanhoffmann
ms.date: 12/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-10
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: eb4200deed5407bef6861913cecdad7114ea68cc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270789"
---
# <a name="override-the-default-reservation-principle-for-materials-in-production"></a>Ignorare il principio di prenotazione predefinito per i materiali in produzione

[!include [banner](../includes/banner.md)]

La funzionalità *Ignora prenotazione di produzione predefinita* consente di impostare un principio di prenotazione predefinito per ogni gruppo di modelli di articoli. Pertanto, è possibile applicare automaticamente principi di prenotazione diversi per ogni articolo che fa parte di una distinta base di produzione (BOM) o di una formula di ordine batch. È possibile selezionare se ogni gruppo di modelli di articolo deve ignorare il principio di prenotazione predefinito impostato per un ordine e quale principio di prenotazione deve essere utilizzato al suo posto (*Manuale*, *Stima*, *pianificazione*, *rilascio* o *inizio*).

Quando si crea un nuovo ordine di produzione o un nuovo ordine batch, viene richiesto di selezionare il principio di prenotazione da applicare a tale ordine e a tutte le sue righe DBA o righe formula. Quando la funzionalità *Ignora prenotazione di produzione predefinita* viene utilizzata, alcune o tutte le righe della distinta base o della formula possono sostituire tale principio di prenotazione e invece utilizzare il principio di prenotazione impostato per il gruppo di modelli di articolo pertinente.

Ad esempio, se si dispone di materie prime o ingredienti che richiedono un lavoro di prelievo, la distinta base o le righe formula create per quei prodotti richiedono una prenotazione fisica, perché la prenotazione fisica è un prerequisito per la generazione del lavoro di magazzino. In genere, se desideri che la prenotazione avvenga automaticamente, seleziona uno dei seguenti principi di prenotazione: *stima*, *pianificazione*, *pubblicazione* o *inizio*. D'altra parte, se disponi di materiali o ingredienti che non richiedono un lavoro di prelievo, poiché vengono utilizzati direttamente da una posizione, in genere si seleziona il principio di prenotazione *Manuale*, che non effettua alcuna prenotazione fisica né genera alcun lavoro di prelievo.

## <a name="turn-on-the-feature"></a>Attivare la funzionalità

Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Controllo produzione*
- **Nome funzionalità:** *Ignora prenotazione di produzione predefinita*

## <a name="assign-a-production-reservation-policy-to-an-item-model-group"></a>Assegnare un criterio di prenotazione di produzione a un gruppo di modelli di articoli

1. Passare a **Gestione costi \> Impostazioni criteri contabili inventario \> Gruppi di modelli di articoli**.
1. Creare o selezionare un gruppo di modelli di articoli.
1. Nella Scheda dettaglio **Criteri di inventario**, selezionare la casella di controllo **Ignora prenotazione di produzione articolo**.
1. Nel campo **Prenotazione** selezionare il principio di prenotazione per gli articoli che appartengono al gruppo di modelli selezionato. Questi articoli includono articoli che si trovano su una distinta base o una riga formula.

    - **Manuale** - Gli articoli nel gruppo di modelli non verranno automaticamente prenotati fisicamente per la produzione. Tuttavia, possono comunque essere prenotati manualmente in base alle esigenze.
    - **Stima** - Gli articoli nel gruppo di modelli verranno prenotati fisicamente durante la stima dell'ordine di produzione.
    - **Pianificazione** - Gli articoli nel gruppo di modelli verranno prenotati fisicamente durante la pianificazione dell'ordine di produzione.
    - **Rilascio** - Gli articoli nel gruppo di modelli verranno prenotati fisicamente quando l'ordine di produzione viene rilasciato.
    - **Inizio** - Gli articoli nel gruppo di modelli verranno prenotati fisicamente all'inizio dell'ordine di produzione.

## <a name="example-using-reservation-principles-in-a-bulkpack-scenario"></a>Esempio: utilizzo dei principi di prenotazione in uno scenario di articoli imballati e di stoccaggio

Un materiale lubrificante sfuso viene prodotto in un miscelatore da 1.000 litri. Dopo che il materiale sfuso è pronto, viene pompato in diverse stazioni di rifornimento, dove vengono riempiti contenitori di diverse dimensioni. Dopo il riempimento, i contenitori vengono imballati in scatole. Quelle scatole vengono quindi imballate su pallet.

In questo scenario, viene creato un ordine batch per produrre 1.000 litri di materiale sfuso. (Questo ordine è l'ordine all'ingrosso). Quando questo ordine batch è completato, viene segnalato come finito all'ubicazione di ingresso del materiale delle stazioni di rifornimento. Viene quindi creato un ordine batch per riempire e imballare ogni formato di contenitore. (Questi ordini sono gli ordini di imballaggio.) Gli ordini di imballaggio hanno una formula che consiste nel materiale sfuso, un contenitore vuoto, un'etichetta e altri materiali di imballaggio. Poiché il materiale sfuso scorre direttamente dal serbatoio del miscelatore alle stazioni di rifornimento, non è necessario alcun lavoro di magazzino per prelevare questo ingrediente e il materiale sfuso viene consumato direttamente dal punto di ingresso. Pertanto, il principio di prenotazione è impostato su *Manuale*. Gli altri materiali vengono portati alla stazione di rifornimento tramite lavori di prelievo. Pertanto, il principio di prenotazione per queste righe è impostato su *rilascio*, ad esempio, in modo che la prenotazione avvenga automaticamente quando viene rilasciato l'ordine di imballaggio.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]