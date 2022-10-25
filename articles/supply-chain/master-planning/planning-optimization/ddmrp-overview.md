---
title: Panoramica della pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP)
description: Questo articolo fornisce informazioni sulla pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP), una metodologia di pianificazione basata sul disaccoppiamento di offerta e domanda.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 31b45fdb92cf8a590ff77104f0c8015fb4d329d5
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689490"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Panoramica della pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Per anni, le società hanno usato la pianificazione dei fabbisogni di materiali (MRP) come sistema per calcolare i materiali e i componenti richiesti per fabbricare un prodotto. Tuttavia, le supply chain ora sono cambiate. Le parti hanno lead time più lunghi perché sempre più spesso provengono da oltreoceano. Di conseguenza, molte società hanno iniziato ad avere problemi di gestione del magazzino e si sono trovate ad affrontare carenze di scorte o scorte in eccesso. Le fluttuazioni del mercato sono aumentate (un problema talvolta acuito da previsioni non accurate) e i clienti chiedono con sempre maggiore frequenza prodotti con un lead time più breve. Questo ha portato a carenze della supply chain a livello mondiale. Inoltre, spesso gli strumenti MRP richiedono ai pianificatori interventi continui in vari ambiti. Così, è difficile capire cosa è veramente importante. Spesso, la soluzione a molti di questi problemi è rappresentata dal passaggio alla pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP).

DDMRP è una metodologia di pianificazione basata sul disaccoppiamento di offerta e domanda. Questo disaccoppiamento si ottiene impostando articoli di punti di disaccoppiamento. Per questi articoli vengono mantenuti dei buffer per garantire costantemente un livello di scorte adeguato. Il disaccoppiamento di offerta e domanda permette di prevenire il cosiddetto "effetto frusta", perché la variabilità della domanda non si ripercuote su tutta la supply chain. (L'*effetto frusta* si riferisce al modo in cui minime fluttuazioni della domanda a livello di vendita al dettaglio possono causare progressivamente fluttuazioni di entità maggiore a livello di vendita all'ingrosso, distributore, produttore e fornitore di materie prime). Ogni buffer copre l'uso medio di una parte e può essere adeguato per coprire eventuali picchi della domanda.

DDMRP si è dimostrata una metodologia di pianificazione efficace per gli ambienti variabili in cui i tempi di tolleranza dei clienti sono più brevi rispetto ai lead time cumulativi.

## <a name="the-five-components-of-ddmrp"></a>I cinque componenti di DDMRP

DDMRP prevede cinque componenti sequenziali (passaggi). I primi tre componenti essenzialmente definiscono la configurazione iniziale e in evoluzione di un modello di pianificazione del fabbisogno di materiale basato sulla domanda. Gli ultimi due componenti definiscono le operazioni quotidiane della metodologia.

1. **[Posizionamento delle scorte strategiche](ddmrp-inventory-positioning.md)**: identificare i punti di disaccoppiamento nella rete della supply chain. I punti di disaccoppiamento sono punti specifici della supply chain in cui si posiziona un buffer delle scorte che viene monitorato e rifornito.
2. **[Profili e livelli di buffer](ddmrp-buffer-profile-and-levels.md)**: per ogni punto di disaccoppiamento, identificare le dimensioni del buffer (quantità minima e massima e punto di riordino) e la quantità di riordino.
3. **[Rettifiche dinamiche del buffer](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)**: adeguare i livelli di buffer in base a vari parametri operativi o a eventi futuri pianificati.
4. **[Pianificazione basata sulla domanda](ddmrp-planning.md)**: generare ordini di fornitura man mano che sono necessari. Questi ordini di fornitura includono ordini di produzione, ordini di acquisto e ordini di trasferimento delle scorte
5. **[Esecuzione altamente collaborativa e visibile](ddmrp-visual-and-collaborative-execution.md)**: eseguire gli ordini di fornitura con l'ausilio della visualizzazione.

La metodologia DDMRP viene generalmente usata dai produttori con distinte base su più livelli. Tuttavia, può anche essere applicata alle reti di distribuzione e vendita al dettaglio.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP in Dynamics 365 Supply Chain Management

DDMRP è inclusa in Microsoft Dynamics 365 Supply Chain Management e non richiede costi per licenze aggiuntive. In Supply Chain Management, la funzionalità DDMRP è stata aggiunta al modulo **Pianificazione generale** esistente. Tuttavia, richiede l'uso del componente aggiuntivo Ottimizzazione pianificazione. 

La funzionalità DDMRP è integrata con i setup di pianificazione esistenti in Supply Chain Management e viene usata congiuntamente a questi per ottenere la corretta configurazione di pianificazione per l'azienda. È controllata da un nuovo codice di copertura, completamente diverso rispetto a periodo, minimo/massimo, fabbisogno e così via. Non è un nuovo modulo e non sostituisce la funzionalità di pianificazione esistente. Rappresenta invece uno strumento aggiuntivo con nuove funzionalità.
