---
title: Invertire lo stato degli ordini di produzione
description: In questo argomento viene descritto come invertire lo stato degli ordini di produzione.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParmStatusDecrease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10816f0a6b651de24fc5b0f9b51a71b1c349e037
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211102"
---
# <a name="reverse-the-production-order-status"></a>Invertire lo stato degli ordini di produzione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come invertire lo stato degli ordini di produzione. 

L'inversione dello stato di un ordine di produzione consiste nel riportare l'ordine e tutte le operazioni associate ai cicli di lavorazione a una fase precedente del ciclo di vita di produzione. Ad esempio, un ordine di produzione ha stato **Programmato** e si riporta lo stato a **Creato**. In questo caso, il sistema deve prima modificare lo stato in **Stimato**, che è lo stato che precede immediatamente **Programmato**. Può quindi modificare lo stato nello stato desiderato, **Creato**. **Nota:** Se l'ordine ha raggiunto lo stato **Dichiarato finito**, è possibile comunque riportarlo a uno stato precedente. Tuttavia, è necessario rieseguire la stima e la programmazione di operazioni o processi, oppure entrambe, per aggiornare le informazioni sull'ordine. Questo passaggio è necessario per reimpostare anche le prenotazioni relative al consumo rimanente di articoli e di risorse operative. Nel resto di questo articolo viene descritto cosa accade quando si inverte lo stato di un ordine di produzione nei modi seguenti:

-   Da **Stimato** a **Creato**
-   Da **Programmato** a **Stimato**
-   Da **Rilasciato** a **Programmato**
-   Da **Iniziato** a **Rilasciato**

## <a name="from-estimated-to-created"></a>Da Stimato a Creato
Quando si inverte lo stato di un ordine di produzione da **Stimato** a **Creato**, il consumo per articolo che è stato calcolato per gli articoli nella distinta base (BOM) viene rimosso. Le transazioni di magazzino incluse nella riga produzione vengono eliminate e il campo **Stato rimanenze** nelle righe DBA dell'ordine di produzione viene reimpostato su **Finito**. Quando le opzioni **Acquisti derivati** e **Produzione derivata** sono selezionate, tutti gli ordini fornitore o di produzione sottostanti vengono eliminati. Se si stimano i costi dell'ordine di produzione o sono stati riservati manualmente articoli da utilizzare nella produzione, queste transazioni vengono rimosse.

## <a name="from-scheduled-to-estimated"></a>Da Programmato a Stimato
Quando si inverte lo statodi un ordine di produzione da **Programmato** a **Stimato**, le date e le ore di inizio e di fine programmate vengono rimosse. Le prenotazioni di capacità effettuate durante la programmazione vengono rimosse e i processi creati durante la programmazione dei processi vengono eliminati. Tutte le informazioni registrate sulla programmazione di operazioni e di processi nella pagina **Dettagli ordine di produzione** vengono reimpostate.

## <a name="from-released-to-scheduled"></a>Da Rilasciato a Programmato
Quando si inverte lo stato di un ordine di produzione da **Rilasciato** a **Programmato**, l'unica modifica che si verifica è il valore nel campo relativo allo stato.

## <a name="from-started-to-released"></a>Da Iniziato a Rilasciato
Quando si inverte lo stato di un ordine di produzione da **Iniziato** a **Rilasciato**, viene ripristinato lo stato precedente di tutti gli articoli dichiarati finiti. Se è stato prelevato materiale o sono state effettuate consegne in entrata o in uscita per la produzione, vengono invertite queste impostazioni. Il campo **Stato rimanenze** nelle righe DBA dell'ordine di produzione viene modificato da **Finito** a **Consumo materiali**. Se il tempo è stato registrato o le quantità sono state dichiarate finite per le operazioni del ciclo di lavorazione produzione, queste impostazioni vengono ripristinate allo stato precedente. Il campo **Stato rimanenze** viene modificato da **Finito** a **Consumo ciclo di lavorazione** nel ciclo di lavorazione produzione. Le impostazioni per tutti gli articoli registrati come in corso o semilavorati vengono ripristinate. Nella pagina **Dettagli ordine di produzione** i campi che indicano una quantità che è stata iniziata o stata dichiarata finita vengono reimpostati. Anche le date di queste transazioni vengono reimpostate.



