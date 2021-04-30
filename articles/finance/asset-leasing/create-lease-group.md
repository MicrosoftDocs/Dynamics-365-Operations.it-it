---
title: Creare un gruppo di leasing
description: In questo argomento viene spiegato come configurare i gruppi di leasing. I gruppi di leasing sono obbligatori per creare nuovi leasing.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 88a49e4db868078fd05875df33ca5727363aaa18
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881230"
---
# <a name="create-a-lease-group"></a>Creare un gruppo di leasing

[!include [banner](../includes/banner.md)]

In questo argomento viene spiegato come configurare i gruppi di leasing. I gruppi di leasing sono obbligatori per creare nuovi leasing. I libri di leasing sono associati a ogni gruppo di leasing. I libri di leasing determinano i libri predefiniti che devono essere creati per ogni leasing. Puoi assegnare account specifici a un gruppo di leasing nella pagina **Parametri di registrazione del leasing**.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Crea un libro di leasing e aggiungi un gruppo di leasing

1. Vai a **Leasing cespiti \> Imposta \> Gruppi di leasing**.
2. Nel riquadro azioni seleziona **Nuovo** per aggiungere un gruppo di leasing. Una riga viene aggiunta alla griglia.
3. Sulla nuova riga, nel campo **Gruppo di leasing**, immetti un valore.
4. Nel campo **Descrizione** immettere un valore.

Le informazioni appena inserite vengono aggiunte al campo **Gruppo di leasing** nella pagina **Aggiungi leasing**.

## <a name="associate-a-book-with-a-lease-group"></a>Associare un libro a un gruppo di leasing

Dopo aver creato i gruppi di leasing, puoi assegnare libri a ciascun gruppo. Quando crei un leasing e lo assegni a un gruppo di leasing, il sistema crea una serie di scadenziari per ogni libro associato a quel gruppo di leasing.

> [!NOTE]
> I libri devono essere configurati prima di poter essere assegnati a un gruppo di leasing.

1. Vai a **Leasing cespiti \> Imposta \> Gruppo di leasing**.
2. Seleziona un gruppo di leasing, quindi seleziona **Libri**.
3. Seleziona **Nuovo**, quindi, nel campo **Tipo di libro**, seleziona il libro da assegnare al gruppo di leasing. Puoi assegnare più libri a un gruppo di leasing se un leasing deve essere contabilizzato in modi diversi.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
