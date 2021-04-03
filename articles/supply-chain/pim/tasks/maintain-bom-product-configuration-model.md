---
title: Gestire DBA per un modello di configurazione prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12eb2d8fcdae5d60efa19e5443a01ab9bd104267
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258805"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Gestire DBA per un modello di configurazione prodotto

[!include [banner](../../includes/banner.md)]

L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente. Il modello High end speaker della società di dati dimostrativi USMF è utilizzato per creare questa procedura.


## <a name="add-a-bom-line"></a>Aggiungere una riga DBA
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare High end speaker per questa procedura.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione Righe DBA.
6. Scegliere Aggiungi.
7. Digitare un valore nel campo Nome.
8. Nel campo Descrizione digitare un valore.
9. Fare clic su Salva.

## <a name="add-bom-line-details"></a>Aggiungere i dettagli riga DBA
1. Fare clic su Dettagli riga DBA.
2. Nel campo Numero di articoli immettere o selezionare un valore.
    * Ad esempio, è possibile selezionare l'articolo M0055.  
    * Per ogni proprietà di riga DBA, è possibile scegliere se prende un valore fisso o viene sottoposta al mapping a un attributo.  
3. Selezionare la casella di controllo Imposta.
4. Selezionare Sì nel campo Calcolo.
    * Impostando la proprietà Calcolo su Sì, si garantisce che la riga DBA venga inclusa nei calcoli dei costi.  
5. Fare clic sulla scheda Impostazioni.
6. Selezionare la casella di controllo Imposta.
7. Nel campo Quantità immettere un numero.
    * Il campo Quantità determina la quantità dell'articolo che verrà incluso nella DBA. Ovviamente può essere utilizzato per il mapping di attributo.  
8. Fare clic sulla scheda Dimensione.
    * Verificare se le dimensioni prodotto sono attive e nel qual caso è necessario assegnare un valore o un attributo.  
9. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]