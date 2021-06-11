---
title: Rilasciare le strutture del prodotto
description: Questo argomento spiega come rilasciare le strutture del prodotto complete oltre a rilasciare i prodotti insieme alle loro versioni di progettazione. In questo modo, è possibile garantire che i dati del prodotto rilevanti per la progettazione possano essere facilmente riutilizzati in diverse persone giuridiche.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 45763d5e602946fc3328cc3b565777fb7e549c61
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115099"
---
# <a name="release-product-structures"></a>Rilasciare le strutture del prodotto

[!include [banner](../includes/banner.md)]

Per garantire che i dati del prodotto rilevanti per la progettazione possano essere facilmente riutilizzati in diverse persone giuridiche, è possibile rilasciare le strutture del prodotto complete oltre a rilasciare i prodotti insieme alle loro versioni di progettazione. Pertanto, è possibile rilasciare le strutture delle distinte base (BOM) multilivello insieme al padre in un'unica azione di rilascio. In questo caso vengono rilasciati la distinta base e i prodotti di livello inferiore.

I prodotti di progettazione sono creati e mantenuti dalla loro società di progettazione in modo tale da soddisfare i requisiti di qualità quando vengono progettati. Ogni azienda operativa che produce un prodotto necessita dello stesso prodotto e della distinta base sottostante. A seconda dell'impianto di produzione, il ciclo di lavorazione potrebbe essere creato localmente. In questo caso, non viene rilasciato un ciclo di lavorazione insieme al prodotto. Per le persone giuridiche che venderanno i prodotti ma non li produrranno, la distinta base potrebbe non essere richiesta.

Per rendere il processo più efficiente, tutti i dati rilevanti per la progettazione possono essere rilasciati contemporaneamente ad altre società operative. Questi dati includono la struttura del prodotto. Durante il processo di rilascio, è possibile scegliere quale parte dei dati del prodotto deve essere rilasciata.

Per ulteriori informazioni sulle società di progettazione e sulle società operative, vedere [Società di progettazione e regole della proprietà dei dati](engineering-org-data-ownership-rules.md).

Si noti che è possibile rilasciare sia prodotti standard che prodotti di progettazione insieme alla struttura del prodotto di rilascio. Durante questo processo, l'intera struttura del prodotto verrà rilasciata, anche la distinta base e il ciclo di lavorazione dall'azienda in cui vengono rilasciati i prodotti.

Per un esempio di come rilasciare un prodotto, vedere [Rilasciare un prodotto di progettazione in una società locale](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>Dati rilasciati per un prodotto quando viene utilizzata la struttura del prodotto di rilascio

I seguenti dati sono inclusi nel rilascio dei prodotti di progettazione:

- **Dati del prodotto** - Viene creato un nuovo prodotto rilasciato.
- **Dati della versione di progettazione** - La versione di progettazione e i suoi dati vengono creati o aggiornati. Tenere presente che se si rilascia la stessa versione di progettazione di nuovo a una società operativa, i dati di progettazione verranno sovrascritti.
- **Attributi di progettazione** - Gli attributi di progettazione e i relativi valori vengono creati o aggiornati.
- **Distinta base di progettazione** - La distinta base di progettazione e le sue righe possono essere create o aggiornate. Per ulteriori informazioni sulla proprietà dei dati, vedere [Proprietari di prodotti](product-owner.md).
- **Cicli di lavorazione di progettazione** - I cicli di lavorazione di progettazione e le relative operazioni possono essere creati o aggiornati. Per ulteriori informazioni sulla proprietà dei dati, vedere [Proprietari di prodotti](product-owner.md).
- **Documenti di progettazione** - I documenti di progettazione che sono collegati alla versione di progettazione vengono creati o aggiornati.

Quando si attiva la gestione delle modifiche di progettazione sul sistema, la struttura del prodotto di rilascio è disponibile. Inoltre, i prodotti standard includono le rispettive distinte base e i cicli di lavorazione quando vengono rilasciati.

## <a name="product-acceptance"></a>Accettazione prodotto

**Accettazione del prodotto** è un parametro chiave che influenza il processo di rilascio. È possibile impostare questo parametro per ciascuna società andando in **Gestione modifiche di progettazione \> Impostazione \> Parametri di gestione modifiche di progettazione**. Per ulteriori informazioni, vedere [Parametri di gestione modifiche di progettazione](engineering-parameters.md).

### <a name="automatic-product-acceptance"></a>Accettazione automatica del prodotto

Ogni versione di prodotti di progettazione inizia quando qualcuno della società di progettazione seleziona un prodotto da rilasciare. Quando il parametro **Accettazione del prodotto** è impostato su *Automatico*, l'utente della società di progettazione decide quali dati del prodotto devono essere rilasciati automaticamente alle società operative. Il prodotto verrà quindi rilasciato automaticamente alle società selezionate nella procedura guidata di rilascio.

### <a name="manual-product-acceptance"></a>Accettazione manuale del prodotto

Ogni versione di prodotti di progettazione inizia quando qualcuno della società di progettazione seleziona un prodotto da rilasciare. Quando il parametro **Accettazione del prodotto** è impostato su *Manuale*, l'utente della società di progettazione decide quali dati del prodotto devono essere rilasciati alle società operative. Un utente di ciascuna società operativa esamina quindi i dati del prodotto e decide se accettare il rilascio. L'utente della società operativa può impostare le seguenti opzioni al momento della ricezione dei dati:

- Se i prodotti (aggiornamenti) non sono rilevanti per la società operativa, l'utente può scegliere di non accettare il rilascio.
- L'utente può modificare il modello dell'articolo per i nuovi prodotti.
- L'utente può scegliere se il prodotto deve essere rilasciato insieme alle sue distinte materiali e/o ai cicli di lavorazione e se deve essere rilasciato come approvato e attivo.
- L'utente può modificare le date di inizio validità dei prodotti.

Per un esempio di come accettare un prodotto, vedere [Esaminare e accettare il prodotto prima di rilasciarlo nella società locale](engineering-scenarios.md#accept).

> [!NOTE]
> Per i prodotti standard, è possibile rilasciare da una persona giuridica a qualsiasi altra persona giuridica. Per i prodotti di progettazione, l'unica persona giuridica da cui è possibile rilasciare è la società di progettazione.

## <a name="release-policies"></a>Criteri di rilascio

Non tutte le società operative necessitano degli stessi dati del prodotto. In generale, le società operative che producono prodotti di progettazione richiedono una DBA, mentre le società operative che vendono solo prodotti di progettazione non richiedono una DBA. È possibile utilizzare i criteri di rilascio per stabilire i parametri utilizzati per il rilascio dei prodotti.

Per ulteriori informazioni sulle categorie di prodotti di progettazione, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).

Durante il processo di rilascio, è possibile influenzare le impostazioni.

## <a name="create-and-manage-product-release-policies"></a>Creare e gestire i criteri di rilascio del prodotto

Per lavorare con i criteri di rilascio del prodotto, andare a **Gestione modifiche di progettazione \> Impostazione \> Criteri di rilascio del prodotto**. Eseguire quindi uno dei passaggi seguenti.

- Per creare un nuovo criterio, selezionare **Nuovo** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per modificare un criterio esistente, selezionarla nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per eliminare un criterio esistente, selezionarlo nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi nella scheda dettaglio **Generale** assicurarsi che l'opzione **Attivo** sia impostata su *No*. Nel riquadro azioni selezionare quindi **Elimina**.

### <a name="header"></a>Intestazione

Impostare i seguenti campi nell'intestazione dei criteri di rilascio del prodotto.

| Campo | Descrizione |
|---|---|
| Nome | Immetti un nome per il criterio. |
| Descrizione | Immettere una descrizione dei criteri. |

### <a name="general-fasttab"></a>Scheda dettaglio Generale

Impostare i seguenti campi nella scheda dettaglio **Generale** dei criteri di rilascio del prodotto.

| Campo | Descrizione |
|---|---|
| Tipo di prodotto | Selezionare se il criterio si applica ai prodotti di tipo *Articolo* o *Servizio*. Non è possibile modificare questa impostazione dopo aver salvato il record. |
| Tipo di produzione | Questo campo viene visualizzato solo quando hai abilitato la [gestione delle modifiche alla formula](manage-formula-changes.md) nel tuo sistema. Seleziona il tipo di produzione a cui si applicano questi criteri di rilascio:<ul><li>**Co-prodotto**: utilizza questi criteri di rilascio per gestire i co-prodotti. I coprodotti vengono prodotti durante la produzione di processo e non sono prodotti di progettazione o versione. I criteri di rilascio per i co-prodotti possono garantire che le impostazioni importanti, come **Gruppo di dimensioni di immagazzinamento** e **Gruppo di dimensioni di tracciabilità**, vengono impostati utilizzando un modello di prodotto rilasciato prima di essere rilasciati a un'azienda.</li><li>**Sottoprodotto**: utilizza questi criteri di rilascio per gestire i sottoprodotti. I sottoprodotti vengono prodotti durante la produzione di processo e non sono prodotti di progettazione o versione. I criteri di rilascio per i sottoprodotti possono garantire che le impostazioni importanti, come **Gruppo di dimensioni di immagazzinamento** e **Gruppo di dimensioni di tracciabilità**, vengono impostati utilizzando un modello di prodotto rilasciato prima di essere rilasciati a un'azienda.</li><li>**Nessuno**: utilizza questi criteri per gestire i prodotti standard che non sono prodotti con versione o di progettazione oppure co-prodotti o sottoprodotti.</li><li>**Elemento di pianificazione**: utilizza questi criteri di rilascio per gestire gli elementi di pianificazione prodotti utilizzando la produzione di processo. Gli elementi di pianificazione utilizzano formule. Assomigliano a formule, ma vengono utilizzati per produrre solo co-prodotti e sottoprodotti, non prodotti finiti.</li><li>**BOM**: utilizza questi criteri di rilascio per gestire i prodotti di progettazione, che non utilizzano formule e in genere (ma non necessariamente) includono le distinte materiali.</li><li>**Formula**: utilizza questi criteri di rilascio per gestire i prodotti finiti prodotti utilizzando la produzione di processo. Questi articoli avranno una formula ma non una distinta base.</li></ul> |
| Applica modelli | Selezionare una delle seguenti opzioni per specificare se e come applicare i modelli di rilascio del prodotto quando vengono utilizzati i criteri:<ul><li>**Sempre** - Un modello di prodotto rilasciato deve essere sempre utilizzato per le versioni. Se si seleziona questa opzione, utilizzare la scheda dettaglio **Tutti i prodotti** per specificare il modello utilizzato per ciascuna società a cui si rilascia. Se non specifichi un modello per ogni società elencata nella scheda dettaglio **Tutti i prodotti** viene visualizzato un errore quando si prova a salvare il criterio.</li><li>**Facoltativo** - Se un modello di prodotto rilasciato è specificato per una società elencata nella scheda dettaglio **Tutti i prodotti**, quel modello verrà utilizzato quando si rilascia a quella società. In caso contrario, non verrà utilizzato alcun modello. Se si seleziona questa opzione, è possibile salvare i criteri senza assegnare modelli a tutte le società. Non verrà visualizzato alcun avviso.</li><li>**Mai** - Nessun modello di prodotto rilasciato verrà utilizzato per alcuna società a cui si rilascia, anche se un modello è specificato per le società elencate nella scheda dettaglio **Tutti i prodotti**. Le colonne del modello non saranno disponibili.</li></ul> |
| Attive | Usare questa opzione per gestire i criteri di rilascio. Impostare su *Sì* per tutti i criteri di rilascio in uso. Impostare su *No* per contrassegnare un criterio di rilascio come inattivo quando non viene utilizzato. Si noti che non è possibile disattivare un criterio di rilascio assegnato a una categoria di prodotti di progettazione ed è possibile eliminare solo i criteri di rilascio inattivi. |

### <a name="all-products-fasttab"></a>Scheda dettaglio Tutti i prodotti

Nella Scheda dettaglio **Tutti i prodotti**, aggiungere una riga per ciascuna società operativa per cui si desidera utilizzare questo criterio per il rilascio. Utilizzare i pulsanti della Scheda dettaglio **Tutti i prodotti** per aggiungere e rimuovere le righe come richiesto. Per ogni riga che si aggiunge, impostare i seguenti campi.

> [!NOTE]
> Le impostazioni nella Scheda dettaglio **Tutti i prodotti** si applicano sia ai prodotti di progettazione che ai prodotti standard.

| Campo | Descrizione |
|---|---|
| ID conto società | Selezionare la società a cui si applica la riga. I parametri sulla riga verranno applicati quando i prodotti verranno rilasciati a questa società. |
| Prodotto rilasciato modello | Aggiungere un modello per il prodotto. |
| Copia approvazione DBA | Selezionare questa casella di controllo per copiare lo stato di approvazione della DBA nella società ricevente. |
| Copia attivazione DBA | Selezionare questa casella di controllo per copiare lo stato di attivazione della DBA nella società ricevente. |
| Copia approvazione ciclo di lavorazione | Selezionare questa casella di controllo per copiare lo stato di approvazione del ciclo di lavorazione nella società ricevente.|
| Copia attivazione ciclo di lavorazione | Selezionare questa casella di controllo per copiare lo stato di attivazione del ciclo di lavorazione nella società ricevente. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Scheda dettaglio Parametri delle opzioni per i prodotti di progettazione

Ogni volta che si aggiunge una riga alla scheda dettaglio **Tutti i prodotti**, una riga che ha un valore **ID account società** corrispondente viene creato nella scheda dettaglio **Parametri delle opzioni per i prodotti di progettazione**. Quindi, se si rimuove una riga dalla scheda dettaglio **Tutti i prodotti**, la riga che ha un valore **ID account società** corrispondente viene rimossa dalla scheda dettaglio **Parametri delle opzioni per i prodotti di progettazione**.

Per ogni riga che viene mostrata nella scheda dettaglio **Parametri delle opzioni per i prodotti di progettazione**, impostare i seguenti campi.

> [!NOTE]
> Le impostazioni nella scheda dettaglio **Parametri delle opzioni per i prodotti di progettazione** si applicano solo ai prodotti di progettazione.

| Campo | Descrizione |
|---|---|
| DBA modello | Quando viene rilasciato un prodotto con una DBA, verranno aggiunte le righe del modello DBA specificato. Questo campo è utile per aggiungere componenti locali, come imballaggi o istruzioni nella lingua locale. |
| Ciclo di lavorazione modello | Quando viene rilasciato un prodotto con un ciclo di lavorazione, verranno aggiunte le righe del modello ciclo di lavorazione specificato. |
| Copia validità | Selezionare se le date di validità devono essere copiate dalla società di progettazione alla società operativa quando si rilasciano i prodotti. |
| Aggiungi automaticamente alla proposta di rilascio | Selezionare questa casella di controllo per i prodotti che devono essere rilasciati automaticamente nell'ordine di modifica di progettazione. In questo modo, i prodotti che appartengono a categorie di prodotti di progettazione che utilizzano questi criteri di rilascio possono essere rilasciati automaticamente alle società operative in cui questa opzione è impostata. Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md).

### <a name="review-each-product-when-you-release-it"></a>Rivedere ogni prodotto al momento del rilascio

Quando vengono rilasciati prodotti di progettazione con distinte materiali o cicli di lavorazione, i parametri verranno impostati sui valori predefiniti, come indicato nei criteri di rilascio. Come utente, è possibile influenzare questo comportamento dal lato del rilascio quando si utilizza la struttura del prodotto di rilascio.

Per rilasciare prodotti di progettazione, nella pagina **Prodotti rilasciati** selezionare i prodotti da rilasciare, quindi selezionare **Rilascia struttura del prodotto** per aprire la procedura guidata di rilascio. La pagina **Seleziona i prodotti di progettazione da rilasciare** mostra i prodotti. Selezionare un singolo prodotto, quindi selezionare **Dettagli sul rilascio** per esaminare i dettagli sul rilascio del prodotto.

Nella pagina **Dettagli sul rilascio** è possibile modificare il valore dei campi **Ricevi DBA**, **Copia approvazione DBA**, **Copia attivazione DBA**, **Ricevi DBA**, **Copia approvazione ciclo di lavorazione** e **Copia attivazione ciclo di lavorazione**. Nello scenario push-pull, è possibile modificare il valore degli stessi campi sul lato di ricezione, a condizione che la distinta base e il ciclo di lavorazione vengano rilasciati.

## <a name="product-owners-and-product-releases"></a>Proprietari di prodotto e versioni del prodotto

Poiché i proprietari del prodotto sanno quali persone giuridiche necessitano dei loro prodotti, un prodotto può essere rilasciato solo dai membri del gruppo di proprietari del prodotto di quel prodotto. Gli altri utenti non possono rilasciare prodotti di cui non sono proprietari.

Questo comportamento si applica solo quando un prodotto viene selezionato direttamente per il rilascio. I prodotti che fanno parte della struttura di un altro prodotto tramite una distinta base *possono* essere rilasciati da utenti non proprietari quando rilasciano il prodotto padre, a condizione che siano proprietari del prodotto padre.

Ad esempio, il prodotto X è assegnato al gruppo di proprietari di prodotto *Armadi di design*. Il prodotto X fa anche parte della distinta base del prodotto Y, che è assegnato a gruppo di proprietari del prodotto *Altoparlanti di design*. Se un utente del gruppo di proprietari del prodotto *Altoparlanti di design* rilascia il prodotto Y e la relativa distinta base, il prodotto X verrà rilasciato insieme al prodotto Y.

Per ulteriori informazioni, vedere [Proprietari del prodotto](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
