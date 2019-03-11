---
title: Configura strutture dei conti
description: In questo argomento vengono fornite informazioni sulle strutture dei conti e le dimensioni finanziarie.
author: aprilolson
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0665f5aec2a0809ecb383c1d4adf4c2072c9569
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "351725"
---
# <a name="configure-account-structures"></a>Configura strutture dei conti

[!include[banner](../includes/banner.md)]

Le strutture dei conti utilizzano il conto principale e le dimensioni finanziarie per creare un set di regole che determinano l'ordine e i valori utilizzati quando si inserisce il numero di conto. È possibile impostare un numero illimitato di strutture dei conti in base alle esigenze della propria azienda. Le strutture dei conti vengono assegnate alla configurazione della contabilità generale di una società, in modo che possano essere condivise.

Quando si crea una struttura dei conti, il numero massimo di segmenti è 11. Se sono necessari più segmenti, è consigliabile valutare a fondo la configurazione e i requisiti della società in quanto questi avranno un impatto sull'esperienza utente. Considerare se un segmento può essere derivato in uno scenario di creazione report utilizzando una gerarchia anziché durante la registrazione ordine oppure utilizzando un campo definito dall'utente. Ad esempio, se si desidera creare un report sull'ubicazione, ma è possibile vedere la posizione per reparto o centro di costo, non è necessario vedere la posizione come dimensione finanziaria. Se dopo la valutazione si determina la necessità di avere più di 11 segmenti, è possibile aggiungerne utilizzando le regole avanzate.

Le strutture dei conti richiedono il conto principale. Il conto principale non deve necessariamente essere il primo segmento nella struttura, ma identifica la struttura dei conti da utilizzare durante l'immissione del numero di conto. Un valore di numero di conto può quindi esistere solo in una struttura assegnata alla contabilità generale e pertanto non c'è sovrapposizione. Dopo che la struttura dei conti è stata identificata, l'elenco dei valori consentiti viene filtrato in modo che l'utente possa selezionare solo valori di dimensione validi, riducendo così la possibilità di immettere scritture contabili errate.

> [!NOTE] 
> Se si prevede di creare il budget in base a una dimensione finanziaria, dovrà far parte di una struttura dei conti. L'impostazione del budget non utilizza attualmente le regole avanzate.

## <a name="example"></a>Esempio
Per illustrare una procedura guidata per l'impostazione di una struttura dei conti, si supponga che una società voglia tenere traccia dei propri conti dello stato patrimoniale a livello di conto e di dimensione finanziaria di Business Unit. Per i conti spese e ricavi (400000..999999), la società tiene traccia delle dimensioni finanziarie a livello di Business Unit, Reparto e Centro di costo. Se avviene una vendita, la società desidera tenere traccia anche del Cliente. In questo scenario, è consigliabile avere due strutture dei conti assegnate alla contabilità generale della società: una per i conti dello stato patrimoniale e una per i conti profitti e perdite. Per ottimizzare l'esperienza utente e la convalida, il cliente deve essere una regola avanzata che viene utilizzata solo quando viene utilizzato un conto vendite.

**Struttura dei conti dello stato patrimoniale**

|Conto principale          | Business Unit    |
|----------------------|-----------|
|100000..399999 | *;" "|

**Struttura dei conti profitti e perdite**

|Conto principale          | Business Unit    |Reparto          | Centro di costo    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | *;" "|*;" "|*;" "|*;" "|

**Regola avanzate per l'aggiunta di un cliente**

Criteri: dove il conto principale è compreso tra 400000 e 499999, quindi aggiungere il cliente. Non può essere lasciato vuoto.

|Cliente         |
|-----------------|
|* |

In questo esempio semplificato, sono consentiti tutti i valori e i valori vuoti, pertanto vengono utilizzati * e " ".

## <a name="segments-and-allowed-values"></a>Segmenti e valori consentiti
Le sezioni **Segmenti** e **Dettagli valori consentiti** contengono una grigli come esperienza per immissione di regole che saranno seguite nella convalida durante la registrazione. È possibile immettere direttamente nelle celle della griglia, importare da Excel o utilizzare la sezione **Dettagli valori consentiti** e seguire le istruzioni.

La sezione **Dettagli valori consentiti** fornisce le istruzioni per creare i criteri utilizzando **Operatori** come inizia con, è compreso in, include e molti altri.

[![Valori consentiti](./media/account.png)](./media/account.png) 

## <a name="more-than-7-criteria-needed"></a>Sono necessari più di 7 criteri

Se sono necessari più di 7 criteri, è possibile continuare ad aggiungerne nella riga successiva. Quando si utilizza la sezione **Dettagli valori consentiti** si noterà che il criterio **+Aggiungi nuovo** non è più attivo dopo che viene immesso il settimo criterio. Ciò è dovuto a molti fattori tra cui: 
 - Larghezza colonna 
 - Modalità con cui i dati vengono memorizzati 
 - Prestazioni del controllo **Dettagli valori consentiti**
 - Usabilità  
 
Per continuare ad aggiungere altri criteri, fare clic su **Duplica nel segmento** e sulla sezione **Valori consentiti**. Questa operazione copia i criteri in una nuova riga. È quindi possibile immettere i dettagli o modificare la sezione **Dettagli valori consentiti**.

(COLLEGAMENTO AL VIDEO CHE SARÀ CREATO)

## <a name="best-practices"></a>Procedure consigliate
Quando si impostano le strutture dei conti esistono alcune procedure consigliate che è possibile seguire. Si tratta tuttavia di indicazioni pertanto una discussione olistica su business, piano di crescita e piano di gestione deve essere considerata parte integrante di tale discussione.

- Creare il conto principale a primo livello della struttura dei conti o il più vicino possibile all'inizio della struttura, in modo che gli utenti ottengano la migliore esperienza possibile durante l'immissione delle voci contabili.

- Riutilizzare le strutture dei conti il più possibile per ridurre la gestione nelle persone giuridiche.

- Per variazioni tra persone giuridiche, considerare l'utilizzo di regole avanzate in modo che le strutture dei conti possano essere riutilizzate.

- Quando si definiscono i valori consentiti, utilizzare intervalli e caratteri jolly il più possibile. Ciò non consente solo di crescere e cambiare senza manutenzione, ma le prestazioni del sistema risultano più ottimali con questa configurazione.

- Basta non mettere un asterisco per ogni segmento nella struttura dei conti e quindi affidarsi solo alle regole avanzate. Questa situazione può essere difficile da gestire e spesso porta a errori da parte dell'utente durante la manutenzione che possono impedire al sistema di registrare.

## <a name="account-structure-activation"></a>Attivazione struttura dei conti
Quando si è soddisfatti della nuova impostazione o di una modifica della struttura dei conti, è necessario attivarla. Se una struttura dei conti è assegnata a una contabilità generale, questa attivazione può essere un processo lungo, in quanto tutte le transazioni non registrate nel sistema devono essere sincronizzate con la nuova struttura. Le transazioni registrate non vengono influenzate dalle modifiche della struttura dei conti.

Per ulteriori informazioni, vedere [Definire il piano dei conti](plan-chart-of-accounts.md), [Dimensioni finanziarie](financial-dimensions.md) e [Immettere le combinazioni di conto e dimensione (controllo di voci segmentato)](enter-account-dimension-combinations-segmented-entry-control.md).
