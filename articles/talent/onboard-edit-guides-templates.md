---
title: Modificare guide e modelli per l'inserimento in Dynamics 365 Talent - Onboard
description: In questo argomento viene descritto come aggiungere attività e altre informazioni nelle guide e nei modelli per l'inserimento in Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
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
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 24369a878e95076783d670894236d56dca18e765
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812881"
---
# <a name="edit-onboarding-guides-and-templates-in-dynamics-365-talent---onboard"></a>Modificare guide e modelli per l'inserimento in Dynamics 365 Talent - Onboard

[!include [banner](includes/banner.md)]

Dopo aver creato una guida o un modello per l'inserimento di nuovi assunti in Microsoft Dynamics 365 Talent: Onboard, è necessario aggiungere un'introduzione, attività, contatti e risorse. Onboard consente di includere contenuti dettagliati nelle guide per l'inserimento, tra cui:

- Video di YouTube
- Presentazioni di Microsoft Sway
- App di Microsoft PowerApps
- Video di Microsoft Stream
- Moduli di Microsoft Forms
- Iframe con contenuto Web

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Modificare le introduzioni o le attività importate da un modello

Se si crea una guida per l'inserimento da un modello o si importano attività da un modello in un altro, si noterà un pulsante **Blocca** sulle attività importate. Queste attività sono definite *attività gestite*.

[![Attività gestite](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

Quando si seleziona un'attività gestita, è possibile vedere il modello di origine in cima all'attività.

[![Origine di un'attività gestita](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Se si modifica un'attività in un modello, Onboard distribuisce le modifiche a tutti i modelli e alle guide non ancora inviate che si basano di quel modello. Se si seleziona una guida non inviata basata su un modello modificato e si seleziona la scheda **Attività** nella guida, verrà visualizzato un avviso indicante che la guida è stata modificata. Per chiudere la notifica, fare clic su **OK**. 

[![Notifica di modifica](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

Accanto alle attività aggiornate verrà visualizzato un punto nero.

[![Attività modifica](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

Non è possibile modificare attività gestite al di fuori del modello originale, eccetto per aggiungere un assegnatario, una data di scadenza o altre informazioni nella sezione di destra dell'attività.

Se si desidera modificare un'attività gestita o se non si desidera che un'attività riceva gli aggiornamenti dal modello di origine, selezionare il pulsante **Blocca** per l'attività in questione. Il pulsante **Blocca** non verrà più visualizzato. L'attività non sarà più gestita dal modello originale e non riceverà più gli aggiornamenti dal modello. Gli aggiornamenti che si apportano a un'attività non influiscono sul modello originale.

Se si elimina un'attività da una guida e si distribuiscono le modifiche dal modello della guida, l'attività resterà eliminata nella guida.

> [!NOTE]
> I contatti e le risorse non vengono gestiti dai modelli. Anche le sezioni non vengono gestite, pertanto se si aggiunge o si modifica una sezione in un modello, le modifiche non verranno distribuite a tutte le altre guide o agli altri modelli che utilizzano il modello modificato.
> 
> Se si aggiungono nuove attività a un modello, le nuove attività vengono distribuite alle guide e ai modelli basati su tale modello e le nuove attività vengono visualizzate nella parte superiore.

## <a name="import-activities-from-another-template"></a>Importare attività da un altro modello

È possibile importare le attività da uno o più modelli in una guida o un modello.

1. Selezionare la guida o il modello che si desidera modificare.

2. Selezionare la scheda **Attività**.

3. Selezionare la scheda **Importa** nella sezione a destra.

   [![Importare le attività](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. Per visualizzare in anteprima le attività in una nuova scheda del browser in uso, selezionare il pulsante **Apri in una nuova scheda** in un template qualsiasi.

   [![Importare le attività](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Trascinare il modello desiderato nella posizione nel modello della guida in cui si desidera visualizzare le attività. Continuare a modificare la guida o il modello.

Le attività importate conterranno un pulsante **Blocca**, che indica che sono gestite dal modello da cui sono state importate. Quando si apportano modifiche al modello importato, verranno aggiornate le attività nel modello in cui sono state importate. Tuttavia, le modifiche non verranno distribuite automaticamente alle altre guide create dal modello originale.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Distribuire le modifiche da un modello ad altri modelli o altre guide

Se si modifica un modello contenente attività utilizzate in altri modelli o altre guide, è necessario distribuire le modifiche se si desidera che vengano visualizzare negli altri modelli o nelle altre guide.

Se non si è certi se le attività del modello vengono utilizzate in altri modelli o guide, selezionare la scheda **Utilizzata in** per vedere dove appaiono tali attività.

   [![Visualizzare le guide e i modelli in cui sono utilizzate le attività](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

Per distribuire le modifiche:

1. Salvare le modifiche facendo clic su **Salva**. In caso contrario, verrà chiesto di salvare le modifiche nel passaggio successivo.

2. Selezionare **Esegui push delle modifiche**.

   
## <a name="add-or-edit-an-introduction"></a>Aggiungere o modificare un'introduzione

1. Nella scheda **Introduzione**, immettere un titolo per la guida e un messaggio di apertura. Per utilizzare il testo di esempio, selezionare **Usa questo messaggio**.

    [![Scheda Introduzione in un modello di Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. Utilizzare i pulsanti di formattazione per formattare i test in base alle proprie esigenze o per aggiungere immagini o collegamenti.
3. Selezionare **Salva** per salvare il lavoro.

## <a name="add-or-edit-activities"></a>Aggiungere o modificare attività

1. Nella scheda **Attività**, trascinare gli elementi da destra nell'area di modifica.
2. Per organizzare la guida in sezioni, trascinare l'elemento **Nuova sezione** nell'area di modifica e immettere un nome e una descrizione facoltativa per la sezione.

    ![[Aggiunta di una nuova sezione a una guida o a un modello per l'inserimento](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Per aggiungere attività che il nuovo assunto deve completare, trascinare l'elemento **Nuova attività** nell'area di modifica, quindi immettere un nome e una descrizione per l'attività.

    ![[Aggiunta di una nuova attività a una guida o a un modello per l'inserimento](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Aggiungere contenuto dettagliato alla guida per l'inserimento:

    - Per aggiungere un video di YouTube, trascinare l'elemento **YouTube** nell'area di modifica, immettere un nome e una descrizione per l'attività e immettere l'URL del video di YouTube.
    - Per aggiungere una presentazione o una newsletter di Sway, trascinare l'elemento **Sway** nell'area di modifica, immettere un nome e una descrizione per l'attività, quindi immettere l'URL incorporato per la presentazione o la newsletter di Sway.
    - Per aggiungere un'app di Microsoft Power Apps, trascinare l'elemento **Power Apps** nell'area di modifica, immettere un nome e una descrizione per l'attività, quindi selezionare l'app di Power Apps desiderata o immettere l'ID dell'app di Power Apps.
    - Per aggiungere un video di Microsoft Stream, trascinare l'elemento **Microsoft Stream** nell'area di modifica, immettere un nome e una descrizione per l'attività e immettere l'URL del video di Microsoft Stream.
    - Per aggiungere un modulo di Microsoft Forms, trascinare l'elemento **Microsoft Forms** nell'area di modifica, immettere un nome e una descrizione per l'attività, immettere l'URL del modulo di Microsoft Forms e specificare le dimensioni dell'area della schermata.
    - Per aggiungere un iframe con contenuto Web, trascinare l'elemento **Contenuto Web (iframe)** nell'area di modifica, immettere un nome e una descrizione per l'attività, immettere l'URL del contenuto Web e specificare le dimensioni dell'area della schermata.

    ![[Aggiunta di contenuto dettagliato a una guida o a un modello per l'inserimento](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Facoltativo: nell'area a destra di ogni attività, assegnare l'attività a una persona o a un ruolo specifico, aggiungere una data di scadenza e un contatto e assegnare un colore per la categoria. Quando si assegna un'attività a una persona o a un ruolo, viene creata un'attività per ciascun individuo. Questa attività appare nel menu **Attività** in Onboard.

    [![Assegnare un'attività in una guida o in un modello per l'inserimento](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. Selezionare **Salva** per salvare il lavoro.

Per eliminare un'attività o una sezione, selezionare il pulsante **Elimina** (il simbolo del cestino) nell'angolo superiore destro dell'attività o della sezione.

Per ridisporre le attività e le sezioni, trascinarle in una nuova posizione.

## <a name="add-or-edit-contacts"></a>Aggiungere o modificare i contatti

È possibile aggiungere contatti che possano essere utili al nuovo assunto nell'inserimento nell'ambiente lavorativo dal primo giorno. Tali contatti possono essere selezionatori, colleghi di team, altri neoassunti, mentori, amministratori e personale del supporto IT.

1. Nella scheda **Contatti**, selezionare **Nuovo contatto**.
2. Nella finestra di dialogo **Aggiungi membro del team**, immettere il nome della persona o l'indirizzo e-mail, immettere una breve descrizione che indichi in che modo il contatto può aiutare il nuovo assunto, quindi selezionare **Aggiungi**. 

    ![[Aggiunta di contatti a una guida o a un modello per l'inserimento](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    In alternativa, è possibile selezionare uno o più contatti in **Suggerimenti**.

3. Selezionare **Salva** per salvare il lavoro.

Per eliminare un contatto, fare clic su **Elimina** (il simbolo del cestino) a destra del contatto.

Per modificare un contatto, fare clic su **Modifica** (il simbolo della matita) a destra del contatto.

## <a name="add-or-edit-resources"></a>Aggiungere o modificare le risorse

È possibile aggiungere file, mappe e collegamenti utili nella sezione **Risorse** della guida per l'inserimento.

1. Nella scheda **Risorse**, selezionare **Nuova risorsa**.
2. Eseguire uno dei passaggi riportati di seguito.

    - Per aggiungere un file, selezionare la scheda **File** e trascinare il file nell'area designata. (In alternativa, fare clic in un punto qualsiasi dell'area per cercare il file nel computer oppure selezionare **Sfoglia OneDrive**). Immettere un nome per il file e selezionare **Aggiungi**.
    - Per aggiungere un collegamento, selezionare la scheda **Collegamento**, immettere un nome e un indirizzo per il collegamento, quindi selezionare **Aggiungi**.
    - Per aggiungere una mappa, selezionare la scheda **Mappa**, immettere un nome e un indirizzo per la mappa, quindi selezionare **Aggiungi**. Onboard includerà una mappa dell'indirizzo specificato.

    ![[Aggiunta di una risorsa a una guida o a un modello per l'inserimento](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. Selezionare **Salva** per salvare il lavoro.

Per eliminare una risorsa, fare clic su **Elimina** (il simbolo del cestino) a destra della risorsa.

Per modificare una risorsa, fare clic su **Modifica** (il simbolo della matita) a destra della risorsa.

## <a name="next-steps"></a>Passaggi successivi

- [Condividere il contenuto con altri collaboratori](./onboard-share-template.md)
- [Visualizzare lo stato di attività e di dipendenti in fase di inserimento](./onboard-view-status.md)
- [Creare team di assunzione in Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Vedere anche

- [Provare o acquistare l'app Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Novità o modifiche in Dynamics 365 Talent](./whats-new.md)
- [Piani di rilascio](https://docs.microsoft.com/business-applications-release-notes/index)
- [Ottenere supporto per Microsoft Dynamics 365 Talent](./talent-support.md)
