---
title: Panoramica dell'IVA
description: Questo argomento fornisce una panoramica del sistema IVA. Descrive gli elementi di configurazione IVA e il modo in cui interagiscono.
author: ShylaThompson
manager: AnnBe
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority, TaxPeriod, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 13111
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08d128e3006d019fa19b52f320b262ae49105e5d
ms.sourcegitcommit: ddd66bd329e76d88178032566b0a57637159b537
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "2666832"
---
# <a name="sales-tax-overview"></a>Panoramica dell'IVA

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica del sistema IVA. Descrive gli elementi di configurazione IVA e il modo in cui interagiscono.

<a name="overview"></a>Panoramica
--------

Il framework dell'IVA supporta numerosi tipi di imposte indirette, ad esempio imposta sul valore aggiunto (IVA), Imposta sui Beni e Servizi (GST, Goods and Services Tax), commissioni in base a unità e ritenuta d'acconto. Queste imposte vengono calcolate e documentate nelle transazioni di acquisto e di vendita. Periodicamente, devono essere dichiarate e pagate agli uffici tributari. 

Nel seguente diagramma vengono mostrate le entità di impostazione imposte e viene indicato come sono correlate.

[![TaxOverview](./media/taxoverview1-300x209.jpg)](./media/taxoverview1.jpg) 

Per ogni importo IVA che una società deve contabilizzare, un codice IVA deve essere definito. In un codice VAT sono archiviate le aliquote di imposta e le regole di calcolo dell'IVA. 

Ogni codice VAT deve essere collegato a un periodo di liquidazione IVA. I periodi di liquidazione IVA definiscono gli intervalli con cui deve essere dichiarata e pagate l'IVA all'ufficio IVA. Ogni periodo di liquidazione IVA deve essere assegnato a un ufficio IVA. L'ufficio IVA rappresenta la persona giuridica a cui viene dichiarata e pagata l'IVA. Consente inoltre di definire il layout del report IVA. Gli uffici VAT possono essere correlati ai conti fornitore. Per ulteriori informazioni, vedere [Impostare i periodi di liquidazione IVA](tasks/set-up-sales-tax-settlement-periods.md).

Ogni codice VAT deve inoltre essere collegato a un gruppo di registrazione contabile. Un gruppo di registrazione contabile specifica i conti principali in cui verranno registrati gli importi per i codici IVA. 

Possono anche essere definiti codici reporting IVA facoltativi. Questi possono essere assegnati ai codici IVA per i diversi tipi di importo calcolati per il codice IVA. Il report **Pagamento IVA per codice** mostra i totali per codice reporting IVA per un determinato intervallo e periodo di liquidazione IVA. 

Ogni transazione per cui deve essere calcolata e registrata l'IVA deve essere associata a una fascia IVA e a una fascia IVA articoli. Le fasce VAT sono correlate alla parte (ad esempio, cliente o fornitore) della transazione, mentre le fasce IVA articoli sono correlate alla risorsa (ad esempio, articolo o categoria di approvvigionamento) della transazione. Le fasce VAT contengono un elenco di codici IVA. I codici IVA che sono presenti sia nella fascia IVA sia nella fascia IVA articoli di una transazione sono i codici IVA applicabili alla transazione. 

Nella seguente tabella sono descritte le entità e la sequenza dell'impostazione IVA.

| Attività di impostazione                                                  | Stato Obbligatorio/Facoltativo e descrizione                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Crea conti principali.                                           | Obbligatorio. Per poter impostare le funzionalità relative all'IVA, è necessario innanzitutto creare i conti principali che la società utilizza per pagare e registrare le imposte.                                                                                                                                                                             |
| Impostare gruppi di registrazione contabile per l'IVA.                     | Obbligatorio. I gruppi di registrazione contabile definiscono i conti principali per la registrazione e il pagamento IVA.   Per ulteriori informazioni, vedere [Impostare gruppi di registrazione contabile per l'IVA](tasks/set-up-ledger-posting-groups-sales-tax.md).                                                                                 |
| Impostare gli uffici IVA.                                   | Obbligatorio. Gli uffici IVA sono persone giuridiche a cui devono essere dichiarate e pagate le imposte.    Per ulteriori informazioni, vedere [Impostare gli uffici IVA](tasks/set-up-sales-tax-authorities.md).                                                                                                                                          |
| Impostare i periodi di liquidazione IVA.                            | Obbligatorio. I periodi di liquidazione IVA contengono informazioni su quando e come deve essere dichiarata e pagata l'IVA. Sono correlati a un ufficio IVA.                                                                                                                                                       |
| Impostare i codici reporting IVA.                               | Facoltativo. I codici reporting IVA possono essere assegnati ai codici IVA per il reporting degli importi per più codici IVA in un unico codice reporting IVA. Per ulteriori informazioni, vedere [Impostare i codici reporting IVA](tasks/set-up-sales-tax-reporting-codes.md).                                         |
| Impostare i codice IVA.                                         | Obbligatorio. I codici IVA contengono le aliquote di imposta e le regole di calcolo dell'IVA. I codici IVA sono correlati al periodo di liquidazione IVA e a un gruppo di registrazione contabile. Per ulteriori informazioni, vedere [Impostare i codici IVA](tasks/set-up-sales-tax-codes.md).                                |
| Impostare le fasce IVA.                                        | Obbligatorio. Le fasce IVA contengono un elenco di codici di vendita che si applicano alla parte (cliente o fornitore) di una transazione. Per una determinata transazione, l'intersezione dei codici IVA nelle fasce IVA e nelle fasce IVA articoli determina i codici IVA inclusi applicabili alla transazione.                  |
| Imposta le fasce IVA articoli.                                   | Obbligatorio. Le fasce IVA articoli contengono un elenco di codici di vendita che si applicano per la risorsa (prodotto, servizio, e così via) di una transazione. Per una determinata transazione, l'intersezione dei codici IVA nelle fasce IVA e nelle fasce IVA articoli determina i codici IVA inclusi applicabili alla transazione. Per ulteriori informazioni, vedere [Impostare le fasce IVA e le fasce IVA articoli](tasks/set-up-sales-tax-groups-item-sales-tax-groups.md). |
| Impostare i parametri IVA nelle pagine dei parametri applicazione. | Obbligatorio. In diverse aree, ad esempio contabilità generale, contabilità clienti e contabilità fornitori, è necessario impostare i parametri per il calcolo corretto delle imposte indirette. Sebbene la maggior parte di questi parametri abbia valori predefiniti, devono essere apportate modifiche in base ai requisiti di ogni società.                                          |

## <a name="sales-tax-on-transactions"></a>IVA su transazioni
In ogni transazione (righe documento di acquisto/vendita, giornali di registrazione e così via), è necessario immettere una fascia IVA e una fascia IVA articoli per calcolare l'IVA. Le fasce predefinite sono specificate nei dati master, ad esempio cliente, fornitore, articolo e categoria di approvvigionamento, ma è possibile modificare manualmente le fasce in una transazione se necessario. Entrambe le fasce contengono un elenco di codici IVA e l'intersezione di due elenchi di codici IVA determina l'elenco dei codici IVA applicabili per la transazione. 

In ciascuna transazione, è possibile individuare l'IVA calcolata aprendo la pagina **Transazione IVA**. È possibile individuare l'IVA per una riga di documento o per l'intero documento. Per alcuni documenti (ad esempio, fatture fornitore e giornali di registrazione generale), è possibile rettificare l'IVA calcolata se nel documento originale vengono mostrati gli importi devianti.

## <a name="sales-tax-settlement-and-reporting"></a>Liquidazione e reporting IVA
L'IVA deve essere dichiarata e pagata agli uffici tributari a intervalli regolari (mensile, trimestrale e così via). È possibile liquidare i conti IVA per l'intervallo e utilizzare in contropartita i saldi nel conto di liquidazione IVA, come specificato nei gruppi di registrazione contabile. È possibile accedere a questa funzionalità nella pagina **Liquida e registra IVA**. È necessario specificare il periodo di liquidazione IVA per cui l'IVA dovrà essere liquidata. 

Dopo aver pagato l'IVA, il saldo del conto di liquidazione IVA deve essere bilanciato a fronte del conto bancario. Se l'ufficio IVA specificato nel periodo di liquidazione IVA è correlato a un conto fornitore, il saldo IVA viene registrato come fattura fornitore aperta e può essere incluso nella proposta di pagamento normale.

## <a name="conditional-sales-tax"></a>IVA condizionata
L'IVA condizionata viene applicata proporzionalmente all'importo effettivo pagato da una fattura. Viceversa, l'IVA standard viene calcolata al momento della fatturazione. L'IVA condizionata deve essere pagata all'ufficio IVA quando viene registrato il pagamento, non quando viene registrata la fattura. Quando viene registrata la fattura, la transazione deve essere dichiarata nel report su libro IVA. La transazione, tuttavia, deve essere esclusa dal report relativo al pagamento IVA. 

Se si seleziona la casella di controllo IVA condizionata nel modulo Parametri di contabilità generale, l'IVA non può essere dedotta finché non verrà pagata la fattura. Questo è un requisito legale in molti paesi.

> [!NOTE]
> Quando si seleziona la casella di controllo IVA condizionata è necessario impostare i codici IVA e le fasce IVA e creare inoltre i gruppi di registrazione contabile per supportare questa funzionalità. |

###  <a name="example"></a>Esempio

Liquidare l'IVA ogni mese. Il 15 giugno creare una fattura cliente di 10.000 più IVA.
-   L'IVA equivale al 25%, ovvero a 25,00.
-   Il pagamento della fattura è dovuto il 30 luglio.

In genere è necessario liquidare e pagare 2.500 all'ufficio tributario quando viene registrata la fattura a giugno, anche se non è stato ricevuto il pagamento dal cliente. 

Tuttavia, se si utilizza un'IVA condizionata, è possibile liquidare quando si riceve il pagamento dal cliente il 30 luglio.

### <a name="postdated-check"></a>Assegno postdatato

Se si utilizza un assegno postdatato come metodo di pagamento, quando viene creato il pagamento, il conto bancario non viene cancellato. In alcuni paesi, l'IVA diventa responsabilità "realizzata" quando il pagamento cancella la banca, il che significa che l'assegno postdatato è stato liquidato. È possibile abilitarlo selezionando l'opzione per **realizzare l'imposta condizionale quando vengono generati assegni postdatati** in **Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche > Assegni postdatati**.

Per ulteriori informazioni, vedere [Impostare la ritenuta d'acconto](tasks/set-up-withholding-tax.md).
