---
title: 'Snapshot di aging cliente '
description: In questo argomento vengono fornite informazioni sugli snapshot di aging cliente. Uno snapshot di aging calcola i saldi con aging per un gruppo di clienti in un determinato momento.
author: JodiChristiansen
ms.date: 05/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b88d3fe97d14d3e2f766367de501148063582000
ms.sourcegitcommit: 16376a301a0f121f384d77f9976638f701f8e88e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "6123364"
---
# <a name="customer-aging-snapshots"></a>Snapshot di aging cliente 

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sugli snapshot di aging cliente. Uno snapshot di aging calcola i saldi con aging per un gruppo di clienti in un determinato momento. Puoi creare record di snapshot di aging per tutti i clienti o per i clienti di un pool di clienti.

Le informazioni dello snapshot di aging sono visualizzate nella pagina elenco **Saldi con aging** e nella pagina **Riscossioni**. Per poter utilizzare la pagina elenco **Saldi con aging**, devi innanzitutto creare uno snapshot di aging. La pagina elenco elenca solo i clienti per i quali è stato creato uno snapshot di aging.

L'area di lavoro **Crediti e riscossioni cliente** mostra anche l'aging del cliente. Per ulteriori informazioni, vedi [Contenuto Power BI per la gestione di crediti e riscossioni](credit-collections-power-bi.md).

> [!NOTE]
> Per ridurre il tempo necessario per creare uno snapshot di aging, attiva la funzionalità **Miglioramento delle prestazioni di aging cliente** nell'area di lavoro **Gestione funzionalità**. Tuttavia, non utilizzare i pool di clienti quando questa funzionalità è attivata. Se un pool di clienti è selezionato, la funzionalità non funzionerà, ma puoi comunque creare uno snapshot di aging.

Quando crei uno snapshot di aging del cliente, utilizza i seguenti campi per inserire le informazioni sullo stesso:

- **Definizione periodo di aging** - Seleziona la definizione del periodo di aging per il snapshot di aging. Puoi avere uno snapshot di aging per ogni definizione del periodo di aging. Lo snapshot di aging e la definizione del periodo di aging devono essere creati separatamente.
- **ID pool** - Questo campo è facoltativo. Puoi utilizzare un pool per definire l'insieme di clienti da elaborare nello snapshot di aging. Se selezioni un pool di clienti in questo campo, uno snapshot di aging viene creato solo per i conti cliente appartenenti a tale pool di clienti. Il pool di clienti selezionato deve essere di tipo **Snapshot di aging**. Se lasci vuoto questo campo, viene creata uno snapshot di aging per tutti i conti cliente.

    > [!NOTE]
    > Se la funzionalità **Miglioramento delle prestazioni di aging cliente** è attivata, non selezionare un pool di clienti.

- **Criteri** - L'aging dello snapshot di aging viene eseguito in base alla data selezionata:

    - **Data transazione** - l'aging di ogni transazione viene eseguito in base alla relativa data di transazione.
    - **Data di scadenza** - L'aging di ogni transazione viene eseguito in base alla relativa data di scadenza.
    - **Data documento** - L'aging di ogni transazione viene eseguito in base alla relativa data documento.

- **Aging a partire dal** - Seleziona la data da utilizzare nel campo **Data corrente** per lo snapshot di aging. I periodi di aging vengono quindi calcolati in base a tale data. 

    - **Data odierna** - Utilizza la data di sistema. Selezione questa opzione se si è impostata l'esecuzione dell'elaborazione in un batch ricorrente. Quindi, ogni volta che viene eseguito il batch, viene utilizzata la data di sistema di quella esecuzione.
    - **Data selezionata** - Utilizza una data specificata. Se selezioni questa opzione, devi immettere una data di aging.

    Ad esempio, il periodo di aging corrente è 30 giorni. Se selezioni **Data odierna** in questo campo, il periodo di aging corrente inizia dalla data odierna e include i 29 giorni precedenti. Se selezioni **Data selezionata** e immetti una data, il periodo di aging corrente inizia dalla data specificata e include i 29 giorni precedenti.

- **Aggiorna stato riscossione** - Imposta questa opzione su **Sì** per aggiornare lo stato di riscossione delle transazioni nella pagina **Collezioni** da **Promessa di pagamento** a **Promessa di pagamento non mantenuta** se la data di aging è successiva alla data nel campo **Promesse di pagamento**. Imposta questa opzione su **No** per lasciare invariato lo stato di riscossione nella pagina **Riscossioni**.
- **Includi clienti con saldo zero** - Imposta questa opzione su **Sì** per includere tutti i clienti, indipendentemente dal loro saldo. Se includi tutti i clienti, ti consigliamo di attivare la funzionalità **Miglioramento delle prestazioni di aging cliente** e di non utilizzare pool di clienti. Imposta questa opzione su **No** per includere solo i clienti che hanno un saldo. Questa impostazione consente di migliorare le prestazioni, perché i clienti che non dispongono di un saldo vengono ignorati.
- **Intervallo società** - Nella scheda **Intervallo società**, seleziona le persone giuridiche (società) da includere nello snapshot di aging. È possibile selezionare solo le persone giuridiche impostate per i pagamenti centralizzati. Le transazioni delle persone giuridiche selezionate vengono quindi incluse nei periodi di aging per i clienti che hanno lo stesso ID parte in tutte quelle persone giuridiche. Gli importi in valuta vengono convertiti nella valuta della persona giuridica a cui sei connesso quando crei lo snapshot di aging.

Si consiglia di pianificare questo processo in modo per l'esecuzione in batch.

> [!NOTE]
> Per migliorare le prestazioni del batch durante la creazione di snapshot di aging, immetti un numero nel campo **Numero massimo di attività batch** nella Scheda dettaglio **Valori predefiniti riscossioni** della scheda **Riscossioni** della pagina **Parametri contabilità clienti**. Nel campo **Saldi con aging cliente**, ti consigliamo di iniziare con il valore predefinito **100** e quindi regola il valore per ottimizzare l'elaborazione per la tua situazione.

