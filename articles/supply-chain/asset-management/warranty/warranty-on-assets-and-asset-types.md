---
title: Garanzie sui cespiti e sui tipi di cespite
description: In questo argomento viene descritto come impostare le garanzie sui cespiti e sui tipi di cespite in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 78ac93b1e681fca7d7eefd921f282a8496aa9d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245325"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garanzie sui cespiti e sui tipi di cespite

[!include [banner](../../includes/banner.md)]

 


In questo argomento viene descritto come impostare le garanzie sui cespiti e sui tipi di cespite in Gestione cespiti.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Impostare una garanzia su un tipo di cespite

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Tipi di cespite** \> **Tipi di cespite**.
2. Nel riquadro sinistro, selezionare il tipo di cespite a cui collegare un contratto di garanzia del fornitore e quindi selezionare **Valori predefiniti tipo di cespite**.
3. Nella Scheda dettaglio **Generale**, nel campo **Garanzia fornitore**, selezionare il contratto.

## <a name="set-up-a-warranty-on-an-asset"></a>Impostare una garanzia su un cespite

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti**.
2. Selezionare il cespite e quindi **Modifica**.
3. Nella Scheda dettaglio **Fornitore**, nella sezione **Garanzia fornitore**, nel campo **Garanzia**, selezionare il contratto di garanzia.
4. Nei campi **Data di inizio garanzia** e **Data di fine garanzia**, selezionare le date di inizio e fine.

    > [!IMPORTANT]
    > Se una data è selezionata nel campo **Data di inizio garanzia** in un ordine di lavoro, la garanzia diventa valida per l'ordine di lavoro in tale data. Quando si crea un ordine di lavoro, il campo **Data di inizio garanzia** viene impostato automaticamente alla data di creazione. Tuttavia, è possibile modificare la data di modo che corrisponda, ad esempio, alla data di inizio di un contratto di garanzia.
    >
    > ![Pagina Ordine di lavoro](media/02-warranty.png)

> [!NOTE]
> Quando si crea un ordine di lavoro per un cespite coperto da una garanzia del fornitore, se l'ordine di lavoro ha una data di inizio prevista durante il periodo di garanzia, si riceve una notifica sul contratto di garanzia. È quindi possibile annullare l'ordine di lavoro, come necessario.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]