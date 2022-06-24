---
title: Fondi budget disponibili
description: Questo articolo introduce la funzionalità di fondi budget disponibili e fornisce informazioni che consentono di configurare il controllo del budget per ottimizzare la gestione delle risorse finanziarie dell'organizzazione.
author: RyanCCarlson2
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b6f94931ba3514c1c66d80b64846d882861d555c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898242"
---
# <a name="budget-funds-available"></a>Fondi budget disponibili

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo introduce la funzionalità di fondi budget disponibili e fornisce informazioni che consentono di configurare il controllo del budget per ottimizzare la gestione delle risorse finanziarie dell'organizzazione.

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
