---
title: Configurare un canale per utilizzare una gerarchia di navigazione nei canali
description: In questo argomento viene descritto come configurare un canale per utilizzare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7b5041d35d310125c314ab2cb77d3cc40cdb7113
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413360"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Configurare un canale per utilizzare una gerarchia di navigazione nei canali


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come configurare un canale per utilizzare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Le gerarchie di navigazione nei canali organizzano i prodotti in categorie di modo che i prodotti possano essere esaminati in un sito di e-commerce o nel POS. I canali di vendita al dettaglio e online devono essere configurati con gerarchie di navigazione nei canali.

## <a name="configure-the-channel"></a>Configurare il canale

Per configurare un canale allo scopo di utilizzare una gerarchia di navigazione nei canali, attenersi alla seguente procedura.

1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Categorie canale e attributi del prodotto**.
1. Selezionare il canale da configurare.
1. Nel riquadro azioni, selezionare **Imposta metadati di attributi**.
1. Nell'elenco a discesa **Gerarchia di categorie**, selezionare la gerarchia di navigazione nei canali appropriata.
1. Nel riquadro azioni selezionare **Salva**.
1. Sotto **Gruppo di attributi**, aggiungere tutti i gruppi di attributi che saranno attributi globali per tutti i nodi.

L'immagine seguente mostra come configurare un canale allo scopo di utilizzare una gerarchia di navigazione nei canali.

![Esempio di configurazione di un canale](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Imposta metadati di attributi

L'impostazione dei metadati di attributi consentirà la configurazione degli attributi in ogni nodo.

Per impostare i metadati di attributi, procedere come segue.

1. Nel riquadro azioni, selezionare **Imposta metadati di attributi**.
1. Per ciascun nodo selezionare **Attributi del prodotto del canale**.
1. Impostare **Mostra attributo sul canale** su **Sì** e **Ridefinizione possibile** su **Sì**, per abilitare raffinatori su quel canale.
1. Dopo aver configurato ciascun nodo come desiderato, nel **Riquadro azioni**, selezionare il pulsante **Salva** per salvare.
1. Selezionare la **X** nell'angolo in alto a destra per uscire da questa schermata e ritornare alla pagina **Categorie canale e attributi del prodotto**.

L'immagine seguente mostra un set di esempi di attributi del prodotto del canale configurati in un nodo di categoria del canale.

![Attributi del canale in un nodo di categoria del canale](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Pubblicare le modifiche

Affinché le modifiche diventino effettive, è necessario pubblicarle.

Per pubblicare le modifiche, attenersi alla procedura riportata di seguito.

1. Nel riquadro azioni, selezionare **Pubblica aggiornamenti canale**.
1. Nel riquadro **Pubblica aggiornamenti canale**, selezionare **OK**.

L'immagine seguente mostra come pubblicare gli aggiornamenti dei canali.

![Pubblica aggiornamenti canale](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare una gerarchia di navigazione nei canali](create-channel-hierarchy.md)


