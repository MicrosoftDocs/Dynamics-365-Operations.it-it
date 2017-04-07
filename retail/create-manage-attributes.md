---
title: Creare e gestire gli attributi
description: In questo articolo viene descritto gli attributi di Microsoft Dynamics 365 per le operazioni. Gli attributi consentono di descrivere un prodotto e le relative caratteristiche tramite campi definiti dall&quot;utente.
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 26c628e10aaa5f47bc87d7510ca8f41ab3630204
ms.lasthandoff: 03/31/2017


---

# <a name="create-and-manage-attributes"></a>Creare e gestire gli attributi

In questo articolo viene descritto gli attributi di Microsoft Dynamics 365 per le operazioni. Gli attributi consentono di descrivere un prodotto e le relative caratteristiche tramite campi definiti dall'utente.

Gli attributi consentono di descrivere un prodotto e le relative caratteristiche tramite campi definiti dall'utente. Ad esempio, è possibile specificare la dimensione di memoria del prodotto o la capacità del disco rigido e indicare se il prodotto è conforme allo standard Energy Star. Gli attributi possono essere associati a varie entità al dettaglio, come ad esempio le categorie di prodotti e canali di vendita al dettaglio. Inoltre è possibile impostarne dei valori predefiniti. I prodotti ereditano i propri attributi e valori predefiniti quando vengono associati alle categorie di prodotti o ai canali di vendita al dettaglio. I valori predefiniti possono essere sovrascritti a livello di singolo prodotto, a livello di canale di vendita al dettaglio o in un catalogo al dettaglio.

#### <a name="examples"></a>Esempi

Categoria

Attributo

Valori permessi

Valore predefinito

TV e video

Marchio

Qualsiasi valore **Marchio** valido

Nessuno

TV

Dimensioni schermo

**20"**-**80"**

Nessuno

Risoluzione verticale

**480i**, **720p**, **1080i** o **1080p**

**1080p**

Frequenza di aggiornamento schermo

**60 hz**, **120 hz** o **240 hz**

**60 hz**

Ingressi HDMI

**0**-**10**

**3**

Ingressi DVI

**0**-**10**

**1**

Ingressi compositi

**0**-**10**

**2**

Ingressi per componenti

**0**-**10**

**1**

LCD

Predisposizione al 3D

**Sì** o **No**

**Sì**

Abilitato 3D

**Sì** o **No**

**No**

Plasma

Temperatura d'esercizio da

**32**-**110** gradi

**32**

Temperatura d'esercizio fino a

**32**-**110** gradi

**100**

LCD

Garanzia tubo a proiezione

**6**, **12** o **18** mesi

**12**

\# di tubi della proiezione

**1**-**5**

**3**

## <a name="attribute-type"></a>Tipo di attributo
  [attributo-fisso- copia![(]. /media/attributes-fixed-copy.png)](. Gli attributi di /media/attributes-fixed-copy.png) sono basati sui tipi di attributo. I tipi di attributo identificano il tipo di dati che può essere immesso per un attributo specifico. Attualmente, Microsoft Dynamics 365 per le operazioni sono supportati i seguenti tipi di attributo:

-   **Valuta** - Questo tipo di attributo supporta i valori di valuta. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Data e ora** - Questo tipo di attributo supporta i valori di data e ora. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Decimale** - Questo tipo di attributo supporta valori numerici che includono decimali. Supporta anche le unità di misura. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Intero** - Questo tipo di attributo supporta i valori numerici. Supporta anche le unità di misura. Può essere associato (ovvero può supportare un intervallo di valori) oppure può essere lasciato aperto.
-   **Testo** - Questo tipo di attributo supporta i valori di testo. Supporta anche un set predefinito di valori possibili (enumerazione).
-   ** Booleano ** il tipo di attributo supporta i valori binari (** riga **/** false **).
-   **Riferimento**.

## <a name="attribute"></a>Attributo
  ![[] (createandmanageattribute-8. /media/createandmanageattribute-8.png)](. /media/createandmanageattribute-8.png) E il nome, il nome descrittivo, la descrizione e il testo guida, uno o più dei seguenti tipi di informazioni sia più di un attributo:

-   Valore predefinito
-   I metadati di attributo, ad esempio i metadati che indicano se è possibile cercare, rifinire o ordinare l'attributo

## <a name="attribute-group"></a>Gruppo attributi
  ![[] (createandmanageattribute-10. /media/createandmanageattribute-10.png)](. /media/createandmanageattribute-10.png) Dopo gli attributi definiti, possono essere raggruppati in gruppi. I gruppi di attributi forniscono raggruppamenti di singoli attributi e possono essere assegnati alle categorie di vendita al dettaglio o ai canali di vendita al dettaglio.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Assegnazione dei gruppi di attributi alle categorie di vendita al dettaglio
  ![[] (createandmanageattribute-12. /media/createandmanageattribute-12.png)](. /media/createandmanageattribute-12.png) Uno o più gruppi di attributi può essere associato ai nodi di categoria nella gerarchia di categorie di vendita al dettaglio del prodotto. Una volta che i prodotti sono stati classificati in categorie, ereditano gli attributi inclusi nei gruppi di attributi.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Assegnazione di gruppi di attributi ai punti vendita al dettaglio
  ![[] (createandmanageattribute-13-1024x576. /media/createandmanageattribute-13-1024x576.png)](. /media/createandmanageattribute-13-1024x576.png) Uno o più gruppi di attributi può essere associato a una o più vendita al dettaglio nella gerarchia di vendita al dettaglio. Una volta che i prodotti sono stati migliorati per gli specifici punti vendita al dettaglio, ereditano gli attributi inclusi nei gruppi di attributi.

## <a name="overriding-attribute-values"></a>Sostituzione dei valori di attributi
### <a name="at-the-product-level"></a>A livello di prodotto

  ![[] (createandmanageattribute-14-1024x576. /media/createandmanageattribute-14-1024x576.png)](. /media/createandmanageattribute-14-1024x576.png) I valori predefiniti degli attributi può essere sostituito a livello di prodotto (ovvero per prodotti singoli).

### <a name="in-a-retail-catalog"></a>In un catalogo di vendita al dettaglio

  ![[] (createandmanageattribute-2. /media/createandmanageattribute-2.png)](. /media/createandmanageattribute-2.png) I valori predefiniti degli attributi può essere sostituito per prodotti singoli nei cataloghi sono specifici di mirati per i canali di articoli specifici.

### <a name="at-the-retail-channel-level"></a>A livello di canale di vendita al dettaglio

  ![[] (createandmanageattribute-1. /media/createandmanageattribute-1.jpg)](. /media/createandmanageattribute-1.jpg) I valori predefiniti degli attributi può essere sostituito per prodotti singoli nei cataloghi sono specifici di mirati per i canali di articoli specifici.


