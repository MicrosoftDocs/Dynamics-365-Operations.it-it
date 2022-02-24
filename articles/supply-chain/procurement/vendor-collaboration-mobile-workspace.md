---
title: Area di lavoro mobile di collaborazione fornitore
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Collaborazione fornitore. Questa area di lavoro consente ai fornitori di restare aggiornati sugli ordini fornitore che sono stati inviati loro per l'approvazione. Possono inoltre visualizzare informazioni su ordini fornitore e contatti nuovi e aggiornati.
author: RichardLuan
manager: tfehr
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: riluan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 5cd8a2b2db7147aca6bdc29ba15d99a619ddb4f8
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020838"
---
# <a name="vendor-collaboration-mobile-workspace"></a>Area di lavoro mobile di collaborazione fornitore

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Collaborazione fornitore**. Questa area di lavoro consente ai fornitori di restare aggiornati sugli ordini fornitore che sono stati inviati loro per l'approvazione. Possono inoltre visualizzare informazioni su ordini fornitore e contatti nuovi e aggiornati.

Questa area di lavoro mobile può essere utilizzata con l'app Finance and Operations per dispositivi mobili.

## <a name="overview"></a>Panoramica 
L'area di lavoro mobile **Collaborazione fornitore** mantiene i fornitori aggiornati sui nuovi ordini fornitore e consente loro di visualizzare gli ordini e quindi di rispondere tramite il client Web. 

>[!NOTE]
> L'area di lavoro mobile dovrebbe essere utilizzata come supplemento all'interfaccia Web per la collaborazione fornitore, non come una sostituzione. 

I fornitori possono utilizzare l'area di lavoro mobile **Collaborazione fornitore** per visualizzare i nuovi ordini fornitore che ricevono per l'approvazione. Vengono visualizzate le informazioni relative agli ordini fornitore, ad esempio prodotti, quantità e date di consegna richieste. Anche le informazioni sul prezzo sono disponibili, a seconda della configurazione di ciascun fornitore. 

Quando un utente accede come fornitore, vede a quali ordini fornitore è stato risposto e quali sono ancora in attesa dell'azione del cliente. Ad esempio, un ordine fornitore potrebbe essere in attesa di un'azione del cliente perché il fornitore ha suggerito un'altra data di consegna ma il cliente non ha ancora confermato la data. Il fornitore visualizza anche un elenco di ordini fornitore confermati, ma non ancora spediti. 

Per rispondere a un ordine fornitore, il fornitore deve utilizzare l'interfaccia Web per la collaborazione fornitore disponibile nel client Web. Inoltre qui il fornitore ottiene ulteriori informazioni sull'ordine, ad esempio gli allegati del documento, l'indirizzo di consegna per riga e le spese associate al fornitore. 

I fornitori che hanno un ruolo di sicurezza speciale possono vedere quali contatti sono registrati per un conto fornitore. Con lo stesso ruolo di sicurezza, il fornitore può vedere lo stato di qualsiasi richiesta utente inviata. 

L'interfaccia Web per la collaborazione fornitore nel client Web deve essere utilizzata per creare nuovi contatti e inviare nuove richieste utente. 

L'area di lavoro mobile **Collaborazione fornitore** consente a un fornitore di eseguire queste attività:

-   Visualizzare nuovi ordini fornitore inviati al fornitore.
-   Visualizzare gli ordini fornitore ai quali il fornitore ha risposto e che sono in attesa dell'azione del cliente.
-   Visualizzare gli ordini fornitore che sono stati confermati, ma non ancora completamente ricevuti.
-   Visualizzare le informazioni sui contatti registrati per il conto fornitore. Questa attività richiede un ruolo di sicurezza aggiuntivo.
-   Visualizzare le informazioni su una richiesta di utente che è stata inoltrata dal fornitore e seguire lo stato della richiesta. Questa attività richiede un ruolo di sicurezza aggiuntivo.

## <a name="prerequisites"></a>Prerequisiti
I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Prerequisiti si utilizza Supply Chain Management
Se Supply Chain Management è stato distribuito nell'organizzazione, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Collaborazione fornitore**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

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
<td>Se si utilizza l'aggiornamento 3 della piattaforma è necessario implementare KB 3216943.</td>
<td>Amministratore di sistema</td>
<td>KB 3216943 è un aggiornamento binario necessario se si utilizza l'aggiornamento 3 della piattaforma. Per implementare questo KB, l'amministratore di sistema deve completare i passaggi seguenti.
<ol>
<li>Eseguire il download di KB 3216943 da Microsoft Dynamics Lifecycle Services (LCS).</li>
<li>Installare l'aggiornamento binario, che viene fornito come pacchetto distribuibile. Per informazioni su come applicare un pacchetto distribuibile, vedere <a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare un pacchetto distribuibile</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Deve essere stato implementato l'articolo KB 4013633.</td>
<td>Amministratore di sistema</td>
<td>l'articoloo KB 4013633 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Scorte disponibili</strong>. Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da LCS</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</li><li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>L'area di lavoro mobile <strong>Collaborazione fornitore</strong> deve essere pubblicata.</td><td>Amministratore di sistema</td>
<td>Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
<tr class="even">
<td>L'utente fornitore deve avere accesso all'interfaccia Web per la collaborazione fornitore nel client Web e deve impostare un utente di collaborazione fornitore.</td><td>Professionisti degli acquisti e amministratore di sistema</td>
<td>Completare i passaggi descritti negli argomenti seguenti per impostare e utilizzare l'interfaccia Web per la collaborazione fornitore.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Utilizzare la collaborazione fornitore per gestire i fornitori esterni</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gestire gli utenti di collaborazione fornitore</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Impostare e gestire la collaborazione fornitore</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Utilizzare la collaborazione fornitore per gestire i clienti in Supply Chain Managements</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili

Scaricare e installare l'app Finance and Operations per dispositivi mobili:

-   [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile
1.  Avviare l'app sul dispositivo mobile.
2.  Immettere il proprio URL Microsoft Dynamics 365.
4.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
5.  Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.

    [![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="use-the-vendor-collaboration-mobile-workspace"></a>Utilizzare l'area di lavoro mobile Collaborazione fornitore
Quando si seleziona l'area di lavoro **Collaborazione fornitore** sono disponibili le seguenti opzioni.

![Area di lavoro mobile di collaborazione fornitore](./media/vendor-collaboration-mobile-app.png)

L'area di lavoro **Collaborazione fornitore** include le seguenti pagine.

### <a name="contacts"></a>Contatti
La pagina **Contatti** consente di visualizzare tutti i contatti impostati per il conto fornitore. Visualizza il nome del contatto, l'indirizzo di posta elettronica principale e l'alias dell'utente, se il contatto ha un alias. Questa pagina mostra inoltre se l'account utente del contatto è attivo. Quando si seleziona un contatto, diventano visibili i dettagli del contatto, ad esempio le persone giuridiche per le quali la persona funge da contatto. Se vengono inoltre visualizzate le informazioni sul contatto, ad esempio un numero di telefono o un indirizzo di posta elettronica alternativo.

### <a name="user-requests"></a>Richieste utente
La pagina **Richieste utente** consente di visualizzare tutte le richieste utente inviate tramite l'interfaccia Web per la collaborazione fornitore. È inoltre possibile monitorare lo stato di tali richieste. Quando si seleziona una richiesta utente, è possibile verificare quanto è stato ordinato, aggiungere o disattivare un utente, cambiare la sicurezza e visualizzare i ruoli di sicurezza che sono stati ordinati per l'utente.

### <a name="purchase-orders-ready-for-review"></a>Ordini fornitore pronti per la revisione
La pagina **Ordini fornitore pronti per la revisione** consente di visualizzare tutti gli ordini fornitore che sono stati inviati dal cliente, ma a cui non è stata ancora data risposta. È possibile visualizzare alcune informazioni relative all'ordine, ad esempio quali prodotti sono stati ordinati e quando dovrebbero essere consegnati. Anche le informazioni sul prezzo sono disponibili, a seconda della configurazione del fornitore.

È inoltre possibile verificare se l'ordine fornitore include note o allegati. Tuttavia, per aprire le note e gli allegati, è necessario utilizzare l'interfaccia Web per la collaborazione fornitore nel client Web. Selezionare **Riga ordine fornitore** per visualizzare tutte le righe insieme ai relativi dettagli. Per ogni riga verrà visualizzato un indicatore che mostrerà se sono presenti note o allegati o se è presente un indirizzo di consegna diverso rispetto a quello riportato nell'intestazione.

Per rispondere all'ordine fornitore, è necessario utilizzare l'interfaccia Web per la collaborazione fornitore nel client Web.

### <a name="awaiting-customer-action"></a>In attesa dell'azione del cliente
La pagina **In attesa dell'azione del cliente** consente di individuare gli ordini fornitore a cui qualcuno della società che ha anche accesso alla collaborazione fornitore ha risposto. Gli ordini fornitore sono visibili solo in questo elenco se il cliente deve eseguire una delle seguenti azioni nell'ordine fornitore.

-   Se l'ordine fornitore è stato rifiutato, il cliente deve aggiornare l'ordine originale o annullarlo e rinviarlo. Quando l'ordine fornitore viene inviato di nuovo, non viene più visualizzato nella pagina **In attesa dell'azione del cliente**.
-   Se l'ordine fornitore è stato accettato con le modifiche, il cliente deve aggiornare l'ordine originale e rinviarlo per la revisione oppure aggiornarlo in base alle modifiche richieste e confermarlo immediatamente. In entrambi i casi l'ordine fornitore non viene più visualizzato nella pagina **In attesa dell'azione del cliente**.
-   Se l'ordine fornitore è stato accettato e appare ancora nella pagina **In attesa dell'azione del cliente**, significa che l'ordine fornitore non è stato confermato automaticamente quando è stato accettato. L'ordine è quindi in attesa che l'agente di acquisto ne imposto lo stato su **Confermato**. In genere, un ordine fornitore viene considerato come un contratto stipulato tra il cliente e il fornitore non appena il fornitore accetta l'ordine. L'aggiornamento allo stato a **Confermato** è in genere una pura formalità.

Quando si seleziona un ordine fornitore, vengono visualizzati dettagli aggiuntivi sulla risposta. È possibile visualizzare i dettagli riga e la risposta per ogni riga. Lo stato della riga indica quale delle seguenti risposte sono state date.

-   Accettato
-   Rifiutato
-   Accettata con modifiche
-   Sostituita/Sostituire
-   Suddivisa in programmazione/Riga programmazione

Si noti che il campo **Consegna** è impostato su **Sì** o su **No** per indicare se le righe verranno consegnate. Una riga non può essere consegnata per i seguenti motivi:

- La riga è stata rifiutata.
- È stata effettuata una sostituzione e la riga originale non può essere consegnata come richiesto nell'ordine ricevuto.
- La riga è stata suddivisa in più righe di programmazione e la riga originale non può essere consegnata come richiesto nell'ordine ricevuto.

Tutte le modifiche apportate alla risposta della riga ordine sono visualizzate. Tuttavia, le note e gli allegati caricati non vengono visualizzati. Per visualizzare le note e gli allegati, è necessario utilizzare l'interfaccia Web per la collaborazione fornitore nel client Web.

### <a name="open-confirmed-orders"></a>Ordini confermati aperti
Quando l'ordine fornitore viene confermato dall'utente (vale a dire, quando lo stato dell'ordine fornitore viene impostato su **Confermato**), l'ordine appare nell'ordine confermato aperto. Resterà nell'elenco fino a quando non verrà registrato come ricevuto dal cliente.
