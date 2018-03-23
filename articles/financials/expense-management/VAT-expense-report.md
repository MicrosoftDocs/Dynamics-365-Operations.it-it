---
title: Recupero IVA in Gestione spese
description: In questo argomento viene descritto come ricevere rimborsi su transazioni di imposta sul valore aggiunto (IVA) idonee.
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: d1c9357f8f51e1a87aebeb8f802dbe3b5fdd5aa0
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2018

---

# <a name="vat-recovery-in-expense-management"></a>Recupero IVA in Gestione spese

Per ricevere rimborsi su transazioni di imposta sul valore aggiunto (IVA) idonee, una società o un'organizzazione deve identificare, raccogliere, verificare e inviare informazioni accurate. Questo processo comprende più attività e, a seconda delle dimensioni della società, può includere diversi dipendenti o ruoli.

Per recuperare l'IVA utilizzando Gestione spese, è necessario completare i seguenti prerequisiti:

- Creare codici imposta per i paesi allocati alle categorie di spesa.
- Creare una fascia IVA per ciascun codice imposta.
- Creare un codice IVA articoli per ciascuna fascia IVA.

Una volta completati i prerequisiti, i dipendenti seguono questi passaggi per richiedere i rimborsi per transazioni IVA.

1. In una nota spese immettere le informazioni fiscali sulle transazioni con carta di credito per identificare i rimborsi IVA idonei.
2. Accertarsi che tutte le informazioni fiscali siano complete, quindi registrare la nota spese.
3. Elaborare le spese applicabili per il recupero IVA internazionale.
4. Inviare i dati del recupero IVA al fornitore di terze parti per presentare le dichiarazioni per il recupero internazionale.
5. Elaborare le spese per il recupero IVA nazionale.

Nelle sezioni seguenti sono riportati alcuni esempi che illustrano come i dipendenti di Contoso completano ciascun passaggio.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>In una nota spese immettere le informazioni fiscali sulle transazioni con carta di credito per identificare i rimborsi IVA idonei.

Nancy, una rappresentante di Contoso residente negli Stati Uniti, è appena tornata da un viaggio di lavoro nel Regno Unito. Durante il viaggio ha sostenuto le spese per i pasti con la carta di credito personale. Nancy deve ora creare una nota spese per riconciliare le spese sostenute.

Quando Nancy immette le informazioni sulla nota spese, seleziona **Regno Unito** nel campo **Paese** nella pagina **Modifica nota spese**. L'elenco delle fasce IVA viene quindi filtrato in modo da riportare solo i gruppi applicabili al Regno Unito. Nancy seleziona la fascia IVA **Regno Unito 001**, quindi sceglie la fascia IVA articoli **Vitto**. A questo punto, Nancy aggiunge una nuova transazione per l'alloggio. Per il Regno Unito esiste una sola fascia IVA e una sola fascia IVA articoli per l'alloggio, pertanto tali informazioni vengono inserite automaticamente nella nota spese di Nancy.

Per i criteri di Contoso, per tutte le spese è necessario disporre di una ricevuta corrispondente. Pertanto, quando Nancy salva la nota spese, riceve un messaggio indicante che è necessario allegare una ricevuta per ciascuna transazione elencata nella nota spese. Nancy verifica di aver allegato un'immagine digitale di ciascuna ricevuta di transazione alla nota spese, quindi invia la nota per l'approvazione. Invia quindi le ricevute cartacee al team di elaborazione di back-office. Questo team invierà i dati del recupero IVA al fornitore di terze parti che presenta le dichiarazioni per il recupero IVA internazionale per Contoso.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Accertarsi che tutte le informazioni fiscali siano complete, quindi registrare la nota spese.

April, coordinatrice contabilità fornitori per Contoso, deve immettere le informazioni fiscali mancanti in una nota spese affinché possa essere registrata. Apre la pagina **Dettagli nota spese** e vede la nota spese approvata di Nancy. Apre quindi la nota spese per visualizzare i dettagli delle transazioni e si accorge che Nancy non ha immesso una fascia IVA articoli per una delle transazioni. Poiché non è stata fornita questa informazione, April non può registrare la nota spese. Pertanto, April consulta la pagina **Configurazioni imposte** in Gestione spese e individua la fascia IVA articoli appropriata per il paese e il tipo di transazione. A questo punto April può registrare la nota spese nella contabilità generale.

Quando April registra la nota spese, viene creato un elemento di lavoro con IVA recuperabile. Tale elemento di lavoro viene assegnato a un membro del team di elaborazione di back-office. April riceve un messaggio che conferma che la registrazione è stata eseguita correttamente. In questo messaggio è elencato anche il numero di transazioni IVA individuate per il recupero.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Elaborare le spese idonee per il recupero IVA internazionale

Arnie, membro del team di elaborazione di back-office di Contoso, è responsabile di confermare che tutte le informazioni richieste per il recupero IVA siano incluse nelle note spese. Arnie apre la pagina **Recupero imposte su spese** e seleziona la nota spese inviata da Nancy. Arnie verifica che siano state allegate tutte le ricevute richieste e che siano stati immessi il codice fascia IVA e il codice IVA articoli corretti.

Quando Arnie riceve le ricevute cartacee da Nancy, le verifica confrontandole con quelle digitali, quindi modifica lo stato della nota spese in **Pronte per il recupero**.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Inviare i dati del recupero IVA al fornitore di terze parti per presentare le dichiarazioni per il recupero internazionale

Quando è pronto a inviare i dati della nota spese al fornitore di terze parti che presenterà le dichiarazioni per il recupero IVA, Arnie apre la pagina **Recupero imposte su spese**. Arnie filtra la pagina in modo da visualizzare solo le note spese contrassegnate come **Pronte per il recupero**. A questo punto, Arnie seleziona **File** &gt; **Esporta in Excel**. Le informazioni sull'IVA presenti nelle note spese vengono esportate in un foglio di lavoro di Microsoft Excel. Arnie invia tale foglio di lavoro al fornitore di terze parti e include un messaggio indicante che le ricevute cartacee sono state inviate tramite corriere.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Elaborare le spese per il recupero IVA nazionale

Arnie deve verificare che le transazioni delle note spese siano idonee per il recupero IVA e che le ricevute digitali siano allegate alle note. Per iniziare a elaborare le spese idonee per il recupero nazionale, Arnie apre la pagina **Recupero imposte su spese** e seleziona la nota spese da verificare. Verifica che le ricevute siano intestate alla società anziché al dipendente. Per il recupero IVA, le ricevute devono essere intestate alla società. Verifica quindi che siano stati applicati il codice fascia IVA e il codice IVA articoli corretti.

Quando Arnie riceve le ricevute cartacee, modifica lo stato della nota spese in **Pronte per il recupero**. A questo punto, Arnie può presentare la dichiarazione all'autorità fiscale competente. In questo caso, l'autorità fiscale competente negli Stati Uniti è l'IRS (Internal Revenue Service).

