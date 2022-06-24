---
title: Creare fatture di pagamento
description: In questo articolo viene illustrato come creare fatture di leasing mensili. Puoi creare fatture per singoli leasing oppure utilizzare un processo batch per crearli per più leasing.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymentSchedule
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0ac9efaf6d068377053ae36951f4ad808fcb2438
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886416"
---
# <a name="create-payment-invoices"></a>Creare fatture di pagamento

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Puoi creare fatture mensili per singoli leasing oppure utilizzare un processo batch per crearli per più leasing. La procedura seguente mostra come creare una singola voce di canone di leasing quando il parametro **Paga a fornitore** nella pagina **Configurazione libro di leasing** è attivata.

1. Nella pagina **Riepilogo leasing**, seleziona un leasing, quindi seleziona **Libri \> Scadenziaio dei pagamenti**.
2. Seleziona il pagamento che deve essere effettuato, quindi seleziona **Crea giornale di registrazione**. Ricevi un messaggio che informa che è stato creato un giornale di registrazione a fronte del pagamento selezionato.
3. Seleziona **Giornali di registrazione fatture**, quindi seleziona la fattura che deve essere pagata.
4. Nella scheda **Righe**, rivedi la scrittura contabile prima di registrarla nella contabilità generale.

    > [!NOTE]
    > Per impostazione predefinita, le righe della fattura fornitore create utilizzano il profilo di registrazione fornitore dalla pagina **Parametri di contabilità fornitori**.

5. Seleziona il giornale di registrazione corretto, quindi seleziona la fattura che deve essere pagata.

    Per questo esempio, il parametro **Paga a fornitore** sul libro dei leasing è attivato. Pertanto, la fattura sarà inclusa nel giornale di registrazione fatture. La sezione **Panoramica** mostra un riepilogo della scrittura contabile e la sezione **Righe** mostra i dettagli delle righe di giornale effettive.
    
   Il sistema blocca la modifica di determinati campi finanziari per evitare eventuali scostamenti tra le transazioni e le pianificazioni. Alcuni campi bloccati includono: **Conto**, **Importi**, **Dimensioni finanziarie**, **Valuta** e **Tipo di transazione**. Inoltre, non sarà possibile aggiungere o eliminare righe di scrittura contabile in nessuna scrittura contabile del leasing cespiti, poiché ciò potrebbe causare scostamenti tra le pianificazioni e le transazioni.

    > [!NOTE]
    > Se il parametro **Paga a fornitore** è disattivato, le scritture contabili dei pagamenti verranno elencate nella pagina **Leasing cespite** per il libro dei leasing e il sistema creerà una voce di leasing di cespite invece di una fattura. La voce di canone di leasing verrà registrata nel nome del giornale di registrazione specificato nel campo **Giornale di registrazione leasing mensile**.

6. Dopo la registrazione della transazione, puoi visualizzare le informazioni sulla transazione e il valore contabile dell'obbligazione sul leasing selezionando **Transazioni di passività** nel libro di leasing.

    Nello scadenzario dei pagamenti, verrà selezionata la casella di controllo **Giornale di registrazione registrato** e la riga mostrerà il numero di giornale di registrazione fattura. Dopo aver creato un giornale di registrazione pagamenti e una registrazione per quel giornale, è necessario stornare il movimento prima che possa essere ricreato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
