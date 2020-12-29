---
title: Nuova interfaccia utente per documenti in Gestione documenti aziendali
description: Questo argomento fornisce informazioni su come utilizzare la nuova interfaccia utente per documenti nella funzionalità Gestione documenti aziendali del framework di creazione di report elettronici (ER).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2cb6e0da4af07b9b8486bf1e5bda29523cbd08e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681354"
---
# <a name="new-document-user-interface-in-business-document-management"></a>Nuova interfaccia utente per documenti in Gestione documenti aziendali

[!include [banner](../includes/banner.md)]

La funzionalità Gestione documenti aziendali consente agli utenti aziendali di modificare i modelli di documenti aziendali tramite un servizio Microsoft 365 o l'applicazione desktop Microsoft Office appropriata. Le modifiche potrebbero includere modifiche alla progettazione o nuove distribuzioni oppure gli utenti potrebbero aggiungere segnaposto per includere dati aggiuntivi senza dover modificare il codice sorgente. Per ulteriori informazioni su come utilizzare Gestione documenti aziendali, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).

La nuova interfaccia utente per documenti è più chiara e più facile da utilizzare. L'area **Documento aziendale** mostra solo i modelli disponibili per il provider corrente.

Il pulsante **Nuovo documento** consente agli utenti di creare e modificare un modello in una configurazione in formato ER fornita da un altro provider. Nell'esempio in questo argomento, il provider è Microsoft.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Rendere disponibile la nuova interfaccia utente per documenti in Gestione documenti aziendali

Per iniziare a utilizzare la nuova interfaccia utente per documenti in Gestione documenti aziendali, è necessario attivare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'area di lavoro **Gestione funzionalità**.

Seguire questi passaggi per attivare questa funzione per tutte le persone giuridiche.

1. Nell'area di lavoro **Gestione funzionalità**, nella scheda **Nuovo**, selezionare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'elenco.
2. Selezionare **Abilita ora** per attivare la funzionalità selezionata.
3. Aggiorna la pagina per accedere alla nuova funzionalità.

### <a name="edit-templates-that-are-owned-by-other-providers"></a>Modificare i modelli di proprietà di altri provider

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM_overview_new_template1.png)

2. Nella finestra di dialogo selezionare il documento da utilizzare come modello e quindi selezionare **Crea documento**.

    ![Finestra di dialogo Documenti aziendali](./media/BDM_overview_new_template2.png)

3. Nella nuova finestra di dialogo, nel campo **Titolo**, cambiare il titolo come richiesto. Il testo del titolo verrà utilizzato per assegnare un nome alla nuova configurazione in formato ER creata automaticamente. La versione bozza di questa configurazione (**Copia report FTl cliente (GER)**) conterrà il modello modificato e verrà automaticamente utilizzata per eseguire questo formato ER per l'utente corrente. Il modello originale della configurazione in formato ER di base sarà utilizzato per eseguire questo formato ER per qualsiasi altro utente.
4. Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.
5. Nel campo **Commento**, aggiornare i commenti per la revisione del modello modificabile che verrà creata automaticamente.
6. Selezionare **OK** per confermare l'avvio del processo di modifica.

    ![Finestra di dialogo per la creazione di documenti](./media/BDM_overview_new_template3.png)

Il pulsante **Nuovo documento** è utilizzato per creare e modificare un modello in una configurazione in formato ER fornita da un altro provider. In questo esempio, il provider è Microsoft. Quando si seleziona **Nuovo documento**, è possibile visualizzare tutti i modelli di proprietà del provider corrente e di altri provider. Dopo aver selezionato il modello, questo viene aperto per la modifica. Il modello modificato verrà archiviato in una nuova configurazione in formato ER generato automaticamente.

Per ulteriori informazioni, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).
