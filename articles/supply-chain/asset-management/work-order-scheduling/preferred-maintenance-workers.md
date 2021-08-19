---
title: Impostare gli addetti alla manutenzione preferiti
description: In questo argomento viene illustrato come impostare gli addetti alla manutenzione preferiti in Gestione cespiti.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 511d875baed029df9083da36baf6c48ca4b7abf866ae569038b554bf594473c8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734429"
---
# <a name="set-up-preferred-maintenance-workers"></a>Imposta gli addetti alla manutenzione preferiti

[!include [banner](../../includes/banner.md)]

 

Durante la programmazione degli ordini di lavoro, è possibile indicare una preferenza riguardo all'addetto alla manutenzione o al gruppo di addetti da allocare per completare l'ordine di lavoro. L'utilizzo di questa funzionalità è facoltativa, ma può consentire la scelta dell'addetto alla manutenzione più qualificato per completare un processo, in base alle competenze del lavoratore. Solo gli addetti alla manutenzione disponibili all'ora della programmazione verranno programmati. Se l'impostazione di un addetto alla manutenzione preferito corrisponde a un ordine di lavoro durante la programmazione, ma tale addetto è allocato ad altri processi, l'ordine di lavoro verrà programmato per un altro addetto alla manutenzione disponibile.

Prima di impostare gli addetti alla manutenzione preferiti, è innanzitutto necessario impostare gli addetti alla manutenzione e i gruppi di addetti. Per una descrizione su come impostare i gruppi di addetti e gli addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Impostare i lavoratori preferiti

Un addetto o un gruppo di addetti alla manutenzione preferito può essere associato uno o più dei seguenti elementi:

- settore  
- variante di tipi di processo di manutenzione  
- tipo di processo di manutenzione  
- categoria di tipi di processo di manutenzione  
- cespite  
- tipo di cespite  

Più selezioni vengono effettuate per lo stesso record, più specifica sarà l'impostazione.

1. Fare clic su **Gestione cespiti** > **Impostazione** > **Lavoratori** > **Addetti alla manutenzione preferiti**.

2. Fare clic su **Nuovo** per creare un nuovo record.

3. Iniziare creando un addetto alla manutenzione o un gruppo di lavoratori "predefinito". Ciò significa che si esegue una selezione solo nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**. Nella schermata seguente, viene visualizzato un esempio del primo record in cui "Richieste" è selezionato come **gruppo di addetti alla manutenzione preferito**.

    [!NOTE] L'impostazione predefinita verrà utilizzata durante la programmazione degli ordini di lavoro se nessun'altra combinazione più specifica corrisponde al contenuto dell'ordine di lavoro.

4. Ripetere il passaggio 2 per creare un nuovo record. Effettuare le selezioni necessarie, a seconda del livello di dettagli per l'addetto o il gruppo di addetti preferito. 

    *Esempio:* nella schermata seguente, nel sesto record, l'addetto alla manutenzione Shawn Richardson è selezionato come lavoratore preferito. Shawn sarà selezionato automaticamente durante la programmazione di un ordine di lavoro che include il cespite "CH-BP1-03-02" e il tipo di processo di manutenzione "Valutazione struttura", se è disponibile al momento della programmazione.

    [!NOTE] In genere, quando un addetto alla manutenzione preferito è selezionato durante la programmazione di un ordine di lavoro, Gestione cespiti esamina tutti i record **Addetti alla manutenzione preferiti** per determinare una corrispondenza possibile, sempre verificando dapprima la combinazione più specifica. Se non viene trovata alcuna corrispondenza, viene utilizzato il record "predefinito" con una selezione nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**.

![Figura 1.](media/02-work-order-scheduling.png)

È anche possibile impostare addetti alla manutenzione *responsabili* che possono essere selezionati quando viene creata una richiesta di intervento di manutenzione o un ordine di lavoro. È possibile modificare la selezione in **Tutti gli ordini di lavoro** e **Tutte le richieste di intervento di manutenzione**, se necessario. Per ulteriori informazioni, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).

Durante la programmazione degli ordini di lavoro, vengono calcolati vari punteggi per determinare quali lavoratori devono completare i processi relativi a un ordine di lavoro (tali punteggi sono impostati in **Parametri di gestione cespiti** >  collegamento **Programmazione dell'ordine di lavoro**). Se due o più addetti alla manutenzione preferiti o addetti alla manutenzione responsabili ottengono lo stesso punteggio durante la programmazione dell'ordine di lavoro, un lavoratore viene selezionato in modo casuale. In caso contrario, è sempre il lavoratore con il punteggio massimo che viene scelto per completare un ordine di lavoro.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]