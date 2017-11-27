---
title: Creare e gestire gli attributi
description: Questo articolo descrive gli attributi in Microsoft Dynamics 365 for Retail. Gli attributi consentono di descrivere un prodotto e le relative caratteristiche tramite campi definiti dall'utente.
author: pdp1207
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a98527d37040dfcc0e57b74d590802e8aa2cb0b6
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="create-and-manage-attributes"></a>Creare e gestire gli attributi

[!include[banner](includes/banner.md)]


Questo articolo descrive gli attributi in Microsoft Dynamics 365 for Retail. Gli attributi consentono di descrivere un prodotto e le relative caratteristiche tramite campi definiti dall'utente.

Gli attributi consentono di descrivere un prodotto e le relative caratteristiche tramite campi definiti dall'utente. Ad esempio, è possibile specificare la dimensione di memoria del prodotto o la capacità del disco rigido e indicare se il prodotto è conforme allo standard Energy Star. Gli attributi possono essere associati a varie entità al dettaglio, come ad esempio le categorie di prodotti e canali di vendita al dettaglio. Inoltre è possibile impostarne dei valori predefiniti. I prodotti ereditano i propri attributi e valori predefiniti quando vengono associati alle categorie di prodotti o ai canali di vendita al dettaglio. I valori predefiniti possono essere sovrascritti a livello di singolo prodotto, a livello di canale di vendita al dettaglio o in un catalogo al dettaglio.

#### <a name="examples"></a>Esempi

| Categoria   | Attributo                | Valori permessi          | Valore predefinito |
|------------|--------------------------|-----------------------------|---------------|
| TV e video | Marchio                    | Qualsiasi valore Marchio valido       | Nessuna priorità          |
| TV         | Dimensioni schermo              | 20''–80''                     | Nessuna priorità          |
| TV         | Risoluzione verticale      | 480i, 720p, 1080i o 1080p | 1080p         |
| TV         | Frequenza di aggiornamento schermo      | 60 hz, 120 hz o 240 hz       | 60 hz          |
| TV         | Ingressi HDMI              | 0–10                        | 3             |
| TV         | Ingressi DVI               | 0–10                        | 1             |
| TV         | Ingressi compositi         | 0–10                        | 2             |
| TV         | Ingressi per componenti         | 0–10                        | 1             |
| LCD        | Predisposizione al 3D                 | Sì o No                   | Sì           |
| LCD        | Abilitato 3D               | Sì o No                   | No            |
| Plasma     | Temperatura d'esercizio da      | 32-110 gradi              | 32            |
| Plasma     | Temperatura d'esercizio fino a        | 32-110 gradi              | 100           |
| LCD | Garanzia tubo a proiezione | 6, 12 o 18 mesi         | 12            |
| LCD | N. di tubi di proiezione    | 1–5                         | 3             |


## <a name="attribute-type"></a>Tipo di attributo
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) 
  
Gli attributi si basano sui tipi di attributo. I tipi di attributo identificano il tipo di dati che può essere immesso per un attributo specifico. Attualmente, Microsoft Dynamics 365 for Retail supporta i seguenti tipi di attributo:

-   **Valuta** - Questo tipo di attributo supporta i valori di valuta. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Data e ora** - Questo tipo di attributo supporta i valori di data e ora. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Decimale** - Questo tipo di attributo supporta valori numerici che includono decimali. Supporta anche le unità di misura. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Intero** - Questo tipo di attributo supporta i valori numerici. Supporta anche le unità di misura. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Testo** - Questo tipo di attributo supporta i valori di testo. Supporta anche un set predefinito di valori possibili (enumerazione).
-   **Booleano** - Questo tipo di attributo supporta valori binari  (**true**/**false**).
-   **Riferimento**.

## <a name="attribute"></a>Attributo
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Oltre al nome, il nome descrittivo, la descrizione e il testo della Guida, è possibile acquisire per un attributo uno o più dei seguenti tipi di informazioni:

-   Valore predefinito
-   I metadati di attributo, ad esempio i metadati che indicano se è possibile cercare, rifinire o ordinare l'attributo

## <a name="attribute-group"></a>Gruppo attributi
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) Una volta definiti, gli attributi possono essere raggruppati in gruppi di attributi. I gruppi di attributi forniscono raggruppamenti di singoli attributi e possono essere assegnati alle categorie di vendita al dettaglio o ai canali di vendita al dettaglio.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Assegnazione dei gruppi di attributi alle categorie di vendita al dettaglio
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) È possibile associare uno o più gruppi di attributi a nodi di categorie nella gerarchia delle categorie di prodotti al dettaglio. Una volta che i prodotti sono stati classificati in categorie, ereditano gli attributi inclusi nei gruppi di attributi.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Assegnazione di gruppi di attributi ai punti vendita al dettaglio
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) È possibile associare uno o più gruppi di attributi a uno o più punti vendita al dettaglio nella gerarchia dei punti vendita al dettaglio. Una volta che i prodotti sono stati migliorati per gli specifici punti vendita al dettaglio, ereditano gli attributi inclusi nei gruppi di attributi.

## <a name="overriding-attribute-values"></a>Sostituzione dei valori di attributi
### <a name="at-the-product-level"></a>A livello di prodotto

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) È possibile sovrascrivere i valori predefiniti degli attributi a livello di prodotto (vale a dire per i singoli prodotti).

### <a name="in-a-retail-catalog"></a>In un catalogo di vendita al dettaglio

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) È possibile sovrascrivere i valori predefiniti degli attributi per singoli prodotti in specifici cataloghi che sono destinati a canali di vendita al dettaglio specifici.

### <a name="at-the-retail-channel-level"></a>A livello di canale di vendita al dettaglio

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) È possibile sovrascrivere i valori predefiniti degli attributi per singoli prodotti in specifici cataloghi che sono destinati a canali di vendita al dettaglio specifici.




