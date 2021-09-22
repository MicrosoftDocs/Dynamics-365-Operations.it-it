---
title: Errore di ubicazione o targa non valida nell'app per dispositivi mobili
description: Quando si esegue la scansione di un ID targa o un'ubicazione, è possibile che venga visualizzato un errore di invalidità. Assicurarsi che l'ID targa non sia prenotato da qualcos'altro.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f9f10dbade0d13b8fc4b0fc92981d84e6e28e83e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476819"
---
# <a name="invalid-license-plate-or-location-error-when-scanning-in-the-mobile-app"></a>Errore di ubicazione o targa non valida durante la scansione nell'app per dispositivi mobili

## <a name="symptoms"></a>Sintomi

Quando si esegue la scansione di un ID targa o un'ubicazione, è possibile che venga visualizzato il seguente messaggio di errore:

> La targa o l'ubicazione non è valida.

## <a name="resolution"></a>Risoluzione

Assicurarsi che l'ID targa non sia prenotato da qualcos'altro. Questo problema si verificava quando il valore scansionato da un utente nell'app per dispositivi mobili Gestione magazzino era sia un'ubicazione valida che un ID targa valido. Tuttavia, questo problema è stato risolto nella versione 10.0.11.
