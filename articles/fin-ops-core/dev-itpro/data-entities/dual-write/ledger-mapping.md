---
title: Contabilità generale integrata
description: In questo articolo viene descritta l'integrazione dei dati di contabilità generale tra Finanza e operazioni e altre applicazioni Dynamics 365 tramite Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e83d66f3f8c8927b9baaf99838a4e242e7e011dc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847191"
---
# <a name="integrated-ledger"></a>Contabilità integrata

[!include [banner](../../includes/banner.md)]



In un'applicazione aziendale, i dati della contabilità generale definiscono il core impostato per il modo in cui un'azienda fa affari. Ad esempio, i dati della contabilità generale descrivono l'anno fiscale dell'azienda, le valute in cui opera e i conti utilizzati. In questo articolo viene descritta l'integrazione dei dati finanziari di base.

## <a name="templates"></a>Modelli

I dati della contabilità generale includono una raccolta di mappe della tabella finanziarie di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

App Finanza e operazioni | App di interazione con i clienti     | descrizione
---------------------------------|----------------------------------|------------
[Tassi di cambio CDS](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Piano dei conti](mapping-reference.md#121) | msdyn_chartofaccountses |
[Valute](mapping-reference.md#218) | transactioncurrencies |
[Coppia di valute tasso di cambio](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Tipo di tasso di cambio](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Formato dimensione finanziaria](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Dimensioni finanziarie](mapping-reference.md#128) | msdyn_dimensionattributes |
[Entità integrazione calendario fiscale](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Periodo di calendario fiscale](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Entità integrazione anno calendario fiscale](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Ledger](mapping-reference.md#148) | msdyn_ledgers |
[Conto principale](mapping-reference.md#152) | msdyn_mainaccounts |
[Categorie di conti principali](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
