---
title: Report finanziari del bilancio di verifica
description: "In questo articolo viene descritto i report predefiniti per i bilanci di verifica. Sono descritti inoltre i blocchi predefiniti associati a questi report e come è possibile modificare i report in modo da soddisfare i requisiti aziendali."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6405599186c8d07ac5ade19d3b7d27ae83b036ff
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="trial-balance-financial-reports"></a>Report finanziari del bilancio di verifica

[!include[banner](../includes/banner.md)]


In questo articolo viene descritto i report predefiniti per i bilanci di verifica. Sono descritti inoltre i blocchi predefiniti associati a questi report e come è possibile modificare i report in modo da soddisfare i requisiti aziendali. 

<a name="default-trial-balance-reports"></a>Report predefiniti del bilancio di verifica
-----------------------------

Tre report di bilancio di verifica sono disponibili in Creazione di report finanziari in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

| Report predefinito                                 | Funzionamento                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Bilancio di verifica dettagliato - Predefinito               | Fornisce informazioni sul saldo per tutti i conti e include i saldi in Avere e in Dare e l'importo netto di questi, insieme alla data della transazione, al giustificativo e alla descrizione del giornale di registrazione.                  |
| Bilancio di verifica riepilogativo - Predefinito                | Fornisce informazioni sul saldo per tutti i conti e include i saldi di chiusura e di apertura e i saldi in Avere e in Dare, insieme alle differenze nette.                                        |
| Bilancio di verifica riepilogativo annuale - Predefinito | Fornisce informazioni sul saldo per tutti i conti e include i saldi di chiusura e di apertura e i saldi in Avere e in Dare, insieme alle differenze nette per l'anno corrente e l'anno precedente. |

## <a name="building-blocks"></a>Blocchi predefiniti
I report finanziari del bilancio di verifica utilizzano i seguenti blocchi predefiniti.

| Report predefinito                                 | Definizione riga          | Definizione colonna                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Bilancio di verifica dettagliato - Predefinito               | Bilancio di verifica - Predefinito | Bilancio di verifica dettagliato - Predefinito               |
| Bilancio di verifica riepilogativo - Predefinito                | Bilancio di verifica - Predefinito | Bilancio di verifica riepilogativo - Predefinito                |
| Bilancio di verifica riepilogativo annuale - Predefinito | Bilancio di verifica - Predefinito | Bilancio di verifica riepilogativo annuale - Predefinito |

### <a name="row-definition"></a>Definizione riga

La definizione di riga, Bilancio di verifica - Predefinito, contiene una singola riga che esegue il pull in tutti i conti principali. Di conseguenza, chiunque può generare il report senza dover apportare eventuali modifiche. Quando si visualizza il report, si analizza la singola riga per visualizzare i dettagli relativi a ciascun conto. È possibile modificare la definizione di riga in modo da includere più dettagli. Per modificare la definizione di riga Bilancio di verifica - Predefinito in modo che includa le righe per tutti i conti, attenersi ai passaggi seguenti.

1.  Fare clic su **Modifica** e quindi su **Inserisci righe da dimensioni**. Il comando **Inserisci righe da dimensioni** consente di scegliere le dimensioni che si desidera inserire nella definizione di riga. Per questa definizione di riga, si utilizza **Conto principale**.
2.  Assicurarsi che **Conto principale** contenga tutte le e commerciali (&) e quindi fare clic su **OK**.

La definizione di riga ora contiene tutti i conti principale per la persona giuridica predefinita.

### <a name="column-definition"></a>Definizione colonna

Ogni report di bilancio di verifica utilizza una definizione di colonna diversa. Le definizioni di colonna contengono i diversi tipi di colonna per fornire diversi livelli di dettagli e dati finanziari.

-   **Bilancio di verifica dettagliato - Tipi predefiniti di colonna:**
    -   **DESC** - Descrizione della definizione di riga.
    -   **ACCT** - Codici conto
    -   **ATTR (3)** - Attributi:
        -   Data della transazione
        -   Giustificativo
        -   Descrizione del giornale di registrazione
    -   **FD** I dati finanziari contenenti solo i debiti
    -   **FD** I dati finanziari contenenti solo i crediti
    -   **CALC** La differenza netta
-   **Bilancio di verifica riepilogativo - Tipi predefiniti di colonna:**
    -   **ACCT** - Codici conto
    -   **DESC** - Descrizione della definizione di riga.
    -   **ATTR** Un attributo:
        -   Giustificativo
    -   **FD** I dati finanziari del saldo iniziale
    -   **FD** I dati finanziari contenenti solo i debiti
    -   **FD** I dati finanziari contenenti solo i crediti
    -   **CALC** La differenza netta
    -   **CALC** Il saldo di chiusura
-   **Bilancio di verifica riepilogativo annuale - Predefinito:**
    -   **ACCT** - Codici conto
    -   **DESC** - Descrizione della definizione di riga.
    -   **ATTR** Un attributo
        -   Giustificativo
    -   **FD** I dati finanziari del saldo iniziale per l'anno in corso
    -   **FD** I dati finanziari contenenti solo i debiti per l'anno in corso
    -   **FD** I dati finanziari contenenti solo i crediti per l'anno in corso
    -   **CALC** La differenza netta
    -   **CALC** Il saldo di chiusura
    -   **FD** I dati finanziari contenenti solo i debiti per l'anno precedente
    -   **FD** I dati finanziari contenenti solo i crediti per l'anno precedente

 

<a name="see-also"></a>Vedere anche
--------

[Creazione di report finanziari](financial-reporting-getting-started.md)

[Visualizza report finanziari](view-financial-reports.md)

[Blog sui report finanziari di Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




