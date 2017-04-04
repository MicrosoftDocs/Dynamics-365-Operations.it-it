---
title: Applicazione POS e impostazioni della lingua dell&quot;utente
description: In questo argomento viene descritto come modificare le impostazioni in lingua nel POS moderno al dettaglio) (MPOS e appannarsi il POS.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>Applicazione POS e impostazioni della lingua dell'utente

In questo argomento viene descritto come modificare le impostazioni in lingua nel POS moderno al dettaglio) (MPOS e appannarsi il POS.

<a name="overview"></a>Panoramica
========

Moderno POS al dettaglio) (MPOS e ambienti del supporto del POS cloud in cui le impostazioni e le traduzioni della lingua possono variare dal punto vendita e le impostazioni utente. Ad esempio, il punto vendita può trovarsi in uno stato/regione in cui inglese è più comune per i propri clienti, ma alcuni lavoratori si preferisce utilizzare l'applicazione con le traduzioni francesi.

## <a name="data-language"></a>Lingua dei dati
Indipendentemente dalle impostazioni utente, MPOS e del POS cloud verranno sempre le impostazioni del linguaggio del punto vendita per determinare le traduzioni utilizzate per i dati. La stampa di tutti gli utenti e cliente siano presenti e coerente.  Esempi di dati includono:

-   Prodotti
-   Attributi e valori
-   Nomi di categoria
-   Ricevute di transazioni stampate o inviate tramite posta elettronica
-   Nomi di metodi di pagamento
-   Messaggi di visualizzazione riga

Lingua del punto vendita verrà utilizzata per la schermata di accesso principale di Retail POS, poiché l'utente non è noto prima dell'accesso. Se una conversione non è disponibile per la lingua del punto vendita, il POS ritornerà la lingua della società.

### <a name="configuring-the-stores-language-setting"></a>Configurazione dell'impostazione della lingua del punto vendita

L'impostazione della lingua del punto vendita viene impostata da ** tutte le vendite al dettaglio ** ** su Retail Store Inventory ** impagina ** nella lingua &gt; generale &gt; delle impostazioni internazionali. ** Utilizzare il calo discesa per selezionare la lingua per ogni punto vendita.

## <a name="user-interface-language"></a>Lingua dell'interfaccia utente
L'impostazione della lingua dell'utente di Retail POS determina le traduzioni utilizzate nell'interfaccia utente dell'applicazione. Sono incluse tutte le etichette, elenchi menu e non vengono considerati dati. Un'eccezione è il testo visualizzato nelle griglie dei pulsanti di Retail POS. Le griglie dei pulsanti non supportano le traduzioni, pertanto visualizzate sempre il testo come definito nel pulsante. Per supportare ha tradurre i pulsanti, sarà necessario copiare e gestire le griglie dei pulsanti separate e assegnarli agli utenti in base alle proprie esigenze.

### <a name="configuring-the-users-language-setting"></a>Configurazione dell'impostazione della lingua dell'utente

L'impostazione della lingua dell'utente di Retail POS viene impostata da ** tutti i lavoratori ** ** lavoratore ** alla pagina in lingua &gt; ** ** al dettaglio.  Non viene impostato nella scheda principale del profilo.  Questa impostazione non viene utilizzata da Retail POS. Se la lingua dell'utente non è impostata o è impostata una lingua per cui le traduzioni non sono disponibili, il POS tornerà alla lingua del punto vendita.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | ** Lingua viene installata ** ** **      | **Lingua dei dati (prodotti, formati ricevuta, visualizzazione riga e così via).** |
| **Società** | Valori predefiniti                    | Valori predefiniti                                                           |
| **Punto vendita**   | Sovrascrive la società          | Sovrascrive la società                                                 |
| **User**    | Sovrascrive il punto vendita o la società | Mai                                                             |




