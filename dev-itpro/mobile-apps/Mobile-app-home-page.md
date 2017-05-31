---
title: Home page dell&quot;app mobile Microsoft Dynamics 365 for Operations
description: In questo argomento viene descritta l&quot;app mobile Microsoft Dynamics 365 for Operations e vengono forniti i collegamenti alle risorse necessarie per implementarla dell&quot;organizzazione.
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5962fa36b061382e7f0ad55c08c81ac2cebc047d
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Home page dell'app mobile Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


In questo argomento viene descritta l'app mobile Microsoft Dynamics 365 for Operations e vengono forniti i collegamenti alle risorse necessarie per implementarla dell'organizzazione.

<a name="overview"></a>Panoramica
--------

L'app mobile Microsoft Dynamics 365 for Operations consente all'organizzazione di rendere disponibili i propri processi aziendali nei dispositivi mobili. Dopo che l'amministratore IT attiva la funzionalità mobile delle aree di lavoro per l'organizzazione, gli utenti potranno accedere all'app e immediatamente iniziare a eseguire i processi aziendali dai dispositivi mobili. L'app mobile Microsoft Dynamics 365 for Operations include le seguenti funzionalità che consentono di aumentare la produttività:

-   Gli utenti possono visualizzare, modificare ed eseguire azioni sui dati business, anche se invece dispongono di connettività di rete intermittente o se i dispositivi mobili sono completamente offline. Se un dispositivo ristabilisce una connessione di rete, le operazioni dati offline vengono sincronizzate automaticamente con Dynamics 365 for Operations.
-   Gli amministratori IT o gli sviluppatori possono creare e pubblicare aree di lavoro mobili che sono state personalizzate per l'organizzazione. L'app utilizza le risorse di codice esistenti. Di conseguenza, non è necessario implementare di nuovo le procedure di convalida, la regola business o la configurazione di protezione.
-   Gli amministratori IT o gli sviluppatori possono progettare facilmente le aree di lavoro mediante la progettazione rapida per area di lavoro inclusa in nel client Web di Dynamics 365 for Operations.
-   Gli amministratori IT o gli sviluppatori possono facoltativamente ottimizzare le capacità offline delle aree di lavoro utilizzando il framework dell'estensibilità della regola business. Poiché i dati continuano a essere elaborati offline anche mentre il dispositivo è offline, gli scenari mobili rimangono ricchi e fluidi anche se i dispositivi non hanno connettività di rete costante.

## <a name="elements-of-the-mobile-app"></a>Elementi dell'app mobile
La navigazione dell'app mobile è costituita si basa su quattro concetti semplici: dashboard, aree di lavoro, pagine e azioni. 

[![Concetti di navigazione nell'app mobile](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   All'avvio dell'app, passare al **dashboard**.
-   Nel dashboard, è possibile visualizzare un elenco di **aree di lavoro** che verrà visualizzato nell'ambiente di Dynamics 365 for Operations.
-   In ciascuna area di lavoro, è possibile visualizzare un elenco **pagine** disponibile per tale area di lavoro.
-   In una pagina, è possibile visualizzare i dati raccolti da una o più pagine di Dynamics 365 for Operations.
-   In una pagina, è possibile accedere ad altre pagine per i dati correlati, ad esempio i dettagli di entità oppure le righe.
-   In una pagina, è inoltre possibile visualizzare un elenco di **azioni** disponibile per tale pagina.
-   Le azioni consentono di creare o modificare i dati esistenti.

## <a name="implementation-process"></a>Processo di implementazione
Nella figura seguente è illustrato il processo di implementazione nell'organizzazione per l'app mobile Microsoft Dynamics 365 for Operations. 

![Processo di implementazione app mobili](./media/mobile-implementation-process_4.png)

Nella tabella riportata di seguito vengono forniti i collegamenti per agevolare l'implementazione dell'app mobile Microsoft Dynamics 365 for Operations nell'organizzazione. I numeri nella prima colonna corrispondono ai passaggi numerati nella precedente figura.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Graduale</th>
<th>Ruolo</th>
<th>Azione</th>
<th>Risorse che consentono di completare l'azione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Amministratore di sistema</td>
<td>Implementare Dynamics 365 for Operations per l'organizzazione.</td>
<td>Se Dynamics 365 for Operations non è ancora stato distribuito nell'organizzazione, vedere <a href="../deployment/deploy-demo-environment.md">Distribuire un ambiente di dimostrazione di Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Amministratore di sistema</td>
<td>Scaricare e installare gli articoli KB che abilitano le aree di lavoro mobili fornite da Microsoft.</td>
<td>Vedere la sezione &quot;prerequisiti&quot; dell'argomento relativo all'area di lavoro mobile di interesse per l'organizzazione:
<ul>
<li><a href="/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Aree di lavoro mobili di controllo costi</a></li>
<li><a href="/dynamics365/operations/supply-chain/inventory/inventory-on-hand-mobile-workspace">Area di lavoro mobile per scorte disponibili</a></li>
<li><a href="/dynamics365/operations/supply-chain/sales-marketing/sales-orders-mobile-workspace">Aree di lavoro mobili per ordini cliente</a></li>
<li><a href="/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Area di lavoro mobile di collaborazione fornitore</a></li>
<li><a href="/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Area di lavoro mobile per immissione ora progetto</a></li>
<li><a href="/dynamics365/operations/financials/expense-management/expense-management-mobile-workspace">Area di lavoro mobile di gestione spese</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Amministratore di sistema</td>
<td>Pubblicare le aree di lavoro mobili fornite da Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Sviluppatore o fornitore di software indipendente (ISV)</td>
<td>Utilizzare il framework mobile di Dynamics 365 for Operations per creare le aree di lavoro mobili personalizzate.</td>
<td><ul>
<li><a href="mobile-platform.md">Framework mobile di Dynamics 365 for Operations</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">API dell'area di lavoro X++ di Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Creare un pacchetto distribuibile contenente le aree di lavoro mobili personalizzate e caricare il pacchetto in Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Amministratore di sistema</td>
<td>Applicare il pacchetto distribuibile contenente le aree di lavoro personalizzate che vengono fornite dall'ISV.</td>
<td><a href="../deployment/apply-deployable-package-system.md">Applicare un pacchetto distribuibile in un sistema Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Amministratore di sistema</td>
<td>Pubblicare le aree di lavoro mobili personalizzate fornite dall'ISV.</td>
<td><a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Utente</td>
<td>Scaricare e installare l'app mobile Microsoft Dynamics 365 for Operations.</td>
<td><ul>
<li>Per Android: <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations in Google Play Store</a></li>
<li>Per iPhone: <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 for Operations nell'app store iTunes</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Utente</td>
<td>Accedere e utilizzare l'app mobile Microsoft Dynamics 365 for Operations. L'app include le aree di lavoro mobili pubblicate.</td>
<td>Per visualizzare un elenco di aree di lavoro mobili fornite da Microsoft, vedere <a href="mobile-workspaces-released.md">Aree di lavoro mobili rilasciate di recente per l'app mobile Dynamics 365 for Operations</a>
</td>
</tr>
</tbody>
</table>






