---
title: Dichiarazione IVA per l'Egitto
description: In questo argomento viene descritto come configurare e generare il modulo di dichiarazione IVA per l'Egitto.
author: sndray
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9c776cedb65804f8cadbe324082c2abac435f906
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186616"
---
#  <a name="vat-declaration-for-egypt-eg-00002"></a>Dichiarazione IVA per l'Egitto (EG-00002)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto come configurare e generare il modulo di dichiarazione IVA e i libri vendite e acquisti per persone giuridiche in Egitto.

Il modulo di dichiarazione IVA per l'Egitto è il documento ufficiale che riepiloga l'importo totale dell'IVA a debito dovuto, l'importo totale dell'IVA a credito recuperabile e la relativa passività dell'importo IVA. Il modulo viene utilizzato per tutti i tipi di contribuenti e deve essere compilato manualmente nel portale dell'ufficio tributario. Il modulo di dichiarazione IVA è comunemente noto come presentazione della dichiarazione IVA.

Il modulo di dichiarazione IVA in Dynamics 365 Finance include i seguenti report:

- Modulo di dichiarazione IVA numero 10, che fornisce un dettaglio di importi, rettifiche e importo IVA per voce nel modulo di dichiarazione IVA come descritto nella legislazione.
- Libro delle transazioni di vendita
- Libro delle transazioni di acquisto

## <a name="prerequisites"></a>Prerequisiti
L'indirizzo principale della persona giuridica deve essere in Egitto.
Nell'area di lavoro **Gestione funzionalità**, attivare la seguente funzionalità:

   - (Egitto) Gerarchia di categorie per il report relativo alle imposte sulle vendite e sugli acquisti.

Per ulteriori informazioni su come abilitare le funzionalità, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Nell'area di lavoro **Creazione di report elettronici**, importare il seguente formato di creazione di report elettronici dal repository:

- Excel di dichiarazione IVA (EG)

> [!NOTE]
> Il formato sopra è basato sul **Modello di dichiarazione fiscale** e utilizza il **Mapping del modello di dichiarazione fiscale**. Ulteriori configurazioni verranno importate automaticamente.

Per ulteriori informazioni su come importare le configurazioni per la creazione di report elettronici, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Scaricare configurazioni per la creazione di report elettronici

L'implementazione del modulo di dichiarazione IVA per l'Egitto si basa sulle configurazioni per la creazione di report elettronici (ER). Per ulteriori informazioni sulle funzionalità e sui concetti di creazione di report configurabili, vedere [Creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Per gli ambienti di produzione e test di accettazione dell'utente (UAT), vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Per generare il modulo di dichiarazione IVA e i relativi report in una persona giuridica egiziana, caricare le seguenti configurazioni:

- Tax declaration model.version.70.xml o una versione successiva
- Tax declaration model mapping.version.70.120.xml o una versione successiva
- VAT Declaration Excel (EG).version.70.32 o una versione successiva

Dopo aver scaricato le configurazioni ER da Lifecycle Services (LCS) o dal repository globale, completare i seguenti passaggi.

1. Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni creazione di report elettronici**.
1. Nella pagina **Configurazioni**, nel riquadro Azioni, selezionare **Exchange** > **Carica da file XML**.
1. Caricare i file nell'ordine in cui sono elencati sopra. Dopo il caricamento di tutte le configurazioni, l'albero di configurazione deve essere presente in Finance.

## <a name="set-up-application-specific-parameters"></a>Configurare parametri specifici dell'applicazione

I parametri specifici dell'applicazione consentono di stabilire i criteri della modalità di classificazione e calcolo delle transazioni fiscali in ogni riga quando viene generato il report. La determinazione si basa sulla configurazione di fascia IVA articoli, fascia IVA, codice IVA e altri criteri stabiliti nella definizione di ricerca.

I report dei libri acquisti e vendite per l'Egitto includono una serie di colonne che corrispondono a specifiche classificazioni di transazioni come tipi di operazioni, prodotti e documenti specifici per l'Egitto. Anziché includere queste nuove classificazioni come nuovi dati di immissione quando le transazioni vengono registrate, le classificazioni saranno determinate in base alle diverse ricerche introdotte in **Configurazioni** > **Configurare parametri specifici dell'applicazione** > **Impostazioni** per soddisfare i requisiti dei report sull'IVA per l'Egitto. 

![Pagina Parametri specifici dell'applicazione](media/egypt-vat-declaration-setup1.png)

Le seguenti configurazioni di ricerca vengono utilizzate per classificare le transazioni nei report sui libri del'IVA a credito e a debito:

- **PurchaseItemTypeLookup** > Colonna O: tipo di elemento
- **VATRateTypeLookup** > Colonna B: tipo di imposta
- **VATRateTypeLookup** > Colonna C: tipo di elemento di tabella
- **PurchaseOperationTypeLookup** > Colonna A: tipo di documento
- **CustomerTypeLookup** > Colonna A: tipo di documento
- **SalesOperationTypeLookup** > Colonna N: tipo di operazione
- **SalesItemTypeLookup** > Colonna O: tipo di elemento

Completare i passaggi seguenti per impostare le differenti ricerche utilizzate per generare i report sulla dichiarazione IVA e sui relativi libri. 

1. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni** > **Impostazione** per impostare le regole per identificare la transazione fiscale nella relativa casella del modulo di dichiarazione IVA.
2. Selezionare la versione corrente e nella Scheda dettaglio **Ricerche** selezionare il nome della ricerca. Ad esempio, **SalesItemTypeLookup**. Questa ricerca identifica l'elenco delle classificazioni nel libro dell'IVA a debito richieste dall'ufficio tributario.
3. Nella Scheda dettaglio **Condizioni**, selezionare **Aggiungi** e nella nuova riga nella colonna **Risultato della ricerca** selezionare la riga correlata che rappresenta la classificazione nella **Colonna O**.
4. Nella colonna **Fascia IVA** selezionare la fascia IVA utilizzata per identificare la classificazione. Ad esempio, **Fattura vendita nazionale**. È inoltre possibile utilizzare la fascia IVA articoli, il codice imposta o la combinazione di attributi della struttura ad albero se la configurazione è definita in un altro modo. 
5. Nella colonna **Nome** selezionare la classificazione della transazione IVA.
6. Ripetere i passaggi da 3 a 5 per tutte le ricerche disponibili.
7. Selezionare **Aggiungi** per includere la riga del record finale e nella colonna **Risultato della ricerca**, selezionare **Non applicabile**. 
8. Nelle colonne rimanenti, selezionare **Non vuoto**. 
9. Nel campo **Stato** selezionare **Completato**.
10. Selezionare **Salva**, quindi chiudere la pagina **Parametri specifici dell'applicazione**.

> [!NOTE]
> Quando si aggiunge l'ultimo record, **Non applicabile**, si definisce la seguente regola: quando la fascia IVA, la fascia IVA articoli, il codice imposta e il nome passato come argomento non soddisfano nessuna delle regole precedenti, le transazioni non sono incluse nel libro IVA a debito. Sebbene questa regola non sia utilizzata durante la generazione del report, aiuta a evitare errori nella generazione del report quando manca una configurazione di regola.

Le tabelle seguenti rappresentano un esempio di configurazione suggerita per le configurazioni di ricerca descritte. 

**SalesItemTypeLookup**

| Risultato della ricerca         | Riga | Fascia IVA    | Fascia IVA articoli    | Codice imposta (Codice) | Nome                  |
|-----------------------|------|--------------------|-------------------------|-----------------|-----------------------|
| Nazionale              | 1    | VAT_LOCAL          | *Non vuoto*             | *Non vuoto*     | Vendite                 |
| Nazionale              | 2    | VAT_LOCAL          | *Non vuoto*             | *Non vuoto*     | SalesCreditNote       |
| Nazionale              | 3    | VAT_FINALC         | *Non vuoto*             | *Non vuoto*     | Vendite                 |
| Nazionale              | 4    | VAT_FINALC         | *Non vuoto*             | *Non vuoto*     | SalesCreditNote       |
| Nazionale              | 5    | VAT_PUBLIO         | *Non vuoto*             | *Non vuoto*     | Vendite                 |
| Nazionale              | 6    | VAT_PUBLIO         | *Non vuoto*             | *Non vuoto*     | SalesCreditNote       |
| Esportazione                | 7    | VAT_EXPORT         | *Non vuoto*             | *Non vuoto*     | Vendite                 |
| Esportazione                | 8    | VAT_EXPORT         | *Non vuoto*             | *Non vuoto*     | SalesCreditNote       |
| Macchina e attrezzatura | 9    | *Non vuoto*        | VAT_M&E                 | *Non vuoto*     | Vendite                 |
| Macchina e attrezzatura | 10   | *Non vuoto*        | VAT_M&E                 | *Non vuoto*     | SalesCreditNote       |
| Macchina con parti        | 11   | *Non vuoto*        | VAT_PARTS               | *Non vuoto*     | Vendite                 |
| Macchina con parti        | 12   | *Non vuoto*        | VAT_PARTS               | *Non vuoto*     | SalesCreditNote       |
| Esenzioni            | 13   | VAT_EXE            | *Non   vuoto*           | *Non vuoto*     | SaleExempt            |
| Esenzioni            | 14   | VAT_EXE            | *Non   vuoto*           | *Non vuoto*     | SalesExemptCreditNote |
| Non applicabile        | 15   | *Vuoto*            | *Vuoto*                 | VAT_ADJ         | *Non vuoto*           |
| Non applicabile        | 16   | *Non vuoto*        | *Non vuoto*             | *Non vuoto*     | *Non vuoto*           |

 **SalesOperationTypeLookup**

| Risultato della ricerca  | Riga | Fascia IVA articoli    | Codice imposta    | Nome                  |
|----------------|------|-------------------------|-------------|-----------------------|
| Beni          | 1    | VAT_GOODS               | *Non vuoto* | Vendite                 |
| Beni          | 2    | VAT_GOODS               | *Non vuoto* | SalesCreditNote       |
| Beni          | 3    | VAT_GOODS               | *Non vuoto* | SaleExempt            |
| Beni          | 4    | VAT_GOODS               | *Non vuoto* | SalesExemptCreditNote |
| Servizi       | 5    | VAT_SERV                | *Non vuoto* | Vendite                 |
| Servizi       | 6    | VAT_SERV                | *Non vuoto* | SalesCreditNote       |
| Servizi       | 7    | VAT_SERV                | *Non vuoto* | SaleExempt            |
| Servizi       | 8    | VAT_SERV                | *Non vuoto* | SalesExemptCreditNote |
| Rettifiche    | 9    | *Vuoto*                 | VAT_ADJ     | Vendite                 |
| Rettifiche    | 10   | *Vuoto*                 | VAT_ADJ     | SalesCreditNote       |
| Non applicabile | 11   | *Non vuoto*             | *Non vuoto* | *Non vuoto*           |

**PurchaseItemTypeLookup**

| Risultato della ricerca          | Riga | Fascia IVA articoli    | Codice imposta    | Nome                     |
|------------------------|------|-------------------------|-------------|--------------------------|
| Beni                  | 1    | VAT_GOODS               | *Non vuoto* | Acquisti                 |
| Beni                  | 2    | VAT_GOODS               | *Non vuoto* | PurchaseCreditNote       |
| Servizi               | 3    | VAT_SERV                | *Non vuoto* | Acquisti                 |
| Servizi               | 4    | VAT_SERV                | *Non vuoto* | PurchaseCreditNote       |
| Macchina e attrezzatura  | 5    | VAT_M&E                 | *Non vuoto* | Acquisti                 |
| Macchina e attrezzatura  | 6    | VAT_M&E                 | *Non vuoto* | PurchaseCreditNote       |
| Macchina con parti         | 7    | VAT_PARTS               | *Non vuoto* | Acquisti                 |
| Macchina con parti         | 8    | VAT_PARTS               | *Non vuoto* | PurchaseCreditNote       |
| Esenzioni             | 9    | VAT_EXE                 | *Non vuoto*  | PurchaseExempt           |
| Esenzioni             | 10   | VAT_EXE                 | *Non vuoto* | PurchaseExemptCreditNote |
| Non applicabile         | 11   | *Non vuoto*             | *Non vuoto* | *Non vuoto*              |

**PurchaseOperationTypeLookup**

| Risultato della ricerca  | Riga | Fascia IVA  | Codice imposta    | Nome                     |
|----------------|------|------------------|-------------|--------------------------|
| Nazionale       | 1    | VAT_LOCAL        | *Non vuoto* | Acquisti                 |
| Nazionale       | 2    | VAT_LOCAL        | *Non vuoto* | PurchaseCreditNote       |
| Nazionale       | 3    | VAT_LOCAL        | *Non vuoto* | PurchaseExempt           |
| Nazionale       | 4    | VAT_LOCAL        | *Non vuoto* | PurchaseExemptCreditNote |
| Importato       | 5    | VAT_IMPORT       | *Non vuoto* | Acquisti                 |
| Importato       | 6    | VAT_IMPORT       | *Non vuoto* | PurchaseCreditNote       |
| Importato       | 7    | VAT_IMPORT       | *Non vuoto* | PurchaseExempt           |
| Importato       | 8    | VAT_IMPORT       | *Non vuoto* | PurchaseExemptCreditNote |
| Rettifiche    | 9    | *Vuoto*          | VAT_ADJ     | PurchaseCreditNote       |
| Rettifiche    | 10   | *Vuoto*          | VAT_ADJ     | Acquisti                 |
| Non applicabile | 11   | *Non vuoto*      | *Non vuoto* | *Non vuoto*              |

**CustomerTypeLookup**

|    Risultato della ricerca    | Riga | Fascia IVA |
|---------------------|------|-----------------|
| Organizzazione        |  1   | VAT_LOCAL       |
| Organizzazione        |  2   | VAT_EXPORT      |
| Organizzazione        |  3   | VAT_EXE         |
| Consumatore finale      |  4   | VAT_FINALC      |
| Organizzazione pubblica |  5   | VAT_PUBLIO      |
| Non applicabile      |  6   | *Non vuoto*     |

**VATRateTypeLookup**

| Risultato della ricerca  | Riga | Codice imposta (Codice) |
|----------------|------|-----------------|
| GeneralGoods   | 1    | VAT_ST          |
| GeneralGoods   | 2    | VAT_RD          |
| FirstTable     | 3    | *Non vuoto*     |
| SecondTable    | 4    | *Non vuoto*     |
| Non applicabile | 5    | *Non vuoto*     |


## <a name="set-up-general-ledger-parameters"></a>Impostazione dei parametri di Contabilità generale

Per generare il report sul modulo di dichiarazione IVA in formato Microsoft Excel, definire un formato ER nella pagina **Parametri di contabilità generale**.

1. Selezionare **Imposta** > **Impostazione** > **Parametri di contabilità generale**.
2. Nella scheda **IVA**, nella sezione **Opzioni imposta**, nel campo **Mapping formato dichiarazione IVA**, selezionare **Excel di dichiarazione IVA (EG)**. Se si lascia il campo vuoto, il report sull'IVA standard verrà generato in formato SSRS.
3. Selezionare la **gerarchia di categorie**. Questa categoria abilita il codice voce doganale nelle transazioni della scheda Commercio estero per consentire agli utenti di selezionare e classificare beni e servizi. La descrizione di questa classificazione è dettagliata nei report sulle transazioni di vendita e acquisto. Questa configurazione è facoltativa.

![Modulo della dichiarazione](media/egypt-vat-declaration-setup2.png)


## <a name="generate-a-vat-return-report"></a>Generare un report sulla dichiarazione IVA
Il processo per preparare e inviare un report sulla dichiarazione IVA di un periodo si basa sulle transazioni di pagamento IVA registrate durante il processo di liquidazione e registrazione dell'IVA. Per ulteriori informazioni sul report e sulla liquidazione dell'IVA, vedere [Panoramica dell'IVA](../general-ledger/indirect-taxes-overview.md).

Completare i seguenti passaggi per generare il report sulla dichiarazione IVA:

1. Selezionare **Imposta** > **Dichiarazioni** > **IVA** > **Report IVA per periodo liquidazione** o **Liquida e registra IVA**.
2. Selezionare il **periodo di liquidazione**.
3. Selezionare la data di inizio e quindi selezionare la versione del pagamento IVA.
5. Selezionare **OK**. 
6. Immettere l'importo di credito del periodo precedente, se applicabile, o lasciare il valore zero.
7. Nel campo **Dettagli report** selezionare una delle seguenti opzioni disponibili: 
   - **Libro IVA a credito**: genera il report sui dettagli delle transazioni IVA a credito.
   - **Libro IVA a debito**: genera il report sui dettagli delle transazioni IVA a debito.
   - **Dichiarazione IVA**: genera solo il modulo di dichiarazione IVA.
8. Immettere il nome della persona registrata per assegnare il modulo.
9. Selezionare la lingua. Tutti i report vengono tradotti in **en-us** e **ar-eg**.
  
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


