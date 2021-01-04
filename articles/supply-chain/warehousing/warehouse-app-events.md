---
title: Eventi dell'app di magazzino
description: In questo argomento viene descritta l'elaborazione degli eventi dell'app di magazzino utilizzata per elaborare messaggi di evento dell'app di magazzino come parte di un processo batch.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 210008c4a1366773f465c59b38eca30f11f0b38c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431009"
---
# <a name="warehouse-app-event-processing"></a>Elaborazione degli eventi dell'app di magazzino

[!include [banner](../includes/banner.md)]

I processi batch in esecuzione in Supply Chain Management possono utilizzare i dati di una coda per elaborare eventi emessi dall'app di magazzino per reagire come necessario agli eventi segnalati. Questa funzionalità aggiunge eventi pertinenti alla coda in risposta a determinati tipi di azioni intraprese dai lavoratori che utilizzano l'app. Un esempio è quando si utilizza la funzionalità **Crea ed elabora ordini di trasferimento nell'app di magazzino**, l'intestazione e le righe dell'ordine di trasferimento vengono create e aggiornate nel back-end quando il sistema esegue il processo batch **Elabora eventi dell'app di magazzino**.

## <a name="enable-the-process-warehouse-app-events-feature"></a>Abilitare la funzionalità Elabora eventi dell'app di magazzino

Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario. La funzionalità Elabora eventi dell'app di magazzino viene elencata come:

- **Modulo**: Gestione magazzino
- **Nome funzionalità**: Elabora eventi dell'app di magazzino

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurare un processo batch per elaborare eventi dell'app di magazzino

### <a name="process-warehouse-app-events"></a>Elaborare eventi dell'app di magazzino

Configura un processo batch pianificato per elaborare gli eventi dell'app di magazzino per la creazione dell'ordine di trasferimento e gli aggiornamenti delle righe.

1. Vai a **Gestione magazzino \> Attività periodiche \> Elabora eventi dell'app di magazzino**.
1. Viene visualizzata la finestra di dialogo Elabora eventi dell'app di magazzino. Espandi la Scheda dettaglio **Esegui in background** e imposta **Elaborazione batch** su **Sì**.
1. Nella Scheda dettaglio **Esegui in background** selezionare **Ricorrenza**.
1. Si apre la finestra di dialogo **Definisci ricorrenza**. Imposta il programma di esecuzione secondo necessità per la tua azienda.
1. Seleziona **OK** per tornare alla finestra di dialogo **Elabora eventi dell'app di magazzino**.
1. Seleziona **OK** nella finestra di dialogo **Elabora eventi dell'app di magazzino** per aggiungere il processo batch alla coda batch.

## <a name="query-warehouse-app-events"></a>Eseguire query sugli eventi dell'app di magazzino

Puoi visualizzare la coda degli eventi e i messaggi di eventi generati dall'app di magazzino selezionando **Gestione magazzino \> Richieste di informazioni e report \> Log dispositivo mobile \> Eventi dell'app di magazzino**.

## <a name="the-standard-event-queue-process"></a>Elaborazione della coda di eventi standard

La coda degli eventi delle app di magazzino verrà in genere utilizzata con il flusso descritto di seguito:

1. Un evento viene aggiunto alla coda con un messaggio di evento. Il nuovo messaggio ha inizialmente lo stato di evento **In attesa**, il che significa che il processo batch **Elabora eventi dell'app di magazzino** non preleverà ed elaborerà questo messaggio.
1. Non appena lo stato del messaggio viene aggiornato a **In coda**, il processo batch degli eventi **Elabora l'app di magazzino** verrà prelevato ed elaborerà l'evento.
1. Il processo batch aggiorna lo stato dell'evento a **Completato** o **Non riuscito**, a seconda dell'esito dell'elaborazione.
1. Quando lo stato di tutti i messaggi di evento correlati è **Completato**, l'evento viene eliminato dalla coda.

 Per un esempio dettagliato, vedi [Creare un ordine di trasferimento dall'elaborazione dell'app di magazzino](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Gestire gli errori degli eventi

Come parte dell'elaborazione degli eventi di magazzino, l'attività di messaggio richiesta potrebbe non ricevere processi dal processo batch. In questo caso, lo stato del messaggio di evento diventerà **Non riuscito**. Puoi usare le informazioni in **Log batch** per sapere perché e intraprendere l'azione necessaria per correggere eventuali problemi.

Per un esempio dettagliato, vedi [Creare un ordine di trasferimento dall'app di magazzino](create-transfer-order-from-warehouse-app.md).

Per ripristinare un messaggio di evento di un'app di magazzino non riuscita:

1. Vai a **Gestione magazzino \> Richieste di informazioni e report \> Log dispositivo mobile \> Eventi dell'app di magazzino**.
1. Nella Scheda dettaglio **Messaggi di evento dell'app di magazzino**, trova e seleziona un evento pertinente nella cui colonna **Stato evento** è visualizzato **Non riuscito**.
1. Seleziona **Ripristina** nella barra degli strumenti **Messaggi di evento dell'app di magazzino** .
1. Continua a lavorare fino a quando tutti i messaggi pertinenti non vengono ripristinati.

Puoi anche rimuovere un messaggio di evento **Non riuscito** utilizzando l'opzione **Elimina** nella barra degli strumenti **Messaggi di evento dell'app di magazzino**.
