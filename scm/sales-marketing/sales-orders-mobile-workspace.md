---
title: Area di lavoro mobile per ordini cliente
description: In questo argomento vengono fornite informazioni sull&quot;area di lavoro mobile per ordini cliente, disponibile per l&quot;app mobile Microsoft Dynamics 365 for Operations. Questa area di lavoro offre aggiornamenti costanti sugli ordini cliente in qualsiasi momento e ovunque.
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 119b80e5d8067ffbf75d8b067f4803558c2c94b0
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Area di lavoro mobile per ordini cliente

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'area di lavoro mobile per ordini cliente, disponibile per l'app mobile Microsoft Dynamics 365 for Operations. Questa area di lavoro offre aggiornamenti costanti sugli ordini cliente in qualsiasi momento e ovunque. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Panoramica dell'area di lavoro mobile per ordini cliente
---------------------------------------------

L'area di lavoro mobile **Ordini cliente** accede a Microsoft Dynamics 365 for Operations e consente di visualizzare informazioni dettagliate su ogni ordine cliente. Tali informazioni includono lo stato dell'ordine, le informazioni di contatto per il cliente e le informazioni di contatto per l'incaricato dell'ordine. L'area di lavoro mobile **Ordini cliente** offre una visualizzazione immediata degli ordini cliente. È possibile visualizzare gli ordini cliente o visualizzare gli ordini cliente in base al cliente oppure visualizzare le informazioni relative a un ordine cliente specifico. L'area di lavoro mobile offre due visualizzazioni che rendono più semplice analizzare a fondo gli ordini cliente.

### <a name="view-all-sales-orders"></a>Visualizza tutti gli ordini cliente

Questa visualizzazione elenca tutti gli ordini cliente.

-   Utilizzare uno dei seguenti filtri per selezionare gli ordini cliente da visualizzare.
    -   Cerca per ordine cliente
    -   Cerca per account cliente
    -   Cerca per nome cliente
    -   Cerca per stato
    -   Cerca per stato di rilascio
    -   Cerca per data e ora di creazione
-   Dopo aver selezionato gli ordini cliente, è possibile visualizzare i dettagli di ordini specifici. In particolare, è possibile visualizzare le seguenti informazioni:
    -   Informazioni sul nome e sull'indirizzo del cliente
    -   Diverse date per l'ordine cliente, ad esempio la data di spedizione richiesta e la data di spedizione confermata
    -   Informazioni di contatto per l'addetto all'ordine
    -   Informazioni di contatto del cliente
    -   Righe ordine
    -   Spedizioni che indicano la modalità e la data di spedizione dell'ordine cliente

### <a name="view-orders-for-a-customer"></a>Visualizza ordini per un cliente

Questa visualizzazione elenca gli ordini cliente per cliente.

-   Utilizzare uno dei seguenti filtri per visualizzare gli ordini per un cliente:
    -   Cerca per nome
    -   Cerca per account
-   Dopo avere selezionato un cliente, è possibile visualizzare le seguenti informazioni:
    -   Nome cliente e gruppo
    -   Informazioni di contatto del cliente
    -   Ordini cliente e dettagli su tali ordini cliente:
        -   Informazioni sul nome e sull'indirizzo del cliente
        -   Diverse date dell'ordine cliente
        -   Informazioni di contatto per l'addetto all'ordine
        -   Informazioni di contatto del cliente
        -   Righe ordine
        -   Spedizioni che indicano la modalità e la data di spedizione dell'ordine cliente

## <a name="prerequisites"></a>Prerequisiti
Prima di utilizzare l'area di lavoro mobile **Ordini cliente**, è necessario verificare che l'amministratore di sistema abbia predisposto i seguenti prerequisiti.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Deve essere stato implementato Dynamics 365 for Operations versione 1611 con aggiornamento alla piattaforma 3 o versione successiva.</td>
<td>Amministratore di sistema</td>
<td>Se Dynamics 365 for Operations non è ancora stato distribuito nell'organizzazione, l'amministratore di sistema deve vedere <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Distribuire un ambiente di dimostrazione di Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Deve essere stato implementato l'articolo KB 4013633.</td>
<td>Amministratore di sistema</td>
<td>KB 4013633 (un aggiornamento X++ o aggiornamento rapido dei metadati) contiene quattro aree di lavoro mobili per la gestione della supply chain. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li>Eseguire il download di KB 4013633 da Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Applicare il pacchetto distribuibile</a> al sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'area di lavoro mobile <strong>Ordini cliente</strong> deve essere pubblicata nell'app mobile Dynamics 365 for Operations.</td>
<td>Amministratore di sistema</td>
<td><ol>
<li>Avviare Dynamics 365 for Operations nel browser.</li>
<li>Nella pagina <strong>Paramenti di sistema</strong> selezionare <strong>Gestisci aree di lavoro mobili</strong>.</li>
<li>Selezionare l'area di lavoro <strong>Ordini cliente</strong>.</li>
<li>Fare clic su <strong>Pubblica area di lavoro mobile</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Scaricare e installare l'app mobile Microsoft Dynamics 365 for Operations.
Scaricare e installare l'app mobile Microsoft Dynamics 365 for Operations dall'App Store mobile.

-   Per Android: [Dynamics 365 for Operations in Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Per iPhone: [Dynamics 365 for Operations nell'app store iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Accedere all'app mobile Microsoft Dynamics 365 for Operations
1.  Avviare l'app sul dispositivo mobile.
2.  Immettere l'URL per Dynamics 365 for Operations.
3.  Immettere la società a cui accedere. Ad esempio, immettere **USMF**.
4.  La prima volta che si accede, verrà richiesto di specificare il nome utente e la password per l'account Dynamics 365 for Operations. Immettere le proprie credenziali.
5.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è possibile effettuare il pull per aggiornare l'elenco delle aree di lavoro mobili. 

    [![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>Consente di visualizzare informazioni sugli ordini cliente per un cliente tramite l'area di lavoro mobile
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Ordini cliente**.
2.  Selezionare **Visualizza ordini per un cliente**.
3.  Utilizzare le informazioni su conto o nome cliente per individuare il cliente desiderato.
4.  Selezionare il cliente.
5.  Selezionare **Informazioni di contatto** o **Ordini cliente**. Se si seleziona **Ordini cliente**, viene visualizzato un elenco di ordini cliente del cliente.
6.  Selezionare **Ordine cliente**. È ora possibile visualizzare informazioni su righe dell'ordine cliente, spedizioni, informazioni di contatto del cliente e dell'incaricato dell'ordine.





