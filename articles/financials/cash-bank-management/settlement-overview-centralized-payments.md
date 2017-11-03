---
title: Panoramica sulla liquidazione per i pagamenti centralizzati
description: "Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una persona giuridica che gestisca tutti i pagamenti. In questo modo si evita di dover immettere la stessa transazione in più persone giuridiche ed è possibile risparmiare tempo grazie alla semplificazione del processo delle proposte di pagamento, del processo di liquidazione, della modifica delle transazioni aperte e della modifica delle transazioni chiuse per i pagamenti centralizzati."
author: abruer
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 222414
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a5baa25c31ea201e5ea98b158b6e02da566262c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="settlement-overview-for-centralized-payments"></a>Panoramica sulla liquidazione per i pagamenti centralizzati

[!include[banner](../includes/banner.md)]


Le organizzazioni che includono più persone giuridiche possono creare e gestire i pagamenti utilizzando una persona giuridica che gestisca tutti i pagamenti. In questo modo si evita di dover immettere la stessa transazione in più persone giuridiche ed è possibile risparmiare tempo grazie alla semplificazione del processo delle proposte di pagamento, del processo di liquidazione, della modifica delle transazioni aperte e della modifica delle transazioni chiuse per i pagamenti centralizzati. 

Quando un pagamento cliente o fornitore viene immesso in una determinata persona giuridica e liquidato con una fattura precedentemente immessa in un'altra persona giuridica, per ciascuna persona giuridica vengono generate automaticamente le transazioni contabili applicabili relative a importi da versare e da ricevere. Un record di liquidazione viene creato per ciascuna combinazione di fattura e pagamento nella transazione. A ogni record di liquidazione viene assegnato un nuovo numero di giustificativo basato sulla serie di sequenze numeriche dei giustificativi di pagamento specificata nella pagina **Parametri contabilità clienti** per i clienti e nella pagina **Parametri contabilità fornitori** per i fornitori. 

Se per sconti di cassa, rivalutazioni valuta estera, differenze in centesimi, eccessi o insufficienze di pagamento vengono generati record di liquidazione aggiuntivi, a questi ultimi viene assegnata la data della transazione del pagamento o, se successiva, la data della transazione di fatturazione. Se la liquidazione avviene dopo la registrazione del pagamento, i record di liquidazione utilizzeranno la data di registrazione della liquidazione specificata nella pagina **Liquida transazioni aperte**.
Tipi di registrazione, tipi di transazione e descrizioni standard
----------------------------------------------------------

Le transazioni giustificativo di liquidazione interaziendale utilizzano il tipo di registrazione compensazione interaziendale e i tipi di transazione compensazione interaziendale cliente e compensazione interaziendale fornitore. Per impostare le informazioni relative al tipo di transazione, è possibile utilizzare la pagina **Descrizioni predefinite**. 

I seguenti tipi di transazione sono disponibili per l'utilizzo nelle liquidazioni per una singola società e tra più società:

-   Liquidazione
-   Sconto di cassa
-   Rivalutazioni valuta estera realizzate e non realizzate
-   Differenza in centesimi
-   Eccedenza/insufficienza di pagamento

È inoltre possibile definire descrizioni predefinite per i giustificativi di compensazione interaziendale.

<a name="currency-exchange-gains-or-losses"></a>Profitti o perdite su cambi valutari
---------------------------------

Il tasso di cambio utilizzato per le transazioni cliente o fornitore viene archiviato con la transazione. I profitti o le perdite realizzati sui cambi valutari vengono registrati nella persona giuridica della fattura o nella persona giuridica del pagamento, a seconda dell'opzione selezionata nel campo **Registra profitto o perdita su cambio valutario** della pagina **Contabilità interaziendale** per la persona giuridica del pagamento. Nei seguenti esempi vengono utilizzate le valute indicate:
-   Valuta di contabilizzazione pagamento: EUR
-   Valuta di contabilizzazione fattura: USD
-   Valuta transazione pagamento: DKK
-   Valuta transazione fatturazione: CAD

#### <a name="currency-calculations"></a>Calcoli valutari

Quando una fattura immessa in una persona giuridica viene liquidata con un pagamento immesso in un'altra persona giuridica, la valuta della transazione di pagamento (DKK) viene convertita in tre passaggi:
1.  Conversione nella valuta di contabilizzazione del pagamento (EUR), applicando i tassi di cambio della persona giuridica del pagamento.
2.  Conversione nella valuta di contabilizzazione della fattura (USD).
3.  Conversione nella valuta di transazione della fattura (CAD), applicando i tassi di cambio della persona giuridica della fattura.

Nel processo di conversione vengono applicati i tassi di cambio alla data di pagamento. Se l'importo del pagamento risultante nella valuta di transazione della fattura (CAD) è identico all'importo della fattura (CAD), quest'ultima viene considerata interamente pagata. 

Quando la pagina **Liquida transazioni aperte** viene aperta da un giornale di registrazione pagamenti in cui non era stato immesso l'importo del pagamento, l'importo da liquidare viene calcolato in base alle fatture selezionate per la liquidazione nella pagina **Liquida transazioni aperte**. L'importo da liquidare viene convertito in tre passaggi:
1.  Conversione nella valuta di contabilizzazione della persona giuridica della fattura (USD), applicando i tassi di cambio della persona giuridica della fattura alla data di pagamento.
2.  Conversione nella valuta di contabilizzazione di pagamento (EUR), applicando i tassi di cambio della persona giuridica della fattura alla data di pagamento.
3.  Conversione nella valuta di transazione del pagamento (DKK).

L'importo del pagamento risultante viene trasferito nella riga del giornale di registrazione pagamenti alla chiusura della pagina **Liquida transazioni aperte**.

#### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Registrazione di profitti o perdite per valute di contabilizzazione diverse

In caso di profitti o perdite su cambio valutario, tali profitti o perdite vengono registrati nella persona giuridica specificata nel campo **Registra profitto o perdita su cambio valutario** della pagina **Contabilità interaziendale** per la persona giuridica del pagamento. L'importo dei profitto o delle perdite viene convertito nella valuta di contabilizzazione della persona giuridica in cui viene registrato il profitto o le perdite, applicando il tasso di cambio impostato per tale persona giuridica.

<a name="cash-discounts"></a>Sconti di cassa
--------------

Gli sconti di cassa generati durante il processo di compensazione interaziendale vengono registrati nella persona giuridica della fattura o nella persona giuridica del pagamento, a seconda dell'opzione selezionata nel campo **Registra sconto di cassa** della pagina **Contabilità interaziendale** per la persona giuridica del pagamento. Nella persona giuridica della fattura viene generata una transazione di liquidazione corrispondente.

<a name="overpayments-and-underpayments"></a>Eccedenze e insufficienze di pagamento
------------------------------

Le eccedenze e le insufficienze di pagamento e le tolleranze di differenza in centesimi vengono determinate in base alla persona giuridica del pagamento in caso di eccedenze di pagamento e in base alla persona giuridica della fattura in caso di insufficienze di pagamento. Il conto di registrazione utilizzato dipende dall'impostazione nel campo **Applicazione sconto di cassa** della pagina **Parametri contabilità clienti** per i clienti e nel campo **Applicazione sconto di cassa** della pagina **Parametri contabilità fornitori** per i fornitori.

-   Se l'impostazione dell'applicazione dello sconto di cassa è Specifico, oppure se l'impostazione è Non specifico e lo sconto di cassa applicabile viene registrato in una persona giuridica diversa da quella dell'eccedenza di pagamento, viene utilizzato il conto automatico per Sconto di cassa cliente, Sconto di cassa fornitore o Differenza in centesimi nella valuta di contabilizzazione. È possibile specificare questi conti nella pagina **Conti per transazioni automatiche**.
-   Se l'impostazione di applicazione dello sconto di cassa è Non specifico e lo sconto di cassa è registrato nella stessa persona giuridica dell'eccedenza di pagamento (la persona giuridica del pagamento e quella della fattura sono identiche), il conto dello sconto di cassa verrà rettificato. Se ad esempio una fattura di 100,00 con uno sconto di cassa disponibile di 3,00 viene liquidata con un pagamento di 98,00, il conto dello sconto di cassa verrà rettificato per 1,00. L'importo netto dello sconto sarà 2,00.
-   Se l'impostazione di applicazione dello sconto di cassa è Non specifico, lo sconto di cassa è registrato nella stessa persona giuridica dell'eccedenza di pagamento e l'eccedenza o insufficienza di pagamento viene liquidata con più fatture contenenti sconti di cassa, il conto dello sconto di cassa relativo all'ultima fattura verrà rettificato.

Se l'impostazione di applicazione dello sconto di cassa è Non specifico, le regole relative alla liquidazione di pagamento non specifica vengono applicate solo nelle seguenti situazioni:
-   Si è verificata un'eccedenza di pagamento.
-   L'eccedenza di pagamento viene liquidata con una o più fatture contenenti uno sconto di cassa.
-   Lo sconto di cassa viene registrato nella stessa persona giuridica dell'eccedenza di pagamento.

In tutte le altre situazioni, le eccedenze o insufficienze di pagamento vengono registrate nel conto automatico per lo sconto di cassa cliente, lo sconto di cassa fornitore o la differenza in centesimi nella valuta di contabilizzazione.

## <a name="sales-tax"></a>IVA
Le transazioni IVA rimangono nella persona giuridica in cui sono state registrate originariamente. 

In caso di registrazione dell'IVA per un pagamento anticipato, la compensazione interaziendale storna l'IVA sul pagamento anticipato nella persona giuridica che l'ha effettuato. Le imposte della persona giuridica della fattura rimangono all'interno di tale persona giuridica.

## <a name="financial-dimensions"></a>Dimensioni finanziarie
In caso di pagamenti cliente, le transazioni relative a importi da versare e da ricevere nella persona giuridica del pagamento utilizzano le dimensioni finanziarie specificate per il conto riepilogativo della contabilità clienti relativo al pagamento in liquidazione. In caso di pagamenti cliente, le transazioni relative a importi da versare e da ricevere nella persona giuridica del pagamento utilizzano le dimensioni finanziarie specificate per il conto riepilogativo della contabilità clienti relativo al pagamento in liquidazione. 

In caso di pagamenti fornitore, le transazioni relative a importi da versare e da ricevere nella persona giuridica del pagamento utilizzano le dimensioni finanziarie specificate per il conto riepilogativo della contabilità fornitori relativo al pagamento in liquidazione. In caso di pagamenti fornitore, le transazioni relative a importi da versare e da ricevere nella persona giuridica del pagamento utilizzano le dimensioni finanziarie specificate per il conto riepilogativo della contabilità fornitori relativo al pagamento in liquidazione.

## <a name="withholding-tax"></a>Ritenuta d'acconto
Il conto fornitore associato alla fattura viene utilizzato per determinare se la ritenuta d'acconto deve essere calcolata. Se la ritenuta d'acconto viene applicata, l'imposta verrà calcolata nella persona giuridica associata alla fattura. Se le persone giuridiche utilizzano valute diverse, verrà utilizzato il tasso di cambio dalla persona giuridica associata alla fattura.






