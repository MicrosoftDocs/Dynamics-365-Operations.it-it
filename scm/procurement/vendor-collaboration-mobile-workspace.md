---
title: Area di lavoro mobile per la collaborazione fornitore per l&quot;app Microsoft Dynamics 365 for Operations
description: Nell&quot;area di lavoro mobile per la collaborazione fornitore i fornitori possono restare aggiornati sugli ordini fornitore che sono stati inviati loro per l&quot;approvazione e visualizzare le informazioni sugli ordini fornitore e i contatti nuovi e aggiornati.
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
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d5157e6f4b10b6158aa08279a9f68dae676f5666
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Area di lavoro mobile per la collaborazione fornitore per l'app Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Nell'area di lavoro mobile per la collaborazione fornitore i fornitori possono restare aggiornati sugli ordini fornitore che sono stati inviati loro per l'approvazione e visualizzare le informazioni sugli ordini fornitore e i contatti nuovi e aggiornati.

<a name="prerequisites"></a>Prerequisiti
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Informazioni sulla piattaforma mobile Microsoft Dynamics 365 for Operations</td>
<td><a href="https://ax.help.dynamics.com/en/wiki/mobile-development-handbook/">Piattaforma mobile di Dynamics 365 for Operations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Assicurarsi di utilizzare un ambiente con Microsoft Dynamics 365 for Operations versione 1611 e l'aggiornamento 3 della piattaforma di Microsoft Dynamics for Operations (novembre 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000">Dispositivo mobile con l'app Dynamics 365 for Operations installata</span></td>
<td><span style="color: #000000">Scaricare l'app Dynamics 365 for Operations dall'App Store mobile.</span></td>
</tr>
<tr class="even">
<td>Aggiornamento rapido KB 4013633</td>
<td>Impostare l'hotfix per abilitare le aree di lavoro che vengono fornite in Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000"><span style="color: #000000">Aggiornamento rapido KB 3216943</span> </span></td>
<td>Installare l'hotfix per abilitare l'area di lavoro mobile per la collaborazione fornitore.</td>
</tr>
<tr class="even">
<td>L'utente fornitore deve avere accesso all'interfaccia Web per la collaborazione fornitore in Dynamics 365 for Operations e impostare un utente di collaborazione fornitore.</td>
<td>Completare i passaggi descritti negli argomenti seguenti per impostare e utilizzare l'interfaccia Web per la collaborazione fornitore.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Utilizzare la collaborazione fornitore per gestire i fornitori esterni</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Gestire gli utenti della collaborazione fornitore</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Impostare e gestire la collaborazione fornitore</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Utilizzare la collaborazione fornitore per gestire i clienti in Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Panoramica
L'area di lavoro mobile per la collaborazione fornitore tiene i fornitori informati sui nuovi ordini fornitore in modo che possano visualizzare e rispondere agli ordini fornitore nel client Web Dynamics 365 for Operations. 

**Nota:** l'area di lavoro mobile dovrebbe essere utilizzata come supplemento all'interfaccia Web per la collaborazione fornitore, non come una sostituzione. 

Nell'area di lavoro mobile per la collaborazione fornitore i fornitori possono visualizzare i nuovi ordini fornitore che vengono inviati per l'approvazione. Vengono visualizzate le informazioni relative agli ordini fornitore, ad esempio prodotti, quantità e date di consegna richieste. Le informazioni sul prezzo sono disponibili, a seconda della configurazione per ciascun fornitore. 

Quando un utente è connesso come fornitore, i fornitori vedranno a quali ordini fornitore è stato risposto o quali sono ancora in attesa dell'azione del cliente. Il fornitore potrebbe avere suggerito un'altra data di consegna non ancora accettata dal cliente, di conseguenza l'ordine fornitore è in attesa dell'azione del cliente. Il fornitore visualizzerà anche un elenco di ordini fornitore confermati, ma non ancora consegnati. 

Per rispondere a un ordine fornitore, il fornitore deve utilizzare l'interfaccia Web per la collaborazione fornitore disponibile nel client Web Dynamics 365 for Operations. Inoltre qui il fornitore otterrà ulteriori informazioni sull'ordine, ad esempio gli allegati del documento, l'indirizzo di consegna per riga e le spese associate al fornitore. 

Con un ruolo di sicurezza speciale il fornitore può visualizzare i contatti che vengono registrati per un conto fornitore. Con lo stesso ruolo di sicurezza, il fornitore può visualizzare lo stato di qualsiasi richiesta utente inviata. 

La creazione di nuovi contatti e l'invio di nuove richieste utente devono essere effettuati nell'interfaccia di collaborazione fornitore disponibile nel client Web Dynamics 365 for Operations. 

Nell'area di lavoro mobile il fornitore può:

-   Visualizzare nuovi ordini fornitore inviati al fornitore.
-   Visualizzare gli ordini fornitore ai quali il fornitore ha risposto e che sono in attesa dell'azione del cliente.
-   Visualizzare gli ordini fornitore che sono confermati, ma non ancora completamente ricevuti.
-   Visualizzare le informazioni del contatto registrate per il conto fornitore (richiede un ruolo di sicurezza aggiuntivo).
-   Visualizzare le informazioni e tenere traccia dello stato di una richiesta utente inviata dal fornitore (richiede un ruolo di sicurezza aggiuntivo).

## <a name="get-started"></a>Per iniziare
Per iniziare sul dispositivo mobile:

1.  Nell'App Store mobile, scaricare e installare l'app Microsoft Dynamics 365 for Operations.
2.  Avviare l'app sul dispositivo.
3.  Immettere il proprio URL Dynamics 365.
4.  Immettere la società a cui accedere. Ad esempio, immettere **USMF**.
5.  La prima volta che si accede, verrà richiesto di specificare il nome utente e la password per l'account Microsoft Dynamics 365 for Operations.

Dopo aver eseguito l'accesso nell'app, non sono presenti aree di lavoro disponibili. Per visualizzare le aree di lavoro nell'app mobile, è necessario innanzitutto pubblicare le aree di lavoro desiderate nell'app Dynamics 365 for Operations. È necessario disporre dell'autorizzazione per l'amministrazione del sistema per pubblicare l'area di lavoro.

1.  Avviare Dynamics 365 for Operations.
2.  Passare ad **Amministrazione sistema** &gt; **Impostazioni** &gt; **Parametri di sistema**.
3.  Selezionare **Gestisci app per dispositivi mobili**.
4.  Selezionare l'area di lavoro **Collaborazione fornitore** per pubblicare nella piattaforma mobile.
5.  Selezionare **Pubblica area di lavoro**.
6.  Aggiornare il dispositivo per visualizzare le aree di lavoro pubblicate.
7.  Selezionare l'area di lavoro **Collaborazione fornitore**. Verrà visualizzata la pagina successiva.

    [![vendor-collaboration-mobile-app](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Contatti
La pagina **Contatti** consente di visualizzare tutti i contatti impostati per il conto fornitore. Visualizza il nome del contatto, la posta elettronica principale e l'alias degli utenti, se disponibile. Mostra inoltre se il conto utente del contatto è attivo. Quando si seleziona un contatto, vengono visualizzati i dettagli di contatto, ad esempio le persone giuridiche di cui la persona è un contatto, e le informazioni di contatto, ad esempio il numero di telefono o un altro indirizzo di posta elettronica.

## <a name="user-requests"></a>Richieste utente
La pagina **Richieste utente** consente di visualizzare tutte le richieste utente inviate tramite l'interfaccia Web per la collaborazione fornitore e di tenere traccia dello stato. Quando si seleziona una richiesta utente, è possibile verificare quanto è stato ordinato, aggiungere o disattivare un utente, cambiare la sicurezza e visualizzare i ruoli di sicurezza che sono stati ordinati per l'utente.

## <a name="purchase-orders-ready-for-review"></a>Ordini fornitore pronti per la revisione
La pagina **Ordini fornitore pronti per la revisione** consente di visualizzare tutti gli ordini fornitore che sono stati inviati dal cliente e ai quali non è stato risposto. È possibile visualizzare alcune informazioni relative all'ordine, ad esempio quali prodotti sono stati ordinati e quando consegnarli. Le informazioni sul prezzo sono disponibili solo se è configurata per il fornitore. È possibile verificare se l'ordine fornitore ha note o allegati. Per aprire gli allegati, è necessario utilizzare la collaborazione fornitore nel client Web. Selezionare **Riga ordine fornitore** per visualizzare tutte le righe con i dettagli. Tenere presente che per ogni riga verrà visualizzato un indicatore che mostrerà se sono presenti note o allegati o se è presente un indirizzo di consegna che è diverso rispetto a quanto riportato nell'intestazione. Per rispondere all'ordine fornitore, è necessario utilizzare il client Web per la collaborazione fornitore.

## <a name="awaiting-customer-action"></a>In attesa dell'azione del cliente
La pagina **In attesa dell'azione del cliente** consente di individuare gli ordini fornitore ai quali l'utente, o qualcuno della società che ha anche accesso alla collaborazione fornitore, ha risposto. Gli ordini fornitore sono visibili solo in questo elenco se il cliente deve eseguire una delle seguenti azioni nell'ordine fornitore.

-   Se l'ordine fornitore è stato rifiutato, il cliente deve aggiornare l'ordine inviato e inviarlo di nuovo o annullare l'ordine e rinviarlo. Quando l'ordine fornitore viene inviato di nuovo, scomparirà dalla pagina **In attesa dell'azione del cliente**.
-   Se l'ordine fornitore è stato accettato con le modifiche, il cliente dovrà aggiornare l'ordine originale e rinviarlo per la revisione o aggiornarlo in base alle modifiche e confermarlo immediatamente. In entrambi i casi l'ordine fornitore scomparirà dalla pagina **In attesa dell'azione del cliente**.
-   Se l'ordine fornitore è stato accettato e appare nella pagina **In attesa dell'azione del cliente**, significa che l'ordine fornitore non è stato confermato automaticamente quando l'accettazione è stata eseguita. È in attesa di essere modificato in Confermato da un addetto agli acquisti. In genere, l'ordine fornitore viene considerato come un contratto stipulato tra il cliente e il fornitore non appena il fornitore accetta l'ordine. Assegnare all'ordine fornitore lo stato Confermato sarebbe una formalità.

Selezionando l'ordine fornitore, vengono visualizzati dettagli aggiuntivi sulla risposta. È possibile visualizzare i dettagli riga e la risposta per ogni riga. Lo stato della riga indica quale delle seguenti risposte sono state date.

-   Accettato
-   Rifiutati
-   Accettata con modifiche
-   Sostituita/Sostituire
-   Suddivisa in programmazione/Riga programmazione

Tenere presente che viene visualizzato un indicatore **Consegna**=sì/no, utilizzato per indicare che le righe non verranno consegnate. Questa situazione potrebbe verificarsi se la riga è stata rifiutata o sostituita nei casi in cui non è prevista la consegna delle righe originali oppure nei casi in cui non è previsto che una riga che è stata suddivisa in più righe di programmazione e la riga originale vengano consegnate come richiesto nell'ordine ricevuto. Tutte le modifiche apportate alla risposta della riga ordine sono visualizzate, ad eccezione delle note e degli allegati caricati che sono visibili tramite l'interfaccia Web per la collaborazione fornitore.

## <a name="open-confirmed-orders"></a>Ordini confermati aperti
Quando l'ordine fornitore viene confermato dal cliente, ovvero all'ordine fornitore viene applicato lo stato confermato, verrà visualizzato nell'ordine confermato aperto. Resterà nell'elenco fino alla registrazione come ricevuto dal cliente.





