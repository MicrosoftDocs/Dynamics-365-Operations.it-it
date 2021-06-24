---
title: Home page app per dispositivi mobili
description: In questo argomento viene descritta l'app per dispositivi mobili Finance and Operations (Dynamics 365) e vengono forniti i collegamenti alle risorse necessarie per implementarla nell'organizzazione.
author: ChrisGarty
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 469b03151f3113f44d932a2d6f4bf3fcfa059133
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188412"
---
# <a name="mobile-app-home-page"></a>Home page app per dispositivi mobili

[!include [banner](../includes/banner.md)]

In questo argomento viene descritta l'app per dispositivi mobili **Finance and Operations (Dynamics 365)** e vengono forniti i collegamenti alle risorse necessarie per implementarla nell'organizzazione.

## <a name="overview"></a>Panoramica

L'app mobile consente all'organizzazione di rendere disponibili i propri processi aziendali nei dispositivi mobili. Dopo che l'amministratore IT attiva le aree di lavoro mobile per l'organizzazione, gli utenti potranno accedere all'app e immediatamente iniziare a eseguire i processi aziendali dai dispositivi mobili. L'app mobile include le seguenti funzionalità che consentono di aumentare la produttività:

- Gli utenti possono visualizzare, modificare ed eseguire azioni sui dati business, anche se invece dispongono di connettività di rete intermittente o se i dispositivi mobili sono completamente offline. Se un dispositivo ristabilisce una connessione di rete, le operazioni dati offline vengono sincronizzate automaticamente.
- Gli amministratori IT o gli sviluppatori possono creare e pubblicare aree di lavoro mobili che sono state personalizzate per l'organizzazione. L'app utilizza le risorse di codice esistenti. Di conseguenza, non è necessario implementare di nuovo le procedure di convalida, la regola business o la configurazione di protezione.
- Gli amministratori IT o gli sviluppatori possono progettare facilmente le aree di lavoro mediante la progettazione rapida per area di lavoro inclusa in nel client Web.
- Gli amministratori IT o gli sviluppatori possono facoltativamente ottimizzare le capacità offline delle aree di lavoro utilizzando il framework dell'estensibilità della regola business. Poiché i dati continuano a essere elaborati offline anche mentre il dispositivo è offline, gli scenari mobili rimangono ricchi e fluidi anche se i dispositivi non hanno connettività di rete costante.

## <a name="elements-of-the-mobile-app"></a>Elementi dell'app mobile
La navigazione dell'app mobile è costituita si basa su quattro concetti di base: dashboard, aree di lavoro, pagine e azioni. 

[![Concetti di navigazione nell'app mobile](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. All'avvio dell'app, passare al **dashboard**.
2. Nel dashboard, è possibile visualizzare un elenco di **aree di lavoro** pubblicate.
3. In ciascuna area di lavoro, è possibile visualizzare un elenco **pagine** disponibile per tale area di lavoro.
4. Una volta posizionati su una pagina, è possibile eseguire più azioni. Di seguito sono riportati alcuni esempi.

    - Visualizzare dati dettagliati.
    - Accedere ad altre pagine per i dati correlati, ad esempio i dettagli di entità oppure le righe.
    - Visualizzare un elenco di **azioni** disponibile per tale pagina. Le azioni consentono di creare o modificare i dati esistenti.

## <a name="implementation-process"></a>Processo di implementazione
Nella figura seguente è illustrato il processo per implementare entrambe le aree di lavoro mobili fornite da Microsoft e le aree di lavoro mobili personalizzate. 

[![Processo di implementazione app mobili](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

Nella seguente tabella sono inclusi collegamenti alle risorse necessarie per implementare entrambe le aree di lavoro mobili fornite da Microsoft e le aree di lavoro mobili personalizzate. I numeri nella prima colonna corrispondono ai passaggi numerati nella precedente figura.

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
<td>Implementare l'app Finance and Operations nell'organizzazione.</td>
<td><ul><li>Se non è stata distribuita una versione di Microsoft Dynamics 365, vedere <a href="../deployment/deploy-demo-environment.md">Distribuire un ambiente di dimostrazione</a>.</li><li>Per visualizzare un elenco di aree di lavoro mobili da utilizzare, vedere <a href="mobile-workspaces-released.md">Aree di lavoro mobili rilasciate di recente</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Amministratore di sistema</td>
<td><strong>Se si utilizza Microsoft Dynamics 365 for Operations versione 1611:</strong> Scaricare e installare gli articoli KB che abilitano le aree di lavoro mobili fornite da Microsoft.</td>
<td>Per ulteriori informazioni, vedere i seguenti argomenti:
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Aree di lavoro mobili di controllo costi</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Area di lavoro mobile per scorte disponibili</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Aree di lavoro mobili per ordini cliente</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Area di lavoro mobile di collaborazione fornitore</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">Area di lavoro mobile per immissione ora progetto</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">Area di lavoro mobile di gestione spese</a></li>

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
<td>Utilizzare la piattaforma mobile per creare aree di lavoro mobili personalizzate.</td>
<td><a href="platform/mobile-platform-home-page.md">Piattaforma mobile</a></td>
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
<td><a href="../deployment/apply-deployable-package-system.md">Applicare un pacchetto distribuibile</a></td>
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
<td>Scaricare e installare l'app mobile.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">App Finance and Operations per Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">App Finance and Operations per iOS</a><BR/>
(Windows Phone non supportato)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Utente</td>
<td>Accedere all'app mobile ed utilizzarla. L'app include le aree di lavoro mobili pubblicate dall'amministratore di sistema.</td>
<td>Per visualizzare un elenco di aree di lavoro mobili fornite da Microsoft, vedere <a href="mobile-workspaces-released.md">Aree di lavoro mobili rilasciate di recente</a>.
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>Risoluzione dei problemi
[Risorse piattaforma mobile](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]