---
title: Creare una gerarchia di navigazione nei canali
description: In questo articolo viene descritto come creare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: c3b28dd29bf444a75e5aa0a2a105d8a03fcacb0d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270266"
---
# <a name="create-a-channel-navigation-hierarchy"></a>Creare una gerarchia di navigazione nei canali


[!include [banner](includes/banner.md)]

In questo articolo viene descritto come creare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Una gerarchia di navigazione nei canali è utilizzata per raggruppare e organizzare prodotti in categorie di modo che i prodotti possano essere esaminati online o nel POS.

## <a name="create-a-channel-navigation-hierarchy"></a>Creare una gerarchia di navigazione nei canali

Per creare una gerarchia di navigazione nei canali, effettuare le seguenti operazioni.

1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Categorie di navigazione nei canali**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella casella **Nome** immettere un nome.
1. Nella casella **Descrizione** immettere una descrizione.
1. Selezionare **Crea**.
1. Nel riquadro azioni selezionare **Nuovo nodo di categoria** per creare un nodo principale.
1. Nella casella **Nome** immettere un nome.
1. Nella casella **Descrizione** immettere una descrizione.
1. Nella casella **Nome descrittivo** immettere un nome descrittivo.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di nodo principale.

![Esempio di nodo principale.](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a>Creare nodi di categoria di navigazione

Per creare eventuali nodi di categoria di navigazione aggiuntivi per rappresentare le categorie di prodotti nel canale, attenersi alla seguente procedura.

1. Nel pannello di navigazione, selezionare il nodo padre a cui aggiungere una categoria.
1. Nel riquadro Azioni selezionare **Nuovo nodo di categoria**.
1. Nella casella **Nome** immettere un nome.
1. Nella casella **Descrizione** immettere una descrizione.
1. Nella casella **Nome descrittivo** immettere un nome descrittivo.
1. Nella casella **Ordine di visualizzazione**, inserire un ordine di visualizzazione (facoltativo).
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di gerarchia di navigazione nei canali completata.

![Esempio di gerarchia dei canali.](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a>Aggiungere prodotti a nodi di categorie

Per aggiungere prodotti a nodi di categoria, attenersi alla seguente procedura.

1. Selezionare un nodo di categoria.
1. Sotto **Prodotti**, selezionare **Aggiungi**.
1. Trovare i nuovi prodotti che si desidera aggiungere utilizzando il numero o il nome di prodotto, quindi selezionare **OK**.
1. Nel riquadro azioni selezionare **Salva**.

> [!NOTE]
> L'aggiunta di prodotti a un nodo all'interno della gerarchia di navigazione nei canali non è sufficiente per visualizzare i prodotti in un canale selezionato in quanto i prodotti devono anche essere assortiti in un canale. Per ulteriori informazioni sugli assortimenti, vedere [Gestione dell'assortimento](assortments.md).

L'immagine seguente mostra un esempio di nodo con prodotti aggiunti.

![Prodotti aggiunti a un nodo di categoria.](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a>Aggiungere gruppi di attributi di prodotto a nodi di categoria

> [!NOTE]
> I gruppi di attributi devono essere creati prima di poterli aggiungere a un nodo in una gerarchia di navigazione nei canali.

Per aggiungere un gruppo di attributi di prodotto a un nodo di categoria, procedere come segue.

1. Selezionare un nodo di categoria.
1. Sotto **Gruppi di attributi del prodotto**, selezionare **Aggiungi**.
1. Trovare i gruppi di attributi che si desidera aggiungere, quindi selezionare **OK**.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di nodo con gruppi di attributi di prodotto aggiunti.

![Gruppi di attributi di prodotto in un nodo.](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare assortimenti](set-up-assortments.md)

[Gestire attributi e gruppi di attributi](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
