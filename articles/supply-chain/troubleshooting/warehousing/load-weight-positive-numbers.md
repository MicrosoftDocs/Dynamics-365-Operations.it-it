---
title: Il peso del carico può contenere solo numeri positivi
description: Durante l'elaborazione del lavoro tra le ubicazioni, è possibile che venga visualizzato un errore relativo al peso del carico e l'annullamento dell'aggiornamento. Per risolvere il problema, procedere come segue.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476756"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Errore di peso del carico e aggiornamento annullato durante l'elaborazione del lavoro tra ubicazioni

## <a name="symptoms"></a>Sintomi

Se è presente un lavoro aperto quando si elabora il lavoro da ubicazioni di imballaggio a ubicazioni di staging o da ubicazioni di staging a ubicazioni di ancoraggio, è possibile che venga visualizzato il seguente messaggio di errore:

> Il campo "Peso del carico"(=-%1) può contenere solo numeri positivi. L'aggiornamento è stato annullato.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, andare a **Amministrazione di sistema \> Attività periodiche \> Database \> Controllo coerenza** ed eseguire il processo **Controllo coerenza peso carico magazzino**.
