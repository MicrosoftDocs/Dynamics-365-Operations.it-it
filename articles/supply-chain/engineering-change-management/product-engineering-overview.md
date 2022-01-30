---
title: Panoramica della gestione delle modifiche di progettazione (video)
description: Questo argomento fornisce una panoramica della gestione delle modifiche di progettazione, che consente di pianificare e gestire il controllo delle versioni del prodotto e gestire i cicli di vita del prodotto e le modifiche di progettazione.
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8c200796d587d77c0f4d2344524a890ba964ab39
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985214"
---
# <a name="engineering-change-management-overview"></a>Panoramica della gestione delle modifiche di progettazione

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Riepilogo funzionalità

I produttori di oggi richiedono una potete gestione di dati del prodotto, controllo della versione e gestione delle modifiche di progettazione per avere successo in un mondo di cicli di vita dei prodotti in costante riduzione, requisiti di qualità e affidabilità aumentati e una maggiore attenzione alla sicurezza del prodotto.

La gestione delle modifiche di progettazione conferisce struttura e disciplina al processo di gestione dei dati di prodotto e consente di definire, rilasciare e rivedere i prodotti in modo controllato e supportato dai flussi di lavoro. Tramite le versioni del prodotto e la gestione delle modifiche di progettazione, è possibile documentare, valutare l'impatto e applicare le modifiche di progettazione durante l'intero ciclo di vita di un prodotto.

La gestione delle modifiche di progettazione consente di pianificare e gestire il controllo delle versioni del prodotto e gestire i cicli di vita del prodotto e le modifiche di progettazione. Ecco un elenco delle sue funzionalità principali:

- Controllo delle versioni del prodotto
- Funzionalità di rilascio del prodotto migliorata che consente di mantenere i dati anagrafici del prodotto in una persona giuridica (la società di progettazione) e pubblicare il prodotto rilasciato completamente configurato in altre persone giuridiche
- Regole per la convalida dell'inserimento delle informazioni richieste prima dell'attivazione di una versione del prodotto (controlli di disponibilità)
- Gestione migliorata del ciclo di vita del prodotto tramite un controllo dettagliato su quando un prodotto rilasciato può essere utilizzato in processi aziendali specifici
- Richieste di modifiche di progettazione supportate dai flussi di lavoro
- Ordini di modifiche di progettazione supportati dai flussi di lavoro

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

Il video precedente ([Cambia capacità di gestione in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) è incluso nella [playlist di Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>Attivare le funzionalità di gestione delle modifiche di progettazione per il sistema

Per poter utilizzare la gestione delle modifiche di progettazione, è necessario abilitare la funzionalità *Gestione delle modifiche di progettazione* e la relativa chiave di configurazione. Se inoltre si desidera monitorare la dimensione della versione dei prodotti nelle transazioni (facoltativo), si deve abilitare sia la funzionalità *Dimensione versione prodotti* sia la relativa chiave di configurazione. Dopo che questi prerequisiti sono stati impostati come richiesto, è possibile attivare funzionalità aggiuntive facoltative per la gestione delle modifiche di progettazione.

### <a name="turn-on-the-basic-engineering-change-management-features"></a>Attivare le funzionalità di gestione delle modifiche di progettazione di base

Innanzi tutto, attivare le funzionalità procedendo come segue.

1. Andare all'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Controllare gli aggiornamenti.
1. Attiva la funzionalità denominata *Gestione modifiche di progettazione*.
1. Per utilizzarla, attivare anche la funzionalità *Versione dimensione prodotto*.

### <a name="turn-on-the-required-configuration-keys"></a>Attivare le chiavi di configurazione richieste

Successivamente, attivare le chiavi di configurazione procedendo come segue.

1. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Espandere il nodo **Commercio**
1. Abilitare la chiave di configurazione per la funzionalità principale selezionando la casella di controllo **Gestione delle modifiche di progettazione**.
1. Espandi il nodo **Gestione delle modifiche di progettazione** e seleziona o deseleziona le seguenti caselle di controllo come richiesto (a seconda delle funzionalità che si desidera utilizzare):

    - **Ricerca attributi**: seleziona questa casella di controllo per abilitare la [funzionalità di ricerca degli attributi](engineering-attributes-and-search.md). È consigliabile utilizzare questa funzionalità, ma puoi deselezionare questa casella di controllo se non la utilizzerai.
    - **Gestione delle modifiche per la produzione di processo**: seleziona questa casella di controllo se desideri utilizzare le funzionalità di gestione delle modifiche di progettazione per gestire le modifiche nelle formule per la produzione di processo. Se non devi gestire le formule, puoi deselezionare questa casella di controllo. Per altre informazioni, vedi [Gestisci le modifiche nelle formule e nei loro ingredienti](manage-formula-changes.md).

1. Per usare anche la dimensione versione, selezionare la casella di controllo **Dimensione prodotto - Versione**. (Questa casella di controllo è più in basso nell'elenco, non nidificata sotto il nodo **Gestione delle modifiche di progettazione**.)
1. Disattivare la modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Il database deve essere sincronizzato per assicurarti che le chiavi di configurazione siano abilitate correttamente. Esegui una delle seguenti operazioni, a seconda del tipo di ambiente su cui stai lavorando:
    - **Per ambienti di livello 1 (sviluppo)**: Apri il tuo progetto in Microsoft Visual Studio e quindi seleziona **Dynamics 365 \> Sincronizza database \> Sincronizza**.
    - **Per ambienti di livello 2 (e superiori)**: il database si sincronizza automaticamente dopo che l'ambiente è entrato e uscito dalla modalità di manutenzione, quindi puoi saltare questo passaggio.

> [!IMPORTANT]
> A partire da aprile 2022, le chiavi di licenza per **Gestione delle modifiche di progettazione** e **Dimensione prodotto - Versione** saranno abilitate per impostazione predefinita per tutte le nuove installazioni, ma potrai comunque disabilitarle se necessario.

### <a name="turn-on-additional-engineering-change-management-features"></a>Attivare le funzionalità di gestione delle modifiche di progettazione aggiuntive

Dopo aver attivato le funzionalità di base di gestione delle modifiche di progettazione e le relative chiavi di configurazione, vengono aggiunte diverse funzionalità aggiuntive e facoltative di gestione delle modifiche di progettazione. Ciascuna di tali funzionalità è elencata nel modulo **Gestione modifiche di progettazione**. La tabella seguente descrive ogni funzione facoltativa e fornisce collegamenti per ulteriori informazioni.

| Nome della funzionalita in gestione funzionalità | descrizione |
|---|---|
| Abilita gestione modifiche su prodotti esistenti | <p>Questa funzionalità consente di convertire i prodotti esistenti in prodotti di progettazione in modo da iniziare a utilizzarli tramite la gestione delle modifiche di progettazione.</p><p>Per ulteriori informazioni, vedere [Abilitare la gestione delle modifiche in prodotti esistenti](change-management-existing-products.md).</p> |
| Notifiche di progettazione per la produzione | <p>Quando un prodotto viene modificato in fase di progettazione, potrebbe essere importante informare la produzione in relazioni a tali modifiche. In questo modo, gli addetti alla produzione possono intraprendere le azioni appropriate, come la sostituzione dei componenti, della distinta base (DBA) o del percorso. Questa funzionalità consente di notificare al reparto produzione le modifiche ai prodotti in fase di produzione stessa.</p><p>Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md).</p> |
| Ereditarietà degli attributi migliorata per la gestione modifiche di progettazione | <p>Questa funzionalità semplifica la gestione degli attributi per prodotti finiti o articoli intermedi. Quando questa funzione è attivata, è più facile identificare tutti gli attributi che appartengono a un articolo ed è possibile selezionare gli attributi che devono essere propagati da quell'articolo al relativo articolo padre. Questa funzione è utile quando, ad esempio, un componente di un prodotto finito è fragile, tossico o infiammabile, perché è possibile identificare facilmente l'attributo fragile, tossico o infiammabile e propagarlo al prodotto finito.</p><p>Per ulteriori informazioni, vedere [Attributi di progettazione e ricerca di attributi di progettazione](engineering-attributes-and-search.md).</p> |
| Controlli di disponibilità prodotto | <p>Tale funzionalità consente di configurare controlli di disponibilità standard (non tecnici). Utilizzare i controlli di disponibilità del prodotto per garantire che ogni prodotto sia completamente definito e che tutti i criteri richiesti siano configurati prima che il prodotto sia reso disponibile e utilizzato nelle transazioni. Se si disattiva questa funzione dopo averla utilizzata per un certo periodo di tempo, tutti i controlli di disponibilità esistenti per i prodotti standard verranno eliminati.</p><p>Per ulteriori informazioni, vedere [Preparazione del prodotto](product-readiness.md).</p> |
| Gestisci modifiche a formule e relativi ingredienti | <p>Questa funzionalità consente di tenere traccia delle modifiche agli ingredienti della formula, ai coprodotti e ai sottoprodotti.</p><p>Per altre informazioni, vedi [Gestisci le modifiche nelle formule e nei loro ingredienti](manage-formula-changes.md).</p> |
| Generazione di varianti per prodotti di progettazione | <p>Questa funzionalità consente di generare varianti per prodotti di progettazione, in base ai valori delle dimensioni disponibili.</p><p>Per ulteriori informazioni, vedere [Generare varianti per prodotti di progettazione](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
