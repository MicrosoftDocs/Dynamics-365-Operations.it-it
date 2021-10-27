---
title: Il processo di pulizia della cronologia degli aggiornamenti delle vendite non riesce o presenta problemi di prestazioni
description: Il processo batch di pulizia della cronologia delle vendite potrebbe non riuscire o richiedere molto tempo se è presente una grande quantità di dati di aggiornamento delle vendite.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 4f04dc204c705b40ed25fadc75118feaef4d6b6e
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641467"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Il processo di pulizia della cronologia degli aggiornamenti delle vendite non riesce o presenta problemi di prestazioni

## <a name="symptoms"></a>Sintomi

Il processo batch di **pulizia della cronologia degli aggiornamenti delle vendite** non riesce o presenta problemi di prestazioni.  

## <a name="cause"></a>Causa

Ciò può verificarsi quando il sistema include un numero elevato di aggiornamenti delle vendite, il che può comportare una grande quantità di dati di aggiornamento delle vendite. Il processo di pulizia tenta di pulire tutti questi dati in un'unica transazione. Di conseguenza, l'esecuzione del lavoro potrebbe richiedere molto tempo o addirittura non riuscire.

## <a name="resolution"></a>Risoluzione

Una nuova versione del processo batch di **pulizia della cronologia degli aggiornamenti delle vendite** è disponibile per Supply Chain Management versione 10.0.19 e successive. Per impostazione predefinita, questa funzionalità non è abilitata. Per i dettagli su come funziona e su come abilitarla nella gestione delle funzionalità, vedi [Miglioramenti delle prestazioni di pulizia della cronologia delle vendite](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

