---
title: Area di lavoro mobile per immissione ora progetto
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile per l'immissione di ore progetto. Questa area di lavoro consente agli utenti di immettere e salvare le ore dedicate a un progetto utilizzando il dispositivo mobile.
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9bf79af6eea6f899158fc3c8d523587cb11c90ad
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="project-time-entry-mobile-workspace"></a>Area di lavoro mobile per immissione ora progetto

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Immissione ora progetto**. Questa area di lavoro consente agli utenti di immettere e salvare le ore dedicate a un progetto utilizzando il dispositivo mobile.

Questa area di lavoro mobile può essere utilizzata con l'app mobile Microsoft Dynamics 365 for Unified Operations. 

## <a name="overview"></a>Panoramica
Durante il lavoro giornaliero, le risorse di progetto si trovano spesso sul campo o in viaggio. L'area di lavoro mobile **immissione ora progetto** consente agli utenti di immettere le relative ore fatturabili o non fatturabili a fronte di un progetto nel dispositivo mobile scelto. Di conseguenza, le risorse di progetto possono registrare voci ore in qualsiasi momento e ovunque. È inoltre possibile visualizzare le voci ore già registrate. 

In particolare, nell'area di lavoro mobile **Immissione ora progetto**, gli utenti possono eseguire queste attività:

-   Per qualsiasi data selezionata, immettere il numero di ore impiegate in un'attività specifica.
-   Ricerca per nome o cliente del progetto per individuare il progetto per cui si desidera specificare l'orario.
-   Specificare la categoria e l'attività delle ore dedicate.
-   Registrare le ore come fatturabili o non fatturabili per il progetto.
-   Immettere qualsiasi commento interno o esterno facoltativo.

## <a name="prerequisites"></a>Prerequisiti
I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Prerequisiti per l'utilizzo di Microsoft Dynamics 365 for Finance and Operations
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Finance and Operations, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Immissione ora progetto**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti. 

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td>Implementare l'articoloo KB 4018050.</td>
<td>Amministratore di sistema</td>
<td>L'articolo KB 4018050 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Immissione ora progetto</strong>. Per implementare l'articolo KB 4018050, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente i modelli <strong>ApplicationSuite</strong> e <strong>ProjectMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Immissione ora progetto</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app mobile

Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile
1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Dynamics 365.
3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
4.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Immettere l'ora utilizzando l'area di lavoro mobile per immissione ora progetto
1.  Sul dispositivo mobile, selezionare l'area di lavoro **Immissione ora progetto**.
2.  Selezionare **Immissione ora**. Vengono visualizzate le date di calendario per la settimana corrente.
3.  Per una data selezionata, selezionare &gt; **Azioni**. **Nuova voce**.
4.  Immettere il numero di ore da registrare.
5.  Selezionare il progetto per la voce ora. Viene visualizzato un elenco dei progetti caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, vedere [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
6.  Se il progetto non è in elenco, selezionare **Cerca altro**. Ricercare per nome o selezionare la ricerca per nome progetto o cliente.
7.  Consente di selezionare una categoria. Viene visualizzato un elenco delle categorie caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, vedere [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
8.  Se la categoria non è in elenco, selezionare **Cerca altro**. Ricerca in base alla categoria o ricerca per nome categoria.
9.  Selezionare un'attività. Viene visualizzato un elenco delle attività caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, vedere [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
10. Se l'attività non è in elenco, selezionare **Cerca altro**. Ricerca in base al numero dell'attività o ricerca per scopo.

11. Selezionare la proprietà riga.
12. Facoltativo: immettere qualsiasi commento interno o esterno.
13. Selezionare **Fine**.

