---
title: Gestisci ciclo di lavorazione per un modello di prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13bbdc706280317c5a1ab7fb21c9585f1c7d48ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247792"
---
# <a name="maintain-route-for-a-product-model"></a>Gestisci ciclo di lavorazione per un modello di prodotto

[!include [banner](../../includes/banner.md)]

L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente. Questa procedura utilizza il modello High end speaker della società di dati dimostrativi USMF per eseguire il processo.


## <a name="add-a-route-operation"></a>Aggiungere un'operazione del ciclo di lavorazione
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il modello High end speaker per questo esercizio.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione Operazioni ciclo di lavorazione.
6. Scegliere Aggiungi.
7. Digitare un valore nel campo Nome.
8. Nel campo Descrizione digitare un valore.
9. Fare clic su Salva.

## <a name="enter-route-operation-details"></a>Immettere i dettagli operazione ciclo di lavorazione
1. Fare clic su Dettagli operazione ciclo di lavorazione.
2. Nel campo Operazione immettere o selezionare un valore.
3. Nel campo Oper. N. immettere un numero.
    * I numeri di operazione determinano la sequenza del ciclo di lavorazione.  
    * Ogni proprietà di un'operazione del ciclo di lavorazione può ottenere un valore statico o essere sottoposta al mapping a un attributo. Il mapping a un attributo determinerà l'impostazione del valore come parte di configurazione.  
4. Nel campo Gruppo di cicli di lavorazione immettere o selezionare un valore.
    * Il gruppo di cicli di lavorazione determina il comportamento essenziale di costi, consumo e impostazione.  
5. Fare clic sulla scheda Impostazioni.
6. Fare clic sulla scheda Tempi.
7. Nel campo Qtà lavorazione immettere un numero.
    * Determinare quante elaborazioni verranno eseguite durante un'operazione.  
8. Nel campo Ore/Ora immettere un numero.
    * Inserire il rapporto durata.  
9. Selezionare la casella di controllo Imposta.
10. Nel campo Tempo di esecuzione immettere un numero.
    * Determinare l'ora di elaborazione per la quantità specificata.  
11. Fare clic sulla scheda Requisiti risorsa.
12. Scegliere Aggiungi.
13. Nell'elenco contrassegnare la riga selezionata.
14. Nel campo Tipo di requisito selezionare un'opzione.
    * Decidere se si desidera specificare risorse o funzionalità specifiche di cui si deve disporre.  
15. Nel campo Requisito immettere o selezionare un valore.
16. Fare clic su OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]