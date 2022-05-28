---
title: Profili valutazione
description: In questo argomento viene descritto come impostare i profili valutazione.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2512b79c87a4640a2b31b7699e85d743b451a14c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676441"
---
# <a name="rating-profiles"></a>Profili valutazione

[!include [banner](../../includes/banner.md)]

Un profilo di valutazione è simile a un contratto di logistica (ma non a un contratto legale). Viene utilizzato per determinare le tariffe di trasporto per i carichi. 

Ogni profilo di valutazione è univoco per il vettore di spedizione. Nel profilo si associa il vettore di spedizione ai dati master tariffe. I dati master tariffe definiscono l'assegnazione di base delle tariffe e la base tariffaria. La base tariffaria determina la tariffa del vettore.

È possibile impostare un profilo di valutazione utilizzando una pagina generica contenente una panoramica di tutti i profili di valutazione esistenti. In alternativa è possibile impostare un profilo di valutazione direttamente dal vettore di spedizione. In entrambi i casi, le informazioni impostate per il profilo di valutazione sono le stesse.

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a>Creare o modificare un profilo di valutazione nella pagina Profili valutazione

Nella pagina **Profili valutazione** è possibile rivedere tutti i profili di valutazione disponibili. Inoltre, è possibile modificare i profili esistenti e creare nuovi profili.

1. Passare a **Gestione trasporto \> Impostazioni \> Valutazione \> Profilo valutazione**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere un nuovo profilo di valutazione alla griglia oppure selezionare **Modifica** per modificare un profilo esistente.
1. Nella riga del profilo di valutazione nuovo o esistente, impostare i seguenti campi:

    - **Profilo valutazione** – Immettere un identificatore univoco (ID) per il profilo di valutazione.
    - **Nome** – Immettere un nome descrittivo per il profilo di valutazione.
    - **Vettore di spedizione** – Selezionare un corriere. Il profilo di valutazione che si sta impostando verrà mostrato anche nella pagina **Vettori di spedizione** per il vettore selezionato.
    - **Sito** e **Magazzino** - Selezionare un sito e un magazzino.
    - **Motore tariffe** - Selezionare il motore delle tariffe per il profilo di valutazione.
    - **Tariffa principale** - Selezionare la tariffa principale per il profilo di valutazione. I dati master tariffe possono essere utilizzati per definire il tipo di base tariffaria e una base tariffaria. Per ulteriori informazioni, vedere [Impostare i dati master tariffe](set-up-rate-masters.md).
    - **Motore tempo di transito** - Selezionare il motore del tempo di transito per il profilo di valutazione.
    - **Indice carburante vettore** – Selezionare il motore transito e l'indice carburante del vettore per il profilo di valutazione.
    - **Data e ora di inizio validità** e **Data e ora di fine validità** - Definire il periodo in cui il profilo di valutazione deve essere attivo.

1. Nel riquadro azioni selezionare **Salva**.

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a>Creare un profilo di valutazione direttamente nella pagina Vettori spedizione

1. Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.
1. Selezionare un vettore di spedizione nell'elenco.
1. Nella Scheda dettaglio **Profili valutazione** selezionare **Nuovo** per creare un profilo di valutazione.
1. Impostare i campi per il nuovo profilo di valutazione. Questi campi corrispondono ai campi nella pagina **Profili di valutazione**, come descritto nella sezione precedente di questo argomento.

> [!NOTE]
> I profili creati nella pagina **Vettori di spedizione** vengono visualizzati anche nella pagina **Profili di valutazione**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]