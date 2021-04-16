---
title: Numero di libri per giornale di registrazione
description: Questo argomento descrive la relazione tra giornali e libri cespiti quando si crea un'acquisizione di cespiti o una proposta di ammortamento tramite un processo batch. Puoi definire il numero massimo di libri inclusi per ciascuna acquisizione e per l'ammortamento.
author: moaamer
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-19
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e948b4353d0216f1e09019a98319e343bd535861
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822035"
---
# <a name="number-of-books-per-journal"></a>Numero di libri per giornale di registrazione

[!include [banner](../includes/banner.md)]

Questo argomento descrive la relazione tra giornali e libri cespiti quando si crea un'acquisizione di cespiti o una proposta di ammortamento tramite un processo batch. Puoi definire il numero massimo di libri inclusi per ciascuna acquisizione e per l'ammortamento utilizzando i campi nella sezione **Numero di libri per giornale di registrazione** nella scheda **Generale** della pagina **Parametri dei cespiti** (**Cespiti \> Imposta \> Parametri dei cespiti**). Questi campi consentono di distribuire il numero di libri cespiti per giornale di registrazione acquisti e giornale di registrazione ammortamenti.

Per una proposta di acquisizione, il valore predefinito è di almeno 10.000 libri. Per una proposta di ammortamento, il valore predefinito è di almeno 2.000 libri.

Ad esempio, se sono presenti 4.000 cespiti e due libri sono associati a ciascun cespite, un libro verrà registrato nel livello corrente e l'altro libro verrà registrato nel livello imposte. Se si acquisiscono 4.000 cespiti tramite l'elaborazione batch, il processo batch che crea un giornale di registrazione acquisizione cespiti conterrà 4.000 libri cespiti.

> [!NOTE]
> Il giornale di registrazione creato continuerà a essere utilizzato fino al completamento del processo batch.
>
> I libri derivati non sono inclusi nel numero massimo di libri per giornale di registrazione.

Puoi utilizzare l'elaborazione batch per eseguire l'ammortamento per lo stesso set di cespiti acquisiti. Ad esempio, un processo batch crea due giornali di registrazione di ammortamento, ciascuno dei quali è composto da 2.000 libri cespiti. Il primo giornale di registrazione conterrà i libri associati ai cespiti numerati da 1 a 2.000. Il secondo giornale di registrazione conterrà quindi i libri associati ai cespiti numerati da 2.001 a 4.000.

Il processo di elaborazione batch esclude i libri chiusi. Ad esempio, in un processo batch per l'ammortamento, vengono chiusi 10 dei primi 2.000 libri. In questo caso, il primo giornale di registrazione conterrà i libri associati ai cespiti numerati da 1 a 2.011. Il secondo giornale di registrazione conterrà quindi i libri associati ai cespiti numerati da 2.012 a 4.000.

> [!NOTE]
> Se hai gli ID cespite con separatori diversi (come - o /) e crei transazioni cespite in processi batch, devi eseguire un processo batch separato per ogni tipo di separatore. Il sistema non può elaborare separatori diversi all'interno dello stesso processo batch.

Il limite al numero di libri viene applicato se gli ID risorsa duplicati non esistono nello stesso giornale. Tuttavia, se l'ID risorsa è uguale all'ID libro, il numero di libri per giornale di registrazione può essere superato per mantenere l'ID risorsa nello stesso giornale.

Ad esempio, ci sono 5.001 ID cespite, tre libri sono associati a ogni ID cespite e ogni libro cespiti viene registrato nello stesso livello di registrazione. Esegui l'ammortamento per tre mesi consecutivi, senza riepilogo.  Il giornale di registrazione ammortamento verrà creato tramite un processo batch e il sistema creerà sette giornali di registrazione con 667 ID cespite e tre libri per ogni ID cespite. Il risultato sarà 2.001 libri. Pertanto, in tre mesi, ci saranno 6.003 righe di giornale di registrazione per mantenere gli stessi ID cespite nello stesso giornale di registrazione. Il sistema creerà anche un giornale di registrazione con 332 ID cespiti e tre libri per ogni ID cespite. In tre mesi ci saranno 2.988 righe.

> [!NOTE] 
> Se il parametro **Riepilogo ammortamento** viene attivato durante la creazione di una proposta di ammortamento, il valore nel campo **Numero di libri per giornale - Proposta di ammortamento** non ha effetto. In questo caso il numero di libri per giornale è 6.000, il limite interno definito.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
