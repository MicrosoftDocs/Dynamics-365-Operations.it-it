---
title: Membri di dimensione statistica e modelli provider misure statistiche
description: Questo argomento fornisce informazioni sui membri di dimensione statistica e i modelli provider misure statistiche. I membri di dimensione statistica possono essere utilizzati come base di allocazione nei criteri quali la distribuzione dei costi e l'allocazione dei costi. Possono essere utilizzati anche per dichiarare il consumo dei costi non monetari.
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerSourceEntryProvider, CAMStatisticalDimension, CAMAXStatisticalMeasureProviderTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c46a9e042482ad66e769383b4e81e2df85a5e97b
ms.sourcegitcommit: fa5c45f7842c4d20c994ac1655e2fbf2a1cf14a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2020
ms.locfileid: "3734912"
---
# <a name="statistical-dimension-members-and-statistical-measure-provider-templates"></a>Membri di dimensione statistica e modelli provider misure statistiche

[!include [banner](../includes/banner.md)]

Una dimensione statistica e i relativi membri vengono utilizzati per registrare e monitorare le voci non monetarie nella contabilità industriale. I membri di dimensione statistica possono essere utilizzati per due scopi:

- Come base di allocazione nei criteri quali la distribuzione dei costi o l'allocazione dei costi
- Per la dichiarazione del consumo non monetario

## <a name="statistical-dimension"></a>Dimensione statistica

Una dimensione statistica ha un nome univoco e un insieme ai membri di dimensione univoci. La dimensione statistica viene assegnata a un ID di contabilità generale della contabilità industriale. Questa relazione associa tutti i membri di dimensione statistica corrispondenti alla contabilità generale della contabilità industriale. Di conseguenza, tutte le voci statistiche verranno create nel contesto di contabilità generale della contabilità industriale.

> [!NOTE]
> Una dimensione statistica può essere assegnata a più di una contabilità generale della contabilità industriale.

Di seguito è riportato un esempio di dimensione statistica.

| Nome                        | Connettore dati per membri di dimensione |
|-----------------------------|--------------------------------------|
| Elementi statistici condivisi | Membri di dimensione importati           |

Di seguito è riportato un esempio di una dimensione statistica assegnata a una contabilità generale di contabilità industriale.

| Nome                  | Valuta di contabilizzazione | Tipo di tasso di cambio | Calendario fiscale | Dimensione elemento di costo | Dimensione statistica       |
|-----------------------|---------------------|--------------------|-----------------|------------------------|-----------------------------|
| Contabilità manageriale | GBP                 | Valuta costante  | Periodo fiscale   | Elementi di costo condivisi   | Elementi statistici condivisi |

## <a name="statistical-dimension-members"></a>Membri di dimensione statistica

Un membro di dimensione statistica rappresenta un'entità per cui si desidera registrare delle misure non monetarie. Queste misure possono essere utilizzate come base di allocazione oppure semplicemente per dichiarare valori non monetari.

I membri di dimensione statistica possono essere creati manualmente. In alternativa, possono essere importati da un file utilizzando lo Strumento di esportazione/importazione della gestione dati.

Un membro di dimensione statistica diventa automaticamente una base di allocazione predefinita. Può essere utilizzata come base di allocazione nei criteri o come input in altri tipi di base di allocazione.

Di seguito sono riportati alcuni esempi di membri di dimensione statistica tipici.

| Nome dimensione statistica  | Elementi statistici | descrizione             | Unità |
|-----------------------------|----------------------|-------------------------|------|
| Elementi statistici condivisi | FTE                  | Dipendenti a tempo pieno     | Cadauno  |
| Elementi statistici condivisi | Elettricità          | Consumo di elettricità | kWh  |
| Elementi statistici condivisi | CC di imballaggio              | Centro di costo per l'imballaggio   | Ore |

## <a name="statistical-measure-provider-template"></a>Modello provider misure statistiche

Le misure statistiche possono derivare da numerosi tipi di origini. Dynamics 365 Finance è un'ottima origine da cui estrarre le misure statistiche. È possibile utilizzare un modello provider misure statistiche per configurare facilmente le misure statistiche che si desidera estrarre.

La definizione di un modello provider misure statistiche è generica e può essere riutilizzata in più di dimensione statistica.

> [!NOTE]
> Tutte le tabelle che contengono dimensioni finanziarie possono essere utilizzate come origini delle misure statistiche.

**Esempio: conteggio dei dipendenti per centro di costo**

Il numero dei dipendenti per centro di costo è una misura statistica che può essere utilizzata per diversi scopi che forniscono informazioni approfondite manageriali:

- Misura di report statistica in base al centro di costo
- Base di allocazione per vari tipi di spese
- Tassi di costo interno per centro di costo:

    - Costo in base al dipendente
    - Ricavi in base al dipendente

La tabella HcmEmployment contiene un elenco di tutti i dipendenti nell'istanza. Questa tabella è una tabella globale. Di conseguenza, i record non sono correlati a un ID area dati specifica.

Di seguito è riportato un esempio di dipendenti inclusi nella tabella HcmEmployment.

| Nome       | Centro di costo | descrizione   | Tipo di lavoratore |
|------------|-------------|----|-------------|
| Dipendente 1 | CC001       | Risorse umane | Dipendente    |
| Dipendente 2 | CC002       | FI | Dipendente    |
| Dipendente 3 | CC002       | FI | Dipendente    |
| Dipendente 4 | CC003       | TS | Dipendente    |
| Dipendente 5 | CC003       | TS | Dipendente    |
| Dipendente 6 | CC002       | FI | Terzista  |

Quando si crea un record **Modello provider misure statistiche**, è necessario decidere quali funzione utilizzare:

- **Conteggio** - Viene trasferito un conteggio di record per oggetto di costo.
- **Somma** - Viene trasferita una somma per i records per oggetto di costo. I campi **Somma** e **Data** sono obbligatori.

## <a name="using-the-count-function"></a>Utilizzo della funzione di conteggio

Ad esempio, un modello provider misure statistiche può essere impostato come indicato di seguito.

| Nome  | Funzione | Tabella di origine  | Campo somma      | Campo data     |
|-------|----------|---------------|----------------|----------------|
| FTE  | Conteggio    | HcmEmployment | Non applicabile | Non applicabile |

È inoltre possibile aggiungere uno o più intervalli per limitare le misure dalla tabella di origine.

In questo esempio, se si desidera semplicemente un conteggio di tutti i dipendenti a tempo pieno (FTE), è possibile aggiungere un intervallo nel campo **Tipo di lavoratore**. Nel campo **Criteri** selezionare **Dipendente** per limitare l'intervallo di output come indicato di seguito.

**Intervalli**

| Tabella di origine  | Campo       | Criteri |
|---------------|-------------|----------|
| HcmEmployment | Tipo di lavoratore | Dipendente |

Prima di immettere le misure statistiche nella contabilità industriale, è necessario impostare la relazione tra il modello provider misure statistiche e il membro di dimensione statistica. Questa relazione viene creata per la contabilità generale e la versione della contabilità industriale. La relazione è costituita da un connettore di dati e da un provider di dati. È possibile avere diversi connettori di dati e provider di dati per membro di dimensione statistica.

> [!NOTE]
> In questo esempio verrà creata una relazione solo per **Versione effettiva**.

Passare a **Movimento CoGe di contabilità industriale** \> **Versione effettiva** \> **Gestione** \> **Misure statistiche** per stabilire la relazione. Per questo scenario, selezionare il connettore di dati **Dynamics 365 Finance - Misure statistiche** per estrarre i dati da Finance.

**Origine dati**

| Nome        | Connettore dati                                                                     | Membro di dimensione statistica |
|-------------|------------------------------------------------------------------------------------|------------------------------|
| FTEs D365FO | Dynamics 365 Finance – Misure statistiche | FTE                         |

**Configurazione del provider di dati**

| Nome del modello statistico |
|---------------------------|
| FTE                      |

Dopo l'elaborazione dei dati di origine della misura statistica, le seguenti voci statistiche vengono create nella contabilità industriale.

**Giornale di registrazione**

| Giornale di registrazione | Tipo giornale di registrazione                       | Periodo di calendario fiscale | Anno   |  Periodo  |  Versione | Voci di origine del connettore di dati|
|---------|------------------------------------|------------------------|--------|----------|----------|------------------------------|
| 00001   | Giornale di registrazione trasferimenti voci statistiche | Fiscale                 | 2017   | Periodo 1 | USMF contabilità generale SA | FTE                   |

**Scritture contabili trasferimenti voci statistiche**

| Data di registrazione | Grandezza | Elemento statistico |   descrizione       | Centro di costo |
|-----------------|-----------|---------------------|---------------------|-------------|
| 31-01-2017      | 1,00      | FTE                | Dipendenti a tempo pieno | CC001       |
| 31-01-2017      | 2.00      | FTE                | Dipendenti a tempo pieno | CC002       |
| 31-01-2017      | 2.00      | FTE                | Dipendenti a tempo pieno | CC003       |

**Voci statistiche**

| Oggetto di costo |    | Data di registrazione | Membro di dimensione statistica |  descrizione        | Grandezza |
|-------------|----|-----------------|------------------------------|---------------------|-----------|
| CC001       | Risorse umane | 31-01-2017      | FTE                         | Dipendenti a tempo pieno | 1,00      |
| CC002       | FI | 31-01-2017      | FTE                         | Dipendenti a tempo pieno | 2.00      |
| CC003       | TS | 31-01-2017      | FTE                         | Dipendenti a tempo pieno | 2.00      |

Se la base di allocazione del membro di dimensione predefinito dei dipendenti a tempo pieno è assegnata come base di allocazione in una regola di distribuzione costi, il costo verrà distribuito utilizzando il seguente fattore di allocazione.

| Oggetto di costo | descrizione    | Grandezza | Fattore di allocazione |
|-------------|----|-----------|-------------------|
| CC001       | Risorse umane | 1,00      | (1/5) × Importo    |
| CC002       | FI | 2.00      | (2/5) × Importo    |
| CC003       | TS | 2.00      | (2/5) × Importo    |

## <a name="using-the-sum-function"></a>Utilizzo della funzione di somma

Un centro di costo di produzione, CC010 (imballaggio) è responsabile per l'imballaggio dei prodotti prima che siano inviati ai clienti. Il costo diretto della manodopera vien aggiunto ai prodotti tramite la distinta base e il ciclo di lavorazione. Anche il costo indiretto di gestione del centro di costo deve essere allocato ai prodotti realizzati. Spesso, la migliore misura statistica per tale allocazione è il numero di ore di produzione registrate per prodotto durante un determinato periodo.

La tabella ProdRouteTrans contiene tutte le transazioni di manodopera di produzione per DataAreadID dell'entità giuridica.

Di seguito è riportato un esempio della tabella ProdRouteTrans.

| Riferimento        | Numero | Operazione | Tipo | Ora  | Data effettiva | Gruppo di prodotti (Dimensione finanziaria) | Persona giuridica |
|------------------|--------|-----------|------|-------|---------------|-------------------------------------|--------------|
| Ordine di produzione | P0001  | Imballaggio | Ora | 8,00  | 01-01-2017    | Orange juice B2B                    | USMF         |
| Ordine di produzione | P0001  | Imballaggio | Ora | 8,00  | 02-01-2017    | Orange juice B2B                    | USMF         |
| Ordine di produzione | P0002  | Imballaggio | Ora | 4,00  | 03-01-2017    | Orange juice Consumer               | USMF         |
| Ordine di produzione | P0003  | Imballaggio | Ora | 4,00  | 03-01-2017    | Orange juice Consumer               | USMF         |
| Ordine di produzione | P0004  | Riconst.  | Ora | 10,00 | 03-01-2017    | Orange juice Consumer               | USMF         |

Quando si crea un record **Modello provider misure statistiche**, è necessario decidere quali funzione utilizzare:

- **Conteggio** - Viene trasferito un conteggio di record per oggetto di costo.
- **Somma** - Viene trasferita una somma per i records per oggetto di costo. I campi **Somma** e **Data** sono obbligatori.

Il modello provider misure statistiche può essere impostato come indicato di seguito.

| Nome    | Funzione | Tabella di origine   | Campo somma | Campo data    |
|---------|----------|----------------|-----------|---------------|
| CC di imballaggio | Totale      | ProdRouteTrans | Ore     | Data effettiva |

È inoltre possibile aggiungere degli intervalli per limitare le misure dalla tabella di origine.

In questo esempio se si desidera semplicemente la somma di ore che sono correlate al centro di costo CC010 Imballaggio, è possibile aggiungere un intervallo nel campo **Operazione**. Nel campo **Criteri** selezionare **Imballaggio** per limitare l'intervallo di output.

**Intervalli**

| Tabella di origine   | Campo     | Criteri  |
|----------------|-----------|-----------|
| ProdRouteTrans | Operazione | Imballaggio |

Prima di immettere le misure statistiche nella contabilità industriale, è necessario impostare la relazione tra il modello provider misure statistiche e il membro di dimensione statistica. Questa relazione viene creata per la contabilità generale e la versione della contabilità industriale. La relazione è costituita da un connettore di dati e da un provider di dati. È possibile avere diversi connettori di dati e provider di dati per membro di dimensione statistica.

> [!NOTE]
> In questo esempio verrà creata una relazione solo per **Versione effettiva**.

Passare a **Movimento CoGe di contabilità industriale** \> **Versione effettiva** \> **Gestione** \> **Misure statistiche** per stabilire la relazione. Per questo scenario, selezionare il connettore di dati **Dynamics 365 Finance - Misure statistiche** per estrarre i dati da Finance.

**Origine dati**

| Nome           | Connettore dati                                                                     | Membro di dimensione statistica |
|----------------|------------------------------------------------------------------------------------|------------------------------|
| CC di imballaggio D365FO | Dynamics 365 Finance – Misure statistiche | CC di imballaggio                      |

Il sistema rileva che ProdRouteTrans è una tabella in cui ogni record appartiene a una persona giuridica distinta. Di conseguenza, verrà chiesto di selezionare la persona giuridica da cui devono essere importate le transazioni.

**Configurazione del provider di dati**

| Nome del modello statistico | Persona giuridica |
|---------------------------|--------------|
| CC di imballaggio                   | USMF         |

Dopo l'elaborazione dei dati di origine della misura statistica, le seguenti voci statistiche vengono create nella contabilità industriale.

**Giornale di registrazione**

| Giornale di registrazione | Tipo giornale di registrazione                     | Periodo di calendario fiscale | Anno   | Periodo | Versione   |   Voci di origine del connettore di dati  |
|---------|----------------------------------|------------------------|--------|---------|----------------|---------|
| 00002   | Giornale di registrazione trasferimenti voci statistiche | Fiscale               | 2017    | Periodo 1  | USMF contabilità generale SA | CC di imballaggio |

**Scritture contabili trasferimenti voci statistiche**

| Data di registrazione | Grandezza | Elemento statistico |  descrizione          | Gruppo di prodotti         |
|-----------------|-----------|---------------------|-----------------------|-----------------------|
| 31-01-2017      | 16,00     | CC di imballaggio             | Centro di costo per l'imballaggio | Orange juice B2B      |
| 31-01-2017      | 8,00      | CC di imballaggio             | Centro di costo per l'imballaggio | Orange juice Consumer |

**Voci statistiche**

| Oggetto di costo           | Data di registrazione | Membro di dimensione statistica |    descrizione        | Grandezza |
|-----------------------|-----------------|------------------------------|-----------------------|-----------|
| Orange juice B2B      | 31-01-2017      | CC di imballaggio                      | Centro di costo per l'imballaggio | 16,00     |
| Orange juice Consumer | 31-01-2017      | CC di imballaggio                      | Centro di costo per l'imballaggio | 8,00      |

Se la base di allocazione del membro di dimensione predefinito del CC d imballaggio è assegnata come base di allocazione in una regola di distribuzione costi, il costo verrà distribuito utilizzando il seguente fattore di allocazione.

| Oggetto di costo           | Grandezza | Fattore di allocazione  |
|-----------------------|-----------|--------------------|
| Orange juice B2B      | 16,00     | (16 ÷ 24) × Importo |
| Orange juice Consumer | 8,00      | (8 ÷ 24) × Importo  |

## <a name="imported-statistical-measures"></a>Misure statistiche importate

È possibile importare le misure statistiche nella contabilità industriale utilizzando lo Strumento di esportazione/importazione della gestione dati.

L'entità di dati che viene utilizzata per l'importazione è denominata Misure statistiche importate.

> [!NOTE]
> Questa entità di dati è progettata per consentire un massimo di cinque valori di dimensione univoci per voce.

Il consumo di elettricità viene registrato in Microsoft Excel utilizzando il formato predefinito dell'entità di dati. Ecco un esempio.

| Data di registrazione | Nome membro di dimensione 1 | Nome membro di dimensione 2 | Nome membro di dimensione 5 | Grandezza  | Identificatore di origine |
|-----------------|------------------------|------------------------|------------------------|------------|-------------------|
| 31-01-2017      | CC001                  |                        |                        | 2,450.00   | Elettricità       |
| 31-01-2017      | CC002                  |                        |                        | 4,100.00   | Elettricità       |
| 31-01-2017      | CC003                  |                        |                        | 15.000,00  | Elettricità       |

Dopo aver importato i dati tramite Gestione dati, i dati verranno archiviati in una tabella di gestione temporanea di contabilità industriale. Di conseguenza, i dati importati possono essere utilizzati in più contabilità generali della contabilità industriale. Non è necessario ricaricare i dati.

Per importare i dati, andare a **Dati importati** \> **Entità di dati** \> **Misure statistiche importate**.

| Identificatore di origine | Data di registrazione | Grandezza  | Nome membro di dimensione 1 | Nome membro di dimensione 2 | Nome membro di dimensione 5 |
|-------------------|-----------------|------------|------------------------|------------------------|------------------------|
| Elettricità       | 31-01-2017      | 2,450.00   | CC001                  |                        |                        |
| Elettricità       | 31-01-2017      | 4,100.00   | CC002                  |                        |                        |
| Elettricità       | 31-01-2017      | 15.000,00  | CC003                  |                        |                        |

Prima di immettere le misure statistiche nella contabilità industriale, è necessario impostare la relazione tra l'identificatore di origine e il membro di dimensione statistica. Questa relazione viene creata per la contabilità generale e la versione della contabilità industriale. La relazione è costituita da un connettore di dati e da un provider di dati. È possibile avere diversi connettori di dati e provider di dati per membro di dimensione statistica.

> [!NOTE]
> In questo esempio verrà creata una relazione solo per **Versione effettiva**.

Passare a **Movimento CoGe di contabilità industriale** \> **Versione effettiva** \> **Gestione** \> **Misure statistiche** per stabilire la relazione. Per questo scenario selezionare il connettore di dati **Misure statistiche importate** poiché i dati sono stati importati da un sistema di terze parti nella contabilità industriale tramite Excel.

**Origine dati**

| Nome        | Connettore dati                | Membro di dimensione statistica |
|-------------|-------------------------------|------------------------------|
| Elettricità | Misure statistiche importate | Elettricità                  |

**Configurazione del provider di dati**

| Importa identificatore di origine | Funzione | Dimensione1   | Dimensione2 | Dimensione5 |
|--------------------------|----------|--------------|------------|------------|
| Elettricità              | Totale      | Centri di costo |            |            |

> [!NOTE]
> Quando si definisce la configurazione del provider di dati, è necessario specificare le dimensioni degli oggetti di costo da associare alle transazioni importate. Dopo l'elaborazione dei dati di origine della misura statistica, le seguenti voci statistiche vengono create nella contabilità industriale.

**Giornale di registrazione**

| Giornale di registrazione | Tipo giornale di registrazione                       | Periodo di calendario fiscale | Anno  | Periodo  |Versione      |Voci di origine del connettore di dati |
|---------|------------------------------------|------------------------|-------|--------|---------------|-------------|
| 00002   | Giornale di registrazione trasferimenti voci statistiche | Fiscale                 | 2017  | Periodo 1 | USMF contabilità generale SA | Elettricità |

**Scritture contabili trasferimenti voci statistiche**

| Data di registrazione | Grandezza  | Elemento di costo |   descrizione           | Centro di costo |
|-----------------|------------|--------------|-------------------------|-------------|
| 31-01-2017      | 2,450.00   | Elettricità  | Consumo di elettricità | CC001       |
| 31-01-2017      | 4,100.00   | Elettricità  | Consumo di elettricità | CC002       |
| 31-01-2017      | 15.000,00  | Elettricità  | Consumo di elettricità | CC003       |

**Voci statistiche**

| Oggetto di costo |    | Data di registrazione | Membro di dimensione statistica |      descrizione                   | Grandezza  |
|-------------|----|-----------------|------------------------------|-------------------------|------------|
| CC001       | Risorse umane | 31-01-2017      | Elettricità                  | Consumo di elettricità | 2,450.00   |
| CC002       | FI | 31-01-2017      | Elettricità                  | Consumo di elettricità | 4,100.00   |
| CC003       | TS | 31-01-2017      | Elettricità                  | Consumo di elettricità | 15.000,00  |

Se la base di allocazione del membro di dimensione predefinito di Elettricità è assegnata come base di allocazione in una regola di distribuzione costi, il costo verrà distribuito utilizzando il seguente fattore di allocazione.

| Oggetto di costo |    | Grandezza | Fattore di allocazione          |
|-------------|----|-----------|----------------------------|
| CC001       | Risorse umane | 2,450.00  | (2,450 ÷ 21,550) × Importo  |
| CC002       | FI | 4,100.00  | (4,100 ÷ 21,550) × Importo  |
| CC003       | TS | 15.000,00 | (15,000 ÷ 21,550) × Importo |

## <a name="additional-resources"></a>Risorse aggiuntive

[Basi di allocazione](allocation-bases.md)
