---
title: Registrare l'entrata di merci sull'ordine fornitore
description: Questa articolo descrive come registrare l'entrata delle merci direttamente su un ordine fornitore.
author: GalynaFedorova
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22baf6d0f6db04b3c6ce3c09ee8cb286e9a1e590
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882462"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrare l'entrata di merci sull'ordine fornitore

[!include [banner](../../includes/banner.md)]

Questa articolo descrive come registrare l'entrata delle merci direttamente su un ordine fornitore. È inoltre possibile registrare l'entrata prodotti nel magazzino e poi registrarla successivamente sull'ordine fornitore. Quest'attività viene eseguita tipicamente da un addetto acquisti o un coordinatore contabilità fornitori. L'esempio indicato in questa guida può essere utilizzato nella società di dati dimostrativi USMF. L'esempio comprende i passaggi per creare un ordine fornitore semplice in modo da poter eseguire la procedura come guida attività. Se si seguisse la procedura utilizzando i propri dati, si dovrebbe iniziare con la sottoattività **Registrare l'entrata dei prodotti**.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Preparare un nuovo ordine fornitore per l'entrata delle merci
1. Passare a **pannello di navigazione > Moduli > Approvvigionamento > Ordini fornitore > Tutti gli ordini fornitore**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto fornitore** immettere `US-101`.
4. Selezionare **OK**.
5. Nel campo **Numero articolo** immettere `M0001`.
6. Nel campo **Quantità** immettere `5`.
7. Nel riquadro azioni fare clic su **Acquisto**.
8. Selezionare **Conferma**.

## <a name="record-receipt-of-goods"></a>Registrare l'entrata dei prodotti
1. Nel riquadro azioni fare clic su **Ricevimento**.
2. Selezionare **Entrata prodotti**. Il campo **Quantità** permette di selezionare opzioni differenti per la quantità che volete ricevere. Ad esempio, se una quantità precedentemente è stata registrata nel magazzino, potete selezionare **Quantità registrata**. Per questo esempio, usare il valore **Quantità ordinata**.
3. Espandere la sezione **Panoramica**.
4. Digitare un valore nel campo **Entrata prodotti**. Questo campo è usato per immettere un riferimento che sarà usato come giustificativo per il giornale di registrazione entrata prodotti.  
5. Espandere la sezione **Righe**.
6. Impostare **Quantità** su '4'. Qui potete specificare manualmente la quantità che si sta ricevendo per ogni riga sull'ordine.  
7. Selezionare **OK**. Le merci ora sono state registrate come ricevute sull'ordine fornitore e un giornale di registrazione entrata prodotti è stato creato come documento per riflettere questo. Potete usare l'azione Entrata prodotti per esaminare i giornali di registrazione creati con l'ordine fornitore e vedere che cosa è stato ricevuto e quando.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]