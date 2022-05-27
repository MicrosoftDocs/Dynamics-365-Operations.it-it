---
title: Creare registrazioni prima nota mensili in un batch
description: Questo argomento spiega come creare registrazioni prima nota in un batch per aumentare l'efficienza quando vengono registrate le spese di leasing mensili.
author: moaamer
ms.date: 08/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cd282ab04312a3ed1821160146b86db902906f3b
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714063"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a>Creare registrazioni prima nota mensili in un batch

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Questo argomento spiega come creare registrazioni prima nota in un batch per aumentare l'efficienza quando vengono registrate le spese di leasing mensili. L'elaborazione batch può essere utilizzata per creare registrazioni prima nota da più scadenziari. Queste registrazioni prima nota possono includere canoni di leasing, ammortamento delle passività, ammortamento degli Asset ROU e spese per i costi esecutivi. È inoltre possibile utilizzare l'elaborazione batch per eseguire il riconoscimento iniziale di più leasing contemporaneamente o per creare rettifiche di transizione per più leasing contemporaneamente.

Per configurare un processo batch o per elaborare fatture di pagamento, ammortamenti o interessi per più leasing, vai a **Leasing cespite \> Periodico \> Creazione di un giornale in batch**. Nella finestra di dialogo visualizzata, puoi selezionare lo scadenziario da cui creare le scritture contabili. Puoi inoltre specificare se il processo batch deve essere eseguito per entità, gruppi di leasing o libri di leasing specifici.

> [!NOTE]
> Le transazioni successive, come piani di ammortamento delle passività, pagamenti, ammortamenti e spese, verranno contabilizzati solo dopo la registrazione iniziale per i leasing corrispondenti.
>
> Le scritture contabili vengono create, ma non verranno registrate finché non selezioni il comando **Esegui**.

Per registrare il giornale di registrazione iniziale in una data diversa dalla data di inizio del leasing, seleziona **Assegnazione data di registrazione riconoscimento iniziale**. Verrà visualizzato un campo **Data** che ti consente di specificare la data di registrazione corretta.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
