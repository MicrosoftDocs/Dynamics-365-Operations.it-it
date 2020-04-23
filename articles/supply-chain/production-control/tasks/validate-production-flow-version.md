---
title: Convalidare un flusso e una versione di produzione
description: Questa procedura mostra come creare un nuovo flusso di produzione e una prima versione per il lean manufacturing.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c30947d01cfb85ea3dbf1aa3e4ea8e092efd18cb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210251"
---
# <a name="validate-a-production-flow-and-version"></a>Convalidare un flusso e una versione di produzione

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come creare un nuovo flusso di produzione e una prima versione per il lean manufacturing. Prerequisiti: i parametri di produzione di lean manufacturing e le unità di misura della classe Time devono essere definiti. È necessario definire un flusso del valore e un gruppo di produzione. Fare riferimento ai white paper sul lean manufacturing per familiarizzare con i concetti di flussi di produzione e attività. Questa procedura si riferisce alla persona giuridica USMF in dati dimostrativi. Tuttavia, presupponendo che la persona giuridica sia configurata per il lean manufacturing, altre persone giuridiche possono essere utilizzate.


## <a name="create-a-production-flow"></a>Creare un flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Un flusso del valore è un'unità operativa che comprende tutte le attività e i flussi del flusso del valore.   In questa fase, le unità operative sono limitate a una persona giuridica e non hanno ulteriori funzionalità.  
7. Nel campo Gruppo di produzioni fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * I gruppi di produzione consentono la definizione dei conti materiale, manodopera e WIP per un processo di produzione. Per associare il contesto di contabilità a un flusso di produzione, un gruppo di produzione deve essere selezionato.  
9. Fare clic su Salva.

## <a name="create-a-production-flow-version"></a>Creare una nuova versione del flusso di produzione
1. Scegliere Aggiungi.
2. Nel campo Data di scadenza immettere una data e un'ora.
    * È possibile aggiornare la data di scadenza della versione in ogni dato momento, anche per le versioni attive. Utilizzare la scadenza della versione per pianificare l'eliminazione di una versione.  
3. Fare clic su OK.
4. Nell'elenco contrassegnare la riga selezionata.
5. Digitare un valore nel campo Unità.
6. Selezionare l'unità del tempo di produzione di un'unità.
7. Nel campo Tempo di produzione di un'unità medio immettere un numero.
    * Per il controllo della produzione di un'unità della versione del flusso di produzione, definire un tempo medio di destinazione per la produzione di un'unità.   La produzione di un'unità viene definita come quantità per periodo di tempo.  Nell'esempio dato, il tempo di produzione di un'unità è di 0,2 ore per 10 pezzi. Per un orario di lavoro di 8 ore, corrisponde a una capacità di produttività giornaliera di 400 pezzi.  
8. Nel campo Quantità per ciclo immettere un numero.
9. Espandere o comprimere la sezione Dettagli versione.
10. Nel campo Tempo di produzione di un'unità minimo immettere un numero.
    * Il tempo minimo di produzione di un'unità deve essere minore o uguale al tempo medio di produzione di un'unità.  
11. Nel campo Tempo di produzione di un'unità massimo immettere un numero.
    * Il tempo massimo di produzione di un'unità deve essere maggiore o uguale al tempo medio di produzione di un'unità.  
12. Immettere il numero di giorni nel periodo per la durata ciclo effettiva.
    * Il periodo di durata ciclo effettiva è il numero di giorni che i processi verranno aggregati dal minuto effettivo a ritroso per calcolare la durata ciclo effettiva. Il valore può essere modificato in qualsiasi momento ed è solo utilizzato per il calcolo delle durate ciclo effettive.  
13. Fare clic su Salva.

