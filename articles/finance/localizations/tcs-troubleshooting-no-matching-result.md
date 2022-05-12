---
title: Impossibile trovare risultati corrispondenti
description: Questo argomento spiega come risolvere l'errore "Impossibile trovare risultati corrispondenti" nel servizio di calcolo delle imposte.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: c1a343b0b74645d40b0a2582749968cc0a56afd7
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645415"
---
# <a name="no-matching-result-could-be-found"></a>Impossibile trovare risultati corrispondenti

[!include [banner](../includes/banner.md)]

Questo argomento illustra i passaggi per la risoluzione dei problemi che puoi eseguire se viene visualizzato un errore "Impossibile trovare risultati corrispondenti" nel servizio di calcolo delle imposte.

## <a name="symptom"></a>Sintomo

Viene visualizzato il seguente messaggio di errore: "Intestazione/righe - 1, Gruppo di imposte, Impossibile trovare risultati corrispondenti".

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Causa

Il problema si verifica quando l'impostazione della funzionalità in Regulatory Configuration Service (RCS) non è corretta.

## <a name="troubleshoot"></a>Risoluzione dei problemi

1. Scarica il file di risoluzione dei problemi. Per ulteriori informazioni, vedi [Abilitare la modalità debug per risolvere i problemi](tcs-troubleshooting-enable-debug-mode.md).
2. Confronta l'input di calcolo del servizio fiscale con l'impostazione della funzione per risolvere il problema di configurazione.

    L'esempio seguente mostra l'input per il calcolo del servizio fiscale.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    La tabella seguente elenca l'applicabilità del gruppo di imposte in RCS.

    | Header.Business process | Lines.Business Unit | Header.Ship From Zip Code | Gruppo di imposta |
    |-------------------------|---------------------|---------------------------|-----------|
    | Giornale di registrazione                 |                     |                           | Gruppo A   |
    | Vendite                   |                     | 30160                     | Gruppo B   |

    Secondo l'input di calcolo del servizio fiscale, il valore **Processo aziendale** sull'intestazione è **Vendite**, e il valore **Spedisci da CAP** sull'intestazione è **30159**. Questo input si basa sull'impostazione delle regole di applicabilità in RCS. Poiché non esiste una riga corrispondente, si verifica l'errore.

    > [!NOTE]
    > Se il valore nella regola di applicabilità è vuoto, la regola è applicabile a qualsiasi valore.

## <a name="mitigation"></a>Attenuazione

Per risolvere l'errore, effettua le operazioni seguenti.

1. In RCS, vai a **Funzionalità di globalizzazione** \> **Calcolo delle tasse**.
2. Crea una nuova versione della funzionalità.
3. Aggiungi una riga per le informazioni corrispondenti.

    | Header.Business process | Lines.Business Unit | Header.Ship From Zip Code| Gruppo di imposta |
    |-------------------------|---------------------|--------------------------|-----------|
    | Giornale di registrazione                 |                     |                          | Gruppo A   |
    | Vendite                   |                     | 30160                    | Gruppo B   |
    | Vendite                   |                     | 30159                    | Gruppo B   |

4. Pubblica la versione di configurazione della funzionalità.
5. In Microsoft Dynamics 365 Finance, vai a **Imposta** \> **Impostazione** \> **Configurazione imposta** \> **Parametri calcolo imposta**, e seleziona la nuova versione.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
