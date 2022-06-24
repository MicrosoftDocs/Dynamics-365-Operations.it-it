---
title: Panoramica sui modelli di configurazione prodotto
description: Questo articolo definisce termini e concetti importanti relativi ai modelli di configurazione prodotto. I modelli di configurazione prodotto consentono di creare una struttura di prodotto generica utilizzabile per configurare più varianti di un singolo prodotto.
author: t-benebo
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails, PCProductConfigurationModelListPage, PCModalWaitDialog, PCTemplateConfigurationManager, PCConfigurationUIGrouping
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "4031"
- intro-internal
ms.assetid: 70b968e8-e550-4731-823d-d713b8910f7b
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9bee2d68a2ed2aa339ddf8232bba4541f4fe52b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871922"
---
# <a name="product-configuration-models-overview"></a>Panoramica sui modelli di configurazione prodotto

[!include [banner](../includes/banner.md)]

Questo articolo definisce termini e concetti importanti relativi ai modelli di configurazione prodotto. I modelli di configurazione prodotto consentono di creare una struttura di prodotto generica utilizzabile per configurare più varianti di un singolo prodotto.

I modelli di configurazione prodotto vengono creati per rappresentare una struttura di prodotto generica. Dopo aver impostato un modello di configurazione prodotto, è possibile configurare una variante prodotto specifico con una distinta base (DBA) e un ciclo univoci. I modelli di configurazione prodotto utilizzano sia i vincoli dichiarativi che i calcoli imperativi per gestire le relazioni e i limiti tra varianti prodotto diverse. È possibile configurare gli articoli negli ordini cliente, nelle offerte di vendita, negli ordini fornitore e negli ordini di produzione. Nella seguente tabella sono descritti i termini e i concetti relativi ai vincoli di tabella.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Componenti</td>
<td>I componenti costituiscono i blocchi predefiniti principali di un modello di configurazione prodotto. I componenti vengono visualizzati in una struttura ad albero nella pagina <strong>Dettagli modello di configurazione prodotto basato su vincoli</strong>. I componenti possono contenere i seguenti elementi:
<ul>
<li>Attributi</li>
<li>Vincoli</li>
<li>Calcoli</li>
<li>Sottocomponenti</li>
<li>Requisiti utente</li>
<li>Righe DBA</li>
<li>Operazioni ciclo di lavorazione</li>
</ul></td>
</tr>
<tr class="even">
<td>Attributi</td>
<td>Gli attributi descrivono tutte le funzionalità del modello di configurazione prodotto. È possibile utilizzare gli attributi per specificare le funzionalità che è possibile selezionare quando viene configurato un prodotto specifico. Gli attributi vengono utilizzati nei vincoli e nelle condizioni. Quando gli attributi vengono creati e aggiunti a un modello di configurazione prodotto, si fa riferimento ai tipi di attributo correlati. Può essere impostato un valore predefinito per un attributo. Il valore predefinito viene utilizzato nell'interfaccia utente (UI) di configurazione quando viene configurato il modello di configurazione prodotto. È possibile specificare che un attributo sia obbligatorio, di sola lettura o nascosto.
<ul>
<li><strong>Obbligatorio</strong>: quando il prodotto viene configurato, deve essere impostato un valore per l'attributo.</li>
<li><strong>Di sola lettura</strong>: il valore dell'attributo viene visualizzato durante una sessione di configurazione, ma non può essere modificato.</li>
<li><strong>Nascosto</strong>: il valore dell'attributo è incluso nei vincoli e condizioni, ma non viene visualizzato durante una sessione di configurazione.</li>
</ul>
È inoltre possibile specificare una condizione per gli attributi. Se la condizione viene soddisfatta, per l'attributo obbligatorio deve essere immesso un valore. Le condizioni sono espressioni che devono essere soddisfatte dagli attributi, dalle righe DBA e dalle operazioni del ciclo di lavorazione da includere nel modello di configurazione prodotto. Qualsiasi attributo a cui si fa riferimento in una condizione diventa obbligatorio. È consigliabile selezionare l'attributo come obbligatorio nella scheda <strong>Attributi</strong>. In questo modo sarà più semplice identificare gli attributi obbligatori. I valori dell'attributo rappresentano un elemento importante del riutilizzo delle configurazioni. Il sistema utilizza i valori attributo per determinare l'esistenza di una configurazione che corrisponda alle selezioni eseguite da un utente durante una sessione di configurazione.</td>
</tr>
<tr class="odd">
<td>Tipi di attributo</td>
<td>I tipi di attributo specificano i tipi di set di dati per gli attributi utilizzati nel modello di configurazione prodotto. Vengono utilizzati i seguenti tipi di attributo:
<ul>
<li><strong>Intero</strong> con o senza un intervallo</li>
<li><strong>Decimali</strong></li>
<li><strong>Testo</strong> con o senza un elenco fisso</li>
<li><strong>Booleano</strong></li>
</ul>
Se il tipo di attributo è <strong>Boolean</strong>, <strong>Intero</strong> con un intervallo, o <strong>Testo</strong> con un elenco fisso, l'insieme dei valori è disponibile quando un modello di configurazione prodotto è installato. <strong>Nota:</strong> il risolutore della configurazione prodotto riconosce solo i seguenti tipi di attributo: <strong>Booleano</strong>, <strong>Testo</strong> con elenco fisso e <strong>Intero</strong> con intervallo. Di conseguenza, è possibile utilizzare solo quei tipi di attributo nei vincoli di espressione e condizioni.</td>
</tr>
<tr class="even">
<td>Vincoli</td>
<td>I vincoli descrivono le restrizioni della configurazione del modello prodotto. I vincoli vengono utilizzati per garantire che solo i valori validi vengano selezionati quando il prodotto viene configurato. I vincoli possono essere sia vincoli di espressione che vincoli di tabella:
<ul>
<li>I vincoli di espressione possono essere utilizzati solo per il componente a cui sono correlati. I vincoli di espressione per un componente possono fare riferimento ad attributi di sottocomponenti del componente. Il solver di configurazione prodotto viene utilizzato per risolvere i vincoli ed è necessario utilizzare la sintassi del solver quando si scrivono i vincoli. Per ulteriori informazioni, vedi il collegamento dell'articolo sui vincoli di espressione e i vincoli di tabella.</li>
<li>I vincoli di tabella devono essere definiti prima di poter essere applicati a un componente in un modello di configurazione prodotto. I vincoli di tabella possono essere definiti dall'utente o dal sistema. Un vincolo di tabella definito dall'utente è un tipo di matrice che può essere utilizzato per descrivere il set di combinazioni per i valori dell'attributo definiti dai tipi di attributo. Ad esempio, se vengono prodotti altoparlanti, la matrice per il vincolo di tabella definito dall'utente può presentare colonne per il rivestimento e la griglia dell'altoparlante.</li>
</ul>
<strong>Esempio</strong> Gli altoparlanti sono disponibili in quattro rivestimenti: nero, quercia, palissandro e bianco. La griglia frontale degli altoparlanti può essere nei seguenti colori: nero, metallo o bianco. La finitura in nero è disponibile per tutte le griglie, mentre le altre finiture sono limitate a griglie specifiche. Nella tabella indicata di seguito viene illustrato un esempio delle informazioni visualizzate nella scheda <strong>Combinazioni consentite</strong> nella pagina <strong>Modifica vincolo di tabella</strong>.
<table>
<thead>
<tr class="header">
<th>Rivestimento del cabinet</th>
<th>Griglia anteriore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nero</td>
<td>Nero</td>
</tr>
<tr class="even">
<td>Nero</td>
<td>Metallo</td>
</tr>
<tr class="odd">
<td>Nero</td>
<td>Bianco</td>
</tr>
<tr class="even">
<td>Quercia</td>
<td>Nero</td>
</tr>
<tr class="odd">
<td>Palissandro</td>
<td>Bianco</td>
</tr>
<tr class="even">
<td>Bianco</td>
<td>Nero</td>
</tr>
<tr class="odd">
<td>Bianco</td>
<td>Bianco</td>
</tr>
</tbody>
</table>
Un vincolo di tabella definito dal sistema rappresenta un mapping tra un tipo di attributo e un campo in una tabella Supply Chain Management. Un vincolo di tabella definito dal sistema collega dinamicamente il tipo di attributo al campo. Il collegamento consente all'attributo in un modello di configurazione prodotto di riflettere i dati del campo nella tabella di Supply Chain Management.</td>
</tr>
<tr class="odd">
<td>Calcoli</td>
<td>I calcoli rappresentano un supplemento ai vincoli. È possibile utilizzare un calcolo per eseguire operazioni aritmetiche su attributi di tipo <strong>Decimale</strong> e<strong>Intero</strong> o operazioni logiche che includono attributi di tipo <strong>Testo</strong> con un elenco fisso e <strong>Booleano</strong>. Un calcolo ha un attributo di destinazione è un attributo che detiene il risultato dell'espressione di calcolo. L'espressione di calcolo viene creata utilizzando l'editor espressioni.</td>
</tr>
<tr class="even">
<td>Sottocomponenti</td>
<td>I sottocomponenti riflettono la struttura ad albero del modello di configurazione prodotto. È possibile utilizzare i sottocomponenti per creare la struttura del modello di configurazione prodotto. I sottocomponenti fanno riferimento ai componenti esistenti. Di conseguenza, l'utilizzo dei sottocomponenti incoraggia il riutilizzo dei componenti in più modelli di configurazione prodotto. Nella pagina <strong>Dettagli riga DBA</strong> per un sottocomponente, è possibile selezionare un valore distinto per il sottocomponente. In alternativa, è possibile selezionare un attributo per il quale il valore viene selezionato quando il modello di configurazione prodotto viene installato. Per includere un prodotto come componente o sottocomponente, quando si crea il prodotto è necessario specificare quanto segue nella pagina<strong> Crea prodotto</strong>:
<ul>
<li>Nel campo <strong>Tipo di prodotto</strong> selezionare <strong>Articolo</strong>.</li>
<li>Nel campo <strong>Sottotipo di prodotto</strong> selezionare <strong>Rappresentazione generale prodotto</strong>.</li>
<li>Nel campo <strong>Tecnologia di configurazione</strong> selezionare <strong>Configurazione basata su vincoli</strong>.</li>
</ul>
È possibile visualizzare se un prodotto rilasciato può essere utilizzato come un componente o sottocomponente nella scheda <strong>Generale</strong> della pagina <strong>Dettagli prodotto rilasciato</strong>. Se <strong>Configurazione basata su vincoli</strong> è selezionato nel campo <strong>Tecnologia di configurazione</strong>, il prodotto può essere utilizzato come componente o sottocomponente. È possibile nascondere i sottocomponenti affinché non vengano visualizzati all'utente durante una sessione di configurazione. Vengono altresì nascosti gli attributi, i sottocomponenti e i requisiti utente correlati al sottocomponente.</td>
</tr>
<tr class="odd">
<td>Requisiti utente</td>
<td>I requisiti utente rappresentano un'astrazione tra i requisiti utente e i componenti e gli attributi specifici. Non è possibile eseguire il mapping dei requisiti utente su un articolo. Ad esempio, un cliente sta effettuando l'acquisto di un sistema home theatre. Il rappresentante potrebbe chiedere informazioni sulla dimensione della stanza in cui il cliente intende installare il sistema per determinare quanti watt sono necessari. In questo esempio, la dimensione della stanza può rappresentare una richiesta utente che consente di determinare il valore attributo appropriato per un componente specifico. È possibile nascondere le richieste utente in modo che non vengano visualizzate dall'utente durante una sessione di configurazione. Possono essere altresì nascosti gli attributi, i sottocomponenti e i requisiti utente correlati alle richieste utente. È possibile scrivere una condizione per controllare se una richiesta utente può essere nascosta. È necessario utilizzare la sintassi OML (Optimization Modeling Language) per scrivere la condizione.</td>
</tr>
<tr class="even">
<td>Righe DBA</td>
<td>Le righe DBA rappresentano i singoli materiali dei componenti nel modello di configurazione prodotto. Nella pagina <strong>Dettagli riga DBA</strong> tutti gli articoli sono disponibili per la selezione. Una condizione può essere aggiunta alla riga DBA per poter variare le righe DBA selezionate per una variante prodotto specifico, in base alla selezione dell'utente quando il modello di configurazione prodotto è installato. Le condizioni sono espressioni che devono essere soddisfatte dagli attributi, dalle righe DBA e dalle operazioni del ciclo di lavorazione da includere nel modello di configurazione prodotto. Nella pagina <strong>Dettagli riga DBA</strong> è possibile selezionare un valore distinto. In alternativa, è possibile effettuare il mapping di un attributo per cui il valore è selezionato quando il modello di configurazione prodotto viene impostato.</td>
</tr>
<tr class="odd">
<td>Operazioni ciclo di lavorazione</td>
<td>Nella pagina <strong>Dettagli operazione ciclo di lavorazione</strong> è possibile selezionare un valore distinto. In alternativa, è possibile effettuare il mapping di un attributo per cui il valore è selezionato quando il modello di configurazione prodotto viene impostato. Le condizioni sono scritte come vincoli di espressione. Le condizioni sono espressioni che devono essere soddisfatte dagli attributi, dalle righe DBA e dalle operazioni del ciclo di lavorazione da includere nel modello di configurazione prodotto.</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]