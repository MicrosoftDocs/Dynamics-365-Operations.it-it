---
title: Estendere le entità di dati delle scorte disponibili
description: Questo argomento fornisce un esempio che mostra come aggiungere campi estesi alle viste INVENTORSITEONHANDENTITY e INVENTWAREHOUSEONHANDENTITY, in modo che le funzionalità delle entità di dati disponibili dell'inventario possano funzionare con le estensioni.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e3bf3a7d48b0aa3e48845882be0ee86da17ed040
ms.sourcegitcommit: e276348a63bfdb9e712c0ea86e6c2a68c50872c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665406"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Estendere le entità di dati delle scorte disponibili

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management fornisce funzionalità di [estendibilità](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) che consentono di [aggiungere campi alle tabelle tramite le estensioni](../../fin-ops-core/dev-itpro/extensibility/add-field-extension). Questo argomento fornisce un esempio che mostra come aggiungere campi estesi alle viste `INVENTORSITEONHANDENTITY` e `INVENTWAREHOUSEONHANDENTITY`, in modo che le funzionalità delle entità di dati disponibili dell'inventario possano funzionare con le estensioni. Per ulteriori informazioni sulle entità dei dati, vedere [Panoramica sulla gestione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> Ecco un elenco di alcune delle entità di dati disponibili nell'inventario:
>
> - Disponibilità scorte in base al sito
> - Disponibilità scorte in base al sito V2
> - Disponibilità scorte in base al magazzino
> - Disponibilità scorte in base al magazzino v2

Dopo aver aggiunto i campi alle tabelle utilizzate dalla vista `inventSiteOnHandView`, è necessario sincronizzare il motore in modo che le estensioni vengano riconosciute correttamente.

1. Estendere la vista `InventSiteOnHandView` aggiungendo il campo di estensione.
1. Estendere la vista `InventSiteOnHandAggregatedView` con i campi dell'estensione.
1. Estendere la classe `InventSiteOnHandAggregatedViewBuilder` viewBuilder modificando il metodo `getExtensionFields()`. In questo modo, si associano i vecchi campi di visualizzazione a nuovi campi di visualizzazione quando viene eseguita la sincronizzazione di viewBuilder.

Ad esempio, sono stati aggiunti i seguenti quattro campi alla tabella `InventTable` tramite estensione:

- Campo personalizzato 1
- Campo personalizzato 2
- Campo personalizzato 3
- Campo personalizzato 4

Nel caso, è necessario modificare il metodo `getExtensionFields()` nel modo seguente.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

Dopo aver completato questi passaggi, è possibile estendere l'inventario disponibile per sito e l'inventario disponibile per entità di dati warehouse aggiungendo i nuovi campi. In questo modo, i campi estesi verranno riconosciuti e inclusi durante la migrazione dei dati che utilizza tali entità di dati.
