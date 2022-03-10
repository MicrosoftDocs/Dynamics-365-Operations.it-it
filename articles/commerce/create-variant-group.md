---
title: Creare un gruppo di varianti
description: In questo argomento viene descritto come creare un gruppo di varianti di dimensioni, stile o colore per un prodotto in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 49e6860fa22bbfba8b86a8243fa29b831e22b489d967a45310648e5debd7512b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749933"
---
# <a name="create-a-variant-group"></a>Creare un gruppo di varianti


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un gruppo di varianti di dimensioni, stile o colore per un prodotto in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Dynamics 365 Commerce supporta molteplici varianti per i prodotti. È ideale per impostare gruppi di varianti per diverse categorie di prodotti. Ad esempio, è possibile creare un gruppo di dimensioni per magliette con taglie XS, S, M, L e XL, oppure un gruppo di colori per includere tutti i colori disponibili di un prodotto. I gruppi di varianti devono essere aggiunti prima dell'aggiunta dei prodotti.

In questo argomento, verrà creato e configurato un gruppo di dimensioni. Procedure simili possono essere utilizzate per aggiungere e configurare gruppi di stili e gruppi di colori.

## <a name="create-a-size-group"></a>Creare un gruppo di dimensioni

Per creare un gruppo di dimensioni, completare i passaggi seguenti.
 
1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Gruppi di varianti \> Gruppi di dimensioni**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella casella **Gruppo di dimensioni**, immettere un nome per il gruppo di dimensioni.
1. Immettere una descrizione appropriata nella casella **Descrizione**.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="add-attributes-to-the-size-group"></a>Aggiungere attributi al gruppo di dimensioni

Per aggiungere attributi a un gruppo di dimensioni, effettuare le operazioni indicate di seguito.

1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Gruppi di varianti \> Gruppi di dimensioni**.
1. Nel pannello di navigazione, selezionare un gruppo di dimensioni.
1. Sotto **Righe gruppo di dimensioni**, selezionare **Aggiungi**.
1. Nella casella **Dimensioni**, immettere una stringa che rappresenta la dimensione (ad esempio, "XL").
1. Nella casella **Nome dimensione**, inserire un nome per la dimensione (ad esempio, "Extra Large").
1. Nella casella **Peso rifornimento**, inserire un numero che rappresenta il peso di rifornimento.
1. Nella casella **Numero nel codice a barre**, inserire un numero che rappresenta il codice a barre.
1. Nella casella **Ordine di visualizzazione**, inserire un numero che rappresenta l'rdine di visualizzazione.
1. Al termine dell'aggiunta delle dimensioni, selezionare **Salva** nel riquadro azioni.

L'immagine seguente mostra un esempio di un gruppo di dimensioni per "taglie di camicie casual".

![Creare un gruppo di dimensioni.](media/create-variant-group.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica delle informazioni sul prodotto](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Configurare prodotti di vendita al dettaglio](set-up-retail-products.md)

[Dimensioni prodotto](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]