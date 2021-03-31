---
title: Tipi di attributo di manutenzione
description: Nell'argomento viene descritto come creare tipi di attributo in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b93c2ab284d5746f4ecd48cd8b8ffe59aea9f90
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217247"
---
# <a name="maintenance-attribute-types"></a>Tipi di attributo di manutenzione

[!include [banner](../../includes/banner.md)]

 

Nell'argomento viene descritto come creare tipi di attributo in Gestione cespiti. Gli attributi consentono di descrivere le proprietà dei vari elementi. È possibile impostare attributi per i seguenti elementi:

- [Tipi di unità funzionali](../setup-for-functional-locations/functional-location-types.md)
- [Creare unità funzionali](../functional-locations/create-functional-locations.md)
- [Tipi di cespite](../setup-for-objects/object-types.md)
- Cespiti

Gli attributi impostabili variano in base all'elemento. Ad esempio, per una unità funzionale, è possibile impostare gli attributi per la configurazione e le dimensioni fisiche della ubicazione. Per un tipo di cespite o un cespite, è possibile impostare gli attributi per il volume del motore, il consumo di energia e la massima capacità di carico in varie condizioni.

## <a name="create-attribute-types"></a>Creare tipi di attributo

È possibile creare propri tipi di attributo. Inoltre, è possibile trasferire le dimensioni prodotto alla pagina **Tipi di attributo**.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Tipi di attributo**.
2. La prima volta che si impostano i tipi di attributo selezionare **Crea dimensioni prodotto** per trasferire automaticamente le dimensioni prodotto standard.
3. Selezionare **Nuovo** per creare un tipo di attibuto.
4. Nel campo **Tipo di attributo** immettere un nome per il tipo di attributo.
5. Nel campo **Descrizione** immettere una descrizione.
6. Nel campo **Unità**, selezionare l'unità di attributo pertinente, secondo le esigenze.
7. Nel campo **Tipo di dati** selezionare un tipo di dati per l'unità.
8. Se è stato selezionato **Stringa** come tipo di dati, seguire questi passaggi per creare valori per il tipo di attributo:

    1. Selezionare il tipo di attributo, quindi selezionare **Valori**.
    2. Nel campo **Valori attributi** selezionare **Nuovo**.
    3. Nel campo **Tipo di attributo** selezionare un tipo di attributo (dimensione).
    4. Nel campo  **Valore** immettere un valore correlato.
    5. Nel campo **Descrizione** immettere una descrizione.
    6. Salvare il record.
    7. Torna alla pagina **Tipi di attributo**.

9. Salvare il record.

    Nel campo **Tipi di unità funzionali** viene visualizzato il numero di unità funzionali che utilizzano il tipo di attributo. Nel campo **Tipi di cespite** viene visualizzato il numero di tipi di cespite che lo utilizzano.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]