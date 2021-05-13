---
title: Elaborazione differita del movimento manuale delle scorte
description: In questo argomento viene descritto come utilizzare l'elaborazione differita del movimento manuale delle scorte in Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: Mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 54a202b7e6728bc83022851c901d3c5db17510bf
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956709"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Elaborazione differita del movimento manuale delle scorte

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare l'elaborazione differita del movimento manuale delle scorte in Microsoft Dynamics 365 Supply Chain Management.

La funzionalità di elaborazione differita consente agli addetti al magazzino di continuare a fare altro lavoro mentre l'operazione di stoccaggio viene elaborata in background. È utile quando il server può avere aumenti occasionali o non pianificati nel tempo di elaborazione e il tempo di elaborazione aumentato può influire sulla produttività dei lavoratori. Il tipo di lavoro *Movimento scorte* è stato ora aggiunto alla serie di tipi di lavoro supportati da questa funzione.

L'elaborazione in background si ottiene utilizzando la [funzionalità Elabora eventi dell'app di magazzino](warehouse-app-events.md).

## <a name="turn-on-this-feature-for-your-system"></a>Attivare questa funzionalità per il sistema

Per rendere disponibile questa funzionalità, attivare le seguenti funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md): Devi attivarle in questo ordine:

1. Blocco lavoro a livello di organizzazione
1. Elabora eventi dell'app magazzino
1. Operazioni Put differite
1. Elaborazione differita dell'operazione di movimento scorte manuale

## <a name="configure-the-work-processing-policies"></a>Configurare i criteri di elaborazione del lavoro

Per utilizzare l'elaborazione differita, è necessario configurare e utilizzare un criterio di elaborazione del  lavoro. Per l'elaborazione differita dello stoccaggio, la [funzionalità Elaborazione differita di lavoro di magazzino](deferred-put.md) supporta i seguenti tipi di lavoro: *Ordine cliente*, *Invio ordine di trasferimento*, e *Rifornimento*. Le funzionalità *Elaborazione differita del movimento manuale delle scorte* aggiunge un nuovo tipo di lavoro: *Movimento scorte*.

Per configurare un criterio di elaborazione del lavoro, seguire questi passaggi.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Criteri di elaborazione lavoro**.
1. Selezionare un criterio esistente nell'elenco oppure creare un nuovo criterio selezionando **Nuovo** nel riquadro azioni. L'intestazione di ogni criterio ha i seguenti campi:

    - **Nome criteri di elaborazione lavoro** - il nome del criterio di elaborazione lavoro.
    - **Descrizione:** una descrizione dei criteri di elaborazione lavoro.

1. Nella scheda dettaglio **Regole di elaborazione**, imposta la raccolta di regole che verranno applicate dal criterio. Utilizzare i pulsanti della barra degli strumenti per aggiungere o rimuovere le righe come necessario: Per ciascuna regola, impostare i seguenti campi:

    - **Tipo ordine di lavoro** - Selezionare il tipo di lavoro a cui si applica il criterio.
    - **Operazione** - Selezionare l'operazione che il criterio viene utilizzato per elaborare. Se hai selezionato *Movimento scorte* nel campo **Tipo ordine di lavoro**, non è necessario impostare questo campo, perché sia le operazioni di prelievo che le operazioni di stoccaggio vengono elaborate come un singolo evento.
    - **Metodo di elaborazione lavoro** - Selezionare il metodo utilizzato per elaborare la riga di lavoro. Se selezioni *Immediato*, il comportamento è simile al comportamento quando nessun criterio di elaborazione del lavoro viene utilizzato per elaborare la riga. Se selezioni *Differito*, il sistema applicherà l'elaborazione differita che utilizza il framework batch.
    - **Soglia di elaborazione differita** - Se imposti questo campo su *0* (zero), non c'è soglia. In questo caso, il metodo di elaborazione *Differito* viene utilizzato se possibile. Se il calcolo specifico è inferiore alla soglia, il metodo *Immediato* viene utilizzato. In caso contrario, verrà usato il metodo *Differito* se possibile. Per lavoro correlato a vendite e trasferimenti, la soglia viene calcolata come il numero di righe di carico di origine associate che vengono elaborate per il lavoro. Per il lavoro di rifornimento, la soglia viene calcolata come il numero di righe di lavoro rifornite dal lavoro. Impostando una soglia, ad esempio, *5* per le vendite, assicuri che i lavori più piccoli con meno di cinque righe di carico di origine iniziali non useranno l'elaborazione differita, ma i lavori maggiori sì. La soglia ha effetto solo se il campo **Metodo di elaborazione lavoro** è impostato su *Differito*.
    - **Gruppo batch di elaborazione differita** - Specificare il gruppo batch utilizzato per l'elaborazione. Se hai selezionato *Movimento scorte* nel campo **Tipo ordine di lavoro**, non è necessario impostare questo campo, perché il gruppo batch è selezionato nella finestra di dialogo **Elabora eventi dell'app di magazzino**.

## <a name="assign-the-work-creation-policy"></a>Assegnare i criteri di creazione del lavoro

Per dettagli su come assegnare un criterio di creazione del lavoro, vedere [Elaborazione differita di lavoro di magazzino](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurare un processo batch per elaborare eventi dell'app di magazzino

Per utilizzare il processo *Elaborazione differita del movimento manuale delle scorte*, impostare un processo batch pianificato.

1. Vai a **Gestione magazzino \> Attività periodiche \> Elabora eventi dell'app di magazzino**.
1. Nella finestra di dialogo **Elabora eventi dell'app di magazzino**, nella Scheda dettaglio **Esegui in background**, imposta l'opzione **Elaborazione in batch** su *Sì*.
1. Selezionare **Ricorrenza** e imposta una pianificazione di esecuzione che soddisfi i requisiti della tua azienda.
1. In ogni finestra di dialogo selezionare **OK**.

## <a name="inquire-about-the-warehouse-app-events"></a>Richiedere informazioni su eventi dell'app di magazzino

Puoi visualizzare la coda degli eventi e i messaggi di eventi generati dall'app di magazzino selezionando **Gestione magazzino \> Richieste di informazioni e report \> Log dispositivo mobile \> Eventi dell'app di magazzino**.

I messaggi degli eventi *Movimento scorte* avranno uno stato di *In coda* quando vengono creati per la prima volta. Questo stato indica che il processo batch **Elabora eventi dell'app di magazzino** preleverà ed elaborerà i messaggi degli eventi. Quando lo stato viene aggiornato in *Completato*, tutti gli eventi correlati vengono eliminati dalla coda.

Tutti gli eventi *Movimento scorte* vengono accumulati in una unica raccolta per tipo di evento e magazzino.

Il processo batch elaborerà gli eventi dell'app di magazzino in base alla ricorrenza impostata nella finestra di dialogo **Elabora eventi dell'app di magazzino**. Pertanto, fino a quando un messaggio non viene elaborato, è possibile trovare l'ID magazzino cercando nel campo **Identificatore**.

I dettagli del messaggio contengono i dettagli del movimento (ad esempio, le ubicazioni "da" e "a").

Per ulteriori informazioni, vedi [Elaborazione di eventi dell'app di magazzino](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configurare il menu del dispositivo mobile per ignorare i criteri di elaborazione differita

Per dettagli su come configurare il menu del dispositivo mobile per ignorare i criteri di elaborazione differita, vedere [Elaborazione differita di lavoro di magazzino](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>Impatto sulle date di chiusura lavoro

Per i dettagli sull'impatto sulle date di chiusura lavoro, vedere [Elaborazione differita di lavoro di magazzino](deferred-put.md).

## <a name="additional-resources"></a>Risorse aggiuntive

- [Elaborazione del lavoro di magazzino rinviata](deferred-put.md)
- [Elaborazione degli eventi dell'app di magazzino](warehouse-app-events.md)
- [Impostare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
