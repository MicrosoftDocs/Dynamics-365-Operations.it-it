---
title: Valore di campo errato in TaxTrans
description: Questo argomento fornisce informazioni sulla risoluzione dei problemi relativi a valori di campo errati in TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 5c1c034c6037d2e8920d9744903debebb2dc537f2644093d5e1eef66f2681191
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746346"
---
# <a name="incorrect-field-value-in-taxtrans"></a>Valore di campo errato in TaxTrans

[!include [banner](../includes/banner.md)]

Se un valore di campo in **TaxTrans** non è corretto, utilizza le informazioni in questo argomento per provare a risolvere il problema.

## <a name="overview-of-values"></a>Panoramica dei valori
Il seguente elenco mostra come **TaxTrans**, **TaxUncommitted**, e **TmpTaxWorkTrans** sono set di dati simili, ma funzionano in modo diverso.

  - **TaxTrans** è il risultato finale della transazione fiscale registrata mantenuto nel database.
  - **TaxUncommitted** è il risultato intermedio dell'imposta calcolata mantenuto nel database (se applicabile), che verrà utilizzato successivamente nella registrazione.
  - **TmpTaxWorkTrans** è il risultato temporaneo dell'imposta calcolata nella tabella in memoria (Tipo di tabella = InMemory).

Se trovi la causa principale di una colonna **TaxTrans** errata, hai anche trovato la causa principale di una colonna **TaxUncommitted** o **TmpTaxWorkTrans** errata. Questo perché le tre colonne vengono copiate l'una dall'altra.

In genere, durante il calcolo delle imposte, **TmpTaxWorkTrans** viene generato e quindi, se applicabile, **TaxUncommitted** viene generato. Durante la registrazione delle imposte, **TaxTrans** viene generato.


## <a name="add-breakpoints"></a>Aggiungere punti di interruzione
Per aggiungere punti di interruzione, completa i passaggi seguenti. 

1. Aggiungi estensioni e punti di interruzione in *insert()* e *update()* nelle estensioni come mostrato di seguito.

     - **TaxTrans**

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TaxUncommitted**

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - **TmpTaxWorkTrans**

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. In alternativa, puoi aggiungere direttamente i punti di interruzione quando **TaxUncommitted** non è incluso.

     - *TaxTrans.insert()*, *TaxTrans.update()*
     - *TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*

## <a name="reproduce-and-debug"></a>Riprodurre ed eseguire il debug

Dopo aver impostato i punti di interruzione, ogni modifica alla persistenza dei dati è visibile durante il debug. Per trovare la causa principale di una colonna errata di **TaxTrans**, **TaxUncommitted**, o **TmpTaxWorkTrans**, rivedi e prendi nota dei seguenti elementi:

- L'ultimo punto di interruzione in cui la colonna è corretta.
- Il primo punto di interruzione in cui la colonna è errata.
- Cosa succede tra questi due punti.

## <a name="determine-whether-customization-exists"></a>Determinare se esiste la personalizzazione
Se hai completato i passaggi nelle sezioni precedenti ma non il problema persiste, determina se esiste la personalizzazione. Se non esiste alcuna personalizzazione, contattare il supporto Microsoft per assistenza.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

