---
title: Gestisci ciclo di lavorazione per un modello di prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921267"
---
# <a name="maintain-route-for-a-product-model"></a>Gestisci ciclo di lavorazione per un modello di prodotto

[!include [banner](../../includes/banner.md)]

L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente. Questa procedura utilizza il modello High end speaker della società di dati dimostrativi USMF per eseguire il processo.

## <a name="add-a-route-operation"></a>Aggiungere un'operazione del ciclo di lavorazione

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
1. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il modello High end speaker per questo esercizio.  
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Espandere la sezione **Operazioni ciclo di lavorazione**.
1. Selezionare **Aggiungi**.
1. Digitare un valore nel campo **Nome**.
1. Digitare un valore nel campo **Descrizione**
1. Selezionare **Salva**.

## <a name="enter-route-operation-details"></a>Immettere i dettagli operazione ciclo di lavorazione

1. Fare clic su **Dettagli operazione ciclo di lavorazione**.
1. Nel campo **Operazione** immettere o selezionare un valore.
1. Nel campo **Oper. n.** immettere un numero.
    * I numeri di operazione determinano la sequenza del ciclo di lavorazione.  
    * Ogni proprietà di un'operazione del ciclo di lavorazione può ottenere un valore statico o essere sottoposta al mapping a un attributo. Il mapping a un attributo determinerà l'impostazione del valore come parte di configurazione.  
1. Nel campo **Gruppo di cicli di lavorazione** immettere o selezionare un valore.
    * Il gruppo di cicli di lavorazione determina il comportamento essenziale di costi, consumo e impostazione.  
1. Seleziona la scheda **Impostazioni**.
1. Seleziona la scheda **Tempi**.
1. Nel campo **Qtà lavorazione** immettere un numero.
    * Determinare quante elaborazioni verranno eseguite durante un'operazione.  
1. Nel campo **Ore/Ora** immettere un numero.
    * Inserire il rapporto durata.  
1. Selezionare la casella di controllo **Imposta**.
1. Nel campo **Tempo di esecuzione** immettere un numero.
    * Determinare l'ora di elaborazione per la quantità specificata.  
1. Selezionare la scheda **Requisiti risorsa**.
1. Selezionare **Aggiungi**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Tipo di requisito** selezionare un'opzione.
    * Decidere se si desidera specificare risorse o funzionalità specifiche di cui si deve disporre.  
1. Nel campo **Requisito** immettere o selezionare un valore.
1. Selezionare **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]