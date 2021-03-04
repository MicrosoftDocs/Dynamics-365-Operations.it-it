---
title: Registrare transazioni cespiti nei livelli di registrazione
description: Questo articolo fornisce una panoramica delle funzionalità del livello di registrazione per le transazioni cespiti.
author: moaamer
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a80e4d1a081b5bd8c58238b0f154f8fbdc660ccb
ms.sourcegitcommit: f80819c67c0a7475315fc68ce1cb568831e2c0e7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "4493674"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Registrare transazioni cespiti nei livelli di registrazione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica delle funzionalità del livello di registrazione per le transazioni cespiti.

L'ammortamento di un cespite viene spesso effettuato in vari modi per diversi scopi. L'ammortamento ai fini fiscali viene calcolato in base alle regole correnti per ottenere l'ammortamento più alto possibile al lordo d'imposta, tuttavia l'ammortamento ai fini della dichiarazione viene calcolato in base alle normative e agli standard contabili vigenti. I diversi tipi di ammortamento vengono calcolati e registrati separatamente nei livelli di registrazione.

Ciascun libro collegato a un cespite viene impostato per un particolare livello di registrazione con un obiettivo di ammortamento complessivo. Sono disponibili dieci livelli di registrazione: Corrente, Operazioni, Imposta e sette livelli personalizzati. È possibile anche disabilitare la registrazione nella contabilità generale per il libro impostando il campo Registra nella contabilità generale su No. Il campo Livello di registrazione verrà impostato automaticamente su Nessuno. In genere i libri che non vengono registrati nella contabilità generale sono utilizzati a fini di reporting fiscale. Ciò offre flessibilità aggiuntiva per eliminare le transazioni storiche del libro cespiti perché non sono state impegnate nella contabilità generale.

I giornali di registrazione cespiti vengono definiti mediante la pagina  Nomi giornale di registrazione da Contabilità generale >Impostazione del giornale di registrazione > Nomi giornale di registrazione. Ciascun giornale di registrazione in cui sia possibile registrare ammortamenti viene definito in base al relativo nome di giornale di registrazione per un solo livello di registrazione. Il livello di registrazione nel giornale di registrazione non può essere modificato. Tale restrizione assicura che le transazioni per ciascun livello di registrazione vengono mantenute separate. Per ciascun livello di registrazione è necessario creare almeno un nome di giornale di registrazione. Se si utilizzano i libri che non vengono registrati nella contabilità generale, è inoltre necessario creare un giornale di registrazione in cui il livello di registrazione è Nessuno.

È possible designare conti CoGe per le transazioni cespiti nella pagina Profili registrazione cespiti. Per ciascun profilo registrazione, è necessario selezionare il tipo di transazione e il libro pertinenti e quindi designare i conti CoGe. Impostare un record di profilo registrazione per ciascun libro che verrà registrato nella contabilità generale.

Il cespite può essere inserito in documenti che supportano solo il livello di registrazione **Corrente**, come **Ordine fornitore**, **Fattura fornitore in sospeso**, **Ordine cliente** o **Fattura a testo libero**. Durante la selezione di un ID cespite in uno qualsiasi di questi documenti, il libro cespiti viene filtrato sul libro con livello di registrazione **Corrente** e verrà compilato automaticamente durante la registrazione quando il sistema convalida che il livello di registrazione cespite è **Corrente**. Se tale convalida non può essere completata, il processo di registrazione verrà interrotto. 

> [!NOTE] 
> L'utilizzo di libri derivati consente di registrare transazioni contemporaneamente in diversi livelli di registrazione. Le transazioni del libro principale vengono create in un giornale di registrazione o documento di origine con il livello di registrazione corrispondente a quello del libro. Durante la registrazione le transazioni del libro derivato vengono registrate nei livelli di registrazione appropriati. 


Per ulteriori informazioni, vedere [Libri derivati](derived-books.md) e [Registrare con i libri derivati](post-derived-value-models.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]