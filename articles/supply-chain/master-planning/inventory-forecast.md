---
title: Previsioni di magazzino
description: Questo argomento descrive la funzionalità di previsione della domanda e dell'offerta che può essere utilizzata per creare previsioni di magazzino in Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1446928c2f5fe606d1d0732764a2a4460643afcf
ms.sourcegitcommit: 4c8223c9540fbc1c1e554962938058d432e4c681
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2022
ms.locfileid: "8548169"
---
# <a name="inventory-forecasts"></a>Previsioni di magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come visualizzare e creare previsioni di magazzino. Puoi creare e visualizzare righe di previsione della domanda e dell'offerta per articoli, gruppi di articoli, chiavi di allocazione articolo, account cliente, gruppi di clienti, account fornitore e gruppi di fornitori.

Per ogni riga di previsione puoi selezionare il modello di previsione utilizzato. Puoi quindi specificare l'articolo o il gruppo di articoli, più la quantità o l'importo della transazione. Puoi anche impostare una programmazione temporale per la quantità prevista.

Le righe di previsione della domanda e dell'offerta producono una previsione di magazzino per la stessa combinazione di un articolo e un modello. Questa previsione di magazzino rappresenta un punto di equilibrio tra la domanda e l'offerta immesse per lo stesso articolo. Questo valore non può essere modificato. La previsione di magazzino aiuta il team di gestione dell'inventario a rivedere le modifiche previste all'inventario disponibile di un articolo durante il successivo periodo oggetto di previsione.

Dopo aver immesso la domanda e/o l'offerta, puoi eseguire una pianificazione previsionale per calcolare i fabbisogni lordi di materiali e la capacità, nonché generare gli ordini pianificati.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Visualizzare e immettere manualmente le righe della previsione

Utilizza questa procedura per creare manualmente righe di previsione per i prodotti.

Esistono anche altri modi per creare righe di previsione:

- [Generare una previsione di base statistica](generate-statistical-baseline-forecast.md).
- [Importare i dati storici per le previsioni della domanda](import-historical-data.md).
- [Generare la previsione usando un servizio Web Learning Machine di Microsoft Azure](demand-forecasting-setup.md).
- [Importare righe di previsione della domanda e dell'offerta usando il framework di gestione dei dati (entità di dati ForecastDemandForecastEntryStaging e ForecastSupplyForecastEntryStaging)](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).

Come mostra la tabella al passaggio 1, esistono diversi modi per accedere alle pagine utilizzate.

1. A seconda del tipo di entità per cui vuoi creare una previsione e del tipo di previsione da creare, apri una pagina di previsione dell'offerta, della domanda o del magazzino come descritto nella tabella seguente.

    | Entità | Istruzioni |
    |---|---|
    | Prodotti rilasciati | <ol><li>Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</li><li>Seleziona il prodotto per cui creare una previsione.</li><li>Nella scheda **Piano** del riquadro delle azioni, gruppo **Previsione**, seleziona **Previsione della domanda**, **Previsione dell'offerta** o **Previsione di magazzino**, a seconda del tipo di previsione da usare.</li></ol> |
    | Varianti prodotti rilasciati | <ol><li>Vai a **Gestione informazioni sul prodotto \> Prodotti \> Varianti prodotti rilasciati**.</li><li>Seleziona la variante per cui creare una previsione.</li><li>Nella scheda **Piano** del riquadro delle azioni, gruppo **Previsione**, seleziona **Previsione della domanda**, **Previsione dell'offerta** o **Previsione di magazzino**, a seconda del tipo di previsione da usare.</li></ol> |
    | Gruppi di articoli | <ol><li>Vai a **Gestione inventario \> Imposta \> Inventario \> Gruppi di articoli**.</li><li>Seleziona il gruppo di articoli per cui creare una previsione.</li><li>Nel riquadro delle azioni, seleziona **Previsione \> Domanda**, **Previsione \> Offerta** o **Previsione \> Previsione di magazzino**, a seconda del tipo di previsione da usare.</li></ol> |
    | Chiavi di allocazione articoli | <ol><li>Vai a **Gestione inventario \> Impostazione \> Previsione**.</li><li>Seleziona la chiave di allocazione dell'articolo per cui creare una previsione.</li><li>Nel riquadro delle azioni, seleziona **Previsione della domanda**.</li></ol> |
    | Clienti | <ol><li>Vai a **Pianificazione generale \> Previsioni \> Voce di previsione manuale \> Clienti**.</li><li>Seleziona il cliente per cui creare una previsione.</li><li>Nel riquadro delle azioni, seleziona **Definisci previsione della domanda**.</li></ol> |
    | Gruppi di clienti | <ol><li>Vai a **Pianificazione generale \> Previsioni \> Voce di previsione manuale \> Gruppi di clienti**.</li><li>Seleziona il gruppo di clienti per cui creare una previsione.</li><li>Nel riquadro delle azioni, seleziona **Definisci previsione della domanda**.</li></ol> |
    | Fornitori | <ol><li>Vai a **Pianificazione generale \> Previsioni \> Voce di previsione manuale \> Fornitori**.</li><li>Seleziona il fornitore per cui creare una previsione.</li><li>Nel riquadro delle azioni, seleziona **Voce** per aprire la pagina **Previsione dell'offerta**.</li></ol> |
    | Gruppi di fornitori | <ol><li>Vai a **Pianificazione generale \> Previsioni \> Voce di previsione manuale \> Gruppi di fornitori**.</li><li>Seleziona il gruppo di fornitori per cui creare una previsione.</li><li>Nel riquadro delle azioni, seleziona **Voce** per aprire la pagina **Previsione dell'offerta**.</li></ol> | 
    | Tutte le righe | <ul><li>Vai a **Pianificazione generale \> Previsione \> Righe di previsione della domanda** oppure a **Pianificazione generale \> Previsione \> Righe di previsione dell'offerta**, in base al tipo di previsione da usare.</li></ul> |

    A seconda della selezione, viene visualizzata la pagina **Previsione della domanda** o **Previsione dell'offerta**. Mostra tutte le righe di previsione esistenti per il record selezionato prima di aprire la pagina.

1. Nel riquadro delle azioni, seleziona **Nuovo** per aggiungere una riga di previsione alla griglia nella parte superiore della pagina.
1. Sulla nuova riga, nel campo **Modello**, seleziona il modello di previsione da utilizzare. Immetti quindi gli altri dettagli in base alle tue esigenze, ad esempio l'articolo, il gruppo di articoli, l'account o il gruppo di clienti o fornitori, la quantità dell'articolo o l'importo totale della transazione. Per i dettagli completi sui campi disponibili nelle pagine **Previsione dell'offerta** e **Previsione della domanda**, vedi le sezioni successive in questo argomento.
1. Per distribuire la previsione nel periodo, nella scheda **Panoramica** seleziona **Alloca previsioni** sulla barra degli strumenti.
1. Nella griglia **Allocazione**, rivedi l'orizzonte e gli intervalli temporali usati per distribuire le quantità previste.

## <a name="supply-forecast-lines"></a>Righe previsione dell'offerta

La previsione dell'offerta consente di creare un piano per gli articoli che devono essere acquistati. Indica agli addetti all'approvvigionamento cosa devono ordinare.

Puoi immettere una previsione dell'offerta per articolo, gruppo di articoli, chiave di allocazione articolo, fornitore e gruppo di fornitori. Per informazioni sulle varie modalità di apertura della pagina **Previsione dell'offerta** per le varie entità e record, vedi la sezione [Visualizzare e immettere manualmente righe di previsione](#manual-entry) in questo argomento.

Nella parte superiore della pagina **Previsione dell'offerta** è disponibile una griglia di righe della previsione dell'offerta e una serie di tabelle che possono essere usate per visualizzare e impostare altre informazioni sulla riga della previsione selezionata. La parte inferiore della pagina fornisce una griglia **Allocazione**.

Le seguenti sottosezioni descrivono tutti i campi disponibili in ciascuna scheda e tutti i comandi disponibili nel riquadro della azioni della pagina e nella barra degli strumenti della scheda **Panoramica**.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>I comandi del riquadro delle azioni nella pagina Previsione dell'offerta

Nella seguente tabella sono descritti i comandi disponibili nel riquadro delle azioni della pagina **Previsione dell'offerta**.

| Comandi | Descrizione |
|---|---|
| Salva | Salva le tue impostazioni correnti. |
| Modifica | Abilita le impostazioni della pagina da modificare. |
| Nuove | Aggiunge una riga di previsione alla griglia superiore. |
| CANC | Rimuove la linea di previsione selezionata dalla griglia superiore. |
| Saldi previsionali | Visualizza i saldi di previsione che sono stati calcolati per l'ID modello della riga selezionata per l'anno fiscale corrente. I saldi sono suddivisi per periodo (mese). |
| Previsioni di cassa | Visualizza le transazioni previsionali che sono state allocate alla contabilità generale. Per ulteriori informazioni, vedi [Previsione di cassa](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Magazzino \> Visualizza dimensioni | Seleziona le dimensioni dell'inventario che devono essere mostrate nella griglia nella scheda **Panoramica**. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>Comandi della barra degli strumenti nella scheda Panoramica nella pagina Previsione dell'offerta

Nella seguente tabella sono descritti i comandi disponibili nella barra degli strumenti, nella scheda **Panoramica** della pagina **Previsione dell'offerta**.

| Comandi | descrizione |
|---|---|
| Alloca previsioni | Se stai utilizzando un metodo di allocazione, genera le singole righe di pianificazione per la transazione previsionale. La quantità della riga viene quindi distribuita per data (in base agli intervalli di tempo selezionati), alla quantità e all'importo per l'intero orizzonte temporale. (Vedere la sezione [Alloca previsioni](#allocate-forecast) di seguito in questo argomento.) |
| Aggiornamento in blocco | Apri la pagina **Modifica transazioni previsionali**. (Vedi la sezione [Aggiornamento in blocco delle transazioni previsionali](#bulk-update) in questo argomento.) |
| Previsione di magazzino | Apri una vita della pagina **Previsione di magazzino** filtrata per la combinazione di articolo/modello selezionata. (Vedi la sezione [Previsione di magazzino](#inventory-forecast) in questo argomento.) |
| Crea richiesta articolo | Apri una finestra di dialogo in cui creare richieste di articoli e righe di ordini cliente o del giornale di registrazione degli articoli per le transazioni previsionali relative al progetto. Sebbene questo comando sia disponibile sia per le righe di previsione dell'offerta che per le righe di previsione della domanda, non può essere usato nella pagina **Previsione dell'offerta**. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>La scheda Panoramica nella pagina Previsione dell'offerta

La tabella seguente descrive i campi della scheda **Panoramica** della pagina **Previsione dell'offerta**.

| Campo | descrizione |
|---|---|
| **Modello** | Modello previsionale a cui è associata la transazione. |
| **Data** | Data di inizio della transazione. |
| **Account fornitore** | Account del fornitore associato alla transazione. |
| **Gruppo di fornitori** | Gruppo di fornitori associato alla transazione. |
| **Numero articolo** | Identificatore dell'articolo. |
| **Gruppo di articoli** | Gruppo di articoli al quale è associata la transazione. |
| **Chiave di allocazione articolo** | Chiave di allocazione dell'articolo associata alla previsione. |
| **Quantità a peso variabile** | La quantità prevista nell'unità a peso variabile specificata. |
| **Unità a peso variabile** | Unità di misura a peso variabile utilizzata per l'acquisto dell'articolo. Il valore viene recuperato automaticamente dall'impostazione dell'articolo. |
| **Quantità** | Quantità prevista nell'unità di acquisto specificata. |
| **Unità** | L'unità utilizzata per l'acquisto dell'articolo. Il valore viene recuperato automaticamente dall'impostazione dell'articolo. Può comunque essere modificato se sono impostate le conversioni di unità. |
| **Importo** | Importo lordo, meno gli sconti, con cui la transazione previsionale contribuisce alla previsione. |
| **Valuta** | Valuta utilizzata per la transazione previsionale. La valuta predefinita viene inserita automaticamente, ma è possibile selezionare un'altra valuta. |
| (Altre dimensioni) | Ulteriori dimensioni possono essere visualizzate come colonne nella griglia. Per selezionare le dimensioni aggiuntive visualizzate, seleziona **Visualizza dimensioni** nel riquadro delle azioni. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>La scheda Generale nella pagina Previsione dell'offerta

La scheda **Generale** mostra una quantità maggiore di informazioni sulla riga attualmente selezionata nella scheda **Panoramica**. Alcune delle informazioni sono ripetute dalla scheda **Panoramica**. La tabella seguente descrive i campi univoci per la scheda **Generale**.

| Campo | descrizione |
|---|---|
| Report | Imposta questa opzione su *Sì* per includere la transazione nella dichiarazione. |
| Commenti | Permette di aggiungere eventuali commenti sulla transazione previsionale. |
| Attive | Seleziona questa casella di controllo per includere la transazione nella dichiarazione budget. |
| Includi in previsioni di cassa | Seleziona questa casella di controllo per allocare la transazione previsionale alla contabilità generale. L'impostazione di questa casella di controllo non può essere modificata per le transazioni di dichiarazione. |
| Fascia IVA | Fascia IVA utilizzata per specificare l'IVA per la transazione previsionale. |
| Fascia IVA articoli | Fascia IVA articoli utilizzata per specificare l'IVA per la transazione previsionale. |
| Metodo | <p>Seleziona il metodo utilizzato per allocare la transazione previsionale:</p><ul><li>**Nessuna**: non viene eseguita alcuna allocazione.</li><li>**Periodo**: è prevista la stessa quantità per ogni periodo. Se selezioni questo valore, specifica una quantità nel campo **Per** e un'unità di tempo nel campo **Unità**.</li><li>**Chiave**: la previsione viene allocata in base alla chiave di allocazione per periodo specificata nel campo **Chiave periodo**. Puoi utilizzare questo metodo se intendi prendere in considerazione la variazione stagionale.</li></ol>|
| Per | <p>Consente di immettere il numero di intervalli di tempo futuri relativi alla durata della previsione. Questo campo è disponibile solo se nel campo **Metodo** hai selezionato *Periodo*.</p><p>Ad esempio, se selezioni *Periodo* nel campo **Metodo**, immetti *1* nel campo **Per**, quindi seleziona *Mesi* nel campo **Unità**. Nel campo **Fine**, specifica una data di fine che copra un intero anno. In questo caso, verrà creata una riga di previsione per ciascun mese dell'anno successivo, in base all'articolo e alla quantità specificati nella riga di intestazione.</p> |
| Unità | Seleziona l'unità dell'intervallo temporale: *Giorni*, *Mesi* o *Anni*. L'allocazione corrisponderà al numero di giorni, mesi o anni specificato nel campo **Per**.|
| Chiave periodo | Permette di specificare la chiave di allocazione per periodo. |
| Fine periodo | Consente di specificare la data di fine quando usi i campi **Per** e **Unità**. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>La scheda Articolo nella pagina Previsione dell'offerta

La scheda **Articolo** mostra ulteriori informazioni sulla riga attualmente selezionata nella scheda **Panoramica**.

La griglia nella parte superiore della scheda **Articolo** ripete informazioni sull'articolo mostrate anche nella scheda **Panoramica**. Inoltre, include il campo **Prezzo unitario**, che mostra il prezzo di acquisto per il numero di unità specificato nel campo **Unità**. Il prezzo unitario viene automaticamente recuperato dall'impostazione dell'articolo, ma può essere modificato.

I campi sotto la griglia forniscono ulteriori dettagli sugli articoli. Alcune di queste informazioni sono ripetute dalla scheda **Panoramica**. La tabella seguente descrive i campi che sono univoci per la scheda **Articolo**.

| Campo | descrizione |
|---|---|
| Unità di prezzo | Il numero di unità a cui si applica il prezzo di acquisto. Il valore viene recuperato automaticamente dalla tabella Articoli, ma può essere modificato. |
| Spese su acquisti | Spese fisse sul prezzo di acquisto. Le spese sono indipendenti dalla quantità. |
| Percentuale sconto | Sconto espresso in percentuale. |
| Importo sconto | Sconto espresso come importo per unità di vendita. |
| Importo lordo | L'importo senza alcuno sconto applicato. |
| Quantità | La quantità della transazione espressa nell'unità di magazzino dell'articolo. |
| Distinta base secondaria | Numero di una DBA secondaria specifica. |
| Percorso secondario | Numero di un ciclo di lavorazione secondario specifico. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>La scheda Dimensioni finanziarie nella pagina Previsione dell'offerta

La scheda **Dimensioni finanziarie** mostra tutti i valori della dimensione finanziaria per la riga attualmente selezionata nella scheda **Panoramica**.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>La scheda Dimensioni inventariali nella pagina Previsione dell'offerta

La scheda **Dimensioni inventariali** mostra tutti i valori della dimensione inventariale per la riga attualmente selezionata nella scheda **Panoramica**.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>La griglia Allocazione nella pagina Previsione dell'offerta

Se stai utilizzando una chiave di allocazione articolo o se hai inserito una previsione dell'articolo per uno o più periodi futuri, puoi allocare la previsione selezionando **Assegna previsione** sulla barra degli strumenti nella scheda **Panoramica**. La quantità viene quindi distribuita secondo le modalità indicate dalle righe nella griglia **Allocazione**.

## <a name="demand-forecast-lines"></a>Righe di previsione della domanda

La previsione della domanda consente di immettere o generare la domanda per un cliente. Aiuta gli addetti alle vendite e al marketing a informare gli addetti alla pianificazione generale in merito alla domanda prevista durante il prossimo periodo di previsione.

Puoi immettere una previsione della domanda per articolo, gruppo di articoli, chiave di allocazione articolo, cliente e gruppo di cliente. Per informazioni sulle varie modalità di apertura della pagina **Previsione della domanda** per le varie entità e record, vedi la sezione [Visualizzare e immettere manualmente righe di previsione](#manual-entry) in questo argomento.

Nella parte superiore della pagina **Previsione della domanda** è disponibile una griglia di righe della previsione della domanda e una serie di tabelle che possono essere usate per visualizzare e impostare altre informazioni sulla riga della previsione selezionata. La parte inferiore della pagina fornisce una griglia **Allocazione**.

Le seguenti sottosezioni descrivono tutti i campi disponibili in ciascuna scheda e tutti i comandi disponibili nel riquadro della azioni della pagina e nella barra degli strumenti della scheda **Panoramica**.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>I comandi del riquadro delle azioni nella pagina Previsione della domanda

Nella seguente tabella sono descritti i comandi disponibili nel riquadro delle azioni della pagina **Previsione della domanda**.

| Comandi | descrizione |
|---|---|
| Salva | Salva le tue impostazioni correnti. |
| Modifica | Abilita le impostazioni della pagina da modificare. |
| Nuove | Aggiunge una riga di previsione alla griglia superiore. |
| CANC | Rimuove la linea di previsione selezionata dalla griglia superiore. |
| Saldi previsionali | Visualizza i saldi di previsione che sono stati calcolati per l'ID modello della riga selezionata per l'anno fiscale corrente. I saldi sono suddivisi per periodo (mese). |
| Previsione di cassa | Visualizza le transazioni previsionali che devono essere allocate alla contabilità generale. Per ulteriori informazioni, vedi [Previsione di cassa](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Visualizza dimensioni | Seleziona il prodotto, lo spazio di archiviazione e le dimensioni di tracciabilità che dovrebbero essere mostrate nella griglia nella scheda **Panoramica**. |
| Anteprima Contabilità generale | Visualizza le voci di contabilità generale relative alla transazione selezionata. |
| Trasferisci righe offerta | Trasferisce le righe dell'offerta nel progetto selezionato. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Comandi della barra degli strumenti nella scheda Panoramica nella pagina Previsione della domanda

Nella seguente tabella sono descritti i comandi disponibili nella barra degli strumenti, nella scheda **Panoramica** della pagina **Previsione della domanda**.

| Comandi | descrizione |
|---|---|
| Alloca previsioni | Se stai utilizzando un metodo di allocazione, genera le singole righe di pianificazione per la transazione previsionale. La quantità della riga viene quindi distribuita per data (in base agli intervalli di tempo selezionati), alla quantità e all'importo per l'intero orizzonte temporale. (Vedere la sezione [Alloca previsioni](#allocate-forecast) di seguito in questo argomento.)|
| Aggiornamento in blocco | Apri la pagina **Modifica transazioni previsionali**. (Vedi la sezione [Aggiornamento in blocco delle transazioni previsionali](#bulk-update) in questo argomento.) |
| Previsione di magazzino | Apri una vita della pagina **Previsione di magazzino** filtrata per la combinazione di articolo/modello selezionata. (Vedi la sezione [Previsione di magazzino](#inventory-forecast) in questo argomento.) |
| Crea richiesta articolo | Apri una finestra di dialogo in cui creare richieste di articoli e righe di ordini cliente o del giornale di registrazione degli articoli per le transazioni previsionali relative al progetto. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>La scheda Panoramica nella pagina Previsione della domanda

La tabella seguente descrive i campi della scheda **Panoramica** della pagina **Previsione della domanda**.

| Campo | descrizione |
|---|---|
| **Nome attività** | Il nome dell'attività batch utilizzata per creare la riga della previsione. |
| **Modello** | Modello previsionale a cui è associata la transazione. |
| **Data** | Data di inizio della transazione. |
| **Account cliente** | L'account del cliente associato alla transazione. |
| **Gruppo di clienti** | Il gruppo di clienti associato alla transazione. |
| **Numero articolo** | Identificatore dell'articolo. |
| **Nome prodotto** | Descrizione dell'articolo. |
| **Chiave di allocazione articolo** | La chiave di allocazione dell'articolo utilizzata per l'allocazione della previsione di magazzino. |
| **Quantità di vendita** | La quantità prevista nell'unità di vendita specificata. |
| **Unità** | Unità in cui viene venduto l'articolo. |
| **Importo** | Importo lordo, esclusi gli sconti, con cui la transazione previsionale contribuisce alla previsione. |
| **Prezzo di vendita** | Il prezzo di vendita per il numero di unità specificato nel campo **Prezzo unitario**. Questo valore viene recuperato automaticamente dall'impostazione dell'articolo, ma può essere modificato. |
| **Valuta di vendita** | Valuta utilizzata per la transazione previsionale. La valuta predefinita viene inserita automaticamente, ma è possibile selezionare un'altra valuta. |
| **Quantità a peso variabile** | La quantità prevista nell'unità a peso variabile specificata. |
| **Unità a peso variabile** | Unità di misura a peso variabile utilizzata per la vendita dell'articolo. Il valore viene recuperato automaticamente dall'impostazione dell'articolo. |
| (Altre dimensioni) | Ulteriori dimensioni di prodotto, spazio di archiviazione e tracciabilità possono essere visualizzate come colonne nella griglia. Per selezionare le dimensioni aggiuntive visualizzate, seleziona **Visualizza dimensioni** nel riquadro delle azioni. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>La scheda Generale nella pagina Previsione della domanda

La scheda **Generale** mostra una quantità maggiore di informazioni sulla riga attualmente selezionata nella scheda **Panoramica**. Alcune delle informazioni sono ripetute dalla scheda **Panoramica**. La tabella seguente descrive i campi univoci per la scheda **Generale**.

| Campo | descrizione |
|---|---|
| Numero progressivo previsioni della domanda | Il numero univoco della riga di previsione della domanda. Questo numero viene generato utilizzando la sequenza numerica selezionata per le previsioni della domanda nella pagina **Parametri di pianificazione generale**. |
| Gruppo di articoli | Gruppo di articoli al quale è associata la transazione. |
| Report | Imposta questa opzione su *Sì* per includere la transazione nella dichiarazione. |
| Commenti | Permette di aggiungere eventuali commenti sulla transazione previsionale. |
| Attive | Seleziona questa casella di controllo per includere la transazione nella dichiarazione budget. L'impostazione di questa casella di controllo non può essere modificata per le transazioni di dichiarazione. |
| Includi in previsioni di cassa | Seleziona questa casella di controllo per allocare la transazione previsionale alla contabilità generale. L'impostazione di questa casella di controllo non può essere modificata per le transazioni di dichiarazione. Per ulteriori informazioni, vedi [Previsione di cassa](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Fascia IVA | Fascia IVA utilizzata per specificare l'IVA per la transazione previsionale. |
| Fascia IVA articoli | Fascia IVA articoli utilizzata per specificare l'IVA per la transazione previsionale. |
| Metodo | <p>Seleziona il metodo utilizzato per allocare la transazione previsionale:</p><ul><li>**Nessuna**: non viene eseguita alcuna allocazione.</li><li>**Periodo**: è prevista la stessa quantità per ogni periodo. Se selezioni questo valore, specifica una quantità nel campo **Per** e un'unità di tempo nel campo **Unità**.</li><li>**Chiave**: la previsione viene allocata in base alla chiave di allocazione per periodo specificata nel campo **Chiave periodo**. Puoi utilizzare questo metodo se intendi prendere in considerazione la variazione stagionale.</li><ul>|
| Per | <p>Consente di immettere il numero di intervalli di tempo futuri relativi alla durata della previsione. Questo campo è disponibile solo se nel campo **Metodo** hai selezionato *Periodo*.</p><p>Ad esempio, se selezioni *Periodo* nel campo **Metodo**, immetti *1* nel campo **Per**, quindi seleziona *Mesi* nel campo **Unità**. Nel campo **Fine**, specifica una data di fine che copra un intero anno. In questo caso, verrà creata una riga di previsione per ciascun mese dell'anno successivo, in base all'articolo e alla quantità specificati nella riga di intestazione. |
| Unità | Seleziona l'unità dell'intervallo temporale: *Giorni*, *Mesi* o *Anni*. L'allocazione corrisponderà al numero di giorni, mesi o anni specificato nel campo **Per**.|
| Chiave periodo | Permette di specificare la chiave di allocazione del periodo utilizzata per allocare la previsione. Per ulteriori informazioni, vedi [Allocazione dei dati di pianificazione del budget](../../finance/budgeting/budget-planning-data-allocation.md). |
| Fine periodo | Consente di specificare la data di fine quando usi i campi **Per** e **Unità**. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>La scheda Articolo nella pagina Previsione della domanda

La scheda **Articolo** mostra una quantità maggiore di informazioni per l'articolo sulla riga attualmente selezionata nella scheda **Panoramica**. Alcune delle informazioni sono ripetute dalla scheda **Panoramica**. La tabella seguente descrive i campi univoci per la scheda **Articolo**.

| Campo | descrizione |
|---|---|
| Unità di prezzo | Numero di unità di vendita a cui viene applicato il prezzo di vendita. Il valore viene recuperato automaticamente dalla tabella Articoli, ma può essere modificato. |
| Spese vendite | Spese fisse sul prezzo di vendita. Le spese sono indipendenti dalla quantità. |
| Prezzo di costo | Costo della transazione previsionale corrente per unità di magazzino. Il valore viene recuperato dalla tabella Articoli, ma è possibile modificarlo. |
| Percentuale sconto | Sconto espresso in percentuale. |
| Importo sconto | Sconto espresso come importo per unità di vendita. |
| Importo lordo | L'importo senza alcuno sconto applicato. |
| Quantità in magazzino | La quantità della transazione espressa nell'unità di magazzino dell'articolo. |
| Utilizza DBA specifica | Numero di una DBA specifica. |
| Utilizza ciclo di lavorazione specifico | Numero di un ciclo di lavorazione secondario specifico. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>La scheda Progetto nella pagina Previsione della domanda

La scheda **Progetto** mostra una quantità maggiore di informazioni per l'articolo sulla riga attualmente selezionata nella scheda **Panoramica**. Alcune delle informazioni sono ripetute dalla scheda **Panoramica**, **Generale** o **Articolo**. La tabella seguente descrive i campi univoci per la scheda **Progetto**.

| Campo | descrizione |
|---|---|
| Data progetto | La data della transazione di domanda della previsione. |
| ID progetto | Identificatore del progetto cui fa riferimento la transazione corrente. |
| Fonte di finanziamento | Fonte di finanziamento cui è associata la previsione della domanda. |
| Numero attività | L'attività associata alla transazione di previsione della domanda. |
| Categoria | La categoria di costi della transazione corrente. |
| Proprietà riga | Stato a cui è collegata la transazione. |
| ID transazione | L'identificativo di sistema per la transazione di previsione della domanda. |
| Importo costi | L'importo della transazione di domanda della previsione. |
| Prezzo unitario | Prezzo per unità. |
| Autore modifica | Identificatore del lavoratore che ha modificato per ultimo la transazione selezionata. |
| Data fattura | Permette di immettere la data della fattura prevista. |
| Data eliminazione | Consente di visualizzare o modificare la data di eliminazione. Al momento della creazione della previsione, come data di eliminazione viene impostata la data di fine del progetto. Se per il progetto non è stata definita una data di fine, viene utilizzata la data del progetto. Questo campo si applica ai progetti a prezzo fisso e a quelli di investimento. |
| Data pagamento costo | Permette di immettere la data prevista per il pagamento dell'acquisto. |
| Data pagamento vendita | Permette di immettere la data prevista per il pagamento della vendita. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>La scheda Dimensioni finanziarie nella pagina Previsione della domanda

La scheda **Dimensioni finanziarie** mostra tutti i valori della dimensione finanziaria per la riga attualmente selezionata nella scheda **Panoramica**.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>La scheda Dimensioni inventariali nella pagina Previsione della domanda

La scheda **Dimensioni inventariali** mostra tutti i valori della dimensione inventariale per la riga attualmente selezionata nella scheda **Panoramica**.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>La griglia Allocazione nella pagina Previsione della domanda

Se stai utilizzando una chiave di allocazione articolo o se hai inserito una previsione dell'articolo per uno o più periodi futuri, puoi allocare la previsione selezionando **Assegna previsione** sulla barra degli strumenti nella scheda **Panoramica**. La quantità viene quindi distribuita secondo le modalità indicate dalle righe nella griglia **Allocazione**. (Vedere la sezione [Alloca previsioni](#allocate-forecast) di seguito in questo argomento.)

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Previsione di magazzino

Le pagine delle righe di previsione della domanda e dell'offerta presentano un pulsante **Previsione di magazzino** che apre una vista della pagina **Previsione di magazzino** filtrata per la stessa combinazione articolo/modello. La previsione di magazzino rappresenta un punto di equilibrio tra la domanda e l'offerta immesse per lo stesso articolo. Questo valore non può essere modificato. La previsione di magazzino aiuta il team di gestione dell'inventario a rivedere le modifiche previste all'inventario disponibile di un articolo durante il successivo periodo oggetto di previsione.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>Il riquadro delle azioni nella pagina Previsione di magazzino

Nella seguente tabella sono descritti i comandi disponibili nel riquadro delle azioni della pagina **Previsione di magazzino**.

| Azione | descrizione |
|---|---|
| Previsione dell'offerta | Apri una vita della pagina **Previsione dell'offerta** filtrata per la stessa combinazione di articolo/modello/data. |
| Previsione della domanda | Apri una vita della pagina **Previsione della domanda** filtrata per la stessa combinazione di articolo/modello/data. |
| Magazzino \> Visualizza dimensioni | Seleziona il prodotto, lo spazio di archiviazione e le dimensioni di tracciabilità che dovrebbero essere mostrate nella griglia **Panoramica**. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>La griglia nella pagina Previsione di magazzino

La tabella seguente descrive i campi nella griglia della pagina **Previsione di magazzino**.

| Campo | descrizione |
|---|---|
| **Modello** | Modello previsionale a cui è associata la transazione. |
| **Numero articolo** | Identificatore dell'articolo. |
| **Data budget** | Data della transazione previsionale. |
| **Tipo di previsione** | L'origine della transazione (*Previsione della domanda* o *Previsione dell'offerta*). |
| **Quantità a peso variabile** | La quantità prevista in unità a peso variabile. |
| **Quantità** | La quantità prevista nell'unità di magazzino. |
| **Peso variabile cumulato** | La quantità prevista accumulata nell'unità a peso variabile quando sono state accumulate più righe di previsione per lo stesso articolo. |
| **Distinta base secondaria** | Numero di una DBA secondaria specifica. |
| **Percorso secondario** | Numero di un ciclo di lavorazione secondario specifico. |
| (Altre dimensioni) | Ulteriori dimensioni possono essere visualizzate come colonne nella griglia. Per selezionare le dimensioni aggiuntive visualizzate, seleziona **Inventario \> Visualizza dimensioni** nel riquadro delle azioni. |

## <a name="allocate-forecast"></a><a name="allocate-forecast"></a>Alloca previsioni

Utilizzare la seguente procedura per elaborare le righe delle transazioni previsionali selezionate. Quando si alloca una previsione, la quantità viene quindi distribuita come indicato dalle righe nella griglia **Allocazione**.

1. A seconda del tipo di entità per cui si sta creando una previsione e del tipo di previsione da creare, aprire una pagina di previsione della domanda o dell'offerta come descritto in [Visualizzare e immettere manualmente le righe della previsione](#manual-entry).
1. Nella pagina delle righe di previsione della domanda o dell'offerta, selezionare una riga di previsione, quindi, nella scheda **Panoramica**, selezionare **Alloca previsione** sulla barra degli strumenti.
1. Nella finestra di dialogo **Alloca previsione**, impostare i campi descritti nella tabella seguente. (Il valore che si seleziona nel campo **Metodo** determina gli altri campi che sono disponibili.)

    | Campo | descrizione |
    |---|---|
    | Metodo | <p>Seleziona il metodo utilizzato per allocare la transazione previsionale:</p><ul><li>**Nessuna**: non viene eseguita alcuna allocazione.</li><li>**Periodo**: è prevista la stessa quantità per ogni periodo. Se selezioni questo valore, specifica una quantità nel campo **Per** e un'unità di tempo nel campo **Unità**.</li><li>**Chiave**: la previsione viene allocata in base alla chiave di allocazione per periodo specificata nel campo **Chiave periodo**. Puoi utilizzare questo metodo se intendi prendere in considerazione le variazioni stagionali.</li><ul>|
    | Per | <p>Consente di immettere il numero di intervalli di tempo futuri relativi alla durata della previsione. Questo campo è disponibile solo se nel campo **Metodo** hai selezionato *Periodo*.</p><p>Ad esempio, se selezioni *Periodo* nel campo **Metodo**, immetti *1* nel campo **Per**, quindi seleziona *Mesi* nel campo **Unità**. Quindi, nel campo **Fine**, specificare una data di fine a distanza di un anno. In questo caso, verrà creata una riga di previsione per ciascun mese dell'anno successivo, in base all'articolo e alla quantità specificati nella riga di intestazione. |
    | Unità | Seleziona l'unità dell'intervallo temporale: *Giorni*, *Mesi* o *Anni*. L'allocazione corrisponderà al numero di giorni, mesi o anni specificato nel campo **Per**.|
    | Chiave periodo | Permette di specificare la chiave di allocazione del periodo utilizzata per allocare la previsione. Per ulteriori informazioni, vedi [Allocazione dei dati di pianificazione del budget](../../finance/budgeting/budget-planning-data-allocation.md). |
    | Fine periodo | Specificare la data di fine che si applica alle proprie impostazioni nei campi **Per** e **Unità**. |

1. Selezionare **OK** per confermare le impostazioni.
1. È possibile rivedere i risultati sulla scheda **Allocazione** per la stessa riga.

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Aggiornamento in blocco delle transazioni previste

Utilizzare la procedura descritta di seguito per elaborare le righe delle transazioni previsionali esistenti. Le righe delle transazioni previsionali possono essere copiate, modificate ed eliminate.

1. Nella pagina delle righe di previsione della domanda o dell'offerta, seleziona **Aggiornamento in blocco**.
1. Nella finestra di dialogo seleziona **Filtro**.
1. Nella scheda **Intervallo**, seleziona i criteri che identificano i dati di previsione di origine che si desidera copiare, modificare o eliminare. Questi dati possono includere il modello previsionale, il numero di articolo e l'account del cliente.
1. Seleziona **OK** per confermare la selezione.

    Una volta selezionati i dati, puoi usare la finestra di dialogo **Modifica transazioni previsionali** per definire come copiarli, modificarli o eliminarli.

    > [!NOTE]
    > Il passaggio di filtraggio è un prerequisito per l'utilizzo della funzionalità **Modifica in blocco**. Se lo salti, il programma seleziona e aggiorna **tutte** le righe di previsione. Pertanto, potresti involontariamente causare la duplicazione o la rimozione delle transazioni.

1. Nella sezione **Gestione**, scegli se vuoi copiare, aggiornare o eliminare le transazioni previsionali selezionate.
1. Usa la sezione **Modifiche nel campo** per modificare i parametri della previsione. Seleziona la casella di controllo associata al parametro, quindi seleziona una delle opzioni disponibili. Ad esempio, seleziona la casella di controllo **Modello**, quindi seleziona un numero di modello di previsione. Le righe di previsioni esistenti vengono copiate nel modello previsionale selezionato.
1. Usa la sezione **Modifica del periodo** per spostare verso il futuro o verso il passato le date di inizio e di fine della previsione. Seleziona la casella di controllo e utilizza i campi relativi alla quantità e al periodo per definire il periodo di tempo per lo spostamento delle date di previsione. Puoi immettere una quantità negativa per spostare verso il passato la data di inizio (ovvero anticiparla).

    Ad esempio, per ritardare di sei mesi la data di inizio della transazione prevista, seleziona la casella di controllo, immetti *6* come quantità e seleziona *Mesi* come periodo.

1. Usa la sezione **Correggi campo** per aggiornare i dati della previsione effettiva. Nel campo **Campo**, seleziona il criterio da modificare. Nel campo **Fattore**, immetti un fattore di moltiplicazione da applicare al criterio selezionato oppure immetti una costante di addizione o sottrazione. Ad esempio, seleziona *Quantità* come criterio e immetti un fattore di *1.5* per moltiplicare la quantità dell'articolo per 1,5. In alternativa, immetti una costante di *-25* per ridurre la quantità dell'articolo di 25 unità.
1. Usa la sezione **Dimensioni finanziarie** per aggiornare le dimensioni finanziarie delle righe di previsione. Seleziona le dimensioni finanziarie da modificare, quindi immetti un valore da applicare alle dimensioni selezionate.
1. Seleziona **OK** per applicare le modifiche.

## <a name="use-forecasts-with-master-planning"></a>Usare le previsioni con la pianificazione generale

Dopo aver immesso la previsione della domanda e/o dell'offerta, è possibile includere le previsioni durante la pianificazione generale per tenere conto della domanda e/o dell'offerta previste nell'esecuzione della pianificazione generale. Quando le previsioni sono incluse nella pianificazione generale, vengono calcolati i fabbisogni lordi di materiali e capacità e vengono generati gli ordini pianificati.

### <a name="set-up-a-master-plan-to-include-an-inventory-forecast"></a>Impostare un piano generale per includere una previsione di inventario

Per impostare un piano generale in modo che includa una previsione di inventario segui questi passaggi.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano esistente o crearne uno nuovo.
1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Modello previsionale** - Selezionare il modello previsionale da applicare. Questo modello verrà preso in considerazione quando viene generato un suggerimento di fornitura per il piano generale corrente.
    - **Includi previsione dell'offerta** - Impostare questa opzione su *Sì* per includere la previsione dell'offerta nel piano generale corrente. Se si imposta questa opzione su *No*, le transazioni di previsione dell'offerta non verranno incluse nel piano generale.
    - **Includi previsione della domanda** - Impostare questa opzione su *Sì* per includere la previsione della domanda nel piano generale corrente. Se si imposta questa opzione su *No*, le transazioni di previsione della domanda non verranno incluse nel piano generale.
    - **Metodo utilizzato per ridurre i requisiti di previsione** - Selezionare il metodo da utilizzare per ridurre i requisiti di previsione. Per ulteriori informazioni, vedi [Chiavi di riduzione previsioni](planning-optimization/demand-forecast.md#reduction-keys).

1. Nella Scheda dettaglio **Intervallo temporale in giorni**, è possibile impostare i seguenti campi per specificare il periodo durante il quale la previsione è inclusa:

    - **Piano previsionale** - Impostare questa opzione su *Sì* per sostituire l'intervallo temporale del piano previsionale che ha origine dai singoli gruppi di copertura. Impostare l'opzione su *No* per utilizzare i valori dei singoli gruppi di copertura per il piano generale corrente.
    - **Periodo di tempo previsto** - Se si imposta l'opzione **Piano previsionale** su *Sì*, specificare il numero di giorni (dalla data odierna) in cui deve essere applicata la previsione della domanda.

    > [!IMPORTANT]
    > L'opzione **Piano previsionale** non è ancora supportata con l'ottimizzazione della pianificazione.

### <a name="run-a-master-plan-that-includes-an-inventory-forecast"></a>Eseguire un piano generale che include una previsione di inventario

Per eseguire un piano generale che include una previsione di inventario segui questi passaggi.

1. Vai a **Pianificazione generale \> Aree di lavoro \> Pianificazione generale**.
1. Nel campo **Piano generale** inserisci o seleziona il piano generale che hai impostato nella procedura precedente.
1. Nel riquadro **Pianificazione generale** seleziona **Esegui**.
1. Nella finestra di dialogo **Pianificazione generale** imposta l'opzione **Traccia ora di elaborazione** su *Sì*.
1. Nel campo **Numero di thread** immettere un numero.
1. Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.
1. Viene visualizzata la finestra di dialogo dell'editor di query standard. Nella scheda **Intervallo** seleziona la riga in cui il campo **Campo** è impostato su *Numero articolo*.
1. Nel campo **Criteri** seleziona il numero dell'articolo da includere nel piano.
1. Selezionare **OK**.

Per visualizzare i requisiti calcolati, apri la pagina **Fabbisogno lordo**. Ad esempio, nella pagina **Prodotti rilasciati**, scheda **Piano** del riquadro azioni, nel gruppo **Requisiti**, seleziona **Fabbisogno lordo**.

Per visualizzare gli ordini pianificati che vengono generati, vai a **Pianificazione generale \> Comune \> Ordini pianificati** e seleziona il piano di previsione appropriato.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica previsioni della domanda](introduction-demand-forecasting.md)
- [Impostazione della previsione della domanda](demand-forecasting-setup.md)
- [Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)
- [Implementare correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)
- [Pianificazione generale con previsioni della domanda](planning-optimization/demand-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]