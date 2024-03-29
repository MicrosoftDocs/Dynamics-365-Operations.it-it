---
title: Gestire DBA per un modello di configurazione prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd78b06f10d0c9b1df57dacdd824b06ebe414b3b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577290"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Gestire DBA per un modello di configurazione prodotto

[!include [banner](../../includes/banner.md)]

L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente. Il modello High end speaker della società di dati dimostrativi USMF è utilizzato per creare questa procedura.

## <a name="add-a-bom-line"></a>Aggiungere una riga DBA

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare High end speaker per questa procedura.  
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Espandere la sezione **Righe DBA**.
1. Selezionare **Aggiungi**.
1. Digitare un valore nel campo **Nome**.
1. Digitare un valore nel campo **Descrizione**
1. Selezionare **Salva**.

## <a name="add-bom-line-details"></a>Aggiungere i dettagli riga DBA

1. Selezionare **Dettagli riga DBA**.
2. Nel campo **Numero articolo** immettere o selezionare un valore.
    * Ad esempio, è possibile selezionare l'articolo M0055.  
    * Per ogni proprietà di riga DBA, è possibile scegliere se prende un valore fisso o viene sottoposta al mapping a un attributo.  
3. Selezionare la casella di controllo **Imposta**.
4. Selezionare *Sì* nel campo **Calcolo**.
    * Impostando la proprietà **Calcolo** su *Sì*, si garantisce che la riga DBA venga inclusa nei calcoli dei costi.  
5. Seleziona la scheda **Impostazioni**.
6. Selezionare la casella di controllo **Imposta**.
7. Nel campo **Quantità** immettere un numero.
    * Il campo Quantità determina la quantità dell'articolo che verrà incluso nella DBA. Ovviamente può essere utilizzato per il mapping di attributo.  
8. Selezionare la scheda **Dimensione**.
    * Verificare se le dimensioni prodotto sono attive e nel qual caso è necessario assegnare un valore o un attributo.  
9. Selezionare **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]