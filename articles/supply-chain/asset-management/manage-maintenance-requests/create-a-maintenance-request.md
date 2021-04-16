---
title: Creare richieste di intervento di manutenzione
description: In questo argomento viene illustrato come creare una richiesta di intervento di manutenzione in Gestione cespiti.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: af67d320f14fc6c3d28eec47de402ba645eea06d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836784"
---
# <a name="create-maintenance-requests"></a>Creare richieste di intervento di manutenzione

[!include [banner](../../includes/banner.md)]

 

Le richieste di intervento di manutenzione può essere utilizzata se gli addetti alla manutenzione o i lavoratori del reparto produzione scoprono attrezzature che richiede la riparazione, ma il processo di riparazione non può essere eseguita immediatamente.

**Esempio:** mentre l'addetto alla manutenzione effettua una riparazione, scopre che un altro cespite nello stesso ubicazione ha bisogno di manutenzione. Tuttavia, l'addetto non ha il tempo o pezzi di ricambio necessari per eseguire il processo di riparazione. A tale scopo, crea una richiesta di intervento di manutenzione sul cespite e immette una breve descrizione del problema.

La sezione **Richieste di interventi di manutenzione attive** del riquadro **Informazioni correlate** sul lato destro della pagina **Tutti i cespiti** o **Cespiti attivi** (**Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**) mostra le richieste attive collegate al cespite selezionato.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.
2. Selezionare **Nuovo**.
3. Nella finestra di dialogo **Crea richiesta**, nel campo **Tipo di richiesta di intervento di manutenzione**, selezionare il tipo di richiesta di intervento di manutenzione. Tipo predefinito viene suggerito.
4. Nel campo **Descrizione**, immettere un nome o un titolo che brevemente descrivono la richiesta di intervento di manutenzione.
5. Nei campi **Unità funzionale** e **Cespite**, selezionare una unità funzionale o un cespite, o una combinazione dei due, come richiesto. È possibile creare una richiesta di intervento di manutenzione senza selezionare un cespite e il cespite può essere aggiunti successivamente alla richiesta di intervento di manutenzione. Se l'addetto alla manutenzione che ha eseguito l'accesso è correlato a una risorsa correlata a un cespite, il campo **Cespite** viene impostato automaticamente.

    Se una richiesta di intervento di manutenzione è già collegata al cespite selezionato, una barra dei messaggi viene visualizzata nella parte superiore della finestra  dialogo **Crea richiesta** per segnalare l'ID della richiesta di intervento di manutenzione esistente. La barra dei messaggi anche informa se il cespite è coperto da un contratto di garanzia.

6. Nel campo **Livello servizio**, selezionare un livello di servizio che indica l'urgenza della richiesta.
7. Se è stato selezionato un cespite nel passaggio 5, è possibile utilizzare i campi **Sintomo problema**, **Area problema** e **Tipo di problema** per creare una registrazione del problema.
8. Se la richiesta di intervento di manutenzione ha determinato tempi di fermo per la manutenzione, immettere la data di inizio e di fine dei tempi di fermo.

    Il campo **Avviato da** viene impostato automaticamente sul tuo nome.

10. Il campo **Inizio effettivo** viene impostato automaticamente sulla data e ora corrente. Tuttavia, è possibile modificare il valore in base alle esigenze.
11. Nel campo **Note**, immettere eventuali note aggiuntive necessarie.
12. Selezionare **OK**.

![Crea richiesta di intervento di manutenzione](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a>Elaborazione successiva delle richieste di intervento di manutenzione

Dopo che una richiesta di intervento di manutenzione viene creata, ma prima che venga convertita in ordine di lavoro, le varie informazioni relative devono essere aggiornate. In genere, un addetto alla pianificazione o un altro dipendente amministrativo completa questa attività.

- Nella pagina **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**, selezionare la richiesta da gestire, quindi **Modifica**.

Nella visualizzazione dettagli, è possibile aggiornare vari dati. Di seguito sono riportati alcuni esempi.

- Selezionare e verificare il cespite. Se è necessario selezionare un cespite diverso successivamente, è possibile impostare l'opzione **Cespite verificato** su **No**.
- Selezionare un gruppo di addetti alla manutenzione e/o un addetto alla manutenzione. Per ulteriori informazioni sull'impostazione richiesta, vedere [Addetti alla manutenzione responsabili](../setup-for-maintenance-requests/responsible-workers.md).
- Selezionare un tipo di processo di manutenzione e, se queste informazioni sono rilevanti, una variante correlata del processo di manutenzione e una mansione qualificata per il processo.
- Nei campi **Longitudine** e **Latitudine**, immettere le coordinate geografiche. Tutte le coordinate aggiunti alla richiesta di intervento di manutenzione verranno trasferite automaticamente a un ordine di lavoro correlato. 

![Aggiornare la richiesta di intervento di manutenzione](media/04-manage-maintenance-requests.png)

> [!NOTE]
> Se si seleziona un cespite quando si crea una richiesta di intervento di manutenzione, è possibile aggiungere un solo problema al cespite. Dopo che la richiesta di intervento di manutenzione è stata creata, è possibile aggiungere più problemi in base alle esigenze. Per aggiungere problemi, selezionare **Errore del cespite** nella pagina **Tutte le richieste di intervento di manutenzione**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]