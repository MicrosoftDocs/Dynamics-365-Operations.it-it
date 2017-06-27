---
title: Dichiarazione elenco vendite UE
description: Questo articolo fornisce informazioni sulla dichiarazione elenco vendite dell'Unione Europea (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12811
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 06656fe519c82293d5a0eb2d48ae0f89ae0aef49
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="eu-sales-list-reporting"></a>Dichiarazione elenco vendite UE

[!include[banner](../includes/banner.md)]


Questo articolo fornisce informazioni sulla dichiarazione elenco vendite dell'Unione Europea (UE).

<a name="eu-sales-list-reporting"></a>Dichiarazione elenco vendite UE
-----------------------

Un fornitore che effettua forniture di prodotti o servizi intracomunitarie ad aziende che hanno sede nell'Unione Europea (EU) deve inviare una dichiarazione di forniture intracomunitaria (elenco vendite UE o ESL). In linea generale, la dichiarazione ESL deve essere inviata agli uffici tributari non oltre l'ultimo giorno del mese successivo al periodo coperto dall'elenco vendite UE. Il fornitore deve dichiarare la propria partita IVA sulla dichiarazione ESL e deve inoltre specificare, per cliente, le seguenti informazioni:

-   Partita IVA del cliente UE
-   Il valore totale delle forniture intracomunitarie di prodotti e servizi che vengono effettuati al cliente UE in tale periodo. Il fornitore deve inoltre separare le forniture di prodotti a un paese dalle forniture commerciali che riguardano tre paesi. Una transazione commerciale triangolare implica la consegna diretta dei prodotti dal fornitore del fornitore al cliente quando entrambe le parti sono registrate in altri stati membri dell'UE.

Utilizzando la dichiarazione ESL, gli uffici tributari di ogni stato membro dell'UE possono verificare se l'IVA è stata pagata per ciascuna transazione intracomunitaria. La combinazione di elenchi e di dichiarazioni VAT permette agli stati membri dell'UE di scambiarsi informazioni sul flusso dei prodotti sul territorio dell'UE.

## <a name="overview-of-the-eu-sales-list-reporting-process"></a>Panoramica del processo di dichiarazione dell'elenco vendite UE
È possibile completare le seguenti attività per la dichiarazione dell'elenco vendite UE:

-   Raccogliere informazioni sulle transazioni commerciali intracomunitarie. Una transazione commerciale intracomunitaria può essere una fattura di vendita, una fattura a testo libero, una fattura di progetto o una fattura fornitore. Una transazione viene identificata in base al paese della controparte. Le transazioni commerciali intracomunitarie di tipi differenti vengono raccolte nella tabella dell'elenco vendite UE, nella quale sono rappresentate nella forma comune. Ogni record della tabella ESL rappresenta una singola transazione ed è costituito dall'identificazione dell'IVA della controparte e il valore totale dei prodotti forniti e dei servizi erogati.
-   (Facoltativo) Visualizzare in anteprima la dichiarazione **Elenco vendite UE**. È possibile visualizzare in anteprima e convalidare la dichiarazione **Elenco vendite UE** per un periodo specificato sotto forma di cartella di lavoro di Microsoft Excel.
-   Generare la dichiarazione **Elenco vendite UE**. La dichiarazione **Elenco vendite UE** viene generata nella forma di un file elettronico di un determinato formato che è specifico a ogni stato membro dell'UE. In linea generale, una dichiarazione **Elenco vendite UE** contiene le informazioni di base sulla parte dichiarante e sui valori delle forniture di prodotti e servizi. Le informazioni vengono raggruppate in base al paese e all'identificatore IVA di una controparte.
-   Chiudere il periodo di dichiarazione Elenco vendite UE. Una volta generata la dichiarazione **Elenco vendite UE** e inviata alle autorità, è possibile contrassegnare i record della tabella ESL come **Chiusi**. Tali transazioni non verranno incluse nelle dichiarazioni aggiuntive.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Prerequisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Impostazione:</strong> persona giuridica</td>
<td>L'indirizzo principale della persona giuridica deve essere uno stato membro UE. Nella pagina <strong>Persone giuridiche</strong> (fare clic su <strong>Amministrazione organizzazione</strong> &gt; <strong>Organizzazioni</strong> &gt; <strong>Persone giuridiche</strong>), selezionare la persona giuridica. Nella Scheda dettaglio <strong>Indirizzi</strong>, creare un indirizzo, selezionare un paese e altri elementi dell'indirizzo, quindi contrassegnare l'indirizzo come <strong>Primario</strong>. Nella Scheda dettaglio <strong>Registrazione fiscale</strong>, nel campo <strong>Partita IVA</strong>, specificare la partita IVA della propria società.</td>
</tr>
<tr class="even">
<td><strong>Impostazione:</strong> parametri di partita IVA</td>
<td>Impostare i parametri di identificazione dell'esenzione IVA nella pagina <strong>Parametri paese</strong> (fare clic su <strong>Imposta</strong> &gt; <strong>Impostazione</strong> &gt; <strong>IVA</strong> &gt; <strong>Parametri paese</strong>). Per ciascun paese in cui si hanno delle controparti, creare un record nella pagina e specificare le seguenti informazioni:
<ul>
<li><strong>Paese</strong> - Selezionare un paese da associare alla partita IVA.</li>
<li><strong>IVA</strong> - Immettere il numero di partita IVA (ovvero il prefisso della partita IVA) per il paese selezionato.</li>
<li><strong>Verifica partita IVA</strong> - Selezionare questa casella di controllo per convalidare la partita IVA per il paese selezionato.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Impostazione: </strong>partite IVA</td>
<td>Creare i numero di esenzione IVA per le controparti nella pagina <strong>Partite IVA</strong> (fare clic su <strong>Imposta</strong> &gt; <strong>Impostazione</strong> &gt; <strong>IVA</strong> &gt; <strong>Partite IVA</strong>). Per ogni partita IVA, creare un record nella pagina e specificare le seguenti informazioni:
<ul>
<li><strong>Paese </strong> - Selezionare il paese di registrazione IVA della controparte.</li>
<li><strong>Partita IVA</strong> - Immettere la partita IVA della controparte.</li>
<li><strong>Ragione sociale</strong> - (Facoltativo) Immettere il nome della controparte.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Impostazione: </strong>registrazione fiscale delle controparti</td>
<td>Impostare le informazioni per la registrazione fiscale delle controparti nella pagina <strong>Tutti i clienti</strong> (fare clic su <strong>Vendite e marketing</strong> &gt; <strong>Clienti</strong> &gt; <strong>Tutti i clienti</strong>, selezionare il record di un cliente, quindi fare clic su <strong>Opzioni</strong> &gt; <strong>Cambia visualizzazione</strong> &gt; <strong>Visualizzazione dettagli</strong>) o nella pagina <strong>Fornitori</strong> (fare clic su <strong>Approvvigionamento</strong> &gt; <strong>Fornitori</strong> &gt; <strong>Fornitori</strong>, selezionare il record di un fornitore, quindi fare clic su <strong>Opzioni</strong> &gt; <strong>Cambia visualizzazione</strong> &gt; <strong>Visualizzazione dettagli</strong>). Nella Scheda dettaglio <strong>Fattura e consegna</strong>, nel campo <strong>Partita IVA</strong>, selezionare il numero di partita IVA.</td>
</tr>
<tr class="odd">
<td><strong>Impostazione: </strong>IVA</td>
<td>Impostare i codici imposta da includere nella dichiarazione <strong>Elenco vendite UE</strong> nella pagina <strong>Codici IVA</strong> (fare clic su <strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Codici IVA</strong>). Nella Scheda dettaglio <strong>Impostazione report</strong>, per ogni codice IVA da includere nel report, deselezionare la casella di controllo <strong>Escluso</strong>. Impostare i parametri IVA per gli articoli nella pagina <strong>Fasce IVA articoli</strong> (fare clic su <strong>Imposta</strong> &gt; <strong>Imposte indirette</strong> &gt; <strong>IVA</strong> &gt; <strong>Fasce IVA articoli</strong>). Per ogni fascia IVA articoli, selezionare un valore nel campo <strong>Tipo di dichiarazione</strong>. Il valore che si seleziona determina la colonna dell'importo ESL nella quale sarà incluso l'importo della riga.
<ul>
<li><strong>Vuoto</strong> - L'importo della riga viene incluso nella colonna <strong>Valore non assegnato</strong>.</li>
<li><strong>Articolo</strong> - L'importo della riga viene incluso nella colonna <strong>Valore degli articoli</strong>.</li>
<li><strong>Servizio</strong> - L'importo della riga viene incluso nella colonna <strong>Valore dei servizi</strong>.</li>
<li><strong>Investimento</strong> - L'importo della riga viene incluso nella colonna <strong>Valore degli investimenti</strong>. Questa colonna è rilevante solo per il Belgio.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Impostazione:</strong> configurazioni della dichiarazione ESL</td>
<td>Importare o creare configurazioni di report elettronici per l'Elenco vendite UE. Per informazioni su come creare e gestire le configurazioni dei report elettronici, vedere la documentazione relativa alla creazione di report elettronici.</td>
</tr>
<tr class="odd">
<td><strong>Impostazione: </strong>parametri generali</td>
<td>Impostare i parametri della dichiarazione ESL nella pagina <strong>Parametri per il commercio estero</strong> (fare clic su <strong>Imposta</strong> &gt; <strong>Impostazione</strong> &gt; <strong>Commercio estero</strong> &gt; <strong>Parametri per il commercio estero</strong>). Specificare i seguenti parametri:
<ul>
<li>Scheda <strong>Elenco vendite UE</strong>:
<ul>
<li><strong>Report sconto di cassa</strong> - Selezionare questa casella di controllo se deve essere incluso uno sconto di cassa nel valore quando viene inclusa una transazione nell'Elenco vendite UE.</li>
<li><strong>Trasferisci acquisti</strong> - Selezionare questa casella di controllo per includere gli acquisti nell'Elenco vendite UE.</li>
<li><strong>Mapping formato file</strong> - Selezionare il formato di report elettronico da utilizzare quando viene generato un file elettronico per l'Elenco vendite UE.</li>
<li><strong>Mapping formato report</strong> - Selezionare il formato di report elettronico da utilizzare quando viene generato un report di anteprima per l'Elenco vendite UE.</li>
<li><strong>Regola di arrotondamento</strong> - Specificare un numero reale da utilizzare per l'arrotondamento. Gli importi dell'Elenco vendite UE verranno arrotondati a multipli di questo numero.</li>
<li><strong>Metodo di arrotondamento</strong> - Selezionare il metodo di arrotondamento da utilizzare quando gli importi ESL vengono arrotondati (<strong>Normale</strong>, <strong>Arrotondamento per difetto</strong> o <strong>Arrotondamento per eccesso</strong>).</li>
<li><strong>Utilizzare il valore minimo</strong> - Selezionare questa casella di controllo se si desidera che gli importi inferiori al numero indicato in <strong>Regola di arrotondamento</strong> vengano arrotondati per eccesso al numero immesso in <strong>Regola di arrotondamento</strong>.</li>
<li><strong>Numero di decimali</strong> - Specificare il numero di decimali da mostrare negli importi ESL (sia nei file elettronici che nel report di <strong>anteprima ESL</strong>).</li>
</ul></li>
<li>Scheda <strong>Parametri paese</strong>: identificare gli stati membri UE. Per ogni stato membro dell'UE, creare un record nella pagina e specificare le seguenti informazioni:
<ul>
<li><strong>Paese</strong> - Selezionare un paese.</li>
<li><strong>Tipo di paese</strong> - Se il valore di <strong>Paese</strong> è il paese in cui ha sede legale la propria società, selezionare <strong>Nazionale</strong>. Se il valore di <strong>Paese</strong> è uno stato membro UE diverso dal paese in cui la propria società ha la sede legale, selezionare <strong>UE</strong>. Se il valore di <strong>Paese</strong> non è uno stato membro dell'UE, selezionare <strong>Paese terzo</strong>.</li>
</ul></li>
<li>Scheda <strong>Sequenze numeriche</strong>: sulla riga in cui il valore di <strong>Riferimento</strong> è <strong>Elenco vendite UE</strong>, selezionare un codice di sequenza numerica.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Transazioni correlate</strong></td>
<td><ul>
<li>Registrare una vendita a un cliente in un altro stato membro dell'UE.</li>
<li>Registrare una fattura a testo libero per un cliente in un altro stato membro dell'UE.</li>
<li>Registrare una fattura di progetto per un cliente in un altro stato membro dell'UE.</li>
<li>Registrare una fattura da un fornitore in un altro stato membro dell'UE.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="working-with-the-esl"></a>Utilizzo dell'Elenco vendite UE
### <a name="collecting-information-about-intra-community-trade-transactions"></a>Raccolta di informazioni sulle transazioni commerciali intracomunitarie

Le transazioni dei seguenti tipi possono essere considerate transazioni commerciali intracomunitarie:

-   Fatture di vendita
-   Fatture a testo libero
-   Fatture progetto
-   Fatture fornitore

Una transazione viene considerata una transazione commerciale intracomunitaria se l'indirizzo di consegna della transazione si trova in uno stato membro dell'UE. Per tali paesi, deve essere presente un record nella scheda **Parametri paese** della pagina **Parametri per il commercio estero** e il valore in **Tipo di paese** deve essere impostato su **UE**. Le transazioni commerciali intracomunitarie sono contrassegnate nel campo **Codice elenco**. Questo campo consente inoltre di separare le transazioni commerciali intracomunitarie generali dalle transazioni commerciali triangolari. È possibile raccogliere le informazioni sulle transazioni commerciali intracomunitarie nella pagina **Elenco vendite UE** (fare clic su **Imposta** &gt; **Dichiarazioni** &gt; **Commercio estero** &gt; **Elenco vendite UE**) utilizzando la funzione **Trasferimento**. Questa funzione consente di includere le transazioni che hanno importi di tipi di report differenti (vale a dire, articoli o servizi), in base alle fasce IVA articoli specificate nelle righe di transazione. È inoltre possibile applicare altri filtri per definire le transazioni che devono essere incluse. La funzione di **trasferimento** crea un record nella pagina **Elenco vendite UE** per ogni transazione commerciale intracomunitaria che viene inclusa e specifica un numero di conto di contropartita, un paese, una partita IVA, un numero di fattura e la data e gli importi totali delle righe per il tipo di report. La funzione copia inoltre il valore **Codice elenco** dalla transazione. È possibile modificare manualmente il codice elenco per la transazione nella pagina **Elenco vendite UE**. La funzione di **trasferimento** crea record nei quali il valore di **Stato relazione** è impostato su **Incluso**. È possibile convalidare le informazioni che vengono raccolte nella pagina **Elenco vendite UE** utilizzando la funzione **Convalida**.

### <a name="generating-the-eu-sales-list-report"></a>Generazione della dichiarazione Elenco vendite UE

È possibile generare una dichiarazione **Elenco vendite UE** utilizzando la funzione **Dichiarazione** nella pagina **Elenco vendite UE**. La funzione consente di selezionare un periodo di dichiarazione e di applicare filtri per definire i record dell'ESL da importare. Inoltre, è possibile specificare altri parametri specifici a ciascun paese. È inoltre possibile scegliere di generare un report di anteprima, un file elettronico o entrambi. La funzione **Dichiarazione** utilizza le impostazioni del report e del formato file che sono specificate nella pagina **Parametri per il commercio estero**. In generale, una dichiarazione **Elenco vendite UE** è costituita da righe distinte che elencano gli importi totali delle forniture per il paese controparte, la partita IVA e il tipo di report (sono incluse le transazioni commerciali triangolari). Una volta generato una dichiarazione **Elenco vendite UE** per uno specifico periodo, è possibile contrassegnare i record dell'Elenco vendite UE che sono inclusi nel report impostando il valore **Stato relazione** su **Dichiarato**. Per impostare questo stato, utilizzare la funzione **Contrassegna come dichiarato** nella pagina **Elenco vendite UE**.

### <a name="closing-the-eu-sales-list-reporting-period"></a>Chiusura del periodo di dichiarazione Elenco vendite UE.

Una volta completato il processo di creazione del report per uno specifico periodo (ad esempio, quando gli uffici IVA hanno accettato la dichiarazione **Elenco vendite UE**), è possibile contrassegnare i record dell'ESL che sono inclusi nel report del periodo impostando il valore in **Stato relazione** su **Chiuso**. Per impostare questo stato, utilizzare la funzione **Contrassegna come chiuso** nella pagina **Elenco vendite UE**. Se si annulla la chiusura del periodo, è possibile contrassegnare i record dell'ESL impostando il valore in **Stato relazione** su **Incluso**. Questi record possono quindi essere inclusi nuovamente in una dichiarazione **Elenco vendite UE**. Per impostare questo stato, utilizzare la funzione **Contrassegna come** **incluso** nella pagina **Elenco vendite UE**.




