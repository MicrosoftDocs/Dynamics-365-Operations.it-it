---
title: Dichiarazione IVA (Svizzera)
description: In questo articolo vengono fornite informazioni su come impostare e generare una dichiarazione di imposta sul valore aggiunto per la Svizzera.
author: AdamTrukawka
ms.date: 09/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Switzerland
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 264584
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
ms.openlocfilehash: f5967fc00cffc7882b9232ab989d897dbe123623
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275209"
---
# <a name="vat-declaration-switzerland"></a>Dichiarazione IVA (Svizzera)

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

Questo articolo descrive come impostare e generare una dichiarazione di imposta sul valore aggiunto (IVA) per la Svizzera nel formato XML ufficiale (standard eCH-0217 eMWST). Descrive inoltre come visualizzare in anteprima la dichiarazione IVA in Microsoft Excel.

Per generare automaticamente il report, è necessario innanzitutto creare codici IVA sufficienti per mantenere una contabilità IVA separata per ogni casella della dichiarazione IVA. Inoltre, nei parametri specifici dell'applicazione del formato di Creazione di report elettronici per la dichiarazione IVA, è necessario associare i codici IVA al risultato delle ricerche per le caselle nella dichiarazione IVA.

Per la Svizzera, è necessario configurare tre ricerche: **Ricerca fatturato**, **Ricerca campi report** e **Ricerca altri flussi di cassa**. Per ulteriori informazioni su come impostare i parametri specifici dell'applicazione, vedi la sezione [Impostare i parametri specifici dell'applicazione per i campi della dichiarazione IVA](#set-up-application-specific-parameters-for-vat-declaration-fields) più avanti in questo articolo.

Nella tabella seguente, la colonna "Risultato ricerca" mostra il risultato della ricerca preconfigurato per una riga specifica della dichiarazione IVA nel formato della dichiarazione IVA. Utilizza queste informazioni per associare correttamente i codici IVA al risultato della ricerca e quindi alla riga della dichiarazione IVA.

### <a name="vat-declaration-overview"></a>Panoramica sulla dichiarazione IVA

La dichiarazione IVA in Svizzera contiene le seguenti informazioni.

**SEZIONE I - FATTURATO**

| Riga           | Elemento XML                   | descrizione                                                                                                                                                                                                                                                               | Ricerca          | Risultato della ricerca                                                                                                                                    |
|----------------|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 200            | totalConsideration            | L'importo totale del corrispettivo concordato o riscosso, compreso il corrispettivo per le forniture per le quali è stata esercitata l'opzione per la tassazione, i trasferimenti di forniture secondo la procedura di notifica e le forniture effettuate all'estero (fatturato mondiale). | Ricerca fatturato | TaxableSupplies TaxableSupplies22 SuppliesToForeignCountries SuppliesAbroad TransferNotificationProcedure SuppliesExemptFromTax VariousDeduction |
| 205            | opted                         | Corrispettivo che è riportato alla riga 200 per le forniture esenti dall'imposta senza credito (articolo 21) e per cui è stata esercitata l'opzione per la tassazione di cui all'articolo 22.                                                                          | Ricerca fatturato | TaxableSupplies22                                                                                                                                |
| **Detrazioni** |                               |                                                                                                                                                                                                                                                                           |                 |                                                                                                                                                  |
| 220            | suppliesToForeignCountries    | Le forniture esenti da imposta, quali le esportazioni (articolo 23) e le forniture a favore di beneficiari istituzionali e privati esenti da soggettività tributaria (articolo 107, comma 1, lett. a).                                              | Ricerca fatturato | SuppliesToForeignCountries                                                                                                                       |
| 221            | suppliesAbroad                | Forniture all'estero (il luogo della fornitura è estero).                                                                                                                                                                                                        | Ricerca fatturato | SuppliesAbroad                                                                                                                                   |
| 225            | transferNotificationProcedure | Trasferimenti di forniture secondo la procedura di notifica (articolo 38). È necessario inviare il modulo 764.                                                                                                                                                                   | Ricerca fatturato | TransferNotificationProcedure                                                                                                                    |
| 230            | suppliesExemptFromTax         | Forniture nel territorio svizzero esenti dall'imposta senza credito (articolo 21) e per cui non è stata esercitata l'opzione per la tassazione di cui all'articolo 22.                                                                                   | Ricerca fatturato | SuppliesExemptFromTax                                                                                                                            |
| 235            | reductionOfConsideration      | Riduzione del corrispettivo, come sconti e ribassi.                                                                                                                                                                                                                | Ricerca fatturato | ReductionOfConsideration                                                                                                                         |
| 280            | variousDeduction              | Varie, come valore del terreno e prezzi di acquisto in caso di tassazione del margine.                                                                                                                                                                                    | Ricerca fatturato | VariousDeduction                                                                                                                                 |
| 289            | Non applicabile                | Righe totali da 220 a 280.                                                                                                                                                                                                                                                | Totale           | 220 + 221 + 225 + 230 + 235 + 280                                                                                                                |
| 299            | Non applicabile                | Fatturato imponibile (riga 200 meno riga 289).                                                                                                                                                                                                                               | Totale           | 200 – 289                                                                                                                                        |

**SEZIONE II - CALCOLO DELLE IMPOSTE**

**Imposte dovute**

| Riga | Elemento XML                           | descrizione                                                 | Ricerca              | Risultato della ricerca                                                                                                                                             |
|------|---------------------------------------|-------------------------------------------------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 302  | supplierTaxRate/aliquota imposta importo imposta | Forniture dal 1 gennaio 2018 ad aliquota normale.          | Ricerca campi report | SuppliesStandardRate                                                                                                                                      |
| 312  | supplierTaxRate/aliquota imposta importo imposta | Forniture dal 1 gennaio 2018 ad aliquota ridotta.           | Ricerca campi report | SuppliesReducedRate                                                                                                                                       |
| 342  | supplierTaxRate/aliquota imposta importo imposta | Forniture dal 1 gennaio 2018 a un'aliquota per prestazioni alberghiere.    | Ricerca campi report | SuppliesAccomodationRate                                                                                                                                  |
| 382  | acquisitionTax/aliquota imposta importo imposta  | Imposta sull'acquisizione per forniture dal 1 gennaio 2018           | Ricerca campi report | SuppliesAcquisitionTax</br> UseTaxAcquisitionTax (questo risultato è riportato per intero alla riga 400.)</br> Importo dell'imposta non detraibile, se presente alla riga 415 |
| 301  | supplierTaxRate/aliquota imposta importo imposta | Forniture fino al 31 dicembre 2017 ad aliquota normale.       | Ricerca campi report | SuppliesOldStandardRate                                                                                                                                   |
| 311  | supplierTaxRate/aliquota imposta importo imposta | Forniture fino al 31 dicembre 2017 ad aliquota ridotta.        | Ricerca campi report | SuppliesOldReducedRate                                                                                                                                    |
| 341  | supplierTaxRate/aliquota imposta importo imposta | Forniture fino al 31 dicembre 2017 a un'aliquota per prestazioni alberghiere. | Ricerca campi report | SuppliesAccomodationOldRate                                                                                                                               |
| 381  | acquisitionTax/aliquota imposta importo imposta  | Imposta sull'acquisizione per forniture fino al 31 dicembre 2017        | Ricerca campi report | SuppliesAcquisitionTaxOldRate                                                                                                                             |
| 399  | Non applicabile                        | Importo totale dell'imposta dovuta (righe da 301 a 382).            | Totale               | 302 + 312 + 342 + 382 + 301 + 311 + 341 + 381                                                                                                             |

**Imposta a credito**

| Riga | Elemento XML                 | descrizione                                                                                                                                                         | Ricerca              | Risultato della ricerca                                                                                                                                    |
|------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 400  | inputTaxMaterialAndServices | Imposta a credito sul costo di materiali e forniture di servizi.                                                                                                        | Ricerca campi report | InputTaxMaterialAndServices (riportato per intero)</br> UseTaxAcquisitionTax (riportato per intero)</br> Importo dell'imposta non detraibile, se presente alla riga 415 |
| 405  | inputTaxInvestments         | Imposta a credito sugli investimenti e altri costi operativi.                                                                                                                 | Ricerca campi report | InputTaxInvestments (riportato per intero)</br> Importo dell'imposta non detraibile, se presente alla riga 415                                                 |
| 410  | subsequentInputTaxDeduction | Detassazione (articolo 32). È necessario allegare un elenco dettagliato.                                                                                                       | Ricerca campi report | SubsequentInputTaxDeduction                                                                                                                      |
| 415  | inputTaxCorrections         | Rettifica della detrazione dell'imposta a credito, sia uso misto (articolo 30) che uso proprio (articolo 31).                                                                        | Ricerca campi report | InputTaxCorrections (riportato per intero ma con il segno invertito)</br>Anche l'importo fiscale non deducibile delle transazioni delle righe 400, 405 è riportato qui                                                                                 |
| 420  | inputTaxReductions          | Riduzione della detrazione dell'imposta a credito: il flusso di fondi che non si considerano computabili, quali sussidi e oneri di soggiorno (articolo 33, paragrafo 2). | Ricerca campi report | InputTaxReductions (riportato per intero ma con il segno invertito)                                                                                     |
| 479  | Non applicabile              | Righe totali da 400 a 420.                                                                                                                                        | Totale               | 400 + 405 + 410 – 415 – 420                                                                                                                      |
| 500  | Non applicabile              | Importo pagabile.                                                                                                                                         | Totale               | 399 – 479, se 399-479 è positivo                                                                                                                |
| 510  | Non applicabile              | Il credito a favore del soggetto tassabile.                                                                                                                          | Totale               | 479 – 399, se 479-399 è positivo                                                                                                              |

**SEZIONE III - ALTRI FLUSSI DI CASSA**

| Riga | Elemento XML | descrizione                                                                                                                                                               | Ricerca                 | Risultato della ricerca |
|------|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 900  | subsidies   | Sussidi, fondi turistici raccolti dagli uffici turistici, contributi per l'acqua cantonale, fondi per fognature o rifiuti (articolo 18, paragrafo 2, lett. da a a c). | Ricerca altri flussi di cassa | Subsidies     |
| 910  | donations   | Donazioni, dividendi, risarcimenti danni, ecc. (articolo 18, comma 2, lett. da d a l).                                                                         | Ricerca altri flussi di cassa | Subsidies     |

#### <a name="purchase-reverse-charge-vat"></a>Reverse charge per acquisti

Se configuri i codici IVA per registrare l'imposta sull'acquisizione in entrata (reverse charge) utilizzando l'imposta di utilizzo, associa i codici IVA al risultato della ricerca di **Ricerca campi report** che contiene "UseTax" nel nome.

In alternativa, è possibile configurare due codici IVA distinti: uno per l'IVA dovuta e uno per la detrazione dell'IVA. Quindi associa ogni codice ai risultati di ricerca corrispondenti di **Ricerca campi report**.

Ad esempio, per le forniture dal 1 gennaio 2018 - imposta sull'acquisizione, configura il codice IVA **UT_S_RC** con l'imposta di utilizzo e associala al risultato di ricerca **UseTaxAcquisitionTax** di **Ricerca campi report**. In questo caso, gli importi che utilizzano il codice IVA **UT_S_RC** vengono riportati alle righe 382 e 400 con l'intero importo e alla riga 415 con l'importo non detraibile, se presente.

In alternativa, configura due codici IVA:

- **VAT_S_RC**, che ha un valore di aliquota d’imposta del -7,7 percento
- **InVAT_S_RC**, che ha un valore di aliquota d’imposta del 7,7 percento

Quindi associ i codici ai risultati della ricerca nel modo seguente:

- Associa **VAT_S_RC** al risultato di ricerca **SuppliesAcquisitionTax** di **Ricerca campi report**.
- Associa **InVAT_S_RC** al risultato di ricerca **InputTaxMaterialAndServices** di **Ricerca campi report**.

In questo caso, gli importi che utilizzano il codice IVA **VAT_S_RC** verranno riportati alla riga 382. Gli importi che utilizzano il codice IVA **InVAT_S_RC** verranno riportati alla riga 400 con l'intero importo e alla riga 415 con l'importo non detraibile.

Per ulteriori informazioni su come configurare la reverse charge, vedi [Reverse charge]emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurare i parametri di sistema

Per generare una dichiarazione IVA, configura l'UID (numero di identificazione dell'azienda).

1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Seleziona la persona giuridica, quindi **ID registrazione**.
3. Seleziona o crea l'indirizzo in Svizzera, quindi, nella Scheda dettaglio **ID registrazione**, seleziona **Aggiungi**.
4. Nel campo **Tipo di registrazione**, seleziona il tipo di registrazione che è dedicato alla Svizzera e che utilizza la categoria di registrazione **ID azienda (COID)**.
5. Nel campo **Numero di registrazione**, inserisci il numero UID nel seguente formato: CHE-123.456.789.
6. Nella scheda **Generale**, nel campo **Valido**, inserisci la data in cui il numero diventa valido.
7. Ripeti questi passaggi per impostare una riga con la partita IVA. In questo caso, seleziona il tipo di registrazione che utilizza la categoria di registrazione **Partita IVA** e inserisci il numero nel seguente formato: CHE-123.456.789 TVA/MWST/IVA.

Per ulteriori informazioni su come impostare le categorie di registrazione e i tipi di registrazione, vedi [ID registrazione](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-switzerland"></a>Impostare una dichiarazione IVA per la Svizzera

### <a name="import-er-configurations"></a>Importare configurazioni ER

Apri l'area di lavoro **Creazione di report elettronici** e importa le seguenti versioni o successive di questi formati della creazione di report elettronici:

- XML di dichiarazione IVA (CH) versione 96.16
- Excel di dichiarazione IVA (CH) versione 96.16.9

### <a name=""></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields">Impostare i parametri specifici dell'applicazione per i campi della dichiarazione IVA</a>

Per generare automaticamente una dichiarazione IVA, associa i codici IVA nell'applicazione e i risultati della ricerca nella configurazione della creazione di report elettronici.

> [!NOTE]
> Consigliamo di abilitare la funzionalità **Utilizza parametri specifici dell'applicazione delle versioni precedenti dei formati ER** nell'area di lavoro **Gestione delle funzionalità**. Quando questa funzionalità è abilitata, i parametri configurati per la versione precedente di un formato ER diventano automaticamente applicabili alla versione successiva dello stesso formato. Se questa funzione non è abilitata, è necessario configurare i parametri specifici dell'applicazione in modo esplicito per ogni versione del formato. Abilitare la funzionalità **Utilizza parametri specifici dell'applicazione delle versioni precedenti dei formati ER** disponibile nell'area di lavoro **Gestione delle funzionalità** a partire dalla versione 10.0.23 di Finance. Per ulteriori informazioni su come impostare i parametri di un formato ER per ciascuna persona giuridica, vedi [Impostare i parametri di un formato ER per la persona giuridica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

#### <a name="set-up-turnover-lookup"></a>Impostare la ricerca fatturato

Segui questi passaggi per definire quali codici IVA generano quali caselle nella sezione I, "Fatturato".

1. Vai ad **Aree di lavoro** > **Creazione di report elettronici** e seleziona **Configurazioni report**.
2. Seleziona la configurazione **XML di dichiarazione IVA (CH)**, quindi seleziona **Configurazioni** > **Impostazione dei parametri specifici dell'applicazione**.
3. Nella pagina **Parametri specifici dell'applicazione**, nella Scheda dettaglio **Ricerche** seleziona **Ricerca fatturato**.
4. Nella Scheda dettaglio **Condizioni**, imposta i seguenti campi per associare i codici IVA e le operazioni.

   | Campo                  | descrizione                                                                                                                                                                                                                                                                                                         |
   |------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Risultato della ricerca          | Seleziona il valore del fatturato. Per ulteriori informazioni sui valori del fatturato e sulla loro assegnazione alle righe della dichiarazione IVA, vedi la sezione [Panoramica sulla dichiarazione IVA](#vat-declaration-overview) precedente in questo articolo.                                                                                         |
   | Codice imposta               | Seleziona il codice IVA da associare all'operazione. Le transazioni IVA registrate che utilizzano il codice IVA selezionato verranno raccolte nella casella appropriata della dichiarazione. Si consiglia di separare i codici IVA in modo tale che un codice IVA generi importi in una sola casella della dichiarazione.   |
   | Classificatore di transazioni | Se sono stati creati codici IVA sufficienti per determinare una casella della dichiarazione, seleziona **\*Non vuoto\***. Se non hai creato un numero sufficiente di codici IVA in modo che un codice IVA generi importi in una sola casella della dichiarazione, puoi impostare un classificatore di transazioni. Sono disponibili i seguenti classificatori di transazioni: <br>- **Acquisti**<br>- **PurchaseExempt** (acquisto esente da tasse) <br>- **PurchaseReverseCharge** (imposta a credito da reverse charge su acquisti) <br>- **Vendite** <br>- **SalesExempt** (vendita esente da tasse) <br>- **SalesReverseCharge** (imposta a debito da reverse charge su acquisti o reverse charge su vendite) <br>- **IVA intracomunitaria** <br> Per ogni classificatore di transazioni è disponibile anche un classificatore per la nota di accredito. Ad esempio, uno di questi classificatori è **PurchaseCreditNote** (nota di accredito di acquisto).|



   > [!NOTE]
   > Associa tutti i codici IVA ai risultati della ricerca. Se i codici IVA non devono generare valori nella sezione I, associali al risultato della ricerca **Altro**.

   ![Pagina dei parametri specifici dell'applicazione per la ricerca fatturato;Pagina dei parametri specifici dell'applicazione per la ricerca fatturato](media/f99d7ff6529a58623732e112cf864230.png)

#### <a name="set-up-report-field-lookup"></a>Impostare la ricerca campi report

Segui questi passaggi per definire quali codici IVA generano quali caselle nella sezione II, "Calcolo delle imposte".

1. Nella pagina **Parametri specifici dell'applicazione**, nella Scheda dettaglio **Ricerche** seleziona **Ricerca campi report**.
2. Nella Scheda dettaglio **Condizioni**, associa i codici IVA e i campi del report.

   > [!NOTE]
   > Associa tutti i codici IVA ai risultati della ricerca. Se i codici IVA non devono generare valori nella sezione II, associali al risultato della ricerca **Altro**.

   ![Pagina dei parametri specifici dell'applicazione per la ricerca campi report;Pagina dei parametri specifici dell'applicazione per la ricerca campi report](media/b440aab1d394fb9e98f12aed5d96582d.png)

#### <a name="set-up-other-cash-flow-lookup"></a>Impostare la ricerca altri flussi di cassa

Segui questi passaggi per definire quali codici IVA generano l'importo nella sezione III, "Altri flussi di cassa".

1. Nella pagina **Parametri specifici dell'applicazione**, nella Scheda dettaglio **Ricerche** seleziona **Ricerca altri flussi di cassa**.
2. Nella Scheda dettaglio **Condizioni**, associa i codici IVA e gli elementi degli altri flussi di cassa.

   > [!NOTE]
   > Come ultima riga dell'impostazione, crea una riga in cui associ il valore **\*Non vuoto\*** del codice imposta con il risultato della ricerca **Altro**. Questa riga indica che tutti gli altri codici IVA non definiti nelle righe precedenti non generano importi nella sezione III.

   ![Pagina dei parametri specifici dell'applicazione per la ricerca altri flussi di cassa](media/2ddd539a62e69bc03c346fb8c90e6299.png)

 3. Nel campo **Stato**, modifica il valore in **Completato**.
 4. Nel riquadro Azioni, seleziona **Esporta** per esportare le impostazioni dei parametri specifici dell'applicazione.
 5. Seleziona la configurazione **Excel di dichiarazione IVA (CH)**, quindi, nel riquadro Azioni, seleziona **Importa** per importare i parametri che hai configurato per **XML di dichiarazione IVA (CH)**.
 6. Nel campo **Stato** selezionare **Completato**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Impostare il formato di reporting IVA per visualizzare in anteprima gli importi in Excel

1. Nell'area di lavoro **Gestione funzionalità**, abilita la funzionalità **Report formato dichiarazione IVA**.
2. Vai a **Contabilità generale \> Impostazione \> Parametri di contabilità generale**.
3. Nella scheda **IVA**, nella Scheda dettaglio **Opzioni imposta**, nel campo **Mapping formato dichiarazione IVA**, seleziona il formato di creazione di report elettronici **Excel di dichiarazione IVA (CH)**.

   Questo formato verrà stampato quando si esegue il report **Report IVA per periodo liquidazione**. Verrà anche stampato quando si seleziona **Stampa** nella pagina **Pagamenti IVA**.

4. Nella pagina **Uffici IVA**, seleziona l'ufficio IVA, quindi nel campo **Layout del report**, seleziona **Predefinito**.

Se stai configurando la dichiarazione IVA in una persona giuridica che ha [più partite IVA](emea-reporting-for-multiple-vat-registrations.md), segui questi passaggi.

1. Vai a **Contabilità generale** > **Impostazione** > **Parametri di contabilità generale**.
2. Nella scheda **IVA**, nella Scheda dettaglio **Creazione di report elettronici per paesi/aree geografiche**, alla riga per **CHE** seleziona il formato della creazione di report elettronici **Excel di dichiarazione IVA (CH)**.

## <a name="set-up-electronic-messages"></a>Impostare i messaggi elettronici

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Scaricare e importare il pacchetto di dati con impostazioni di esempio per i messaggi elettronici

Il pacchetto dati contiene le impostazioni per i messaggi elettronici che vengono utilizzate per generare la dichiarazione IVA in formato XML e visualizzarne l'anteprima in Excel. Puoi estendere queste impostazioni o crearne di tue. Per ulteriori informazioni su come utilizzare con la messaggistica elettronica e creare le proprie impostazioni, vedi [Messaggistica elettronica](../general-ledger/electronic-messaging.md).

1. In [LCS](https://lcs.dynamics.com/v2), nella raccolta di risorse condivise, seleziona **Pacchetto dati** come tipo di risorsa, quindi scarica **Pacchetto EM dichiarazione IVA CH**. Il file scaricato si chiama **CH VAT declaration EM package.zip**.
2. In Finance, nell'area di lavoro **Gestione dati** seleziona **Importa**.
3. Nella Scheda dettaglio **Importa**, nel campo **Nome gruppo** immetti un nome per il processo.
4. Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi file**.
5. Nella finestra di dialogo **Aggiungi file**, verifica che il campo **Formato dati di origine** sia impostato su **Pacchetto**, seleziona **Carica e aggiungi**, quindi seleziona il file zip scaricato in precedenza.
6. Selezionare **Chiudi**.
7. Dopo che le entità di dati sono state caricate, nel riquadro Azioni seleziona **Importa**.
8. Vai a **Imposta** > **Richieste di informazioni e report** > **Messaggi elettronici** > **Messaggi elettronici** e convalida l'elaborazione del messaggio elettronico importato (**Dichiarazione IVA CH**).

### <a name="configure-electronic-messages"></a>Configurare i messaggi elettronici

1. Vai a **Imposta** > **Impostazione** > **Messaggi elettronici** > **Azioni di popolamento record**.
2. Seleziona la riga per **CH Compila i record di dichiarazione IVA**, quindi seleziona **Modifica query**.
3. Utilizza il filtro per specificare i periodi di liquidazione da includere nel report.
4. Se devi riportare le transazioni fiscali di altri periodi di liquidazione in una dichiarazione diversa, crea una nuova azione **Popola record** e seleziona i periodi di liquidazione appropriati.

## <a name="preview-the-vat-declaration-in-excel"></a>Visualizzare in anteprima la dichiarazione IVA in Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Visualizzare in anteprima la dichiarazione IVA in Excel dall'attività periodica Report IVA per periodo liquidazione

1. Vai a **Imposta** > **Attività periodiche** > **Dichiarazioni** > **IVA** > **Report IVA per periodo liquidazione**.
2. Impostare i seguenti campi.

   | Campo                     | descrizione                                    |
   |---------------------------|------------------------------------------------|
   | Periodo di liquidazione         | Seleziona il periodo di liquidazione.                  |
   | Versione pagamento IVA | Selezionare uno dei seguenti valori: <br>- **Originale**: genera un report per le transazioni IVA del pagamento IVA originale o prima che venga generato il pagamento IVA. <br>- **Correzioni**: genera un report per le transazioni IVA di tutti i pagamenti IVA successivi per il periodo. <br> - **Elenco totale**: genera un report per tutte le transazioni IVA per il periodo, incluse l'originale e tutte le correzioni.            |
   | Data di inizio                 | Seleziona la data di inizio del periodo di riferimento. |

3. Seleziona **OK** ed esamina il report Excel.

### <a name=""></a><a name="settle-and-post-sales-tax"> Liquida e registra IVA</a>

1. Vai a **Imposta** > **Attività periodiche** > **Dichiarazioni** > **IVA** > **Liquida e registra IVA**.
2. Impostare i seguenti campi.

   | Campo                     | descrizione                                    |
   |---------------------------|------------------------------------------------|
   | Periodo di liquidazione         | Seleziona il periodo di liquidazione.                  |
   | Versione pagamento IVA | Selezionare uno dei seguenti valori: <br> - **Originale**: genera il pagamento IVA originale per il periodo di liquidazione. <br> - **Ultime correzioni**: genera un pagamento IVA di correzione dopo la creazione del pagamento IVA originale per il periodo di liquidazione.          |
   | Data di inizio                 | Seleziona la data di inizio del periodo di riferimento. |

3. Selezionare **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Visualizzare in anteprima la dichiarazione IVA in Excel da un pagamento IVA

1. Vai a **Imposta** > **Richieste di informazioni e report** > **Richieste di informazioni su IVA** > **Pagamenti IVA** e seleziona una riga di pagamento IVA.
2. Seleziona **Stampa report**.
3. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, imposta i campi come spiegato in precedenza in questo articolo. Quindi esamina il file Excel generato per la riga di pagamento IVA selezionata.

   > [!NOTE]
   > Il report viene generato solo per la riga selezionata del pagamento IVA. Se è necessario generare, ad esempio, una dichiarazione correttiva che contenga tutte le correzioni per il periodo o una dichiarazione sostitutiva che contenga i dati originali e tutte le correzioni, utilizza l'attività periodica **Report IVA per periodo liquidazione**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Generare una dichiarazione IVA dai messaggi elettronici

Quando si utilizzano messaggi elettronici per generare il report, è possibile raccogliere dati fiscali da più persone giuridiche. Per ulteriori informazioni, vedi la sezione [Eseguire una dichiarazione IVA per più persone giuridiche](#run-a-vat-declaration-for-multiple-legal-entities) più avanti in questo articolo.

La procedura seguente si applica all'elaborazione di messaggi elettronici di esempio importata in precedenza dalla raccolta di risorse condivise LCS.

1. Vai a **Imposta \> Richieste di informazioni e report \> Messaggi elettronici \> Messaggi elettronici**.
2. Nel riquadro a sinistra, seleziona **Dichiarazione IVA CH**.
3. Nella Scheda dettaglio **Messaggi**, seleziona **Nuovo**, quindi nella finestra di dialogo **Esegui elaborazione** seleziona **OK**.
4. Seleziona la riga del messaggio creata, immetti una descrizione e quindi specifica le date di inizio e di fine per la dichiarazione.

   > [!NOTE]
   >  I passaggi da 5 a 7 sono facoltativi.

5. Facoltativo: nella Scheda dettaglio **Messaggi**, seleziona **Raccogli dati**, quindi seleziona **OK**. I pagamenti IVA generati in precedenza vengono aggiunti al messaggio. Per ulteriori informazioni, vedi la sezione [Liquida e registra IVA](#settle-and-post-sales-tax) descritta precedentemente in questo articolo. Se salti questo passaggio, puoi comunque generare una dichiarazione IVA utilizzando il campo **Versione dichiarazione fiscale** nella finestra di dialogo **Dichiarazione**.
6. Facoltativo: nella Scheda dettaglio **Elementi del messaggio**, rivedi i pagamenti IVA trasferiti per l'elaborazione. Per impostazione predefinita, sono inclusi tutti i pagamenti IVA del periodo selezionato che non sono stati inclusi in nessun altro messaggio della stessa elaborazione.
7. Facoltativo: seleziona **Documento originale** per rivedere i pagamenti IVA o seleziona **Elimina** per escludere i pagamenti IVA dall'elaborazione. Se salti questo passaggio, puoi comunque generare una dichiarazione IVA utilizzando il campo **Versione dichiarazione fiscale** nella finestra di dialogo **Dichiarazione**.
8. Nella Scheda dettaglio **Messaggi**, seleziona **Aggiorna stato**. Nella finestra di dialogo **Aggiorna stato**, seleziona **Pronto a generare**, quindi seleziona **OK**. Verifica che lo stato del messaggio sia cambiato in **Pronto a generare**.
9. Seleziona **Genera report**. Per visualizzare in anteprima gli importi della dichiarazione IVA, nella finestra di dialogo **Esegui elaborazione** seleziona **Anteprima report**, quindi seleziona **OK**.
10. Nella finestra di dialogo **Parametri per la creazione di report elettronici** imposta i seguenti campi, quindi seleziona **OK**.

      | **Campo**               | **Descrizione**    |
      |-------------------------|---------------------|
      | Periodo di liquidazione       | Seleziona il periodo di liquidazione. Se hai selezionato **Raccogli dati** al passaggio 5, puoi ignorare questo campo. Il report verrà generato per le transazioni IVA incluse nei pagamenti IVA riscossi. |
      | Versione dichiarazione fiscale | Selezionare uno dei seguenti valori: <br>-**Originale**: genera un report per le transazioni IVA del pagamento IVA originale o prima che venga generato il pagamento IVA. <br>-**Correzioni**: genera un report per le transazioni IVA di tutti i pagamenti IVA successivi per il periodo. <br>- **Elenco totale**: genera un report per tutte le transazioni IVA per il periodo, incluse l'originale e tutte le correzioni.               |
    
    Se hai selezionato **Raccogli dati** al passaggio 5, puoi ignorare questo campo. Il report verrà generato per le transazioni IVA incluse nei pagamenti IVA riscossi.

11. Seleziona il pulsante **Allegati** (simbolo della graffetta) nell'angolo in alto a destra della pagina, quindi seleziona **Apri** per aprire il file. Rivedi gli importi nel documento Excel.
12. Seleziona **Genera report**.
13. Per generare una dichiarazione IVA in formato XML, nella finestra di dialogo **Esegui elaborazione** seleziona **Genera report**, quindi seleziona **OK**.
14. Nella finestra di dialogo **Parametri per la creazione di report elettronici** imposta i campi come descritto in precedenza in questa procedura, quindi seleziona **OK**.

## <a name=""></a><a name="run-a-vat-declaration-for-multiple-legal-entities">Eseguire una dichiarazione IVA per più persone giuridiche</a>

Per utilizzare i formati per riportare la dichiarazione IVA per un gruppo di persone giuridiche, è necessario prima impostare i parametri specifici dell'applicazione dei formati della creazione di report elettronici per i codici IVA di tutte le persone giuridiche richieste.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Impostare i messaggi elettronici per raccogliere dati fiscali da diverse persone giuridiche

Segui questi passaggi per impostare i messaggi elettronici per raccogliere dati da più persone giuridiche.

1. Vai a **Aree di lavoro** > **Gestione funzionalità**.
2. Trova e seleziona la funzionalità **Query interaziendali per le azioni di popolamento dei record** nell'elenco, quindi seleziona **Abilita ora**.
3. Vai a **Imposta** > **Impostazione** > **Messaggi elettronici** > **Azioni di popolamento record**.
4. Nella pagina **Azione di popolamento record**, seleziona la riga per **CH Compila i record di dichiarazione IVA**.

   Nella griglia **Impostazione origini dati**, è disponibile un nuovo campo **Società**. Per i record esistenti, questo campo mostra l'identificatore della persona giuridica corrente.

5. Nella griglia **Impostazione origini dati**, aggiungi una riga per ogni persona giuridica aggiuntiva che deve essere inclusa nella dichiarazione. Per ogni nuova riga, imposta i seguenti campi.

   | Campo                  | descrizione                                                                                                                   |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
   | Nome                   | Inserisci un valore che ti aiuti a capire da dove proviene questo record. Ad esempio, inserisci **Pagamento IVA dell'affiliata 1**. |
   | Tipo di elemento del messaggio      | Seleziona **Dichiarazione IVA**. Questo valore è l'unico valore disponibile per tutti i record.                                    |
   | Tipo di account           | Seleziona **Tutto**.                                                                                                               |
   | Nome tabella master      | Specifica **TaxReportVoucher** per tutti i record.                                                                             |
   | Campo Numero documento  | Specifica **Voucher** per tutti i record.                                                                                      |
   | Campo Data documento    | Specifica **TransDate** per tutti i record.                                                                                    |
   | Campo Conto documento | Specifica **TaxPeriod** per tutti i record.                                                                                    |
   | Società                | Seleziona l'ID della persona giuridica.                                                                                            |
   | Query utente             | Questa casella di controllo viene selezionata automaticamente quando definisci i criteri selezionando **Modifica query**.                                 |

6. Per ogni nuova riga, seleziona **Modifica query** e indica un periodo di liquidazione per la persona giuridica specificata nel campo **Società** sulla riga.

   Al termine dell'impostazione, la funzione **Raccogli dati** nella pagina **Messaggi elettronici** raccoglie i pagamenti IVA da tutte le persone giuridiche definite.
