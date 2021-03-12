---
title: Gerarchie Commerce
description: Questo articolo descrive le gerarchie in Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: OMHierarchyManager, EcoResCategoryHierarchyFactbox
audience: Application User
ms.reviewer: josaw
ms.custom: 15851
ms.assetid: dfa11d41-2a0c-4cde-99b6-058c49176c94
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 94b391ab5028f76debb75d25ac9469e25361cb12
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979618"
---
# <a name="commerce-hierarchies"></a>Gerarchie Commerce

[!include [banner](includes/banner.md)]

Questo articolo descrive le gerarchie in Dynamics 365 Commerce.

È possibile creare una gerarchia di categorie per organizzare i prodotti venduti tramite i canali. È possibile utilizzare le gerarchie di prodotti per classificare o raggruppare prodotti. Tali prodotti possono essere utilizzati per creare gli assortimenti prodotti e i programmi fedeltà dei clienti. È inoltre possibile assegnare al prodotto attributi e proprietà, assegnare una struttura del prezzo, includere i prodotti nelle promozioni prodotto e utilizzare i prodotti per la dichiarazione. È possibile creare una gerarchia di categorie per rappresentare tutti i prodotti e le categorie nell'organizzazione, quindi utilizzare tale gerarchia di categorie per più scopi. In alternativa, è possibile creare più gerarchie di categorie per scopi specifici, quali promozioni prodotto. Quando si crea una gerarchia di prodotti, è necessario assegnare un tipo di gerarchia di categorie per identificare lo scopo della gerarchia di categorie. Ad esempio, quando si esplorano i prodotti per categoria online o punto di vendita (POS), viene fatto riferimento solo alle gerarchie di prodotti alle quali è stato assegnato il tipo **Gerarchia di navigazione di Commerce**.

## <a name="hierarchy-types"></a>Tipo di gerarchie

Nella seguente tabella vengono riportati i tipi di gerarchie di categorie disponibili e lo scopo generale di ogni tipo.

| Tipo di gerarchia di categorie       | Scopo |
|-------------------------------|---------|
| Gerarchia prodotti      | Utilizzare questo tipo di gerarchia per definire la gerarchia di prodotti generale per l'organizzazione. È possibile utilizzare questo tipo di gerarchia per la vendita, la determinazione dei prezzi, le promozioni, il reporting e la pianificazione degli assortimenti. A questo tipo di gerarchia può essere assegnata solo una gerarchia di prodotti. |
| Gerarchia supplementare | Utilizzare questo tipo di gerarchia per tutte le gerarchie di categorie aggiuntive che si desidera creare. Ad esempio, in primavera, è disponibile una promozione per costumi da bagno. Pertanto, i costumi da bagno vengono inclusi in una gerarchia di categorie separata e viene applicato un prezzo promozionale alle varie categorie di prodotti. |
| Gerarchia di navigazione   | Utilizzare questo tipo di gerarchia per raggruppare e organizzare i prodotti in categorie in modo che possano essere esplorati online o nei POS. |

Utilizzando una gerarchia di categorie per strutturare i prodotti, è possibile impostare e gestire gli attributi del prodotto e le proprietà a livello di categoria. Tali attributi e proprietà includono le impostazioni per le dimensioni prodotto e le impostazioni del POS. Tutti i prodotti assegnati alle categorie ereditano automaticamente gli attributi e le proprietà definiti. È inoltre possibile copiare le impostazioni delle proprietà per qualsiasi prodotto a più prodotti in una categoria selezionata contemporaneamente.
