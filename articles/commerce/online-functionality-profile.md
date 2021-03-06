---
title: Creare un profilo funzionalità online
description: In questo argomento viene descritto come creare un profilo funzionalità online in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: be78b92858979b8bb009a4699eff96379ef7cef3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791104"
---
# <a name="create-an-online-functionality-profile"></a>Creare un profilo funzionalità online

[!include [banner](includes/banner.md)]

In questo argomento viene presentata una panoramica sulla configurazione di un profilo funzionalità online per Microsoft Dynamics 365 Commerce.

Il profilo funzionalità online fornisce varie impostazioni utilizzate per canali online. Ogni canale online deve specificare un profilo funzionalità online.

## <a name="create-an-online-functionality-profile"></a>Creare un profilo funzionalità online

La seguente procedura spiega come creare un profilo funzionalità online nell'app Commerce Headquarters.

1. Nel pannello di navigazione, andare a **Moduli \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Profilo**, immettere un ID per il profilo.
1. Nel campo **Descrizione**, immettere un valore per il profilo ("Adventure Works Profile" nell'immagine di esempio seguente).
1. Nella sezione **Funzioni**, modificare le impostazioni **CARRELLO**, **CLIENTI DI VENDITA AL DETTAGLIO** o **CHECKOUT** come necessario.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra un esempio di profilo funzionalità online.
  
![Esempio di profilo funzionalità online](media/online-functionality-profile.png)

## <a name="functions"></a>Funzioni

- **Aggrega prodotti**: se abilitata, questa funzione consente al carrello di aggiornare la quantità quando lo stesso articolo viene aggiunto più volte.
- **Consenti checkout senza pagamenti**: se abilitata, questa funzione gestisce lo scenario in cui gli articoli aggiunti al carrello hanno un prezzo $0,00.
- **Crea cliente in modalità asincrona**: questa è un'impostazione legacy applicabile a canali di e-commerce di terze parti e non è applicabile al sito di e-commerce di Dynamics 365.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Impostare un canale online](channel-setup-online.md)

[Impostare un canale di vendita al dettaglio](channel-setup-retail.md)

[Impostare un canale servizio clienti](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
