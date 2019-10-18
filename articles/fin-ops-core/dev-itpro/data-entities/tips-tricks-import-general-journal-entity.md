---
title: Procedure consigliate per l'importazione di giustificativi utilizzando l'entità giornale di registrazione generale
description: In questo argomento vengono forniti suggerimenti per l'importazione dei dati nel giornale di registrazione generale tramite l'entità giornale di registrazione generale.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 167afa70bfa35b966081709f1587d61d401d318f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184349"
---
# <a name="best-practices-for-importing-vouchers-by-using-the-general-journal-entity"></a>Procedure consigliate per l'importazione di giustificativi utilizzando l'entità giornale di registrazione generale

[!include [banner](../includes/banner.md)]

In questo argomento vengono forniti suggerimenti per l'importazione dei dati nel giornale di registrazione generale tramite l'entità giornale di registrazione generale.

È possibile utilizzare l'entità giornale di registrazione generale per importare i giustificativi che dispongono di un tipo di conto o di conto di contropartita **Contabilità generale, Cliente, Fornitore o Bancario**. Il giustificativo può essere immesso come riga unica, usando sia il campo **Conto** che il campo **Conto di contropartita** , o come giustificativo con più righe. In questo caso viene utilizzato solo il campo **Conto** e il campo **Conto di contropartita** viene lasciato vuoto su ogni riga. L'entità giornale di registrazione generale non supporta tutti i tipi di conto. Invece, altre entità esistono per gli scenari in cui sono necessarie diverse combinazioni di tipi di conto. Ad esempio, per importare una transazione di progetto, utilizzare l'entità giornale di registrazione spese di progetto. Ogni entità è progettata per supportare scenari specifici. Questo significa che campi aggiuntivi potrebbero essere disponibili in entità per questi scenari ma non in entità di uno scenario diverso.

## <a name="setup"></a>Imposta
Prima di importare utilizzando l'entità giornale di registrazione generale, convalidare l'impostazione seguente:

- **Impostazione di sequenza numerica per il numero di batch del giornale di registrazione** – per impostazione predefinita, quando si importa utilizzando l'entità giornale di registrazione generale, il numero batch del giornale di registrazione utilizza la sequenza numerica definita nei parametri di contabilità generale. Se si imposta la sequenza numerica per il numero di batch del giornale di registrazione su **Manuale**, un numero predefinito non viene applicato. Questa impostazione non è supportata.
- **Configurazione della dimensione finanziaria** – ogni organizzazione deve definire l'ordine delle dimensioni finanziarie quando le entità vengono utilizzate per importare le transazioni. L'ordine viene definito per il formato **Integrazione dimensioni contabilità generale** in **Contabilità generale** &gt; **Piano dei conti** &gt; **Dimensioni** &gt; **Configurazione dimensione finanziaria per integrazione applicazioni** &gt; **Seleziona entità di dati**. I segmenti del conto CoGe da importare devono avere lo stesso ordine. In caso contrario, si verificherà un errore durante l'importazione.

## <a name="general-journal-entity-setup"></a>Impostazione dell'entitò giornale di registrazione generale
Due impostazioni nella gestione dei dati influiscono sulla modalità di applicazione del numero batch o sul numero giustificativo del giornale di registrazione predefinito:

- **Elaborazione basata su set** (nell'entità di dati)
- **Generata automaticamente** (per il mapping dei campi)

Nelle sezioni seguenti viene descritto l'effetto di queste impostazioni e anche spiegato come vengono generati i numeri batch del giornale di registrazione e i numeri di giustificativo.

### <a name="journal-batch-number"></a>Numero batch giornale di registrazione

- L'impostazione **Elaborazione basata su set** dell'entità giornale di registrazione generale non influenza la modalità di generazione di numeri batch del giornale di registrazione.
- Se il campo **Numero batch giornale di registrazione** è impostato su **Generato automaticamente**, viene creato un nuovo numero di batch del giornale di registrazione per ogni riga che viene importata. Questo comportamento non è consigliato. L'impostazione **Generato automaticamente** è presente nel progetto di importazione, in **Visualizza mapping** nella scheda **Dettagli mapping**.
- Se il campo **Numero batch giornale di registrazione** non è impostato su **Generato automaticamente**, viene creato il nuovo numero di batch del giornale di registrazione come segue:

    - Se il numero di batch del giornale di registrazione che è definito nel file importato corrisponde a un giornale di registrazione quotidiano esistente e non registrato, tutte le righe che hanno un numero di batch di giornale di registrazione corrispondente vengono importate nel giornale di registrazione esistente. Le righe non vengono mai importate in un numero di batch di giornale di registrazione registrato. Al contrario, viene creato un nuovo numero.
    - Se il numero di batch del giornale di registrazione che è definito nel file importato non corrisponde a un giornale di registrazione quotidiano esistente e non registrato, tutte le righe che hanno lo stesso numero di batch di giornale di registrazione vengono raggruppate in un nuovo giornale di registrazione. Ad esempio, tutte le righe che hanno un numero di batch del giornale di registrazioni di 1 vengono importate in un nuovo giornale e tutte le righe che hanno un numero di batch del giornale di registrazione di 2 vengono importate in un secondo nuovo giornale di registrazione. Il numero di batch del giornale di registrazione viene creato utilizzando la sequenza numerica definita nei parametri di contabilità generale.

### <a name="voucher-number"></a>Numero del giustificativo

- Quando si utilizza l'impostazione **Elaborazione basata su set** nell'entità giornale di registrazione generale, il numero di giustificativo deve essere fornito nel file importato. A tutte le transazioni nel giornale di registrazione generale viene assegnato il numero di giustificativo che viene fornito nel file importato, anche se il giustificativo non è bilanciato. Se si desidera utilizzare l'elaborazione basata su set, ma si desidera anche utilizzare la sequenza numerica definita per i numeri di giustificativo, è disponibile un aggiornamento rapido per la versione di febbraio 2016. Il numero di aggiornamento rapido è 3170316 ed è disponibile per il download da Lifecycle Services (LCS). Per ulteriori informazioni, vedere [Download degli aggiornamenti rapidi da Lifecycle Services](../migration-upgrade/download-hotfix-lcs.md).

    - Per abilitare questa funzionalità, nel nome del giornale di registrazione utilizzato per le importazioni impostare **Assegnazione numero in fase di registrazione** su **Sì**.
    - Un numero di giustificativo deve comunque essere definito nel file importato. Tuttavia, questo numero è temporaneo e viene sovrascritto dal numero di giustificativo quando il giornale di registrazione viene registrato. È necessario assicurarsi che le righe del giornale di registrazione sono raggruppate correttamente per numero di giustificativo temporaneo. Ad esempio, durante la registrazione, vengono trovate tre righe a cui è associato un numero di giustificativo temporaneo pari a 1. Il numero del giustificativo temporaneo di tutte le tre righe viene sovrascritto con il numero successivo della sequenza numerica. Se le tre righe non sono una voce bilanciata, non viene registrato il giustificativo. Successivamente, se vengono trovate righe che hanno un numero di giustificativo temporaneo di 2, questo numero viene sovrascritto dal numero di giustificativo successivo nella sequenza numerica e così via.

- Quando non si utilizza l'impostazione **Elaborazione basata su set** non è necessario fornire un numero di giustificativo nel file importato. I numeri di giustificativo vengono creati durante l'importazione, in base all'impostazione del nome del giornale di registrazione (**Un solo numero di giustificativo**, **In relazione al saldo** e così via). Ad esempio, se il nome di giornale di registrazione viene definito come **In relazione al saldo**, la prima riga riceve un nuovo numero giustificativo predefinito. Il sistema valuta quindi la riga per determinare se i debiti sono pari ai crediti. Se esiste un conto di contropartita nella riga, la riga successiva che viene importata riceve un nuovo numero di giustificativo. Se non esiste alcun conto di contropartita, il sistema valuta se i debiti sono pari ai crediti per ogni nuova riga che viene importata.
- Se il campo **Numero del giustificativo** è impostato su **Generato automaticamente**, l'importazione non riuscirà. L'impostazione **Generato automaticamente** per il campo **Numero del giustificativo** non è supportata.

Per impostazione predefinita, l'entità giornale di registrazione generale utilizza l'elaborazione basata su set. Dopo aver valutato i requisiti aziendali dell'organizzazione, è possibile modificare l'impostazione **Elaborazione basata su set** facendo clic su **Entità di dati** nell'area di lavoro **Gestione dati**. L'elaborazione basata su set viene utilizzata per velocizzare il processo di importazione. Se non si utilizza l'elaborazione basata su set, l'importazione tramite l'entità giornale di registrazione generale sarà più lenta.
