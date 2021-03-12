---
title: Transazioni e stati del ciclo di vita del prodotto
description: Questo argomento spiega come controllare quali transazioni sono consentite per ogni stato del ciclo di vita mentre un prodotto di progettazione attraversa il suo ciclo di vita.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 69ee39479424c1b629388c18e8bfefd023036d22
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431600"
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

| Campo | descrizione |
|---|---|
| Stato/regione | Immettere un nome per lo stato del ciclo di vita del prodotto. |
| descrizione | Immettere una descrizione dello stato del ciclo di vita del prodotto. |

### <a name="general-fasttab"></a>Scheda dettaglio Generale

Nella scheda dettaglio **Generale** impostare i seguenti campi.

| Campo | descrizione |
|---|---|
| Predefinito quando viene rilasciato a una persona giuridica | Per i prodotti standard, impostare questa opzione su *Sì* se questo stato del ciclo di vita deve essere applicato a tutti i prodotti per impostazione predefinita quando vengono rilasciati per la prima volta. Impostarlo su *No* se questo stato del ciclo di vita verrà applicato manualmente in un secondo momento.<p>Questa impostazione non è applicabile ai prodotti di progettazione. Lo stato del ciclo di vita di una versione del prodotto di progettazione dopo che è stata creata nella società di progettazione è specificato nella sua categoria delle modifiche di progettazione. Quando il prodotto viene rilasciato a una società operativa, lo stato del ciclo di vita del prodotto viene copiato. In altre parole, quando un prodotto di progettazione viene rilasciato a una società operativa, ha lo stesso stato del ciclo di vita che aveva nella società di progettazione. Lo stato del ciclo di vita può essere sovrascritto nella società operativa.</p> |
| Attivo per pianificazione | Impostare questa opzione su *Sì* per includere i prodotti che si trovano in questo stato del ciclo di vita nei calcoli a livello di pianificazione generale e distinta base (DBA). Impostarla su *No* per escludere i prodotti che si trovano in questo stato del ciclo di vita dai calcoli. |

### <a name="enabled-business-processes-fasttab"></a>Scheda dettaglio Processi aziendali abilitati

Utilizzare la scheda dettaglio **Processi aziendali abilitati** per controllare quali dei processi aziendali disponibili possono essere utilizzati con i prodotti nello stato del ciclo di vita corrente. I processi elencati in questa Scheda dettaglio vengono trovati automaticamente nel modo seguente:

- La prima volta che si salva un nuovo stato del ciclo di vita, la pagina carica i processi aziendali attualmente disponibili.
- Se aggiungi nuovi processi aziendali al tuo sistema, puoi aggiornare l'elenco nella scheda dettaglio **Processi aziendali abilitati** per uno stato del ciclo di vita esistente selezionando **Controlla aggiornamenti** nel riquadro azioni.

I seguenti campi sono disponibili per ogni processo elencato nella scheda dettaglio **Processi aziendali abilitati**.

| Campo | descrizione |
|---|---|
| Elaborazione | Questo campo di sola lettura mostra il nome di un processo aziendale esistente. |
| Area di processo | Questo campo di sola lettura mostra il nome di un'area di processo esistente. |
| Polizza | Selezionare uno dei seguenti valori per controllare se e come il processo corrente sarà consentito per i prodotti che si trovano in questo stato del ciclo di vita:<ul><li>**Abilitato** - Il processo aziendale è consentito.</li><li>**Bloccato** - Il processo non è consentito. Se un utente tenta di utilizzare il processo su un prodotto che si trova in questo stato del ciclo di vita, il sistema bloccherà il tentativo e mostrerà un errore. Ad esempio, si potrebbe bloccare l'acquisto dei prodotti a fine vita.</li><li>**Abilitato con avviso** - Il processo è consentito, ma verrà visualizzato un avviso. Ad esempio, si potrebbe desiderare che un prodotto prototipo venga inserito in un ordine di produzione creato dal reparto Ricerca e sviluppo. Tuttavia, gli altri reparti devono essere consapevoli che non devono ancora produrre il prodotto.</li></ul> |

Se stai aggiungendo più regole dello stato del ciclo di vita come personalizzazione, puoi visualizzare tali regole nell'interfaccia utente selezionando **Aggiorna processi** nel riquadro superiore. I pulsante **Aggiorna processi** è disponibile solo per gli amministratori.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]