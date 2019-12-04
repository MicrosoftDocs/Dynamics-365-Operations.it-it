---
title: Creare e inviare una guida per l'inserimento utilizzando Dynamics 365 Talent - Onboard
description: In questo argomento viene illustrato come utilizzare l'app Microsoft Dynamics 365 Talent - Onboard per creare una guida per l'inserimento dei neoassunti. Questa attività è un primo passaggio fondamentale della strategia di gestione del capitale umano (HCM).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a095fe97b05898403b501763204a462ee8dcc12a
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814630"
---
# <a name="create-and-send-an-onboarding-guide-by-using-dynamics-365-talent---onboard"></a>Creare e inviare una guida per l'inserimento utilizzando Dynamics 365 Talent - Onboard

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Onboard consente di creare guide per l'inserimento da modelli che si possono creare personalmente, da modelli disponibili in una raccolta o creati da zero.

Dopo aver creato una guida per l'inserimento è possibile inviarla a un nuovo assunto. In alternativa, è possibile inviarla a più neoassunti specificati in un file di Microsoft Excel che si scarica dall'app Onboard.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a>Creare una guida per l'inserimento da un modello e inviarla a un nuovo assunto

1. Nel menu a sinistra, selezionare **Modelli**.
2. In **Modelli personali**, selezionare il modello che si desidera impostare come guida di inserimento per il nuovo assunto.
3. Modificare il modello in base alle esigenze. Ricordarsi di salvare il lavoro di tanto in tanto.
4. Dopo aver modificato il modello, selezionare **Crea guida**.

    [![Creazione di una guida per l'inserimento da un modello](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)

5. Nella finestra **Crea guida**, in **A chi è destinato l'onboarding**, immettere il nome o l'indirizzo di posta elettronica del nuovo assunto. Se il nuovo assunto non è ancora presente nel sistema, selezionare **Aggiungi ora** e immettere le informazioni del dipendente.

    ![[Inserimento delle informazioni per la guida per l'inserimento](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. In **Quando devono iniziare**, selezionare una data di inizio.
7. Se la guida per l'inserimento deve essere inviata automaticamente al nuovo assunto in una data specifica, assicurarsi che l'opzione **Programma una data di invio automatica** sia attivata e quindi selezionare la data di invio automatica. Per inviare la guida immediatamente, disattivare l'opzione **Programma una data di invio automatica**.
8. Selezionare **Fine**.
9. Al termine della modifica della guida per l'inserimento, selezionare **Invia** nell'angolo superiore destro. Eseguire quindi uno dei passaggi seguenti:

    - Per inviare al nuovo assunto un collegamento alla guida per l'inserimento, selezionare **copia un link** e selezionare **Copia**.
    - Per personalizzare l'e-mail per la guida per l'inserimento prima di inviarla, selezionare **Personalizzare il messaggio di posta elettronica prima di inviare**, selezionare **Avanti**, personalizzare il messaggio in base alle proprie esigenze e quindi selezionare **Invia**.
    - Per inviare l'e-mail senza personalizzarlo, selezionare **Avanti**, quindi selezionare **Invia**.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a>Creare una guida per l'inserimento da un modello e inviarla a più nuovi assunti

Onboard consente di inviare una guida per l'inserimento a più nuovi assunti nello stesso momento.

1. Nel menu a sinistra, selezionare **Modelli**.
2. In **Modelli personali**, selezionare il modello che si desidera impostare come guida di inserimento per i nuovi assunti.
3. Modificare il modello in base alle esigenze. Ricordarsi di salvare il lavoro di tanto in tanto.
4. Dopo aver modificato il modello, selezionare **Crea guida**.
5. Nella finestra **Crea una guida** selezionare **È necessario effettuare l'onboarding di più utenti contemporaneamente**.

    [![Creazione di una guida per l'inserimento per più nuovi assunti](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)

6. Selezionare **modello della nuova assunzione**.
7. Dopo aver scaricato il file con estensione xlsx, selezionare **Apri**, immettere le informazioni sui dipendenti nella cartella di Excel e salvare e salvare la cartella di lavoro.

    [![Scaricamento del modello di Excel per l'invio della guida per l'inserimento a più nuovi assunti](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)

    > [!NOTE]
    > Prima di poter modificare la cartella di lavoro, è necessario selezionare **Abilita modifica** in Excel.
    > 
    > [![Attivazione della funzione di modifica](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)

8. Trascinare la cartella di lavoro di Excel nell'area designata nella finestra **Crea più guide** oppure fare clic in un punto qualsiasi nell'area per cercare il file nel computer.

    [![Trascinamento della cartella di lavoro modificata](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)

9. Al termine della modifica della guida per l'inserimento, selezionare **Invia** nell'angolo superiore destro. Eseguire quindi uno dei passaggi seguenti:

    - Per inviare ai nuovi assunti un collegamento alla guida per l'inserimento, selezionare **copia un link** e selezionare **Copia**.
    - Per personalizzare l'e-mail per la guida per l'inserimento prima di inviarla, selezionare **Personalizzare il messaggio di posta elettronica prima di inviare**, selezionare **Avanti**, personalizzare il messaggio in base alle proprie esigenze e quindi selezionare **Invia**.
    - Per inviare l'e-mail senza personalizzarlo, selezionare **Avanti**, quindi selezionare **Invia**.

## <a name="create-a-guide-without-using-a-template"></a>Creare una guida senza utilizzare un modello

Non è necessario creare una guida sempre da un modello. Se si preferisce, è possibile crearla da zero.

1. Nel menu a sinistra, selezionare **Guides** e quindi selezionare il pulsante **Aggiunti** (il segno più \[**+**\]).
2. Nella finestra **Crea guida**, in **A chi è destinato l'onboarding**, immettere il nome o l'indirizzo di posta elettronica del nuovo assunto. Se il nuovo assunto non è ancora presente nel sistema, selezionare **Aggiungi ora** e immettere le informazioni del dipendente.

    ![[Inserimento delle informazioni per la guida per l'inserimento](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. In **Quando devono iniziare**, selezionare una data di inizio.
4. Se la guida per l'inserimento deve essere inviata automaticamente al nuovo assunto in una data specifica, assicurarsi che l'opzione **Programma una data di invio automatica** sia attivata e quindi selezionare la data di invio automatica. Per inviare la guida immediatamente, disattivare l'opzione **Programma una data di invio automatica**.
5. Selezionare **Fine**.

## <a name="save-a-guide-as-a-template"></a>Salvare una guida come modello

È possibile salvare una guida per l'inserimento come modello. In questo modo, è possibile risparmiare tempo quando si devono creare più guide.

1. Nel menu a sinistra, selezionare **Guides**.
2. Selezionare il pulsante **Altro** (punti di sospensione \[**...**\]) per la guida da cui si desidera creare un modello, quindi selezionare **Salva come modello**.

    ![[Salvataggio di una guida per l'inserimento come modello](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. Nella finestra **Salva come nuovo modello**, immettere un nome per il nuovo modello e selezionare **Salva**.

## <a name="next-steps"></a>Passaggi successivi

- [Modificare guide e modelli per l'inserimento](./onboard-edit-guides-templates.md)
- [Condividere il contenuto con altri collaboratori](./onboard-share-template.md)
- [Visualizzare lo stato di attività e di dipendenti in fase di inserimento](./onboard-view-status.md)
- [Creare team di assunzione in Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Vedere anche

- [Provare o acquistare l'app Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Novità o modifiche in Dynamics 365 Talent](./whats-new.md)
- [Piani di rilascio](https://docs.microsoft.com/business-applications-release-notes/index)
- [Ottenere supporto per Microsoft Dynamics 365 Talent](./talent-support.md)
