---
title: Configurare i tipi di spesa
description: Nell'articolo viene descritto come configurare i tipi di spesa in Leasing cespite.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseExpenseTypeTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9978041059437d5d3556236c7ac02c00db93f933
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908040"
---
# <a name="set-up-expense-types"></a>Configurare i tipi di spesa

[!include [banner](../includes/banner.md)]

Nell'articolo viene descritto come configurare i tipi di spesa in Leasing cespite. I costi che non sono rappresentati dallo scadenziario dei pagamenti sono noti come *costi di spesa*. Esempi di questi costi includono le tasse sulla proprietà, i costi di manutenzione delle aree comuni e le spese di assicurazione.

## <a name="add-an-administrative-expense-type"></a>Aggiungere un tipo di spesa amministrativa

1. Vai a **Leasing cespiti \> Imposta \> Tipi di spesa**.
2. Selezionare **Nuovo**.
3. Nei campi appropriati, inserisci il nuovo tipo di spesa e una descrizione.

## <a name="assign-accounts-to-administrative-costs"></a>Assegnare i conti ai costi amministrativi

Successivamente, è consigliabile associare i conti ai tipi di spesa. Questi conti verranno addebitati quando vengono registrati i movimenti del programma spese. Il conto di contropartita è specificato nelle righe **Piano di pagamento dei costi di esecuzione** su ogni leasing.

1. Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.
2. Nella scheda **Conti**, nella Scheda dettaglio **Costi di esecuzione**, nel campo **Tipo di spesa**, seleziona il tipo di spesa.
3. Selezionare **Aggiungi**.
4. Nel campo **Tipo di libro** seleziona il tipo di libro da collegare ai costi amministrativi.

    > [!NOTE]
    > È possibile collegare più tipi di libri allo stesso conto spese.

5. Nel campo **Codice conto**, specifica a quali leasing deve essere applicato il libro:

    - **Tutti**: applica il libro a tutti i leasing.
    - **Gruppo**: applica il libro a un gruppo specifico di leasing.
    - **Tabella**: applica il libro a leasing specifichi.

6. Se hai selezionato **Gruppo** o **Tabella** nel campo **Codice conto**, seleziona un numero di conto o numero di gruppo nel campo **Numero conto/gruppo**.
7. Nei campi appropriati seleziona il conto principale del leasing finanziario e il conto principale del leasing operativo.

Dopo aver completato questi passaggi, puoi aggiungere le spese tramite le righe **Piano di pagamento dei costi di esecuzione** nella pagina **Dettagli leasing** di un leasing selezionato. In alternativa, puoi aggiungere le spese quando crei un nuovo leasing.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
