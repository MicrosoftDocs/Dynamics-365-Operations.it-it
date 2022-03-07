---
title: Addetti alla manutenzione responsabili
description: In questo argomento viene illustrato come impostare gli addetti alla manutenzione responsabili in Gestione cespiti.
author: johanhoffmann
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d68c9e6de6e9d62d1dea95c747b17900d343e7324857dcfc083d48e5c1006b0e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731297"
---
# <a name="responsible-maintenance-workers"></a>Addetti alla manutenzione responsabili

[!include [banner](../../includes/banner.md)]

 

Gli addetti alla manutenzione responsabili possono essere correlati ai tipi di cespite, ai cespiti, unità funzionali, le categorie di tipi di processi di manutenzione, ai tipi di processi di manutenzione, varianti di tipi di processi di manutenzione e alle mansioni qualificate. Possono essere utilizzati negli ordini di lavoro e nelle richieste di intervento di manutenzione per indicare una preferenza relativa agli addetti alla manutenzione che devono essere responsabile di un ordine di lavoro. (Tuttavia, questi addetti alla manutenzione non sono necessariamente gli lavoratori che vengano programmati per eseguire l'ordine di lavoro.) L'utilizzo di questa funzionalità è facoltativo. Ad esempio, la si può utilizzare per selezionare i lavoratori o i gruppi di lavoratori responsabili per determinati tipi o aree di lavoro.

Durante il ciclo di vita di un ordine di lavoro o una richiesta di intervento di manutenzione, gli addetti alla manutenzione responsabili possono essere modificati o aggiornati. Questa modifica o aggiornamento può essere correlato, ad esempio, a una modifica dello stato del ciclo di vita della richiesta di intervento di manutenzione o dell'ordine di lavoro.

L'impostazione della pagina **Addetti alla manutenzione responsabili** *non* viene utilizzata durante la programmazione degli ordini di lavoro.

> [!NOTE]
> In Gestione cespiti, è inoltre possibile impostare gli addetti alla manutenzione *preferiti* che possono essere assegnati agli ordini di lavoro durante la programmazione degli ordini di lavoro.

Prima di poter impostare gli addetti alla manutenzione responsabili, è necessario impostare i lavoratori e i gruppi di addetti alla manutenzione che devono essere disponibili per la selezione. Per informazioni su come impostare i lavoratori e i gruppi di addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-responsible-maintenance-workers"></a>Imposta gli addetti alla manutenzione responsabili

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Lavoratori** \> **Addetti alla manutenzione responsabili**.
2. Selezionare **Nuovo** per creare un record.
3. Creare innanzitutto un'impostazione predefinita di addetto alla manutenzione responsabile o di gruppo di addetti alla manutenzione responsabili, in cui impostate soltanto il campo **Gruppo di addetti alla manutenzione responsabili** e/o il campo **Lavoratore responsabile**. Lasciare vuoti i campi rimanenti. Questa impostazione predefinita verrà utilizzata durante la programmazione degli ordini di lavoro se nessun'altra combinazione più specifica corrisponde al contenuto dell'ordine di lavoro.

    > [!NOTE]
    > Durante la creazione di una richiesta di intervento di manutenzione, quando un addetto alla manutenzione responsabile o un gruppo di addetti alla manutenzione responsabili vengono resi disponibili per la selezione nella pagina **Tutte le richieste di intervento di manutenzione**, Gestione cespiti analizza tutti i record lavoratori responsabili di manutenzione per verificare la presenza di una corrispondenza possibile. Controlla sempre la combinazione più specifica per prima. In altre parole, Gestione cespiti controlla prima **Mansione qualificata** per trovare una corrispondenza. Se non trova corrispondenza, controlla **Variante tipo di processo di manutenzione**. Se non trova corrispondenza, controlla **Tipo di processo di manutenzione** e così via. Come si vede nel layout di questa pagina, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per trovare una corrispondenza (prima **Mansione qualificata**, poi **Variante tipo di processo di manutenzione** poi **Tipo di processo di manutenzione**, poi **Categoria tipo di processo di manutenzione**, poi **UNità funzionale**, quindi **Cespite** e infine **Tipo di cespite**). Se non viene trovata alcuna corrispondenza, il record predefinito senza selezioni in quei sette campi viene utilizzato.

Nella figura seguente è illustrato un esempio della pagina **Addetti alla manutenzione responsabili**.

![Pagina Addetti alla manutenzione responsabili.](media/08-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]