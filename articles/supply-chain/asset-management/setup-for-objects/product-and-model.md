---
title: Produttori e modelli di cespiti
description: In questo articolo viene descritto come impostare i produttori di cespiti e i relativi modelli in Gestione cespiti.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b00cb62926f3a482ec655235b6e2f5880edbcd04
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016277"
---
# <a name="asset-manufacturers-and-models"></a>Produttori e modelli di cespiti

[!include [banner](../../includes/banner.md)]

 

In questo articolo viene descritto come impostare i produttori di cespiti e i relativi modelli in Gestione cespiti. I modelli possono essere correlati ai tipi di cespite.

## <a name="set-up-product-model-relations"></a>Impostare le relazioni prodotto-modello

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Produttore e modello**.
2. Selezionare **Nuovo** per creare un nuovo prodotto.
3. Nel campo  **Produttore** immettere un nome per il produttore di cespiti.
4. Nel campo **Descrizione** immettere una descrizione.
5. Nella Scheda dettaglio **Modelli**, selezionare **Aggiungi** per creare un modello di cespite che deve essere correlato al produttore di cespiti.
6. Nel campo **Modello** immettere un nome per il modello di cespite.
7. Nel campo **Descrizione** immettere una descrizione.
8. Nel campo **Tipo di cespite**, selezionare il tipo di cespite a cui il modello del produttore deve essere correlato.

    > [!NOTE]
    > È inoltre possibile impostare le relazioni per i tipi, i produttori e modelli di cespite nella ricerca **Tipi di cespite**. Per ulteriori informazioni, vedere [Tipi di cespite](../setup-for-objects/object-types.md).

    Nella Scheda dettaglio **Dettagli**, il campo **Modelli** mostra il numero di modelli di cespite impostati per il produttore di cespiti selezionato. Nel campo **Cespiti** viene visualizzato il numero di cespiti che utilizzano il produttore selezionato.
    
    Nel campo **Cespiti** viene visualizzato il numero di oggetti che utilizzano il modello del produttore.

> [!NOTE]
> Un tipo di cespite può avere nessuna relazione con modelli del produttore di cespiti, può essere correlato a un modello del produttore di cespiti o può essere correlato a più modelli del produttore di cespiti. Se un tipo di cespite è correlato ad almeno un modello del produttore, solo combinazioni impostate nella ricerca **Modello del produttore** possono essere selezionate nelle pagine di Gestione cespiti in cui una combinazione di tipo, di produttore e di modello di cespite può essere configurata. Queste pagine includono **Tutti i cespiti**, **Livelli di servizio cespiti**, **Valori predefiniti tipo di processo** e **Righe budget di manutenzione**. Se alcuni tipi di cespite non sono correlati ad alcun modello del produttore, solo i tipi di cespite e modelli del produttore che non hanno nessuna relazione con i tipi di cespite, vengono visualizzati nelle pagine.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Selezionare un produttore e un modello per un oggetto

1. Seleziona **Gestione cespiti** \> **_Cespiti_* \> **Tutti i cespiti**.
2. Nella colonna **Cespite**, selezionare il collegamento per il cespite. Viene visualizzata la pagina **Dettagli**.
3. Selezionare **Modifica**.
4. Nella Scheda dettaglio **Generale**, selezionare i valori nei campi **Modello** e **Produttore**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]