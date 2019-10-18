---
title: Dimensioni finanziarie e registrazione
description: Quando si pianifica e si imposta il piano dei conti, è necessario considerare il modo in cui i vari componenti interagiscono durante la registrazione di un documento o un giornale di registrazione. Questi componenti includono strutture dei conti, regole avanzate nonché dimensioni fisse e di bilanciamento. In questo argomento vengono descritti i componenti e il modo in cui interagiscono.
author: aprilolson
manager: AnnBe
ms.date: 08/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 76fd305ce0f0f073648339d1de969981693f1da5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186810"
---
# <a name="financial-dimensions-and-posting"></a>Dimensioni finanziarie e registrazione 

[!include [banner](../includes/banner.md)]

Quando si pianifica e si imposta il piano dei conti, è necessario considerare il modo in cui i vari componenti interagiscono durante la registrazione di un documento o un giornale di registrazione. Questi componenti includono strutture dei conti, regole avanzate nonché dimensioni fisse e di bilanciamento. In questo argomento vengono descritti i componenti e il modo in cui interagiscono.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Componenti di dimensioni finanziarie e piano dei conti

Un sistema basato su regole avanzato è utilizzato per definire combinazioni valide di conti principali e valori di dimensioni finanziarie. Questa sezione include una breve panoramica della funzionalità di ciascun componente e informazioni su dove trovare il componente.

### <a name="account-structures"></a>Strutture dei conti

Una struttura dei conti è necessaria quando si imposta la contabilità generale. È necessario definire e attivare almeno una struttura dei conti e assegnarla alla contabilità generale. La struttura dei conti deve includere il conto principale. È possibile definire l'ordine dei segmenti più appropriato per l'azienda. Dopo la definizione del conto principale, il sistema può determinare la struttura dei conti utilizzata. Mettendo il conto principale prima o vicino alla parte iniziale di una struttura, è possibile limitare i valori nonché consentire al sistema di applicare l'ultimo valore valido noto come valore predefinito. È possibile avere fino a 10 dimensioni finanziarie aggiuntive nella struttura dei conti. La struttura dei conti definisce quali valori di dimensioni sono validi in combinazione con altri valori e se i valori di dimensioni devono essere immessi.

### <a name="advanced-rules"></a>Regole avanzate

Le regole avanzate sono un componente facoltativo nell'impostazione del piano dei conti. È possibile aggiungere un numero illimitato di regole avanzate a una struttura dei conti. Le regole avanzate sono spesso utilizzate per gestire scenari in cui è necessario tenere traccia di dimensioni finanziarie supplementari quando vengono soddisfatti specifici criteri. Ad esempio, se si utilizza un conto spese di viaggio, è possibile che si intenda tenere traccia di informazioni aggiuntive come l'evento all'origine del viaggio. Se sono presenti più regole avanzate, vengono applicate in ordine alfabetico, in base ai nomi delle regole. I segmenti aggiunti da una regola sono applicabili solo dopo i segmenti della struttura dei conti.

### <a name="balancing-dimension"></a>Dimensione di bilanciamento

È possibile eventualmente definire una dimensione finanziaria di bilanciamento. Nella pagina **Contabilità generale**, è possibile definire la dimensione finanziaria che deve essere bilanciata. Quindi, ogni volta che delle transazioni vengono registrate in tale dimensione finanziaria, il sistema crea e registra automaticamente le voci per bilanciare la dimensione finanziaria.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Dimensioni finanziarie predefinite/fisse nel conto principale

Le dimensioni predefinite provengono da varie posizioni, come record di dati master (ad esempio, record cliente o fornitore), intestazioni di documento e conto principale. In questo argomento vengono descritte le dimensioni predefinite nel conto principale in base alla persona giuridica. È possibile definire se un conto principale ha un valore **Non fissa** o **Fisso** per ogni dimensione finanziaria utilizzata in tutte le strutture dei conti per la contabilità generale. Se una dimensione finanziaria è **Non fissa**, viene utilizzato un valore predefinito, ma tale valore può comunque essere sovrascritto. Questo comportamento si applica a tutti i valori predefiniti nel sistema, anche a quelli che provengono dai record di dati master. Se il valore di una dimensione finanziaria è **Fisso**, tale valore viene sempre applicato, indipendentemente dal fatto che sia un valore predefinito o immesso dall'utente.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>Ordine in cui le dimensioni predefinite sono applicate durante la registrazione

Gli utenti si pongono spesso domande in merito all'ordine in cui i vari componenti vengono eseguiti. È molto importante comprendere l'ordine di applicazione delle dimensioni predefinite, poiché questo comportamento determina l'approccio da seguire per l'impostazione.

> [!NOTE]
> Queste informazioni sono valide unicamente per l'applicazione delle dimensioni predefinite nell'applicazione. Se si importano dati utilizzando Microsoft Excel o il framework di gestione dei dati, il comportamento differisce.

### <a name="example-1"></a>Esempio 1

**Struttura dei conti**

| Conto principale            | Business Unit           | Reparto              | Centro di costo             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Tutti i valori sono consentiti. | Tutti i valori sono consentiti. | Tutti i valori sono consentiti. | Tutti i valori sono consentiti. |

**Conto principale**

| Conto principale | Nome          | Persona giuridica | Reparto                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Vendite prodotto | USMF         | Fisso – 022 Reparto Vendite e marketing |

L'illustrazione seguente mostra la dimensione predefinita fissa impostata nel conto principale 401100.

[![Dimensioni finanziarie predefinite](./media/default-dimensions.png)](./media/default-dimensions.png)

In questo esempio elementare, immetteremo un giornale di registrazione generale in cui la dimensione Reparto è impostata per utilizzare il valore predefinito **023** (Operazioni). Inoltre, immetteremo e registreremo un conto CoGe. L'illustrazione seguente mostra la dimensione finanziaria predefinita nell'intestazione di contabilità generale.

[![Giornali di registrazione generali](./media/general-journal.png)](./media/general-journal.png)

La dimensione predefinita nell'intestazione del giornale di registrazione implica l'applicazione, per impostazione predefinita, del dipartimento 23 alla riga del conto vendite. L'illustrazione seguente mostra la riga del giornale di registrazione generale con applicato il valore di dimensione predefinito **023** dell'intestazione.

[![Giustificativo giornale di registrazione](./media/journal-voucher.png)](./media/journal-voucher.png)

Tuttavia, alla registrazione delle riga, viene applicata la dimensione fissa e la riga viene registrata nel reparto 022. L'illustrazione seguente mostra il giustificativo registrato, dove la dimensione fissa è applicata per il conto vendite.

[![Transazioni giustificativo](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>Esempio 2

In questo esempio viene utilizzata la stessa impostazione del primo esempio. Aggiungeremo tuttavia un secondo componente e utilizzeremo la dimensione Reparto come dimensione di bilanciamento. Nell'illustrazione seguente, **Reparto** è impostato come dimensione finanziaria di bilanciamento per la contabilità generale USMF.

[![Contabilità generale](./media/ledger.png)](./media/ledger.png)

Quando si utilizza la stessa impostazione dell'intestazione del giornale di registrazione e si registra la stessa transazione, la dimensione fissa viene applicata per prima. Viene quindi applicata la logica di bilanciamento per garantire che ogni reparto ha una voce bilanciata. L'illustrazione seguente mostra transazioni giustificativo che includono la voce di bilanciamento dopo l'applicazione della dimensione fissa.

[![Transazioni giustificativo](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>Esempio 3

In questo esempio, aggiungeremo una regola avanzata. La regola avanzata specifica che se il conto vendite 401100 e il reparto 022 (Vendite e marketing) sono utilizzati, il sistema deve tenere traccia di un segmento aggiuntivo denominato Cliente.

Questo esempio è importante per via dell'ordine. La struttura dei conti viene determinata dopo l'immissione del conto principale. Se si fa riferimento all'impostazione della struttura dei conti, il sistema può determinare che il conto principale, la business unit, il reparto e il centro di costo sono rilevanti. A questo punto, la regola avanzata non è stata attivata, poiché le dimensioni fisse vengono applicate solo dopo l'applicazione delle dimensioni predefinite per il giustificativo del giornale di registrazione durante la registrazione. Nell'illustrazione seguente, il segmento Cliente non è presente poiché i criteri per la regola avanzata non sono stati soddisfatti.

[![Conto CoGe](./media/drop-down.png)](./media/drop-down.png)

La registrazione non riuscirà poiché la dimensione fissa è stata applicata alla fine del processo. La convalida della dimensione determina che il segmento Cliente è necessario se il conto principale è 401100 e il reparto è 022. La registrazione non può essere eseguita a causa di un errore di convalida. L'illustrazione seguente mostra il messaggio visualizzato dopo che la convalida della dimensione determina che il segmento Cliente è necessario.

[![Dettagli messaggio](./media/message.png)](./media/message.png)

In questo esempio, è necessario sovrascrivere il valore predefinito in modo da attivare la regola avanzata e immettere il segmento Cliente. Tuttavia, questa soluzione non è sempre possibile e alcuni utenti non sono nemmeno a conoscenza delle regole di registrazione. Di conseguenza, è importante comprendere l'ordine in cui le dimensioni predefinite sono applicate quando si imposta il piano dei conti.

Per ottenere lo scopo desiderato in questo esempio, è possibile modificare la configurazione in vari modi. Ad esempio, è possibile creare una nuova struttura dei conti per i conti vendite e includere il segmento Cliente nella struttura. È inoltre possibile aggiungere ulteriori righe in una struttura dei conti esistente e specificare il conto principale e valori di reparto validi. Nella struttura cliente aggiuntiva, potrebbe risultare utile avere una struttura dei conti distinta per i conti vendite in cui il segmento Cliente è presente.

## <a name="additional-resources"></a>Risorse aggiuntive 

Alcune delle seguenti risorse fanno riferimento a una versione precedente del nostro software. Tuttavia, la maggior parte delle informazioni sull'applicazione delle dimensioni predefinite e molti dei concetti sono uguali nella versione precedente e i riferimenti sono ancora validi.

[Giornali di registrazione bilanciati per la contabilizzazione interunità](example-balanced-journals-interunit-accounting.md)

[Definire il piano dei conti](plan-chart-of-accounts.md) 

[Blog Pianificazione del piano dei conti in AX 2012](https://blogs.msdn.microsoft.com/axsa/2014/06/12/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7/) – Collegamento al primo di una serie di sette articoli.

[Impostazione predefinita delle dimensioni nelle distribuzioni contabili](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2013/12/16/dimension-defaulting-in-accounting-distributions-part-1-introduction/)

[Impostazione predefinita delle dimensioni nel framework di dimensioni](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2014/09/)
