---
title: Creare una nuova gerarchia prodotti
description: In questo articolo viene descritto come creare un nuova gerarchia di prodotti in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
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
ms.openlocfilehash: 54a29381bb9231766d76b653904339d4bd60c257
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270129"
---
# <a name="create-a-new-product-hierarchy"></a>Creare una nuova gerarchia prodotti


[!include [banner](includes/banner.md)]

In questo articolo viene descritto come creare un nuova gerarchia di prodotti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

In Dynamics 365 Commerce sono supportati più canali di vendita al dettaglio. Questi canali di vendita al dettaglio includono punti vendita online, call center e punti vendita al dettaglio, noti anche come punti vendita fisici. Ogni canale di vendita al dettaglio può disporre di propri metodi di pagamento, gruppi di prezzi, POS, conti ricavi/spese e personale. È necessario impostare tutti questi elementi prima di creare un canale di vendita al dettaglio. 

Una gerarchia di prodotti di Commerce è utilizzata per definire la gerarchia di prodotti generale per l'organizzazione. È possibile utilizzare una gerarchia di prodotti di Commerce per il merchandising, la determinazione dei prezzi, le promozioni, il reporting e la pianificazione degli assortimenti. A un'organizzazione può essere assegnata una sola gerarchia di prodotti di Commerce.

## <a name="create-and-configure-a-product-hierarchy"></a>Creare e configurare una nuova gerarchia di prodotti

Per creare e configurare una gerarchia di prodotti Commerce, effettuare le seguenti operazioni.

1. Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Prodotti e categorie \> Gerarchia di prodotti Commerce**.
1. Se non esiste ancora alcuna gerarchia, nel **riquadro azioni**, selezionare **Nuovo** per creare la radice della gerarchia.
1. Sotto **Generale**:
    1. Nella casella **Nome** immettere un nome.
    1. Nella casella **Descrizione** immettere una descrizione.
    1. Nella casella **Nome descrittivo** immettere un nome descrittivo.
    1. Impostare **Attivo** su **Sì**.

## <a name="add-hierarchy-nodes"></a>Aggiungere nodi di gerarchia

Per aggiungere nodi di gerarchia, attenersi alla seguente procedura.

1. Nel riquadro Azioni selezionare **Modifica gerarchia di categorie**.
1. Selezionare il nodo principale a cui si desidera aggiungere un nuovo nodo, quindi selezionare **Nuovo nodo di categoria**.
1. Nella sezione **Generale** la sezione fornisce **Nome**, **Descrizione**, **Nome descrittivo** e **Parole chiave**.
1. Sotto **Generale**:
    1. Nella casella **Nome** immettere un nome.
    1. Nella casella **Descrizione** immettere una descrizione.
    1. Nella casella **Nome descrittivo** immettere un nome descrittivo.
    1. Nella casella **Parole chiave**, inserire le parole chiave pertinenti.
    1. Nella casella **Ordine di visualizzazione**, inserire un numero per l'ordine di visualizzazione (facoltativo).
1. Nel riquadro azioni selezionare **Salva**.
1. Ripetere i passaggi precedenti per aggiungere altri nodi.

L'immagine seguente mostra la creazione di un nuovo nodo di gerarchia di prodotti.

![Creare un gerarchia di prodotti.](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Altre impostazioni

I gruppi di attributi di categoria possono anche essere assegnati a ogni gruppo come richiesto.  

## <a name="additional-resources"></a>Risorse aggiuntive

[gerarchie commerce](retail-hierarchies.md)

[Gestire le categorie di prodotti e i prodotti](category-management-product-creation.md)

[Modificare l'ordinamento di visualizzazione per entità di merchandising](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
