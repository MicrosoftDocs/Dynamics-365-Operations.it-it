---
title: Ricalcolare i costi di sostituzione e i valori assicurati per i gruppi di cespiti
description: Questo articolo illustra il processo per aggiornare i costi di sostituzione e i valori assicurati per i cespiti.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 74af494f261af20d6762176d780e90b4d6644b4c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Ricalcolare i costi di sostituzione e i valori assicurati per i gruppi di cespiti

[!include[banner](../includes/banner.md)]


Questo articolo illustra il processo per aggiornare i costi di sostituzione e i valori assicurati per i cespiti.

È possibile che periodicamente si riceva una notifica relativa al cambiamento del costo di sostituzione o assicurazione di cespiti specifici. È ad esempio possibile che il proprio superiore richieda di aumentare del 3% il costo di sostituzione di tutti i cespiti a causa dell'inflazione del 3% registrata l'anno precedente. 

Benché sia possibile modificare il costo di sostituzione e il valore assicurato di singoli cespiti nel modulo Cespiti, tramite il modulo Aggiorna costi di sostituzione e valori assicurati questi valori potranno essere aggiornati per un gruppo di cespiti contemporaneamente. In questo argomento viene descritta la procedura per aggiornare i valori per gruppi cespite o per cespiti specifici all'interno di gruppi.

## <a name="how-values-are-updated"></a>Modalità di aggiornamento dei valori
Per ricalcolare i costi di sostituzione e i valori assicurati per gruppi cespite, è necessario innanzitutto specificare la percentuale in base alla quale modificare i costi di sostituzione e i valori assicurati esistenti, quindi eseguire l'aggiornamento periodico per ricalcolare effettivamente i valori. Specificare la percentuale nei campi Fattore costo di sostituzione e Fattore valore assicurato nel modulo Gruppi cespite. Benché questi fattori vengano specificati per il gruppo di cespiti, quando si utilizza il modulo Aggiorna costi di sostituzione e valori assicurati è possibile selezionare se ricalcolare il costo di sostituzione e il valore assicurato solo per cespiti specifici di un gruppo. 

Quando si utilizza il modulo Aggiorna costi di sostituzione e valori assicurati per ricalcolare il costo di sostituzione e il valore assicurato per i cespiti, vengono utilizzate le seguenti formule:

-   \[(Fattore costo di sostituzione del gruppo di cespiti / 100) + 1\] \* Costo di sostituzione esistente del cespite
-   \[(Fattore valore assicurato del gruppo di cespiti / 100) + 1\] \* Valore assicurato esistente del cespite

> [!NOTE] 
> Se si utilizza il modulo Aggiorna costi di sostituzione e valori assicurati, verranno aggiornati per i cespiti selezionati sia il costo di sostituzione sia il valore assicurato. Non è possibile specificare l'aggiornamento di un solo valore. Per lasciare invariato un valore e aggiornare l'altro, immettere 0 (zero) come fatto nel modulo Gruppi cespite. Se il fattore non viene specificato o viene impostato su zero, nell'aggiornamento il calcolo non verrà eseguito. L'aggiornamento periodico non incide sul valore contabile e sul valore contabile netto dei cespiti. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a>Modalità di utilizzo di una data per la selezione degli articoli da aggiornare
Per impostazione predefinita, con il processo di aggiornamento vengono aggiornati i cespiti selezionati che non sono stati aggiornati nella data corrente, ma che possono essere stati aggiornati nei giorni precedenti. Ad esempio, &lt; data corrente indica "prima di oggi". È possibile modificare la data nel modulo Aggiorna costi di sostituzione e valori assicurati facendo clic sul pulsante Seleziona. I criteri della data specificati vengono confrontati con la data dell'ultimo aggiornamento periodico del cespite (campo Ultimo aggiornamento periodico valore/costo nel modulo Cespiti). Ogni volta che viene eseguito l'aggiornamento del costo di sostituzione o del valore assicurato di un cespite, il campo Ultimo aggiornamento periodico valore/costo viene automaticamente aggiornato alla data corrente. 

Esempio 

Si consideri ad esempio uno scenario in cui il costo di sostituzione dei gruppi Veicoli, Mobili per ufficio ed Edifici è stato aggiornato del 5% da un giorno. Si ritiene pertanto che tali cespiti siano accuratamente aggiornati. Per escluderli dall'aggiornamento che si desidera eseguire nella giornata corrente per tutti gli altri cespiti, immettere nel campo Ultimo aggiornamento periodico valore/costo una data antecedente a quella del giorno precedente (&lt; data di ieri), poiché l'ultimo aggiornamento per i gruppi Veicoli, Mobili per ufficio ed Edifici è stato eseguito al di fuori dei criteri di data immessi.

## <a name="cumulative-effect-of-each-update"></a>Effetto cumulativo di ciascun aggiornamento
Poiché ciascun aggiornamento produce un effetto cumulativo, è consigliabile pianificare accuratamente gli aggiornamenti. Se ad esempio il martedì vengono aumentati del 3% tutti i cespiti, quindi il venerdì vengono aumentati del 4% i mobili per ufficio, i mobili per ufficio risulteranno aumentati del 7,12% in totale.

## <a name="scenario"></a>Scenario
Si riceve dal responsabile la notifica delle seguenti modifiche per i cespiti:
-   Aumentare del 3,25% il costo di sostituzione di tutti i cespiti, ad eccezione dei computer.
-   Aumentare di un ulteriore 1% il costo di sostituzione di tutti i mobili per ufficio.
-   Ridurre del 10% il costo di sostituzione e il valore assicurato di tutti i computer.

È possibile apportare le seguenti modifiche:
1.  Nel modulo Gruppi cespite, per tutti i gruppi cespite, ad eccezione dei gruppi Mobili per ufficio e Computer, digitare 3,25 nel campo Fattore costo di sostituzione e 0 nel campo Fattore valore assicurato.
2.  Per il gruppo Mobili per ufficio, digitare 4,25 nel campo Fattore costo di sostituzione e 0 nel campo Fattore valore assicurato.
3.  Per il gruppo Computer, digitare -10 nel campo Fattore costo di sostituzione e -10 nel campo Fattore valore assicurato.
4.  Nel modulo Aggiorna costi di sostituzione e valori assicurati, fare clic su OK per eseguire il ricalcolo per tutti i cespiti.

Il giorno successivo il proprio superiore informa che i computer sono diminuiti dell'8% anziché del 10% e che è pertanto necessario correggere i costi di sostituzione e i valori assicurati. Per correggere l'errore, è possibile utilizzare uno dei seguenti metodi:
-   Modificare manualmente i campi Valore assicurato e Costo di sostituzione del modulo Cespiti per ciascun cespite del gruppo di cespiti Computer. Calcolare e immettere manualmente i valori come se l'importo originale fosse stato ridotto dell'8%. Utilizzando questo metodo, non si utilizza il modulo Aggiorna costi di sostituzione e valori assicurati.
-   Immettere i fattori di costo di sostituzione e di valore assicurato per il gruppo Computer nei campi Fattore costo di sostituzione e Fattore valore assicurato nel modulo Gruppi cespite. In questo modo verrà ripristinato il valore originale del cespite (prima della riduzione del 10%) e verrà applicata la riduzione dell'8% al valore originale. Utilizzare quindi il modulo Aggiorna costi di sostituzione e valori assicurati per ricalcolare i valori, a seconda dei fattori immessi.

> [!NOTE]  
> Non è possibile stornare il fattore -10 immettendo un fattore 10 positivo o un fattore 2, ovvero la differenza tra -10 e -8, poiché gli importi non verrebbero calcolati come desiderato. 






