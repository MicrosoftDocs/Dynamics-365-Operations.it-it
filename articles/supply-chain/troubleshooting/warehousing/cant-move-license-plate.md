---
title: Impossibile spostare la targa se sono consentite entrate e uscite non specificate
description: Non è possibile spostare una targa se sono consentite entrate e uscite non specificate per il numero di serie. Questo problema verrà risolto rendendo facoltativo il campo del numero di serie.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476760"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>Impossibile spostare una targa se sono consentite entrate e uscite non specificate per il numero di serie

## <a name="symptoms"></a>Sintomi

Non è possibile spostare una targa utilizzando la voce di menu **Spostamento** se il numero di serie ha le impostazioni *Uscita non specificata consentita* e *Entrata non specificata consentita* nel gruppo di dimensioni di tracciabilità e se sono presenti più targhe nella stessa ubicazione, alcune delle quali hanno numeri di serie e altre no.

## <a name="resolution"></a>Risoluzione

Questo problema verrà risolto dalle modifiche distribuite in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Queste modifiche renderanno il campo **Numero di serie** facoltativo quando sono consentite entrate e uscite non specificate.
