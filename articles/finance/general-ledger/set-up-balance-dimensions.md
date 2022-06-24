---
title: Come posso impostare il bilanciamento delle dimensioni finanziarie?
description: Questo articolo descrive le opzioni per l'impostazione e l'utilizzo della funzionalità della dimensione finanziaria di bilanciamento.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: dd859629b0eb9f14fa4907699613382f3897d21d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878014"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>Come posso impostare il bilanciamento delle dimensioni finanziarie?

[!include [banner](../includes/banner.md)]

Questo articolo descrive le opzioni per l'impostazione e l'utilizzo della funzionalità della dimensione finanziaria di bilanciamento.

## <a name="symptom"></a>Sintomo

Sono disponibili due opzioni per l'impostazione delle dimensioni finanziarie di bilanciamento. La prima opzione è usare il campo **Bilanciamento della dimensione finanziaria** nella pagina di configurazione **Contabilità generale** (**Contabilità generale \> Configurazione contabilità generale \> Contabilità generale**). La seconda opzione è usare il campo **Richiedi che la dimensione sia bilanciata** nella pagina **Dimensioni finanziarie** (**Contabilità generale > Piano dei conti \> Dimensioni \> Dimensioni finanziarie**). Questo articolo spiega la differenza tra queste due opzioni.

## <a name="resolution"></a>Risoluzione

Le organizzazioni in genere utilizzano le dimensioni di bilanciamento per generare uno stato patrimoniale a livello di dimensione finanziaria. L'abilitazione di entrambe le funzionalità non riequilibrerà le dimensioni registrate e sbilanciate. È necessario prima inserire manualmente le voci di rettifica per riequilibrare lo stato patrimoniale prima di abilitare entrambe le funzioni.

Le due opzioni si escludono a vicenda. L'opzione utilizzata dall'organizzazione dovrebbe essere basata sui requisiti aziendali. Si sente spesso parlare di clienti che definiscono la dimensione di bilanciamento sia nell'impostazione della contabilità generale che nell'impostazione della dimensione finanziaria e quindi completano alcune o tutte le impostazioni aggiuntive richieste. Tuttavia, non possono ancora pubblicare a causa di uno squilibrio a livello di dimensione finanziaria.

Le sezioni seguenti descrivono le due opzioni e spiegano come impostarle.

### <a name="ledger--balancing-financial-dimension"></a>Contabilità generale - Dimensione finanziaria di bilanciamento

La dimensione di bilanciamento nella pagina di configurazione della **Contabilità generale** viene utilizzata per abilitare la contabilizzazione interunità. Per attivare la funzionalità, effettuare le seguenti operazioni.

1. Determina quale dimensione finanziaria sarà la dimensione di bilanciamento.

    - Questa funzionalità consente di selezionare solo una dimensione finanziaria come dimensione di bilanciamento.
    - Non selezionare ancora la dimensione nella pagina di configurazione della **Contabilità generale**.
    - Assicurati che lo stato patrimoniale sia già in pareggio per la dimensione finanziaria selezionata.

2. Aggiornare la struttura dei conti per la dimensione finanziaria di bilanciamento.

    - La dimensione finanziaria di bilanciamento deve essere inclusa in tutte le strutture dei conti assegnate alla contabilità generale.
    - La dimensione finanziaria non deve consentire spazi vuoti nella struttura dei conti. Questa restrizione garantisce che ogni registrazione contabile registrata in Contabilità generale contenga un valore di dimensione finanziaria. Una dimensione vuota non è valida quando si utilizzano dimensioni di bilanciamento.

3. Nella pagina **Conti per transazioni automatiche** (**Contabilità generale \> Impostazione di registrazione \> Conti per transazioni automatiche**), definire i conti principali interunitari dare e avere.
4. Nella pagina di configurazione **Contabilità generale** (**Contabilità generale \> Impostazione contabilità generale \> Contabilità generale**), nel campo **Dimensione finanziaria di bilanciamento**, selezionare una dimensione finanziaria da usare per il bilanciamento.

Se la dimensione finanziaria selezionata non viene bilanciata durante l'inserimento e la registrazione delle transazioni, il sistema aggiungerà automaticamente le voci di dare o avere necessarie per bilanciare la registrazione contabile durante la registrazione. I conti di contabilità debito e credito per la transazione interunità vengono visualizzati nel giustificativo registrato in Contabilità generale. Tuttavia, non verranno visualizzati nei giornali di registrazione o nei documenti di origine per i quali sono state registrate le registrazioni contabili.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Dimensioni finanziarie - richiedono che la dimensione sia bilanciata

Sebbene la dimensione di bilanciamento nella pagina **Dimensioni finanziarie** è tipicamente utilizzata dalle aziende del settore pubblico, la funzionalità non è collegata ad alcuna chiave di configurazione del settore pubblico. Poiché non ci sono limitazioni nel sistema, puoi utilizzare questa funzionalità anche se la tua organizzazione non è un'entità del settore pubblico.

Questa funzionalità viene in genere utilizzata nella clientela del settore pubblico perché richiede l'utilizzo di definizioni di registrazione per bilanciare automaticamente ogni transazione. Non utilizza i conti di debito e di credito interunitari definiti nella pagina **Conti per transazioni automatiche** per bilanciare automaticamente le voci contabili. Se una voce contabile non viene bilanciata a livello di dimensione dopo l'applicazione delle definizioni di registrazione, la transazione non verrà registrata, anche se sono definiti i conti di debito e di credito interunitari.

Si sente spesso parlare di clienti che definiscono la dimensione di bilanciamento sia nell'impostazione della contabilità generale che nell'impostazione della dimensione finanziaria. In questo caso, il sistema utilizza la funzionalità delle dimensioni finanziarie. L'impostazione per le dimensioni di bilanciamento a livello di dimensione finanziaria ha la precedenza durante la registrazione. La registrazione avrà esito negativo se la definizione di registrazione non crea una voce contabile bilanciata a livello di dimensione finanziaria.

Seguire questi passaggi per attivare l'utilizzo di una dimensione di bilanciamento a livello di dimensione finanziaria.

1. Determina quali dimensioni finanziarie saranno le dimensioni di bilanciamento.

    - È possibile impostare più di una dimensione finanziaria come dimensione di bilanciamento.
    - Non impostare ancora le dimensioni finanziarie che saranno necessarie per bilanciare una transazione nella pagina **Dimensioni finanziarie**.

2. Definire le definizioni di registrazione per ogni tipo di giornale di registrazione o documento di origine utilizzato dalla propria organizzazione. Le definizioni di registrazione utilizzano i conti contabili da un giornale di registrazione non registrato o da un documento di origine come "criteri di corrispondenza". La definizione di registrazione restituisce quindi le "voci generate" che diventano la voce contabile. Se la definizione di registrazione è impostata correttamente, la voce generata include i conti contabili dei criteri di corrispondenza, oltre a conti aggiuntivi per bilanciare la voce contabile a livello di dimensione. Per ulteriori informazioni, vedere [Definizioni di registrazione](posting-definitions.md). 
   
   Le definizioni di registrazione non sono supportate su ogni tipo di transazione. Ad esempio, non è possibile definire definizioni di registrazione per le transazioni immesse tramite il Giornale di registrazione generale o il Giornale di registrazione cespiti. Se non è possibile definire una definizione di registrazione per un giornale di registrazione o un documento di origine, la transazione deve essere bilanciata manualmente in base al valore della dimensione finanziaria. Ad esempio, se viene effettuata una scrittura contabile generale e la dimensione Reparto è la dimensione di bilanciamento, è necessario assicurarsi che ogni valore di reparto sia in pareggio.  Se la dimensione non è bilanciata per ogni valore di reparto, il giustificativo non verrà registrato finché lo sbilanciamento non verrà corretto aggiungendo manualmente un addebito o un credito interunitario al giustificativo. 

    > [!IMPORTANT]
    > Se un numero eccessivo di transazioni deve essere bilanciato manualmente, **non** dovresti utilizzare la funzionalità dimensione di bilanciamento nella pagina **Dimensioni finanziarie**. Utilizzare invece la funzionalità della dimensione di bilanciamento nella pagina di configurazione **Contabilità generale**.

3. Dopo aver definito le definizioni di registrazione, le dimensioni finanziarie possono essere contrassegnate come richieste per il bilanciamento.

Quando si immettono e si registrano le transazioni, le definizioni di registrazione vengono richiamate durante la registrazione per determinare le voci contabili. Se le dimensioni finanziarie sono bilanciate, la convalida avviene dopo la determinazione delle voci contabili. Se le dimensioni finanziarie non sono bilanciate, la transazione non verrà registrata e riceverai un messaggio che indica che i debiti non corrispondono ai crediti per una dimensione specifica.
