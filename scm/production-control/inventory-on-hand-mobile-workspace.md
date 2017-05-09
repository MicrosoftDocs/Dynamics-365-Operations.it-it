---
title: "Area di lavoro mobile Disponibilità scorte per l&quot;app Microsoft Dynamics 365 for Operations"
description: L&quot;area di lavoro mobile Scorte disponibili consente di ottenere informazioni su dispositivo mobile relative alle scorte disponibili e prenotate in qualsiasi momento e ovunque.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Area di lavoro mobile Disponibilità scorte per l'app Microsoft Dynamics 365 for Operations

L'area di lavoro mobile Scorte disponibili consente di ottenere informazioni su dispositivo mobile relative alle scorte disponibili e prenotate in qualsiasi momento e ovunque. 

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                         | descrizione                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Informazioni sulla piattaforma mobile Microsoft Dynamics 365 for Operations | [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 for Operations                                          | Un ambiente con Microsoft Dynamics 365 for Operations versione 1611 e aggiornamento 3 della piattaforma di Microsoft Dynamics for Operations (novembre 2016) |
| Hotfix KB 3215650                                                    | Impostare l'hotfix per abilitare le aree di lavoro che vengono fornite in Microsoft Dynamics 365 for Operations.                                       |
| Dispositivo mobile con l'app Dynamics 365 for Operations installata | Scaricare l'app Dynamics 365 for Operations dall'App Store mobile.                                                                           |

## <a name="introduction"></a>Introduzione
In genere, le società con più spedizioni e più ricevimenti di scorte ogni giorno. Tali movimenti modificano costantemente lo stato delle scorte disponibili. L'area di lavoro mobile Scorte disponibili consente di visualizzare lo stato delle scorte interaziendali disponibili, in modo da poter ottenere le informazioni più aggiornate sui dati delle scorte sul dispositivo mobile di propria scelta. Indipendentemente dal fatto che si lavori nel magazzino o nei reparti acquisti, vendite, produzione, gestione o si ricoprano altri ruoli, è possibile accedere ai dati sulle scorte disponibili in qualsiasi momento e ovunque. L'area di lavoro mobile offre un punto di vista istantaneo dello stato di disponibilità in tutte le strutture e consente di visualizzare le scorte disponibili in tutte le strutture, le prenotazioni correnti di materiali e le scorte disponibili non prenotate. È inoltre possibile immettere i numeri di articolo per eseguire query sulle scorte disponibili ed eseguire una ricerca filtrata per i prodotti o le varianti disponibili. In particolare, l'area di lavoro mobile fornisce le seguenti funzionalità:

-   È possibile cercare per nome o numero di prodotto per individuare i prodotti per i quali visualizzare lo stato delle scorte disponibili.
-   Per i prodotti selezionati, è possibile visualizzare le seguenti informazioni:
    -   Scorte disponibili in base al sito
    -   Scorte disponibili in base al magazzino
    -   Scorte disponibili in base alla località
    -   Scorte disponibili per batch (per prodotti controllati in base ai batch)
    -   Scorte disponibili in base allo stato dell'inventario

<!-- -->

-   Le scorte di prodotti disponibili vengono visualizzate nei seguenti modi:
    -   Per scorte fisiche (questa visualizzazione rappresenta l'importo totale).
    -   Per scorte prenotate (questa visualizzazione rappresenta l'importo prenotato).
    -   Per scorte fisiche disponibili (questa visualizzazione rappresenta la quantità disponibile senza prenotazioni).

## <a name="get-started"></a>Per iniziare
Per iniziare sul dispositivo mobile:

1.  Nell'App Store mobile, scaricare e installare l'app Microsoft Dynamics 365 for Operations.
2.  Avviare l'app sul dispositivo.
3.  Immettere il proprio URL Dynamics 365.
4.  Immettere la società a cui accedere. Ad esempio, immettere **USMF**.
5.  La prima volta che si accede, verrà richiesto di specificare il nome utente e la password per l'account Microsoft Dynamics 365 for Operations. Immettere le proprie credenziali. Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.

Per visualizzare le aree di lavoro nell'app mobile, è necessario innanzitutto pubblicare le aree di lavoro desiderate nell'app Dynamics 365 for Operations.

1.  Avviare Dynamics 365 for Operations.
2.  Passare ad **Amministrazione sistema** &gt; **Impostazioni** &gt; **Parametri di sistema**.
3.  Selezionare **Gestisci app per dispositivi mobili**.
4.  Selezionare l'area di lavoro da pubblicare nella piattaforma mobile.
5.  Selezionare **Pubblica area di lavoro**.
6.  Aggiornare il dispositivo per visualizzare le aree di lavoro pubblicate.

## <a name="view-the-onhand-inventory-for-a-product"></a>Visualizzare le scorte disponibili per un prodotto
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Scorte disponibili**.
2.  Selezionare **Verifica disponibilità per un articolo**. Viene visualizzato un elenco dei prodotti caricati nell'app per l'utilizzo offline. Per impostazione predefinita, 50 articoli vengono caricati, ma è possibile cambiare questo numero. Per ulteriori informazioni, vedere il manuale iniziale.
3.  Se l'articolo non è presente nell'elenco, selezionare **Cerca altro** per effettuare una ricerca online in Dynamics 365 for Operations. Cercare per numero di prodotto o passare a una ricerca per nome di prodotto.
4.  Selezionare un prodotto. Se l'articolo dispone di un'immagine, l'immagine viene visualizzata.
5.  Selezionare una delle seguenti opzioni per visualizzare lo stato delle scorte disponibili:
    -   Visualizzare le scorte disponibili in base al sito
    -   Visualizzare le scorte disponibili in base al magazzino
    -   Visualizzare le scorte disponibili in base alla località
    -   Visualizzare le scorte disponibili per batch (per prodotti controllati in base ai batch)
    -   Visualizzare le scorte disponibili in base allo stato dell'inventario

    Le scorte di prodotti disponibili vengono visualizzate nei seguenti modi:
    -   Per scorte fisiche (questa visualizzazione rappresenta l'importo totale).
    -   Per scorte prenotate (questa visualizzazione rappresenta l'importo prenotato).
    -   Per scorte fisiche disponibili (questa visualizzazione rappresenta la quantità disponibile senza prenotazioni).




