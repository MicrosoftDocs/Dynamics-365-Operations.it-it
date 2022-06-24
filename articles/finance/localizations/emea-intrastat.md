---
title: Panoramica di Intrastat
description: In questo articolo vengono fornite informazioni sulla dichiarazione Intrastat per gli scambi commerciali di beni e servizi tra paesi dell'Unione Europea.
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9360f97506ac7bdf67bb2f1b296f01b6ed49b39f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894781"
---
# <a name="intrastat-overview"></a>Panoramica di Intrastat

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sulla dichiarazione Intrastat per gli scambi commerciali di beni e servizi tra paesi dell'Unione Europea. Sono riportate inoltre informazioni generali sul processo di dichiarazione e vengono descritte le impostazioni necessarie e i prerequisiti.

Intrastat è il sistema per la raccolta e la generazione di statistiche sugli scambi commerciali tra paesi dell'Unione Europea. La dichiarazione Intrastat è richiesta ogni volta che un prodotto attraversa il confine di un altro paese UE. In più paesi, il report Intrastat si applica anche ai servizi. Gli elementi obbligatori e facoltativi possono essere raccolti nella dichiarazione Intrastat. Gli elementi seguenti sono obbligatori: numero di imposta sul valore aggiunto (IVA) della parte responsabile di immettere informazioni, il periodo di riferimento, il flusso (arrivo o spedizione), il codice di voce doganale di otto cifre, lo stato membro del partner (stato membro della spedizione negli arrivi e stato membro di destinazione delle spedizioni), il valore delle merci, la quantità delle merci (massa netto e unità supplementare) e la natura della transazione. Per i paesi/regioni è inoltre possibile raccogliere gli elementi facoltativi nelle varie condizioni. Alcuni elementi facoltativi sono il paese di origine, i termini di consegna, la modalità di trasporto, un codice di voce doganale più dettagliato che CN8, l'area di origine nelle spedizioni e l'area di destinazione degli arrivi, la procedura statistica, il valore statistico, una descrizione delle merci e il porto/aeroporto di carico/di scarico.

## <a name="overview-of-the-intrastat-reporting-process"></a>Panoramica del processo di reporting Intrastat
Le seguenti sezioni illustrano il flusso globale di informazioni utilizzato per la dichiarazione Intrastat.

### <a name="enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>Immettere una transazione che attraversa il confine di un altro paese UE

Una fattura cliente, una fattura a testo libero, una fattura di acquisto, una fattura di progetto, un documento di trasporto cliente, un'entrata prodotti del fornitore, un ordine di trasferimento viene trasferito nel giornale di registrazione Intrastat solo se il tipo di paesi di destinazione (sulle spedizioni) o la spedizione (gli arrivi) è **UE**. Questa funzionalità è stata estesa per Microsoft Dynamics 365 for Operations (1611) e consente di specificare gli indirizzi di carico per una transazione intracomunitaria. Se l'indirizzo di carico è diverso all'ufficio del fornitore (o l'indirizzo commerciale del cliente per ordine di reso) la dichiarazione Intrastat opererà con queste informazioni. Quando si crea un ordine cliente, una fattura a testo libero, un ordine fornitore, una fattura fornitore, una fattura di progetto, un ordine di trasferimento, alcuni campi correlati al commercio estero hanno valori predefiniti nell'intestazione del documento o nella riga. Il codice transazione predefinito viene ricavato dal campo corrispondente sulla pagina **Parametri per il commercio estero**. Il codice di voce doganale predefinito, il paese di origine e lo stato/regione o provincia di origine vengono ottenuti dall'articolo. È possibile modificare i valori predefiniti ed è inoltre necessario completare altre informazioni commerciali estere: procedura statistica, metodo di trasporto e porto.

### <a name="use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>Utilizzare il giornale di registrazione Intrastat per generare informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE).

A fini statistici, generare ogni mese le informazioni relative al commercio tra i diversi paesi/regioni UE. È possibile trasferire le transazioni da una fattura a testo libero, una fattura cliente, un documento di trasporto cliente, una fattura fornitore, un documento di trasporto fornitore, una fattura progetto, o un ordine di trasferimento, in base ai criteri di trasferimento impostati nella pagina **Parametri per il commercio estero**. In alternativa, è possibile immettere le transazioni manualmente. È possibile aggiornare manualmente le transazioni trasferite nel giornale di registrazione Intrastat, se gli aggiornamenti vengono richiesti. Sotto le condizioni specifiche impostate nella pagina **Compressione di Intrastat**, è possibile comprimere le transazioni nel giornale di registrazione Intrastat. Alcuni paesi consentono di applicare una piccola soglia di transazione. È quindi possibile dichiarare tutte le transazioni in tale soglia nel codice di voce doganale specificato. È possibile aggiornare il codice di voce doganale sulle righe del giornale di registrazione Intrastat corrispondenti, in **Limite minimo** base all'impostazione della pagina **Parametri per il commercio estero**. È inoltre possibile comprimere le transazioni, in base all'impostazione **Compressione di Intrastat**. È possibile convalidare la completezza delle transazioni nel giornale di registrazione Intrastat, in base all'impostazione **Impostazione dell'assegno** della pagina **Parametri per il commercio estero**. I dati nei campi corrispondenti possono essere convalidati per completezza: paese, stato/regione o provincia, peso, codice di voce doganale, codice transazione, unità aggiuntiva, porta, origine, termini di consegna, metodo di trasporto e numero esenzione IVA. Le transazioni che non vengono completate verranno contrassegnate come non valide.

### <a name="use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>Utilizzare il giornale di registrazione Intrastat per registrare e visualizzare informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE)

A fini statistici, registrare ogni mese le informazioni relative al commercio tra i diversi paesi/regioni UE. È possibile stampare il report Intrastat, in base alle impostazioni **Mapping formato di report** nella pagina **Parametri per il commercio estero**. È possibile anche generare un file elettronico, in base alle impostazioni **Mapping formato file** nella pagina **Parametri per il commercio estero**. Per ulteriori informazioni sulla dichiarazione Intrastat, inclusi i prerequisiti necessari, vedere le registrazioni attività sulla dichiarazione Intrastat:

  - Generare una dichiarazione Intrastat UE
  - Trasferire transazioni a Intrastat
  - Specifica di un indirizzo di carico per una transazione intracomunitaria

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono elencati i prerequisiti per la dichiarazione Intrastat.

|  Prerequisito  |  Descrizione  |
|-------------------------|-------------------------|
| Impostazione indirizzo | Configurare codice del paese utilizzato dall'ISO (International Organization for Standardization). |
| Persona giuridica | Impostare le partite VAT dell'importazione/esportazione, l'estensione del codice filiale di importazione/esportazione e il codice Intrastat assegnato alla persona giuridica. |
| Gerarchia di categorie di prodotti (gerarchia di vendita, gerarchia di approvvigionamento) | Assegnare i codici di voce doganale Intrastat ai nodi di categoria **Codici di voce doganale** nella scheda **Gerarchia di categorie** della pagina. Quando si assegna un codice di voce doganale a un nodo di categoria padre, il codice è applicabile a tutti i nodi di categoria figlio. I codici di voce doganale selezionati saranno disponibili nella visualizzazione **Selezionato** quando si seleziona un codice di voce doganale nei dettagli del prodotto e nelle righe di ordine cliente, ordine fornitore e ordine di trasferimento. |
| Dettagli prodotto rilasciato | Impostare i seguenti dati del commercio estero per i prodotti rilasciati:<ul><li>**Codice di voce doganale** Consente di selezionare dall presente una o due l'elenco delle voci doganali selezionate che viene recuperato dalle categorie di prodotti assegnati o dall'elenco completo di codici di voce doganale Intrastat.</li><li>**Percentuale spese totali**</li><li>**Paese di origine** Consente di selezionare il paese predefinito in cui le merci sono state completamente ottenute o prodotto si.</li><li>**Stato/regione o provincia di origine/destinazione** Consente di selezionare lo stato predefinito/regione di destinazione per gli arrivi e il stato/regione o provincia di origine per le spedizioni.</li><li>**Peso netto in kg**</li><li>**Escludi** - Abilita questo parametro per non trasferire le transazioni con questo prodotto a Intrastat</li></ul> |
| Clienti | Paese in cui è presente l'indirizzo di consegna del cliente nella regione UE. |
| Fornitori | Paese in cui è presente l'indirizzo di consegna del cliente nella regione UE. |
| Spese varie | Impostare il codice di spese varie da includere nell'importo della fattura, l'importo statistico, o entrambi. **Codici di spese** In **Commercio estero** la pagina, nella scheda, attivare **Valore di fattura Intrastat** per includere le spese ammontano il valore di fattura e consentono **Valore statistico Intrastat** per includere le spese ammontano il valore statistico.</br>Per ulteriori informazioni, esamina l'esempio [Codici di transazione e spese varie](#transaction-codes-and-miscellaneous-charges). |
| Creazione di report elettronici | Impostare le configurazioni del report elettroniche per esportare i dati Intrastat in un file elettronico con il formato richiesto dagli uffici competenti e visualizzare l'anteprima dei dati Intrastat in formato semplice da usare e leggibile (ad esempio, in Microsoft Excel). |
| Magazzino | Associare i conti fornitore con i codici magazzino per il ricaricamento della partita IVA durante il trasferimento dell'ordine di trasferimento.</br>Per ulteriori informazioni, esamina l'esempio [Ordine di trasferimento](#transfer-order).|

## <a name="setup"></a>Impostazione
Nelle sezioni seguenti sono descritte le impostazioni necessarie per la dichiarazione Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Impostare tutti gli elenchi correlati a Intrastat richiesti

|   Elenco   |   Informazioni aggiuntive   |
|-------------------------|-------------------------|
| Codici voce doganale | Impostare una gerarchia di categorie di tipo **Codice di voce doganale** e immettere i codici di voce doganale in base all'elenco di nomenclatura combinata. Per ciascuna voce doganale è possibile definire le seguenti informazioni:<ul><li>Il nome della voce doganale e il codice della voce doganale</li><li>Il nome descrittivo e/o il nome tradotto</li><li>Impostazioni per la dichiarazione di unità aggiuntive (supplementari) nella scheda **Commercio estero**. È possibile selezionare l'unità aggiuntiva nell'elenco di unità. È inoltre possibile specificare se il peso delle voci doganali deve essere dichiarato oltre all'unità aggiuntiva selezionata.</li></ul>Per ulteriori informazioni, esamina l'esempio [Unità aggiuntive](#additional-units).|
| Codici transazioni | Imposta la natura della transazione in base ai requisiti per il paese o l'area geografica. Per ogni codice transazione impostato, è necessario impostare le regole per calcolare gli importi fattura e gli importi statistici per gli ordini di trasferimento e vendite.<ul><li>Per gli ordini di trasferimento, si imposta una delle seguenti regole per calcolare gli importi fattura e gli importi statistici:<ul><li>**Vuoto** – L'importo sarà 0 (zero).</li><li>**Importo costo finanziario** – L'importo sarà uguale al costo finanziario.</li><li>**Costo totale** – L'importo sarà uguale al costo totale della transazione.</li><li>**Manuale** – L'importo sarà uguale a quello che è specificato manualmente nella riga ordine di trasferimento.</li></ul></li><li>Per gli ordini cliente e gli ordini acquisto, si imposta una delle seguenti regole per calcolare gli importi fattura e gli importi statistici:<ul><li>**Vuoto** – L'importo sarà 0 (zero).</li><li>**Importo della fattura** – L'importo sarà uguale a quello fatturato per la voce doganale.</li><li>**Imponibile** – L'importo sarà uguale a quello che sarà fatturato prima di qualsiasi sconto applicato.</li></ul></ul>Per ulteriori informazioni, esamina l'esempio [Codici di transazione e spese varie](#transaction-codes-and-miscellaneous-charges). |
| Metodi di trasporto | Imposta la modalità di trasporto in base ai requisiti per il paese o l'area geografica. Per ciascuna modalità di consegna, è possibile impostare un metodo predefinito di trasporto nella scheda **Commercio estero**. |
| Porti | Impostare il porto/aeroporto di carico/scarico se queste informazioni vengono raccolte dal proprio paese. |
| Procedure statistiche | Impostare la procedura statistica se queste informazioni vengono raccolte dal proprio paese. |



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
<li>Valore predefinito per i codici transazione da utilizzare sugli ordini acquisto, note di credito e ordini di trasferimento. Il codice transazione impostato per le note di accredito verrà utilizzato come il codice per le merci fisiche restituite ed è utilizzato per i resi fisici di scostamento rispetto alle note di accredito della correzione. I resi di beni fisici vengono dichiarati in trasferimento Intrastat con una direzione diversa. Il reso di arrivo è dichiarato come intervento e il reso di intervento è dichiarato come arrivo.</li>
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

## <a name="example"></a>Esempio

### <a name="transaction-codes-and-miscellaneous-charges"></a><a name= "transaction-codes-and-miscellaneous-charges"></a>Codici di transazione e spese varie

Questo articolo tratta uno scenario in cui un'azienda in Germania deve acquistare beni da un'azienda in Italia. Per effettuare questo acquisto, l'azienda tedesca deve impostare nuovi codici di transazione e configurare regole di calcolo per l'importo della fattura e l'importo statistico per i codici di transazione. Inoltre, quando l'azienda crea una fattura, deve specificare le spese varie e le relative percentuali. Tali valori verranno presi in considerazione quando si calcola il valore statistico.

Questo scenario usa la persona giuridica **DEMF**.

#### <a name="preliminary-setup"></a>Impostazioni preliminari

1. Vai a **Amministrazione organizzazione** > **Organizzazione** > **Persone giuridiche** e seleziona **DEMF**.
2. Nella scheda dettaglio **Indirizzi** verifica che il campo **Paese/Area geografica** sia impostato su **DEU (Germania)**.
3. Vai a **Contabilità fornitori** > **Fornitori** > **Tutti i fornitori**.
4. Nella griglia seleziona **DE-001**.
5. Nella Scheda dettaglio **Indirizzo** seleziona **Modifica**.
6. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **ITA**.
7. Selezionare **OK** per chiudere la finestra di dialogo.

#### <a name="set-up-transaction-codes"></a>Imposta codici transazioni

1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Codici transazioni**.
2. Nella griglia seleziona **11**. Nel riquadro azioni seleziona **Elimina**.
3. Nel Riquadro azioni selezionare **Nuovo**.
4. Nella Scheda dettaglio **Codici di transazione**, nel campo **Codice** **di transazione** immetti **11**.
5. Nel campo **Nome**, immetti **Acquisto/Vendita in blocco**.
6. Nella sezione **Vendite e acquisti** nel campo **Importo fattura** seleziona **Importo fattura**.
7. Nel campo **Importo statistico** seleziona **Importo fattura**.
8. Nel riquadro azioni selezionare **Salva**.

#### <a name="set-up-miscellaneous-charges"></a>Impostare le spese varie

1. Vai a **Contabilità fornitori** > **Impostazione spese** > **Codice spese**.
2. Nella griglia seleziona **Spese di trasporto**.
3. Nel riquadro azioni, seleziona **Modifica**.
4. Nella Scheda dettaglio **Commercio estero** imposta le opzioni **Valore fattura intrastat** e **Valore statistico intrastat** su **sì**.

#### <a name="set-up-foreign-trade-parameters"></a>Imposta parametri per il commercio estero

1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
2. Nella scheda **Intrastat** nella Scheda dettaglio **Generale** nel campo **Codice** **transazione** seleziona **11**.
3. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, verifica che il campo **Gerarchia di categorie** sia impostato su **Intrastat**.

#### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai a **Contabilità fornitori** > **Ordini fornitore** > **Tutti gli ordini fornitore**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine fornitore**, nel campo **Conto fornitore** seleziona **DE-001**.
4. Selezionare **OK**.
5. Nella scheda **Intestazione**, nella Scheda dettaglio **Commercio** **estero** verifica che il campo **Codice transazione** sia impostato su **11**.
6. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine fornitore**, nel campo **Codice articolo** seleziona **D0003**. Quindi, nel campo **Quantità** immetti **10**.
7. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Commercio estero**, nella sezione **Commercio estero** assicurati che il campo **Codice di transazione** sia impostato automaticamente.
8. Nella Scheda dettaglio **Righe ordine di acquisto** nel menu **Dati finanziari** nella sezione **Spese** seleziona **Gestisci spese**.
9. Nel campo **Codice di spese** seleziona **SPESE DI TRASPORTO**.
10. Nel campo **Valore spese** immetti **30**.
11. Nel riquadro azioni selezionare **Salva**. Quindi, chiudere la pagina.
12. Nel riquadro Azioni, nella scheda **Acquisto**, nel gruppo **Azioni**, seleziona **Conferma**.
13. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
14. Nel riquadro Azioni seleziona **Predefinito da**. Nel campo **Quantità predefinita per le righe**, seleziona **Quantità ordinata**. Selezionare **OK**.
15. Nella Scheda dettaglio **Intestazione fattura fornitore**, nella sezione **Identificazione fattura**, nel campo **Numero** immetti **00100**.
16. Nella sezione **Date fatture**, nel campo **Data fattura** seleziona **24/11/2021** (24 novembre 2021).
17. Nel riquadro Azioni, seleziona **Registra** per registrare la fattura.

### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Trasferire la fattura fornitore nel giornale di registrazione Intrastat

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura fornitore** su **Sì**.
4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

   ![La riga rappresenta l'ordine fornitore con le spese varie nella pagina Intrastat](media/intrastat_overview_1.png)

5. Rivedi la scheda **Generale** per l'ordine fornitore. Tieni presente che il campo **Valore fattura** mostra la somma dei campi **Importo fattura** e **Importo spese fattura** e il campo **Valore statistico** mostra la somma dei campi **Importo statistico** e **Importo spese statistico**.

   ![Dettagli dell'ordine fornitore con le spese varie nella scheda Generale della pagina Intrastat](media/intrastat_overview_2.png)

### <a name="transfer-order"></a>Ordine di trasferimento

In questo esempio, un'azienda in Germania deve spostare due unità di merce da un magazzino in Germania a un magazzino in Italia. Le spese con un tasso del 20% devono essere specificate anche per questo prodotto per la contabilizzazione nel campo **Valore statistico**. Questo esempio usa la persona giuridica **DEMF**.

#### <a name="preliminary-setup"></a>Impostazioni preliminari

1. Vai a **Amministrazione organizzazione** > **Organizzazione** > **Persone giuridiche** e seleziona **DEMF**.
2. Nella scheda dettaglio **Indirizzi** verifica che il campo **Paese/Area geografica** sia impostato su **DEU (Germania)**.
3. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
4. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, verifica che il campo **Gerarchia di categorie** sia impostato su **Intrastat**.
5. Vai a **Contabilità fornitori** > **Fornitori** > **Tutti i fornitori**.
6. Nella griglia seleziona **DE-001**.
7. Nella Scheda dettaglio **Indirizzo** seleziona **Modifica**.
8. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **ITA**.
9. Selezionare **OK** per chiudere la finestra di dialogo.

#### <a name="set-up-transaction-codes"></a>Imposta codici transazioni

1. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Codici transazioni**.
2. Nella griglia seleziona **11**. Nel riquadro azioni seleziona **Elimina**.
3. Nel Riquadro azioni selezionare **Nuovo**.
4. Nella Scheda dettaglio **Codici di transazione**, nel campo **Codice** **di transazione** immetti **11**.
5. Nel campo **Nome**, immetti **Acquisto/Vendita in blocco**.
6. Nella sezione **Ordine di trasferimento** nel campo **Importo fattura** seleziona **Costo totale**.
7. Nel campo **Importo statistico** seleziona **Costo totale**.
8. Nel riquadro azioni selezionare **Salva**.
9. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
10. Nella scheda **Intrastat** nella scheda dettaglio **Generale** nel campo **Ordine di trasferimento** seleziona **11**.

#### <a name="set-up-charges-for-an-item"></a>Impostare le spese per un articolo

1. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
2. Nella griglia seleziona **D0001**.
3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Percentuale spese** immetti **20**.

#### <a name="change-the-site-address"></a>Modificare l'indirizzo del sito

1. Vai a **Gestione magazzino** > **Impostazione** > **Magazzino** > **Siti**.
2. Nella griglia seleziona **1**.
3. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
4. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **DEU**.
5. Seleziona **OK**.
6. Nella griglia seleziona **2**.
7. Nella Scheda dettaglio **Indirizzi** seleziona **Modifica**.
8. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **ITA**.
9. Seleziona **OK**.
10. Vai a **Gestione magazzino** > **Impostazioni** > **Magazzino** > **Magazzini**.
11. Nella griglia seleziona **21**.
12. Nella Scheda dettaglio **Generale**, nella sezione **Riferimento**, nel campo **Conto fornitore**, seleziona **DE-001**.

#### <a name="create-a-transfer-order"></a>Creare un ordine di trasferimento

1. Vai a **Gestione inventario** > **Ordini in uscita** > **Ordine di trasferimento**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella scheda **Righe** nella scheda dettaglio **Intestazione ordine di trasferimento** nella sezione **Panoramica** nel campo **Da magazzino** seleziona **11**. Nel campo **A magazzino** seleziona **21**.
4. Nella scheda **Righe** nella scheda dettaglio **Righe ordine di trasferimento** seleziona **Aggiungi**.
5. Nel campo **Numero articolo** selezionare **D0001**. Quindi, nel campo **Quantità trasferimento** immetti **2**.
6. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Commercio estero**, nella sezione **Commercio estero** assicurati che il campo **Codice di transazione** sia impostato automaticamente.
7. Nel riquadro azioni, nella scheda **Spedizione**, nel gruppo **Operazioni** seleziona **Ordine di trasferimento spedizione**.
8. Nella finestra di dialogo **Spedizione** nella scheda **Panoramica** nel campo **Aggiorna** seleziona **Tutto**.
9. Seleziona **OK** per spedire l'ordine.
10. Nel riquadro azioni, nella scheda **Ricevi**, nel gruppo **Operazioni**, seleziona **Ricevi**.
11. Nella finestra di dialogo **Ricevi** nella scheda **Panoramica** nel campo **Aggiorna** seleziona **Tutto**.
12. Seleziona **OK** per spedire l'ordine.

#### <a name="transfer-the-transfer-order-to-the-intrastat-journal"></a>Trasferire l'ordine di trasferimento nel giornale di registrazione Intrastat

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)** imposta l'opzione **Ordine di trasferimento** su **sì** e tutte le altre opzioni su **No**.
4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

   ![La riga rappresenta l'ordine di trasferimento nella pagina Intrastat](media/intrastat_overview_3.png)

5.  Rivedi la scheda **Generale** per l'ordine di trasferimento.

    Tieni presente che i campi nelle sezioni **Valore fattura** e **Valore statistico** vengono impostati automaticamente. I valori dei campi **Importo fattura** e **Importo statistico** si basano sulle impostazioni della pagina **Codici di transazione**. Il valore **20** nel campo **Percentuale spese** è il valore impostato nella pagina **Prodotto rilasciato**. Il valore nel campo **Importo spese statistico** è un'espressione quantitativa delle spese (perché 107,24 equivale al 20 percento di 536,18). Il valore del campo **Valore statistico** è la somma dei valori dei campi **Importo statistico** e **Importo spese statistico**.

  ![Dettagli dell'ordine di trasferimento nella scheda Generale della pagina Intrastat](media/intrastat_overview_4.png)

### <a name="additional-units"></a>Unità supplementari

In questo esempio, un'azienda in Germania deve acquistare 10 unità di merce da un'azienda in Italia. Oltre ai codici di voce doganale, per tali merci devono essere specificate unità aggiuntive. L'esempio mostra come creare nuove unità di misura, assegnare unità aggiuntive al codice di voce doganale Intrastat, registrare le transazioni con unità aggiuntive ed esaminare il giornale di registrazione Intrastat in cui è impostato il campo per le unità aggiuntive.

#### <a name="preliminary-setup"></a>Impostazioni preliminari

1. Vai a **Amministrazione organizzazione** > **Organizzazione** > **Persone giuridiche** e seleziona **DEMF**.
2. Nella scheda dettaglio **Indirizzi** verifica che il campo **Paese/Area geografica** sia impostato su **DEU (Germania)**.
3. Seleziona **Imposta** > **Impostazione** > **Commercio estero** > **Parametri per il commercio estero**.
4. Nella scheda **Intrastat** nella Scheda dettaglio **Generale** nel campo **Codice** **transazione** seleziona **11**.
5. Nella scheda dettaglio **Gerarchia di codici di voce doganale**, verifica che il campo **Gerarchia di categorie** sia impostato su **Intrastat**.
6. Vai a **Contabilità fornitori** > **Fornitori** > **Tutti i fornitori**.
7. Nella griglia seleziona **DE-001**.
8. Nella Scheda dettaglio **Indirizzo** seleziona **Modifica**.
9. Nella finestra di dialogo **Modifica indirizzo**, nel campo **Paese/area geografica**, seleziona **ITA**.
10. Selezionare **OK** per chiudere la finestra di dialogo.

#### <a name="create-a-unit-of-measure"></a>Creare un'unità di misura

1. Vai a **Amministrazione organizzazione** > **Impostazione** > **Unità** > **Unità**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Unità** immetti un nome per l'unità di misura. Per questo esempio, immetti **GRM**.
4. Nella scheda dettaglio **Generale** nella sezione **Classificazione** nel campo **Classe di unità** seleziona la proprietà misurata dall'unità. Per questo esempio, seleziona **Massa**.
5. Nel campo **Sistema di misurazione** seleziona il sistema di misurazione a cui appartiene l'unità. Ad esempio, seleziona **Unità sistema metrico decimale**.

#### <a name="set-up-unit-conversions"></a>Configurare le conversioni di unità

1. Vai a **Amministrazione organizzazione** > **Impostazione** > **Unità** > **Conversioni di unità**.
2. Nella scheda **Conversioni tra classi** seleziona **Nuovo**.
3. Nella finestra di dialogo **Conversione unità**, nel campo **Prodotto** seleziona **F00007**.
4. Nel campo **Da unità** selezioa **ea**.
5. Nel campo **A unità** seleziona **GRM**.
6. Verifica che il tasso di conversione sia **1 = 1**.
7. Seleziona **OK**.
8. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
9. Nella griglia seleziona **F00007**.
10. Nella Scheda dettaglio **Gestione articoli** nella sezione **Inventario** nel campo **Unità** seleziona **GRM**.
11. Nel riquadro azioni selezionare **Salva**.

#### <a name="set-up-product-information"></a>Impostare le informazioni prodotto

1. Seleziona **Gestione informazioni sul prodotto** > **Prodotti** > **Prodotti rilasciati**.
2. Nella griglia seleziona **F00007**.
3. Nella Scheda dettaglio **Commercio estero** nella sezione **Intrastat** nel campo **Voce doganale** seleziona **920 20 34**.
4. Nel riquadro azioni selezionare **Salva**.

#### <a name="assign-the-additional-unit-to-an-intrastate-commodity-code"></a>Assegnare l'unità aggiuntiva a un codice di voce doganale intrastat

1. Vai a **Gestione informazioni sul prodotto** > **Impostazioni** > **Categorie e attributi** > **Gerarchie di categorie**.
2. Nell'elenco seleziona **Intrastat**.
3. Nella griglia seleziona **Altoparlante**.
4. Nella Scheda dettaglio **Commercio estero** nel campo **Unità aggiuntive**, seleziona **GRM**.
5. Nel riquadro azioni selezionare **Salva**.

   Per ulteriori informazioni, vedi [Gestire le unità di misura](../../supply-chain/pim/tasks/manage-unit-measure.md).

#### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai a **Contabilità fornitori** > **Ordini fornitore** > **Tutti gli ordini fornitore**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea ordine fornitore**, nel campo **Conto fornitore** seleziona **DE-001**.
4. Selezionare **OK**.
5. Nella scheda **Intestazione**, nella Scheda dettaglio **Commercio** **estero** verifica che il campo **Codice transazione** sia impostato su **11**.
6. Nella scheda **Righe**, nella Scheda dettaglio **Righe ordine fornitore**, nel campo **Codice articolo** seleziona **F00007**. Quindi, nel campo **Quantità** immetti **10**.
7. Nella Scheda dettaglio **Dettagli riga**, nella scheda **Commercio estero**, nella sezione **Commercio estero** assicurati che i campi **Codice di transazione** e **Voce doganale** siano impostati automaticamente.
8. Nel riquadro Azioni, nella scheda **Acquisto**, nel gruppo **Azioni**, seleziona **Conferma**.
9. Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.
10. Nel riquadro Azioni seleziona **Predefinito da**. Nel campo **Quantità predefinita per le righe**, seleziona **Quantità ordinata**. Selezionare **OK**.
11. Nella Scheda dettaglio **Intestazione fattura fornitore**, nella sezione **Identificazione fattura**, nel campo **Numero** immetti **VE-0010**.
12. Nella sezione **Date fatture**, nel campo **Data fattura** seleziona **5/10/2021** (5 ottobre 2021).
13. Nel riquadro Azioni, seleziona **Registra** per registrare la fattura.

#### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Trasferire la fattura fornitore nel giornale di registrazione Intrastat

1. Seleziona **Imposta** > **Dichiarazioni** > **Commercio estero** > **Intrastat**.
2. Nel riquadro azioni seleziona **Trasferisci**.
3. Nella finestra di dialogo **Intrastat (trasferimento)**, imposta l'opzione **Fattura fornitore** su **Sì**.
4. Seleziona **OK** per trasferire le transazioni, quindi esamina il giornale di registrazione Intrastat.

   ![La riga rappresenta l'ordine fornitore nella pagina Intrastat](media/intrastat_overview_5.png)

5. Rivedi la scheda **Generale** per l'ordine fornitore. Tieni presente che i campi **Quantità di unità aggiuntive** e **Unità aggiuntiva** nella sezione **Unità** vengono impostati automaticamente.

   ![Dettagli dell'ordine fornitore nella scheda Generale della pagina Intrastat](media/intrastat_overview_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
