---
title: Aggiornamento automatico dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento automatico dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875742"
---
# <a name="automatic-update-of-asset-counters"></a>Aggiornamento automatico dei contatori di cespiti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Nella sezione precedente, è stata descritta la registrazione manuale dei contatori di cespiti. L'impostazione dei contatori di cespiti è descritta in [Contatori](../setup-for-objects/counters.md).

I valori dei contatori possono essere aggiornati automaticamente dalle registrazioni di produzione, basate sulle ore di produzione o sulla quantità prodotta. A questo proposito, si utilizza **Aggiorna contatori di cespiti**. È possibile aggiornare uno o più cespiti inserendo il parametro **Dal**. Questo parametro specifica la data di inizio delle registrazioni di produzione (ore o quantità prodotte), ovvero la data a partire dalla quale i valori dei contatori devono essere aggiornati.

Tutti i cespiti correlati a una risorsa *e* che hanno contatori di cespiti, i quali sono impostati per essere aggiornati in base alle ore di produzione o alla quantità prodotta, saranno inclusi in un aggiornamento automatico e verranno creati nuovi valori dei contatori.

I contatori basati sulla quantità di produzione, la quantità idonea e la quantità difettosa registrate sono inclusi nel conteggio. Se l'unità utilizzata per la registrazione della quantità prodotta è diversa dall'unità utilizzata nel contatore, la quantità viene convertita per corrispondere all'unità del contatore.

Come descritto in precedenza, i contatori automatici possono essere aggiornati dalle registrazioni di produzione. Di conseguenza, il cespite per il quale si desidera aggiornare automaticamente i contatori deve essere associato a una risorsa (macchina). Le descrizioni riportate di seguito forniscono una panoramica dell'impostazione e dell'elaborazione degli ordini di produzione (nel modulo **Controllo produzione**), utilizzata come base per l'aggiornamento automatico dei contatori in un cespite nel modulo **Gestione cespiti**.

Quando le quantità prodotte o le ore di produzione sono state registrate nella risorsa, è possibile aggiornare i contatori di cespiti correlati.

1. Fare clic su **Gestione cespiti** > **Periodico** > **Cespiti** > **Aggiorna contatori di cespiti**.

2. Selezionare la data di inizio dell'aggiornamento automatico nel campo **Dal**.

>[!NOTE]
>La data in questo campo corrisponde alla data "WIP" in **Transazioni cicli di lavorazione** (**Controllo produzione** > **Richieste di informazioni e report** > **Produzione** > **Transazioni cicli di lavorazione** > **Data effettiva**).

3. Se si desidera selezionare specifici cespiti, tipi di cespite o risorse per l'aggiornamento automatico, fare clic su **Filtro** nella Scheda dettaglio **Record da includere** ed effettuare le selezioni pertinenti.

4. Se necessario, è possibile impostare l'aggiornamento automatico come processo batch nella Scheda dettaglio **Esecuzione in background**.

![Figura 1](media/12-work-orders.png)

5. Fare clic su **OK**. Dopo l'aggiornamento automatico dei contatori di cespiti, è possibile visualizzare le registrazioni contatore relative al cespite in **Contatori cespiti** (**Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti** > selezionare il cespite > pulsante **Contatori** ).

In **totali contatori cespiti**, è possibile ottenere una panoramica dell'ultima registrazione effettuata in tutti i cespiti di tutti i tipi. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Valore aggregato cespiti**. La visualizzazione è molto simile a **Contatori cespiti**, ma non è possibile aggiungere o modificare le registrazioni in **Valore aggregato cespiti**. La visualizzazione è disponibile solo a scopo informativo.

![Figura 2](media/13-work-orders.png)


- È sempre possibile creare registrazioni manuali dei valori di contatore per i tipi di contatori che vengono aggiornati automaticamente. Per ulteriori informazioni, fare riferimento alla sezione "Aggiornamento manuale dei contatori di cespiti".
- È possibile impostare contatori correlati a un altro contatore, ovvero quando un contatore viene aggiornato, anche i contatori associati vengono aggiornati automaticamente. Leggere l'argomento [Contatori](../setup-for-objects/counters.md) per informazioni sull'impostazione di contatori associati.
