---
title: Formalizzare i processi aziendali
description: "Questo argomento spiega come usare la funzionalità Processo aziendale per creare un modello di processo aziendale per processi che devono essere completati nell'organizzazione."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ee4035f3156a91faecdecba45289dbb1ca6e947a
ms.openlocfilehash: fd538677d897c1e7d3103cd714c688373aab8d29
ms.contentlocale: it-it
ms.lasthandoff: 06/19/2018

---
# <a name="formalize-business-processes"></a>Formalizzare i processi aziendali

[!include[banner](includes/banner.md)]

La funzionalità Processo aziendale consente di creare un modello di processi aziendali per processi che devono essere completati nell'organizzazione. Ad esempio, la società completa un controllo di Risorse umane (HR) ogni anno. In questo caso, è possibile creare un modello che segue tutte le attività che il processo di controllo comprende. Questo modello può quindi consentire di assicurarsi che tutte le attività vengono effettuate tutte le volte che il controllo viene eseguito. Inoltre, se le attività devono essere completate in un ordine specifico, il modello consente di garantire che sono state effettuate nell'ordine corretto.

I modelli possono essere riutilizzati per i processi ricorrenti. Possono essere copiati e utilizzati come punto di partenza per la creazione di nuovi modelli.

Dopo la creazione di un processo aziendale, è possibile avviare e monitorare un processo aziendale nell'area di lavoro **Processo aziendale**. Quando viene avviato un processo aziendale, le attività sono assegnate alle persone appropriate e includono una data di scadenza.

## <a name="business-process-templates"></a>Modelli di processo aziendale
Un modello del processo aziendale elenca un gruppo di attività che costituiscono un processo aziendale. I responsabili e gli assistenti delle Risorse umane possono creare processi aziendali per impostazione predefinita. Tuttavia, è possibile modificare i ruoli che possono creare processi di business modificando il metodo **Gestire i processi aziendali generici** nella configurazione di sicurezza.

È possibile definire un proprietario processo per ogni processo aziendale. Il proprietario del processo ha visibilità su tutte le attività per il processo e può riassegnarle o modificare le date di scadenza. Ad esempio, il direttore delle risorse umane crea un modello di processo aziendale per la revisione dei benefici e specifica il responsabile della retribuzione e dei benefici come proprietario del processo. Il responsabile della retribuzione e dei benefit ha quindi visibilità sui compiti che devono essere portati a termine nell'ambito della revisione.

Il proprietario di un processo non può creare nuovi processi aziendali o modelli di processi aziendali, né eliminare i processi aziendali attivi o i modelli di processi aziendali.

## <a name="tasks"></a>Attività
Un processo aziendale spesso comprende molteplici attività. Alcune attività, come la revisione delle offerte di corsi interni, possono essere completate in Microsoft Dynamics 365 for Talent[?]. In questo caso, si seleziona un'opzione nel campo **Collegamento attività**. Altre attività potrebbero includere la verifica o il completamento di pagine su un sito Web. In questo caso, nel campo **URL** è selezionato **Collegamento attività** e infine l'indirizzo Web può essere immesso. È possibile immettere URL per siti interni ed esterni. È inoltre possibile creare attività da completare manualmente, ad esempio la revisione dell'accessibilità di tutte le strutture. In questo caso, un collegamento di attività non è obbligatorio. Questa flessibilità consente di monitorare più tipi di attività in un processo completo.

Le attività possono essere assegnate a un lavoratore specifico o a una posizione. Ad esempio, il responsabile delle retribuzioni e dei benefit sarà sempre la persona che conduce una revisione dei premi assicurativi. Pertanto, quando si crea questa attività, selezionare la **posizione** per il **tipo di assegnazione**, quindi selezionare **Responsabile retribuzione** e benefit dall'elenco **Posizione**. Quando il processo aziendale ha inizio, l'attività viene assegnata al lavoratore che occupa la posizione di **responsabile retribuzione e benefit**. È possibile assegnare un'attività a un lavoratore specifico selezionando **Lavoratore** nel campo **Tipo di assegnazione** e selezionando la persona appropriata.

Le date di scadenza dell'attività dipendono dalla data stabilita immessa all'inizio del processo aziendale. Alcune attività devono essere completate prima della data stabilita e alcune possono essere completate dopo la data stabilita. Quando si definisce un'attività, nel campo **Offset data di scadenza da data stabilita** si specifica una data di scadenza relativa alla data target. Ad esempio, il responsabile delle retribuzioni e dei deve debba eseguire una verifica dei premi assicurativi 10 giorni prima che sia completato il controllo da parte delle Risorse umane. In questo caso, l'attività creata per la revisione ha un valore **Offset data di scadenza da data stabilita** di **-10**. Pertanto, se il processo aziendale è stato avviato il 13 maggio, la data di scadenza dell'attività sarà il 3 maggio.

> [!NOTE]
> Le date di scadenza possono essere modificate anche dopo che il processo aziendale è stato avviato.

Attività complesse possono richiedere più passaggi, o le persone che eseguono le attività potrebbero dover fornire ulteriori informazioni. Per questi scenari, è possibile aggiungere istruzioni a un'attività. Le istruzioni possono fornire ulteriori informazioni su come completare l'attività per la persona che deve completarla. È anche possibile includere nelle istruzioni la formattazione di rich text.

## <a name="starting-a-business-process"></a>Avvio di un processo aziendale
In un modello di processo aziendale, è possibile avviare un processo aziendale selezionando **Avvia processo**. Quando viene avviato un processo, le attività verranno create per i lavoratori selezionati e/o le ubicazioni definite nelle attività incluse nel modello. Verrà assegnata una scadenza a ogni attività aggiungendo o sottraendo i giorni di offset dalla data di destinazione come spiegato nella sezione "Attività". È possibile visualizzare i processi aziendali attivi nell'ambiente di lavoro **Processi aziendali**.

## <a name="employee-self-service"></a>Dipendente self-service
Dopo che un'attività è stata assegnata a un dipendente, il dipendente può visualizzarla, e tutte le altre attività assegnate, sulla pagina **Dipendente self-service**. Per ogni attività dei processi aziendali che viene assegnato a lui o lei, il dipendente può vedere il nome e la descrizione del compito, le istruzioni per completarlo, e il nome di una persona di contatto. Nella pagina **Dipendente self service**, il dipendente può anche aprire la pagina associata in Microsoft Dynamics 365 o la pagina Web associata e contrassegnare le attività come in corso, annullate o completate.

## <a name="business-process-workspace"></a>Area di lavoro del processo aziendale
I professionisti delle Risorse umane possono visualizzare i processi aziendali attivi nell'area di lavoro **Processo aziendale**. Questa area di lavoro elenca tutti i processi attivi e le attività associate a ogni processo. L'elenco di attività completo può essere filtrato in base alla data di scadenza. L'area di lavoro elenca inoltre le attività scadute e le attività assegnate specificatamente al professionista HR. Il professionista HR può inoltre aggiornare lo stato di tutte le attività e, se necessario, riassegnare le attività per far avanzare il processo aziendale globale.

## <a name="my-business-processes-workspace"></a>Area di lavoro Processi aziendali personali
I proprietari processo possono visualizzare i processi aziendali attivi a essi assegnati nell'area di lavoro **Processi aziendali personali**. L'area di lavoro elenca tutti i processi attivi e le attività associate di proprietà dell'utente. L'elenco di attività completo può essere filtrato in base alla data di scadenza. L'area di lavoro elenca inoltre le attività assegnate specificatamente al proprietario del processo. Il proprietario del processo può inoltre aggiornare lo stato di tutte le attività nonché riassegnare qualsiasi attività.

## <a name="navigating-business-processes"></a>Esplorazione dei processi aziendali
Per creare o copiare un modello di processo aziendale o per avviare un processo aziendale, accedere a Processi aziendali - collegamenti - Amministrazione dei processi aziendali. Sarà quindi possibile effettuare le azioni riportate di seguito:

- Selezionare **Nuovo** per creare un nuovo modello del processo aziendale.
- **Copia da modello** copierà il modello selezionato in uno nuovo.
- **Avvia processo** avvierà il processo aziendale selezionato, assegnerà le attività e calcolerà le date di scadenza.

Per visualizzare i processi attivi e le attività associate spostarsi sull'area di lavoro **Processi aziendali**.


