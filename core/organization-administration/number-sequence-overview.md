---
title: Panoramica delle sequenze numeriche
description: In Microsoft Dynamics 365 for Operations le sequenze numeriche vengono utilizzate per generare identificatori univoci leggibili per record transazioni e dati master che richiedono identificatori. Un record transazioni o dati master che richiede un identificatore viene definito <em>riferimento</em>.
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a2dcbbbd0b67c171d5a26bbf2053d159f7367cc5
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="number-sequence-overview"></a>Panoramica delle sequenze numeriche

[!include[banner](../includes/banner.md)]


In Microsoft Dynamics 365 for Operations le sequenze numeriche vengono utilizzate per generare identificatori univoci leggibili per record transazioni e dati master che richiedono identificatori. Un record transazioni o dati master che richiede un identificatore viene definito <em>riferimento</em>.

Prima di poter creare nuovi record per un riferimento in Microsoft Dynamics 365 for Operations, è necessario impostare una sequenza numerica e associarla al riferimento. Per impostare sequenze numeriche, è consigliabile utilizzare le pagine in **Amministrazione organizzazione**. Se sono necessarie impostazioni specifiche del modulo, è possibile utilizzare la pagina parametri in un modulo per specificare sequenze numeriche per i riferimenti in quel modulo. In **Contabilità clienti** e **Contabilità fornitori**, ad esempio, è possibile impostare gruppi di sequenze numeriche per allocare sequenze numeriche specifiche a fornitori o clienti specifici. Quando si imposta una sequenza numerica, è necessario specificare un ambito per definire in quale organizzazione verrà utilizzata la sequenza numerica. L'ambito può essere **Condiviso**, **Società**, **Persona giuridica** o **Unità operativa**. Gli ambiti **persona giuridica** e **società** possono anche essere combinati con **Periodo di calendario fiscale** per creare sequenze numeriche ancora più specifiche. I formati delle sequenze numeriche sono dati da segmenti. Le sequenze numeriche con un ambito diverso da **Condiviso** possono contenere segmenti corrispondenti all'ambito. Una sequenza numerica con un ambito **Persona giuridica**, ad esempio, può contenere un segmento persona giuridica. Includendo un segmento ambito nel formato della sequenza numerica, è possibile identificare l'ambito di un record facendo riferimento al relativo numero. Oltre ai segmenti che corrispondono agli ambiti, i formati delle sequenze numeriche possono contenere i segmenti **Costante** e **Segmenti alfanumerici**. Un segmento **costante** può contenere un set di lettere, numeri o simboli che non cambia. Un segmento **alfanumerico** contiene un set di lettere o numeri che aumentano ogni volta che viene utilizzato un numero. Utilizzare un simbolo di numero (\#) per rappresentare i numeri che aumentano e la e commerciale (&) per rappresentare le lettere che aumentano. Il formato t \#\#\#\#\#\_2017, ad esempio, consente di ottenere la sequenza 00001\_2017, 00002\_2017 e così via.
Esempi di sequenze numeriche
------------------------

Negli esempi riportati di seguito viene illustrato come utilizzare segmenti per creare formati di sequenze numeriche: In particolare, gli esempi dimostrano gli effetti dell'utilizzo dei segmenti ambito.
### <a name="expense-report-numbers"></a>Numeri di note spese

Nell'esempio seguente i numeri delle note spese vengono impostati per la persona giuridica **CS**. **Area:** viaggi e spese **Riferimento:** numero report spese **Ambito:** persona giuridica **Persona giuridica:** CS
| Segmenti  | Tipo di segmento | Valore     |
|-----------|--------------|-----------|
| Segmento 1 | Persona giuridica | CS        |
| Segmento 2 | Costante     | -SPESA- |
| Segmento 3 | Alfanumerico | \#\#\#\#  |

**Esempio di numero formattato**: CS-EXPENSE-0039 È possibile impostare un formato di sequenza numerica simile per altre persone giuridiche. Ad esempio, per una persona giuridica denominata **RW**, se si modifica unicamente il valore del segmento di entità legale, il numero formattato sarà RW-EXPENSE-0039. È inoltre possibile modificare il formato dell'intera sequenza numerica per altre persone giuridiche. Ad esempio, è possibile omettere il segmento ambito della persona giuridica per creare un numero formattato quale Exp-0001.

### <a name="sales-order-numbers"></a>Numeri di ordini cliente

Nell'esempio seguente i numeri degli ordini cliente vengono impostati per l'ID società **CEU**. **Area:** vendite **Riferimento:** ordine cliente **Ambito:** società **Società:** CEU
| Segmenti  | Tipo di segmento | Valore    |
|-----------|--------------|----------|
| Segmento 1 | Costante     | OC:      |
| Segmento 2 | Alfanumerico | \#\#\#\# |

**Esempio di numero formattato**: SO-0029 Anche se un segmento ambito non viene incluso nel formato, la numerazione ricomincia per ogni ID società. Se si utilizza lo stesso formato per tutti gli ID società, gli stessi numeri vengono utilizzati in ogni società. Ad esempio, il numero dell'ordine cliente SO-0029 viene utilizzato in ogni società. È inoltre possibile modificare il formato dell'intera sequenza numerica per altri ID società.

### <a name="purchase-requisition-numbers"></a>Numeri delle richieste di acquisto

Nell'esempio seguente i numeri delle richieste di acquisto si riferiscono all'intera organizzazione. **Area:** richiesta **Riferimento:** richiesta di acquisto **Ambito:** condiviso
| Segmenti  | Tipo di segmento | Valore    |
|-----------|--------------|----------|
| Segmento 1 | Costante     | Rich      |
| Segmento 2 | Alfanumerico | \#\#\#\# |

**Esempio di numero formattato**: Req0052 Poiché l'ambito è **condiviso**, il formato della sequenza numerica viene utilizzato nell'intera organizzazione. Non è possibile impostare formati di sequenze numeriche diversi per parti diverse dell'organizzazione. Considerazioni relative alle prestazioni per le sequenze numeriche
-----------------------------------------------

Considerare le informazioni seguenti in relazione al modo in cui la configurazione delle sequenze numeriche può influire sulle prestazioni del sistema prima di impostare sequenze numeriche.
### <a name="continuous-and-non-continuous-number-sequences"></a>Sequenze numeriche continue e non continue

Le sequenze numeriche possono essere continue o non continue. Una sequenza numerica continua non salta alcun numero, ma i numeri possono anche non essere utilizzati in sequenza. I numeri di una sequenza numerica non continua vengono utilizzati in sequenza, ma la sequenza può saltare dei numeri. Ad esempio, se un utente annulla una transazione, un numero viene generato, ma non utilizzato. In una sequenza numerica continua, quel numero verrà riciclato in seguito. In una sequenza numerica non continua, il numero non verrà invece utilizzato. Le sequenze numeriche continue vengono in genere utilizzate per documenti esterni quali ordini fornitore, ordini cliente e fatture. Le sequenze numeriche continue possono tuttavia influire negativamente sui tempi di risposta del sistema perché quest'ultimo deve richiedere un numero al database ogni volta che viene creato un nuovo record o un nuovo documento. Se si utilizza una sequenza numerica non continua, è possibile abilitare **Preallocazione** nella scheda **Prestazioni** della pagina **Sequenze numero**. Se si specifica una quantità di numeri da preallocare, questi numeri vengono selezionati e archiviati in memoria. Nuovi numeri vengono richiesti dal database solo dopo che la quantità preallocata è stata utilizzata. A meno che un particolare requisito normativo non richieda l'utilizzo delle sequenze numeriche continue, per garantire prestazioni migliori è consigliabile utilizzare sequenze numeriche non continue.

### <a name="automatic-cleanup-of-number-sequences"></a>Pulitura automatica di sequenze numeriche

In caso di un'interruzione dell'alimentazione, di un errore dell'applicazione o di altri problemi imprevisti, i numeri per le sequenze numeriche continue non possono essere riciclati automaticamente. È possibile eseguire il processo di pulitura manualmente o automaticamente per recuperare i numeri persi. Si consideri attentamente l'utilizzo del server quando si pianifica il processo di pulitura. È consigliabile eseguire la pulitura come processo batch nelle ore di attività meno intense.






