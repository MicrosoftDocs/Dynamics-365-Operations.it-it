---
title: Sconto sulla spedizione
description: Questo articolo descrive le funzionalità relative allo sconto sulla spedizione in Microsoft Dynamics 365 Commerce e la configurazione necessaria per utilizzarle.
author: ShalabhjainMSFT
ms.date: 08/23/2020
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2019-01-31
ms.openlocfilehash: 74cfe5246ad72cbdedd0ed4e3b3394bf7277919e
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473852"
---
# <a name="shipping-discount"></a>Sconto sulla spedizione

[!include [banner](includes/banner.md)]

Questo articolo descrive le funzionalità relative allo sconto sulla spedizione in Microsoft Dynamics 365 Commerce e la configurazione necessaria per utilizzarle.

La spedizione gratuita o scontata è un fattore che influisce sulle decisioni di acquisto online dei clienti. Per aumentare i ricavi per transazione, molti rivenditori utilizzano la spedizione gratuita per spingere i clienti ad acquistare ulteriori articoli.

Commerce supporta una funzionalità di sconto sulla spedizione che consente ai rivenditori di configurare una percentuale di sconto sulle spese di spedizione per un metodo di spedizione specifico quando l'importo totale delle vendite degli articoli idonei nella transazione soddisfa specifici criteri. Un esempio di scenario che utilizza la funzionalità di sconto sulla spedizione è "Spendi 50 USD o più per ottenere la spedizione gratuita".

## <a name="prerequisites"></a>Prerequisiti

La funzionalità di sconto sulla spedizione è supportata dalle funzionalità relative alle [spese automatiche avanzate omnicanale](/dynamics365/unified-operations/retail/omni-auto-charges). Affinché la funzionalità di sconto sulla spedizione funzioni, devi abilitare la configurazione **Utilizza spese automatiche avanzate** nella scheda **Ordini cliente** della pagina **Parametri di Commerce** in Commerce headquarters. I rivenditori possono utilizzare la funzionalità Spese automatiche avanzate per impostare vari tipi di spese, come gestione, installazione e smaltimento.

Lo sconto sulla spedizione viene applicato solo alle spese di spedizione. Pertanto, un rivenditore deve specificare quali sono le spese di spedizione. Per specificare le spese di spedizione, in Commerce headquarters, vai a **Impostazione canale \> Spese \> Codice spese** e imposta l'opzione **Spese di spedizione** su **Sì** per le spese desiderate.

![Specificare una spesa come spesa di spedizione.](./media/Specify_shipping_charge.png)

## <a name="configuration"></a>Configurazione

La funzionalità di sconto sulla spedizione è basata su livelli e supporta solo il tipo di calcolo **Percentuale di sconto**. Per impostare uno sconto sulla spedizione, in Commerce headquarters, vai a **Prezzi e sconti \> Sconto soglia spedizione**. Puoi quindi specificare la modalità di consegna a cui si applica lo sconto, definire una o più soglie di importo e impostare la percentuale di sconto per ogni soglia. Puoi anche configurare un elenco di categorie o prodotti come articoli idonei. In tal modo, verrà conteggiato solo l'importo delle vendite rispetto a quegli articoli in una transazione quando il motore di determinazione dei prezzi valuta se il totale della transazione soddisfa la soglia.

> [!NOTE]
> A differenza di altri tipi di sconto, lo sconto sulla spedizione non crea righe di sconto, ma modifica direttamente le spese di spedizione e aggiunge il nome dello sconto alla descrizione delle spese.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
