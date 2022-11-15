---
title: Suddivisione dei clienti nelle programmazione di fatturazione
description: Questo articolo descrive come suddividere un cliente quando viene utilizzata la fatturazione dell'abbonamento.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746315"
---
# <a name="customer-split-on-billing-schedules"></a>Suddivisione dei clienti nelle programmazione di fatturazione

In base a un programma di fatturazione, il *conto fattura* è il cliente che riceve la fattura dell'ordine cliente in modo che possa pagare la fattura. In alcuni scenari, più di un cliente può pagare una fattura. La funzionalità **Suddivisione clienti** consente di aggiungere più clienti che possono essere fatturati per la stessa pianificazione di fatturazione. Per abilitare questa funzionalità, vai a **Fatturazione abbonamento \> Fatturazione contratto ricorrente \> Imposta \> Parametri di fatturazione contratto ricorrente**, e imposta l'opzione **Suddivisione clienti** su **Sì**.

## <a name="customer-split-on-the-billing-schedule-header"></a>Suddivisione dei clienti nell'intestazione della programmazione di fatturazione

Dopo aver creato una programmazione di fatturazione, è possibile aggiungere altri clienti all'intestazione della programmazione di fatturazione.

Per aggiungere un cliente, segui questi passaggi.

1. Nella scheda **Programmazione fatturazione** seleziona **Suddivisione clienti**. I campi **Conto cliente** e **Nome conto cliente** i campi in alto specificano il cliente a cui è assegnato **Cliente con programmazione fatturazione**.

    > [!NOTE]
    > Il conto cliente che aggiungi non può essere lo stesso dell'account di fatturazione.

2. Nella scheda **Righe suddivisione clienti** seleziona **Aggiungi riga**.
3. Seleziona un cliente, quindi inserisci la percentuale di ciascuna fattura per quel cliente.
4. Per impostazione predefinita, le date di inizio e di fine della programmazione di fatturazione vengono utilizzate come date di inizio e fine. Immetti date di inizio e fine diverse se il nuovo cliente pagherà la percentuale specificata solo per una parte della programmazione di fatturazione. Ad esempio, se la programmazione di fatturazione ha una data di inizio 1 gennaio e una data di fine 31 dicembre e al nuovo cliente viene fatturato il 40% per i primi nove mesi, specifica 1 gennaio come data di inizio e 30 settembre come data di fine ed immetti **40,00** come percentuale.

Puoi aggiungere più di un cliente alle righe di suddivisione dei clienti. In questo caso, la percentuale totale immessa non deve superare il 100 percento. Immetti un riferimento cliente e una richiesta cliente come campi informativi che verranno visualizzati nella riga dell'ordine cliente durante il processo **Genera fattura**.

I dettagli della riga mostreranno le informazioni di contatto, l'indirizzo di consegna, l'indirizzo di fatturazione e i dettagli di pagamento dei clienti aggiunti. Queste informazioni verranno visualizzate anche nell'ordine cliente per i clienti.

Quando aggiungi le informazioni sulla suddivisione dei clienti all'intestazione della programmazione di fatturazione, se sono presenti righe della programmazione di fatturazione non fatturate nella programmazione di fatturazione, riceverai il seguente messaggio che ti chiede di annullare le modifiche: "Annullare la modifica dall'intestazione alle righe? Le modifiche aggiorneranno solo le righe di programmazione fatturazione non fatturate." Seleziona **Sì** per aggiornare le informazioni sulla suddivisione dei clienti nella riga della programmazione di fatturazione. Le modifiche non verranno aggiornate se la riga della programmazione di fatturazione è già stata fatturata.

Se viene creata una programmazione di fatturazione utilizzando l'opzione **Copia programmazione**, le informazioni predefinite verranno inserite nelle righe di intestazione della suddivisione del cliente. Non può essere la stessa del conto cliente.

Quando il processo **Genera fattura** è completato, verranno creati più ordini cliente. (Se si utilizza la registrazione automatica, verranno create anche più fatture di vendita.) Questi ordini cliente e fatture di vendita possono essere visualizzati nella scheda **Fattura** della Scheda dettaglio **Dettagli riga** della pagina **Visualizza i dettagli di fatturazione**. **Multiplo** viene visualizzato nella riga dei dettagli di fatturazione per indicare che sono stati creati più ordini cliente e fatture di vendita.

## <a name="customer-split-on-billing-schedule-lines"></a>Suddivisione dei clienti nelle righe della programmazione di fatturazione

La suddivisione dei clienti può essere aggiunta a singole righe della programmazione di fatturazione se desideri suddividere solo righe della programmazione di fatturazione specifiche. Seleziona la casella di controllo **Suddivisione clienti** sulla riga, quindi seleziona **Suddivisione clienti** nel menu della riga della programmazione di fatturazione per aggiornare o inserire le informazioni sulla suddivisione dei clienti.

Le informazioni di controllo vengono aggiornate se la programmazione di fatturazione è già stata fatturata, ma la percentuale è stata modificata nella riga della programmazione di fatturazione. Tutte le righe fatturate dopo tale modifica utilizzeranno la nuova percentuale.

> [!NOTE]
> - L'opzione di suddivisione dei clienti non possono essere utilizzate con i prodotti stoccati.
> - Se la casella di controllo **Ricavi non fatturati** è selezionata, la casella di controllo **Suddivisione clienti** non può essere selezionata.
> - Se utilizzi l'opzione **Solo suddivisione ricavi**, la riga padre ha l'opzione **Suddivisione clienti**, ma la riga figlio no.
