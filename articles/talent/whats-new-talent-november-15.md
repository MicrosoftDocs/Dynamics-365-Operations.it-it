---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (15 novembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1a7598db1dc4c11864cf5f5a73d00672ceb66e8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461632"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-15-2018"></a>Novità o modifiche in Dynamics 365 Talent - Core HR (15 novembre 2018)

**Build 8.1.2045**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="other-changesfixes"></a>Altre modifiche/correzioni

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Impossibile modificare la posizione corrente del dipendente in una posizione aperta futura

È stata effettuata una modifica per abilitare i trasferimenti di posizioni quando la posizione è disponibile solo in futuro. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>La posizione non viene visualizzata quando si crea un nuovo dipendente

È stata effettuata una modifica per visualizzare tutte le posizioni aperte disponibili per l'assegnazione quando si assumono nuovi dipendenti in Talent. Sono incluse le posizioni storiche o le posizioni future. Le posizioni sono ora visualizzate correttamente in base alla data di inizio impiego. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>La data di fine rapporto viene visualizzata in base alle impostazioni utente

È stata effettuata una modifica all'elenco dei dipendenti passati per prendere in considerazione eventuali differenze di fuso orario per il fuso orario preferito dei dipendenti quando si visualizza la data di fine rapporto.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>I collegamenti di Elementi di lavoro assegnati all'utente non visualizzano le informazioni corrette

Con questa modifica, il percorso ai dettagli dei singoli elementi di lavoro nell'elenco visualizza le informazioni corrette per l'elemento selezionato. Questo problema si è verificato solo con opzioni di sicurezza avanzate.


## <a name="known-issue"></a>Problema noto

- **Problema**: quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono inattivi. 
- **Soluzione alternativa:** prima di aprire la pagina dell'allegato, verificare che le schede dettaglio della pagina **Lavoratore** siano chiuse. Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati. Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.


[!INCLUDE[footer-include](../includes/footer-banner.md)]