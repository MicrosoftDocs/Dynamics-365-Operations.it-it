---
title: Importazione dei giustificativi utilizzando l'entità registrazione COGE
description: In questo articolo vengono forniti suggerimenti per l'importazione dei dati nel giornale di registrazione generale tramite l'entità giornale di registrazione generale.
author: rcarlson
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5917a047d3098875f3ab95087e761e6428c18b
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135722"
---
# <a name="importing-vouchers-by-using-the-general-journal-entity"></a>Importazione dei giustificativi utilizzando l'entità registrazione COGE

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

In questo articolo vengono forniti suggerimenti per l'importazione dei dati nel giornale di registrazione generale tramite l'entità giornale di registrazione generale.

È possibile utilizzare l'entità journal generale per importare buoni con un account o un tipo di conto offset di **Contabilità generale**, **Cliente**, **Fornitore**, or **Banca**. Il giustificativo può essere immesso come riga unica, usando sia il campo **Conto** che il campo **Conto di contropartita** , o come giustificativo con più righe. In questo caso viene utilizzato solo il campo **Conto** e il campo **Conto di contropartita** viene lasciato vuoto su ogni riga. L'entità giornale di registrazione generale non supporta tutti i tipi di conto. Invece, altre entità esistono per gli scenari in cui sono necessarie diverse combinazioni di tipi di conto. Ad esempio, per importare una transazione di progetto, utilizzare l'entità giornale di registrazione spese di progetto. Ogni entità è progettata per supportare scenari specifici. Ciò significa che potrebbero essere disponibili campi aggiuntivi nelle entità per tali scenari. Tuttavia, i campi aggiuntivi potrebbero non essere disponibili nelle entità per diversi scenari.

## <a name="setup"></a>Attrezzaggio
Prima di importare utilizzando l'entità giornale di registrazione generale, convalidare l'impostazione seguente:

- **Impostazione di sequenza numerica per il numero di batch del giornale di registrazione** – per impostazione predefinita, quando si importa utilizzando l'entità giornale di registrazione generale, il numero batch del giornale di registrazione utilizza la sequenza numerica definita nei parametri di contabilità generale. Se si imposta la sequenza numerica per il numero di batch del giornale di registrazione su **Manuale**, un numero predefinito non viene applicato. Questa impostazione non è supportata.
- **Configurazione della dimensione finanziaria** – ogni organizzazione deve definire l'ordine delle dimensioni finanziarie quando le entità vengono utilizzate per importare le transazioni. L'ordine viene definito per il formato **Integrazione dimensioni contabilità generale** in **Contabilità generale** &gt; **Piano dei conti** &gt; **Dimensioni** &gt; **Configurazione dimensione finanziaria per integrazione applicazioni** &gt; **Seleziona entità di dati**. I segmenti del conto CoGe da importare devono avere lo stesso ordine. In caso contrario, si verificherà un errore durante l'importazione.

## <a name="general-journal-entity-setup"></a>Impostazione dell'entitò giornale di registrazione generale
Due impostazioni nella gestione dei dati influiscono sulla modalità di applicazione del numero batch o sul numero giustificativo del giornale di registrazione predefinito:

- **Elaborazione basata su set** (nell'entità di dati)
- **Generata automaticamente** (per il mapping dei campi)

Le seguenti sezioni descrivono l'effetto di queste impostazioni. Spiegano inoltre come il sistema genera numeri di batch per giornali di registrazione e numeri di giustificativi.

### <a name="journal-batch-number"></a>Numero batch giornale di registrazione

- L'impostazione **Elaborazione basata su set** dell'entità giornale di registrazione generale non influenza la modalità di generazione di numeri batch del giornale di registrazione.
- Se il campo **Numero batch giornale di registrazione** è impostato su **Generato automaticamente**, viene creato un nuovo numero di batch del giornale di registrazione per ogni riga che viene importata. Questo comportamento non è consigliato. L'impostazione **Generato automaticamente** è presente nel progetto di importazione, in **Visualizza mapping** nella scheda **Dettagli mapping**.
- Se il campo **Numero batch giornale di registrazione** non è impostato su **Generato automaticamente**, viene creato il nuovo numero di batch del giornale di registrazione come segue:

    - Se il numero di batch del giornale di registrazione che è definito nel file importato corrisponde a un giornale di registrazione quotidiano esistente e non registrato, tutte le righe che hanno un numero di batch di giornale di registrazione corrispondente vengono importate nel giornale di registrazione esistente. Le righe non vengono mai importate in un numero di batch di giornale di registrazione registrato. Al contrario, viene creato un nuovo numero.
    - Se il numero di batch del giornale di registrazione che è definito nel file importato non corrisponde a un giornale di registrazione quotidiano esistente e non registrato, tutte le righe che hanno lo stesso numero di batch di giornale di registrazione vengono raggruppate in un nuovo giornale di registrazione. Ad esempio, tutte le righe che hanno un numero di batch del giornale di registrazioni di 1 vengono importate in un nuovo giornale e tutte le righe che hanno un numero di batch del giornale di registrazione di 2 vengono importate in un secondo nuovo giornale di registrazione. Il numero di batch del giornale di registrazione viene creato utilizzando la sequenza numerica definita nei parametri di contabilità generale.

### <a name="voucher-number"></a>Numero del giustificativo

- Quando si utilizza l'impostazione **Elaborazione basata su set** nell'entità giornale di registrazione generale, il numero di giustificativo deve essere fornito nel file importato. A tutte le transazioni nel giornale di registrazione generale viene assegnato il numero di giustificativo che viene fornito nel file importato, anche se il giustificativo non è bilanciato. Tenere presente quanto segue se si desidera utilizzare l'elaborazione basata su set, ma si desidera utilizzare anche la sequenza numerica definita per i numeri di giustificativo.

    - Per abilitare questa funzionalità, nel nome del giornale di registrazione utilizzato per le importazioni impostare **Assegnazione numero in fase di registrazione** su **Sì**.
    - Un numero di giustificativo deve comunque essere definito nel file importato. Tuttavia, questo numero è temporaneo e verrà sovrascritto dal numero di giustificativo quando il giornale di registrazione viene registrato. Assicurarsi che le righe del giornale di registrazione siano raggruppate correttamente per numero di giustificativo temporaneo. Ad esempio, durante la registrazione, vengono trovate tre righe a cui è associato un numero di giustificativo temporaneo pari a 1. Il numero del giustificativo temporaneo di tutte le tre righe viene sovrascritto con il numero successivo della sequenza numerica. Se le tre righe non sono una voce bilanciata, il giustificativo non viene pubblicato. Quindi, se vengono rilevate righe con un numero di voucher temporaneo pari a 2, questo numero viene sovrascritto dal numero di voucher successivo nella sequenza e così via.

- Quando non si utilizza l'impostazione **Elaborazione basata su set** non è necessario fornire un numero di giustificativo nel file importato. I numeri di giustificativo vengono creati durante l'importazione, in base all'impostazione del nome del giornale di registrazione (**Un solo numero di giustificativo**, **In relazione al saldo** e così via). Ad esempio, se il nome di giornale di registrazione viene definito come **In relazione al saldo**, la prima riga riceve un nuovo numero giustificativo predefinito. Il sistema valuta quindi la riga per determinare se i debiti sono pari ai crediti. Se esiste un conto di contropartita nella riga, la riga successiva che viene importata riceve un nuovo numero di giustificativo. Se non esiste alcun conto di contropartita, il sistema valuta se i debiti sono pari ai crediti per ogni nuova riga che viene importata.
- Se il campo **Numero del giustificativo** è impostato su **Generato automaticamente**, l'importazione non riuscirà. L'impostazione **Generato automaticamente** per il campo **Numero del giustificativo** non è supportata.

Per impostazione predefinita, l'entità giornale di registrazione generale utilizza l'elaborazione basata su set. Dopo aver valutato i requisiti aziendali dell'organizzazione, è possibile modificare l'impostazione **Elaborazione basata su set** facendo clic su **Entità di dati** nell'area di lavoro **Gestione dati**. L'elaborazione basata su set viene utilizzata per velocizzare il processo di importazione. Se non si utilizza l'elaborazione basata su set, l'importazione tramite l'entità giornale di registrazione generale sarà più lenta.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
