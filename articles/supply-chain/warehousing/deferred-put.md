---
title: Elaborazione differita di lavoro di magazzino
description: In questo argomento vengono descritte le funzionalità che rendono l'elaborazione differita delle operazioni di stoccaggio del lavoro di magazzino disponibili in Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d274eae4ad3ba60eadb18ca8de22d4b2d10fe727
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205692"
---
# <a name="deferred-processing-of-warehouse-work"></a>Elaborazione differita di lavoro di magazzino

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità che rendono l'elaborazione differita delle operazioni di stoccaggio per il lavoro di magazzino disponibili in Dynamics 365 Supply Chain Management.

La funzionalità di elaborazione differita consente agli addetti al magazzino di continuare a fare altro lavoro mentre l'operazione di stoccaggio elaborata in background. L'Elaborazione differita è utile quando più righe di lavoro devono essere elaborate e il lavoratore può lasciare che il lavoro sia elaborato in modo asincrono. È inoltre utile quando il server può avere aumenti ad hoc o non pianificati nel tempo di elaborazione e il tempo di elaborazione aumentato può influire sulla produttività dell'utente.

L'elaborazione in background viene ottenuta utilizzando il framework SysOperation. Per ulteriori informazioni, vedere [Panoramica del framework SysOperation](https://docs.microsoft.com/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>Configurazione dei criteri di elaborazione del lavoro

Per utilizzare l'elaborazione differita, è necessario configurare e utilizzare un criterio di elaborazione del  lavoro.

I criteri sono configurati nella pagina **Criteri di elaborazione lavoro**. Nella seguente tabella vengono illustrati i campi della pagina.

| Campo                           | Descrizione |
|---------------------------------|-------------|
| Nome criteri di elaborazione lavoro     | Nome del criterio di elaborazione del lavoro. |
| Tipo ordine di lavoro                 | Tipo di ordine di lavoro a cui si applicano i criteri. |
| Operazione                       | Operazione che viene elaborata utilizzando i criteri. |
| Metodo di elaborazione lavoro          | Metodo usato per elaborare la riga di lavoro. Se il metodo è impostato su **Immediato**, il comportamento è simile al comportamento quando nessun criterio di elaborazione del lavoro viene utilizzato per elaborare la riga. Se il metodo è impostato su **Differito**, l'elaborazione differita che utilizza il framework batch viene utilizzata. |
| Soglia di elaborazione differita   | Il valore **0** (zero) indica che non esiste una soglia. In questo caso, l'elaborazione differita viene utilizzata se possibile. Se il calcolo specifico è inferiore alla soglia, il metodo immediato viene utilizzato. In caso contrario, verrà usato il metodo Differito se possibile. Per lavoro correlato a vendite e trasferimenti, la soglia viene calcolata come il numero di righe di carico di origine associate che vengono elaborate per il lavoro. Per il lavoro di rifornimento, la soglia viene calcolata come il numero di righe di lavoro rifornite dal lavoro. Impostando una soglia, ad esempio, **5** per le vendite, i lavori più piccoli con meno di cinque righe di carico di origine iniziali non useranno l'elaborazione differita, ma i lavori maggiori sì. La soglia ha effetto solo se il metodo di elaborazione di lavoro è **Differito**. |
| Gruppo batch di elaborazione differita |Gruppo batch utilizzato per elaborazione. |

Per l'elaborazione differita di stoccaggio, sono supportati i seguenti tipi di ordini di lavoro: ordine cliente, invio dell'ordine di trasferimento e rifornimento.

## <a name="assigning-the-work-creation-policy"></a>Assegnare i criteri di creazione del lavoro

I criteri di creazione di lavoro possono essere assegnati nei parametri di gestione magazzino. Possono inoltre essere assegnati a livello dei singoli magazzini. Se i criteri sono assegnati a un magazzino, vengono applicati solo a lavoro creato per tale magazzino. Se non viene assegnato criteri a livello di magazzino, i criteri dai parametri di gestione magazzino vengono applicati.

## <a name="viewing-the-deferred-put-processing-tasks"></a>Visualizzazione delle attività di elaborazione differita di stoccaggio

È possibile visualizzare le attività di elaborazione differita di stoccaggio nella pagina **Attività di elaborazione differita stoccaggio**.

Per impostazione predefinita, le attività **Completate** verranno visualizzate.

| Campo            | Descrizione |
|------------------|-------------|
| Stato           | Stato dell'attività. |
| Stato del processo batch | Stato del processo batch correlato. Se il processo batch è stato elaborato, lo storico batch contiene il registro e le informazioni del processo batch. |

Ecco una descrizione dei possibili stati:

- **In attesa** - Il processo batch correlato è in attesa di elaborazione nel server batch.
- **Non riuscito** - Elaborazione non riuscita. L'attività può essere rielaborata mediante l'azione **Elabora stoccaggio differito**, oppure è possibile annullarla con l'azione **Annulla stoccaggio differito**.
- **Completato** - Il processo è stato completato.

## <a name="impact-on-closed-work-dates"></a>Impatto sulle date di chiusura lavoro

Se l'elaborazione differita dello stoccaggio viene utilizzata, la data di chiusura lavoro è impostata come data/ora creazione delle attività di elaborazione differita dello stoccaggio. La data di chiusura di lavoro viene utilizzata perché è la stima migliore relativa al completamento dell'operazione di stoccaggio.

## <a name="reprocessing-a-failed-task"></a>Rielaborazione di un'attività non riuscita

È possibile rielaborare un'attività non riuscita selezionandola nella pagina e quindi facendo clic su **Elabora stoccaggio differito**. La rielaborazione corrisponde a una situazione in cui l'utente completa lo stoccaggio tramite il dispositivo mobile come se fosse stato impostato per l'elaborazione immediata.

## <a name="canceling-failed-tasks"></a>Annullare le attività non riuscite

Solo attività non riuscite possono essere annullate. Quando si annulla un'attività, è possibile assegnarla a un nuovo utente. In alternativa, l'attività può rimanere assegnato all'utente che ha elaborato il lavoro. L'annullamento corrisponde a una situazione in cui il lavoro viene riportato nel dispositivo mobile come se fosse appena stato completato l'ultimo passaggio di prelievo e il lavoro deve essere stoccato. Tuttavia, l'utente potrà determinare che il lavoro è "diverso", perché avrà solo un passaggio di stoccaggio e l'ubicazione corrisponderà all'ubicazione che il primo utente che ha elaborato il lavoro aveva come ubicazione di stoccaggio finale.

Quando un'attività viene annullata, il lavoro non verrà più bloccato dal motivo di blocco di elaborazione differita di stoccaggio. Può essere rielaborato utilizzando il dispositivo mobile.

Il record attività viene eliminati quando l'attività viene annullata.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configurazione del menu del dispositivo mobile per ignorare i criteri di elaborazione differita

È possibile configurare la voce di menu del dispositivo mobile in modo da non utilizzare i criteri di elaborazione differita. Il lavoro viene quindi elaborato come quando alcun criteri di elaborazione differita viene utilizzato. Questa funzionalità consente a un supervisore di utilizzare una voce di menu specifica dove lo stoccaggio differito non viene utilizzato. Per configurarla, impostare il campo **Criteri di elaborazione differita stoccaggio** su **Ignora impostazioni ed elabora stoccaggio in modo sincrono**. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Limitazioni quando l'elaborazione differita dello stoccaggio non si applica

Esistono vari scenari in cui l'elaborazione differita dello stoccaggio non viene applicata anche se i criteri sono configurati. Di seguito sono riportati alcuni esempi.

- Il completamento manuale di lavoro verrà utilizzato.
- Il lavoro viene completato utilizzando il completamento automatico.
- I modelli di audit vengono utilizzati.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>Monitoraggio delle attività di elaborazione differita dall'area di lavoro Monitoraggio lavoro in uscita

L'area di lavoro **Monitoraggio lavoro in uscita** ha due riquadri che consentono di controllare le attività di elaborazione differita dello stoccaggio:

- **Attività di elaborazione differita stoccaggio non riuscite** - Questi riquadri mostrano il numero di attività non riuscite. Se sono presenti attività non riuscite, il responsabile del magazzino deve rielaborarle o annullarle, in quanto non verranno rielaborate automaticamente.
- **Attività di elaborazione differita stoccaggio in attesa** - Questo riquadro mostra il numero di attività che sono state in stato **In attesa** per oltre 10 minuti. Se il riquadro mostra un numero, può indicare che un problema si è verificato durante l'elaborazione batch. È possibile elaborare manualmente le attività **In attesa**. Se il processo batch per un'attività viene elaborato in seguito, avrà solo esito negativo, poiché è già stato elaborato. Non ci sarà impatto.

## <a name="deleting-completed-tasks"></a>Eliminazione di attività completate

È possibile eliminare le attività di elaborazione differita dello stoccaggio già completate selezionandole e eliminandole nella pagina.
