---
title: Date della fattura fornitore
description: Questo argomento descrive le date che compaiono sulle fatture fornitore. Spiega inoltre come impostare il sistema in modo che rettifichi automaticamente la data di registrazione.
author: sunfzam
ms.date: 08/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: a066f828b47f297b8ad520b9eb0f4f311d49b111
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647896"
---
# <a name="vendor-invoice-dates"></a>Date della fattura fornitore

[!include [banner](../includes/banner.md)]

Questo argomento descrive le date che compaiono sulle fatture fornitore. Spiega inoltre come impostare il sistema in modo che rettifichi automaticamente la data di registrazione.

Nella pagina **Fattura fornitore dettagliata in attesa**, l'intestazione della fattura mostra quattro date: la data di ricezione della fattura, la data della fattura, la data di registrazione e la data di scadenza. Quando viene creata una fattura fornitore, per impostazione predefinita vengono immesse le seguenti date:

- **Data di ricezione fattura** – Questo campo è impostato sulla data di sistema corrente.
- **Data di registrazione** – Questo campo è impostato sulla data di sistema corrente. 
- **Data di scadenza** – La data in questo campo viene calcolata in base alla data di registrazione e ai termini di pagamento.
- **Data fattura** – Per impostazione predefinita, questo campo è vuoto. Tuttavia, puoi immettere un valore in base alle esigenze. In tal caso, la data nel campo **Data di scadenza** viene ricalcolato in base alla data della fattura e ai termini di pagamento.

A volte, una fattura fornitore potrebbe rimanere in sospeso per molto tempo dopo la chiusura del periodo. Quando è pronta per la registrazione, viene ancora utilizzata la vecchia data di registrazione del periodo di registrazione passato. Tuttavia, quel periodo è ora chiuso. Pertanto, un addetto alla contabilità fornitori deve modificare manualmente tutte le date di registrazione nel nuovo periodo di registrazione per tutte le fatture in sospeso create in precedenza.

La funzionalità descritta in questo argomento consente di impostare il sistema in modo che rettifichi automaticamente la data di registrazione in base ai requisiti aziendali.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Parametro per la rettifica automatica della data di registrazione della fattura fornitore

Segui questi passaggi per consentire al sistema di rettificare automaticamente la data di registrazione per le fatture fornitore.

1.  Passa a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
2.  Nella scheda **Contabilità generale e IVA** nel campo **Rettifica automaticamente data di registrazione** seleziona uno dei seguenti valori:

    - **Nessuna modifica** – Il sistema non modifica automaticamente la data di registrazione durante la registrazione. Questo valore è selezionato per impostazione predefinita.
    - **Modifica sempre la data di registrazione nella data di sistema** – Il sistema modifica automaticamente la data di registrazione con la data di sistema durante la registrazione.
    - **Cambia data di registrazione nella data di sistema quando il periodo della data di registrazione è chiuso o in attesa** – Il sistema modifica la data di registrazione con la data di sistema durante la registrazione, ma solo se il periodo corrispondente della data di registrazione ha lo stato **Chiuso** o **In attesa**.
    - **Cambia data di registrazione nel primo giorno del nuovo periodo quando il periodo della data di registrazione è chiuso o in attesa** – Il sistema modifica la data di registrazione con il primo giorno del nuovo periodo di apertura, ma solo se il periodo corrispondente della data di registrazione ha lo stato **Chiuso** o **In attesa**.

## <a name="impact-of-posting-date-changes"></a>Impatto delle modifiche alla data di registrazione

Quando viene modificata la data di registrazione di una fattura fornitore in sospeso, la modifica ha i seguenti effetti:

- **Data di scadenza**

    - Se il campo **Data fattura** è vuoto, la data di scadenza viene ricalcolata in base alla nuova data di registrazione e ai termini di pagamento.
    - Se il campo **Data fattura** è stato precedentemente impostato, la modifica della data di registrazione non influisce sulla data di scadenza.

- **Data sconto di cassa**

    - Se il campo **Data fattura** è vuoto, la nuova data di registrazione viene utilizzata per calcolare lo sconto di cassa.
    - Se il campo **Data fattura** era precedentemente impostato, lo sconto di cassa non viene modificato.

- **Tasso di cambio** – La data del tasso di cambio è determinata dall'impostazione dell'opzione **Aggiorna contabilità fornitore utilizzando la data fattura** nella scheda **Fattura** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**).

    - Se questa opzione è impostata su **sì**, viene utilizzata la data della fattura e la modifica della data di registrazione non influisce sul tasso di cambio.
    - Se questa opzione è impostata su **No**, la data di registrazione viene utilizzata per calcolare il tasso di cambio. Quando la data di registrazione viene aggiornata, gli importi di contabilizzazione e di dichiarazione vengono ricalcolati. Pertanto, la convalida della corrispondenza deve essere eseguita nuovamente.

## <a name="validation"></a>Convalida

Altri due campi nella scheda **Fattura** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**) influiscono sull'elaborazione delle fatture:

- Se il campo **Verifica il numero di fattura utilizzato** è impostato su **Rifiuta duplicati entro l'anno fiscale**, il sistema utilizza la data di registrazione per verificare la presenza di fatture duplicate durante la registrazione della fattura.
- Se il campo **Richiedi data documento sulla fattura fornitore** è impostato su **Opzione di errore**, il campo **Data fattura nell'intestazione fattura in sospeso** è obbligatiorio. Se la data della fattura è successiva alla data di registrazione, il sistema mostra un messaggio di errore.
