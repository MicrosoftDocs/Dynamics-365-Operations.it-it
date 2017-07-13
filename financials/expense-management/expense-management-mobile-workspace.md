---
title: Area di lavoro mobile di gestione spese
description: In questo argomento vengono fornite informazioni sull&quot;area di lavoro mobile di gestione spese, disponibile per l&quot;app mobile Microsoft Dynamics 365 for Finance and Operations. Questa area di lavoro consente agli utenti di acquisire e caricare una ricevuta, in modo che possono successivamente collegarla a una nota spese. L&quot;area di lavoro mobile consente inoltre agli utenti di creare rapidamente una riga di spesa utilizzando una ricevuta collegata.
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0e52d1c5dde7f79c4a8ac5ac2d9c3b25bba9c2cd
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017


---

# <a name="expense-management-mobile-workspace"></a>Area di lavoro mobile di gestione spese

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'area di lavoro mobile di gestione spese, disponibile per l'app mobile Microsoft Dynamics 365 for Finance and Operations. Questa area di lavoro consente agli utenti di acquisire e caricare una ricevuta, in modo che possono successivamente collegarla a una nota spese. L'area di lavoro mobile consente inoltre agli utenti di creare rapidamente una riga di spesa utilizzando una ricevuta collegata.

<a name="overview-of-the-expense-management-mobile-workspace"></a>Panoramica dell'area di lavoro mobile di gestione spese
---------------------------------------------------

In molte organizzazioni è necessario che una copia della ricevuta venga allegata a un report spese correlato al business che un dipendente inoltra per il rimborso. L'area di lavoro mobile **Gestione spese** consente agli utenti di creare rapidamente nuove righe di spesa nel dispositivo mobile preferito utilizzando una foto allegata di una ricevuta. In alternativa, è possibile acquisire una foto di una ricevuta e quindi successivamente allegarla a una nota spese. In particolare, l'area di lavoro mobile **Gestione spese** consente a un utente di effettuare queste operazioni:

-   Prendere una foto di ricevuta e caricarla in Microsoft Dynamics 365 for Finance and Operations. Un utente può quindi allegare la foto a una note spese in un secondo momento.
-   Caricare un file come ricevuta acquisita. Un utente può quindi allegare il file a una note spese in un secondo momento.
-   Creare una nuova riga di spesa utilizzando una ricevuta collegata. Un utente può quindi aggiungere la voce a una nota spese successivamente e inviarla per l'approvazione e rimborso.

Nelle altre aree di questo argomento viene descritto come implementare e utilizzare l'area di lavoro mobile **Gestione spese**.

## <a name="prerequisites"></a>Prerequisiti
Prima di implementare l'area di lavoro mobile **Gestione spese**, è necessario verificare che l'amministratore di sistema abbia soddisfatto i seguenti prerequisiti.

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
<td>Se Finance and Operations non è ancora stato distribuito nell'organizzazione, l'amministratore di sistema deve vedere <a href="/dynamics365/unified-operations/dev-itpro/deployment/deploy-demo-environment">Distribuire un ambiente di dimostrazione di Microsoft Dynamics 365 for Finance and Operations</a>.</td>
</tr>
<tr class="even">
<td>Deve essere stato implementato l'articolo KB 4019015.</td>
<td>Amministratore di sistema</td>
<td>KB 4019015 (un aggiornamento X++ o aggiornamento rapido dei metadati) contiene quattro aree di lavoro mobili per la gestione della supply chain. Per implementare l'articolo KB 4019015, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li>Eseguire il download di KB 4019015 da Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente il modello <strong>ApplicationSuite</strong> e <strong>ExpenseMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a> al sistema Finance and Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'area di lavoro mobile <strong>Gestione spese</strong> deve essere pubblicata nell'app mobile Finance and Operations.</td>
<td>Amministratore di sistema</td>
<td><ol>
<li>Avvia Finance and Operations nel browser.</li>
<li>Nella pagina <strong>Paramenti di sistema</strong> selezionare <strong>Gestisci aree di lavoro mobili</strong>.</li>
<li>Selezionare l'area di lavoro mobile <strong>Gestione spese</strong>.</li>
<li>Fare clic su <strong>Pubblica area di lavoro mobile</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-finance-and-operations-mobile-app"></a>Scaricare e installare l'app mobile Finance and Operations
Scaricare e installare l'app mobile Finance and Operations dall'App Store mobile.

-   Per Android: [Finance and Operations su Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Per iPhone: [Finance and Operations nell'app store iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-finance-and-operations-mobile-app"></a>Accedere all'app mobile Finance and Operations
1.  Avviare l'app sul dispositivo mobile.
2.  Immettere l'URL di Finance and Operations.
3.  Immettere la società a cui accedere. Ad esempio, immettere **USMF**.
4.  La prima volta che si accede, verrà richiesto di specificare il nome utente e la password per l'account Finance and Operations. Immettere le proprie credenziali.
5.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è possibile effettuare il pull per aggiornare l'elenco delle aree di lavoro mobili. 

[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Acquisire una ricevuta tramite l'area di lavoro mobile di Gestione spese
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Gestione spese**.
2.  Selezionare **Acquisisci ricevuta**.
3.  Selezionare **Scatta foto** o **Scegli immagine**.
4.  Se selezionata l'opzione **Scatta foto**, effettuare le seguenti operazioni:
    1.  Viene aperta la macchina fotografica sul dispositivo mobile, in modo che sia possibile scattare una foto della ricevuta. Al termine, fare clic su **OK** per accettare la foto.
    2.  Facoltativo: immettere un nome per la foto ed eventuali note.

     **Oppure:** se si seleziona l'opzione **Scegli immagine**, effettuare le seguenti operazioni:
    1.  Selezionare un'immagine nell'elenco.
    2.  Facoltativo: immettere un nome per l'immagine ed eventuali note.

5.  Selezionare **Fine**.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>Immissione rapida delle spese tramite l'area di lavoro mobile di Gestione spese
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Gestione spese**.
2.  Selezionare **Immissione rapida spese**.
3.  Selezionare la categoria di spesa per la spesa. Viene visualizzato un elenco delle categorie di spesa caricate nell'app per l'utilizzo offline. Per impostazione predefinita, viene caricato un massimo 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono consultare [Piattaforma mobile di Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). Se la categoria non è presente nell'elenco, selezionare **Cerca** per effettuare una ricerca online in Finance and Operations. Ricercare per categoria di spesa o selezionare la ricerca per tipo di spesa.
4.  Immettere la data della transazione per la spesa.
5.  Facoltativo: registrare l'esercente per la spesa.
6.  Consente di immettere l'importo della spesa.
7.  Consente di selezionare la valuta della spesa. Viene visualizzato un elenco dei codici valuta caricati nell'app per l'utilizzo offline. Per impostazione predefinita, viene caricato un massimo 400 valute, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono consultare [Piattaforma mobile di Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). Se la valuta non è presente nell'elenco, selezionare **Cerca** per effettuare una ricerca online in Finance and Operations. Ricerca in base alla valuta o ricerca per nome.
8.  Selezionare **Scatta foto** o **Scegli immagine**.
9.  Se si è selezionato **Scatta foto**, viene aperta la macchina fotografica sul dispositivo mobile, in modo che sia possibile scattare una foto della ricevuta. Al termine, fare clic su **OK** per accettare la foto.  oppure Se viene selezionata **Scegli immagine**, selezionare un'immagine nell'elenco.
10. Selezionare **Fine**.






