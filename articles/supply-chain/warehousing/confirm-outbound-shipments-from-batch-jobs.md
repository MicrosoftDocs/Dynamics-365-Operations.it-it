---
title: Conferma spedizioni in uscita da processi batch
description: Questo argomento descrive come configurare un processo batch che conferma automaticamente le spedizioni dell'ordine di trasferimento in uscita per i carichi pronti per la spedizione.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 69e61e1c04dd72efbe1d2f028c078100e07176f6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838444"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Conferma spedizioni in uscita da processi batch

[!include [banner](../includes/banner.md)]

Questo argomento descrive come configurare un processo batch che conferma automaticamente le spedizioni dell'ordine di trasferimento in uscita per i carichi pronti per la spedizione. Il processo batch qui descritto si applica solo alle spedizioni degli ordini di trasferimento, non agli ordini cliente.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Abilitare la funzionalità Conferma spedizioni in uscita da processi batch

Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario. La funzionalità viene elencata come:

- **Modulo** - *Gestione magazzino*
- **Nome funzionalità** - *Conferma spedizioni in uscita da processi batch*

## <a name="process-outbound-shipments"></a>Elabora spedizioni in uscita

Per configurare un processo batch pianificato per eseguire la conferma di spedizione in uscita per i carichi pronti per la spedizione:

1. Vai a **Gestione magazzino \> Attività periodiche \> Elaborazione spedizioni in uscita**.
1. Si apre la finestra di dialogo **Conferma spedizione**. Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.
1. Si apre la finestra di dialogo dell'editor di query. Nella scheda **Intervallo**, aggiungi una riga con i seguenti valori:
    - **Tabella** - *Carichi*
    - **Tabella derivata** - *Carichi*
    - **Campo** - *Stato carico*
    - **Criteri** - *Caricato*
1. Selezionare **OK** per tornare alla finestra di dialogo **Conferma spedizione**.
1. Nella Scheda dettaglio **Esegui in background**, impostare **Elaborazione batch** su **Sì**.
1. Nella Scheda dettaglio **Esegui in background** selezionare **Ricorrenza**.
1. Si apre la finestra di dialogo **Definisci ricorrenza**. Imposta il programma di esecuzione secondo necessità per la tua azienda.
1. Selezionare **OK** per tornare alla finestra di dialogo **Conferma spedizione**.
1. Selezionare **OK** nella finestra di dialogo **Conferma spedizione** per aggiungere il processo batch alla coda batch.

Per ulteriori informazioni, vedere [Panoramica elaborazione batch](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]