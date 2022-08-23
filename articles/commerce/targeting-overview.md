---
title: Targeting per dispositivo, mercato e georilevazione
description: Questo articolo descrive come creare, modificare e gestire audience e target in Generatore siti di Microsoft Dynamics 365 Commerce utilizzando informazioni relativi a dispositivi, mercati e georilevazione.
author: sushma-rao
ms.date: 02/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: sushmar
ms.search.validFrom: 2021-07-31
ms.dyn365.ops.version: AX 10.0.21
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: ebac0f4ee98f36027f8cb50a368b9b6dcbb24623
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279423"
---
# <a name="device-market-and-geolocation-targeting"></a>Targeting per dispositivo, mercato e georilevazione

[!include [banner](includes/banner.md)]

Questo articolo descrive come creare, modificare e gestire audience e target in Generatore siti di Microsoft Dynamics 365 Commerce utilizzando informazioni relativi a dispositivi, mercati e georilevazione.

Dynamics 365 Commerce ti consente di personalizzare le variazioni del contenuto della tua pagina (note come *target*) per specifici gruppi di clienti (noti come *audience*) per aumentare l'engagement e la soddisfazione degli utenti. Puoi creare dapprima un audience o un target. Tuttavia, un'esperienza di targeting di successo richiede entrambi questi componenti.

Crei e gestisci audience in Generatore di siti di Commerce in base a dati dei clienti come posizione, informazioni sul dispositivo, stato di accesso e altre informazioni derivate dinamicamente dalle richieste Web dei clienti. Inoltre, crei e gestisci target in moduli e frammenti di e-commerce in Generatore di siti di Commerce.

**Dichiarazione di non responsabilità**: sei responsabile dell'utilizzo di questa funzionalità in conformità con tutte le leggi e i regolamenti applicabili, inclusi quelli relativi al targeting e al profiling. 

## <a name="audiences"></a>Audience

Un audience è un gruppo di utenti e l'appartenenza al gruppo è determinata da un insieme di regole dinamiche. Queste regole sono semplici test logici eseguiti in base alle informazioni disponibili nelle richieste dei clienti o in altri segmenti disponibili. Puoi combinare più regole utilizzando gli operatori AND/OR.

Commerce supporta in modo nativo segmenti di base come informazioni sul dispositivo, stato di accesso, referrer e parametri di stringa di query. Supporta anche segmenti estendibili tramite connessioni a provider di terze parti.

### <a name="basic-segments"></a>Segmenti di base

Per impostazione predefinita, sono disponibili i seguenti segmenti che possono essere inclusi nelle definizioni di audience:

- **Stato accesso**: verifica se un utente è autenticato.
- **Piattaforma dispositivo**: verifica i seguenti tipi di dispositivi:

    - Dispositivo mobile
    - PC desktop
    - Tablet
    - Altro

- **Sistema operativo dispositivo**: verifica i seguenti sistemi operativi:

    - Windows
    - Linux
    - iOS
    - Android, altro

- **Parametri di stringa di query**: verifica l'esistenza di una coppia chiave-valore in un parametro di stringa di query di un URL di richiesta. Ad esempio, per l'URL `www.fabrikam.com/en-us/request?promo=true`, è possibile scrivere una regola per verificare che il valore del parametro **promo** è **true**.
- **Cookie**: verifica un valore di cookie impostato per il dominio nell'URL della richiesta. Ad esempio, una richiesta di Fabrikam.com potrebbe includere un cookie il cui nome è **CustomLayout** e il valore è **1**. La verifica dei cookie verifica l'esistenza di un cookie ma non ne crea uno in modo esplicito. Nell'esempio precedente, JavaScript deve aver precedentemente impostato il cookie **CustomLayout** di un altro modulo o di qualche altro processo aziendale.

    > [!NOTE]
    > Assicurati che l'utilizzo dei cookie sia conforme alle leggi applicabili.

- **Referrer**: se un utente segue un collegamento per richiedere la pagina, il referrer è l'URL della pagina che ha ospitato il collegamento.

### <a name="extensible-segments"></a>Segmenti estendibili

Commerce ti consente di espandere l'elenco di segmenti disponibili connettendoti a provider di segmentazione di terze parti. Un provider di segmentazione descriverà i tipi di segmenti disponibili. Per ulteriori informazioni su come connettersi a un provider di geolocalizzazione o segmentazione, vedi [Configurare e abilitare i connettori](e-commerce-extensibility/connectors.md).

> [!NOTE]
> - Se un provider esterno è abilitato, potrebbe connettersi a un servizio che ha prestazioni imprevedibili. Per garantire una migliore esperienza utente, se un utente richiede una pagina che include il targeting e tale pagina fa riferimento a un audience che controlla un provider di segmenti di terze parti, viene visualizzata la versione predefinita della pagina.
> - L'utente deve fornire il suo consenso all'uso dei cookie. Il browser dell'utente richiede quindi tutti i segmenti ai provider pertinenti e i risultati vengono inseriti in un cookie che viene restituito all'utente. Le richieste successive alla pagina utilizzeranno queste informazioni per fornire all'utente contenuti mirati. Per ulteriori informazioni sulla conformità dei cookie, vedi [Conformità dei cookie](cookie-compliance.md).

**Dichiarazione di non responsabilità**: se abiliti questa funzionalità, i tuoi dati verranno condivisi con i sistemi di terze parti che selezioni. Sei tu che decidi quali dati fornire alla terza parte. La gestione dei dati e gli standard di conformità della terza parte potrebbero differire dagli standard di Microsoft Dynamics 365 Commerce. La privacy degli utenti è importante per Microsoft. Per ulteriori informazioni, leggi l'[informativa Privacy e cookie](https://privacy.microsoft.com/privacystatement) di Microsoft.

### <a name="create-an-audience-in-site-builder"></a>Crea un audience in Generatore di siti

Per creare un'audience in Generatore di siti Web di Commerce, segui questi passaggi.

1. Nel pannello di navigazione a sinistra, seleziona **Audience**.
1. Selezionare **Nuovo**.
1. Immetti un nome per l'audience. Eventualmente puoi anche aggiungere tag e una descrizione.
1. Seleziona **Crea** e quindi **Aggiungi nuovo blocco di regole**. Un blocco di regole è una raccolta di regole unite da condizioni AND. Puoi anche creare più blocchi di regole che hanno condizioni OR tra loro.
1. Seleziona un'origine dati per i tuoi segmenti, quindi specifica il nome del segmento, l'operatore e i valori. Puoi creare ed eliminare più regole in un blocco di regole oppure puoi creare ed eliminare interi blocchi di regole. Puoi anche spostare blocchi di regole verso l'alto o verso il basso come necessario.

    > [!NOTE]
    > Puoi avere fino a 100 valori in un elenco e ogni elemento dell'elenco può contenere fino a 50 caratteri.

1. Quando sei soddisfatto della configurazione dell'audience, seleziona **Fine modifica**. Puoi quindi selezionare **Pubblica** per rendere disponibile l'audience per l'uso in un target attivo. In alternativa, puoi pubblicare l'audience insieme al target. 

Per modificare un'audience, seleziona il relativo collegamento ipertestuale nella scheda **Audience**, quindi seleziona **Modifica** nell'editor di audience visualizzato. Per visualizzare l'elenco di target e pagine che fanno riferimento a un audience, seleziona l'audience nella visualizzazione elenco delle audience, quindi seleziona **Visualizza assegnazioni**. Per eliminare un'audience nella visualizzazione elenco delle audience o nell'editor delle audience, annulla la pubblicazione se è già stata effettuata, quindi seleziona **Elimina** nella barra dei comandi.

> [!NOTE]
> Le audience sono un concetto a livello di sito in Generatore di siti di Commerce. Puoi condividere la stessa audience in più target.

### <a name="rename-an-audience-in-site-builder"></a>Rinominare un gruppo di destinatari in Generatore di siti

Per rinominare un gruppo di destinatari esistente in Generatore di siti Web di Commerce, segui questi passaggi.

1. Nel pannello di navigazione a sinistra, seleziona **Audience**.
1. Selezionare il nome del segmento di gruppo di destinatari che vuoi rinominare.
1. Selezionare **Modifica** per iniziare a modificare il gruppo di destinatari.
1. Nel riquadro delle proprietà del gruppo di destinatari, seleziona il simbolo della penna accanto al nome del gruppo di destinatari.
1. Modificare il nome del destinatario, se necessario.
1. Selezionare il segno di spunta per confermare la modifica del nome.
1. Selezionare **Fine modifica**.

## <a name="targets"></a>Destinatari

Un target è l'esperienza utente mostrata ai membri di una o più audience selezionate. Può includere variazioni di uno o più moduli in una pagina o in un frammento. 

Puoi definire una pianificazione per i target per specificare per quanto tempo devono rimanere attivi. Tieni presente che questa azione è separata dall'azione di pianificazione di un gruppo di pubblicazione che determina quando verrà pubblicata una raccolta di contenuti. Puoi anche visualizzare i target in anteprima per vedere come appariranno ai membri delle audience selezionate. Inoltre, puoi dare la priorità ai tuoi target per specificare quale deve essere mostrato in caso di conflitto.

### <a name="create-a-target"></a>Creare un target

Per creare una shell di target per moduli di pagine in Generatore siti di Commerce, segui questi passaggi.

1. Nel pannello di navigazione a sinistra, selezionare **Pagine**. Quindi seleziona il collegamento ipertestuale per la pagina che contiene i moduli che desideri scegliere come target.
1. Seleziona **Modifica** per estrarre la pagina per la modifica.
1. Nel menu **Target**, seleziona **Nuovo target** per creare una nuova shell di target. Puoi creare più target in una pagina come necessario.
1. Immetti un nome e una descrizione per il target e seleziona **Avanti**.
1. Seleziona **Aggiungi** per includere le audience che vedranno il contenuto mirato o per escludere audience. Quindi seleziona **Avanti**.

    > [!NOTE]
    > L'assegnazione di audience è un passaggio facoltativo durante la creazione di target. Tuttavia, prima di pubblicare il target, devi includere almeno un'audience per assicurarti che i gruppi di utenti previsti visualizzeranno il contenuto mirato.

1. Definisci la finestra temporale per la visualizzazione del target selezionando il fuso orario nonché date e orari di inizio e fine. Puoi impostare il target di modo che venga sempre visualizzato durante la finestra temporale oppure selezionare giorni e orari specifici. Al termine, seleziona **Avanti**.

    > [!NOTE]
    > Gli orari e il fuso orario specificati sono globali. Se desideri scegliere come target differenti località in orari o fusi orari diversi, devi creare differenti target e definire la pianificazione desiderata per ogni località.

1. Esamina i dettagli e quando tutto sembra corretto, seleziona **Crea un'esperienza target** e quindi **Vai a target**. Viene creata la shell di target. Ora puoi aggiungervi moduli.
1. Seleziona il modulo da scegliere come target, seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi a target corrente**. Quando scegli come target un modulo padre, tutti i relativi figli diventano parte di quel target. I moduli scelti come target sono evidenziati in verde.
1. Apporta gli aggiornamenti di contenuto necessari al modulo scelto come target e aggiungi più moduli al target come necessario. Quindi seleziona **Salva** per salvare tutte le modifiche.
1. Prima di pubblicare il target, assicurati di selezionare **Anteprima** nella barra dei comandi per esaminarlo. Puoi quindi selezionare una delle opzioni seguenti:

    - **Anteprima di base**: seleziona questa opzione per visualizzare in anteprima solo la variazione selezionata (pagina predefinita o target), senza alcuna audience associata.
    - **Anteprima avanzata**: seleziona questa opzione se disponi di più target in una pagina e desideri visualizzarli in anteprima come utente che appartiene a un insieme selezionato di audience o in una data/ora specifica. Seleziona **Avanti** per selezionare da un elenco di audience pertinenti. Puoi anche rimuovere il filtro per selezionare tra tutte le audience.

1. Quando sei soddisfatto della configurazione del target, devi pubblicare la pagina per rendere attivo il target. Seleziona **Pubblica** per rendere immediatamente attivo il target. In alternativa, puoi utilizzare un gruppo di pubblicazione per pianificare l'attivazione della pagina. Per informazioni sui gruppi di pubblicazione, vedi [Utilizzare i gruppi di pubblicazione](publish-groups.md).

Puoi anche scegliere dei frammenti come target. La procedura è simile. Tuttavia, nel passaggio 1, devi selezionare **Frammenti** anziché **Pagine** nel riquadro di navigazione a sinistra.

> [!NOTE]
> Per evitare qualsiasi impatto negativo sulle metriche, puoi avere un esperimento o dei target in una pagina o in un frammento. Non puoi avere l'esperimento e i target contemporaneamente.

### <a name="manage-targets"></a>Gestire i target

Per modificare, duplicare o eliminare i target, vai alla pagina o al frammento predefinito e segui questi passaggi.

1. Nel menu a discesa, seleziona **Target**, quindi seleziona **Gestisci target**.
1. Seleziona un target da modificare, duplicare o eliminare.
1. Se hai più target nello stesso modulo o se più target hanno pianificazioni in conflitto, seleziona **Priorità target** per specificare l'ordine in cui devono essere visualizzati. Se aggiungi più di un target in una pagina o in un frammento, il pulsante **Priorità target** appare anche nella barra di notifica per ricordarti che devi gerarchizzare i target. Se non specifichi alcuna priorità, per impostazione predefinita viene selezionato il target più recente.

### <a name="localize-targets"></a>Localizzare i target

I target nelle pagine e nei frammenti vengono automaticamente inclusi quando i file XLIFF vengono esportati e importati per scopi di localizzazione. Tuttavia, se non sono necessarie impostazioni locali, puoi eliminare i target per gli stessi dopo l'importazione dei file XLIFF localizzati.

> [!NOTE]
> I target sono gestiti per canale e per impostazioni locali. Le modifiche apportate ai target in un canale o nelle impostazioni locali non vengono automaticamente trasferite ad altri canali o impostazioni locali.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
