---
title: Area di lavoro mobile per scorte disponibili
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Scorte disponibili. Questa area di lavoro mobile consente di ottenere informazioni su dispositivo mobile relative alle scorte disponibili e prenotate in qualsiasi momento e ovunque.
author: yufeihuang
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yufeihuang
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9e67e16acc8ed72d571e9010131723038c8586a9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573899"
---
# <a name="inventory-on-hand-mobile-workspace"></a>Area di lavoro mobile per scorte disponibili

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Scorte disponibili**. Questa area di lavoro consente di ottenere informazioni su dispositivo mobile relative alle scorte disponibili e prenotate in qualsiasi momento e ovunque.

Questa area di lavoro mobile può essere utilizzata con l'app Finance and Operations per dispositivi mobili.

## <a name="overview"></a>Panoramica
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
I prerequisiti variano in base alla versione di Supply Chain Management che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Prerequisiti si utilizza Supply Chain Management
Se Supply Chain Management è stato distribuito nell'organizzazione, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Scorte disponibili**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>Prerequisiti per l'utilizzo dell'Aggiornamento piattaforma 3 o versione successiva 
Se nell'organizzazione è stato distribuito l'Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti. 

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

<td>l'articoloo KB 4013633 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Scorte disponibili</strong>. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Scorte disponibili</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili

Scaricare e installare l'app Finance and Operations per dispositivi mobili:

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile

1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Dynamics 365.
3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

    [![Trascinare verso il basso.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Visualizzare le scorte disponibili per un prodotto tramite l'area di lavoro mobile Scorte disponibili

1.  Sul dispositivo mobile, selezionare l'area di lavoro **Scorte disponibili**.

2.  Selezionare **Verifica disponibilità per un articolo**. Viene visualizzato un elenco dei prodotti caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
3.  Se l'articoloo non è in elenco, selezionare **Cerca altro**. Cercare per numero di prodotto o passare a una ricerca per nome di prodotto.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]