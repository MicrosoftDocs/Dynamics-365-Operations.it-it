---
title: Conferma spedizioni in uscita da processi batch
description: Questo articolo descrive come configurare un processo batch che conferma automaticamente le spedizioni dell'ordine di trasferimento in uscita per i carichi pronti per la spedizione.
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
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 00749a69b17b0064290d7b41ccb2171386716302
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875103"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Conferma spedizioni in uscita da processi batch

[!include [banner](../includes/banner.md)]

Questo articolo descrive come configurare un processo batch che conferma automaticamente le spedizioni dell'ordine di trasferimento in uscita per i carichi pronti per la spedizione. Il processo batch qui descritto si applica solo alle spedizioni degli ordini di trasferimento, non agli ordini cliente.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>Attivare o disattivare la funzionalità Conferma spedizioni in uscita da processi batch

Per utilizzare le funzionalità descritte in questo articolo, è necessario attivare la funzionalità *Conferma spedizioni in uscita da processi batch* per il sistema. A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.25, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Conferma spedizioni in uscita da processi batch* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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