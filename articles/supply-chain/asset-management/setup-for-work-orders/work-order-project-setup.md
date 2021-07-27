---
title: Impostazione del progetto di ordine di lavoro
description: In questo argomento viene descritta l'impostazione del progetto di ordine di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 19cdc33fcc9d1293b235facbaffd1ccf62875217
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360055"
---
# <a name="work-order-project-setup"></a>Impostazione del progetto di ordine di lavoro

[!include [banner](../../includes/banner.md)]

 

Nel modulo **Gestione cespiti**, una relazione progetti è necessaria per ogni processo di ordine di lavoro. Il progetto associato a un processo di ordine di lavoro consente di tenere traccia dei costi in vari progetti correlati a Gestione cespiti, ad esempio progetti di manutenzione interni, progetti di manutenzione dei servizi e progetti di investimento. 

## <a name="project-setup-for-a-work-order-job"></a>Impostazione del progetto per un processo di ordine di lavoro

Quando si crea un processo di ordine di lavoro in un ordine di lavoro, l'impostazione del progetto nel modulo **Gestione progetti e contabilità** e l'impostazione del progetto di ordine di lavoro nel modulo **Gestione cespiti** determina il modo in cui i progetti possono essere utilizzati per il controllo dei costi nel cespite selezionato in quel processo di ordine di lavoro. In questa sezione vengono descritte le parti seguenti dell'impostazione del progetto utilizzata per un ordine di lavoro, ovvero il progetto principale (ID di progetto), il tipo di progetto, le attività di progetto e dimensioni finanziarie:

- Quando si crea un processo di ordine di lavoro in un ordine di lavoro, un ID di progetto univoco e un'attività di progetto correlata vengono creati automaticamente. Tuttavia, se diversi processi di ordine di lavoro in un ordine di lavoro includono lo stesso cespite, lo stesso ID di progetto viene utilizzato per tutti tali processi. In altre parole un ID di progetto viene creato per ogni cespite in un ordine di lavoro.

    - Il progetto principale (ID di progetto) per un processo di ordine di lavoro è indicato nell'impostazione di tale progetto (per ulteriori informazioni sull'impostazione del progetto principale, vedere la sezione successiva). Ad esempio, se si associa un cliente o un'unità funzionale a uno specifico progetto principale, il progetto principale viene utilizzato ogni volta che si creano ordini di lavoro per quel cliente o quell'unità funzionale. Se non si un esegue una correlazione tra uno specifico ID di progetto e un'unità funzionale, verrà utilizzato il progetto principale pertinente successivo nell'impostazione del progetto di ordine di lavoro.
    - Un tipo di progetto è necessario per ogni ID di progetto. Il tipo di progetto è indicato nell'impostazione del gruppo di progetti (per ulteriori informazioni sull'impostazione del gruppo di progetti, vedere la sezione successiva). Se non viene rilevata alcuna corrispondenza nell'impostazione del gruppo di progetti, questa viene utilizzata nel progetto principale.
    - L'impostazione per richiedere attività di progetto nelle previsioni e nei giornali di registrazione viene copiata dal progetto principale al progetto di ordine di lavoro. Se le opzioni **Ora**, **Spese** e **Articolo** sono impostate su **Sì** per il progetto utilizzato come progetto principale, un'attività di progetto è obbligatoria nelle previsioni e nei giornali di registrazione Per accedere a queste opzioni, selezionare **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti** e quindi selezionare il progetto utilizzato come progetto principale. Le opzioni sono disponibili nella sezione **Richiedi attività su giornali di registrazione** nella Scheda dettaglio **Impostazione**.

- Le dimensioni finanziarie vengono copiate dal cespite e unite al progetto principale.

Nella sezione successiva viene descritto come impostare progetti principali e gruppi di progetti. Il progetto principale e i gruppi principali vengono utilizzati per controllare gli ordini di lavoro. Sono utilizzati anche per la creazione di report sugli ordini di lavoro.

## <a name="set-up-work-order-projects"></a>Impostare progetti di ordine di lavoro

Prima di iniziare a creare ordini di lavoro, è necessario impostare progetti di ordine di lavoro. La pagina **Impostazione del progetto di ordine di lavoro** (**Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Impostazione progetto**) contiene due schede: **Progetto principale** e **Gruppo di progetti**.

Nella scheda **Progetto principale**, è possibile impostare relazioni di progetto da utilizzare se alcun progetto è impostato nel cespite selezionato nel processo di ordine di lavoro. Un'impostazione di progetto principale non è necessaria se la società utilizza progetti relativi ai cespiti. È pertiente solo se si desidera utilizzare progetti di ordine di lavoro anziché progetti relativi ai cespiti. In questo caso, è necessario impostare almeno un progetto principale.

Nella scheda **Gruppo di progetti**, è possibile impostare gruppi di progetti associabili a tipi di ordine di lavoro, tipi di cespite e cespiti.

I gruppi di progetti possono essere utilizzati per creare categorie specifiche (gruppi) utilizzate per il controllo dei costi. Ad esempio, creando gruppi di progetti per specifici tipi di cespite o tipi di ordine di lavoro, è possibile effettuare una tracciatura dettagliata dei costi di gestione per tipo.

I gruppi di progetti non sono obbligatori. Se non si impostano gruppi di progetti, il progetto principale viene utilizzato per determinare il gruppo di progetti e un progetto secondario viene creato dal gruppo di progetti del progetto principale.

L'impostazione consente l'integrazione completa con il modulo **Gestione progetti e contabilità**. Di conseguenza, è possibile tenere traccia dei costi relativi agli ordini di lavoro nei progetti correlati. La procedura seguente descrive l'impostazione per i progetti di ordine di lavoro.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Impostazione progetto**.
2. Nella scheda **Progetto principale** selezionare **Aggiungi**.
3. Nei campi **Tipo di ordine di lavoro**, **Unità funzionale**, **Tipo di cespite** e **Cespite**, selezionare i valori necessari. Per ogni riga aggiunta, è possibile impostare uno o più campi. Il numero di campi impostati determina la combinazione utilizzata quando un ID di progetto viene selezionato in Gestione cespiti. 

    Se si seleziona un'unità funzionale, le ubicazioni secondarie correlate vengono incluse automaticamente. Se si seleziona un cespite, è possibile creare ulteriori righe per l'impostazione di progetti di ordine di lavoro per lo stesso cespite, ma è possibile selezionare progetti differenti per quel cespite.

4. Nel campo **ID progetto**, selezionare il progetto che deve essere correlato all'impostazione creata nel passaggio 3.
5. Se l'impostazione di progetto deve essere valida solo per un periodo limitato, selezionare una data di fine nel campo **Data di fine**. In caso contrario, selezionare **Nessuno**.

    Per impostazione predefinita, la data di inizio corrisponde alla data alla quale si aggiunge il progetto di ordine di lavoro alla pagina. Questa data determinata dal campo **Data di inizio validità**, che è nascosto per impostazione predefinita. Per visualizzare il campo **Data di inizio validità**, selezionare **Visualizza** \> **Tutto**. È quindi possibile utilizzare il campo **Data di inizio validità** insieme al campo **Data di fine** per impostare un periodo di validità limitato per il progetto di ordine di lavoro.

    ![Pagina Impostazione del progetto dell'ordine di lavoro.](media/17-setup-for-work-orders.png)

6. Nella scheda **Gruppo di progetti** selezionare **Aggiungi**.
7. Nel campo **Tipo di ordine di lavoro** selezionare un tipo di ordine di lavoro.
8. Se l'associazione del gruppo di progetti deve essere più specifica, selezionare un tipo di cespite nel campo **Tipo di cespite** o un cespite nel campo **Cespite**.
9. Nel campo **Gruppo di progetti**, selezionare il gruppo di progetti che deve essere correlato al tipo di ordine di lavoro. Ad esempio, un tipo di ordine di lavoro denominato **Manutenzione preventiva** può essere associato a un gruppo di progetti denominato **Manut prev** o **Interno**. In alternativa, un tipo di ordine di lavoro **Investimento** utilizzato per gli ordini di lavoro correlati agli investimenti e i cespiti possono essere associati a un gruppo di progetti denominato **Invest** o **Investimento**.
10. Selezionare **Salva**.

![Pagina Impostazione del progetto dell'ordine di lavoro, Aggiungi ordine di lavoro.](media/18-setup-for-work-orders.png)

> [!NOTE]
> Ogni volta che si crea una riga di ordine di lavoro, Gestione cespiti ricerca un gruppo di progetti che deve essere correlato al progetto di processo di ordine di lavoro. La ricerca è basata sull'impostazione descritta in questo argomento. Ogni gruppo di progetti presenta un tipo di progetto correlato. I gruppi di progetti con il tipo di progetto **Tempistica e materiali** o **A prezzi fissi** sono validi solo per i cespiti associati a un conto cliente.
>
> Per i progetti principali e i gruppi di progetti, quando il sistema seleziona il progetto di ordine di lavoro o il gruppo di progetti disponibile, la selezione è basata sui record creati utilizzando la procedura precedente. Gestione cespiti controlla i record associati al progetto di ordine di lavoro per determinare se esiste una corrispondenza possibile. Controlla sempre la combinazione più specifica per prima. In altre parole, per il progetto di ordine di lavoro principale, Gestione cespiti cerca una possibile corrispondenza per il campo **Cespite**. Se non trova alcuna corrispondenza, ne cerca una per il campo **Tipo di cespite**. Se non trova alcuna corrispondenza anche in questo caso, ne cerca una per il campo **Unità funzionale** e così via. Come si vede nel layout della pagina **Impostazione del progetto di ordine di lavoro**, questo comportamento indica che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza. Se non viene trovata alcuna corrispondenza, viene utilizzato il record predefinito dove solo un ID di progetto è selezionato. Il processo per l'individuazione del gruppo di progetti correlato è simile. Gestione cespiti cerca dapprima una possibile corrispondenza per il campo **Cespite**, quindi per il campo **Tipo di cespite** e infine per campo **Tipo di ordine di lavoro**. Se non viene trovata alcuna corrispondenza, viene utilizzato il record predefinito dove solo un gruppo di progetti è selezionato.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]