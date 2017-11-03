---
title: Dettagli delle dichiarazioni IVA per l'Italia
description: In questo argomento viene illustrato come impostare la dichiarazione IVA per le persone giuridiche in Italia.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 269664
ms.assetid: af07d122-5694-4de6-96bf-7bf5478b0175
ms.search.region: Italy
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 941c21671945e6b62054ba7fd14a7a4ebff0b69f
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="vat-statements-details-for-italy"></a>Dettagli delle dichiarazioni IVA per l'Italia

[!include[banner](../includes/banner.md)]


In questo argomento viene illustrato come impostare la dichiarazione IVA per le persone giuridiche in Italia. 

<a name="set-up-customervendor-tax-information-for-tax-reports"></a>Impostare le informazioni fiscali di clienti/fornitori per report fiscali
------------------------------------------------------

Per generare il report IVA, il cliente e il fornitore devono essere configurati con le informazioni fiscali per l'Italia. Nella pagina **Clienti**, selezionare i campi nella seguente tabella.

#### <a name="invoice-and-delivery"></a>Fattura e consegna

| **Campo**             | **Descrizione**                                        |
|-----------------------|--------------------------------------------------------|
| **Partita IVA** | Immettere il numero di partita IVA per la dichiarazione IVA.       |
| **Codice fiscale**       | Immettere il codice fiscale per questo cliente.               |
| **Fascia IVA**   | Selezionare una fascia IVA da utilizzare per questo cliente. |

Nella pagina **Fornitori**, selezionare i campi nella seguente tabella.

#### <a name="invoice-and-delivery"></a>Fattura e consegna

| **Campo**             | **Descrizione**                                      |
|-----------------------|------------------------------------------------------|
| **Partita IVA** | Immettere il numero di partita IVA per la dichiarazione IVA.     |
| **Codice fiscale**       | Immettere il codice fiscale per questo fornitore.               |
| **Fascia IVA**   | Selezionare una fascia IVA da utilizzare per questo fornitore. |

## <a name="set-up-a-company-fiscal-code-and-tax-registration-number"></a>Impostare codice fiscale e partita IVA della società
Per generare report, il codice fiscale e la partita IVA della società devono essere impostati nella pagina **Persona giuridica**. Nella pagina **Persona giuridica**, selezionare i campi nella seguente tabella.

#### <a name="registration-numbers"></a>Numeri di registrazione

| **Campo**        | **Descrizione**                                                    |
|------------------|--------------------------------------------------------------------|
| **Codice fiscale**  | Immettere il codice fiscale della registrazione della persona giuridica in Italia. |
| **Natura giuridica** | Immettere la struttura legale della società.                          |
| **CUC**          | Immettere il codice CUC.                                                |

#### <a name="tax-registration"></a>Registrazione fiscale

| **Campo**               | **Descrizione**                                                 |
|-------------------------|-----------------------------------------------------------------|
| Partita IVA | Immettere la partita IVA per la persona giuridica in Italia |

#### <a name="set-up-parameters-for-italian-sales-tax-book"></a>Impostare i parametri per il libro IVA italiano

Nella pagina **IVA**, creare i libri IVA da dichiarare al governo italiano dopo il periodo di liquidazione.

| **Campo**                     | **Descrizione**                                 |
|-------------------------------|-------------------------------------------------|
| **Tipo di libro IVA**       | Immettere la direzione del movimento. (Vendite/acquisti)  |
| **Libro IVA**            | Immettere l'identificatore del libro IVA.     |
| **Nome**                      | Immettere il nome del libro IVA.           |
| **Tipo di libro IVA**       | Immettere la direzione del movimento. (Vendite/acquisti)  |
| **Periodo di liquidazione**         | Il periodo per questo libro fiscale.                   |
| **Chiuso al**                 | Selezionare la data della transazione.                    |
| **Vendite UE**                  | L'importo di vendita per l'Unione Europea.          |
| **ATECOFIN**                  | Il codice fiscale per il reporting IVA.           |
| **Stampa riepilogo e pagamenti** | Selezionare questa opzione per stampare il riepilogo e il report di pagamento. |

## <a name="yearly-tax-communication-report"></a>Report di comunicazione annuale delle imposte
Dopo la fine dell'anno, generare il report per ogni periodo di liquidazione. La trasmissione è obbligatoria in base a quanto richiesto dall'autorità fiscale italiana tramite un sito Web. Nella pagina **Comunicazione annuale imposte**, è possibile creare o visualizzare un report.

#### <a name="overview"></a>Panoramica

| **Campo**                | **Descrizione**                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------|
| **ID comunicazione imposte** | Immettere il numero di identificazione del report Comunicazione annuale imposte.                       |
| **Anni**                | Immettere l'anno della comunicazione imposte.                                                      |
| **Codice ATECOFIN**        | Immettere il codice imposta associato alla classificazione di possibili attività della società. |
| **Esportato**             | Indica che il file con estensione .ivc è esportato.                                                     |

#### <a name="general"></a>Generale

| **Campo**                | **Descrizione**                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------|
| **ID comunicazione imposte** | Immettere il numero di identificazione del report Comunicazione annuale imposte.                       |
| **Anni**                | Immettere l'anno della comunicazione imposte.                                                      |
| **Codice ATECOFIN**        | Immettere il codice imposta associato alla classificazione di possibili attività della società. |
| **Esportato**             | Indica che il file è stato esportato.                                                         |
| **Data di esportazione**       | Data in cui è stato esportato il file con estensione .ivc.                                                     |
| **Nome file di esportazione**     | Nome del file con estensione ivc.                                                                    |

## <a name="vat-summary-report"></a>Report di riepilogo IVA
Per il reporting IVA, l'Italia richiede la dichiarazione e la formattazione di informazioni specifiche. Nella pagina **Uffici IVA**, in **Impostazione fiscale**, configurare l'autorità italiana.

| **Campo**                                 | **Descrizione**                                                                                |
|-------------------------------------------|------------------------------------------------------------------------------------------------|
| **Layout del report**                         | Selezionare il report italiano per attivare i campi italiani.                                            |
| **Stampa pagina vuota senza transazioni** | Selezionare per stampare le pagine vuote quando non sono presenti transazioni.                                  |
| **Registro riepilogo separato**             | Selezionare questa casella di controllo per utilizzare un libro IVA separato per numerare le sezioni riepilogative. |
| **Conto Guadagni**                          | Guadagno dovuto all'arrotondamento.                                                                          |
| **Conto Perdite**                          | Perdita dovuta all'arrotondamento.                                                                          |

## <a name="sales-tax-settlement-periods"></a>Periodi liquidazione IVA
Per la legislazione italiana, le regole si applicano ai periodi di liquidazione. Ad esempio, una volta chiuso il periodo di liquidazione, non sono consentite modifiche. È necessario dichiarare se la liquidazione si riferisce all'ultimo periodo dell'anno fiscale. Visualizzare lo stato del periodo di liquidazione e dichiarare se si riferisce a una chiusura annuale. Nela pagina **Periodo liquidazione IVA** &gt; scheda **Intervalli periodici**, selezionare i seguenti campi.

| **Campo**       | **Descrizione**                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
| **Chiuso**      | Indica se il libro IVA italiano relativo al periodo è stato aggiornato e chiuso automaticamente. |
| **Ultimo periodo** | Selezionare questa opzione se si tratta dell'ultimo periodo di un anno IVA.                          |






