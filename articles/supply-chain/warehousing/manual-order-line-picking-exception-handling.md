---
title: Gestire manualmente le vendite e le eccezioni di prelievo riga di trasferimento
description: Questo articolo descrive come gli amministratori possono prelevare (o annullare il prelievo) manualmente le transazioni di magazzino per risolvere i problemi causati da vendite danneggiate e trasferire i dati degli ordini.
author: perlynne
ms.date: 08/19/2022
ms.topic: article
ms.search.form: WHSManualSalesLinePicking, WHSManualInventTransferLinePicking, InventTransPick, WHSLoadLineManualCorrection, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d2f89a7109060e69aca6a06eadaedc017728bbae
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403670"
---
# <a name="manually-handle-sales-and-transfer-line-picking-exceptions"></a>Gestire manualmente le vendite e le eccezioni di prelievo riga di trasferimento

[!include [banner](../includes/banner.md)]

La gestione manuale delle eccezioni di prelievo riga di vendita e trasferimento consente agli amministratori di risolvere i problemi causati da dati di vendita e ordini di trasferimento danneggiati. Consente agli utenti attendibili di prelevare (o annullare il prelievo) manualmente le transazioni di magazzino correlate alle righe ordine di vendita e trasferimento mentre i processi di magazzino sono già in corso.

La funzionalità qui descritta deve essere utilizzata solo nei casi in cui il sistema non può completare l'elaborazione dello stack dei processi di magazzino nel modo consueto. Per impostazione predefinita, solo gli utenti che dispongono di un ruolo di amministratore di sistema possono usarlo. Tuttavia, puoi concederne l'accesso assegnando il privilegio *Preleva manualmente le righe di vendita* ad altri ruoli di cui hai bisogno.

## <a name="turn-on-this-feature-for-your-system"></a>Attivare questa funzionalità per il sistema

Prima di poter utilizzare una delle funzionalità descritte in questo articolo, è necessario attivarla nel sistema. Gli amministratori possono usare le [impostazioni di gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato delle varie funzionalità e attivarle. Nell'area di lavoro **Gestione funzionalità**, le funzionalità sono elencate nel modo seguente:

- *Servizio di prelievo manuale righe di vendita per amministratori o utenti attendibili simili*<br>(a partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata).
- *Servizio di prelievo manuale righe di trasferimento per amministratori o utenti attendibili simili*

## <a name="correct-transactions-related-to-sales-or-transfer-order-lines"></a>Correggere le transazioni relative alle righe dell'ordine di vendita o di trasferimento

Utilizzare la procedura seguente per correggere le transazioni correlate a righe ordine di vendita o di trasferimento.

1. Seguire uno di questi passaggi a seconda del tipo di ordine che è necessario correggere:

    - Per correggere una transazione correlata a un ordine cliente, andare a **Gestione del magazzino \> Attività periodica \> Pulitura \> Preleva manualmente le righe di vendita**.
    - Per correggere una transazione correlata a un ordine di trasferimento, andare a **Gestione del magazzino \> Attività periodica \> Pulitura \> Preleva manualmente le righe di trasferimento**.

1. Nella pagina **Preleva manualmente le righe di vendita** o **Preleva manualmente le righe di trasferimento**, utilizzare i filtri nella parte superiore della griglia per trovare la riga che si sta cercando, quindi selezionare la riga dell'ordine di destinazione nella griglia superiore.
1. Utilizzare le schede **Transazioni di inventario**, **Righe carico**, **Righe lavoro** e **Righe contenitore** nella sezione inferiore per visualizzare ulteriori informazioni sulla riga selezionata. Le informazioni in queste schede forniscono una panoramica di base dei processi di magazzino correlati e dei relativi stati.
1. Nel riquadro Azioni, seleziona **Preleva** per aprire la riga ordine selezionata nella pagina **Preleva** per le transazioni di inventario. È possibile completare questo passaggio anche per le righe ordine che sono già state rilasciate al magazzino. (In genere, le righe ordine che sono state rilasciate al magazzino non possono essere aperte nella pagina **Preleva**.)

    > [!NOTE]
    > Potresti ricevere vari avvisi quando apri la pagina **Preleva**. Eseguire qualsiasi azione consigliata da questi avvisi. Ad esempio, potresti ricevere un avviso sulle righe ordine collegate al lavoro di magazzino. In questo caso, ha senso provare ad annullare il lavoro utilizzando la funzionalità [Annulla il lavoro](cancel-warehouse-work.md) standard prima di eseguire la correzione manuale.

1. Selezionare la riga nella griglia **Transazioni**, quindi selezionare **Aggiungi riga di prelievo** nella barra degli strumenti **Transazioni**.
1. La riga selezionata viene spostata nella griglia **Righe di prelievo**. Impostare i valori appropriati per tutte le colonne in cui mancano le informazioni richieste. (Ad esempio, specificare l'ubicazione e la targa da cui prelevare/non prelevare l'articolo.)
1. Nella barra degli strumenti **Righe di prelievo**, selezionare **Conferma Preleva tutto**.

## <a name="correct-load-line-quantities"></a>Correggere le quantità della riga di carico

Utilizzare la seguente procedura per rettificare la quantità della riga di carico.

1. Seguire uno di questi passaggi a seconda del tipo di ordine che è necessario correggere:

    - Per correggere una transazione correlata a un ordine cliente, andare a **Gestione del magazzino \> Attività periodica \> Pulitura \> Preleva manualmente le righe di vendita**.
    - Per correggere una transazione correlata a un ordine di trasferimento, andare a **Gestione del magazzino \> Attività periodica \> Pulitura \> Preleva manualmente le righe di trasferimento**.

1. Nella pagina **Preleva manualmente le righe di vendita** o **Preleva manualmente le righe di trasferimento**, utilizzare i filtri nella parte superiore della griglia per trovare la riga che si sta cercando, quindi selezionare la riga dell'ordine di destinazione nella griglia superiore.
1. Nella scheda **Righe di carico**, nella sezione inferiore, selezionare **Correggi manualmente righe di carico** sulla barra degli strumenti.
1. Nella pagina **Correggi manualmente righe di carico**, nella griglia **Transazioni di magazzino**, rivedere le transazioni di magazzino correlate alla riga di carico selezionata.
1. Nella griglia superiore, correggere le quantità della riga di carico nelle seguenti colonne come richiesto:

    - **Quantità di lavoro creata**
    - **Quantità prelevata**
    - **Quantità cross-docking pianificata**

    Il sistema convaliderà tutte le modifiche apportate a queste colonne.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
