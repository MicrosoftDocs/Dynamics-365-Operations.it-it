---
title: Utilizzare i gruppi di pubblicazione
description: Questo argomento descrive la funzionalità dei gruppi di pubblicazione in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a83affb5b383b50317ddf53de4d3bf565f0d9439
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413565"
---
# <a name="work-with-publish-groups"></a>Utilizzare i gruppi di pubblicazione


[!include [banner](includes/banner.md)]

Questo argomento descrive la funzionalità dei gruppi di pubblicazione in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I siti Web di e-commerce vengono costantemente aggiornati con nuovi contenuti durante tutto l'anno. Gli aggiornamenti sono spesso pubblicati in batch in corrispondenza di eventi di e-commerce impegnativi quali festività, campagne di marketing stagionali o lanci promozionali. Questi aggiornamenti richiedono spesso che gruppi di contenuti del sito Web (ad esempio pagine, immagini, frammenti e modelli) vengano preparati, convalidati e pubblicati contemporaneamente con un'unica azione.

La possibilità di raggruppare gli elementi in insiemi logici che pubblicano insieme gli elementi, in cui ogni set ha il proprio ciclo di vita, offre molti vantaggi agli autori del sito. In Commerce, questi set logici sono noti come gruppi di pubblicazione. Consentono agli autori del sito di tenere traccia dei set insiemi di aggiornamenti come entità configurabili, testabili e pubblicabili.

Gli autori possono visualizzare in anteprima gli aggiornamenti in un gruppo di pubblicazione approntato senza impatto sul sito Live o su altri gruppi di pubblicazione autonomi. Gli autori possono quindi pianificare l'azione di pubblicazione per pubblicare contemporaneamente tutti gli elementi nel gruppo di pubblicazione sul sito Live. La possibilità di raggruppare, visualizzare in anteprima e pianificare gli aggiornamenti per la pubblicazione è importante per molte aziende di livello enterprise che generano considerevoli ricavi annuali intorno ad attività cardine di aggiornamento del sito basate su eventi.

Le aziende possono sostenere costi dovuti a implementazione lente o non valide di contenuti su cui si verificano problemi. I gruppi di pubblicazione aiutano a garantire che i lanci siano organizzati, convalidati e pubblicati in tempo. Che siano grandi o piccoli, i gruppi di pubblicazione forniscono un prezioso set di strumenti che aiuta gli autori a organizzare e semplificare le attività di aggiornamento del sito in corso.

## <a name="when-to-use-publish-groups"></a>Quando utilizzare i gruppi di pubblicazione

Puoi utilizzare gruppi di pubblicazione ogni volta che devi mettere preparare e pubblicare più documenti insieme. Ad esempio, se il sito Web aggiorna i contenuti ogni stagione, è possibile creare gruppi di pubblicazione per questi movimenti di marketing stagionali. Il gruppo di pubblicazione "Aggiornamento stagionale autunnale" potrebbe contenere nuove immagini stagionali, frammenti con messaggi di marketing stagionali, pagine che includono raccolte di prodotti stagionali o altri aggiornamenti di siti Web stagionali.

Un vantaggio dei gruppi di pubblicazione è la possibilità di approntare più aggiornamenti in parallelo. Ad esempio, subito dopo l'aggiornamento per il gruppo di pubblicazione "Aggiornamento stagionale autunnale", potrebbe esserci un aggiornamento del contenuto per un fine settimana festivo specifico. In questo caso, è possibile approntare i contenuti per il gruppo di pubblicazione "Aggiornamento stagionale autunnale" contemporaneamente all'approntamento di contenuti per un successivo gruppo di pubblicazione "Aggiornamento vacanze autunnali". Ogni gruppo di pubblicazione contiene un proprio set unico di pagine, immagini, frammenti, modelli e così via. È possibile organizzare, visualizzare in anteprima e convalidare questi due gruppi di pubblicazione in modo indipendente ma su una sequenza temporale simultanea. Ogni gruppo di pubblicazione può quindi essere pianificato per essere pubblicato sul tuo sito in date e orari specifici.

## <a name="turn-on-the-publish-groups-feature"></a>Attivare la funzionalità dei gruppi di pubblicazione

La funzionalità dei gruppi di pubblicazione è facoltativa e deve essere attivata per il sito.

Per attivare la funzionalità di gruppi di pubblicazione per il sito negli strumenti di creazione di Commerce, procedere nel seguente modo.

1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.
1. In **Impostazioni sito**, selezionare **Funzionalità**.
1. Impostare l'opzione **Gruppi di pubblicazione** su **Attiva**.

## <a name="create-a-publish-group"></a>Creare un gruppo di pubblicazione

Per creare un gruppo di pubblicazione per il sito negli strumenti di creazione di Commerce, procedere nel seguente modo.

1. Nel riquadro di spostamento sinistro, selezionare **Gruppi di pubblicazione**.
1. Nella barra dei comandi superiore, selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea gruppo di pubblicazione**, in **Nome gruppo di pubblicazione**, inserisci un nome descrittivo. Selezionare **OK**.

## <a name="set-the-publish-group-authoring-context"></a>Impostare il contesto di creazione del gruppo di pubblicazione

In Commerce, il contesto di creazione predefinito è il contesto del sito Live. Il contesto di creazione del sito Live è la visualizzazione predefinita in cui è possibile visualizzare e apportare modifiche direttamente al sito Web senza utilizzare un gruppo di pubblicazione. Rappresenta gli ultimi aggiornamenti diretti alla versione pubblicata del sito. Se il controllo di contesto in **Gruppi di pubblicazione** nel riquadro di spostamento sinistro mostra il nome **Sito live**, si sta lavorando nel contesto di creazione del sito live. **Sito live** è il nome predefinito del controllo di contesto. In caso contrario, il controllo di contesto mostra il nome di un gruppo di pubblicazione.

Per lavorare in un gruppo di pubblicazione, è necessario passare al contesto di creazione del gruppo di pubblicazione per esso. Per impostare il contesto del gruppo di pubblicazione, seguire uno di questi passaggi.

- Nel riquadro di spostamento sinistro, selezionare il controllo di contesto direttamente sotto **Gruppi di pubblicazione**, quindi selezionare il nome del gruppo di pubblicazione nell'elenco delle opzioni visualizzate. Il controllo di contesto viene rinominato e mostra il nome di un gruppo di pubblicazione.
- Nel riquadro di spostamento sinistro, selezionare **Gruppi di pubblicazione** e quindi, in **Gruppi di pubblicazione**, selezionare il nome del gruppo di pubblicazione. Il controllo di contesto viene rinominato e mostra il nome di un gruppo di pubblicazione.

Dopo aver impostato il contesto di creazione del gruppo di pubblicazione, si lavora in quel contesto di gruppo di pubblicazione quando si visualizza in anteprima e si modifica il contenuto del sito.

Per tornare al contesto di creazione del sito live predefinito, selezionare il controllo di contesto, quindi selezionare **Sito live**.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Aggiungere pagine o altri elementi a un gruppo di pubblicazione

Dopo aver selezionato un contesto di creazione di gruppi di pubblicazione e il controllo di contesto nel riquadro di spostamento sinistro mostra il suo nome, è possibile creare il contenuto esattamente come nel contesto predefinito del sito live. È inoltre possibile aggiungere pagine esistenti o altri elementi da altri gruppi di pubblicazione o dal contesto del sito live.

Per copiare pagine esistenti in un gruppo di pubblicazione, attenersi alla seguente procedura.

1. Selezionare il contesto di creazione da cui copiare, quindi, nel riquadro di spostamento sinistro, selezionare **Pagine**.
1. Selezionare la pagina da aggiungere a un gruppo di pubblicazione.
1. Nella barra dei comandi, selezionare **Copia in gruppo di pubblicazione**.
1. Nella finestra di dialogo **Selezionare un gruppo di pubblicazione**, selezionare il gruppo di pubblicazione a cui aggiungere la pagina, quindi selezionare **OK**.

È possibile utilizzare gli stessi passaggi di base per creare pagine di prodotti, URL, modelli, layout, frammenti e risorse della libreria multimediale personalizzati o per aggiungere elementi esistenti di questi tipi a un gruppo di pubblicazione.

## <a name="validate-a-publish-group"></a>Convalidare un gruppo di pubblicazione

Per assicurarsi che tutte le dipendenze nel contenuto del gruppo di pubblicazione siano soddisfatte e che tutte le convalide vengano superate, è possibile eseguire la convalida per identificare eventuali problemi che devono essere risolti prima di pianificare un'azione di pubblicazione.

Per convalidare il gruppo di pubblicazione prima di pianificarlo, attenersi alla seguente procedura.

1. Nel riquadro di spostamento sinistro, selezionare **Gruppi di pubblicazione**.
1. Selezionare il gruppo di pubblicazione da convalidare.
1. Nella barra dei comandi, selezionare **Convalida**.

La convalida viene eseguita su tutto il contenuto nel gruppo di pubblicazione. Tutti i problemi che impediscono il completamento di un'azione di pubblicazione vengono visualizzati in una casella di notifica che appare in alto a destra.

> [!NOTE]
> La convalida viene sempre eseguita automaticamente quando viene pianificato un gruppo di pubblicazione. Tuttavia, il pulsante **Convalida** nella barra dei comandi è utile perché consente di identificare i problemi che è necessario risolvere prima di provare a pianificare la pubblicazione di un gruppo di pubblicazione.

## <a name="schedule-a-publish-group-to-go-live"></a>Pianificare il passaggio allo stato Live di un gruppo di pubblicazione

Per pianificare il passaggio allo stato Live di un gruppo di pubblicazione sul proprio sito, attenersi alla seguente procedura.

1. Nel riquadro di spostamento sinistro, selezionare **Gruppi di pubblicazione**.
1. In **Gruppi di pubblicazione**, selezionare il gruppo di pubblicazione da pianificare.
1. Nella barra dei comandi, selezionare **Modifica programmazione**. Viene visualizzata la finestra di dialogo **Modifica programmazione**.
1. Seleziona la data e l'ora in cui il gruppo di pubblicazione deve passare allo stato Live, quindi selezionare **OK**.

Per annullare la pianificazione di un gruppo di pubblicazione, seguire gli stessi passaggi, ma selezionare **Annulla programmazione gruppo di pubblicazione** nella finestra di dialogo **Modifica programmazione**.

> [!NOTE]
> I gruppi di pubblicazione molto grandi potrebbero impiegare fino a un minuto o due per essere pubblicati quando arriva l'orario programmato. Tenere presente che un'azione di pubblicazione non è istantanea e che i gruppi di pubblicazione più piccoli verranno pubblicati più rapidamente.

## <a name="publish-groups-faq"></a>Domande frequenti sui gruppi di pubblicazione

**Quanti elementi possono essere inclusi in un gruppo di pubblicazione?**

Attualmente, esiste un limite di 2.000 elementi per gruppo di pubblicazione. Tenere presente che i gruppi di pubblicazione molto grandi potrebbero impiegare diversi minuti per essere pubblicati quando arriva l'orario programmato.

**I gruppi di pubblicazione sono come i "rami" di codice della terminologia di sviluppo software?**

Sì e no. Si può pensare ai gruppi di pubblicazione come versioni con biforcazioni del sito. In questo modo, si comportano come rami. Tuttavia, non esiste un'idea di unione a livello di singoli elementi. L'elemento pubblicato per ultimo sovrascrive quello che esisteva in precedenza e l'azione di pubblicazione più recente sostituisce sempre le azioni di pubblicazione precedenti.

**Posso programmare due gruppi di pubblicazione per passare allo stato Live contemporaneamente?**

N. Per motivi di prestazioni e conflitti, il sistema obbligherà a scaglionare i gruppi di pubblicazione pianificati a distanza di almeno cinque minuti.

**Posso utilizzare i gruppi di pubblicazione per pianificare elementi di back-office multicanale, come sconti e aggiornamenti sui prodotti?**

Attualmente, la funzionalità dei gruppi di pubblicazione supporta solo contenuti di siti Web. Tuttavia, Microsoft è consapevole del fatto che l'integrazione con scenari di merchandising di back-office potrebbe essere utile per il coordinamento e l'automazione dei lanci di campagne multicanale.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modalità di aggiungere contenuti](add-manage-content.md)

[Glossario del modello di pagina](page-elements-overview.md)

[Stato e ciclo di vita documento](document-states-overview.md)

[Abilitare e utilizzare la condivisione multicanale](cross-channel-sharing.md)

[Utilizzare i moduli](work-with-modules.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Panoramica modelli e layout](templates-layouts-overview.md)

[Personalizzare la navigazione del sito](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]