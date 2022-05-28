---
title: Trasferire un cespite
description: Questa guida attività trasferirà le informazioni finanziarie per un libro cespiti da un set di dimensioni finanziarie in un nuovo set di dimensioni finanziarie.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c8428467d6e12b6d6af9023980b8cf8738d9294
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727007"
---
# <a name="transfer-a-fixed-asset"></a>Trasferire un cespite

[!include [banner](../../includes/banner.md)]

Questa guida attività trasferirà le informazioni finanziarie per un libro cespiti da un set di dimensioni finanziarie in un nuovo set di dimensioni finanziarie.  

1. Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.
2. Nell'elenco, individuare e selezionare il cespite da trasferire.
3. Nel riquadro azioni fare clic su **Cespite**.
4. Fare clic su **Trasferisci cespiti**.
5. Nel campo **Data di trasferimento** immettere una data.
6. Immettere i commenti per descrivere il trasferimento.
    
    In questo elenco vengono visualizzati tutti i libri per il cespite.  
7. Contrassegnare i libri da trasferire in un nuovo set di dimensioni finanziarie.
    * In questo elenco vengono visualizzati i valori di dimensione finanziaria esistenti per il libro selezionato.  
    * Selezionare la dimensione finanziaria da aggiornare per il libro cespiti selezionato.  
8. Nel campo **Dimensione finanziaria** fare clic sul pulsante a discesa per aprire la ricerca.
    * Impostare altri valori di dimensione finanziaria in base alle esigenze.  
    * Tutti i valori di dimensione finanziaria vengono modificati quando avviene un trasferimento, sia che il valore sia stato immesso o lasciato vuoto. Ad esempio, se è stato immesso un valore per il BusinessUnit e sono stati lasciati vuoti dimensioni finanziarie Reparto e CostCenter. Se la struttura dei conti consente valori vuoti per CostCenter e Reparto, il trasferimento determinerà che ciascun modello di valore abbia il nuovo valore per BusinessUnit e un valore vuoto per CostCenter e Reparto.  
9. Fare clic su **Aggiorna**.
    * Si ha l'opportunità di visualizzare l'anteprima delle modifiche prima di finalizzare il trasferimento.  
    * Esaminare i risultati prima di trasferire i libri cespiti.  
10. Fare clic su **Trasferisci**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
