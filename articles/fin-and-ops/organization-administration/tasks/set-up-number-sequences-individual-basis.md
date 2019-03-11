---
title: Impostare sequenze numeriche singole
description: Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono.
author: sericks007
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6734d66a06f8a8dc90a48bd68b7b4e22177b4672
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "362213"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Impostare sequenze numeriche singole

[!include [task guide banner](../../includes/task-guide-banner.md)]

Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono. Un record transazioni o dati master che richiede un identificatore viene definito riferimento. Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento. È possibile impostare tutte le sequenze numeriche richieste contemporaneamente utilizzando la procedura guidata Imposta sequenze numeriche oppure creare o modificare singole sequenze numeriche utilizzando la pagina Sequenze numeriche.

1. Andare a Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche.
2. Fare clic su Sequenza numerica.
3. Nel campo Codice sequenza numerica selezionare un valore.
4. Digitare un valore nel campo Nome.
5. Espandere la sezione Parametri di ambito.
    * Nella Scheda dettaglio Parametri di ambito selezionare un ambito per la sequenza numerica e selezionare i valori dell'ambito.     L'ambito definisce quali organizzazioni utilizzano la sequenza numerica. Inoltre, le sequenze numeriche con un ambito diverso da Condiviso possono avere segmenti corrispondenti al loro ambito. Una sequenza numerica con un ambito di Persona giuridica, ad esempio, può avere un segmento persona giuridica. Per ulteriori informazioni sugli ambiti, vedere l'argomento della Guida "Panoramica delle sequenze numeriche".  
6. Espandere la sezione Segmenti.
    * Nella Scheda dettaglio Segmenti definire il formato della sequenza numerica aggiungendo, eliminando e riorganizzando i segmenti.  
    * Le sequenze numeriche di tutti gli ambiti possono contenere segmenti costanti e segmenti alfanumerici. I segmenti costanti contengono un insieme di caratteri alfanumerici che non cambiano. Utilizzare questo tipo di segmento per aggiungere un trattino o altri separatori tra i segmenti della sequenza numerica. I segmenti alfanumerici contengono una combinazione di simboli numerici (#) e commerciali (&). Questi caratteri rappresentano lettere e numeri che aumentano ogni volta che viene utilizzato un numero della sequenza. Utilizzare un simbolo di numero (#) per rappresentare i numeri che aumentano e la e commerciale (&) per rappresentare le lettere che aumentano. Il formato #####_2014, ad esempio, consente di ottenere la sequenza 00001_2014, 00002_2014 e così via.     Deve essere presente almeno un segmento alfanumerico. I segmenti ambito, ad esempio società o persona giuridica, non sono obbligatori. Tuttavia, se non si inseriscono segmenti ambito nel formato, i numeri per il riferimento selezionato vengono comunque generati per ambito.  
7. Espandere la sezione Riferimenti.
    * Nella Scheda dettaglio Riferimenti selezionare il tipo di documento o il record cui assegnare la sequenza numerica.     Questo passaggio è facoltativo per sequenze definite per tipi di utilizzo speciali dell'applicazione. In questi scenari, un nuovo numero viene generato utilizzando il valore di un codice o ID di una sequenza numerica, senza usare un riferimento. Un esempio di un tipo di utilizzo speciale dell'applicazione è una serie di giustificativi utilizzata per nomi di giornali di registrazione specifici. Tuttavia, non consigliamo di adottare questi tipi di utilizzo.  
8. Espandere la sezione Generale.
    * Nella Scheda dettaglio Generale specificare se la sequenza numerica è manuale e continua o non continua. Immettere, inoltre, il numero minimo e massimo che è possibile utilizzare nella sequenza numerica.     Si consiglia di non modificare una sequenza numerica non continua con una sequenza numerica continua. La sequenza numerica non continua verrà soddisfatta. La modifica può causare anche le violazioni della chiave duplicata nel database. Inoltre, le sequenze numeriche continue hanno un maggiore effetto sulle prestazioni.   
9. Fare clic su Salva.

