---
title: Errore durante la selezione dell'ubicazione nel corso della registrazione della distinta di prelievo
description: Errore durante la selezione dell'ubicazione nel corso della registrazione della distinta di prelievo.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: da5905fb7ed1e890c85e891843379aa07de3279bd8972d6fc57136aa703c9ea4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762796"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Errore durante la selezione dell'ubicazione nel corso della registrazione della distinta di prelievo

Numero KB: 4613106

## <a name="symptoms"></a>Sintomi

Questo problema si verifica quando il sistema è configurato per prenotare automaticamente ordini cliente. Se tenti di selezionare l'ubicazione per una riga di registrazione della distinta di prelievo, viene visualizzato il seguente messaggio di errore quando utilizzi i processi di prenotazione di Gestione magazzino (WMS):

> Impossibile aggiornare la quantità con nuove dimensioni

Questo problema può verificarsi perché non disponi di scorte disponibili sufficienti in un'ubicazione specificata.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto.

Negli scenari in cui utilizzi il processo di prenotazione a livello di magazzino, se le scorte disponibili non sono prenotate a tutti i livelli delle dimensioni inventariali e non disponi di scorte disponibili sufficienti in un'ubicazione specificata, ti consigliamo di utilizzare il processo di prenotazione manuale dalla riga di prelievo. Successivamente, puoi utilizzare la funzione *Prenota lotto* per distribuire le prenotazioni inferiori, come l'ubicazione, per tutte le quantità disponibili.
