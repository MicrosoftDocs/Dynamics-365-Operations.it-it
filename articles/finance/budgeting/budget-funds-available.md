---
title: Fondi budget disponibili
description: Questo argomento introduce la funzionalità di fondi budget disponibili e fornisce informazioni che consentono di configurare il controllo del budget per ottimizzare la gestione delle risorse finanziarie dell'organizzazione.
author: rcarlson
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: a8279ae9b08c7537548c1c8b71e6e978fee2b8a1
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891316"
---
# <a name="budget-funds-available"></a>Fondi budget disponibili

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento introduce la funzionalità di fondi budget disponibili e fornisce informazioni che consentono di configurare il controllo del budget per ottimizzare la gestione delle risorse finanziarie dell'organizzazione.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Funzionalità di calcolo avanzata per i fondi budget disponibili

La funzionalità **Traccia solo gli importi nel calcolo dei fondi di budget disponibili** consente di tenere traccia delle tabelle di controllo del budget sottostanti per i tipi e gli stati dei documenti, in base alle impostazioni della pagina **Definire i parametri di controllo del budget**.

Alcune opzioni di configurazione del controllo del budget devono avere impostazioni specifiche affinché la funzionalità funzioni correttamente. Tali opzioni vengono selezionate o deselezionate nella scheda **Fondi budget disponibili** della pagina **Definire i parametri di controllo del budget**. La tabella seguente mostra le impostazioni necessarie per la funzionalità Fondi budget disponibili.

| Se questa opzione è selezionata | Anche questa opzione deve essere selezionata |
| ------------------------- | -------------------------------- |
| Prenotazioni budget per impegni preliminari di spesa | Prenotazioni budget per impegni di spesa *e* spese effettive |
| Prenotazioni budget per impegni di spesa | Spese effettive |
| Prenotazioni di budget per impegni di spesa con documenti di tipo Richiesta di acquisto | Prenotazioni budget per impegni preliminari di spesa |

Questa funzionalità ha effetto solo sui nuovi documenti. Gli importi per i documenti esistenti continueranno a essere tracciati e visualizzati nella richiesta delle statistiche di controllo del budget fino a quando non viene modificata un'impostazione di fondi budget disponibili e non viene attivata la nuova configurazione di controllo del budget. A quel punto, i dati di tracciabilità del budget verranno rimossi per i documenti che sono stati rimossi dal calcolo dei fondi di budget disponibili.

Ti consigliamo di lasciare l'opzione **Spese effettive non registrate** deselezionata. Se è selezionata, verrà eseguito un lungo calcolo di controllo del budget sui documenti non registrati, come le fatture fornitore in sospeso.
