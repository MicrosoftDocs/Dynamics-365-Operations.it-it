---
title: Panoramica su eliminazione e consolidamento
description: Questo articolo fornisce informazioni generali sul processo di consolidamento ed eliminazione. Sono incluse le risposte ad alcune domande frequenti.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13151
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 60dd33f296a37f0010a948c410738ce5486b780e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="consolidation-and-elimination-overview"></a>Panoramica su eliminazione e consolidamento

[!INCLUDE [banner](../includes/banner.md)]

Questo articolo fornisce informazioni generali sul processo di consolidamento ed eliminazione. Sono incluse le risposte ad alcune domande frequenti.

Quando si consolidano i dati, i risultati finanziari di più società affiliate vengono combinati in un risultato per un'unica società consolidata. Le affiliate potrebbero utilizzare versioni o sistemi diversi, non essere completamente di proprietà e utilizzare valute diverse. Sono disponibili più opzioni per il consolidamento dei dati:

-   **Consolida online** Questa opzione consolida i saldi quotidiani in base ai conti e alle dimensioni selezionati e li archivia in una società di consolidamento.
-   **Report finanziari** Questa opzione abilita il consolidamento delle transazioni e dei saldi e può essere generata in qualsiasi momento. Più livelli di gerarchie possono essere create e più valute di dichiarazione più possono essere visualizzate.
-   **Consolida con importazione** Questa opzione importa i saldi in una società di consolidamento.
-   **Esporta saldi società** Questa opzione fornisce un file di esportazione dei saldi della società. Il file può quindi essere importato in altre istanze o sistemi. I report finanziari possono essere utilizzati per esportare i saldi in un file di Microsoft Excel.

Le eliminazioni possono essere dichiarate in più modi:

-   Le regole di eliminazione possono essere impostate nel sistema e quindi elaborate durante il processo di consolidamento o mediante una proposta di eliminazione. Le regole possono essere registrate in qualsiasi società che abbia l'opzione **Utilizza per processo di eliminazione finanziario** selezionata nell'impostazione della persona giuridica.
-   Una società separata può essere creata e utilizzata per determinare e registrare manualmente le transazioni di eliminazione. La società può essere utilizzata nel processo di consolidamento o nei report finanziari.
-   I conti e le dimensioni finanziarie che vengono utilizzati per determinare l'attività interaziendale possono essere filtrati in una definizione di riga o di colonna nei report finanziari e possono essere utilizzate le funzionalità complete di drill-down. Una colonna o una riga calcolata potrà quindi essere utilizzata per rimuovere i conti e le dimensioni finanziarie dal totale consolidato.

Sono disponibili molti scenari di consolidamento e ciascun metodo può gestire gli scenari in vari modi.

## <a name="frequently-asked-questions"></a>Domande frequenti
1.  Si preferisce registrare le eliminazioni in un database. Quali sono le opzioni disponibili?

Sono disponibili più opzioni. È possibile utilizzare l'opzione **Consolida online** e includere le eliminazioni durante il processo o come proposta. Le transazioni verranno registrate nella società di consolidamento. In alternativa, è possibile avere una società separata in cui si creano manualmente le eliminazioni e quindi utilizzare la società nei report finanziari o nel processo di consolidamento.

2.  I risultati consolidati sono necessari in più valute di dichiarazione.

L'opzione **Report finanziari** dispone di un numero illimitato di valute di dichiarazione. I dati vengono convertiti durante la creazione del report, in base al tipo di tasso di cambio e al metodo di conversione della valuta impostati sul conto principale. Tuttavia, poiché l'opzione **Consolida online** ha una sola valuta di dichiarazione, è necessaria una società consolidata per ogni valuta di dichiarazione se si utilizza tale opzione. L'opzione **Report finanziari** è il metodo consigliato.

3.  Si desiderano visualizzare i dettagli a livello di transazione per ogni società.

L'opzione **Report finanziari** è la soluzione, perché i dettagli a livello di transazione può essere visualizzati per qualsiasi società quando vengono incluse nella definizione dell'albero gerarchico.

4.  Si utilizza la pianificazione o il controllo del budget e deve essere consolidato.
L'opzione **Report finanziari** è la soluzione per consolidare i dati di pianificazione o del controllo del budget.

5.  Le filiali sono dislocate in tutto il mondo e sono disponibili più piani dei conti. Qual è il metodo migliore per il consolidamento dei dati?

Sono disponibili più opzioni per gestire i piani dei conti. È possibile utilizzare l'opzione **Consolida online** e quindi si sceglie di utilizzare il conto di consolidamento definito nel conto principale o un gruppo di conti di consolidamento. È inoltre possibile utilizzare l'opzione **Report finanziari**, includere più collegamenti nelle dimensioni finanziarie nella definizione di riga e mappare i conti.

6.  Sono necessari più livelli di consolidamento. In altre parole, per prima cosa si consolidano tutte le filiali europee nella sterlina inglese (GBP). Quindi con questi dati, l'importo viene consolidato in dollari. Come si può effettuare questa operazione?

Quando sono necessari più livelli di consolidamento e si utilizzano valute diverse per ogni livello, è necessario usare l'opzione **Consolida online**. Devono essere create più società di consolidamento diverse nelle contabilità e nelle valute di dichiarazione. Il consolidamento deve quindi essere eseguito più volte. L'opzione **Report finanziari** converte sempre la valuta di contabilizzazione di origine della società nella valuta selezionata.

7.  Le affiliate utilizzano un sistema diverso. Come si possono consolidare?

Utilizzare l'opzione **Consolida con importazione** per importare i saldi in una società di consolidamento.

8.  Alcune filiali non sono totalmente di proprietà. Qual è il metodo migliore per il loro consolidamento?

Sono disponibili più opzioni per le filiali parzialmente di proprietà. Mediante l'opzione **Report finanziari**, è possibile specificare una definizione dell'albero gerarchico e la proprietà. È inoltre possibile utilizzare una riga o una colonna calcolata per rappresentare l'importo parzialmente di proprietà. È inoltre possibile visualizzare gli interessi di minoranza come riga separata in un report. È inoltre possibile utilizzare l'opzione **Consolida online**. La scheda **Persone giuridiche** include la colonna **Proprietà** in cui è possibile definire la percentuale di proprietà della società consolidata.

9.  L'organizzazione deve visualizzare i consolidamenti per Business Unit o desidera utilizzare le gerarchie organizzative.

L'opzione **Report finanziari** è la soluzione. Le gerarchie organizzative che includono persone giuridiche o dimensioni finanziarie possono essere dichiarate nei report finanziari. È inoltre possibile creare proprie gerarchie multilivello utilizzando una definizione dell'albero gerarchico con una combinazione di persone giuridiche e valori di dimensione.

10. Sono disponibili più istanze del sistema.

Utilizzando l'opzione **Esporta saldi società** per esportare da un'istanza e quindi utilizzando l'opzione **Consolida con importazione** sull'altra istanza, è possibile consolidare i dati.


Per ulteriori informazioni, vedere [Rivalutazione della valuta in una società di consolidamento](..\general-ledger\currency-revaluation-consolidation-company.md).



