---
title: Gestione degli errori
description: In questo argomento viene descritta la gestione degli errori in Gestione cespiti.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 11f5a77dc9d36436c8ab3e0634dc98aa5d2f35ac
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347142"
---
# <a name="fault-management"></a>Gestione degli errori

[!include [banner](../../includes/banner.md)]

 

In Gestione cespiti, è possibile utilizzare Designer errori per impostare sintomi di errore, aree di errore e tipi di errore nei tipi di cespite. In questo modo, è possibile gestire gli errori rilevati nei cespiti. Inoltre, le cause di errore e i suggerimenti per la correzione degli errori possono essere registrati in un ordine di lavoro.

Il processo per la registrazione e la gestione degli errori comporta le fasi seguenti.

1. Creare un elenco di sintomi di errore, aree di errore e tipi di errore che potrebbero verificarsi nei tipi di cespite.
2. In Designer errori, impostare i sintomi, le aree di errore e i tipi di errore.

Di seguito sono riportati alcuni esempi per illustrare la differenza tra i sintomi di errore, le aree di errore e i tipi di errore.

**Sintomi di errore**

- Tensioni non bilanciate
- Cortocircuito
- Rumore
- Perdita
- Vibrazioni

**Aree di errore:**

- Elettrico
- Meccanico
- Idraulico
- Pneumatico

**Tipi di errore:**

- Bobina statore principale difettosa
- Diodo difettoso
- Bobine sporche
- Generatore difettoso
- Sensore difettoso

## <a name="create-fault-symptoms"></a>Creare un elenco di sintomi di errore

Seguire questa procedura per creare un elenco di sintomi utilizzabile in Designer errori.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Sintomi di errore**.
2. Selezionare **Nuovo** per creare un record.
3. Nel campo **Sintomo errore**, immettere un nome per il sintomo di errore.
4. Nel campo **Descrizione** immettere una descrizione.
5. Selezionare **Salva**.

## <a name="create-fault-areas"></a>Creare un elenco di aree di errore

Seguire questa procedura per creare un elenco di aree utilizzabile in Designer errori.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Aree di errore**.
2. Selezionare **Nuovo** per creare un record.
3. Nel campo **Area di errore**, immettere un nome per l'area di errore.
4. Nel campo **Descrizione** immettere una descrizione.
5. Selezionare **Salva**.

## <a name="create-fault-types"></a>Creare un elenco di tipi di errore

Seguire questa procedura per creare un elenco di tipi di errore che possono essere utilizzati in Designer errori.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Tipi di errore**.
2. Selezionare **Nuovo** per creare un record.
3. Nel campo **Tipo di errore** immettere un nome per il tipo di errore.
4. Nel campo **Descrizione** immettere una descrizione.
5. Selezionare **Salva**.

## <a name="set-up-the-fault-designer"></a>Impostare Designer errori

In Designer errori, è possibile impostare i dati dell'errore nei tipi di cespite.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Designer errori**.
2. Nel riquadro sinistro, selezionare il tipo di cespite per il quale impostare un record di errore.
3. Nella Scheda dettaglio **Sintomo errore**, selezionare **Aggiungi riga** e nel campo **Sintomo errore**, selezionare un sintomo di errore.
4. Nella Scheda dettaglio **Area di errore**, selezionare **Aggiungi riga** e nel campo **Area di errore**, selezionare un'area di errore.
5. Nella Scheda dettaglio **Tipo di errore**, selezionare **Aggiungi riga** e nel campo **Tipo di errore**, selezionare un tipo di errore.
6. Per creare rapidamente le combinazioni di tutti i sintomi, le aree e i tipi di errore esistenti per il tipo di cespite selezionato, selezionare **Crea combinazioni di errore**. Questa funzione è utile se sono stati aggiunti molti sintomi, aree e tipi di errore. È più semplice eliminare le righe di qualsiasi combinazione che non sono pertinenti al tipo di cespite che creare nuove righe manualmente.

    > [!NOTE]
    > Per copiare la configurazione di sintomi, aree e tipi di errore di un tipo di cespite nel tipo di cespite selezionato, selezionare **Copia da tipo di cespite**.

7. Selezionare **Salva** per salvare le modifiche.

![Pagina Designer errori.](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Creare un elenco di cause di errore

Attenersi alla procedura seguente per creare un elenco di cause di errore note che possono essere aggiunte a un ordine di lavoro o a una richiesta di intervento di manutenzione.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Cause errore**.
2. Selezionare **Nuovo** per creare un record.
3. Nel campo **Causa errore** immettere un nome per la causa dell'errore.
4. Nel campo **Descrizione** immettere una descrizione.
5. Selezionare **Salva**.

## <a name="create-fault-remedies"></a>Creare un elenco di rimedi agli errori

Attenersi alla procedura seguente per creare un elenco di suggerimenti per correggere gli errori che possono essere aggiunti a un ordine di lavoro o a una richiesta di intervento di manutenzione.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Errore** \> **Rimedi a errori**.
2. Selezionare **Nuovo** per creare un record.
3. Nel campo **Rimedio a errore**, immettere un nome per il rimedio all'errore.
4. Nel campo **Descrizione** immettere una descrizione.
5. Selezionare **Salva**.

> [!NOTE]
> È possibile modificare i nomi di sintomi, aree, tipi, cause e rimedi come necessario. Le modifiche ai nomi vengono automaticamente implementate nelle registrazioni di errore correlate.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]