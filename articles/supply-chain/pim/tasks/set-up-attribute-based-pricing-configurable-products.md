---
title: Impostare prezzi basati su attributi per prodotti configurabili
description: In questo argomento viene illustrato come impostare prezzi basati su attributi.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5abb2e7dc33b46589c1a3699e70b56af6f694aed49294eb81a2122db6d414a96
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743556"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Impostare prezzi basati su attributi per prodotti configurabili

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare prezzi basati su attributi. Come prerequisito, è necessario disporre di un modello di configurazione prodotto contenente uno o più componenti e attributi. Nell'esempio viene utilizzato il modello di prodotto High End Speaker della società di dati dimostrativi USMF. In genere, un responsabile di prodotto usa questa procedura.


## <a name="create-a-new-price-model"></a>Creare un nuovo modello di prezzo

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Nell'elenco, selezionare la riga **High End Speaker**, ma non il collegamento per il nome.
1. Nel Riquadro azioni selezionare **Modello**.
1. Selezionare **Modelli di prezzo**.
1. Selezionare **Nuovo**.
1. Digitare un valore nel campo **Nome modello di prezzo**. Utilizzare un nome che rende il modello semplice identificare.  
1. Digitare un valore nel campo **Descrizione**
1. Selezionare **Salva**.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]