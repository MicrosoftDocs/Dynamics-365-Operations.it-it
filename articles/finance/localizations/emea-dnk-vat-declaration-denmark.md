---
title: Dichiarazione IVA (Danimarca)
description: Questo articolo descrive come impostare e generare una dichiarazione di imposta sul valore aggiunto (IVA) avanzata per la Danimarca.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 99c8b7a35258116adfe7433e884564d64dbf140f
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812134"
---
# <a name="vat-declaration-denmark"></a>Dichiarazione IVA (Danimarca)

[!include [banner](../includes/banner.md)]

Questo articolo descrive come impostare la dichiarazione di imposta sul valore aggiunto (IVA) per la Danimarca e visualizzarlo in anteprima in Microsoft Excel.

Per generare automaticamente il report, è necessario innanzitutto creare codici IVA sufficienti per mantenere una contabilità IVA separata per ogni casella della dichiarazione IVA avanzata. Inoltre, nei parametri specifici dell'applicazione del formato di Creazione di report elettronici per la dichiarazione IVA avanzata, è necessario associare i codici IVA al risultato delle ricerche per le caselle nella dichiarazione IVA.

Per la Danimarca, è necessario configurare **Ricerca campi report**. Per ulteriori informazioni su come impostare i parametri specifici dell'applicazione, vedi la sezione [Impostare i parametri specifici dell'applicazione per i campi della dichiarazione IVA](#set-up-application-specific-parameters) più avanti in questo articolo.

Nella tabella seguente, la colonna "Risultato ricerca" mostra il risultato della ricerca preconfigurato per una riga specifica della dichiarazione IVA nel formato della dichiarazione IVA. Utilizza queste informazioni per associare correttamente i codici IVA al risultato della ricerca e quindi alla riga della dichiarazione IVA.

### <a name="vat-declaration-overview"></a>Panoramica sulla dichiarazione IVA

La dichiarazione IVA in Danimarca contiene le seguenti informazioni.

**VAT a debito**

| Description                                                  | Tasse base/Importo imposte | Risultato della ricerca/Totale                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IVA a debito                                                   | Importo dell'imposta          | **OutputVAT**</br> **DomesticVATUseTax** (riportato anche nella casella "IVA a credito")                                                                                                                                                                                                                                                                       |
| IVA su merci e così via acquistati all'estero                           | Importo dell'imposta          | **PurchaseGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (riportato anche nella casella "IVA a credito")</br>**PurchaseGoodsEU** (l'imposta base è riportata in "Casella A - acquisizione di beni".)</br>**PurchaseGoodsEUUseTax** (l'importo delle imposte è inoltre riportato nella casella "IVA a credito". L'imposta base è riportata in "Casella A - acquisizione di beni".)                   |
| IVA su servizi acquistati all'estero soggetti a reverse charge | Importo dell'imposta          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (riportato anche nella casella "IVA a credito")</br>**PurchaseServicesEU** (L'imposta base è riportata in "Casella A - acquisizione di servizi".)</br>**PurchaseServicesEUUseTax** (l'importo delle imposte è inoltre riportato nella casella "IVA a credito". L'imposta base è riportata in "Casella A - acquisizione di servizi".) |
| Contabilità totale                                                | Importo dell'imposta          | Totale delle tre caselle precedenti                                                                                                                                                                                                                                                                                                            |

**Detrazioni**

| Description                                                                               | Tasse base/Importo imposte | Risultato della ricerca/Totale                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IVA a credito                                                                                 | Importo dell'imposta          | **InputVAT**</br> **DomesticVATUseTax** (riportato anche nella casella "IVA a debito")</br>**PurchaseGoodsAbroadUseTax** (riportato anche nella casella "IVA su merci acquistate all'estero)</br>**PurchaseServicesAbroadUseTax** (riportato anche nella casella "IVA sui servizi acquistati all'estero soggetta a IVA intracomunitaria)</br>**PurchaseGoodsEUUseTax** (riportato anche nella casella "IVA su merci acquistate all'estero)</br> **PurchaseServicesEUUseTax** (riportato anche nella casella "IVA sui servizi acquistati all'estero soggetta a IVA intracomunitaria) |
| Imposta su combustibile e gas in bombole                                                                  | Importo dell'imposta          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Imposta su energia/elettricità                                                                    | Importo dell'imposta          | **PowerElectricityDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Imposta su gas naturale e gas di città                                                             | Importo dell'imposta          | **NaturalTownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Imposta sul carbonio                                                                               | Importo dell'imposta          | **CarbonDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Importo dell'imposta          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Spese di acqua                                                                              | Importo dell'imposta          | **WaterCharge**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Detrazioni totali                                                                          | Importo dell'imposta          | Totale delle sei caselle precedenti                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Importo totale delle imposte (importo positivo = effettuare il pagamento, importo negativo = ricevere il rimborso) | Importo dell'imposta          | "Contabilità totale" – "Detrazioni totali"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Informazioni aggiuntive**

| Description                                                                                                                                                                                                                                | Tasse base/Importo imposte | Risultato della ricerca/Totale                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| Casella A - acquisto di merci. Il valore senza IVA dell'acquisto di merci intracomunitarie.                                                                                                                                                   | Imponibile            | **PurchaseGoodsEU PurchaseGoodsEUUseTax**       |
| Casella A - acquisto di servizi. Il valore senza IVA dell'acquisto di servizi intracomunitari.                                                                                                                                             | Imponibile            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| Casella B - fornitura di merci - da segnalare a "Vendite UE senza IVA"/DK VIES. Il valore senza IVA della fornitura di merci intracomunitarie                                                                                                           | Imponibile            | **SalesGoodsEU**                                |
| Casella B - forniture - da non segnalare a "Vendite UE senza IVA"/DK VIES. Il valore senza IVA di alcune forniture intracomunitarie, ad esempio di installazione, assemblaggio, vendite a distanza e nuovi mezzi di trasporto per le persone non imponibili. | Imponibile            | **SalesInstallationAssemblyEtcEU**              |
| Casella B - fornitura di servizi. Il valore senza IVA di forniture di servizi intracomunitari per i quali l'addetto acquisti è responsabile del pagamento dell'IVA come IVA intracomunitario: deve inoltre essere segnalato a "Vendite UE senza IVA"/DK VIES.                          | Imponibile            | **SalesServicesEU**                             |
| Casella C - altre forniture. Il valore della fornitura di altre merci e servizi forniti senza IVA nel territorio della Danimarca, ad altri Stati Membri dell'UE, e a paesi o territori terzi.                                     | Imponibile            | **OtherSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>Reverse charge per acquisti

Se configuri i codici IVA per registrare l'IVA reverse charge in entrata utilizzando l'imposta di utilizzo, associa i codici IVA al risultato della ricerca di **Ricerca campi report** che contiene "UseTax" nel nome.

In alternativa, è possibile configurare due codici IVA distinti: uno per l'IVA dovuta e uno per la detrazione dell'IVA. Quindi associa ogni codice ai risultati di ricerca corrispondenti di **Ricerca campi report**.

Ad esempio, per le acquisizioni intracomunitarie imponibili, configura il codice IVA **UT_S_EU** con l'imposta sull'uso e associala al risultato della ricerca **PurchaseGoodsEUUseTax** di **Ricerca campi report**. In questo caso, gli importi fiscali che utilizzano il codice IVA **UT_S_EU** sono riportati nelle caselle "IVA su merci acquistate all'estero e "IVA a credito". Le imposte base sono riportate nella "Casella A - acquisizione di beni".

In alternativa, configura due codici IVA:

- **VAT_S_EU**, che ha un valore di aliquota d’imposta del -25 percento
- **InVAT_S_EU**, che ha un valore di aliquota d’imposta del 25 percento

Quindi associ i codici ai risultati della ricerca di **Ricerca campi report** nel modo seguente:

- Associa **VAT_S_EU** al risultato della ricerca **PurchaseGoodsEU**.
- Associa **InVAT_S_EU** al risultato della ricerca **InputVAT**.

In questo caso, gli importi fiscali che utilizzano il codice IVA **VAT_S_EU** sono riportati nelle caselle "IVA su merci acquistate all'estero" e "Casella A - acquisto di merci". Gli importi che utilizzano il codice IVA **InVAT_S_EU** vengono riflessi nella casella "IVA a credito".

Per ulteriori informazioni su come configurare la reverse charge, vedi [Reverse charges](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurare i parametri di sistema

Per generare una dichiarazione IVA, è necessario configurare il numero IVA.

1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Seleziona la persona giuridica, quindi **ID registrazione**.
3. Seleziona o crea l'indirizzo in Danimarca, quindi, nella Scheda dettaglio **ID registrazione**, seleziona **Aggiungi**.
4. Nel campo **Tipo di registrazione**, seleziona il tipo di registrazione che è dedicato alla Danimarca e che utilizza la categoria di registrazione **Partita IVA**.
5. Nel campo **Numero di registrazione** immetti il numero imposta.
6. Nella scheda **Generale**, nel campo **Valido**, inserisci la data in cui il numero diventa valido.

Per ulteriori informazioni su come impostare le categorie di registrazione e i tipi di registrazione, vedi [ID registrazione](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Impostare un'anteprima della dichiarazione IVA per la Danimarca

### <a name="import-er-configurations"></a>Importare configurazioni ER

Apri l'area di lavoro **Creazione di report elettronici** e importa il formato ER **Excel di dichiarazione IVA (DK)**.

Per ulteriori informazioni, vedere [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a>Impostare i parametri specifici dell'applicazione per i campi della dichiarazione IVA

> [!NOTE]
> Consigliamo di abilitare la funzionalità **Utilizza parametri specifici dell'applicazione delle versioni precedenti dei formati ER** nell'area di lavoro **Gestione delle funzionalità**. Quando questa funzionalità è abilitata, i parametri configurati per la versione precedente di un formato ER diventano automaticamente applicabili alla versione successiva dello stesso formato. Se questa funzione non è abilitata, è necessario configurare i parametri specifici dell'applicazione in modo esplicito per ogni versione del formato. Abilitare la funzionalità **Utilizza parametri specifici dell'applicazione delle versioni precedenti dei formati ER** disponibile nell'area di lavoro **Gestione delle funzionalità** a partire dalla versione 10.0.23 di Finance. Per ulteriori informazioni su come impostare i parametri di un formato ER per ciascuna persona giuridica, vedi [Impostare i parametri di un formato ER per la persona giuridica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Per generare automaticamente una dichiarazione IVA, associa i codici IVA nell'applicazione e i risultati della ricerca nella configurazione della creazione di report elettronici.

Segui questi passaggi per definire quali codici IVA generano quali caselle nella dichiarazione IVA.

1. Vai ad **Aree di lavoro** > **Creazione di report elettronici** e seleziona **Configurazioni report**.
2. Seleziona la configurazione **Excel di dichiarazione IVA (DK)**, quindi seleziona **Configurazioni \> Impostazione dei parametri specifici dell'applicazione**.
3. Nella pagina **Parametri specifici dell'applicazione**, nella Scheda dettaglio **Ricerche** seleziona **Ricerca campi report**.
4. Nella Scheda dettaglio **Condizioni**, imposta i seguenti campi per associare i codici IVA e i campi del report.

    | Campo                  | Description                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Risultato della ricerca          | Seleziona il valore del campo del report. Per ulteriori informazioni sui valori e sulla loro assegnazione alle righe della dichiarazione IVA, vedi la sezione [Panoramica sulla dichiarazione IVA](#vat-declaration-overview) precedente in questo articolo.                                                                                               |
    | Codice imposta               | Seleziona il codice IVA da associare al campo del report. Le transazioni IVA registrate che utilizzano il codice IVA selezionato verranno raccolte nella casella appropriata della dichiarazione. Si consiglia di separare i codici IVA in modo tale che un codice IVA generi importi in una sola casella della dichiarazione. |
    | Classificatore di transazioni | Se sono stati creati codici IVA sufficienti per determinare una casella della dichiarazione, seleziona **\*Non vuoto\***. Se non hai creato un numero sufficiente di codici IVA in modo che un codice IVA generi importi in una sola casella della dichiarazione, puoi impostare un classificatore di transazioni. Sono disponibili i seguenti classificatori di transazioni:</br>-   **Acquisto**</br>-   **PurchaseExempt** (acquisto esente da tasse)</br>-   **PurchaseReverseCharge** (imposta a credito da reverse charge su acquisti)</br>-   **Vendite**</br>-   **SalesExempt** (vendita esente da tasse)</br>-   **SalesReverseCharge** (imposta a debito da reverse charge su acquisti o reverse charge su vendite)</br>-   **Imposta d'uso**. </br>Per ogni classificatore di transazioni è disponibile anche un classificatore per la nota di accredito. Ad esempio, uno di questi classificatori è **PurchaseCreditNote** (nota di accredito di acquisto).</br>Assicurati di creare due righe per ogni codice IVA: una con il valore del classificatore della transazione e l'altra con il classificatore della transazione per il valore della nota di credito. |


    > [!NOTE]
    > Associa tutti i codici IVA ai risultati della ricerca. Se i codici IVA non devono generare valori nella dichiarazione IVA, associali al risultato della ricerca **Altro**.

    ![Pagina Parametri specifici dell'applicazione.](media/7db74920fad66a0db7fad60758698cc0.png)


5. Nel campo **Stato**, modifica il valore in **Completato**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Impostare il formato di reporting IVA per visualizzare in anteprima gli importi in Excel

1. Nell'area di lavoro **Gestione funzionalità**, trova e seleziona **Report formato dichiarazione IVA** nell'elenco, quindi seleziona **Abilita ora**.
2. Vai a **Contabilità generale** > **Impostazione** > **Parametri di contabilità generale**.
3. Nella scheda **IVA**, nella Scheda dettaglio **Opzioni imposta**, nel campo **Mapping formato dichiarazione IVA**, seleziona il formato di creazione di report elettronici **Excel di dichiarazione IVA (DK)**.

   Questo formato viene stampato quando si esegue il report **Report IVA per periodo liquidazione**. Viene anche stampato quando si seleziona **Stampa** nella pagina **Pagamenti IVA**.

4. Nella pagina **Uffici IVA**, seleziona l'ufficio IVA, quindi nel campo **Layout del report**, seleziona **Predefinito**.

Se stai configurando la dichiarazione IVA in una persona giuridica che ha [più partite IVA](emea-reporting-for-multiple-vat-registrations.md), segui questi passaggi.

1. Vai a **Contabilità generale** \> **Impostazione** \> **Parametri di contabilità generale**.
2. Nella scheda **IVA**, nella Scheda dettaglio **Creazione di report elettronici per paesi/aree geografiche**, alla riga per **DNK** seleziona il formato della creazione di report elettronici **Excel di dichiarazione IVA (DK)**.

## <a name="set-up-electronic-messages"></a>Impostare i messaggi elettronici

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Scaricare e importare il pacchetto di dati con impostazioni di esempio per i messaggi elettronici

Il pacchetto dati contiene le impostazioni per i messaggi elettronici che vengono utilizzate per visualizzare in anteprima la dichiarazione IVA in Excel. Puoi estendere queste impostazioni o crearne di tue. Per ulteriori informazioni su come utilizzare con la messaggistica elettronica e creare le proprie impostazioni, vedi [Messaggistica elettronica](../general-ledger/electronic-messaging.md).

1. In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), nella raccolta di risorse condivise, seleziona **Pacchetto dati** come tipo di risorsa, quindi scarica **Pacchetto dichiarazione IVA DK**. Il file scaricato si chiama **DK VAT declaration package.zip**.
2. In Finance, nell'area di lavoro **Gestione dati** seleziona **Importa**.
3. Nella Scheda dettaglio **Importa**, nel campo **Nome gruppo** immetti un nome per il processo.
4. Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi file**.
5. Nella finestra di dialogo **Aggiungi file**, verifica che il campo **Formato dati di origine** sia impostato su **Pacchetto**, seleziona **Carica e aggiungi**, quindi seleziona il file zip scaricato in precedenza.
6. Selezionare **Chiudi**.
7. Dopo che le entità di dati sono state caricate, nel riquadro Azioni seleziona **Importa**.
8. Vai a **Imposta** > **Richieste di informazioni e report** > **Messaggi elettronici** > **Messaggi elettronici** e convalida l'elaborazione del messaggio elettronico importato (**Dichiarazione IVA DK**).

### <a name="configure-electronic-messages"></a>Configurare i messaggi elettronici

1. Vai a **Imposta** > **Impostazione** > **Messaggi elettronici** > **Azioni di popolamento record**.
2. Seleziona la riga per **Compila i record di dichiarazione IVA DK**, quindi seleziona **Modifica query**.
3. Utilizza il filtro per specificare i periodi di liquidazione da includere nel report.
4. Se devi riportare le transazioni fiscali di altri periodi di liquidazione in una dichiarazione diversa, crea una nuova azione **Popola record** e seleziona i periodi di liquidazione appropriati.

## <a name="preview-the-vat-declaration-in-excel"></a>Visualizzare in anteprima la dichiarazione IVA in Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a>Visualizzare in anteprima la dichiarazione IVA in Excel dall'attività periodica Report IVA per periodo liquidazione

1. Vai a **Imposta** > **Attività periodiche** > **Dichiarazioni** > **IVA** > **Report IVA per periodo liquidazione**.
2. Nel campo **Periodo di liquidazione** seleziona un valore.
3. Nel campo **Versione pagamento IVA**, seleziona uno dei seguenti valori:

    - **Originale**: genera un report per le transazioni IVA del pagamento IVA originale o prima che venga generato il pagamento IVA.
    - **Correzioni**: genera un report per le transazioni IVA di tutti i pagamenti IVA successivi per il periodo.
    - **Elenco totale**: genera un report per tutte le transazioni IVA per il periodo, incluse l'originale e tutte le correzioni.

4. Seleziona la data di inizio del periodo di dichiarazione nel campo **Dal**.
5. Seleziona **OK** ed esamina il report Excel.

### <a name="settle-and-post-sales-tax"></a>Liquida e registra IVA

1. Vai a **Imposta** > **Attività periodiche** > **Dichiarazioni** > **IVA** > **Liquida e registra IVA**.
2. Nel campo **Periodo di liquidazione** seleziona un valore.
3. Nel campo **Versione pagamento IVA**, seleziona uno dei seguenti valori:

    - **Originale**: genera il pagamento IVA originale per il periodo di liquidazione.
    - **Ultime correzioni**: genera un pagamento IVA di correzione dopo la creazione del pagamento IVA originale per il periodo di liquidazione.

4. Seleziona la data di inizio del periodo di dichiarazione nel campo **Dal**.
5. Seleziona **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Visualizzare in anteprima la dichiarazione IVA in Excel da un pagamento IVA

1. Vai a **Imposta** > **Richieste di informazioni e report** > **Richieste di informazioni su IVA** > **Pagamenti IVA** e seleziona una riga di pagamento IVA.
2. Seleziona **Stampa report** quindi seleziona **OK**.
3. Esamina il file Excel generato per la riga di pagamento IVA selezionata.

> [!NOTE]
> Il report viene generato solo per la riga selezionata del pagamento IVA. Se è necessario generare, ad esempio, una dichiarazione correttiva che contenga tutte le correzioni per il periodo o una dichiarazione sostitutiva che contenga i dati originali e tutte le correzioni, utilizza l'attività periodica **Report IVA per periodo liquidazione**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Generare una dichiarazione IVA dai messaggi elettronici

Quando si utilizzano messaggi elettronici per generare il report, è possibile raccogliere dati fiscali da più persone giuridiche. Per ulteriori informazioni, vedi la sezione [Eseguire una dichiarazione IVA per più persone giuridiche](#run-vat-declaration) più avanti in questo articolo.

La procedura seguente si applica all'elaborazione di messaggi elettronici di esempio importata in precedenza dalla raccolta di risorse condivise LCS.

1. Vai a **Imposta \> Richieste di informazioni e report \> Messaggi elettronici \> Messaggi elettronici**.
2. Nel riquadro a sinistra, seleziona **Dichiarazione IVA DK**.
3. Nella Scheda dettaglio **Messaggi**, seleziona **Nuovo**, quindi nella finestra di dialogo **Esegui elaborazione** seleziona **OK**.
4. Seleziona la riga del messaggio creata, immetti una descrizione e quindi specifica le date di inizio e di fine per la dichiarazione.

   > [!NOTE]
   > I passaggi da 5 a 7 sono facoltativi.

5. Facoltativo: nella Scheda dettaglio **Messaggi**, seleziona **Raccogli dati**, quindi seleziona **OK**. I pagamenti IVA generati in precedenza vengono aggiunti al messaggio. Per ulteriori informazioni, vedi la sezione [Liquida e registra IVA](#settle-and-post-sales-tax) descritta precedentemente in questo articolo. Se salti questo passaggio, puoi comunque generare una dichiarazione IVA utilizzando il campo **Versione dichiarazione fiscale** nella finestra di dialogo **Dichiarazione**.
6. Facoltativo: nella Scheda dettaglio **Elementi del messaggio**, rivedi i pagamenti IVA trasferiti per l'elaborazione. Per impostazione predefinita, sono inclusi tutti i pagamenti IVA del periodo selezionato che non sono stati inclusi in nessun altro messaggio della stessa elaborazione.
7. Facoltativo: seleziona **Documento originale** per rivedere i pagamenti IVA o seleziona **Elimina** per escludere i pagamenti IVA dall'elaborazione. Se salti questo passaggio, puoi comunque generare una dichiarazione IVA utilizzando il campo **Versione dichiarazione fiscale** nella finestra di dialogo **Dichiarazione**.
8. Nella Scheda dettaglio **Messaggi**, seleziona **Aggiorna stato**. Nella finestra di dialogo **Aggiorna stato**, seleziona **Pronto a generare**, quindi seleziona **OK**. Verifica che lo stato del messaggio sia cambiato in **Pronto a generare**.
9. Seleziona **Genera report**. Per visualizzare in anteprima gli importi della dichiarazione IVA, nella finestra di dialogo **Esegui elaborazione** seleziona **Anteprima report**, quindi seleziona **OK**.
10. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, imposta i campi come descritto nella sezione [Visualizzare in anteprima la dichiarazione IVA in Excel dall'attività periodica Report IVA per periodo liquidazione](#preview-vat-excel) in alto in questo articolo, quindi seleziona **OK**.
11. Seleziona il pulsante **Allegati** (simbolo della graffetta) nell'angolo in alto a destra della pagina, quindi seleziona **Apri** per aprire il file. Rivedi gli importi nel documento Excel.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a>Eseguire una dichiarazione IVA per più persone giuridiche

Per utilizzare i formati per riportare la dichiarazione IVA per un gruppo di persone giuridiche, è necessario prima impostare i parametri specifici dell'applicazione dei formati della creazione di report elettronici per i codici IVA di tutte le persone giuridiche richieste.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Impostare i messaggi elettronici per raccogliere dati fiscali da diverse persone giuridiche

Segui questi passaggi per impostare i messaggi elettronici per raccogliere dati da più persone giuridiche.

1. Vai a **Aree di lavoro** > **Gestione funzionalità**.
2. Trova e seleziona la funzionalità **Query interaziendali per le azioni di popolamento dei record** nell'elenco, quindi seleziona **Abilita ora**.
3. Vai a **Imposta** > **Impostazione** > **Messaggi elettronici** > **Azioni di popolamento record**.
4. Nella pagina **Azione di popolamento record**, seleziona la riga per **Compila i record di dichiarazione IVA DK**.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
