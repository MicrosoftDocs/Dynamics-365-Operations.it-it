---
title: Sincronizzare l'impostazione fiscale dal servizio di calcolo delle imposte in Dynamics 365 Finance
description: Questo articolo spiega come sincronizzare i dati master dell'impostazione delle imposte dal servizio di calcolo delle imposte in Microsoft Dynamics 365 Finance.
author: EricWangChen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.custom: intro-internal
ms.search.form: TaxIntegration, TaxServiceParameters
ms.openlocfilehash: 315f2b27a64906ca0fc404d704d0b170dbfa48c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283855"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Sincronizzare l'impostazione fiscale dal servizio di calcolo delle imposte in Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Questo articolo spiega come sincronizzare i dati master dell'impostazione delle imposte dal servizio di calcolo delle imposte in Microsoft Dynamics 365 Finance.

Dopo aver completato i passaggi di configurazione richiesti in [Introduzione al calcolo delle imposte](global-get-started-with-tax-calculation-service.md), i seguenti dati di configurazione delle imposte vengono sincronizzati automaticamente dal Servizio di calcolo delle imposte in Finance.

## <a name="sales-tax-code"></a>Codice IVA

| Servizio di calcolo delle imposte           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Codice imposta                          | Codice IVA                      |
| Description                       | Name                                |
| Input utente                        | Periodo di liquidazione                   |
| Input utente                        | Gruppo registrazione contabile                |
| Input utente                        | Valuta IVA                  |
| È configurata un'aliquota fiscale negativa | Consenti aliquota IVA negativa |

## <a name="tax-value"></a>Valore imposta

| Servizio di calcolo delle imposte | Finance                   |
| ----------------------- | ------------------------- |
| Dalla data transazione   | Data iniziale                 |
| Alla data transazione     | Data finale                   |
| Importo minimo          | Limite minimo             |
| Quantità massima          | Limite massimo             |
| Aliquota IVA                | Valore                     |
| Aliquota non deducibile     | % non deducibile |

## <a name="tax-limits"></a>Limiti d'imposta

| Servizio di calcolo delle imposte | Finance           |
| ----------------------- | ----------------- |
| Dalla data transazione   | Data iniziale         |
| Alla data transazione     | Data finale           |
| Importo imposta minimo      | IVA minima |
| Importo imposta massimo      | IVA massima |

## <a name="sales-tax-group"></a>Fascia IVA

| Servizio di calcolo delle imposte                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Gruppo di imposte                                       | Fascia IVA                            |
| Codici imposta in questo gruppo di imposte                  | Codici IVA in questo gruppo di IVA |
| Il codice imposta è contrassegnato come **Esente**         | Esente                                     |
| Il codice imposta è contrassegnato come **Esente**         | Codice esenzione                                |
| Il codice imposta è contrassegnato come **Reverse charge**. | Reverse charge                             |
| Il codice imposta è contrassegnato come **Imposta di utilizzo**        | IVA intracomunitaria                                    |

## <a name="item-sales-tax-group"></a>Fascia IVA articoli

| Servizio di calcolo delle imposte             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Gruppo d'imposta dell'articolo                      | Fascia IVA articoli                            |
| Codici imposta in questo gruppo di imposte articoli | Codici IVA in questo gruppo di IVA articoli |

Una volta completata la sincronizzazione, continua a gestire i parametri rimanenti in Finance per scopi di registrazione e reporting.

> [!NOTE]
> La sincronizzazione dell'impostazione imposte da Finance al servizio di calcolo delle imposte non è supportata. Per un ambiente Finance esistente, crea prima l'impostazione imposte nel servizio di calcolo delle imposte. Quindi sincronizza nuovamente i dati di impostazione con l'ambiente Finance.
