---
title: Utilizzare flussi di lavoro di approvazione del leasing
description: In questo articolo viene illustrato come utilizzare i flussi di lavoro per approvare i leasing di cespite e come tenere traccia dello stato e della cronologia dei flussi di lavoro.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4205b83919f0b3c30a4b5d8e3290af230f538f39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906444"
---
# <a name="use-lease-approval-workflows"></a>Utilizzare flussi di lavoro di approvazione del leasing

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come utilizzare i flussi di lavoro per approvare i leasing di cespite e come tenere traccia dello stato e della cronologia dei flussi di lavoro. I flussi di lavoro aiutano a portare coerenza nella gestione delle approvazioni di leasing fornendo una serie standard di passaggi di approvazione e assegnando utenti specifici che approvano ogni passaggio del processo. Un approvatore può approvare un leasing, rifiutarlo, richiederne una modifica o assegnarlo a un altro utente per l'approvazione. I flussi di lavoro possono anche offrire maggiore visibilità al processo di approvazione consentendo di tenere traccia del loro stato e della cronologia. Inoltre, è possibile visualizzare un elenco di lavoro centralizzato che elenca le attività e le approvazioni assegnate a specifici approvatori.

Prima di utilizzare questa procedura, assicurati che sia stato creato almeno il flusso di lavoro di approvazione del leasing. Se non esiste alcun flusso di lavoro, creane uno. Per informazioni su come configurare un flusso di lavoro, vedi [Configurare flussi di lavoro di approvazione del leasing](set-up-lease-wrkflw.md).

1. Inviare un leasing per l'approvazione. Nella pagina **Dettagli del libro** per il leasing, seleziona **Flusso di lavoro** e quindi seleziona **Invia**.
2. Nella finestra di dialogo che appare, puoi aggiungere un commento. L'approvatore designato vedrà questo commento insieme al leasing. Quando hai finito di inserire il commento, seleziona **Invia**. Il leasing viene inviato al sistema del flusso di lavoro e l'approvatore lo riceve per l'approvazione.
3. Per visualizzare i leasing designati per l'approvazione, vai a **Moduli \> Comune \> Elementi di lavoro \> Elementi di lavoro assegnati a me**.
4. Nella pagina **Elementi di lavoro assegnati a me**, seleziona il collegamento **ID leasing** che vuoi visualizzare. La pagina che appare dipende dai libri di leasing e dai dettagli del leasing a cui hai accesso.
5. Quando hai finito di visualizzare il leasing, seleziona **Flusso di lavoro** e decidi quale azione intraprendere. Le opzioni includono **Approva**, **Rifiuta**, **Richiedi modifica**, **Delega** e **Annullato**. Puoi anche selezionare **Visualizza cronologia** per visualizzare la cronologia delle approvazioni per il leasing selezionato.
6. Dopo aver selezionato un'azione, inserisci un commento per descrivere l'azione. Quando hai finito di inserire il commento, seleziona l'azione **Approvato** nell'elenco.
7. Per visualizzare le azioni di approvazione, torna alla pagina **Dettagli del leasing** dalla pagina **Riepilogo leasing**, quindi seleziona **Flusso di lavoro \> Visualizza cronologia**.

    Puoi visualizzare le attività del flusso di lavoro nella pagina **Storico flusso di lavoro**. Questa pagina mostra i passaggi del flusso di lavoro che sono stati eseguiti nel leasing specifico. Puoi anche utilizzare il campo **Elementi di lavoro** per visualizzare lo stato degli elementi di lavoro assegnati.

8. Per interrompere un flusso di lavoro, nella pagina **Storico flusso di lavoro**, seleziona **Richiama**. Nella finestra di dialogo visualizzata, immetti un commento e quindi seleziona **OK**.
9. Per disattivare un flusso di lavoro o per attivare un flusso di lavoro creato in precedenza, vai a **Leasing cespite \> Imposta \> Flusso di lavoro di leasing**. Quindi, nella pagina **Flusso di lavoro di leasing**, seleziona **Flusso di lavoro \> Versioni**. Per rendere inattivo un flusso di lavoro corrente, seleziona il leasing attivo nella finestra di dialogo della versione del leasing, quindi seleziona **Rendi inattivo**. Per rendere attivo un flusso di lavoro esistente, seleziona il flusso di lavoro e quindi seleziona **Rendi attivo**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
