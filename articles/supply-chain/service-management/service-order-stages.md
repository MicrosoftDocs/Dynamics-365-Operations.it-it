---
title: Fasi dell'ordine di assistenza
description: Tramite la definizione delle fasi di un ordine di assistenza e la loro assegnazione ai lavoratori, è possibile controllare il flusso di un ordine di assistenza tramite le attività che varie persone eseguono nell'organizzazione che presta tale servizio.
author: sorenva
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e748afbd159d7a8fca1372676872cc02dd7ea57
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671732"
---
# <a name="service-order-stages"></a>Fasi dell'ordine di assistenza   

[!include [banner](../includes/banner.md)]


È possibile impostare le fasi di un ordine di assistenza per definire le attività da completare, l'ordine in cui vengono completate e i lavoratori responsabili del loro completamento. Tramite la definizione delle fasi di un ordine di assistenza e la loro assegnazione ai lavoratori, è possibile controllare il flusso di un ordine di assistenza tramite le attività che varie persone eseguono nell'organizzazione che presta tale servizio. La sequenza delle fasi deve includere una fase iniziale.

È inoltre possibile definire le azioni consentite a ogni fase. Ad esempio, se si deseleziona la casella di controllo **Registrazione** per tutte le fasi eccetto la fase finale, si impedisce agli ordini di assistenza di essere registrati prima che vengano elaborati tramite la sequenza completa di fasi.

## <a name="branching-in-service-order-stages"></a>Creazione di un ramo nelle fasi di un ordine di assistenza

Quando si imposta una fase di assistenza, è possibile creare più opzioni, o più rami, da cui scegliere per la fase di assistenza successiva. Tutti i rami creati sono disponibili per la selezione dal completamento della fase iniziale. Ad esempio, si imposta **Pianificazione** come fase iniziale. Si creano due fasi denominate **In corso** e **Annulla**, quindi si seleziona **Pianificazione** come elemento principale. Assegnare la fase **Pianificazione** all'ordine cliente. Quando la fase di pianificazione dell'ordine cliente viene completata, è possibile selezionare la fase **In corso** se l'ordine cliente è pronto a lavorare oppure è possibile selezionare la fase **Annulla** se l'ordine cliente viene annullato.

## <a name="see-also"></a>Vedere anche

[Imposta le fasi dell'ordine di assistenza](set-up-service-order-stages.md)

[Cambiare la fase dell'ordine di assistenza](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]