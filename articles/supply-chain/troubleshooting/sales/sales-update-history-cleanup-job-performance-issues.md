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
ms.openlocfilehash: 371a8c7178cd7c5091d6dd9a91d0ee03b943a269
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103190"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Il processo di pulizia della cronologia degli aggiornamenti delle vendite non riesce o presenta problemi di prestazioni

## <a name="symptoms"></a>Sintomi

Il processo batch di **pulizia della cronologia degli aggiornamenti delle vendite** non riesce o presenta problemi di prestazioni.  

## <a name="cause"></a>Causa

Ciò può verificarsi quando il sistema include un numero elevato di aggiornamenti delle vendite, il che può comportare una grande quantità di dati di aggiornamento delle vendite. Il processo di pulizia tenta di pulire tutti questi dati in un'unica transazione. Di conseguenza, l'esecuzione del lavoro potrebbe richiedere molto tempo o addirittura non riuscire.

## <a name="resolution"></a>Risoluzione

Una nuova versione del processo batch di **pulizia della cronologia degli aggiornamenti delle vendite** è disponibile per Supply Chain Management versione 10.0.19 e successive. Per impostazione predefinita, questa funzionalità è disattivata. Per i dettagli su come funziona e su come abilitarla nella gestione delle funzionalità, vedi [Miglioramenti delle prestazioni di pulizia della cronologia delle vendite](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

