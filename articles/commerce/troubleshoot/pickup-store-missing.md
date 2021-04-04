---
title: Il punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso cui effettuare il ritiro
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso i quali è possibile ritirare gli articoli.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 652f5f1a779a412c21c18814071ba0fb7dd2e155
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585400"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>Il punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso cui effettuare il ritiro

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso i quali è possibile ritirare gli articoli.

## <a name="description"></a>Descrizione

Un punto vendita al dettaglio non viene visualizzato nell'elenco dei punti vendita presso i quali è possibile ritirare gli articoli.

## <a name="resolution"></a>Risoluzione

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Configurare la longitudine e la latitudine per l'indirizzo del punto vendita in Commerce Headquarters

Per configurare la longitudine e la latitudine per l'indirizzo del punto vendita in Commerce Headquarters, procedere come segue.

1. Passare a **Retail e Commerce \> Canali \> Punti vendita \> Tutti i punti vendita**.
1. Trovare il punto vendita che deve essere visualizzato tra le opzioni di ritiro nel sito di e-commerce. Prendere nota del relativo valore **Numero unità operativa**.
1. Selezionare **Amministrazione organizzazione \> Organizzazioni \> Unità operative**.
1. Cercare il numero di unità operativa annotata in precedenza, quindi selezionare l'unità operativa nei risultati della ricerca.
1. Nella Scheda dettaglio **Indirizzi**, selezionare **Altre opzioni** e quindi selezionare **Avanzate**.
1. Nella Scheda dettaglio **Generale**, assicurarsi che i campi **Longitudine** e **Latitudine** siano impostati correttamente. Come parte di questo passaggio, assicurarsi che i valori siano specificati correttamente come numeri positivi o negativi.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Configurare gruppi di adempimento in Commerce Headquarters

Per configurare gruppi di adempimento in Commerce Headquarters, seguire questi passaggi.

1. Andare a **Retail e Commerce \> Canali \> Punti vendita online**.
1. Selezionare il punto vendita online da configurare.
1. Nel riquadro Azioni, selezionare **Imposta**, quindi selezionare **Assegnazione gruppo di adempimento**.
1. Nella pagina **Assegnazione gruppo di adempimento**, selezionare il gruppo di adempimento per il punto vendita online.
1. In **Impostazione**, assicurarsi che il punto vendita al dettaglio sia configurato correttamente per il gruppo di adempimento.

## <a name="additional-resources"></a>Risorse aggiuntive 

[Creare una unità operativa](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[Impostare un canale online](../channel-setup-online.md)
