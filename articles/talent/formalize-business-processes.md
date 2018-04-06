---
title: Formalizzare i processi aziendali
description: "La funzionalità Processo aziendale consente di creare un modello di processo aziendale per processi che devono essere completati nell'organizzazione."
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
ms.sourcegitcommit: 812db9f1d319e4d16f83700a7153a0a3b318963e
ms.openlocfilehash: 48f80eac5009e1a241d501b0c4a3a70b78f5d709
ms.contentlocale: it-it
ms.lasthandoff: 03/23/2018

---
# <a name="formalize-business-processes"></a>Formalizzare i processi aziendali
La funzionalità Processo aziendale consente di creare un modello di processo aziendale per processi che devono essere completati nell'organizzazione. Ad esempio, la società può completare un controllo delle Risorse umane ogni anno. È possibile creare un modello per tenere traccia di tutte le attività del controllo per assicurarsi che tutte le attività vengano svolte ogni volta che viene completato il processo e, se necessario, per assicurarsi che vengano svolte nell'ordine corretto. I modelli possono essere riutilizzati per processi ricorrenti o copiati per l'uso come punto di partenza per la creazione di nuovi.

Dopo la creazione di un modello, è possibile avviare e monitorare un processo nell'area di lavoro Processo aziendale.  Quando viene avviato un processo aziendale, le attività saranno assegnate alle persone appropriate e includeranno una data di scadenza. Questi componenti sono descritti dettagliatamente di seguito.

## <a name="business-process-template"></a>Modello di processo aziendale
Un modello del processo aziendale elenca un gruppo di attività che costituiscono un processo aziendale. I responsabili e gli assistenti delle Risorse umane possono creare processi aziendali per impostazione predefinita.  Tuttavia, è possibile modificare questa impostazione nella configurazione di sicurezza modificando il diritto Gestire i processi aziendali generici.

È possibile definire un Proprietario processo per ogni processo.  Il proprietario del processo avrà visibilità su tutte le attività per il processo e può riassegnarle o modificare le date di scadenza.  Ad esempio, il responsabile delle Risorse umane può creare un modello di processo aziendale per una revisione dei benefit.  Il responsabile delle retribuzioni e dei benefit può essere impostato come proprietario del processo, in modo da ottenere informazioni sulle attività che devono essere completate nell'ambito della revisione.  Un Proprietario processo non può creare o eliminare modelli di processo aziendale o processi aziendali attivi.

## <a name="task"></a>Compito
Un processo aziendale spesso comprende molteplici attività. Alcune attività possono essere completate in Dynamics 365 per Talent[?], ad esempio la revisione di offerte di corsi interni. In questa istanza, una voce di menu verrebbe selezionata nel campo Collegamento attività. Altre attività potrebbero includere la verifica o il completamento di moduli su un sito Web. La selezione dell'URL nel campo Collegamento attività consente l'accesso all'indirizzo Web. È possibile immettere URL per siti interni ed esterni in questo campo. È inoltre possibile creare attività da completare manualmente, ad esempio la revisione dell'accessibilità di tutte le strutture. In questa istanza, un collegamento di attività non è obbligatorio. Questa flessibilità consente di monitorare più tipi di attività in un processo completo.

Le attività possono essere assegnate a un lavoratore specifico o a una posizione. Ad esempio, il responsabile delle retribuzioni e dei benefit sarà sempre la persona che conduce una revisione dei premi assicurativi.   Quando si crea questa attività, selezionare la posizione per il tipo di assegnazione, quindi selezionare Responsabile retribuzione e benefit dall'elenco Posizione. Quando il processo ha inizio, l'attività viene assegnata al lavoratore che occupa la posizione di responsabile retribuzione e benefit. È inoltre possibile assegnare un'attività a un lavoratore specifico selezionando Lavoratore nel campo Tipo di assegnazione e selezionando la persona appropriata.

Le date di scadenza dell'attività dipendono dalla data stabilita immessa all'inizio del processo. Alcune attività devono essere completate prima della data stabilita e alcune possono essere completate dopo la data stabilita.  Quando si definisce un'attività, si immetterà una data di scadenza che è relativa alla data stabilita nel campo Offset data di scadenza da data stabilita. Si supponga, ad esempio, che il responsabile delle retribuzioni e dei benefit debba eseguire una verifica dei premi assicurativi 10 giorni prima che sia completato il controllo da parte delle Risorse umane. L'attività creata avrà una data di scadenza relativa alla data stabilita di -10. Pertanto, se il processo è stato avviato il 13 maggio, la data di scadenza dell'attività sarà il 3 maggio. Nota: le date di scadenza possono essere modificate anche dopo che il processo è stato avviato.

Le attività complesse possono richiedere più passaggi o che l'utente esegua le attività per fornire informazioni aggiuntive. È anche possibile aggiungere istruzioni all'attività e includere la formattazione RTF per le istruzioni. Le istruzioni possono fornire ulteriori informazioni su come completare l'attività per la persona che deve completarla.

Avvio di un processo Un processo può essere avviato in un modello di processo aziendale selezionando Avvia processo.  Quando viene avviato un processo, le attività verranno create per i lavoratori selezionati e/o le ubicazioni definite nelle attività incluse nel modello di processo aziendale. Verrà assegnata una scadenza a ogni attività aggiungendo o sottraendo i giorni di offset dalla data di destinazione (vedere le informazioni relative ai giorni di offset nell'area delle attività). I processi aziendali possono essere visualizzati nell'area di lavoro Processi aziendali. 

## <a name="employee-self-service"></a>Dipendente self-service
Quando un'attività è assegnata a un dipendente, le relative attività assegnate possono essere visualizzate nella pagina Dipendente self-service. I dipendenti con un'attività di processo aziendale assegnata possono visualizzare l'attività, la relativa descrizione, le istruzioni per il completamento e il nome di un contatto e possono aprire la pagina Dynamics 365 o una pagina Web associata dalla propria pagina Dipendente self-service. Le attività possono essere contrassegnate come in corso, annullate o completate.

## <a name="business-process-workspace"></a>Area di lavoro del processo aziendale
I professionisti delle Risorse umane possono visualizzare i processi aziendali attivi dall'area di lavoro Processo aziendale. L'area di lavoro elenca tutti i processi attivi e le attività associate a ogni processo. L'elenco di attività completo può essere filtrato in base alla data di scadenza. La pagina elenca inoltre le attività scadute e le attività assegnate specificatamente al professionista HR. Possono inoltre aggiornare lo stato di tutte le attività e, se necessario, riassegnare le attività per far avanzare il processo aziendale globale.

## <a name="my-business-processes-workspace"></a>Area di lavoro Processi aziendali personali
I proprietari processo possono visualizzare i processi aziendali attivi a essi assegnati dall'area di lavoro Processi aziendali personali. L'area di lavoro elenca tutti i processi attivi e le attività associate di proprietà dell'utente.  L'elenco di attività completo può essere filtrato in base alla data di scadenza. La pagina elenca inoltre le attività assegnate specificatamente al proprietario del processo. Il proprietario del processo può inoltre aggiornare lo stato di tutte le attività nonché riassegnare qualsiasi attività.

## <a name="navigating-business-processes"></a>Esplorazione dei processi aziendali
1.   Per aggiungere un modello di processo, accedere a Processi aziendali – Collegamenti – Amministrazione di processi aziendali.
 - a.   Nuovo creerà un nuovo modello.
 - b.   Copia da modello copierà il modello selezionato in uno nuovo.
 - c.   Avvia processo avvierà il processo aziendale selezionato, assegnerà le attività e calcolerà le date di scadenza.  
2.  Per visualizzare i processi attivi e le attività associate spostarsi sull'area di lavoro Processi aziendali.

