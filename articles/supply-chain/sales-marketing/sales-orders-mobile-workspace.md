---
title: Area di lavoro mobile per ordini cliente
description: In questo articolo vengono fornite informazioni sull'area di lavoro mobile Ordini cliente. Questa area di lavoro offre aggiornamenti costanti sugli ordini cliente in qualsiasi momento e ovunque.
author: Henrikan
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 38971f2a5f3f3d2692de0e52365e2215170101cc
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103182"
---
# <a name="sales-orders-mobile-workspace"></a>Area di lavoro mobile per ordini cliente

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

In questo articolo vengono fornite informazioni sull'area di lavoro mobile **Ordini cliente**. Questa area di lavoro offre aggiornamenti costanti sugli ordini cliente in qualsiasi momento e ovunque. 

Questa area di lavoro mobile può essere utilizzata con l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365).

## <a name="overview"></a>Panoramica
L'area di lavoro mobile **Ordini cliente** consente di visualizzare informazioni dettagliate su ogni ordine cliente. Tali informazioni includono lo stato dell'ordine, le informazioni di contatto per il cliente e le informazioni di contatto per l'incaricato dell'ordine. L'area di lavoro mobile **Ordini cliente** offre una visualizzazione immediata degli ordini cliente. È possibile visualizzare gli ordini cliente o visualizzare gli ordini cliente in base al cliente oppure visualizzare le informazioni relative a un ordine cliente specifico. 

L'area di lavoro mobile offre due visualizzazioni che rendono più semplice analizzare a fondo gli ordini cliente.

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
I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Prerequisiti si utilizza Supply Chain Management 
Se Supply Chain Management è stato distribuito nell'organizzazione, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Ordini cliente**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Prerequisiti se si usa Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva
Se nell'organizzazione è stato distribuito Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti. 

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementare l'articoloo KB 4013633.</td>
<td>Amministratore di sistema</td>

<td>l'articoloo KB 4013633 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Ordini cliente</strong>. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Ordini cliente</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili
Scarica e installa l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365):

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile

1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Dynamics 365.
3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

[![Trascinare verso il basso.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Consente di visualizzare informazioni sugli ordini cliente per un cliente tramite l'area di lavoro mobile Ordini cliente

1.  Sul dispositivo mobile, selezionare l'area di lavoro **Ordini cliente**.
2.  Selezionare **Visualizza ordini per un cliente**.
3.  Utilizzare le informazioni su conto o nome cliente per individuare il cliente desiderato.
4.  Selezionare il cliente.
5.  Selezionare **Informazioni di contatto** o **Ordini cliente**. Se si seleziona **Ordini cliente**, viene visualizzato un elenco di ordini cliente del cliente.
6.  Selezionare **Ordine cliente**. È ora possibile visualizzare informazioni su righe dell'ordine cliente, spedizioni, informazioni di contatto del cliente e dell'incaricato dell'ordine.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

