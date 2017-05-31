---
title: Area di lavoro mobile per immissione ora progetto per l&quot;app Microsoft Dynamics 365 for Operations
description: In questo argomento vengono fornite informazioni sull&quot;area di lavoro mobile per l&quot;immissione di ore progetto. Questa area di lavoro consente agli utenti di immettere e salvare le ore dedicate a un progetto utilizzando il dispositivo mobile.
author: annbe
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9c592c301908898915164e9236850759b73543fe
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Area di lavoro mobile per immissione ora progetto

[!include[banner](../includes/banner.md)]



In questo argomento vengono fornite informazioni sull'area di lavoro mobile per l'immissione di ore progetto per l'app mobile Dynamics 365 for Operations. Questa area di lavoro consente agli utenti di immettere e salvare le ore dedicate a un progetto utilizzando il dispositivo mobile.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>Panoramica dell'area di lavoro mobile per l'immissione di ore progetto
---------------------------------------------------

Durante il lavoro giornaliero, le risorse di progetto si trovano spesso sul campo o in viaggio. L'area di lavoro mobile **immissione ora progetto** consente agli utenti di immettere le relative ore fatturabili o non fatturabili a fronte di un progetto nel dispositivo mobile scelto. Di conseguenza, le risorse di progetto possono registrare voci ore in qualsiasi momento e ovunque. È inoltre possibile visualizzare le voci ore già registrate. 

In particolare, l'area di lavoro mobile per l'**immissione di ore progetto** consente di effettuare queste operazioni:

-   Per qualsiasi data selezionata, immettere il numero di ore impiegate in un'attività specifica.
-   Ricerca per nome o cliente del progetto per individuare il progetto per cui si desidera specificare l'orario.
-   Specificare la categoria e l'attività delle ore dedicate.
-   Registrare le ore come fatturabili o non fatturabili per il progetto.
-   Immettere qualsiasi commento interno o esterno facoltativo.

Per implementare l'area di lavoro mobile **immissione ora progetto**, vedere le sezioni riportate di seguito in questo argomento.

## <a name="prerequisites"></a>Prerequisiti
Prima di implementare l'area di lavoro mobile **Immissione ora progetto**, è necessario verificare che l'amministratore di sistema abbia soddisfatto i seguenti prerequisiti.

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
<td>Deve essere stato implementato l'articolo KB 4018050.</td>
<td>Amministratore di sistema</td>
<td>L'articolo KB 4018050 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Immissione ora progetto</strong>. Per implementare l'articolo KB 4018050, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li>Eseguire il download di KB 4018050 da Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Creare un pacchetto distribuibile</a> contenente i modelli <strong>ApplicationSuite</strong> e <strong>ProjectMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Applicare il pacchetto distribuibile</a> al sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'area di lavoro mobile <strong>Immissione ora progetto</strong> deve essere pubblicata nell'app mobile Dynamics 365 for Operations.</td>
<td>Amministratore di sistema</td>
<td><ol>
<li>Avviare Dynamics 365 for Operations nel browser.</li>
<li>Nella pagina <strong>Paramenti di sistema</strong> nella scheda <strong>Gestisci aree di lavoro mobili</strong> selezionare l'area di lavoro <strong>Immissione ora progetto</strong>.</li>
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

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Immettere l'ora utilizzando l'area di lavoro mobile per immissione ora progetto
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Immissione ora progetto**.
2.  Selezionare **Immissione ora**. Vengono visualizzate le date di calendario per la settimana corrente.
3.  Per una data selezionata, selezionare &gt; **Azioni**. **Nuova voce**.
4.  Immettere il numero di ore da registrare.
5.  Selezionare il progetto per la voce ora. Viene visualizzato un elenco dei progetti caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono consultare [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Se il progetto non è presente nell'elenco, selezionare **Cerca** per effettuare una ricerca online in Dynamics 365 for Operations. Ricercare per nome o selezionare la ricerca per nome progetto o cliente.
7.  Consente di selezionare una categoria. Viene visualizzato un elenco delle categorie caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono consultare [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Se la categoria non è presente nell'elenco, selezionare **Cerca** per effettuare una ricerca online in Dynamics 365 for Operations. Ricerca in base alla categoria o ricerca per nome categoria.
9.  Selezionare un'attività. Viene visualizzato un elenco delle attività caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono consultare [Piattaforma mobile di Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Se l'attività non è presente nell'elenco, selezionare **Cerca** per effettuare una ricerca online in Dynamics 365 for Operations. Ricerca in base al numero dell'attività o ricerca per scopo.
11. Selezionare la proprietà riga.
12. Facoltativo: immettere qualsiasi commento interno o esterno.
13. Selezionare **Fine**.






