---
title: Area di lavoro mobile Gestione ordini cliente per l&quot;app Microsoft Dynamics 365 for Operations
description: "Con l&quot;area di lavoro mobile per gli ordini cliente, è possibile avere informazioni sempre aggiornate sugli ordini cliente ovunque ci si trovi."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Area di lavoro mobile Gestione ordini cliente per l'app Microsoft Dynamics 365 for Operations

Con l'area di lavoro mobile per gli ordini cliente, è possibile avere informazioni sempre aggiornate sugli ordini cliente ovunque ci si trovi. 

<a name="prerequisites"></a>Prerequisiti
-------------

| Prerequisito                                                         | descrizione                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Informazioni sulla piattaforma mobile Microsoft Dynamics 365 for Operations | [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Assicurarsi di utilizzare un ambiente con Microsoft Dynamics 365 for Operations versione 1611 e l'aggiornamento 3 della piattaforma di Microsoft Dynamics for Operations (novembre 2016). |
| Hotfix KB 3215650                                                    | Impostare l'hotfix per abilitare le aree di lavoro che vengono fornite in Microsoft Dynamics 365 for Operations.                                                                       |
| Dispositivo mobile con l'app Dynamics 365 for Operations installata | Scaricare l'app Dynamics 365 for Operations dall'App Store mobile.                                                                                                      |

## <a name="overview"></a>Panoramica
Questa area di lavoro mobile accede all'applicazione Dynamics 365 for Operations e consente di visualizzare informazioni dettagliate su ogni ordine cliente, ad esempio lo stato dell'ordine, le informazioni di contatto del cliente e le informazioni di contatto dell'incaricato dell'ordine. L'area di lavoro mobile offre una visualizzazione immediata degli ordini cliente. È possibile visualizzare gli ordini cliente in base al cliente, visualizzare tutti gli ordini cliente oppure visualizzare le informazioni relative a un ordine cliente specifico. L'area di lavoro mobile offre due visualizzazioni che rendono più semplice analizzare a fondo gli ordini cliente.

### <a name="view-all-sales-orders"></a>Visualizza tutti gli ordini cliente

Questa visualizzazione elenca tutti gli ordini cliente.

-   Utilizzare uno dei seguenti filtri per selezionare gli ordini cliente che si desidera visualizzare.
    -   Cerca per ordine cliente
    -   Cerca per account cliente
    -   Cerca per nome cliente
    -   Cerca per stato
    -   Cerca per stato di rilascio
    -   Cerca per data e ora di creazione

<!-- -->

-   Dopo aver selezionato gli ordini cliente, è possibile visualizzare i dettagli di ordini specifici. In particolare, è possibile visualizzare:
    -   Informazioni sul nome e sull'indirizzo del cliente
    -   Diverse date dell'ordine cliente, ad esempio la data di spedizione richiesta e la data di spedizione confermata
    -   Informazioni di contatto dell'incaricato dell'ordine
    -   Informazioni di contatto del cliente
    -   Righe ordine
    -   Spedizioni che indicano la modalità e la data di spedizione dell'ordine cliente

### <a name="view-orders-for-a-customer-"></a>Visualizza ordini per un cliente** **

Questa visualizzazione elenca gli ordini cliente in base al cliente.

-   Utilizzare uno dei seguenti filtri per visualizzare gli ordini per un cliente.
    -   Cerca per nome
    -   Cerca per account

<!-- -->

-   Dopo avere selezionato un cliente, è possibile visualizzare:
    -   Nome cliente e gruppo
    -   Informazioni di contatto del cliente
    -   Ordini cliente e dettagli sugli ordini cliente:
        -   Informazioni sul nome e sull'indirizzo del cliente
        -   Diverse date dell'ordine cliente
        -   Informazioni di contatto dell'incaricato dell'ordine
        -   Informazioni di contatto del cliente
        -   Righe ordine
        -   Spedizioni che indicano la modalità e la data di spedizione degli ordini cliente

## <a name="get-started"></a>Per iniziare
Attenersi a questa procedura per iniziare a utilizzare l'area di lavoro mobile degli ordini cliente sul proprio dispositivo mobile.

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

## <a name="view-information-about-sales-orders-for-a-customer"></a>Visualizzare informazioni sugli ordini cliente per un cliente specifico
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Ordini cliente**.
2.  Selezionare **Visualizza ordini per un cliente**.
3.  Utilizzare le informazioni **Account **o **Nome cliente** per individuare il cliente desiderato.
4.  Selezionare il cliente.
5.  Selezionare **Informazioni di contatto** o **Ordini cliente**.
6.  Se si seleziona **Ordini cliente**, viene visualizzato un elenco di ordini cliente del cliente.
7.  Selezionare **Ordine cliente**.
8.  Qui è possibile visualizzare informazioni sulle righe dell'ordine cliente, le spedizioni, le informazioni di contatto del cliente e dell'incaricato dell'ordine.




