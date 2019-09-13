---
title: Impostare gli addetti alla manutenzione preferiti
description: In questo argomento viene illustrato come impostare gli addetti alla manutenzione preferiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887413"
---
# <a name="preferred-maintenance-workers"></a>Addetti alla manutenzione preferiti

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

È possibile indicare una preferenza riguardo agli addetti alla manutenzione da allocare per completare gli ordini di lavoro durante la programmazione degli stessi. L'utilizzo di questa funzionalità è facoltativa, ma può consentire la scelta dell'addetto alla manutenzione più qualificato per completare un processo, in base alle competenze del lavoratore. Pertanto, durante la programmazione degli ordini di lavoro, l'impostazione in **Addetti alla manutenzione preferiti** viene utilizzata per determinare se uno specifico addetto alla manutenzione o gruppo di addetti alla manutenzione deve essere programmato per un ordine di lavoro. Solo gli addetti alla manutenzione disponibili all'ora della programmazione verranno programmati. Se l'impostazione di un addetto alla manutenzione preferito corrisponde a un ordine di lavoro durante la programmazione, ma tale addetto è allocato ad altri processi, l'ordine di lavoro verrà programmato per un altro addetto alla manutenzione disponibile.

Prima di poter impostare gli addetti alla manutenzione preferiti, è necessario dapprima impostare gli addetti e i gruppi di addetti alla manutenzione che devono essere disponibili per la selezione. Per una descrizione su come impostare i gruppi di addetti e gli addetti alla manutenzione, vedere [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Impostare i lavoratori preferiti

Un addetto o un gruppo di addetti alla manutenzione preferito può essere associato in modo specifico a

- settore  
- variante di tipi di processo di manutenzione  
- tipo di processo di manutenzione  
- categoria di tipi di processo di manutenzione  
- cespite  
- tipo di cespite  

o una combinazione di tali elementi. Più selezioni vengono effettuate per lo stesso record, più specifica sarà l'impostazione.

1. Fare clic su **Gestione cespiti** > **Impostazione** > **Lavoratori** > **Addetti alla manutenzione preferiti**.

2. Fare clic su **Nuovo** per creare un nuovo record.

3. Iniziare creando un'impostazione di addetto o gruppo di addetti alla manutenzione predefinita che non presenta selezioni nei campi visualizzati nell'elenco precedente. Ciò significa che si esegue una selezione solo nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**. Nella figura seguente, viene visualizzato un esempio del primo record in cui "Richieste" è selezionato come gruppo di addetti alla manutenzione preferito.

>[!NOTE]
>L'impostazione predefinita verrà utilizzata durante la programmazione degli ordini di lavoro se nessun'altra combinazione più specifica corrisponde al contenuto dell'ordine di lavoro durante la programmazione dello stesso.

4. Ripetere il passaggio 2 per creare un nuovo record. Effettuare le selezioni necessarie, a seconda del livello di dettagli per l'addetto o il gruppo di addetti preferito. *Esempio:* nella figura seguente, nel sesto record, l'addetto alla manutenzione Shawn Richardson è selezionato come lavoratore preferito. Shawn sarà selezionato automaticamente durante la programmazione di un ordine di lavoro che include il cespite "CH-BP1-03-02" e il tipo di processo di manutenzione "Valutazione struttura", se è disponibile al momento della programmazione.

>[!NOTE]
>In genere, quando un addetto alla manutenzione preferito è selezionato durante la programmazione di un ordine di lavoro, Gestione cespiti esamina tutti i record **Addetti alla manutenzione preferiti** per determinare una corrispondenza possibile, sempre verificando dapprima la combinazione più specifica. Se non viene trovata alcuna corrispondenza, viene utilizzato il record "predefinito" con una selezione nel campo **Gruppo di addetti alla manutenzione preferito** o nel campo **Addetto alla manutenzione preferito**.


![Figura 1](media/02-work-order-scheduling.png)

È anche possibile impostare addetti alla manutenzione responsabili che possono essere selezionati quando viene creata una richiesta di intervento di manutenzione o un ordine di lavoro. In **Tutti gli ordini di lavoro** e **Tutte le richieste di intervento di manutenzione**, è possibile modificare la selezione, se necessario. Per ulteriori informazioni, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).

Durante la programmazione degli ordini di lavoro, vengono calcolati vari punteggi per determinare quali lavoratori devono completare i processi relativi a un ordine di lavoro (tali punteggi sono impostati in **Parametri di gestione cespiti** >  collegamento **Programmazione dell'ordine di lavoro**). Se due o più addetti alla manutenzione preferiti o addetti alla manutenzione responsabili ottengono lo stesso punteggio durante la programmazione dell'ordine di lavoro, un lavoratore viene selezionato in modo casuale. In caso contrario, è sempre il lavoratore con il punteggio massimo che viene scelto per completare un ordine di lavoro.

