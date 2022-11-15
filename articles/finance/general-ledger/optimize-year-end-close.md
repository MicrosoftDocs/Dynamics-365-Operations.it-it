---
title: Ottimizzazione della chiusura di fine anno
description: Questo articolo descrive il componente aggiuntivo del servizio Ottimizza chiusura di fine anno disponibile per il processo di chiusura di fine anno della contabilità generale.
author: moaamer
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 41d0c2975341cf3d612cc36be348326e24e94f1b
ms.sourcegitcommit: 707957bb7bcd98faf2600eff1c98067901a0fb73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750010"
---
# <a name="optimize-year-end-close"></a>Ottimizzazione della chiusura di fine anno

Il componente aggiuntivo del servizio Ottimizza chiusura di fine anno per Microsoft Dynamics 365 Finance consente l'esecuzione dell'elaborazione di chiusura di fine anno all'esterno dell'istanza AOS (Application Object Server) per le risorse di Dynamics 365 Finance. Utilizza la tecnologia del microservizio. I vantaggi associati alla funzionalità Ottimizza chiusura di fine anno includono prestazioni migliorate e un impatto minimo sul database SQL durante l'elaborazione della chiusura di fine anno.

Per utilizzare la funzionalità Ottimizza chiusura di fine anno, è necessario completare le seguenti attività:

1. Installa il componente aggiuntivo del servizio Ottimizza chiusura di fine anno dal tuo progetto in Microsoft Dynamics Lifecycle Services.
2. Abilita la funzionalità **Ottimizza chiusura di fine anno** in Gestione funzionalità.

> [!NOTE]
> Puoi comunque utilizzare la funzionalità di chiusura di fine anno corrente per le risorse finanziarie disabilitando la funzionalità **Ottimizza chiusura di fine anno** in Gestione funzionalità.

## <a name="improved-performance"></a>Prestazioni migliorate

La funzionalità **Ottimizza chiusura di fine anno** è progettata per accelerare l'elaborazione della chiusura di fine anno, in particolare per i clienti che dispongono di grandi volumi di dati. Quando la chiusura di fine anno viene eseguita su un servizio, l'elaborazione pesante viene scaricata dalle risorse Finance per ridurre i tempi di elaborazione e liberare risorse che potrebbero influire sulle operazioni quotidiane di altri utenti.

La funzionalità **Ottimizza chiusura di fine anno** può aiutarti a raggiungere i seguenti obiettivi:

- Migliora le prestazioni della chiusura di fine anno riducendo il runtime.
- Riduci l'impatto su altri processi durante l'esecuzione della chiusura di fine anno.
- Migliora la creazione di report e le rettifiche per i risultati di fine anno, in quanto l'esecuzione della chiusura di fine anno richiede meno tempo.

## <a name="new-options-and-visibility"></a>Nuove opzioni e visibilità

Quando la funzionalità **Ottimizza chiusura di fine anno** è abilitata, due nuove colonne, **Risultati** e **Stato**, vengono aggiunte nei seguenti posti:

- Nella pagina **Chiusura di fine anno**
- Nella finestra di dialogo **Risultati chiusura di fine anno**
- Nelle opzioni **Trasferimento dimensione finanziaria stato patrimoniale** della pagina **Modello di chiusura di fine anno**

L'illustrazione seguente mostra un esempio delle colonne **Risultati** e **Stato** della pagina **Chiusura di fine anno**. Puoi selezionare il collegamento **Visualizza risultati** nella colonna **Risultati** per aprire i risultati della chiusura di fine anno. La colonna **Stato** mostra lo stato corrente del processo di chiusura di fine anno. Pertanto, le nuove colonne forniscono visibilità sull'andamento del processo di chiusura di fine anno.

[![Colonne Risultati e Stato nella pagina di chiusura di fine anno.](./media/Yearendclose.jpg)](./media/Yearendclose.jpg)

Inoltre, quando la funzionalità **Ottimizza chiusura di fine anno** è abilitata, una scheda Dettaglio **Dimensioni finanziarie stato patrimoniale** diventa disponibile nella pagina **Modello di chiusura di fine anno**. Puoi utilizzare questa Scheda dettaglio per specificare in dettaglio le dimensioni finanziarie dello stato patrimoniale quando si chiude un anno. Questa funzionalità è parallela a quella già disponibile per i conti profitti e perdite.

## <a name="architecture-and-data-flow"></a>Architettura e flusso di dati

Per utilizzare la funzionalità **Ottimizza chiusura di fine anno** ed eseguire la chiusura di fine anno su un microservizio, è necessario installare il componente aggiuntivo del servizio Ottimizza chiusura di fine anno da Lifecycle Services e quindi abilitare la funzionalità **Ottimizza chiusura di fine anno** in Gestione funzionalità.

Come mostra l'illustrazione seguente, l'elaborazione della chiusura di fine anno verifica che il componente aggiuntivo sia installato e che la funzionalità sia abilitata. Se vengono soddisfatti entrambi i prerequisiti, la chiusura di fine anno viene eseguita nel microservizio.

[![Diagramma del flusso di dati.](./media/Lifecycle-services.jpg)](./media/Lifecycle-services.jpg)

## <a name="high-level-flow-for-year-end-close-processing"></a>Flusso di alto livello per l'elaborazione della chiusura di fine anno

1. Il processo di chiusura di fine anno inizia in Finance, in **Contabilità generale \> Chiusura periodo \> Chiusura di fine anno**. Il processo crea processi e attività batch di chiusura per le persone giuridiche che vengono chiuse.
2. La chiusura di fine anno determina se la chiusura di fine anno deve essere eseguita nel microservizio o nella logica di chiusura corrente.

    - Se i componente aggiuntivo del servizio Ottimizza chiusura di fine anno è installato in Lifecycle Services e la funzionalità **Ottimizza chiusura di fine anno** è abilitata in Gestione funzionalità, la chiusura di fine anno verrà eseguita nel microservizio.

        1. La funzionalità Ottimizza chiusura di fine anno crea un processo di servizio di chiusura di fine anno per ogni persona giuridica che viene chiusa, quindi esegue la logica di chiusura di fine anno. Il microservizio esegue la chiusura di fine anno.
        2. Finance ascolta la chiusura di fine anno nel microservizio per determinare quando il microservizio è terminato. I risultati della chiusura di fine anno vengono quindi aggiornati nella pagina **Chiusura di fine anno** in Finance.

    - In caso contrario, la chiusura di fine anno verrà eseguita sulla logica di chiusura corrente.
