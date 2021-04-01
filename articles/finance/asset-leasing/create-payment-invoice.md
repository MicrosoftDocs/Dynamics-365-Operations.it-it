---
title: Creare fatture di pagamento
description: In questo argomento viene illustrato come creare fatture di leasing mensili. Puoi creare fatture per singoli leasing oppure utilizzare un processo batch per crearli per più leasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a8b9457b158afaa32718976a7a97f48411be0e1a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5241524"
---
# <a name="create-payment-invoices"></a>Creare fatture di pagamento

[!include [banner](../includes/banner.md)]

Puoi creare fatture mensili per singoli leasing oppure utilizzare un processo batch per crearli per più leasing. La procedura seguente mostra come creare una singola voce di canone di leasing quando il parametro **Paga a fornitore** nella pagina **Configurazione libro di leasing** è attivata.

1. Nella pagina **Riepilogo leasing**, seleziona un leasing, quindi seleziona **Libri \> Scadenziaio dei pagamenti**.
2. Seleziona il pagamento che deve essere effettuato, quindi seleziona **Crea giornale di registrazione**. Ricevi un messaggio che informa che è stato creato un giornale di registrazione a fronte del pagamento selezionato.
3. Seleziona **Giornali di registrazione fatture**, quindi seleziona la fattura che deve essere pagata.
4. Nella scheda **Righe**, rivedi la scrittura contabile prima di registrarla nella contabilità generale.

    > [!NOTE]
    > Per impostazione predefinita, le righe della fattura fornitore create utilizzano il profilo di registrazione fornitore dalla pagina **Parametri di contabilità fornitori**.

5. Seleziona il giornale di registrazione corretto, quindi seleziona la fattura che deve essere pagata.

    Per questo esempio, il parametro **Paga a fornitore** sul libro dei leasing è attivato. Pertanto, la fattura sarà inclusa nel giornale di registrazione fatture. La sezione **Panoramica** mostra un riepilogo della scrittura contabile e la sezione **Righe** mostra i dettagli delle righe di giornale effettive.

    > [!NOTE]
    > Se il parametro **Paga a fornitore** è disattivato, le scritture contabili dei pagamenti verranno elencate nella pagina **Leasing cespite** per il libro dei leasing e il sistema creerà una voce di leasing di cespite invece di una fattura. La voce di canone di leasing verrà registrata nel nome del giornale di registrazione specificato nel campo **Giornale di registrazione leasing mensile**.

6. Dopo la registrazione della transazione, puoi visualizzare le informazioni sulla transazione e il valore contabile dell'obbligazione sul leasing selezionando **Transazioni di passività** nel libro di leasing.

    Nello scadenzario dei pagamenti, verrà selezionata la casella di controllo **Giornale di registrazione registrato** e la riga mostrerà il numero di giornale di registrazione fattura. Dopo aver creato un giornale di registrazione pagamenti e una registrazione per quel giornale, è necessario stornare il movimento prima che possa essere ricreato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]