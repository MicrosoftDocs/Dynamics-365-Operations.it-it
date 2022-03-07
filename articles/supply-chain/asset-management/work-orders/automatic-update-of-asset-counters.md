---
title: Aggiornamento automatico dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento automatico dei contatori di cespiti in Gestione cespiti
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9a3814a575fbe4379b59723f269d83379a253ede71962c0c82b5f4cc55d36e6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738297"
---
# <a name="automatic-update-of-asset-counters"></a>Aggiornamento automatico dei contatori di cespiti

[!include [banner](../../includes/banner.md)]

Per informazioni sulla registrazione manuale dei contatori di cespiti, vedere [Aggiornamento manuale dei contatori di cespiti](../work-orders/manual-update-of-asset-counters.md). Per informazioni su come impostare i contatori di cespiti, vedere [Contatori](../setup-for-objects/counters.md).

I valori dei contatori possono essere aggiornati automaticamente dalle registrazioni di produzione, basate sulle ore di produzione o sulla quantità di produzione (ossia la quantità prodotta). Questo aggiornamento viene eseguito nella pagina **Aggiornare i contatori di cespiti**. È possibile aggiornare uno o più cespiti impostando il parametro **Dal**. Questo parametro specifica la data di inizio per le registrazioni di produzione (ore di produzione o quantità di produzione). In altre parole, specifica la data di inizio dell'aggiornamento dei controvalori.

Tutti i cespiti correlati a una risorsa *e* che hanno contatori di cespiti, i quali sono impostati per essere aggiornati in base alle ore di produzione o alla quantità di produzione, saranno inclusi in un aggiornamento automatico. I nuovi controvalori verranno creati.

Per i contatori basati sulla quantità di produzione, il conteggio include la quantità idonea e la quantità difettosa registrate. Se l'unità utilizzata per la registrazione della quantità di produzione è diversa dall'unità utilizzata per il contatore, la quantità viene convertita per corrispondere all'unità del contatore.

Come descritto in precedenza, i contatori automatici possono essere aggiornati dalle registrazioni di produzione. Di conseguenza, il cespite per il quale si desidera aggiornare automaticamente i contatori deve essere associato a una risorsa (macchina). Quando le quantità prodotte o le ore di produzione sono state registrate nella risorsa, è possibile aggiornare i contatori di cespiti correlati.

1. Selezionare **Gestione cespiti** > **Periodico** > **Cespiti** > **Aggiorna contatori di cespiti**.

2. Selezionare la data di inizio dell'aggiornamento automatico nel campo **Dal**.

    >[!NOTE]
    >La data in questo campo corrisponde alla data "WIP" in **Transazioni cicli di lavorazione** (**Controllo produzione** > **Richieste di informazioni e report** > **Produzione** > **Transazioni cicli di lavorazione** > **Data effettiva**).

3. Nella Scheda dettaglio **Record da includere**, è possibile selezionare i cespiti, i tipi di cespite o le risorse per l'aggiornamento automatico. Selezionare **Filtro** ed effettuare la selezione delle opzioni rilevanti.

4. Nella Scheda dettaglio **Esecuzione in background**, è possibile impostare l'aggiornamento automatico come processo batch, come necessario.

    Nella figura seguente è illustrato un esempio della finestra di dialogo **Aggiornare i contatori di cespiti**.

    ![Figura 1.](media/12-work-orders.png)

5. Selezionare **OK**. 

Dopo l'aggiornamento automatico del contatore di cespiti, è possibile visualizzare le registrazioni del contatore correlate al cespite nella pagina **Contatori cespiti**. Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**, selezionare il cespite, quindi nel riquadro azioni, nella scheda **Cespite**, nel gruppo **Preventivo** selezionare **Contatori**.

Nella pagina **Valore aggregato cespiti**, è possibile ottenere una panoramica dell'ultima registrazione effettuata in tutti i cespiti di tutti i tipi. Selezionare **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Valore aggregato cespiti**. Questa pagina è simile alla pagina **Contatori cespiti**, ma non è possibile aggiungere o modificare le registrazioni. La visualizzazione è disponibile solo a scopo informativo.

Nella figura seguente è illustrato un esempio della pagina **Valore aggregato cespiti**.

![Figura 2.](media/13-work-orders.png)

Notare i punti seguenti:

- È comunque possibile creare registrazioni manuali dei valori di contatore per i tipi di contatori che vengono aggiornati automaticamente. Per ulteriori informazioni, vedere [Aggiornamento manuale dei contatori di cespiti](../work-orders/manual-update-of-asset-counters.md).

- È possibile impostare i contatori correlati a un altro contatore. In questo caso, quando un contatore viene aggiornato, i contatori correlati vengono aggiornati automaticamente contemporaneamente. Per ulteriori informazioni su come impostare i contatori correlati, vedere [Contatori](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]