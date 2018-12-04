--- 
title: Impostare prezzi basati su attributi per prodotti configurabili
description: Questa procedura mostra come impostare prezzi basati su attributi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 88402bef6fd5dad38a74795cd31a4046085d6db7
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Impostare prezzi basati su attributi per prodotti configurabili

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare prezzi basati su attributi. Come prerequisito, è necessario disporre di un modello di configurazione prodotto contenente uno o più componenti e attributi. Nell'esempio viene utilizzato il modello di prodotto High End Speaker della società di dati dimostrativi USMF. In genere, un responsabile di prodotto usa questa procedura.


## <a name="create-a-new-price-model"></a>Creare un nuovo modello di prezzo
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco, selezionare la riga High End Speaker, ma non fare clic sul collegamento corrispondente al nome.
4. Nel riquadro azioni, fare clic su Modello.
5. Fare clic su Modelli di prezzo.
6. Fare clic su Nuovo.
7. Digitare un valore nel campo Nome modello di prezzo.
    * Utilizzare un nome che rende il modello semplice identificare.  
8. Nel campo Descrizione digitare un valore.
9. Fare clic su Salva.

## <a name="add-price-elements"></a>Aggiungere elementi di prezzo
1. Fare clic su Modifica.
    * Ciascun componente in un modello di prodotto può avere un elemento di prezzo base e un numero qualsiasi di regole di espressione del prezzo. È inoltre possibile aggiungere i prezzi in valute diverse.  
2. Digitare un valore nel campo Espressione prezzo di base.
    * Ad esempio, digitare 100.   Un'espressione per il prezzo di base può essere un valore numerico o può essere costituita da un calcolo aritmetico che include uno o più attributi.  
3. Scegliere Aggiungi.
4. Nel campo Nome digitare 'Rosewood'.
    * Il nome dell'espressione per il prezzo aiuta a identificare cosa l'elemento di prezzo rappresenta. In questo esempio, si crea un elemento di prezzo relativo all'opzione di rivestimento in palissandro per il cabinet dell'altoparlante.  
5. Fare clic su Modifica condizione.
    * Uan condizione di prezzo consente di garantire che un elemento dell'espressione per il prezzo viene incluso nel prezzo di vendita solo se una combinazione specifica di attributi è presente.  
6. Nel campo ConstraintBody, immettere 'CabinetFinish=="Rosewood"'.
7. Fare clic su OK.
8. Nel campo Espressione digitare un valore.
    * Ad esempio, digitare 50.  
9. Chiudere la pagina.
10. Chiudere la pagina.


