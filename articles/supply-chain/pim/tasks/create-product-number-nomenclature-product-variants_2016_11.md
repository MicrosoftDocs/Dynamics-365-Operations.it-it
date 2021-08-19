---
title: Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate
description: In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: da52385f60b2522cf358e0ceb70448479a1e5dc714ef15ba361611ed404ed852
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726827"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Creare una nomenclatura del numero di prodotto per le varianti prodotto configurate

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile. Questa procedura dimostra anche come è possibile creare una nomenclatura di configurazione per un componente del modello di configurazione prodotto. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La nuova nomenclatura di numero prodotto è assegnata alla rappresentazione generale prodotto D0004. Questa attività viene in genere effettuata da un responsabile del design del prodotto.

## <a name="create-a-product-number-nomenclature"></a>Creare una nomenclatura di numero prodotto

1. Vai a **Gestione informazioni sul prodotto \> Imposta \> Nomenclatura di prodotto**.
1. Selezionare **Nuovo**.
1. Digitare un valore nel campo **Nome**.
1. Digitare un valore nel campo **Descrizione**
1. Selezionare **Aggiungi**.
1. Selezionare **Numero rappresentazione generale prodotto**.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Seleziona **Configurazione**
1. Chiudere la pagina.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Assegnare la nomenclatura di un numero prodotto a una rappresentazione generale prodotto

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Rappresentazioni generali prodotto**.
1. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al campo **Numero prodotto** con un valore di 'D'.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Seleziona **Modifica**.
1. Selezionare *Sì* nel campo **Utilizza nomenclatura**.
1. Nel campo **Nomenclatura di numero di variante prodotto** immettere o selezionare un valore.
1. Chiudere la pagina.
1. Chiudere la pagina.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Creare una nomenclatura per un componente di modello di configurazione prodotto

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Seleziona **Modifica**.
1. Selezionare *Sì* nel campo **Utilizza nomenclatura di configurazione**.
1. Selezionare **Aggiungi**.
1. Selezionare **Valore attributo**
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Attributo** immettere o selezionare un valore.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Selezionare **Valore attributo**
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Attributo** immettere o selezionare un valore.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Selezionare **Valore attributo**
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Attributo** immettere o selezionare un valore.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Selezionare **Valore attributo**
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Attributo** immettere o selezionare un valore.
1. Selezionare **Aggiungi**.
1. Selezionare **Costante testo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Digitare un valore nel campo **Testo**.
1. Selezionare **Aggiungi**.
1. Selezionare **Valore sequenza numerica**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Sequenza numerica** immettere o selezionare un valore.
1. Chiudere la pagina.
1. Chiudere la pagina.
1. Chiudere la pagina.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]