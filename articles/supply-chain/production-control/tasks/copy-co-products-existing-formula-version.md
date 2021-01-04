---
title: Copiare co-prodotti da una versione di formula esistente
description: Questa procedura mostra come copiare i co-prodotti da una versione di formula esistente in una versione di formula diversa per un prodotto rilasciato.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 79b70ccbdac2061baf3896ecbd9449da3c38842a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430876"
---
# <a name="copy-co-products-from-an-existing-formula-version"></a>Copiare co-prodotti da una versione di formula esistente

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come copiare i co-prodotti da una versione di formula esistente in una versione di formula diversa per un prodotto rilasciato. Esiste un prerequisito per cui è presente almeno una versione di formula associata a co-prodotti. La società di dati dimostrativi USP2 è utilizzata per creare questa procedura.


## <a name="find-a-released-product"></a>Trovare un prodotto rilasciato
1. Fare clic su Prodotti rilasciati.
2. Fare clic su Mostra filtri.
    * Il campo Tipo di produzione sta per essere aggiunto nella finestra di dialogo Filtro.  
3. Fare clic su Aggiungi un campo di filtro per aggiungere il campo Tipo di produzione.
    * Al passaggio successivo è necessario immettere manualmente la formula nel campo Tipo di produzione prima di selezionare Applica. Questa imposta il filtro nell'elenco dei prodotti rilasciati.  
4. Immettere manualmente la formula nel campo del Tipo di produzione.
5. Fare clic su Applica.

## <a name="select-a-released-product"></a>Selezionare un prodotto rilasciato
1. Nell'elenco trovare e selezionare il record desiderato.
2. Fare clic su Versioni formula.
    * Nel riquadro azioni di progettazione, fare clic su Versioni formula.  

## <a name="copy-co-products"></a>Copiare co-prodotti
1. Nel riquadro azioni, fare clic su Versione formula.
2. Fare clic su Co-prodotti.
3. Fare clic su Copia.
4. Nel campo Numero di articoli immettere o selezionare un valore.
5. Nel campo Versione formula immettere o selezionare un valore.
6. Fare clic su OK.
7. Chiudere la pagina.

