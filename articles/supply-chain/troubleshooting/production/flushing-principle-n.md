---
title: Le impostazioni del principio di registrazione del consumo di materiali nelle righe DBA non vengono rispettate
description: Le impostazioni del principio di registrazione del consumo di materiali nelle righe della distinta base non vengono rispettate.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026645"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Le impostazioni del principio di registrazione del consumo di materiali nelle righe DBA non vengono rispettate

Numero KB: 4612725

## <a name="symptoms"></a>Sintomi

Questo problema si verifica quando il campo **Consumo DBA automatico** nella scheda **Aggiornamento automatico** della pagina **Parametri di controllo produzione** è impostato su *Principio di registrazione del consumo di materiali*. Questa impostazione indica che tutte le righe della distinta base (DBA) devono essere utilizzate automaticamente quando viene ricevuto un ordine fornitore. Se il campo **Principio di registrazione del consumo di materiali** nelle righe DBA è impostato esplicitamente su *Manuale*, potresti aspettarti che le righe DBA non vengano consumate automaticamente. Tuttavia, quando si verifica questo problema, le righe DBA dove il campo **Principio di registrazione del consumo di materiali** è impostato su *Manuale* vengono comunque consumate automaticamente.

## <a name="resolution"></a>Risoluzione

Se si verifica questo problema, i parametri di controllo della produzione potrebbero essere impostati per ignorare l'impostazione **Principio di registrazione del consumo di materiali** delle righe DBA. Nella pagina **Parametri di controllo produzione**, nella scheda **Aggiornamento automatico**, controlla il valore del campo **Consumo DBA automatico**. Se è impostato su *Sempre*, il sistema ignorerà l'impostazione **Principio di registrazione del consumo di materiali** di tutte le righe DBA e registrerà sempre il consumo di materiali delle righe. Affinché il sistema prenda in considerazione l'impostazione **Principio di registrazione del consumo di materiali** per le righe DBA, imposta il valore del campo **Consumo BOM automatico** su *Principio di registrazione del consumo di materiali*.
