---
title: Area di lavoro mobile per la collaborazione fornitore per Microsoft Dynamics 365 per il app di operazioni
description: Nell&quot;area di lavoro mobile per la collaborazione di fornitori, i fornitori possono restare aggiornati sugli ordini fornitore che sono stati inviati loro di approvazione e visualizzare le informazioni sui nuovi ordini cliente e ordini fornitore aggiornati e i contatti.
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 36 - 37
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: fe8e912d-8446-4584-8a24-d8892e9028cd
ms.search.region: global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 9f441508b745d22218316128572c9ec6aeb7207b
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Area di lavoro mobile per la collaborazione fornitore per Microsoft Dynamics 365 per il app di operazioni

Nell'area di lavoro mobile per la collaborazione di fornitori, i fornitori possono restare aggiornati sugli ordini fornitore che sono stati inviati loro di approvazione e visualizzare le informazioni sui nuovi ordini cliente e ordini fornitore aggiornati e i contatti.

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
<td>Letto di Microsoft Dynamics 365 per la presentazione di cellulare di operazioni</td>
<td><a href="/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Dynamics 365 per la presentazione di cellulare di operazioni</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 per le operazioni</td>
<td>Assicurarsi che si utilizza un ambiente con Microsoft Dynamics 365 per la versione 1611 delle operazioni e Microsoft Dynamics per l'aggiornamento 3 la piattaforma delle operazioni (novembre 2016).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000;">Dispositivo mobile con Dynamics 365 per il app delle operazioni in</span></td>
<td><span style="color: #000000;">Scaricare Dynamics 365 per il app delle operazioni dalla memoria di cellulare del app.</span></td>
</tr>
<tr class="even">
<td>3215650 KB di Hotfix</td>
<td>Impostare il hotfix per abilitare le aree di lavoro che vengono fornite in Dynamics 365 per le operazioni.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000;"><span style="color: #000000;">3216943 KB di Hotfix</span></span></td>
<td>Impostare il hotfix per consentire all'area di lavoro del cellulare di collaborazione fornitore.</td>
</tr>
<tr class="even">
<td>L'utente fornitore deve avere accesso all'interfaccia Web per la collaborazione fornitore in Dynamics 365 per le operazioni e impostare un utente di collaborazione fornitore.</td>
<td>Completare i passaggi descritti negli argomenti seguenti per impostare e utilizzare l'interfaccia Web per la collaborazione a l fornitore.
<ul>
<li><a href="vendor-collaboration-work-external-vendors.md">Utilizzare la relazione fornitore per utilizzare i fornitori esterni</a></li>
<li><a href="manage-vendor-collaboration-users.md">Gestire gli utenti di collaborazione fornitore</a></li>
<li><a href="set-up-maintain-vendor-collaboration.md">Impostare e gestire la collaborazione fornitore</a></li>
<li><a href="vendor-collaboration-work-customers-dynamics-365-operations.md">Utilizzare la relazione fornitore per utilizzare i clienti in Dynamics 365 per le operazioni</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Panoramica
L'area di lavoro mobile per la collaborazione fornitore sono archiviati i fornitori informati sui nuovi ordini fornitore in modo da poter visualizzare e rispondere agli ordini fornitore in Dynamics 365 per la Web client delle operazioni.  

** Nota: ** L'area di lavoro spostato da utilizzare come supplemento all'interfaccia Web per la collaborazione fornitore, ma non sostituzione.  

Nell'area di lavoro mobile per la collaborazione di fornitori, i fornitori possono visualizzare i nuovi ordini fornitore che vengono inviati per l'approvazione. Consente di visualizzare le informazioni relative agli ordini fornitore, ad esempio prodotti, la quantità e date di consegna richieste. Le informazioni sul prezzo è disponibile, a seconda della configurazione per ciascun fornitore.  

Quando un utente connesso come fornitore, negli ordini fornitore completati o, ad esempio ordini fornitore ancora in attesa l'azione del cliente. Il fornitore può suggerire un intervallo di date di consegna non ancora acconsentita al cliente in modo dall'ordine fornitore è in attesa dell'azione del cliente. Il fornitore verranno visualizzati anche un elenco di ordini fornitore confermati ma non ancora consegnate.  

Per rispondere a un ordine fornitore, il fornitore deve utilizzare l'interfaccia Web per la collaborazione fornitore disponibile in Dynamics 365 per la Web client delle operazioni. Si tratta del fornitore assegnato ulteriori informazioni sull'ordine, ad esempio gli allegati di documento, l'indirizzo di consegna di riga e le spese associate al fornitore.  

Con un ruolo di sicurezza speciale, il fornitore può visualizzare che i contatti vengono registrate per un conto fornitore. Con lo stesso ruolo di sicurezza, il fornitore può visualizzare lo stato di qualsiasi richiesta utente inviata.  

Creazione di nuovi contatti e inviare nuove richieste utente devono essere effettuati nell'interfaccia di collaborazione fornitore disponibile in Dynamics 365 per la Web client delle operazioni.  

Nell'area di lavoro di cellulare, il fornitore può:

-   Nuovi ordini fornitore di visualizzazione inviati al fornitore.
-   Gli ordini fornitore di visualizzazione che il fornitore ha completato in attesa dell'azione del cliente.
-   Visualizzare ordini fornitore in uno stato confermato nonché completamente non sono ancora stati ricevuti.
-   Consente di visualizzare le informazioni sul contatto registrate per il conto fornitore (richiede un ruolo di sicurezza aggiuntive).
-   Consente di visualizzare informazioni e tenere traccia dello stato di una richiesta utente inviata dal fornitore (richiede un ruolo di sicurezza aggiuntive).

## <a name="get-started"></a>Per iniziare
Per iniziare sul dispositivo mobile:

1.  Nella memoria di cellulare del app, download e impostare Microsoft Dynamics 365 per il app delle operazioni.
2.  Inizia app Approvazioni sull'unità.
3.  Immettere il proprio Dynamics 365 URL.
4.  Immettere la società in per accedere a. Ad esempio, immettere USMF ** **.
5.  La prima volta che ha in, verrà chiesto di specificare il nome utente e password per il sistema Microsoft Dynamics 365 per l'account operazioni. 

Dopo aver aperto la sessione il app, non sono presenti aree di lavoro disponibili. Per visualizzare le aree di lavoro nell'app Approvazioni di cellulare, è necessario rilasciare le aree di lavoro desiderate in Dynamics 365 per il app delle operazioni. È necessario disporre di autorizzazioni per Amministrazione sistema a emettere l'area di lavoro.

1.  Avviare Dynamics 365 per le operazioni.
2.  ** Fare clic su Amministrazione sistema ** &gt; ** l'impostazione ** &gt; ** parametri di sistema **.
3.  Selezionare ** gestire il app mobile **.
4.  Selezionare l'area di lavoro ** relazione fornitore ** per emettere la piattaforma spostato.
5.  ** Pubblicare Selezionare l'area di lavoro **.
6.  Aggiorna la propria unità per visualizzare le aree di lavoro generati.
7.  Selezionare ** relazione fornitore ** l'area di lavoro. La pagina successiva.

[fornitore-collaborazione-cellulare- app![(]. /media/vendor-collaboration-mobile-app.png)](. /media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Contatti
** Contatti ** la pagina consente di visualizzare tutti i contatti impostati per il conto fornitore. Visualizza il nome del contatto, posta elettronica principale e l'alias di utenti, se disponibile. Viene inoltre illustrato se l'account utente del contatto è attivo. Quando si seleziona un contatto, i dettagli di contatto, ad esempio le persone giuridiche la persona è un contatto per le informazioni di contatto e relative ad esempio il numero di telefono o un indirizzo di posta elettronica diverso.

## <a name="user-requests"></a>Richieste utente
** Richieste utente ** la pagina consente di visualizzare tutte le richieste utente inviata tramite l'interfaccia Web per la collaborazione fornitore e tenere traccia dello stato. Quando si seleziona una richiesta utente, è possibile verificare quanto è stato ordinato, aggiungere o disattiva un utente, si modifica la protezione e determina la visualizzazione dei ruoli di sicurezza sono stati ordinati per l'utente.

## <a name="purchase-orders-ready-for-review"></a>Ordini fornitore pronti per la revisione
** Ordini fornitore pronti per la revisione ** la pagina consente di visualizzare tutti gli ordini fornitore che sono stati inviati dal cliente e come completato. È possibile visualizzare le informazioni relative all'ordine, ad esempio per cui i prodotti sono stati ordinati e sulla distribuzione. Le informazioni sul prezzo è disponibile solo se questa è configurata per il fornitore.  

È possibile verificare se l'ordine fornitore ha note o collegati. Per aprire gli allegati, è necessario utilizzare la relazione fornitore nella Web client. Selezionare ** riga ordine fornitore ** visualizzare tutte le righe con i dettagli. Tenere presente che per ogni riga, verrà visualizzato un indicatore se sono presenti note o collegati o se è presente un indirizzo di consegna che è diverso rispetto a quanto è indicato nell'intestazione.  

Per rispondere a un ordine fornitore, è necessario utilizzare il client Web per la collaborazione a l fornitore.

## <a name="awaiting-customer-action"></a>In attesa dell'azione del cliente
** Attendendo a cliente determinerà ** la pagina consente di individuare gli ordini fornitore a cui l'utente, uno o nella società denominata anche ha accesso alla collaborazione fornitore, ha risposto. Gli ordini fornitore sono visibili solo in questo elenco se il cliente deve eseguire una delle seguenti azioni dell'ordine fornitore.

-   Se l'ordine fornitore è stato rifiutato, il cliente deve o aggiornare l'ordine invio nonché inviare di nuovo, o annullare l'ordine e invio. Quando l'ordine fornitore viene inviato di nuovo, scomparirà ** attesa a cliente determinerà ** dalla pagina.
-   Se l'ordine fornitore è stato accettato con le modifiche, il cliente è necessario aggiornare l'ordine originario e rinviare per la revisione, o aggiornilo in base alle modifiche e confermilo immediatamente. In entrambi i casi, l'ordine fornitore scomparirà ** attesa a cliente determinerà ** dalla pagina.
-   Se l'ordine fornitore è stato accettato e riportato ** attesa a cliente determinerà ** nella pagina, in quanto l'ordine fornitore non è stato confermato automaticamente durante l'accettazione è stata eseguita. Sta in attesa di revisione e per modificare l'ordine a Confermato. In genere, l'ordine fornitore viene considerato come contratto stipulato tra il cliente e il fornitore non appena il fornitore accetta l'ordine. Spostamento dell'ordine fornitore allo stato confermato sarebbe una formalità.

Selezionando l'ordine fornitore, dettagli aggiuntivi vengono visualizzati sulla risposta. È possibile visualizzare i dettagli riga e la risposta per ogni riga. Stato della riga indica quale dei seguenti risposte sono state date.

-   Accettato
-   Rifiutati
-   Accettata con modifiche
-   Sostituito/soltanto in
-   Dividi di programmazione/riga di programmazione

Tenere presente che viene visualizzato un indicatore ** consegnando ** =yes/no, utilizzato per indicare che le righe non verranno consegnate. Questa situazione potrebbe verificarsi se la riga è stata rifiutata, o sostituito in cui le righe originali non che i record consegnassero, ovvero una riga che è stata suddivisa in più righe di programmazione e riga originale non si prevede di consegnasse richiesti nell'ordine ricevuto.  

Tutte le modifiche apportate alla risposta della riga ordine visualizzate, ad eccezione delle note e gli allegati caricati, che sia possibile tramite l'interfaccia Web per la collaborazione a l fornitore.

## <a name="open-confirmed-orders"></a>Apri confermato gli ordini
Quando l'ordine fornitore viene confermato dal cliente, che indica l'ordine fornitore viene modificato lo stato confermato, verrà visualizzato nell'ordine aperto confermato. Resterà nell'elenco fino alla registrazione come ricevuto dal cliente.


