---
title: Visualizzare inserimenti nel giornale di registrazione e transazioni
description: "Questo articolo illustrate le varie modalità in cui è possibile visualizzare gli inserimenti nel giornale di registrazione e le transazioni."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8607f27bc36d62865b03f433c24c90763e8e0bec
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="view-journal-entries-and-transactions"></a>Visualizzare inserimenti nel giornale di registrazione e transazioni

[!include[banner](../includes/banner.md)]


Questo articolo illustrate le varie modalità in cui è possibile visualizzare gli inserimenti nel giornale di registrazione e le transazioni. 

Gli utenti che desiderano visualizzare giornali di registrazione e transazioni possono utilizzare diversi modi per accedere ai dati. È possibile sfruttare le pagine di richiesta di informazioni che consentono di eseguire il drill-down o utilizzare le varie opzioni di report nella contabilità generale.

## <a name="voucher-transactions"></a>Transazioni giustificativo
**Transazioni giustificativo** è una pagina di richiesta di informazioni in cui è possibile selezionare diversi campi e tabelle per specificare i criteri per il saldo o la transazione da cercare. Ad esempio, è possibile visualizzare tutte le transazioni per una data o un conto specifico oppure tutte le transazioni di tipo **In funzione** in un livello di registrazione specifico. Per impostazione predefinita, la pagina mostra il numero del giornale di registrazione, il giustificativo, la data e il conto principale, ma è possibile aggiungere tabelle, campi e criteri ulteriori per limitare la ricerca.

## <a name="audit-trail"></a>Audit trail
**Audit trail** è una pagina di richiesta di informazioni che mostra i tipi di transazioni, le descrizioni, gli utenti che hanno creato le transazioni e le date in cui le transazioni sono state create. Nella pagina di richiesta di informazioni **Audit trail** è possibile visualizzare le transazioni giustificativo.

## <a name="financial-reports"></a>Report finanziari
È inoltre possibile esplorare e analizzare le transazioni di contabilità generale eseguendo i report finanziari. Poiché la progettazione dei report finanziari può essere basata su conti, dimensioni, categorie di conto o su una combinazione di questi tre elementi, è possibile visualizzare le transazioni eseguendo il drill-down in diversi modi. Se è necessario visualizzare ulteriori informazioni sulle transazioni di contabilità generale, è inoltre possibile includere più proprietà di transazione come parte della progettazione del report. Inoltre, se si desidera visualizzare le transazioni che costituiscono un saldo di contabilità generale, è possibile eseguire il drill-down delle transazioni di conto, così come è possibile effettuare tale operazione dalla pagina elenco **Bilancio di verifica**.

## <a name="ledger-reports"></a>Report di contabilità generale
Oltre ai report finanziari, è possibile utilizzare i seguenti report di contabilità generale per visualizzare le transazioni di contabilità generale:

-   **Rendiconto dimensioni**: questo report mostra le transazioni per giorno e conto e sono inoltre disponibili opzioni per visualizzare le transazioni per dimensione e periodo.
-   **Elenco transazioni contabili**: questo report mostra le transazioni nelle valute di transazione, contabilizzazione e dichiarazione per un conto.
-   **Stampa giornale di registrazione** - Il report mostra i risultati di un giornale registrato. È possibile eseguire il report per numero batch di giornale di registrazione o tipo di giornale di registrazione o aggiungere ulteriori campi.
-   **Transazioni registrate per giornale**: questo report mostra le transazioni registrate in un giornale di registrazione, raggruppate per giustificativo.
-   **Elenco transazioni per data**: questo report mostra tutte le transazioni per data, insieme al numero del giornale di registrazione, giustificativo e conto CoGe. In questo report vengono inoltre visualizzate le transazioni nelle valute di transazione, contabilizzazione e dichiarazione.
-   **Origine della transazione**: questo report di transazione mostra il conto per giornale di registrazione e per valuta di transazione, contabilizzazione e dichiarazione. In questo report viene inoltre visualizzata ogni riga del giornale di registrazione utilizzata come contropartita.


##<a name="see-also"></a>Vedere anche
- [Saldi dei conti della contabilità generale](general-ledger-account-balances.md) 
- [Esplora origine contabilità](..\accounts-payable\accounting-source-explorer.md)
- [Creazione di report finanziari](financial-reporting-getting-started.md)




