---
title: Area di lavoro mobile per scorte disponibili
description: In questo argomento vengono fornite informazioni sull&quot;area di lavoro mobile per scorte disponibili, disponibile per l&quot;app mobile Microsoft Dynamics 365 for Operations. Questa area di lavoro mobile consente di ottenere informazioni su dispositivo mobile relative alle scorte disponibili e prenotate in qualsiasi momento e ovunque.
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7387df37e047d5ab7a90b696a6ffa249094499c4
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Area di lavoro mobile per scorte disponibili

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'area di lavoro mobile per scorte disponibili, disponibile per l'app mobile Microsoft Dynamics 365 for Operations. Questa area di lavoro mobile consente di ottenere informazioni su dispositivo mobile relative alle scorte disponibili e prenotate in qualsiasi momento e ovunque.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Panoramica dell'area di lavoro mobile per scorte disponibili
--------------------------------------------------

In genere, le società con più spedizioni e più ricevimenti di scorte ogni giorno. Tali movimenti modificano costantemente lo stato delle scorte disponibili. L'area di lavoro mobile **Scorte disponibili** consente di visualizzare lo stato delle scorte interaziendali disponibili, in modo da poter ottenere le informazioni più aggiornate sui dati delle scorte sul dispositivo mobile di propria scelta. Indipendentemente dal fatto che si lavori nel magazzino o nei reparti acquisti, vendite, produzione, gestione o si ricoprano altri ruoli, è possibile accedere ai dati sulle scorte disponibili in qualsiasi momento e ovunque. 

L'area di lavoro mobile offre un punto di vista immediato sullo stato delle scorte disponibili. Consente di visualizzare le scorte disponibili nelle strutture, le prenotazioni correnti di materiale e le scorte disponibili non prenotate. È inoltre possibile immettere i numeri di articolo per eseguire query sulle scorte disponibili ed eseguire una ricerca filtrata per i prodotti o le varianti disponibili. 

In particolare, l'area di lavoro mobile fornisce le seguenti funzionalità:

-   È possibile cercare per nome o numero di prodotto per individuare i prodotti per i quali visualizzare lo stato delle scorte disponibili.

-   Per i prodotti selezionati, è possibile visualizzare le seguenti informazioni:
    -   Scorte disponibili in base al sito
    -   Scorte disponibili in base al magazzino
    -   Scorte disponibili in base alla località
    -   Scorte disponibili per batch (per prodotti controllati in base ai batch)
    -   Scorte disponibili in base allo stato dell'inventario
    
-   Le scorte di prodotti disponibili vengono visualizzate nei seguenti modi:
    -   Per scorte fisiche (questa visualizzazione rappresenta l'importo totale).
    -   Per scorte prenotate (questa visualizzazione rappresenta l'importo prenotato).
    -   Per scorte fisiche disponibili (questa visualizzazione rappresenta la quantità disponibile senza prenotazioni).

## <a name="prerequisites"></a>Prerequisiti
Prima di utilizzare l'area di lavoro mobile **Scorte disponibili**, è necessario verificare che l'amministratore di sistema abbia predisposto i seguenti prerequisiti.

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
<td>Deve essere stato implementato Microsoft Dynamics 365 for Operations versione 1611 con aggiornamento alla piattaforma 3 o versione successiva.</td>
<td>Amministratore di sistema</td>
<td>Se Dynamics 365 for Operations non è ancora stato distribuito nell'organizzazione, l'amministratore di sistema deve vedere <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Distribuire un ambiente di dimostrazione di Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Deve essere stato implementato l'articolo KB 4013633.</td>
<td>Amministratore di sistema</td>
<td>KB 4013633 (un aggiornamento X++ o aggiornamento rapido dei metadati) contiene quattro aree di lavoro mobili per la gestione della supply chain. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li>Eseguire il download di KB 4013633 da Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a> al sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'area di lavoro mobile <strong>Scorte disponibili</strong> deve essere pubblicata nell'app mobile Dynamics 365 for Operations.</td>
<td>Amministratore di sistema</td>
<td><ol>
<li>Avviare Dynamics 365 for Operations nel browser.</li>
<li>Nella pagina <strong>Paramenti di sistema</strong> selezionare <strong>Gestisci aree di lavoro mobili</strong>.</li>
<li>Selezionare l'area di lavoro mobile <strong>Scorte disponibili</strong>.</li>
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

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>Visualizzare le scorte disponibile per un prodotto tramite l'area di lavoro mobile Scorte disponibili
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Scorte disponibili**.
2.  Selezionare **Verifica disponibilità per un articolo**. Viene visualizzato un elenco dei prodotti caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono consultare [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
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






