---
title: Transazioni e stati del ciclo di vita del prodotto
description: Questo argomento spiega come controllare quali transazioni sono consentite per ogni stato del ciclo di vita mentre un prodotto di progettazione attraversa il suo ciclo di vita.
author: t-benebo
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1e9b8a9f25edfa654a57e0ab4071cd93c8033d85
ms.sourcegitcommit: d375ef4138e898621416754c40770d8ccca4d271
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2022
ms.locfileid: "8322746"
---
# <a name="product-lifecycle-states-and-transactions"></a>Transazioni e stati del ciclo di vita del prodotto

[!include [banner](../includes/banner.md)]

Mentre un prodotto di progettazione attraversa il suo ciclo di vita, è importante essere in grado di controllare quali transazioni sono consentite per ogni stato del ciclo di vita. Ad esempio, i prodotti che non sono ancora in uno stato maturo non devono essere inseriti in un ordine cliente. In alternativa, se un prodotto sta raggiungendo il suo stato di fine vita, si potrebbe voler controllare l'afflusso di quel prodotto.

Per un prodotto di progettazione, le modifiche allo stato del ciclo di vita sono collegate alle versioni di progettazione del prodotto. Pertanto, lo stato del ciclo di vita del prodotto può anche essere collegato alle sue versioni di progettazione. Quando lo stato del ciclo di vita del prodotto è connesso a una versione di progettazione, è possibile utilizzare lo stato del ciclo di vita per controllare quali transazioni sono consentite per la versione di progettazione.

## <a name="create-and-manage-product-lifecycle-states"></a>Creare e gestire gli stati del ciclo di vita del prodotto

Per lavorare con gli stati del ciclo di vita del prodotto, andare a **Gestione modifiche di progettazione \> Impostazione \> Stato del ciclo di vita del prodotto**. Eseguire quindi uno dei passaggi seguenti.

- Per creare un nuov stato del ciclo di vita, selezionare **Nuovo** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per modificare uno stato del ciclo di vita esistente, selezionarlo nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per eliminare uno stato del ciclo di vita esistente, selezionarlo nel riquadro dell'elenco, quindi selezionare **Elimina** nel riquadro azioni.

> [!NOTE]
> I prodotti di progettazione utilizzano gli stessi stati del ciclo di vita del prodotto dei prodotti standard (non di progettazione). È anche possibile aprire la pagina **Stato del ciclo di vita del prodotto** descritta in questo argomento accedendo a **Gestione informazioni sul prodotto \> Impostazione \> Stato del ciclo di vita del prodotto**. Per ulteriori informazioni sugli stati del ciclo di vita del prodotto, sia per i prodotti di progettazione che per i prodotti standard, vedere [Panoramica dello stato del ciclo di vita del prodotto](../pim/product-lifecycle.md).

### <a name="header"></a>Intestazione

Impostare i seguenti campi nell'intestazione dello stato del ciclo di vita del prodotto.

| Campo | Descrizione |
|---|---|
| Stato/regione | Immettere un nome per lo stato del ciclo di vita del prodotto. |
| Descrizione | Immettere una descrizione dello stato del ciclo di vita del prodotto. |

### <a name="general-fasttab"></a>Scheda dettaglio Generale

Nella scheda dettaglio **Generale** impostare i seguenti campi.

| Campo | Descrizione |
|---|---|
| Predefinito quando viene rilasciato a una persona giuridica | Per i prodotti standard, impostare questa opzione su *Sì* se questo stato del ciclo di vita deve essere applicato a tutti i prodotti per impostazione predefinita quando vengono rilasciati per la prima volta. Impostarlo su *No* se questo stato del ciclo di vita verrà applicato manualmente in un secondo momento.<p>Questa impostazione non è applicabile ai prodotti di progettazione. Lo stato del ciclo di vita di una versione del prodotto di progettazione dopo che è stata creata nella società di progettazione è specificato nella sua categoria delle modifiche di progettazione. Quando il prodotto viene rilasciato a una società operativa, lo stato del ciclo di vita del prodotto viene copiato. In altre parole, quando un prodotto di progettazione viene rilasciato a una società operativa, ha lo stesso stato del ciclo di vita che aveva nella società di progettazione. Lo stato del ciclo di vita può essere sovrascritto nella società operativa.</p> |
| Attivo per pianificazione | Impostare questa opzione su *Sì* per includere i prodotti che si trovano in questo stato del ciclo di vita nei calcoli a livello di pianificazione generale e distinta base (DBA). Impostarla su *No* per escludere i prodotti che si trovano in questo stato del ciclo di vita dai calcoli. |

### <a name="enabled-business-processes-fasttab"></a>Scheda dettaglio Processi aziendali abilitati

Utilizzare la scheda dettaglio **Processi aziendali abilitati** per controllare quali dei processi aziendali disponibili possono essere utilizzati con i prodotti nello stato del ciclo di vita corrente. I processi elencati in questa Scheda dettaglio vengono trovati automaticamente nel modo seguente:

- La prima volta che si salva un nuovo stato del ciclo di vita, la pagina carica i processi aziendali attualmente disponibili.
- Se aggiungi nuovi processi aziendali al tuo sistema, puoi aggiornare l'elenco nella scheda dettaglio **Processi aziendali abilitati** per uno stato del ciclo di vita esistente selezionando **Controlla aggiornamenti** nel riquadro azioni.

I seguenti campi sono disponibili per ogni processo elencato nella scheda dettaglio **Processi aziendali abilitati**.

| Campo | Descrizione |
|---|---|
| Elaborazione | Questo campo di sola lettura mostra il nome di un processo aziendale esistente. |
| Area di processo | Questo campo di sola lettura mostra il nome di un'area di processo esistente. |
| Polizza | Selezionare uno dei seguenti valori per controllare se e come il processo corrente sarà consentito per i prodotti che si trovano in questo stato del ciclo di vita:<ul><li>**Abilitato** - Il processo aziendale è consentito.</li><li>**Bloccato** - Il processo non è consentito. Se un utente tenta di utilizzare il processo su un prodotto che si trova in questo stato del ciclo di vita, il sistema bloccherà il tentativo e mostrerà un errore. Ad esempio, si potrebbe bloccare l'acquisto dei prodotti a fine vita.</li><li>**Abilitato con avviso** - Il processo è consentito, ma verrà visualizzato un avviso. Ad esempio, si potrebbe desiderare che un prodotto prototipo venga inserito in un ordine di produzione creato dal reparto Ricerca e sviluppo. Tuttavia, gli altri reparti devono essere consapevoli che non devono ancora produrre il prodotto.</li></ul> |

Se stai aggiungendo più regole dello stato del ciclo di vita come personalizzazione, puoi visualizzare tali regole nell'interfaccia utente selezionando **Aggiorna processi** nel riquadro superiore. I pulsante **Aggiorna processi** è disponibile solo per gli amministratori.

## <a name="lifecycle-states-for-released-products-and-product-variants"></a>Stati del ciclo di vita per prodotti rilasciati e varianti prodotto

Per un prodotto che ha varianti (master e varianti), il prodotto (master) avrà uno stato del ciclo di vita e ciascuna delle varianti può anche avere uno stato del ciclo di vita diverso.

Per specifici processi, se la variante o il prodotto è bloccato, anche il processo verrà bloccato. Nello specifico, per determinare se un processo è bloccato, il sistema effettuerà i seguenti controlli:

- Per prodotti con controllo tecnico:
  - Se la versione di progettazione corrente è bloccata, il processo viene bloccato.
  - Se la variante corrente è bloccata, il processo viene bloccato.
  - Se il prodotto rilasciato è bloccato, il processo viene bloccato.
- Per prodotti standard:
  - Se la variante corrente è bloccata, il processo viene bloccato.
  - Se il prodotto rilasciato è bloccato, il processo viene bloccato.

Ad esempio, supponi di voler vendere solo una variante (rossa) di un determinato prodotto (t-shirt) e di bloccare per ora le vendite di tutte le altre varianti. Potresti fare ciò utilizzando la seguente configurazione:

- Assegna al prodotto uno stato del ciclo di vita che consenta il processo. Ad esempio, assegna al prodotto t-shirt lo stato del ciclo di vita *Vendibile*, che consente il processo di business *Ordine cliente*.
- Assegna alla variante vendibile uno stato del ciclo di vita che consente il processo. Ad esempio, assegna anche alla variante rossa lo stato del ciclo di vita *Vendibile*.
- A tutte le altre varianti viene assegnato un altro stato del ciclo di vita quando il processo viene bloccato. Ad esempio, assegna alla variante bianca (e a tutte le altre varianti) lo stato del ciclo di vita *Non vendibile*, che blocca il processo di business *Ordine cliente*.

## <a name="default-product-lifecycle-states"></a>Stati del ciclo di vita prodotto predefiniti

Lo stato del ciclo di vita predefinito per una versione di progettazione è specificato dalla relativa categoria di progettazione. Lo stato sarà predefinito quando si crea una nuova versione di progettazione, inclusa la prima versione di un nuovo prodotto.

Quando crei un nuovo prodotto o prodotto di progettazione, puoi anche impostare lo stato del ciclo di vita predefinito specificandolo nel modello prodotto rilasciato del criterio di rilascio assegnato al prodotto.

In questo caso, è possibile che il prodotto abbia uno stato del ciclo di vita diverso rispetto alla versione quando si crea un nuovo prodotto di progettazione.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
