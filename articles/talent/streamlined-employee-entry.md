---
title: Inserimento e navigazione dei dipendenti semplificati
description: L'immissione dei dati per i lavoratori in Dynamics 365 Talent è stata migliorata per consentire l'immissione rapida per tutti i dipendenti, passati, attivi o futuri. Un modello semplificato/consolidato di navigazione è stato aggiornato per individuare rapidamente le informazioni e la visualizzazione correlate e creare tutti gli aggiornamenti necessari.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent October 2019 update
ms.openlocfilehash: 40bbb8429355fa18fe12c7cf56f8d58f19766cad
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009424"
---
# <a name="streamlined-employee-entry-and-navigation"></a>Inserimento e navigazione dei dipendenti semplificati

[!include [banner](includes/banner.md)]

Dynamics 365 Talent consente l'immissione efficiente dei dati del dipendente e dell'impiego. È possibile aggiornare rapidamente le informazioni dello storico di lavoro dei dipendenti e dei terzisti passati, attivi e futuri.

È inoltre possibile consentire un'esperienza semplificata di navigazione per individuare rapidamente le informazioni correlate e di apportare le modifiche necessarie. Questa funzionalità è ora disponibile negli ambienti sandbox. Per attivare questa funzionalità, passare ad **Amministrazione sistema > Collegamenti > Impostazioni > Parametri di sistema > Funzionalità di anteprima**. Selezionare **Navigazione e modulo lavoratore avanzati**. In questo modo le modifiche saranno valide per tutti gli utenti. È possibile disattivare questa opzione in qualsiasi momento.

## <a name="view-options"></a>Opzioni di visualizzazione

È possibile utilizzare **Opzioni di visualizzazione** nel modulo del lavoratore per selezionare qualsiasi combinazione di dipendenti e di terzisti da un unico elenco. Queste opzioni consentono di visualizzare i lavoratori in tutte le persone giuridiche o per la persona giuridica a cui si è attualmente registrati. È inoltre possibile visualizzare i lavoratori attivi, in sospeso e che hanno lasciato la posizione nonché limitare i risultati in base al tipo di lavoratore (dipendente o terzista). Se è attiva la funzionalità di sicurezza avanzata, verranno visualizzati solo i dipendenti e i terzisti nelle persone giuridiche a cui si ha accesso.

Il contenuto delle colonne nell'elenco varia in base alle selezioni effettuate. Ad esempio, quando si visualizzano i dipendenti che hanno lasciato la posizione lavorativa, vengono visualizzati i codici della data di fine rapporto e del motivo come colonne aggiuntive nell'elenco. 

[![Opzioni di visualizzazione](./media/Worker-view-option.png)](./media/worker-view-option.png)

## <a name="navigation-and-banner"></a>Navigazione e banner

Un banner visualizza le informazioni chiave per ogni lavoratore. Il banner per i lavoratori attivi visualizza i seguenti campi:

- **Funzione**
- **Reparto**
- **Tipo di posizione**
- **Tipo di lavoratore**
- **Responsabile**
- **Persona giuridica**

Il banner per i lavoratori che hanno lasciato la posizione lavorativa visualizza i seguenti campi:

- **Data uscita**
- **Motivo**

Il banner per i lavoratori in sospeso visualizza i seguenti campi:

- **Funzione**
- **Reparto**
- **Tipo di posizione**
- **Responsabile**
- **Data di inizio**
- **Persona giuridica**

Il riquadro delle azioni della pagina del lavoratore è stato riorganizzato per includere meno opzioni. Le informazioni sono ora suddivise nelle seguenti categorie: 

- Lavoro
- Persona
- Uscire
- Retribuzione
- Benefit
- Conformità

Inoltre, una nuova scheda **Collegamenti** nella pagina del lavoratore principale offre agli utenti una posizione centrale per accedere a tutte le informazioni correlate per un lavoratore.

A causa di queste modifiche, le informazioni possono apparire in una posizione diversa da quella a cui si è abituati. Ad esempio, le informazioni sulla retribuzione, che prima erano visualizzate nel modulo del lavoratore, ora appaiono nel riquadro delle azioni in **Retribuzione > Retribuzioni** e la scheda **Informazioni personali** ora dispone di un pulsante **Ulteriori informazioni** per nascondere i campi a cui non si accede spesso.

[![Banner](./media/Banner.png)](./media/Banner.png)

## <a name="work-history"></a>Storico lavoro

La scheda **Storico lavoro** mostra lo storico del lavoro in tutte le persone giuridiche ed è disponibile per i dipendenti e i terzisti attivi, in sospeso e che hanno lasciato il lavoro. È ora possibile visualizzare tutto lo storico di lavoro contemporaneamente per le persone giuridiche a cui si ha accesso. Inoltre, è possibile modificare le informazioni per ognuna delle voci dello storico di lavoro senza modificare il contesto dei dati. È possibile aggiornare tutte le informazioni direttamente nella pagina. 

[![Storico lavoro](./media/Worker-work-history.png)](./media/Worker-work-history.png)

## <a name="position-history"></a>Storico delle posizioni

Nella scheda **Posizioni** della pagina principale del lavoratore offre una vista completa di tutte le posizioni occupate all'interno dell'azienda, incluse le assegnazioni passate, presenti e future. È possibile accedere direttamente allo storico delle posizioni del lavoratore anche nel riquadro delle azioni.

[![Posizioni](./media/Worker-position-history.png)](./media/Worker-position-history.png)

