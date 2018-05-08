---
title: Impostare avvisi antifrode
description: "In questo argomento viene illustrato come impostare le regole per avvisare i rappresentanti dell'assistenza clienti di informazioni potenzialmente fraudolente quando gli ordini vengono elaborati. È possibile definire codici specifici da utilizzare per mettere automaticamente o manualmente gli ordini sospetti in attesa."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-fraud-alerts"></a>Impostare avvisi antifrode

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come impostare criteri e regole per sospendere ordini cliente potenzialmente fraudolenti da verificare ulteriormente. La funzionalità antifrode viene utilizzata per determinare la validità delle informazioni in un ordine cliente. Se le informazioni nell'ordine cliente vengono considerate sospette in base a criteri e regole antifrode di un'organizzazione, l'ordine può essere sospeso per un'ulteriore verifica da parte di un amministratore.

> [!NOTE]
> Questa funzionalità può essere utilizzata solo con l'elaborazione di ordini cliente mediante il canale servizio clienti di Retail. 

Quando il canale servizio clienti viene definito, l'opzione **Attiva completamento ordine** deve essere impostata su **Sì**. Quando il completamento dell'ordine è attivato, gli utenti possono visualizzare il riepilogo dell'ordine e fare clic su **Invia** per finalizzare l'ordine. Agli utenti vengono anche fornite opzioni per sospendere manualmente l'ordine cliente da sottoporre alla revisione antifrode. Gli ordini cliente immessi da un utente del servizio clienti vengono elaborati mediante regole e criteri antifrode durante il processo di invio.

Sono disponibili due tipi di criteri antifrode a cui il sistema farà riferimento per verificare se l'ordine deve essere sottoposto a una verifica antifrode:

-   Le **regole statiche** utilizzano un valore specifico, come un numero di telefono che è stato inserito nella blacklist o un indirizzo di posta elettronica già utilizzato per transazioni fraudolente in passato. Nella pagina **Dati fraudolenti statici**, le informazioni fraudolente possono essere aggiunte manualmente o tramite l'importazione dei dati, con punteggi associati alle informazioni fraudolente. Se la verifica antifrode è attivata, ogni ordine cliente immesso verrà confrontato ai dati statici. Se i dati sono presenti nell'indirizzo di fatturazione o di consegna del cliente, o se i dati sono presenti nell'indirizzo di consegna sulla riga di vendita, i punteggi di tutte le corrispondenze univoche verranno sommati.  
-   Le **regole dinamiche** sono composte da variabili e condizioni definite per tali variabili. Con le regole dinamiche, è possibile verificare altri criteri non definiti nelle regole statiche. Istruzioni "E/O" più complesse possono essere utilizzate per considerare molteplici condizioni e determinare se è presente una corrispondenza positiva in base ai criteri delle regole e all'ordine cliente inviato. Ad esempio, se un utente desidera sospendere e sottoporre a verifica antifrode tutti gli ordini per i clienti associati a uno specifico valore di gruppo di clienti e che hanno ordinato uno specifico prodotto, le condizioni per convalidare il cliente e i prodotti verrebbero definite nella pagina **Regole** con una condizione "E". L'ordine verrebbe sospeso solo se entrambe le condizioni fossero vere e se il valore assegnato alla regola stabilirebbe che il punteggio frodi totale dell'ordine è superiore al punteggio frodi minimo come definito nei parametri del servizio clienti.

Un utente del servizio clienti può anche inserire manualmente un ordine nella coda delle sospensioni per frode. Se l'utente che immette l'ordine ritiene che il cliente che piazza l'ordine può essere sospetto e desidera che qualcun altro verifichi ulteriormente la validità dell'ordine prima che questo venga elaborato, l'utente che immette l'ordine può scegliere l'opzione **Sospensione manuale per frode** nel menu a discesa **Sospensioni** della pagina **Riepilogo ordine cliente** (visualizzata dopo la chiamata della funzione dell'ordine **Completa**). All'utente verrà richiesto di immettere una nota per spiegare perché ritiene che l'ordine sia fraudolento in modo che il revisore abbia più contesto.

Tutti gli ordini sospesi a seguito della sospensione manuale per frode o del calcolo sistematico dei punteggi frode saranno visualizzati nella pagina **Sospensioni ordine**, dove l'ordine può essere esaminato e quindi annullato o rilasciato per l'elaborazione.

> [!NOTE]
> L'utilizzo di più regole o di regole eccessivamente complesse altererà negativamente le prestazioni del sistema quando gli ordini cliente vengono inviati. La funzionalità di avviso antifrode non è stata ottimizzata per gestire un grande volume di dati fraudolenti statici e molte regole attive. È importante ricordare che ogni regola viene valutata durante la funzione di inoltro della registrazione ordine cliente del servizio clienti. Le regole vengono valutate rispetto all'intestazione dell'ordine cliente e a tutte le righe dell'ordine. Più regole sono presenti e più complesse sono le istruzioni delle regole, più lungo sarà il processo di valutazione. Se l'ordine presenta molte voci e il numero di regole attive e di immissioni di dati statici è molto elevato, questo processo sistematico di verifica e convalida di tutti i dati e di calcolo di un punteggio frodi può alterare considerevolmente le prestazioni.  Le organizzazioni che utilizzano questa funzionalità devono sempre verificare e confermare che il tempo di elaborazione dell'invio dell'ordine è accettabile prima di applicare eventuali modifiche alle regole o ai criteri antifrode statici nell'ambiente di produzione.

