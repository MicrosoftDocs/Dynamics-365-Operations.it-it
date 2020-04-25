---
title: Creare una nuova versione del flusso di produzione
description: Questa procedura è incentrata sulla creazione di una nuova versione del flusso di produzione.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da3b77ed459f42ef91d64066b18b07fece9efc8f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212137"
---
# <a name="create-a-production-flow-version"></a>Creare una nuova versione del flusso di produzione

[!include [banner](../../includes/banner.md)]

Questa procedura è incentrata sulla creazione di una nuova versione del flusso di produzione. Per questa procedura, i parametri di produzione di lean manufacturing e le unità di misura della classe Time devono essere definiti. È inoltre necessario definire un flusso del valore e un gruppo di produzione. Per ulteriori informazioni sui flussi e attività di produzione nel lean manufacturing, vedere i white paper sul lean manufacturing per Microsoft Dynamics AX. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-production-flow"></a>Creare un flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare un'unità operativa del flusso del valore di tipo. Un flusso del valore è un'unità operativa che comprende tutte le attività e i flussi del flusso del valore. In questa fase, le unità operative sono limitate a una persona giuridica e non hanno ulteriori funzionalità.  
7. Nel campo Gruppo di produzioni fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare un gruppo di produzione per il flusso di produzione. I gruppi di produzione consentono la definizione dei conti materiale, manodopera e WIP per un processo di produzione. Per associare il contesto di contabilità a un flusso di produzione, un gruppo di produzione deve essere selezionato.  
9. Fare clic su Salva.

## <a name="create-a-production-flow-version"></a>Creare una nuova versione del flusso di produzione
1. Scegliere Aggiungi.
2. Nel campo Data di scadenza immettere una data e un'ora.
    * Se necessario, definire una data di scadenza della versione. È possibile aggiornarla in ogni dato momento, anche per le versioni attive. È possibile utilizzarla per pianificare di eliminare una versione.  
3. Fare clic su OK.
4. Nell'elenco contrassegnare la riga selezionata.
5. Digitare un valore nel campo Unità.
6. ResolveChanges per l'unità di tempo di produzione di un'unità.
7. Nel campo Tempo di produzione di un'unità medio immettere un numero.
    * Definire il tempo medio di produzione di un'unità della versione. Per il controllo della produzione di un'unità della versione del flusso di produzione, definire un tempo medio di destinazione per la produzione di un'unità. La produzione di un'unità viene definita come quantità per periodo di tempo. Nell'esempio, il tempo di produzione di un'unità è di 0,2 ore per 10 pezzi. Per un orario di lavoro di 8 ore, corrisponde a una capacità di produttività giornaliera di 400 pezzi.  
8. Nel campo Quantità per ciclo immettere un numero.
    * Definire la quantità per ciclo correlata al tempo medio di produzione di un'unità.  
9. Attivare/disattivare l'espansione della sezione Dettagli versione.
10. Nel campo Tempo di produzione di un'unità minimo immettere un numero.
    * Definire il tempo minimo di produzione di un'unità. Il tempo minimo di produzione di un'unità deve essere minore o uguale al tempo medio di produzione di un'unità.  
11. Nel campo Tempo di produzione di un'unità massimo immettere un numero.
    * Il tempo massimo di produzione di un'unità deve essere maggiore o uguale al tempo medio di produzione di un'unità.  
12. Nel campo Periodo per durata ciclo effettiva (giorni) immettere un numero.
    * Immettere il numero di giorni nel periodo per la durata ciclo effettiva. Il periodo di durata ciclo effettiva è il numero di giorni che i processi verranno aggregati dal minuto effettivo a ritroso per calcolare la durata ciclo effettiva. Il valore può essere modificato in qualsiasi momento ed è solo utilizzato per il calcolo delle durate ciclo effettive.  
13. Fare clic su Salva.

