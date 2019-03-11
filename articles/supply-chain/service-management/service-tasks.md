---
title: Attività di assistenza tecnica
description: Utilizzare le attività di assistenza tecnica per descrivere l'attività da eseguire durante un ordine di assistenza. Tali informazioni possono essere visualizzate sia dai tecnici che dai clienti.
author: ShylaThompson
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2538a7b4a4c13a299afb37dd336f2f5d6f36a23
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "308600"
---
# <a name="service-tasks"></a>Attività di assistenza tecnica  

[!include [banner](../includes/banner.md)]

Utilizzare le attività di assistenza tecnica per descrivere l'attività da eseguire durante un ordine di assistenza.
Tali informazioni possono essere visualizzate sia dai tecnici che dai clienti.

È possibile creare attività di assistenza tecnica nella pagine **Attività di assistenza tecnica** e associarle a un determinato contratto o ordine di assistenza creando relazioni per tali attività. Ogni volta che si crea una relazione di questo tipo, è possibile creare quanto segue:

-  Note interne per l'attività, ad esempio richieste dettagliate relative all'attività di cui il tecnico deve essere informato.

-  Note esterne che possono essere visualizzate dal cliente. Potrebbero fornire una descrizione meno tecnica dell'attività da eseguire in base al contratto stipulato tra il cliente e la società di assistenza.

Una volta definita una relazione tra un'attività di assistenza tecnica e un ordine o un contratto di assistenza, è possibile specificare tale attività quando si creano le righe per l'ordine o il contratto di assistenza corrente.

Quando si generano ordini di assistenza sulla base di un contratto di assistenza, è possibile utilizzare le attività di assistenza tecnica assegnate a ogni riga del contratto per raggruppare le righe dell'ordine di assistenza in ordini di assistenza.

## <a name="create-a-service-task"></a>Creare un'attività di assistenza tecnica

1. Fare clic su **Gestione assistenza** \> **Impostazione** \> **Attività di assistenza tecnica**.
2. Creare una nuova riga.
3. Immettere l'ID e la descrizione del servizio.

## <a name="example"></a>Esempio

Un tecnico deve effettuare due interventi su una scatola ingranaggi (oggetto assistenza GB-1234) presso il cliente. Per tale cliente viene creato un contratto di assistenza e agli interventi vengono associate numerose transazioni. Di seguito sono riportati il contratto di assistenza e le relative righe per i due interventi:

### <a name="service-agreement"></a>Contratto di assistenza

| Project | Contratto di assistenza | descrizione                                  | Raggruppa   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Controllo e sostituzione di routine – GB-1234 | Gratifiche |

### <a name="service-agreement-lines"></a>Righe contratto di assistenza

| descrizione             | Tipo di transazione | Oggetto assistenza | Attività di assistenza tecnica |
|-------------------------|------------------|----------------|--------------|
| Controllo e pulizia | Ore             | GB-1234        | I/C - GB1234 |
| Travel                  | Expense          | GB-1234        | I/C - GB1234 |
| Materiali               | Articolo             | GB-1234        | I/C - GB1234 |
| Sostituzione di routine     | Ore             | GB-1234        | RR - GB1234  |
| GR-1                    | Articolo             | GB-1234        | RR - GB1234  |
| GR-5                    | Articolo             | GB-1234        | RR - GB1234  |

Alle righe del contratto di assistenza relative ai due interventi sono associate due attività di assistenza tecnica. Le attività di assistenza tecnica determinano le transazioni appartenenti a ciascun intervento. Nel primo caso, con l'attività di assistenza tecnica I/C - GB1234 vengono identificate tutte le righe del contratto di assistenza interessate dal controllo e dalla pulizia dell'oggetto GB-1234. Nel secondo caso, con l'attività di assistenza tecnica RR - GB1234 vengono identificate tutte le righe del contratto di assistenza interessate dall'esecuzione di un intervento di sostituzione di routine.

Le relazioni che collegano le attività di assistenza tecnica al contratto specifico sono le seguenti.

### <a name="service-tasks"></a>Attività di assistenza tecnica

| Attività di assistenza tecnica | Descrizione                             | Nota interna                                                                                                                 | Nota esterna                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | Controllo della scatola ingranaggi GB-1234           | Controllo visivo e meccanico e pulizia della scatola ingranaggi GB-1234.                                                              | Controllo di routine della scatola ingranaggi |
| RR - GB1234  | Sostituzione di routine di alcuni componenti della scatola ingranaggi GB-1234 | Sostituzione di routine dei componenti GR-1 e GR-5 (per le scatole ingranaggi prodotte prima del 2002, sostituzione anche del componente GR-2) | Sostituzione di routine di alcuni componenti  |

## <a name="group-service-orders"></a>Raggruppare ordini di assistenza

Quando si creano automaticamente ordini di assistenza, è possibile utilizzare le attività di assistenza tecnica come criteri per il raggruppamento. Per poter raggruppare gli ordini di assistenza in base a tali attività, è necessario definire nel contratto di assistenza che gli ordini di assistenza basati sul contratto dovranno essere raggruppati in base all'ID dell'attività di assistenza tecnica come criteri di raggruppamento iniziale.

**Effettuare il raggruppamento in base all'attività di assistenza tecnica**

1. Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.
2. Nella scheda **Impostazione** selezionare **In base all'attività di assistenza** nel campo **Combina ordini di assistenza**.


