---
title: Configurare parametri condivisi
description: È necessario impostare parametri condivisi per i record condivisi tra società, ad esempio Record posizione. In questo articolo viene spiegato come impostare i parametri di Human Resources tra persone giuridiche.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7aff01bee8cadcf852ae32fd60447c68e2174a2a
ms.sourcegitcommit: 43962e6fedaf55aab2f28f53bc38a69d2ff58403
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2021
ms.locfileid: "6332997"
---
# <a name="configure-shared-parameters"></a>Configurare parametri condivisi

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È necessario impostare parametri condivisi per i record condivisi tra società, ad esempio Record posizione. In questo articolo viene spiegato come impostare i parametri di Human Resources tra persone giuridiche.

Alcuni tipi di record, ad esempio i record Posizione, sono condivisi tra le società. Per questi record, è necessario configurare dei parametri condivisi. Ad esempio, è possibile utilizzare la pagina **Parametri condivisi Risorse umane** per configurare i parametri HR in tutte le persone giuridiche. 

Nella pagina **Parametri condivisi Risorse umane** i parametri sono raggruppati in aree a seconda della relativa funzionalità. 

### <a name="settings"></a>Impostazioni
Nella scheda **Identificazione** è necessario selezionare i tipi di identificazione che rappresentano i numeri di identificazione che sono elencati nella pagina. È necessario impostare i tipi di identificazione prima di immettere le informazioni di identificazione per i lavoratori. Le informazioni sul Social Security Number, il numero del documento di identità, il numero di identificativo straniero e il codice ID personale vengono gestite nella pagina **Tipo di identificazione**. Per definire un nuovo tipo di identificazione o rivedere l'elenco dei tipi esistenti, fare clic su **Gestione dipendente** &gt; **scheda Collegamenti** &gt; **Impostazioni** &gt; **Tipi di identificazione**. È possibile immettere un codice e una descrizione semplici. 

Nella scheda **Sequenze numeriche** è possibile selezionare le sequenze numeriche che sono utilizzate per i seguenti record: Numero dipendente, Posizione, ID richiesta utente, Documento I-9, Candidato, Discussione, ID benefit e Azione dipendente (se questo tipo di record è attivato). Per gestire i codici e i riferimenti delle sequenze numeriche, utilizzare la pagina elenco **Sequenze numeriche**. Per trovare questa pagina, utilizzare la funzionalità di ricerca della pagina. 

Nella scheda **Posizioni** indicare se per impostazione predefinita sono disponibili nuove posizioni da assegnare:

- **Sempre**: è possibile assegnare lavoratori a nuove posizioni quando si creano posizioni. Quando vengono create posizioni, la data e l'ora **Disponibile per l'assegnazione** nella scheda **Generale** della pagina **Posizione** vengono impostate automaticamente sulla data e ora di creazione.
- **Mai**: non è possibile assegnare lavoratori a nuove posizioni quando si creano posizioni. Se si seleziona questa opzione, è necessario aprire la pagina **Posizione** per ogni nuova posizione non appena diventa disponibile. Nella scheda **Generale** immettere la data **Disponibile per l'assegnazione** per abilitare l'assegnazione del lavoratore.

Nella scheda **Accesso avanzato** è possibile limitare l'accesso ad alcune informazioni o collegamenti:

- **Limita l'accesso alle informazioni sui lavoratori**: attivare questa funzione se gli utenti devono essere in grado di visualizzare le informazioni sui dipendenti solo per le persone giuridiche a cui hanno accesso e per i dipendenti con un impiego in quelle persone giuridiche.

    Dopo aver attivato questa funzione, è necessario seguire questi passaggi per impostare le autorizzazioni appropriate per ciascun utente la cui visualizzazione deve essere limitata:

    1. Nella pagina **Utenti** selezionare un utente.
    1. Selezionare un ruolo per l'utente. Diventa disponibile l'opzione **Assegna organizzazioni**.
    1. Selezionare **Assegna organizzazioni**.
    1. Nella nuova pagina, selezionare **Concedi l'accesso a singole organizzazioni specifiche**, quindi selezionare le organizzazioni a cui l'utente dovrebbe avere accesso.
    1. Ripetere i passaggi da 2 a 4 per ogni altro ruolo dell'utente, incluso il ruolo utente di sistema.

    > [!NOTE]
    > Le società a cui un utente ha accesso devono corrispondere a tutti i ruoli dell'utente.

- **Abilita visualizzazione retribuzione interaziendale**: la retribuzione per i dipendenti viene assegnata in base alla persona giuridica dell'impiego. A volte, un dipendente può avere contemporaneamente un impiego in più persone giuridiche. Quando questa funzione è attivata, la retribuzione per ogni persona giuridica verrà visualizzato in Dipendenti self-service e Responsabile self-service senza che sia necessario cambiare le persone giuridiche. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
