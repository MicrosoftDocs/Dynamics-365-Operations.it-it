---
title: Impostare prezzi basati su attributi per prodotti configurabili
description: In questo argomento viene illustrato come impostare prezzi basati su attributi.
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d23030b79670e31cc237b9ca53b0b3881678786f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149828"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Impostare prezzi basati su attributi per prodotti configurabili

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare prezzi basati su attributi. Come prerequisito, è necessario disporre di un modello di configurazione prodotto contenente uno o più componenti e attributi. Nell'esempio viene utilizzato il modello di prodotto High End Speaker della società di dati dimostrativi USMF. In genere, un responsabile di prodotto usa questa procedura.


## <a name="create-a-new-price-model"></a>Creare un nuovo modello di prezzo
1. Selezionare **Definizione modello di variante prodotto** nella home page.
2. Selezionare **Modelli di configurazione prodotto** nella sezione **Collegamenti**.
3. Nell'elenco, selezionare la riga **High End Speaker**, ma non il collegamento per il nome.
4. Nel Riquadro azioni selezionare **Modello**.
5. Selezionare **Modelli di prezzo**.
6. Selezionare **Nuovo**.
7. Digitare un valore nel campo **Nome modello di prezzo**. Utilizzare un nome che rende il modello semplice identificare.  
8. Digitare un valore nel campo **Descrizione**
9. Selezionare **Salva**.

## <a name="add-price-elements"></a>Aggiungere elementi di prezzo
1. Selezionare **Modifica**. Ciascun componente in un modello di prodotto può avere un elemento di prezzo base e un numero qualsiasi di regole di espressione del prezzo. È inoltre possibile aggiungere i prezzi in valute diverse.  
2. Digitare un valore nel campo **Espressione prezzo di base**. Ad esempio, digitare 100. Un'espressione per il prezzo di base può essere un valore numerico o può essere costituita da un calcolo aritmetico che include uno o più attributi.  
3. Selezionare **Aggiungi**.
4. Nel campo **Nome**, digitare `Rosewood`. Il nome dell'espressione per il prezzo aiuta a identificare cosa l'elemento di prezzo rappresenta. In questo esempio, si crea un elemento di prezzo relativo all'opzione di rivestimento in palissandro per il cabinet dell'altoparlante.  
5. Selezionare **Modifica condizione**. Uan condizione di prezzo consente di garantire che un elemento dell'espressione per il prezzo viene incluso nel prezzo di vendita solo se una combinazione specifica di attributi è presente.  
6. Nel campo **ConstraintBody** immettere `CabinetFinish=="Rosewood"`.
7. Selezionare **OK**.
8. Nel campo **Espressione** digitare un valore. Ad esempio, digitare `50`. 
9. Chiudere la pagina.

