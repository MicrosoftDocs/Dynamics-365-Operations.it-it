---
title: La correzione della bolla di consegna non può essere elaborata
description: Se si prova a correggere una bolla di consegna dopo che è stata registrata, si riceve un errore. Questa pagina spiega come correggere i documenti di trasporto registrati per gli articoli abilitati per WMS.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bb0d827adff8abd8762bf2de844cad5574628e4b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476794"
---
# <a name="delivery-note-correction-cant-be-processed"></a>La correzione della bolla di consegna non può essere elaborata

## <a name="symptoms"></a>Sintomi

Dopo aver registrato una bolla di consegna, non è possibile annullarla perché il pulsante **Annulla** non è disponibile. Inoltre, non è possibile correggere la bolla di consegna. Se si prova a effettuare tale operazione, viene visualizzato il seguente messaggio di errore:

> La correzione della bolla di consegna non può essere elaborata. La bolla di consegna contiene solo articoli soggetti a processi di gestione del magazzino, in quanto non sono supportati dalla correzione della bolla di consegna.

## <a name="resolution"></a>Risoluzione

Per correggere i documenti di trasporto registrati per gli articoli abilitati per la gestione avanzata del magazzino (WMS), è necessario che la avvenga dal carico, non dall'ordine.
