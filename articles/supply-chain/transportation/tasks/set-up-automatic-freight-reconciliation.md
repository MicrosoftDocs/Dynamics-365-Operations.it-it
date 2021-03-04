---
title: Impostare la riconciliazione trasporto automatica
description: In questa procedura viene illustrato come impostare i dati per la riconciliazione automatica di trasporto.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f11edc15821faad84485d5b81e4a9ded0b7e974
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430934"
---
# <a name="set-up-automatic-freight-reconciliation"></a>Impostare la riconciliazione trasporto automatica

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come impostare i dati per la riconciliazione automatica di trasporto. Il processo è in genere eseguito da un amministratore di magazzino. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.


## <a name="set-up-the-freight-bill-type"></a>Impostare il tipo di fattura di trasporto
1. Passare a Gestione trasporto > Impostazione > Riconciliazione trasporto > Tipo di fattura trasporto.
    * Il tipo di fattura di trasporto determina come le fatture di trasporto e le fatture vettore devono essere associate.  
2. Fare clic su Nuovo.
3. Nel campo Tipo di fattura trasporto, digitare un valore.
4. Nel campo Assembly motore digitare "Microsoft.Dynamics.Ax.Tms.dll".
    * Si tratta della libreria di codice del motore di associazione gestione trasporto standard.  
5. Nel campo Classe motore digitare "Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer".
    * Si tratta della classe del motore di associazione gestione trasporto standard.  
6. Fare clic su Nuovo.
7. Nel campo Descrizione, selezionare il valore che deve corrispondere sulla fattura di trasporto e sulla fattura del vettore.  
8. Selezionare 'Sì' nel campo Corrispondenza necessaria.
    * Se si imposta il campo su Sì questo significa che il valore selezionato nel campo Descrizione deve corrispondere sia sulla fattura di trasporto che sulla fattura del vettore. Se viene impostato su No, il campo può essere vuoto in una di queste.  
9. Fare clic su Salva.

## <a name="set-up-the-freight-bill-type-assignment"></a>Impostare l'assegnazione del tipo di fattura di trasporto
1. Chiudere la pagina.
2. Passare a Gestione trasporto > Impostazione > Riconciliazione trasporto > Assegnazioni tipo di fattura di trasporto.
    * L'assegnazione del tipo di fattura di trasporto viene utilizzata per specificare il tipo di fattura di trasporto utilizzato per un vettore specifico.   
3. Fare clic su Nuovo.
4. Nel campo Modo immettere o selezionare un valore.
5. Nel campo Vettore spedizione immettere o selezionare un valore.
6. Nel campo Tipo di fattura trasporto, selezionare il tipo di fattura trasporto creato in precedenza.
7. Chiudere la pagina.

## <a name="set-up-the-audit-master"></a>Impostare l'audit principale
1. Passare a Gestione trasporto > Impostazione > Riconciliazione trasporto > Audit principale.
    * I dati master di controllo definiscono i limiti di tolleranza per la riconciliazione automatica di trasporto. Specificano di quanto gli importi monetari nella fattura di trasporto e nella fattura vettore possono differire e ancora ammettere la riconciliazione. Definiscono inoltre la modalità di gestione delle discrepanze.  
2. Fare clic su Nuovo.
3. Immettere un valore nel campo ID audit principale.
4. Nel campo Vettore spedizione selezionare lo stesso vettore di spedizione della selezione precedente.
5. Nel campo Tipo di fattura trasporto, selezionare il tipo di fattura trasporto creato in precedenza.
6. Espandere la sezione Tolleranza.
7. Nel campo Livello tolleranza minima immettere un numero.
8. Nel campo Livello tolleranza massima immettere un numero.
9. Espandere la sezione Risultato.
10. Nel campo Codice motivo eccedenza di pagamento immettere o selezionare un valore.
    * Se gli importi monetari differiscono nella fattura di trasporto e la fattura vettore, i codici motivo di eccedenza e insufficienza di pagamento specificano i conti in cui la differenza deve essere registrata, a condizione che la differenza sia nei livelli di tolleranza.  
11. Nel campo Codice motivo insufficienza di pagamento immettere o selezionare un valore.
12. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]