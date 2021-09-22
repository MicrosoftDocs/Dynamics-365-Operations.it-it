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
ms.openlocfilehash: ef34b4fdcc572c56319f6cbf4913d822d8857595
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474966"
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
