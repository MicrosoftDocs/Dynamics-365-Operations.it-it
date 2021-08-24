---
title: Prodotti e categorie mancanti dopo la copia dell'ambiente
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando prodotti e categorie risultano mancanti dopo che un sito viene copiato tra ambienti o nello stesso ambiente.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 813289db052323fd87cd5a65184d71a580f1a3e0df9ea7d50a752e26b3962d1c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763622"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Prodotti e categorie mancanti dopo la copia dell'ambiente

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando prodotti e categorie risultano mancanti dopo che un sito viene copiato tra ambienti o nello stesso ambiente.

## <a name="description"></a>Descrizione

Dopo che un sito viene copiato da un ambiente a un altro o nello stesso ambiente, i prodotti e le categorie risultano mancanti nel sito. I prodotti e le categorie mancheranno nella vetrina di e-commerce e nella scheda **Prodotti** di Creazione di siti di Commerce.

## <a name="resolution"></a>Risoluzione

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Mappare il numero di unità operativa del canale a un sito appena copiato in Creazione di siti di Commerce

Per mappare il numero di unità operativa del canale a un sito appena copiato in Creazione di siti di Commerce, procedere come segue.

1. Selezionare il sito appena copiato.
1. Sotto **Impostazioni sito**, selezionare **Canali**.
1. Accanto al nome del canale, selezionare i puntini di sospensione (**...**), quindi selezionare **Modifica canale punto vendita online**.
1. Nella finestra di dialogo **Modifica canale punto vendita online**, selezionare il canale da mappare al sito appena copiato, quindi selezionare **OK**.
1. Seleziona **Salva e pubblica**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Associare un sito Dynamics 365 Commerce a un canale online](../associate-site-online-store.md)
