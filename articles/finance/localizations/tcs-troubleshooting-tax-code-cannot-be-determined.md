---
title: Non è possibile determinare il codice imposta
description: Questo argomento spiega come risolvere l'errore "Impossibile determinare il codice imposta" nel servizio di calcolo delle imposte.
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
ms.openlocfilehash: 3c0914f0013ad2de61cd5a59e3092fef149742e4
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645404"
---
# <a name="tax-code-cannot-be-determined"></a>Non è possibile determinare il codice imposta

[!include [banner](../includes/banner.md)]

Questo argomento illustra i passaggi per la risoluzione dei problemi che puoi eseguire se viene visualizzato un errore "Impossibile determinare il codice imposta" nel servizio di calcolo delle imposte.

## <a name="symptom"></a>Sintomo

Viene visualizzato il seguente messaggio di errore: "Intestazione/righe - 1, Impossibile determinare il codice imposta". In alternativa, puoi trovare l'errore nel file di risoluzione dei problemi, come mostrato nell'esempio seguente. Per ulteriori informazioni, vedi [Abilitare la modalità debug per risolvere i problemi](tcs-troubleshooting-enable-debug-mode.md).

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
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
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

Il problema si verifica probabilmente perché il gruppo di imposte e il gruppo di imposte articolo non si intersecano.

## <a name="troubleshoot"></a>Risoluzione dei problemi

Per risolvere il problema, procedi come segue.

1. Nel file di risoluzione dei problemi, verifica che il gruppo di imposte e il gruppo di imposte articolo siano state determinate. Se i valori per **Gruppo di imposte** e **Gruppo di imposte articolo** sono vuoti, il l gruppo di imposte e il gruppo di imposte articolo non sono stati determinati. Se sono stati determinati, i risultati potrebbero non essere corretti.

    Di seguito è riportato un esempio di file di risoluzione dei problemi.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
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

2. Verifica che l'opzione **Sostituisci IVA** nella scheda **Impostazione** dei dettagli della riga dell'ordine cliente sia abilitata.

    - Se è abilitato, i codici imposta sono determinati dai valori **Gruppo di imposte** e **Gruppo di imposte articolo** immessi nella riga della transazione. Verifica che questi valori siano inseriti correttamente.
    - Se non è abilitata, verifica che siano stati impostati i valori corretti per i campi **Applicabilità del gruppo di imposte** e **Applicabilità del gruppo di imposte articolo**. Per ulteriori informazioni, vedi [Impossibile trovare risultati corrispondenti](tcs-troubleshooting-no-matching-result.md).

3. Se il gruppo di imposte e il gruppo di imposte articolo sono stati determinati correttamente, determina se esiste un'intersezione tra loro.

    1. In RCS, vai a **Funzionalità fiscali** \> **Codici imposta e gruppi** \> **Gruppo di imposte**.

        | Line.Tax Group | Codici imposta |
        |----------------|-----------|
        | Gruppo A        | A         |

    2. Vai a **Funzionalità fiscali** \> **Codici imposta e gruppi** \> **Gruppo di imposte articolo**.

        | Line.Item Tax Group | Codici imposta |
        |---------------------|-----------|
        | Gruppo B             | B         |

    Se non esiste un'intersezione tra il gruppo di imposte e il gruppo di imposte articolo, il codice imposta non verrà determinato.

## <a name="mitigation"></a>Attenuazione

1. Esegui ogni passaggio della sezione [Risoluzione dei problemi](#troubleshoot) di questo argomento e correggi l'installazione come richiesto. Se il gruppo di imposte e il gruppo di imposte articolo non sono stati determinati correttamente, vedi [Impossibile trovare risultati corrispondenti](tcs-troubleshooting-no-matching-result.md).
2. Se non esiste un'intersezione tra il gruppo di imposte e il gruppo di imposte articolo, crea una nuova versione della funzionalità in RCS e correggi l'impostazione.

    - Vai a **Funzionalità fiscali** \> **Codici imposta e gruppi** > **Gruppo di imposte articolo**.

        | Line.Item Tax Group | Codici IVA |
        |---------------------|-----------|
        | Gruppo B             | A;B       |

    Il codice imposta sarà determinato come **A**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
