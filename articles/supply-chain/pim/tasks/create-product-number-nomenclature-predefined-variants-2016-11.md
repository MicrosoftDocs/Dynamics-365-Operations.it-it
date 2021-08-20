---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite
description: In questo argomento viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fada426b03aa8a908c3351932a288c911cb8c60fa13ccbfbfd0ceed232759a88
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736042"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Creare una nomenclatura del numero di prodotto per le varianti prodotto predefinite

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto predefinite e come può essere assegnata al gruppo di dimensioni prodotto appropriato. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La nuova nomenclatura di numero prodotto è assegnata al gruppo di dimensioni prodotto Colore e Dimensioni. Questa attività viene in genere effettuata da un responsabile del design del prodotto.


## <a name="create-a-product-number-nomenclature"></a>Creare una nomenclatura di numero prodotto

1. Vai a **Gestione informazioni sul prodotto \> Imposta \> Nomenclatura di prodotto**.
1. Selezionare **Nuovo**.
1. Nel campo **Nome**, immettere un nome di nomenclatura che consente di identificare il gruppo di dimensioni prodotto di destinazione, ad esempio `ColorSize`.
1. Digitare un valore nel campo **Descrizione**
1. Selezionare **Aggiungi**.
1. Selezionare **Numero rappresentazione generale prodotto**.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Seleziona **Colore**.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Seleziona **Dimensioni**.
1. Chiudere la pagina.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Assegnare la nomenclatura a una rappresentazione generale prodotto

1. Selezionare **Gruppi di dimensioni prodotto**.
2. Selezionare il gruppo di **dimensioni prodotto SizeCol**.
3. Selezionare **Modifica**.
4. Selezionare **Sì** nel campo **Utilizza nomenclatura**.
5. Nel campo **Nomenclatura di numero di variante prodotto** immettere o selezionare un valore.
6. Chiudere la pagina.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]