---
title: Eseguire aggiornamenti di fatture per i resi
description: Questa funzionalità consente di supportare i processi aziendali delle organizzazioni nelle quali gli ordini di reso e gli ordini cliente vengono fatturati contemporaneamente e da parte di uno stesso utente.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3890ea31ee899f021405fb5475b20f9dd63c1e2e103b63af8b53bccc53d0781f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730156"
---
# <a name="perform-invoice-updates-for-returns"></a>Eseguire aggiornamenti di fatture per i resi 

[!include [banner](../includes/banner.md)]


Un ordine di reso è un tipo di ordine cliente contrassegnato come reso. Per generare fatture per gli ordini di reso viene pertanto utilizzata la pagina elenco **Tutti gli ordini cliente** anziché il modulo **Ordini di reso**. Questa funzionalità consente di supportare i processi aziendali delle organizzazioni nelle quali gli ordini di reso e gli ordini cliente vengono fatturati contemporaneamente e da parte di uno stesso utente.

Poiché la fattura per un reso è per un importo negativo, viene denominata nota di accredito.

Quando si imposta l'aggiornamento della fattura per l'elaborazione batch, lo stato della riga di reso dell'ordine cliente di tipo **Ordine di reso** deve essere **Ricevuto**, che indica che il documento di trasporto dell'ordine è stato aggiornato.

## <a name="post-an-invoice-for-a-return-order"></a>Registrare una fattura per un ordine di reso

1.  Fare clic su **Contabilità clienti** \> **Comune** \> **Ordini cliente** \> **Tutti gli ordini cliente**.

2.  Selezionare un ordine cliente per il quale **Ordine di reso** è visualizzato nel campo **Tipo di ordine**.

3.  Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, fare clic su **Fattura**.

4.  Selezionare la casella di controllo **Registrazione** nella scheda **Parametri**.

5.  Verificare le informazioni del modulo e apportare le modifiche necessarie.

6.  Fare clic su **OK**. La nota di accredito è stata registrata.

## <a name="see-also"></a>Vedere anche

[Aggiornamenti dei documenti di trasporto per i resi](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]