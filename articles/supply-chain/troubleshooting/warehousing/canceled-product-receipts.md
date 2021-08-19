---
title: Le ricevute di prodotti annullate non aggiornano lo stato della transazione su Registrato
description: Dopo aver annullato la ricevuta di prodotti in un carico in entrata, il sistema aggiorna automaticamente lo stato della transazione di magazzino da Ricevuto a Ordinato.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eae703ce0b2c981518b18c4badd4f90031b902ece62f3ca0837427b306d618b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731105"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>Le ricevute di prodotti annullate non aggiornano lo stato della transazione su Registrato

## <a name="symptoms"></a>Sintomi

Dopo aver eseguito l'azione **Annulla ricevute prodotti** in un carico in entrata, il sistema aggiorna automaticamente lo stato delle transazioni di magazzino da *Ricevuto* a *Ordinato*.

## <a name="resolution"></a>Risoluzione

Quando i documenti di trasporto vengono annullati per i carichi in uscita, lo stato delle transazioni di magazzino rimane *Prelevato*. Tuttavia, quando le ricevute prodotti da un carico in entrata vengono annullate, lo stato delle transazioni di magazzino non viene ripristinato su *Registrato*. Pertanto, dopo l'annullamento di una ricevuta prodotti da un carico in entrata, l'addetto al magazzino deve registrare nuovamente le quantità di articoli per i carichi.

Per ulteriori informazioni, vedi [Registrare le quantità di articoli che arrivano in un carico in entrata](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
