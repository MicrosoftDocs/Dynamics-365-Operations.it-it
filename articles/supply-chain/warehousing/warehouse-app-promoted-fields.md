---
title: Configurare i campi promossi per i passaggi nell'app per dispositivi mobili Warehouse Management
description: In questo articolo viene descritto come promuovere ed evidenziare specifiche informazioni per i passaggi nei flussi di attività per l'app per dispositivi mobili Warehouse Management.
author: Mirzaab
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5f5f24f47d0a2376be714f9208cd383cf3aacc07
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857056"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Configurare i campi promossi per i passaggi nell'app per dispositivi mobili Warehouse Management

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Le caratteristiche che sono descritte in questo articolo si applicano solo alla nuova applicazione mobile Warehouse Management. Non riguardano la vecchia app del magazzino, che ora è deprecata.

In questo articolo viene descritto come promuovere ed evidenziare specifiche informazioni per i passaggi nei flussi di attività per l'app per dispositivi mobili Warehouse Management. Questa capacità può aiutare a concentrare l'attenzione dei lavoratori sui campi più importanti mentre lavorano in un flusso. Per ogni passaggio di ogni processo, gli amministratori possono selezionare quali campi promuovere e quali campi evidenziare.

## <a name="enable-promoted-fields-in-your-system"></a>Abilitare i campi promossi nel tuo sistema

Prima di poter impostare i campi promossi, è necessario completare la procedura seguente per abilitare le funzionalità richieste e generare i nomi dei campi richiesti nell'app per dispositivi mobili Warehouse Management.

1. Vai a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Nell'area di lavoro [**Gestione funzionalità**](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), abilita la funzionalità elencata nel modo seguente:

    - **Modulo:** *Gestione Magazzino*
    - **Nome della funzione:** *Istruzioni per il passo dell'app del magazzino*

    Per ulteriori informazioni sulla funzionalità *Istruzioni del passaggio dell'app di magazzino*, vedi [Personalizzare i titoli dei passi e le istruzioni per l'applicazione mobile Warehouse Management](mobile-app-titles-instructions.md). Questa funzione è un prerequisito per la funzionalità *Campi promossi dell'app di magazzino*.

1. Abilita la funzionalità elencata nel modo seguente:

    - **Modulo:** *Gestione Magazzino*
    - **Nome funzionalità:** *Campi promossi dall'app di magazzino*

    Questa è la funzionalità descritta in questo articolo.

1. Aggiorna i nomi dei campi nell'app per dispositivi mobili Warehouse Management andando in **Warehouse Management \> Impostazioni \> Dispositivo mobile \> Nomi dei campi dell'app di magazzino** e selezionando **Crea impostazione predefinita**. Per ulteriori informazioni, vedi [Configurare i campi per l'app per dispositivi mobili Gestione magazzino](configure-app-field-names-priorities-warehouse.md).
1. Ripeti il passaggio precedente per ogni persona giuridica (società) in cui si utilizza l'app per dispositivi mobili Warehouse Management.

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Configurare campi promossi da un override specifico del menu

Per impostare i campi promossi attieniti alla seguente procedura.

1. Crea un override specifico del menu per il menu pertinente e procedi come descritto in [Personalizzare i titoli dei passaggi e le istruzioni per l'app per dispositivi mobili Warehouse Management](mobile-app-titles-instructions.md).
1. Trova la combinazione di valori **ID passo** e **Nome voce di menu** che vuoi modificare e quindi seleziona il valore nella colonna **ID passo** .
1. Nella pagina che appare, nella scheda dettaglio **Seleziona campi promossi** scegli **Seleziona campi** sulla barra degli strumenti.
1. Nella finestra di dialogo **Campi promossi** seleziona i campi che vuoi promuovere. Puoi anche evidenziare fino a due campi selezionati. I campi evidenziati verranno mostrati in grassetto nell'app per dispositivi mobili Warehouse Management. Quando selezioni i campi, considera il fatto che alcune schermate potrebbero mostrare solo il primo o i primi due campi promossi. Per un esempio che mostra come usare queste impostazioni, vedi lo scenario più avanti in questo articolo.

    > [!NOTE]
    > L'elenco **Campi disponibili** è limitato ai campi che possono apparire per la voce di menu. Tuttavia, altri fattori (come la composizione della voce) determinano se un campo viene effettivamente visualizzato nell'app per dispositivi mobili Warehouse Management. Se hai configurato i campi promossi, solo i campi selezionati verranno visualizzati nella pagina principale dell'app per dispositivi mobili Warehouse Management. Tuttavia, i lavoratori possono comunque visualizzare i campi rimanenti toccando la pagina dei dettagli.

1. Seleziona **OK** per applicare le impostazioni. I campi selezionati sono ora elencati nella scheda dettaglio **Seleziona campi promossi**.

## <a name="example-scenario"></a>Scenario di esempio

### <a name="enable-sample-data"></a>Abilitare dati di esempio

Per usare i record e i valori di esempio specificati in questo scenario, devi utilizzare un sistema in cui sono installati i dati dimostrativi standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Configurare il prelievo vendite con passaggi promossi nel passaggio targa

In questa procedura, imposti i campi promossi ed evidenziati per la voce di menu **Prelievo vendite** nel passaggio targa.

1. Vai alla **gestione del magazzino \> Impostazione \> Dispositivo mobile \> Passi per il dispositivo mobile**.
1. Trova e seleziona l'ID del passaggio denominato *LicensePlateId*.
1. Nel riquadro delle azioni, seleziona **Aggiungi configurazione del passo**.
1. Nella finestra di dialogo a discesa, utilizza il campo **Voce di menu** per trovare e selezionare *Prelievo vendite*.
1. Selezionare **OK**.
1. Viene visualizzata la pagina dei dettagli per l'override appena creato. Nella scheda dettaglio **Seleziona campi promossi** scegli **Seleziona campi** sulla barra degli strumenti.
1. Nella finestra di dialogo **Campi promossi** puoi selezionare i campi da promuovere ed evidenziare. Nell'elenco **Campi disponibili** trova e seleziona i seguenti campi e utilizza i pulsanti per spostarli nell'elenco **Campi selezionati**:

    - Ubicazione
    - Articolo
    - Nome prodotto
    - Stato inventario

1. Utilizza i pulsanti freccia su e freccia giù per personalizzare l'ordine dei campi nell'elenco **Campi selezionati**. Nell'app per dispositivi mobili Warehouse Management, i campi verranno visualizzati nell'ordine impostato qui.
1. Seleziona il campo **Posizione** quindi seleziona **Evidenzia**.
1. Seleziona **OK** per salvare la configurazione.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Visualizzare i campi promossi nell'app per dispositivi mobili Warehouse Management

In questa procedura, aprirai l'app per dispositivi mobili Warehouse Management e seguirai i passaggi per visualizzare i campi che hai promosso ed evidenziato nella procedura precedente.

1. In Microsoft Dynamics 365 Supply Chain Management, crea un ordine cliente che richiederà un passaggio di prelievo per prelevare da un'ubicazione in cui è tracciata la targa. Rilascia quindi l'ordine cliente al magazzino. Prendi nota dell'ID lavoro generato.
1. Apri l'app per dispositivi mobili Warehouse Management e accedi al magazzino 24. (Nei dati demo standard, accedere utilizzando *24* come ID utente e *1* come password.)
1. Seleziona il menu **Uscita** quindi seleziona la voce di menu **Prelievo vendite**.
1. Seguire le istruzioni per l'immissione dei dati sullo schermo per inserire l'ID lavoro generato nel passaggio 1.
1. Nel passaggio contenente il testo **Scansiona targa**, dovresti vedere le modifiche apportate nella pagina dei dettagli. I campi vengono visualizzati nell'ordine impostato per i campi promossi e il campo **Ubicazione** è mostrato in grassetto.
