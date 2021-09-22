---
title: Errore del percorso di certificazione durante l'aggiornamento o la migrazione a WMS
description: Se l'app mostra l'errore "Ancoraggio attendibile per percorso di certificazione non trovato" durante l'aggiornamento o la migrazione a WMS, questa pagina fornisce informazioni su come risolvere il problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476742"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>Ancoraggio attendibile per il percorso di certificazione non trovato durante l'aggiornamento e la migrazione a WMS

## <a name="symptoms"></a>Sintomi

Durante l'aggiornamento e la migrazione a gestione avanzata del magazzino (WMS), l'app Warehouse Management potrebbe mostrare il seguente messaggio di errore:

> java.security.cert.certPathValidatorException: l'ancoraggio attendibile per il percorso di certificazione non è stato trovato.

## <a name="cause"></a>Causa

Ciò si verifica perché i certificati autofirmati non sono attendibili negli s in ambienti locali Android 8+.

## <a name="resolution"></a>Risoluzione

Utilizzare un'autorità di certificazione (CA) esterna (pubblica). Una correzione per questo problema è disponibile nella versione 1.9.0.0 dell'app Warehouse Management. Per ulteriori informazioni su questo problema e su come risolverlo, vedere [Ancoraggio attendibile per il percorso di certificazione non trovato durante la configurazione della connessione dell'app](certification-path-app-connection-error.md).
