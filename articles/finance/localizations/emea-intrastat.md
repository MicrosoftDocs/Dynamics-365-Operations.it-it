---
title: Panoramica di Intrastat
description: In questo argomento vengono fornite informazioni sulla dichiarazione Intrastat per gli scambi commerciali di beni e servizi tra paesi dell'Unione Europea. Sono riportate informazioni generali sul processo di dichiarazione e vengono descritte le impostazioni necessarie e i prerequisiti.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a70108696d6187126c23eca1779553210cd4a9d6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175787"
---
# <a name="intrastat-overview"></a>Panoramica di Intrastat

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sulla dichiarazione Intrastat per gli scambi commerciali di beni e servizi tra paesi dell'Unione Europea. Sono riportate informazioni generali sul processo di dichiarazione e vengono descritte le impostazioni necessarie e i prerequisiti.

Intrastat è il sistema per la raccolta e la generazione di statistiche sugli scambi commerciali tra paesi dell'Unione Europea. La dichiarazione Intrastat è richiesta ogni volta che un prodotto attraversa il confine di un altro paese UE. In più paesi, il report Intrastat si applica anche ai servizi. Gli elementi obbligatori e facoltativi possono essere raccolti nella dichiarazione Intrastat. Gli elementi seguenti sono obbligatori: numero di imposta sul valore aggiunto (IVA) della parte responsabile di immettere informazioni, il periodo di riferimento, il flusso (arrivo o spedizione), il codice di voce doganale di otto cifre, lo stato membro del partner (stato membro della spedizione negli arrivi e stato membro di destinazione delle spedizioni), il valore delle merci, la quantità delle merci (massa netto e unità supplementare) e la natura della transazione. Per i paesi/regioni è inoltre possibile raccogliere gli elementi facoltativi nelle varie condizioni. Alcuni elementi facoltativi sono il paese di origine, i termini di consegna, la modalità di trasporto, un codice di voce doganale più dettagliato che CN8, l'area di origine nelle spedizioni e l'area di destinazione degli arrivi, la procedura statistica, il valore statistico, una descrizione delle merci e il porto/aeroporto di carico/di scarico.

## <a name="overview-of-the-intrastat-reporting-process"></a>Panoramica del processo di reporting Intrastat
Le seguenti sezioni illustrano il flusso globale di informazioni utilizzato per la dichiarazione Intrastat.

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>1. Immettere una transazione che attraversa il confine di un altro paese UE

Una fattura cliente, una fattura a testo libero, una fattura di acquisto, una fattura di progetto, un documento di trasporto cliente, un'entrata prodotti del fornitore, un ordine di trasferimento viene trasferito nel giornale di registrazione Intrastat solo se il tipo di paesi di destinazione (sulle spedizioni) o la spedizione (gli arrivi) è **UE**. Questa funzionalità è stata estesa per Microsoft Dynamics 365 for Operations (1611) e consente di specificare gli indirizzi di carico per una transazione intracomunitaria. Se l'indirizzo di carico è diverso all'ufficio del fornitore (o l'indirizzo commerciale del cliente per ordine di reso) la dichiarazione Intrastat opererà con queste informazioni. Quando si crea un ordine cliente, una fattura a testo libero, un ordine fornitore, una fattura fornitore, una fattura di progetto, un ordine di trasferimento, alcuni campi correlati al commercio estero hanno valori predefiniti nell'intestazione del documento o nella riga. Il codice transazione predefinito viene ricavato dal campo corrispondente sulla pagina **Parametri per il commercio estero**. Il codice di voce doganale predefinito, il paese di origine e lo stato/regione o provincia di origine vengono ottenuti dall'articolo. È possibile modificare i valori predefiniti ed è inoltre necessario completare altre informazioni commerciali estere: procedura statistica, metodo di trasporto e porto.

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>2. Utilizzare il giornale di registrazione Intrastat per generare informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE).

A fini statistici, generare ogni mese le informazioni relative al commercio tra i diversi paesi/regioni UE. È possibile trasferire le transazioni da una fattura a testo libero, una fattura cliente, un documento di trasporto cliente, una fattura fornitore, un documento di trasporto fornitore, una fattura progetto, o un ordine di trasferimento, in base ai criteri di trasferimento impostati nella pagina **Parametri per il commercio estero**. In alternativa, è possibile immettere le transazioni manualmente. È possibile aggiornare manualmente le transazioni trasferite nel giornale di registrazione Intrastat, se gli aggiornamenti vengono richiesti. Sotto le condizioni specifiche impostate nella pagina **Compressione di Intrastat**, è possibile comprimere le transazioni nel giornale di registrazione Intrastat. Alcuni paesi consentono di applicare una piccola soglia di transazione. È quindi possibile dichiarare tutte le transazioni in tale soglia nel codice di voce doganale specificato. È possibile aggiornare il codice di voce doganale sulle righe del giornale di registrazione Intrastat corrispondenti, in **Limite minimo** base all'impostazione della pagina **Parametri per il commercio estero**. È inoltre possibile comprimere le transazioni, in base all'impostazione **Compressione di Intrastat**. È possibile convalidare la completezza delle transazioni nel giornale di registrazione Intrastat, in base all'impostazione **Impostazione dell'assegno** della pagina **Parametri per il commercio estero**. I dati nei campi corrispondenti possono essere convalidati per completezza: paese, stato/regione o provincia, peso, codice di voce doganale, codice transazione, unità aggiuntiva, porta, origine, termini di consegna, metodo di trasporto e numero esenzione IVA. Le transazioni che non vengono completate verranno contrassegnate come non valide.

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>3. Utilizzare il giornale di registrazione Intrastat per registrare e visualizzare informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE).

A fini statistici, registrare ogni mese le informazioni relative al commercio tra i diversi paesi/regioni UE. È possibile stampare il report Intrastat, in base alle impostazioni **Mapping formato di report** nella pagina **Parametri per il commercio estero**. È possibile anche generare un file elettronico, in base alle impostazioni **Mapping formato file** nella pagina **Parametri per il commercio estero**. Per ulteriori informazioni sulla dichiarazione Intrastat, inclusi i prerequisiti necessari, vedere le registrazioni attività sulla dichiarazione Intrastat:

-   Generare una dichiarazione Intrastat UE
-   Trasferire transazioni a Intrastat
-   Specifica di un indirizzo di carico per una transazione intracomunitaria

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono elencati i prerequisiti per la dichiarazione Intrastat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Impostazione indirizzo</td>
<td>Configurare codice del paese utilizzato dall'ISO (International Organization for Standardization).</td>
</tr>
<tr class="even">
<td>Persona giuridica</td>
<td>Impostare le partite VAT dell'importazione/esportazione, l'estensione del codice filiale di importazione/esportazione e il codice Intrastat assegnato alla persona giuridica.</td>
</tr>
<tr class="odd">
<td>Gerarchia di categorie di prodotti (gerarchia di vendita, gerarchia di approvvigionamento)</td>
<td>Assegnare i codici di voce doganale Intrastat ai nodi di categoria <strong>Codici di voce doganale</strong> nella scheda <strong>Gerarchia di categorie</strong> della pagina. Quando si assegna un codice di voce doganale a un nodo di categoria padre, il codice è applicabile a tutti i nodi di categoria figlio. I codici di voce doganale selezionati saranno disponibili nella visualizzazione <strong>Selezionato</strong> quando si seleziona un codice di voce doganale nei dettagli del prodotto rilasciato e nelle righe di ordine cliente, ordine fornitore e ordine di trasferimento.</td>
</tr>
<tr class="even">
<td>Dettagli prodotto rilasciato</td>
<td>Impostare i seguenti dati del commercio estero per i prodotti rilasciati:
<ul>
<li><strong>Codice di voce doganale</strong> Consente di selezionare dall presente una o due l'elenco delle voci doganali selezionate che viene recuperato dalle categorie di prodotti assegnati o dall'elenco completo di codici di voce doganale Intrastat.</li>
<li><strong>Percentuale spese totali</strong></li>
<li><strong>Paese di origine</strong> Consente di selezionare il paese predefinito in cui le merci sono state completamente ottenute o prodotto si.</li>
<li><strong>Stato/regione o provincia di origine/destinazione</strong> Consente di selezionare lo stato predefinito/regione di destinazione per gli arrivi e il stato/regione o provincia di origine per le spedizioni.</li>
<li><strong>Peso netto in kg</strong></li>
</ul></td>
</tr>
<tr class="odd">
<td>Clienti</td>
<td>Paese in cui è presente l'indirizzo di consegna del cliente nella regione UE.</td>
</tr>
<tr class="even">
<td>Fornitori</td>
<td>Paese in cui è presente l'indirizzo di consegna del cliente nella regione UE.</td>
</tr>
<tr class="odd">
<td>Spese varie</td>
<td>Impostare il codice spese varie da includere nell'importo della fattura, l'importo statistico, o entrambi. <strong>Codici spese</strong> In <strong>Commercio estero</strong> la pagina, nella scheda, attivare <strong>Valore di fattura Intrastat</strong> per includere le spese ammontano il valore di fattura e consentono <strong>Valore statistico Intrastat</strong> per includere le spese ammontano il valore statistico.</td>
</tr>
<tr class="even">
<td>Creazione di report elettronici</td>
<td>Impostare le configurazioni del report elettroniche per esportare i dati Intrastat in un file elettronico con il formato richiesto dagli uffici competenti e visualizzare l'anteprima dei dati Intrastat in formato semplice da usare e leggibile (ad esempio, in Microsoft Excel).</td>
</tr>
<tr class="even">
<td>Magazzino</td>
<td>Associare i conti fornitore con i codici magazzino per il ricaricamento della partita IVA durante il trasferimento dell'ordine di trasferimento.</td>
</tr>
</tbody>
</table>

## <a name="setup"></a>Imposta
Nelle sezioni seguenti sono descritte le impostazioni necessarie per la dichiarazione Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Impostare tutti gli elenchi correlati a Intrastat richiesti

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elenco</th>
<th>Informazioni aggiuntive</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Codici voce doganale</td>
<td>Impostare una gerarchia di categorie di tipo <strong>Codice di voce doganale</strong> e immettere i codici di voce doganale in base all'elenco di nomenclatura combinata. Per ciascuna voce doganale è possibile definire le seguenti informazioni:
<ul>
<li>Il nome della voce doganale e il codice della voce doganale</li>
<li>Il nome descrittivo e/o il nome tradotto</li>
<li>Impostazioni per la dichiarazione di unità aggiuntive (supplementari) nella scheda <strong>Commercio estero</strong>. È possibile selezionare l'unità aggiuntiva nell'elenco di unità. È inoltre possibile specificare se il peso delle voci doganali deve essere dichiarato oltre all'unità aggiuntiva selezionata.</li>
</ul></td>
</tr>
<tr class="even">
<td>Codici transazioni</td>
<td>Impostare la natura della transazione in base ai requisiti per il paese. Per ogni codice transazione impostato, è necessario impostare le regole per calcolare gli importi fattura e gli importi statistici per gli ordini di trasferimento e vendite.
<ul>
<li>Per gli ordini di trasferimento, si imposta una delle seguenti regole per calcolare gli importi fattura e gli importi statistici:
<ul>
<li><strong>Vuoto</strong> – L'importo sarà 0 (zero).</li>
<li><strong>Importo costo finanziario</strong> – L'importo sarà uguale al costo finanziario.</li>
<li><strong>Costo totale</strong> – L'importo sarà uguale al costo totale della transazione.</li>
<li><strong>Manuale</strong> – L'importo sarà uguale a quello che è specificato manualmente nella riga ordine di trasferimento.</li>
</ul></li>
<li>Per gli ordini cliente e gli ordini acquisto, si imposta una delle seguenti regole per calcolare gli importi fattura e gli importi statistici:
<ul>
<li><strong>Vuoto</strong> – L'importo sarà 0 (zero).</li>
<li><strong>Importo della fattura</strong> – L'importo sarà uguale a quello fatturato per la voce doganale.</li>
<li><strong>Imponibile</strong> – L'importo sarà uguale a quello che sarà fatturato prima di qualsiasi sconto applicato.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Metodi di trasporto</td>
<td>Impostare la modalità di trasporto in base ai requisiti per il paese. Per ciascuna modalità di consegna, è possibile impostare un metodo predefinito di trasporto nella scheda <strong>Commercio estero</strong>.</td>
</tr>
<tr class="even">
<td>Porti</td>
<td>Impostare il porto/aeroporto di carico/scarico se queste informazioni vengono raccolte dal proprio paese.</td>
</tr>
<tr class="odd">
<td>Procedure statistiche</td>
<td>Impostare la procedura statistica se queste informazioni vengono raccolte dal proprio paese.</td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Impostare regole di compressione per le transazioni Intrastat

Nella pagina **Compressione di Intrastat**, è possibile selezionare i campi da utilizzare per la compressione. Tutte le transazioni con la stessa combinazione di valori dei campi selezionati nel giornale di registrazione Intrastat verranno compresse in una singola transazione quando si esegue la funzione di comprimi nel giornale di registrazione Intrastat.

### <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

Utilizzare la pagina **Parametri per il commercio estero** per impostare i parametri nella seguente tabella.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>TAB</th>
<th>Parametri</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generale</td>
<td><ul>
<li>Nella scheda <strong>Generale </strong> specificare le e seguenti informazioni:
<ul>
<li>Valore predefinito per i codici transazione da utilizzare sugli ordini acquisto, note di credito e ordini di trasferimento. Il codice transazione impostato per le note di accredito verrà utilizzato come il codice per le merci fisiche restituite ed è utilizzato per i resi fisici di scostamento rispetto alle note di accredito della correzione.</li>
<li>Il dipendente responsabile di produzione report Intrastat.</li>
</ul></li>
<li><strong>Limite minimo</strong> Consente di specificare le impostazioni per aggiornare le transazioni nella soglia:
<ul>
<li>L'importo e il peso di soglia</li>
<li>Il codice di voce doganale da applicare alle transazioni che sono sotto la soglia</li>
</ul></li>
<li><strong>Trasferisci</strong> Consente di specificare i criteri per le transazioni di trasferimento nel giornale di registrazione Intrastat. È possibile specificare le transazioni vengono trasferite solo quando gli articoli sono conformi a un o tutti criteri seguente:
<ul>
<li>Gli articoli non sono articoli di tipo Assistenza.</li>
<li>Gli articoli hanno un codice voce doganale.</li>
<li>Gli articoli hanno un peso.</li>
<li>Gli articoli hanno unità supplementari.</li>
</ul></li>
<li><strong>Impostazione dell'assegno</strong> Consente di specificare le regole per la convalida della completezza dei dati Intrastat. È possibile selezionare i dati vengono convalidati.</li>
<li><strong>Regole di arrotondamento</strong> Consente di specificare le seguenti impostazioni per gli importi di arrotondamento e i pesi nella dichiarazione Intrastat:
<ul>
<li>Regola di arrotondamento (precisione)</li>
<li>Metodo di arrotondamento per eccesso: eccesso, difetto o normale</li>
<li>Il numero di posizioni decimali per gli importi e i pesi</li>
<li>Istruzioni per l'arrotondamento i pesi minori di 1 chilogrammo (kg): con arrotondamento a 1 chilogrammo, normale, o non arrotondamento</li>
</ul></li>
<li><strong>Report elettronico</strong> Consente di specificare i riferimenti alle configurazioni del report elettroniche, in modo da poter generare un file elettronico e un report.</li>
<li><strong>Gerarchia di codici di voce doganale</strong> Consente di specificare la gerarchia <strong>Codice di voce doganale</strong> di categorie di tipo che rappresenta il codice di voce doganale CN8 Intrastat.</li>
  <li> <strong>Tipo di tasso di cambio</strong> - Facoltativamente, specificare un tasso di cambio da utilizzare per dichiarare le vendite Intrastat e le transazioni di acquisto in valuta estera. Questa opzione viene utilizzata se il tasso è diverso da quello applicato quando si registra la transazione.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Informazioni sul contatto agente</td>
<td>Specificare il nome, indirizzo, la partita IVA, il numero di telefono e il numero di fax agente.</td>
</tr>
<tr class="odd">
<td>Proprietà paese</td>
<td>Impostare il paese della persona giuridica corrente su <strong>Domestico</strong>. Impostare il paese dei diversi paesi UE delle aree in cui partecipi al commercio UE alla persona giuridica corrente <strong>UE</strong>. Per ogni paese, vengono identificate il codice paese per scopi di commercio estero.</td>
</tr>
<tr class="even">
<td>Sequenza numerica</td>
<td>Specificare la sequenza numerica del giornale di registrazione Intrastat.</td>
</tr>
</tbody>
</table>

