---
title: Processo di pulizia delle voci disponibili per la gestione del magazzino
description: Questo argomento descrive il processo di pulizia delle voci disponibili, che consente di migliorare le prestazioni del sistema identificando ed eliminando record correlati ma non necessari.
author: perlynne
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 4dd3bb9dc580e715b6945da1f94cf27e601c549e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808728"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Processo di pulizia delle voci disponibili per la gestione del magazzino

Le prestazioni delle query utilizzate per calcolare le scorte disponibili sono influenzate dal numero di record nelle tabelle interessate. Un modo di migliorare le prestazioni è ridurre il numero di record che il database deve considerare.

Questo argomento descrive il processo di pulizia delle voci disponibili, che elimina i record non necessari nelle tabelle InventSum e WHSInventReserve. Queste tabelle contengono informazioni sulla disponibilità per gli articoli abilitati per l'elaborazione della gestione del magazzino. (questi articoli sono definiti articoli Gestione magazzino). La cancellazione di questi record può migliorare significativamente le prestazioni dei calcoli sulle disponibilità.

## <a name="what-the-cleanup-job-does"></a>Funzione del lavoro di pulizia

Il processo di pulizia delle voci disponibili elimina tutti i record nelle tabelle WHSInventReserve e InventSum in cui tutti i valori dei campi sono *0* (zero). Questi record possono essere eliminati perché non contribuiscono alle informazioni sulla disponibilità. Il processo elimina solo i record al di sotto del livello **Ubicazione**.

Se un inventario fisico negativo è consentito, il processo di pulizia potrebbe non essere in grado di eliminare tutte le voci pertinenti. Il motivo di questa limitazione è che il processo deve consentire uno scenario speciale in cui una targa ha più numeri di serie e uno di quei numeri di serie è diventato negativo. Ad esempio, il sistema avrà una disponibilità zero a livello di targa quando una targa ha +1 pezzi del numero di serie 1 e -1 pezzi del numero di serie 2. Per questo scenario speciale, il processo esegue dapprima un'eliminazione in profondità tentando di eliminare prima i livelli inferiori.

## <a name="schedule-and-configure-the-cleanup-job"></a>Pianificare e configurare il processo di pulizia

Il processo di pulizia delle voci disponibili è disponibile in **Gestione scorte \> Attività periodiche \> Pulizia \> Processo di pulizia delle voci disponibili per la gestione del magazzino**. Utilizzare le impostazioni del processo standard per controllare l'ambito e la pianificazione per l'esecuzione del processo. Inoltre, sono disponibili le seguenti impostazioni:

- **Elimina se non aggiornato da giorni** - Immettere il numero minimo di giorni che il processo deve attendere prima di eliminare una voce disponibile la cui quantità è scesa a zero. Utilizzare questa impostazione per ridurre il rischio di eliminare le voci disponibili ancora in uso. Se la pulizia deve essere eseguita il più presto possibile, immettere *0* (zero) o lasciare vuoto il campo.
- **Tempo di esecuzione massimo (ore)** - Immettere il tempo di esecuzione massimo del processo di pulizia, in ore. Se il processo non viene completato prima della scadenza di tale periodo di tempo, salverà il lavoro completato fino a quel momento e quindi si chiuderà automaticamente. Questa funzionalità è particolarmente rilevante per le implementazioni che fanno un utilizzo elevato delle scorte. In questi casi, è necessario pianificare il processo affinché venga eseguito quando il carico del sistema è il più basso possibile. Se il processo batch deve continuare a essere eseguito fino al completamento, immettere *0* (zero) o lasciare il campo vuoto. Questa impostazione è disponibile solo se la relativa funzionalità è stata [attivata nel sistema](#max-execution-time).

Sebbene sia possibile eseguire il processo durante il normale orario lavorativo, si consiglia di eseguirlo in altri periodi della giornata. In questo modo, si prevengono i conflitti che possono verificarsi se un utente sta utilizzando un record che viene anch'esso pulito.

Se il processo tenta di eliminare un record di un articolo mentre quel record viene utilizzato da un altro utente, si verifica un errore di deadlock per il processo di pulizia o per l'utente.

Quando il processo è in esecuzione, ha una dimensione di commit pari a 100. In altre parole, proverà a eseguire il commit per ogni 100 eliminazioni. Tuttavia, poiché alcune eliminazioni sono basate su set, potrebbero esserci scenari in cui è possibile eliminare più di 100 record nella stessa transazione. Pertanto, a volte possono verificarsi delle escalation di blocchi.

## <a name="possible-user-impact"></a>Impatto possibile sugli utenti

Gli utenti potrebbero essere interessati se il processo di pulizia delle voci disponibili elimina tutti i record per un determinato livello (come il livello della targa). In questo caso, la funzionalità che consente di determinare che l'inventario era precedentemente disponibile in una targa potrebbe non funzionare come previsto, poiché le voci disponibili pertinenti non sono più disponibili. Questa capacità può essere utile nelle seguenti situazioni:

- In **Scorte disponibili**, quando l'utente deseleziona la condizione **Quantità\<\> 0** o seleziona la condizione **Transazioni chiuse** nelle impostazioni **Visualizzazione delle dimensioni**.
- In un report **Inventario fisico per dimensione inventariale** per periodi passati, quando l'utente imposta il parametro **In data**.

Tuttavia, il miglioramento delle prestazioni fornito dal lavoro di pulizia dovrebbe compensare queste piccole perdite di funzionalità.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>Rendere disponibile l'impostazione Tempo di esecuzione massimo

Per impostazione predefinita, l'impostazione **Tempo di esecuzione massimo** non è disponibile. Se si desidera utilizzarla, è necessario utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare la funzione correlata nel sistema. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzione:** *Tempo di esecuzione massimo per il processo di pulizia delle voci disponibili per la gestione del magazzino*


[!INCLUDE[footer-include](../../includes/footer-banner.md)]