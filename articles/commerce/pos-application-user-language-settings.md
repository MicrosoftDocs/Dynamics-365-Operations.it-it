---
title: Applicazione POS e impostazioni della lingua dell'utente
description: In questo argomento viene descritto come modificare le impostazioni della lingua in Modern POS (MPOS) e Cloud POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 49bfcaa4c05ea8e6cc6bf0a8f855f2474cea35bc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413568"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Applicazione POS e impostazioni della lingua dell'utente

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come modificare le impostazioni della lingua in Modern POS (MPOS) e Cloud POS.

## <a name="overview"></a>Panoramica
Modern POS (MPOS) e Cloud POS supportano ambienti in cui le impostazioni di lingua e le traduzioni possono variare tra il punto vendita e le impostazioni dell'utente. Ad esempio, il punto vendita può trovarsi in uno stato/regione in cui l'inglese è più comune per i propri clienti, ma alcuni lavoratori preferiscono utilizzare l'applicazione con le traduzioni francesi.

## <a name="data-language"></a>Lingua dei dati

Indipendentemente dalle impostazioni utente, MPOS e Cloud POS useranno sempre le impostazioni di lingua del punto vendita per determinare le traduzioni utilizzate per i dati. In questo modo, vi sarà uniformità di esperienza tra tutti gli utenti e i clienti. Di seguito sono riportati alcuni esempi di dati:

- Prodotti
- Attributi e valori
- Nomi di categoria
- Ricevute di transazioni stampate o inviate tramite posta elettronica
- Nomi di metodi di pagamento
- Messaggi di visualizzazione riga

La lingua del punto vendita verrà utilizzata per la schermata di accesso principale al POS, poiché l'utente non è noto prima dell'accesso. Se per la lingua del punto vendita non è disponibile una traduzione, il POS utilizzerà la lingua della società.

### <a name="configuring-the-stores-language-setting"></a>Configurazione dell'impostazione della lingua del punto vendita

La lingua del punto vendita viene impostata da **Tutti i punti vendita** nella pagina **Punto vendita** in **Generale &gt; Impostazioni internazionali &gt; Lingua**. Usare l'elenco a discesa per scegliere la lingua per ciascun punto vendita.

## <a name="user-interface-language"></a>Lingua dell'interfaccia utente

L'impostazione della lingua dell'utente del POS determina le traduzioni utilizzate nell'interfaccia utente dell'applicazione. Sono inclusi tutti i menu, le etichette e gli elenchi che non sono considerati come dati. Fa eccezione il testo che viene visualizzato nelle griglie dei pulsanti del POS. Le griglie dei pulsanti non supportano le traduzioni, pertanto il testo sarà sempre visualizzato così come è definito sul pulsante. Per supportare i pulsanti tradotti, sarà necessario copiare e gestire griglie di pulsanti separate e assegnarle agli utenti nel modo appropriato.

### <a name="configuring-the-users-language-setting"></a>Configurazione dell'impostazione della lingua dell'utente

L'impostazione della lingua dell'utente viene impostata in **Tutti i lavoratori** nella pagina **Lavoratore** in **Retail e Commerce &gt; Lingua**. Non viene impostata nella scheda Profilo. Questa impostazione non viene utilizzata dal POS. Se la lingua dell'utente non è impostata o è impostata una lingua per cui le traduzioni non sono disponibili, il POS tornerà alla lingua del punto vendita.

|             | Lingua dell'interfaccia utente                   | Lingua dei dati (prodotti, formati ricevuta, visualizzazione riga e così via). |
|-------------|----------------------------|---------------------------------------------------------------|
| **Società** | Valori predefiniti                    | Valori predefiniti                                                       |
| **Punto vendita**   | Sovrascrive la società          | Sovrascrive la società                                             |
| **Utente**    | Sovrascrive il punto vendita o la società | Mai                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]