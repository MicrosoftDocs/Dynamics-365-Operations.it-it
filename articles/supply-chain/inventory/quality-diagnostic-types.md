---
title: Tipi di diagnostica per non conformità
description: Questo argomento descrive come utilizzare e creare tipi di diagnostica che possono essere utilizzati con non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7a5c593f1d9e8f7a77f693f6e652e9355a985fb
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022278"
---
# <a name="diagnostic-types-for-nonconformances"></a>Tipi di diagnostica per non conformità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come utilizzare e creare tipi di diagnostica che possono essere utilizzati con non conformità.

Utilizzare la pagina **Tipi di diagnostica** per definire una classificazione delle azioni di diagnostica. Quindi, quando si crea una correzione per una non conformità, si seleziona una diagnostica. Una correzione specifica il tipo di azione di diagnostica da eseguire per una non conformità approvata e l'utente che deve eseguire l'azione. Specifica inoltre la data di completamento richiesta e la data di completamento pianificata.

## <a name="examples-of-diagnostic-types"></a>Esempi di tipi di diagnostica

Lavori per un'azienda di produzione e diversi articoli non hanno superato i test di controllo qualità. Tali articoli vengono spostati in un'area di quarantena e contrassegnati come prodotti non conformi. Un record di non conformità viene creato in Microsoft Dynamics 365 Supply Chain Management per tenere traccia dei dettagli attraverso la risoluzione dei problemi.

In questo caso, i problemi di qualità si verificano perché i cuscinetti della macchina che imballa gli articoli si sono deteriorati e si stanno surriscaldando. La correzione per questo problema è sostituire le parti nella macchina.

Quando si configurano i tipi di diagnostica, è possibile creare più record, ognuno dei quali rappresenta un diverso tipo di problema che la macchina potrebbe avere. In alternativa, è possibile creare un tipo di diagnostica generico che rappresenta la riparazione della macchina.

## <a name="create-a-diagnostic-type"></a>Creare un tipo di diagnostica

1. Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Tipi di diagnostica**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Diagnostica** - Immettere un ID o un nome univoco per il tipo di diagnostica.
    - **Descrizione** - Immettere una descrizione dettagliata del tipo di diagnostica.

1. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Lavoratori responsabili dell'approvazione delle non conformità](quality-responsible-workers.md)
- [Aree di quarantena per non conformità](quality-quarantine-zones.md)
- [Tipi di problemi per non conformità](quality-problem-types.md)
- [Spese di gestione qualità per non conformità](quality-charges.md)
- [Operazioni per non conformità](quality-operations.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
