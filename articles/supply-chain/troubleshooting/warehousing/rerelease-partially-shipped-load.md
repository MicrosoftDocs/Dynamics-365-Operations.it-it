---
title: Non è possibile rilasciare un carico spedito parzialmente al magazzino
description: Nelle versioni precedenti, non era possibile rilasciare nuovamente un carico parzialmente spedito quando si utilizzavano determinate funzionalità con prenotazioni incomplete. Questo problema è stato risolto.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476785"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>Non è possibile rilasciare un carico spedito parzialmente al magazzino

## <a name="symptoms"></a>Sintomi

Non è possibile rilasciare un carico spedito parzialmente al magazzino. Quando si effettua il rilascio al magazzino, viene visualizzato il messaggio "Operazione completata", ma non accade nulla e non viene creato alcun lavoro per la quantità rimanente. Questo problema si verifica quando si utilizza la funzionalità di carico di trasporto e c'è una prenotazione incompleta.

## <a name="resolution"></a>Risoluzione

[Il problema KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("I carichi parzialmente spediti possono essere nuovamente elaborati e inclusi nel ciclo") è stato corretto nel [rilascio 10.0.15](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15).
