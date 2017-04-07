---
title: Dettagli delle dichiarazioni VAT per l&quot;Italia
description: In questo argomento viene descritto come installare una dichiarazione VAT per le persone giuridiche italiane.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269664
ms.assetid: af07d122-5694-4de6-96bf-7bf5478b0175
ms.search.region: Italy
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 7804441cac6bdcbdaec693f676a89fac43ce9829
ms.lasthandoff: 03/31/2017


---

# <a name="vat-statements-details-for-italy"></a>Dettagli delle dichiarazioni VAT per l'Italia

In questo argomento viene descritto come installare una dichiarazione VAT per le persone giuridiche italiane. 

<a name="set-up-customervendor-tax-information-for-tax-reports"></a>Impostare le informazioni fiscali di clienti e fornitori per i report VAT
------------------------------------------------------

Per generare il report VAT, cliente e il fornitore devono essere configurati con le informazioni fiscali per l'Italia. ** Clienti ** nella pagina, selezionare i campi nella seguente tabella.

#### <a name="invoice-and-delivery"></a>Fattura e consegna

| **Field**             | **Description**                                        |
|-----------------------|--------------------------------------------------------|
| **Tax exempt number** | Immettere la partita VAT per la dichiarazione VAT.       |
| **Fiscal code**       | Immettere il codice fiscale del cliente.               |
| ** Fascia VAT **   | Selezionare una fascia VAT da utilizzare per il cliente. |

** Fornitori ** nella pagina, selezionare i campi nella seguente tabella.

#### <a name="invoice-and-delivery"></a>Fattura e consegna

| **Field**             | **Description**                                      |
|-----------------------|------------------------------------------------------|
| **Tax exempt number** | Immettere la partita VAT per la dichiarazione VAT.     |
| **Fiscal code**       | Immettere il codice fiscale del fornitore.               |
| ** Fascia VAT **   | Selezionare una fascia VAT da utilizzare per il fornitore. |

## <a name="set-up-a-company-fiscal-code-and-tax-registration-number"></a>Impostare un numero di conto della società e tassi il numero di registrazione
Per generare report, il codice della società e il numero di registrazione fiscale devono essere installati ** persona giuridica ** nella pagina. ** Persona giuridica ** nella pagina, selezionare i campi nella seguente tabella.

#### <a name="registration-numbers"></a>Numeri di registrazione

| **Field**        | **Description**                                                    |
|------------------|--------------------------------------------------------------------|
| ** Numero di conto **  | Immettere il codice fiscale della registrazione della persona giuridica è in Italia. |
| ** Natura giuridica ** | Immettere la struttura legale della società.                          |
| **CUC**          | Immettere il codice di CUC.                                                |

#### <a name="tax-registration"></a>Registrazione fiscale

| **Field**               | **Description**                                                 |
|-------------------------|-----------------------------------------------------------------|
| Partita IVA | Immettere il numero di registrazione fiscale per la persona giuridica è in Italia |

#### <a name="set-up-parameters-for-italian-sales-tax-book"></a>Consente di impostare i parametri per il libro VAT italiano

** VAT ** nella pagina, creare libri VAT da dichiarare al governo italiano dopo il periodo di liquidazione è oltre.

| **Field**                     | **Description**                                 |
|-------------------------------|-------------------------------------------------|
| **Sales tax book type**       | Immettere la direzione di movimento. (Unità di vendita/acquisto)  |
| **Sales tax book**            | Consente di immettere l'identificatore del libro VAT.     |
| **Name**                      | Immettere il nome del libro VAT.           |
| **Sales tax book type**       | Immettere la direzione di movimento. (Unità di vendita/acquisto)  |
| **Settlement period**         | Il periodo per il libro VAT.                   |
| **Closed to**                 | Selezionare la data della transazione.                    |
| **EU sales**                  | Importo venduto all'Unione Europea.          |
| ** ATECOFIN **                  | Numero di conto per il reporting VAT.           |
| **Print summary and payment** | Selezionare questa opzione per stampare il riepilogo e il report di pagamento. |

## <a name="yearly-tax-communication-report"></a>Report di comunicazione annuale delle imposte
Alla fine anno, generare il report per ogni periodo di liquidazione. La trasmissione è obbligatoria in base alle esigenze dell'autorità fiscale italiano tramite un sito Web. ** Impostazioni comunicazione annuale imposte ** nella pagina, è possibile creare o visualizzare un report.

#### <a name="overview"></a>Panoramica

| **Field**                | **Description**                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------|
| **Tax communication ID** | Immettere il numero di identificazione del report comunicazione annuale imposte.                       |
| **Years**                | Immettere l'anno della comunicazione VAT.                                                      |
| **ATECOFIN Code**        | Immettere il codice fiscale associato alla classificazione delle possibili attività della società. |
| **Exported**             | Indica che il file con estensione ivc esportato.                                                     |

#### <a name="general"></a>Generale

| **Field**                | **Description**                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------|
| **Tax communication ID** | Immettere il numero di identificazione del report comunicazione annuale imposte.                       |
| **Years**                | Immettere l'anno della comunicazione VAT.                                                      |
| **ATECOFIN Code**        | Immettere il codice fiscale associato alla classificazione delle possibili attività della società. |
| **Exported**             | Indica che il file è stato esportato.                                                         |
| **Date of export**       | Data in cui il file con estensione ivc è stato esportato.                                                     |
| **Export file name**     | Nome del file con estensione ivc.                                                                    |

## <a name="vat-summary-report"></a>Minuti riepilogativo VAT
Per il reporting VAT, l'Italia in informazioni specifiche da dichiarare e formattare. In ** gli uffici VAT ** pagine, da ** imposta impostata **, configurare l'autorità italiano.

| **Field**                                 | **Description**                                                                                |
|-------------------------------------------|------------------------------------------------------------------------------------------------|
| **Report layout**                         | Selezionare il report italiano per attivare i campi italiani.                                            |
| **Print blank page with no transactions** | Selezionare per stampare le pagine vuote quando non sono presenti transazioni.                                  |
| **Separate summary register**             | Selezionare questa casella di controllo per utilizzare un libro IVA separato per numerare le sezioni riepilogative. |
| **Account gain**                          | Guadagno dovuto l'arrotondamento.                                                                          |
| **Account loss**                          | Perdita dovuta l'arrotondamento.                                                                          |

## <a name="sales-tax-settlement-periods"></a>Periodi liquidazione IVA
Per normativa italiana, le regole si applicano ai periodi di liquidazione. Ad esempio, dopo il periodo di liquidazione è chiuso, non sono consentite modifiche è consentita. È necessario indicare se la liquidazione si riferisce all'ultimo periodo dell'anno fiscale. Visualizzare lo stato del periodo di liquidazione e report se si riferisce a una chiusura annuale. ** Periodo di liquidazione VAT ** nella &gt; pagina ** intervalli periodici ** la scheda, selezionare i seguenti campi.

| **Field**       | **Description**                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
| **Closed**      | Indica se il libro VAT italiano relativo al periodo è stato aggiornato e chiuso automaticamente. |
| **Last period** | Selezionare questa opzione se si tratta dell'ultimo periodo di un anno IVA.                          |




