---
title: Impostare un magazzino
description: Questo argomento descrive come impostare un magazzino da utilizzare con un nuovo canale in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 67c0bb169bee8a7ea90edb4db7233111a8ee6e34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993655"
---
# <a name="warehouse-set-up"></a>impostare un magazzino


[!include [banner](includes/banner.md)]

Questo argomento descrive come impostare un magazzino da utilizzare con un nuovo canale in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

A ogni canale di Commerce è necessario associare un magazzino configurato. Le seguenti procedure forniscono la configurazione minima richiesta per impostare un magazzino per un canale di Commerce. Per ulteriori informazioni sull'impostazione di un magazzino, consultare [Panoramica della gestione magazzino](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).

## <a name="configure-a-warehouse-site"></a>Configurare un sito di magazzino

Prima di impostare un magazzino, è necessario configurare un sito di magazzino.

Per configurare un sito di magazzino, attenersi alla seguente procedura.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Siti**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Sito** immettere un valore.
1. Nel campo **Nome** immettere un valore.
1. Nella sezione **Generale**, impostare il **Fuso orario** appropriato.
1. Nella sezione **Indirizzi** immettere un indirizzo.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di sito di magazzino.

![Esempio di sito di magazzino](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Impostare un magazzino

Per impostare un magazzino, seguire questi passaggi.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Magazzino** immettere un valore.  Se si tratta di una mappatura 1:1 a un punto vendita, considerare l'utilizzo di un nome di punto vendita o di un nome di centro di distribuzione regionale.
1. Nel campo **Nome** immettere un valore.
1. Nell'elenco a discesa **Sito**, selezionare il sito di magazzino creato in precedenza.
1. Nel campo **Tipo** selezionare **Predefinito**.
    - Se si desidera impostare un **Magazzino di quarantena**, è necessario dapprima seguire questi passaggi per creare un magazzino aggiuntivo dove **Tipo** è impostato su **Quarantena**.
    - Se si desidera impostare un **Magazzino di transito**, è necessario dapprima seguire questi passaggi per creare un magazzino aggiuntivo dove **Tipo** è impostato su **Transito**.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="set-up-inventory-aisles"></a>Impostare le sezioni di magazzino

Per impostare le sezioni di magazzino, effettuare le seguenti operazioni.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Impostazione ubicazione \> Sezioni magazzino**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nell'elenco a discesa **Magazzino**, selezionare il magazzino creato in precedenza.
1. Nel campo **Sezione**, immettere un nome (ad esempio "Predef").
1. Nel campo **Nome**, immettere un nome (ad esempio "Sezione predefinita").
1. Nel riquadro azioni selezionare **Salva**.

## <a name="set-up-warehouse-inventory-locations"></a>Impostare le ubicazioni delle scorte magazzino

Per impostare le ubicazioni delle scorte magazzino per scorte standard, danneggiate e restituite, attenersi alla seguente procedura.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.
1. Selezionare il magazzino creato in precedenza.
1. Nel riquadro azioni selezionare **Modifica**.
1. Nel riquadro azioni, selezionare **Magazzino**, quindi selezionare **Ubicazione di magazzino**.
1. Nel Riquadro azioni selezionare **Nuovo**. Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.
    1. Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza. 
    1. Impostare **Aggiornamento manuale** su **Sì**
    1. Nella casella **Ubicazione**, immettere il nome del magazzino.
    1. Nel riquadro azioni selezionare **Salva**.
 1. Nel Riquadro azioni selezionare **Nuovo**.  Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.
    1. Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza.  
    1. Impostare **Aggiornamento manuale** su **Sì**
    1. Nella casella **Ubicazione**, immettere "Danneggiato".
    1. Nel riquadro azioni selezionare **Salva**.
 1. Nel Riquadro azioni selezionare **Nuovo**.  Per impostazione predefinita, nell'elenco a discesa **Magazzino** dovrebbe essere visualizzato il nuovo magazzino.
    1. Nella casella **Sezione**, immettere il nome della sezione specificata in precedenza. 
    1. Impostare **Aggiornamento manuale** su **Sì**
    1. Nella casella **Ubicazione**, immettere "Resi".
    1. Nel riquadro azioni selezionare **Salva**.
    
L'immagine seguente mostra l'impostazione dell'ubicazione delle scorte magazzino a San Francisco.

![Esempio di impostazione dell'ubicazione delle scorte](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Completare l'impostazione del magazzino

Per completare l'impostazione del magazzino, attenersi alla procedura seguente.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Magazzini**.
1. Selezionare il magazzino creato in precedenza.
1. Nel riquadro azioni selezionare **Modifica**.
1. Sotto **Gestione articoli e magazzino**:
    1. Impostare **Ubicazione predefinita entrata** sull'ubicazione predefinita creata sopra.
    1. Selezionare **Ubicazione predefinita uscita** sull'ubicazione predefinita creata sopra.
1. Sotto la sezione **Indirizzi**, immettere un indirizzo di magazzino.
1. Sotto la sezione **Al dettaglio**: 
    1. Nella casella **Ubicazione reso predefinita**, immettere l'ubicazione dei resi creata in precedenza.
    1. Impostare **Punto vendita** su **Sì**.
    1. Impostare **Peso** su **1,00**. 
    1. Nella casella **Dimensioni di immagazzinamento**, immettere l'ubicazione predefinita creata in precedenza.
1. Sotto la sezione **Magazzino**, impostare **Scorte fisiche negative** su **Sì**.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra i dettagli di un magazzino configurato.

![Esempio di magazzino configurato](media/warehouse-sample.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica gestione del magazzino](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Impostare un canale di vendita al dettaglio](channel-setup-retail.md)
    
[Impostare un canale online](channel-setup-online.md)

[Impostare un canale servizio clienti](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]