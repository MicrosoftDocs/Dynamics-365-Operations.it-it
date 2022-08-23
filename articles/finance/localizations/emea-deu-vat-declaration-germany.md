---
title: Dichiarazione IVA (Germania)
description: Questo articolo descrive come impostare e generare una dichiarazione di imposta sul valore aggiunto (IVA) avanzata per la Germania nel formato XML ufficiale.
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 8ee288a1ec7ae950bdff9da7d373e29daef74d3c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269406"
---
# <a name="vat-declaration-germany"></a>Dichiarazione IVA (Germania)

[!include [banner](../includes/banner.md)]

Questo articolo descrive come impostare e generare una dichiarazione di imposta sul valore aggiunto (IVA) avanzata per la Germania nel formato XML ufficiale. Questo articolo descrive inoltre come visualizzare in anteprima la dichiarazione IVA in Microsoft Excel.

Per generare automaticamente il report, è necessario innanzitutto creare codici IVA sufficienti per mantenere una contabilità IVA separata per ogni casella della dichiarazione IVA avanzata. Inoltre, nei parametri specifici dell'applicazione del formato di Creazione di report elettronici per la dichiarazione IVA avanzata, è necessario associare i codici IVA al risultato delle ricerche per le caselle nella dichiarazione IVA.

Per la Germania, è necessario configurare **Ricerca campi report**. Per ulteriori informazioni su come impostare i parametri specifici dell'applicazione, vedi la sezione [Impostare i parametri specifici dell'applicazione per i campi della dichiarazione IVA](#set-up-application-specific-parameters-for-vat-declaration-fields) più avanti in questo articolo.

Nella tabella seguente, la colonna "Risultato ricerca" mostra il risultato della ricerca preconfigurato per una riga specifica della dichiarazione IVA nel formato della dichiarazione IVA. Utilizza queste informazioni per associare correttamente i codici IVA al risultato della ricerca e quindi alla riga della dichiarazione IVA.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>Panoramica sulla dichiarazione IVA

La dichiarazione IVA avanzata in Germania contiene le seguenti informazioni.

**SEZIONE – CONSEGNE E ALTRI SERVIZI**

**Vendite tassabili**

| Riga | Casella - Imposta base | Casella - Importo imposta | Description                                                                                                                                      | Risultato della ricerca                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Senza codice     | Vendite imponibili con un'aliquota del 19%.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) – con segno meno             |
| 21  | 86             | Senza codice     | Vendite imponibili con un'aliquota del 7%.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced (86/50) – con segno meno               |
| 22  | 35             | 36               | Vendite imponibili ad altre aliquote fiscali.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) – con segno meno      |
| 23  | 77             | *Nessun importo imposta*  | Consegne da aziende agricole e forestali ai sensi del §24 della legge tedesca sull'IVA (UStG) a clienti che hanno un numero di partita IVA. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) – con segno meno |
| 24  | 76             | 80               | Vendite per le quali deve essere pagata un'imposta, ai sensi del §24 dell'UStG (prodotti di segheria, bevande e liquidi alcolici).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Vendite esentasse con detrazione dell'imposta a monte**

| Riga | Casella - Imposta base | Casella - Importo imposta | Description                                                                       | Risultato della ricerca                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Nessun importo imposta*  | Consegne intracomunitarie a clienti titolari di partita IVA.                       | 26-EUSales                          |
| 27  | 44             | *Nessun importo imposta*  | Consegne intracomunitarie di veicoli nuovi ad acquirenti privi di partita IVA.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Nessun importo imposta*  | Consegne intracomunitarie di veicoli nuovi al di fuori di un'azienda.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Nessun importo imposta*  | Altre vendite esentasse che hanno una detrazione dell'imposta a monte, come le consegne di esportazione. | 29-ExportOtherTaxFreeSales          |

**Vendite esentasse senza detrazione dell'imposta a monte**

| Riga | Casella - Imposta base | Casella - Importo imposta | Description                                            | Risultato della ricerca                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Nessun importo imposta*  | Vendite esentasse che non hanno una detrazione dell'imposta a monte. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Acquisizioni intracomunitarie**

| Riga | Casella - Imposta base | Casella - Importo imposta | Description                                                                                                                   | Risultato della ricerca                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Nessun importo imposta*  | Acquisti intracomunitari esentasse di alcuni oggetti e oro da investimento.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Senza codice     | Acquisti intracomunitari imponibili ad un'aliquota del 19%.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Senza codice     | Acquisti intracomunitari imponibili ad un'aliquota del 7%.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced (93/61)          |
| 36  | 95             | 98               | Acquisti intracomunitari imponibili ad altre aliquote.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Acquisti imponibili intracomunitari di nuovi veicoli da fornitori che non hanno un numero di partita IVA, all'aliquota fiscale generale. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**SEZIONE – BENEFICIARIO COME DEBITORE FISCALE**

| Riga | Casella - Imposta base | Casella - Importo imposta | Description                                                                        | Risultato della ricerca                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Altri servizi di un imprenditore, basati sul resto dell'area community.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | Vendite che rientrano nella sezione 13b (2) n. 3 di UStG.                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | Altri servizi che rientrano nella sezione 13b (2) n. 1, 2 e da 4 a 12 di UStG. | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                           |

**SEZIONE – INFORMAZIONI SUPPLEMENTARI SULLE VENDITE**

| Riga | Casella - Imposta base  | Casella - Importo imposta | Description                                                                                                | Risultato della ricerca                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Nessun importo imposta*  | Consegne da parte del primo cliente in caso di operazioni triangolari intracomunitarie.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Nessun importo imposta*  | Vendite imponibili dell'imprenditore per le quali il destinatario del servizio deve pagare l'imposta. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Nessun importo imposta*  | Altri servizi non imponibili.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Nessun importo imposta*  | Altre vendite non imponibili quando il luogo di adempimento non è in Germania.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *Nessun importo imposta* | *Nessun importo imposta*  | IVA.                                                                                                       | Riga 20 + Riga 21 + Riga 22 + Riga 2 4 + Riga 34 + Riga 35 + Riga 36 + Riga 37 + Riga 40 + Riga 41 + Riga 42 |

**SEZIONE – IMPOSTA A MONTE DETRAIBILE**

| Riga | Casella - Importo imposta | Description                                                                                                | Risultato della ricerca                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Importi di imposte a monte delle fatture da altre società, servizi e transazioni triangolari intracomunitarie.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – con segno meno                                                                   |
| 56  | 61               | Importi dell'imposta a monte da acquisizione intracomunitaria di beni.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | IVA di importazione sostenuta.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Importi dell'imposta a monte dai servizi ai sensi del §13b di UStG.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                                                 |
| 59  | 63               | Importi dell'imposta a monte calcolati in base alle aliquote medie generali.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) – con segno meno                                                                                    |
| 60  | 59               | Detrazione dell'imposta a monte per consegne intracomunitarie di veicoli nuovi al di fuori di un'azienda e piccole imprese. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) – con segno meno                                                                  |
| 61  | 64               | Rettifica della detrazione dell'imposta a monte.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | Importo rimanente.                                                                                      | Riga 52 – Riga 55 – Riga 56 – Riga 57 – Riga 58 – Riga 50 – Riga 60 – Riga 61                                                                                                        |

**SEZIONE – ALTRI IMPORTI DI IMPOSTE**

| Riga | Casella - Importo imposta | Description                                                                                                                                                                                                                                                         | Risultato della ricerca                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Imposta a causa di una modifica della forma di tassazione e imposta addizionale sugli acconti imponibili a causa della modifica dell'aliquota fiscale.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | Importi fiscali errati o ingiustificati indicati nelle fatture e importi dovuti ai sensi della sezione 6a (4) frase 2, sezione 17 (1) frase 7 o sezione 25b (2) di UStG, o che sono dovuti da una società di outsourcing o un magazziniere. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | Detrazione del pagamento anticipato speciale fisso per proroga permanente. In genere questa riga viene compilata solo con l'ultima notifica anticipata del periodo d'imposta.                                                                                                  | Parametro di input dell'utente nella finestra di dialogo del report |
| 68  | 83               | Il restante pagamento anticipato dell'imposta sulle vendite e l'eccedenza residua. Includi un segno negativo davanti all'importo.                                                                                                                                                          | Riga 62 + Riga 64 – Riga 65 – Riga 66             |

**SEZIONE – INFORMAZIONI SUPPLEMENTARI SULLE RIDUZIONI**

| Riga | Casella - Imposta base | Casella - Importo imposta | Description                                                            | Risultato della ricerca                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Riduzione della base imponibile sulle righe da 20 a 24.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | Riduzione degli importi dell'imposta a monte detraibile alle righe 55, 59 e 60. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>Reverse charge per acquisti

Se configuri i codici IVA per registrare l'IVA reverse charge in entrata utilizzando l'imposta di utilizzo, associa i codici IVA al risultato della ricerca di **Ricerca campi report** che contiene "UseTax" nel nome.

In alternativa, è possibile configurare due codici IVA distinti: uno per l'IVA dovuta e uno per la detrazione dell'IVA. Quindi associa ogni codice ai risultati di ricerca corrispondenti di **Ricerca campi report**.

Ad esempio, per le acquisizioni intracomunitarie imponibili a un'aliquota standard, configura il codice IVA **UT_S_EU** con l'imposta sull'uso e associala al risultato della ricerca **34-UseTaxEUPurchaseStandard** di **Ricerca campi report**. In questo caso, gli importi che utilizzano il codice IVA **UT_S_EU** sono riportati nelle caselle 089 e 061 (righe 34 e 56).

In alternativa, configura due codici IVA:

  - **VAT_S_EU**, che ha un valore di aliquota d’imposta del -19 percento
  - **InVAT_S_EU**, che ha un valore di aliquota d’imposta del 19 percento

Quindi associ i codici ai risultati della ricerca di **Ricerca campi report** nel modo seguente:

  - Associa **VAT_S_EU** al risultato della ricerca **34-EUPurchaseStandard**.
  - Associa **InVAT_S_EU** al risultato della ricerca **56-InputTaxEUPurchase**.

In questo caso, gli importi che utilizzano il codice IVA **VAT_S_EU** vengono riportati nella casella 089 (riga 34). Gli importi che utilizzano il codice IVA **InVAT_S_EU** vengono riportati nella casella 061 (riga 56).

Per ulteriori informazioni su come configurare la reverse charge, vedi [Reverse charges](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configurare i parametri di sistema

Per generare una dichiarazione IVA, devi configurare il numero imposta (Steuernummer) della tua organizzazione.

1. Vai a **Amministrazione organizzazione** > **Organizzazioni** > **Persone giuridiche**.
2. Seleziona la persona giuridica, quindi **ID registrazione**.
3. Seleziona o crea l'indirizzo in Germania, quindi, nella Scheda dettaglio **ID registrazione**, seleziona **Aggiungi**.
4. Nel campo **Tipo di registrazione**, seleziona il tipo di registrazione che è dedicato alla Germania e che utilizza la categoria di registrazione **ID azienda (COID)**.
5. Nel campo **Numero di registrazione** immetti il numero imposta.
6. Nella scheda **Generale**, nel campo **Valido**, inserisci la data in cui il numero diventa valido.

Per ulteriori informazioni su come impostare le categorie di registrazione e i tipi di registrazione, vedi [ID registrazione](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Impostare una dichiarazione IVA per la Germania

### <a name="import-er-configurations"></a>Importare configurazioni ER

Apri l'area di lavoro **Creazione di report elettronici** e importa le seguenti versioni o successive di questi formati della creazione di report elettronici:

   - Excel di dichiarazione IVA (DE).version.101.16.12.xml
   - XML di dichiarazione IVA (DE).version.101.16.12.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Impostare i parametri specifici dell'applicazione per i campi della dichiarazione IVA

Per generare automaticamente una dichiarazione IVA, associa i codici IVA nell'applicazione e i risultati della ricerca nella configurazione della creazione di report elettronici.

> [!NOTE]
> Consigliamo di abilitare la funzionalità **Utilizza parametri specifici dell'applicazione delle versioni precedenti dei formati ER** nell'area di lavoro **Gestione delle funzionalità**. Quando questa funzionalità è abilitata, i parametri configurati per la versione precedente di un formato ER diventano automaticamente applicabili alla versione successiva dello stesso formato. Se questa funzione non è abilitata, è necessario configurare i parametri specifici dell'applicazione in modo esplicito per ogni versione del formato. Abilitare la funzionalità **Utilizza parametri specifici dell'applicazione delle versioni precedenti dei formati ER** disponibile nell'area di lavoro **Gestione delle funzionalità** a partire dalla versione 10.0.23 di Finance. Per ulteriori informazioni su come impostare i parametri di un formato ER per ciascuna persona giuridica, vedi [Impostare i parametri di un formato ER per la persona giuridica](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Segui questi passaggi per definire quali codici IVA generano quali caselle nella dichiarazione IVA.

1. Vai ad **Aree di lavoro** > **Creazione di report elettronici** e seleziona **Configurazioni report**.
2. Seleziona la configurazione **XML di dichiarazione IVA (DE)**, quindi seleziona **Configurazioni \> Impostazione dei parametri specifici dell'applicazione**.
3. Nella pagina **Parametri specifici dell'applicazione**, nella Scheda dettaglio **Ricerche** seleziona **Ricerca campi report**.
4. Nella Scheda dettaglio **Condizioni**, imposta i seguenti campi per associare i codici IVA e i campi del report.

    | Campo                  | Description                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Risultato della ricerca          | Seleziona il valore del campo del report. Per ulteriori informazioni sui valori e sulla loro assegnazione alle righe della dichiarazione IVA, vedi la sezione [Panoramica sulla dichiarazione IVA](#vat-declaration-overview) precedente in questo articolo.                                                                                               |
    | Codice imposta               | Seleziona il codice IVA da associare al campo del report. Le transazioni IVA registrate che utilizzano il codice IVA selezionato verranno raccolte nella casella appropriata della dichiarazione. Si consiglia di separare i codici IVA in modo tale che un codice IVA generi importi in una sola casella della dichiarazione. |
    | Classificatore di transazioni | Se sono stati creati codici IVA sufficienti per determinare una casella della dichiarazione, seleziona **\*Non vuoto\***. Se non hai creato un numero sufficiente di codici IVA in modo che un codice IVA generi importi in una sola casella della dichiarazione, puoi impostare un classificatore di transazioni. Sono disponibili i seguenti classificatori di transazioni:</br>-   **Acquisto**</br>-   **PurchaseExempt** (acquisto esente da tasse)</br>-   **PurchaseReverseCharge** (imposta a credito da reverse charge su acquisti)</br>-   **Vendite**</br>-   **SalesExempt** (vendita esente da tasse)</br>-   **SalesReverseCharge** (imposta a debito da reverse charge su acquisti o reverse charge su vendite)</br>-   **Imposta d'uso**. </br>Per ogni classificatore di transazioni è disponibile anche un classificatore per la nota di accredito. Ad esempio, uno di questi classificatori è **PurchaseCreditNote** (nota di accredito di acquisto).</br>Assicurati di creare due righe per ogni codice IVA: una con il valore del classificatore della transazione e l'altra con il classificatore della transazione per il valore della nota di credito. |

    > [!NOTE]
    > Associa tutti i codici IVA ai risultati della ricerca. Se i codici IVA non devono generare valori nella dichiarazione IVA, associali al risultato della ricerca **Altro**.

    ![Pagina Parametri specifici dell'applicazione](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. Nel campo **Stato**, modifica il valore in **Completato**.
6. Nel riquadro Azioni, seleziona **Esporta** per esportare le impostazioni dei parametri specifici dell'applicazione.
7. Seleziona la configurazione **Excel di dichiarazione IVA (DE)**, quindi, nel riquadro Azioni, seleziona **Importa** per importare i parametri che hai configurato per **XML di dichiarazione IVA (DE)**.
8. Nel campo **Stato** selezionare **Completato**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Impostare il formato di reporting IVA per visualizzare in anteprima gli importi in Excel

1. Nell'area di lavoro **Gestione funzionalità**, trova e abilita la funzionalità **Report formato dichiarazione IVA**.
2. Vai a **Contabilità generale** > **Impostazione** > **Parametri di contabilità generale**.
3. Nella scheda **IVA**, nella Scheda dettaglio **Opzioni imposta**, nel campo **Mapping formato dichiarazione IVA**, selezionare **Excel di dichiarazione IVA (DE)**.

   Questo formato viene stampato quando si esegue il report **Report IVA per periodo liquidazione**. Viene anche stampato quando si seleziona **Stampa** nella pagina **Pagamenti IVA**.

4. Nella pagina **Uffici IVA**, seleziona l'ufficio IVA, quindi nel campo **Layout del report**, seleziona **Predefinito**.

Se stai configurando la dichiarazione IVA in una persona giuridica che ha [più partite IVA](emea-reporting-for-multiple-vat-registrations.md), segui questi passaggi:

1. Vai a **Contabilità generale** > **Impostazione** > **Parametri di contabilità generale**.
2. Nella scheda **IVA**, nella Scheda dettaglio **Creazione di report elettronici per paesi/aree geografiche**, alla riga per **DEU** seleziona il formato della creazione di report elettronici **Excel di dichiarazione IVA (DE)**.

## <a name="set-up-electronic-messages"></a>Impostare i messaggi elettronici

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Scaricare e importare il pacchetto di dati con impostazioni di esempio per i messaggi elettronici

Il pacchetto dati contiene le impostazioni per i messaggi elettronici che vengono utilizzate per generare la dichiarazione IVA in formato XML e visualizzarne l'anteprima in Excel. Puoi estendere queste impostazioni o crearne di tue. Per ulteriori informazioni su come utilizzare con la messaggistica elettronica e creare le proprie impostazioni, vedi [Messaggistica elettronica](../general-ledger/electronic-messaging.md).

1. In [Microsoft Dynamics Lifecycle Services(LCS)](https://lcs.dynamics.com/v2), nella raccolta di risorse condivise, seleziona **Pacchetto dati** come tipo di risorsa, quindi scarica **Pacchetto EM dichiarazione IVA DE**. Il file scaricato si chiama **DE VAT declaration EM package.zip**.
2. In Dynamics 365 Finance, nell'area di lavoro **Gestione dati** seleziona **Importa**.
3. Nella Scheda dettaglio **Importa**, nel campo **Nome gruppo** immetti un nome per il processo.
4. Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi file**.
5. Nella finestra di dialogo **Aggiungi file**, verifica che il campo **Formato dati di origine** sia impostato su **Pacchetto**, seleziona **Carica e aggiungi**, quindi seleziona il file zip scaricato in precedenza.
6. Selezionare **Chiudi**.
7. Dopo che le entità di dati sono state caricate, nel riquadro Azioni seleziona **Importa**.
8. Vai a **Imposta** > **Richieste di informazioni e report** > **Messaggi elettronici** > **Messaggi elettronici**, e convalida l'elaborazione del messaggio elettronico importato.

### <a name="configure-electronic-messages"></a>Configurare i messaggi elettronici

1. Vai a **Imposta** > **Impostazione** > **Messaggi elettronici** > **Azioni di popolamento record**.
2. Seleziona la riga per **DE Compila i record di dichiarazione IVA**, quindi seleziona **Modifica query**.
3. Utilizza il filtro per specificare i periodi di liquidazione da includere nel report.
4. Se devi riportare le transazioni fiscali di altri periodi di liquidazione in una dichiarazione diversa, crea una nuova azione **Popola record** e seleziona i periodi di liquidazione appropriati.

## <a name="preview-the-vat-declaration-in-excel"></a>Visualizzare in anteprima la dichiarazione IVA in Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Visualizzare in anteprima la dichiarazione IVA in Excel dall'attività periodica Report IVA per periodo liquidazione

1. Vai a **Imposta** > **Attività periodiche** > **Dichiarazioni** > **IVA** > **Report IVA per periodo liquidazione**.
2. Nel campo **Periodo di liquidazione** seleziona un valore.
3. Nel campo **Versione pagamento IVA**, seleziona uno dei seguenti valori:

    - **Originale**: genera un report per le transazioni IVA del pagamento IVA originale o prima che venga generato il pagamento IVA.
    - **Correzioni**: genera un report per le transazioni IVA di tutti i pagamenti IVA successivi per il periodo.
    - **Elenco totale**: genera un report per tutte le transazioni IVA per il periodo, incluse l'originale e tutte le correzioni.

4. Seleziona la data di inizio del periodo di dichiarazione nel campo **Dal**.
5. Seleziona **OK** ed esamina il report Excel.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Liquida e registra IVA

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

Quando si utilizzano messaggi elettronici per generare il report, è possibile raccogliere dati fiscali da più persone giuridiche. Per ulteriori informazioni, vedi la sezione [Eseguire una dichiarazione IVA per più persone giuridiche](#run-a-vat-declaration-for-multiple-legal-entities) più avanti in questo articolo.

La procedura seguente si applica all'elaborazione di messaggi elettronici di esempio importata dalla raccolta di risorse condivise LCS.

1. Vai a **Imposta** > **Richieste di informazioni e report** > **Messaggi elettronici** > **Messaggi elettronici**.
2. Nel riquadro a sinistra, seleziona **Dichiarazione IVA DE**.
3. Nella Scheda dettaglio **Messaggi**, seleziona **Nuovo**, quindi nella finestra di dialogo **Esegui elaborazione** seleziona **OK**.
4. Seleziona la riga del messaggio creata, immetti una descrizione e quindi specifica le date di inizio e di fine per la dichiarazione.

    > [!NOTE]
    > I passaggi da 5 a 7 sono facoltativi.

5. Facoltativo: nella Scheda dettaglio **Messaggi**, seleziona **Raccogli dati**, quindi seleziona **OK**. I pagamenti IVA generati in precedenza vengono aggiunti al messaggio. Per ulteriori informazioni, vedi la sezione [Liquida e registra IVA](#settle-and-post-sales-tax) descritta precedentemente in questo articolo. Se salti questo passaggio, puoi comunque generare una dichiarazione IVA utilizzando il campo **Versione dichiarazione fiscale** nella finestra di dialogo **Dichiarazione**.
6. Facoltativo: nella Scheda dettaglio **Elementi del messaggio**, rivedi i pagamenti IVA trasferiti per l'elaborazione. Per impostazione predefinita, sono inclusi tutti i pagamenti IVA del periodo selezionato che non sono stati inclusi in nessun altro messaggio della stessa elaborazione.
7. Facoltativo: seleziona **Documento originale** per rivedere i pagamenti IVA o seleziona **Elimina** per escludere i pagamenti IVA dall'elaborazione. Se salti questo passaggio, puoi comunque generare una dichiarazione IVA utilizzando il campo **Versione dichiarazione fiscale** nella finestra di dialogo **Dichiarazione**.
8. Nella Scheda dettaglio **Messaggi**, seleziona **Aggiorna stato**. Nella finestra di dialogo **Aggiorna stato**, seleziona **Pronto a generare**, quindi seleziona **OK**. Verifica che lo stato del messaggio sia cambiato in **Pronto a generare**.
9. Seleziona **Genera report**. Per visualizzare in anteprima gli importi della dichiarazione IVA, nella finestra di dialogo **Esegui elaborazione** seleziona **Anteprima report**, quindi seleziona **OK**.
10. Nella finestra di dialogo **Parametri per la creazione di report elettronici** imposta i seguenti campi, quindi seleziona **OK**.

    | **Campo**                                   | **Descrizione**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Periodo di liquidazione                           | Seleziona il periodo di liquidazione. Se hai selezionato **Raccogli dati** al passaggio 5, puoi lasciare questo campo vuoto. Il report verrà generato per le transazioni IVA incluse nei pagamenti IVA riscossi. |
    | Versione dichiarazione fiscale                     | Selezionare uno dei seguenti valori:</br>-   **Originale**: genera un report per le transazioni IVA del pagamento IVA originale o prima che venga generato il pagamento IVA.</br>-   **Correzioni**: genera un report per le transazioni IVA di tutti i pagamenti IVA successivi per il periodo.</br>-   **Elenco totale**: genera un report per tutte le transazioni IVA per il periodo, incluse l'originale e tutte le correzioni.|
    | Rappresentante fiscale | Seleziona la parte che è un rappresentante fiscale per la dichiarazione IVA, se applicabile. Le informazioni sulla parte selezionata vengono esportate nell'elemento XML **DatenLieferant**. |
    | Contatto | Seleziona una persona nell'organizzazione come fornitore di dati. Le informazioni sulla persona selezionata vengono esportate nell'elemento XML **DatenLieferant**. |
    | Dichiarazione correttiva | Seleziona **Sì** se questa è una dichiarazione IVA correttiva. In questo caso, l'elemento XML KZ10 avrà un valore di **1**.|
    | Documenti giustificativi | Seleziona **Sì** se invii anche documenti di supporto. In questo caso, l'elemento XML KZ22 avrà un valore di **1**.|
    | Il mandato di addebito diretto SEPA viene revocato come eccezione| Seleziona **Sì** se il mandato di addebito diretto SEPA verrà revocato in via eccezionale per questo periodo di preregistrazione. Ad esempio, a causa delle richieste di compensazione. L'eventuale saldo residuo è da pagare a parte. In questo caso, l'elemento XML KZ26 avrà un valore di **1**. |
    | Compensazione dell'importo del rimborso desiderato | Seleziona **Sì** in caso di compensazione dell'importo del rimborso voluto o se l'importo del rimborso è stato assegnato. In questo caso, l'elemento XML KZ29 avrà un valore di **1**. |
    | Speciale estensione permanente del pagamento anticipato | Immetti l'importo di detrazione del pagamento anticipato speciale fisso per proroga permanente. Questo importo di detrazione viene solitamente completato solo nell'ultima preregistrazione del periodo d'imposta. L'importo viene esportato nella riga 67 (casella 39) e nell'elemento XML KZ39 della dichiarazione IVA. |

11. Seleziona **Allegati** nell'angolo superiore destro della pagina e scegli **Apri**.
12. Rivedi gli importi nel documento Excel, quindi seleziona **Genera report**.
13. Per generare una dichiarazione IVA in formato XML, nella finestra di dialogo **Esegui elaborazione** seleziona **Genera report**, quindi seleziona **OK**.
14. Nella finestra di dialogo **Parametri per la creazione di report elettronici** imposta i campi come descritto al passaggio 10.
15. Seleziona **Allegati** nell'angolo in alto a destra della pagina, scarica il file e utilizzalo per inviarlo all'autorità fiscale.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Eseguire una dichiarazione IVA per più persone giuridiche

Per utilizzare i formati per riportare la dichiarazione IVA per un gruppo di persone giuridiche, è necessario prima impostare i parametri specifici dell'applicazione dei formati della creazione di report elettronici per i codici IVA di tutte le persone giuridiche richieste.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Impostare i messaggi elettronici per raccogliere dati fiscali da diverse persone giuridiche

Segui questi passaggi per impostare i messaggi elettronici per raccogliere dati da più persone giuridiche.

1. Vai a **Aree di lavoro** > **Gestione funzionalità**.
2. Trova e seleziona la funzionalità **Query interaziendali per le azioni di popolamento dei record** nell'elenco, quindi seleziona **Abilita ora**.
3. Vai a **Imposta** > **Impostazione** > **Messaggi elettronici \> Azioni di popolamento record**.
4. Nella pagina **Azione di popolamento record**, seleziona la riga per **DE Compila i record di dichiarazione IVA**.

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
