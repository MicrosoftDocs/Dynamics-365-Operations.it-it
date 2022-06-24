---
title: Configurare ed eseguire l'elaborazione per chiamare un formato ER di esportazione semplice con cui generare un report di Excel
description: Questo articolo fornisce un esempio che mostra come impostare e utilizzare i messaggi elettronici.
author: liza-golub
ms.date: 07/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 9894aabde854189e6fc1b6bb62051747f190e3ec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904588"
---
# <a name="set-up-and-run-processing-to-call-a-simple-exporting-er-format-to-generate-an-excel-report"></a>Configurare ed eseguire l'elaborazione per chiamare un formato ER di esportazione semplice con cui generare un report di Excel

[!include [banner](../includes/banner.md)]

Dopo aver creato il formato ER, averlo mappato alle origini dati e completato, è possibile eseguirlo utilizzando l'area di lavoro **Creazione di report elettronici**. Il report generato può essere salvato localmente.

Per controllare i seguenti aspetti del processo di reporting, è necessario configurare l'elaborazione del messaggio elettronico:

- Registrare informazioni sull'utente che ha generato il report.
- Registrare informazioni su quando il report è stato generato.
- Salva i report generati per i periodi precedenti.

L'esempio che segue mostra come è possibile impostare la messaggistica elettronica per generare un report basato su un formato ER di esportazione per Microsoft Excel. Se si intende seguire questo esempio, il formato ER di esportazione per Excel deve essere già creato, mappato alle origini dati e completato. Inoltre, una sequenza numerica deve essere già stata configurata per i messaggi elettronici.

Quando si crea l'elaborazione, è utile definire dapprima gli stati e le azioni di elaborazione che verranno impostati. L'illustrazione seguente mostra l'elaborazione per questo esempio.

![Schema di elaborazione](media/processing-scheme.png)

## <a name="create-message-statuses"></a>Creare stati del messaggio

1. Accedere a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Stati del messaggio**.
2. Creare i seguenti stati del messaggio:

    - Nuovo
    - Preparato
    - Generato

    ![Stati del messaggio](media/message-statuses.png)

3. Nella riga dello stato **Nuovo** selezionare la casella di controllo **Consenti eliminazione** per consentire agli utenti di eliminare i messaggi con tale stato.

## <a name="create-additional-fields"></a>Creare campi aggiuntivi

1. Accedere a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Campi aggiuntivi**.
2. Aggiungere un campo aggiuntivo e i relativi valori.
3. Impostare **Modifica utente** su **Sì** per consentire agli utenti di modificare il campo.

![Campi aggiuntivi](media/additional-fields.png)

## <a name="create-message-processing-actions"></a>Creare azioni di elaborazione messaggi

Per questo esempio, creeremo le seguenti azioni di elaborazione dei messaggi:

- **Crea messaggio**
- **Aggiorna a preparato**
- **Genera report**
- **Aggiorna a stato iniziale** (facoltativo)

Seguire questi passaggi per creare le azioni.

1. Accedere a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Azioni di elaborazione messaggi**.
2. Creare un'azione denominata **Crea messaggio**. Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Crea messaggio**.
3. Creare un'azione denominata **Aggiorna a preparato** e impostare i seguenti campi:

    - Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Elaborazione utente livello del messaggio**.
    - Nella scheda Dettaglio **Stati iniziali**, nel campo **Stato messaggio**, selezionare **Nuovo**.
    - Nella scheda Dettaglio **Stati di risultati**, nel campo **Stato messaggio**, selezionare **Preparato**. Nel campo **Tipo di risposta**, immettere **Esecuzione completata**.

4. Creare un'azione denominata **Genera report** e impostare i seguenti campi:

    - Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Esportazione creazione di report elettronici**. Nel campo **Mapping formato**, selezionare il formato ER di esportazione. Le opzioni sono **Excel**, **XML**, **JSON**, **Testo** e **Altro**.
    - Nella scheda Dettaglio **Stati iniziali**, nel campo **Stato messaggio**, selezionare **Preparato**.
    - Nella scheda Dettaglio **Stati di risultati**, nel campo **Stato messaggio**, selezionare **Generato**. Nel campo **Tipo di risposta**, immettere **Esecuzione completata**.

    ![Azione Genera report](media/generate-report-action.png)

5. Facoltativo: per consentire agli utenti di generare un report più volte, è possibile creare un'azione denominata **Aggiorna a stato iniziale** e impostare i seguenti campi:

    - Nella scheda Dettaglio **Generale**, nel campo **Tipo di azione**, selezionare **Elaborazione utente livello del messaggio**.
    - Nella scheda Dettaglio **Stati iniziali**, nel campo **Stato messaggio**, selezionare **Generato**.
    - Nella Scheda dettaglio **Stati di risultati**, aggiungere una riga distinta per ognuno dei due stati (**Preparato** e **Nuovo**). Per entrambe le righe, impostare il campo **Tipo di risposta** su **Eseguito correttamente**.

## <a name="electronic-message-processing"></a>Elaborazione messaggio elettronico

Per questo esempio, tutte le azioni devono essere configurate di modo che possano essere eseguite separatamente. Si presuppone che l'utente inizializzerà ogni azione.

1. Accedere a **Imposta** \> **Impostazione** \> **Messaggi elettronici** \> **Elaborazione messaggio elettronico**.
2. Aggiungere un record per l'elaborazione, tutte le azioni definite in precedenza e un campo aggiuntivo.
3. Facoltativo: nella scheda Dettaglio **Ruoli di sicurezza**, definire i ruoli di sicurezza per l'elaborazione per limitare l'accesso a specifico reporting.
4. Accedere a **Imposta** \> **Richieste di informazioni e report** \> **Messaggi elettronici** \> **Messaggi elettronici**.
5. Selezionare **Nuovo** per creare un messaggio. A questo punto, è possibile aggiungere date e una descrizione. È anche possibile aggiornare il valore del campo aggiuntivo come necessario.

    ![Creazione di un messaggio elettronico](media/create-electronic-message.png)

    La griglia nella scheda Dettaglio **Registro azioni** viene automaticamente riempita con un registro di tutte le azioni eseguite sul messaggio.

    È ora possibile eliminare o aggiornare lo stato del messaggio. 

6. Per aggiornare lo stato del messaggio, selezionare **Aggiorna stato**. Nel campo **Nuovo stato** selezionare **Preparato** e selezionare **OK**.

    ![Aggiornamento dello stato del messaggio](media/update-status.png)

    Lo stato del messaggio è aggiornato a **Preparato**.

7. Generare il report selezionando **Genera report**.

    Il report viene generato e lo stato del messaggio e il registro delle azioni del vengono aggiornati.

8. Per visualizzare il report generato, selezionare il pulsante **Allegato** (il simbolo di graffetta) nell'angolo superiore destro della pagina.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
