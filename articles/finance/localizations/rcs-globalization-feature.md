---
title: Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione
description: Questo argomento spiega come utilizzare Microsoft Regulatory Configuration Services (RCS) e il repository globale per creare e utlizzare le funzionalità di globalizzazione.
author: JaneA07
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: cbb1d9a53a7a09ab525532f08553898c4e40223a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822783"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Regulatory Configuration Services (RCS) - Funzionalità di globalizzazione

[!include [banner](../includes/banner.md)]

È possibile utilizzare Microsoft Regulatory Configuration Services (RCS) per creare una funzionalità di globalizzazione che può essere utilizzata nei servizi di globalizzazione, ad esempio un servizio di fatturazione elettronica. RCS consente di eseguire queste attività:

- Definire i componenti correlati di una funzionalità.
- Gestire il ciclo di vita delle funzionalità attraverso lo stato delle funzionalità.
- Rendere disponibile una funzionalità per ambienti definiti.
- Condividere una funzionalità con altre organizzazioni.

Le seguenti procedure spiegano come un utente in RCS può aggiungere una funzione di globalizzazione e i relativi componenti, aggiornare lo stato della funzionalità e renderla disponibile di modo che possa essere utilizzata nei servizi di globalizzazione.

Prima di completare le procedure, è necessario completare i passaggi correlati alle seguenti attività:

- Accesso a un'istanza RCS.
- Creazione e attivazione di un provider di configurazioni. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Nell'istanza delle app Finance and Operations, attenersi alla seguente procedura.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Se non è stato effettuato il provisioning di alcun ambiente RCS per la società, selezionare **Regulatory services - Configurazione** e seguire le istruzioni per il provisioning di un ambiente.

> [!NOTE]
> Se è già stato eseguito il provisioning di un ambiente RCS per la società, utilizzare l'URL della pagina per accedere all'ambiente selezionando l'opzione di accesso.

## <a name="turn-on-the-globalization-features"></a>Attivare le funzionalità di globalizzazione

1. Nell'istanza RCS, selezionare il riquadro **Gestione funzionalità**.
2. Nell'area di lavoro **Gestione funzionalità**, selezionare **Funzionalità di globalizzazione** nell'elenco, quindi selezionare **Abilita ora**.

    ![Funzionalità di globalizzazione in Gestione funzionalità](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Funzionalità di globalizzazione

Per utilizzare una funzionalità di globalizzazione, è necessario innanzitutto importarla dal repository globale e crearne una versione personalizzata. Esistono due modi per aggiungere funzionalità di globalizzazione:

- Aggiungendo una funzionalità derivata basata su una funzionalità esistente che è stata pubblicata o condivisa.
- Aggiungendo una nuova funzionalità creata da zero.

## <a name="access-globalization-features"></a>Accedere alle funzionalità di globalizzazione

1. Assicurarsi che **Funzionalità di globalizzazione** sia attivata in Gestione funzionalità, come descritto in precedenza in questo argomento.
2. Aprire la nuova area di lavoro **Funzionalità di globalizzazione** e quindi sotto **Funzionalità**, selezionare il riquadro **Fatturazione elettronica**.

    ![Area di lavoro Funzionalità di globalizzazione](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    Viene aperta la pagina **Funzionalità di fatturazione elettronica**.

    ![Pagina Funzioni di fatturazione elettronica](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Aggiungere una funzionalità di globalizzazione derivata

È possibile aggiungere una nuova funzionalità di globalizzazione derivandola da una funzionalità esistente che è stata pubblicata o condivisa.

1. Selezionare **Importa** per aprire la pagina **Importa funzionalità da repository globale**.

    ![Pagina Importa funzionalità da repository globale](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. Selezionare **Sincronizza** per ottenere le funzionalità più recenti.

    L'elenco sincronizzato include funzionalità che sono disponibili perché sono state pubblicate da Microsoft o perché sono state condivise da un altro provider di configurazioni.

    ![Elenco di funzionalità sincronizzato](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. Nell'elenco, selezionare le funzionalità da importare, quindi selezionare **Importa**. Se le funzionalità selezionate vengono importate correttamente, viene visualizzato un messaggio.

    ![Messaggio che indica il completamento dell'importazione](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Selezionare **Aggiungi**, quindi, nella finestra di dialogo a discesa, selezionare l'opzione **Basato sulla versione esistente**.
5. Immettere un nome e una descrizione per la funzionalità.
6. Nell'elenco di funzionalità disponibili, selezionare la versione di base della funzionalità, quindi selezionare **Crea funzionalità**.

    ![Aggiungere una funzione derivata](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    La funzionalità aggiunta viene creata e ha lo stato **Bozza**.

    ![Funzionalità derivata con stato Bozza](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Esaminare i componenti della funzionalità per determinare se sono necessari degli aggiornamenti:

    - Rivedere le configurazioni, nel caso in cui sia necessario personalizzare i formati per la creazione di report elettronici (ER) e la relativa associazione con mapping di formati per la versione della funzionalità.
    - Esaminare l'impostazione, nel caso sia necessario personalizzare la scheda **Azioni**, la scheda **Regole di applicabilità** o la scheda **Variabili** per la versione della funzionalità.

8. Nella scheda **Versioni**, selezionare una **Data di inizio validità** e immettere una descrizione se il campo **Descrizione** è vuoto.
9. Selezionare **Cambia stato** per completare la funzionalità. Le funzionalità completate possono essere rese disponibili per un ambiente specifico di modo che possano essere utilizzate nei servizi di globalizzazione o pubblicate nel repository globale.

> [!NOTE]
> Le funzionalità il cui valore **Stato versione funzionalità** è **Pubblicata** possono essere condivise con organizzazioni esterne.

## <a name="add-a-new-globalization-feature"></a>Aggiungere una nuova funzionalità di globalizzazione

È possibile aggiungere una nuova funzionalità di globalizzazione creandola da zero.

1. Nella pagina **Importa funzionalità da repository globale**, selezionare **Aggiungi**, quindi, nella finestra di dialogo a discesa, selezionare l'opzione **Nuova funzionalità**.
2. Immettere un nome e una descrizione per la funzionalità.
3. Selezionare **Crea funzionalità**.

    ![Aggiungere una nuova funzionalità](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. Nella scheda **Versioni**, selezionare una **Data di inizio validità**, quindi selezionare **Cambia stato** per completare la funzionalità. Le funzionalità completate possono essere rese disponibili per un ambiente specifico di modo che possano essere utilizzate nei servizi di globalizzazione o pubblicate nel repository globale.

> [!NOTE]
> Le funzionalità il cui valore **Stato versione funzionalità** è **Pubblicata** possono essere condivise con organizzazioni esterne.

## <a name="feature-component-overview"></a>Panoramica dei componenti delle funzionalità

Le funzionalità di globalizzazione hanno vari componenti:

- **Versione** - Questo componente supporta la gestione del ciclo di vita delle funzionalità e consente agli utenti di gestire lo stato per diverse versioni della funzionalità.
- **Configurazioni** - Questo componente consente agli utenti di gestire, visualizzare e modificare i formati ER e i mapping dei formati correlati.
- **Impostazioni** - Questo componente consente agli utenti dei servizi di globalizzazione, come un servizio di fatturazione elettronica, di gestire l'impostazione della versione della funzionalità correlata. Pertanto, supporta la costruzione flessibile delle regole di comunicazione e risposta.
- **Ambiente** - Questo componente consente agli utenti dei servizi di globalizzazione, come un servizio di fatturazione elettronica, di gestire l'ambiente in cui viene utilizzata l'impostazione delle versioni della funzionalità e di concedere l'autorizzazione agli utenti che accederanno allo stesso.
- **Organizzazioni** - Questo componente consente agli utenti di condividere la funzionalità con organizzazioni esterne.

## <a name="configuring-feature-components"></a>Configurazione dei componenti delle funzionalità

### <a name="version-and-status"></a>Versione e stato

La versione viene utilizzata per gestire il ciclo di vita della funzionalità di globalizzazione.

Lo stato può essere modificato nel campo **Stato** nella scheda **Versione**. Sono disponibili i seguenti stati:

- **Bozza** - La funzionalità può essere modificata solo quando è in questo stato.
- **Completa** - La funzionalità e tutti i componenti correlati sono stati finalizzati (completati) e non possono essere modificati.
- **Pubblicata** - La funzionalità e tutti i componenti correlati sono stati pubblicati nel repository globale.
- **Condivisa** - La funzionalità e tutti i componenti correlati sono stati condivisi con organizzazioni esterne.
- **Abilitata** - La funzionalità e tutti i componenti correlati sono stati abilitati per l'uso in un servizio di globalizzazione, come un servizio di fatturazione elettronica.

> [!NOTE]
> Le funzionalità devono passare sequenzialmente ad alcuni di questi stati. Pertanto, non tutti gli stati potrebbero essere disponibili in ogni fase del ciclo di vita.

### <a name="configurations"></a>Configurazioni

Le seguenti azioni sono disponibili per le configurazioni:

- **Visualizza** - Visualizza le configurazioni delle funzionalità sottostanti che non richiedono alcun aggiornamento.
- **Modifica** - Crea una versione bozza di una configurazione selezionata in modo da poter modificare il formato o il mapping del formato nella finestra Progettazione formati.
- **Elimina** - Elimina una configurazione selezionata dalla funzionalità.
- **Riassegna** - Riassegna la funzionalità. Per ulteriori informazioni, vediere la sezione [Riassegnare funzionalità di globalizzazione derivate](#rebase) più avanti in questo argomento.

### <a name="setups"></a>Impostazioni

Le azioni seguenti sono disponibili per le impostazioni di funzionalità:

- **Aggiungi** - Crea una nuova impostazione di funzionalità. Questa impostazione può essere derivata da un'impostazione esistente o creata da zero.
- **Elimina** - Elimina l'impostazione di funzionalità selezionata.
- **Visualizza** - Visualizza un'impostazione di funzionalità sottostante che non richiede alcuna modifica.
- **Modifica** - Crea, elimina o modifica gli attributi dei tre componenti principali di un'impostazione di funzionalità:

    - Azioni e i relativi parametri
    - Regole di applicabilità
    - Variabili

![Pagina Impostazione versioni funzionalità](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Ambienti

Le seguenti azioni sono disponibili per gli ambienti:

- **Abilita** - Per la versione della funzionalità selezionata, selezionare un ambiente pubblicato e una **Data di inizio validità** alla quale dovrebbe essere disponibile. Per ulteriori informazioni, vediere la sezione [Configurare ambienti per l'abilitazione](#configureenvironment) più avanti in questo argomento.
- **Annulla** - Rimuove un ambiente per un'impostazione di funzionalità.

### <a name="organizations"></a>Organizzazioni

Seguire questi passaggi per condividere una funzionalità di globalizzazione con un'organizzazione esterna.

1. Nella pagina **Funzionalità di fatturazione elettronica**, selezionare la funzionalità e la versione della funzionalità da condividere.
2. Nella scheda **Organizzazioni**, selezionare **Condividi con**, quindi, nella finestra di dialogo a discesa, immettere il nome di dominio dell'organizzazione.
3. Selezionare **Condividi**.

    ![Condividere una funzionalità con un'organizzazione](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

La funzionalità è condivisa con l'organizzazione selezionata ed è disponibile per tale organizzazione nel repository globale. Da lì, la funzionalità può essere importata nell'istanza di RCS o di Dynamics 365 Finance dell'organizzazione in modo che possa essere utilizzata.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Riassegnare funzionalità di globalizzazione derivate

È possibile riassegnare una funzionalità di globalizzazione derivata alla versione di base nuova o aggiornata della funzionalità. In questo modo, le modifiche alla versione di base possono essere aggiornate automaticamente. La versione di base aggiornata della funzionalità viene creata dal provider di configurazioni di origine e viene quindi pubblicata o condivisa.

![Versione di base aggiornata di una funzionalità](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Ad esempio, se si desidera riassegnare la versione derivata di una funzionalità creata, si ottiene innanzitutto la versione più recente della funzionalità importandola dal repository globale.

1. Nella pagina **Funzionalità di fatturazione elettronica**, selezionare **Importa**.
2. Selezionare **Sincronizza** per ottenere le funzionalità più recenti.
3. Nell'elenco di funzionalità, selezionare le funzionalità da importare, quindi selezionare **Importa**.

    ![Importazione dell'ultima versione di una funzionalità](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. Nell'elenco delle funzionalità, selezionare la funzionalità da riassegnare.
5. Nella scheda **Versione**, selezionare **Nuova** per creare una versione bozza.

    ![Nuova versione bozza creata](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Selezionare **Riassegna**.
7. Nella finestra di dialogo **Riassegna**, selezionare la versione più recente a cui riassegnare la funzionalità.

    ![Finestra di dialogo Riassegna](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Selezionare **OK**.
9. Esaminare i componenti della funzionalità e apportare le modifiche necessarie.
10. Selezionare **Cambia stato** per completare la funzionalità riassegnata. Una volta completata la riassegnazione, è possibile eseguire azioni aggiuntive. Ad esempio, è possibile pubblicare la funzionalità e renderla disponibile per l'uso nei servizi di globalizzazione.

    ![Stato della funzionalità aggiornato a Completata](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>Configurare ambienti per le funzionalità di globalizzazione

Gli utenti dei servizi di globalizzazione possono gestire l'ambiente per impostare una funzione di globalizzazione e concedere l'autorizzazione ad altri utenti che vi avranno accesso.

1. Aprire la nuova area di lavoro **Funzionalità di globalizzazione** e quindi sotto **Ambienti**, selezionare il riquadro **Fatturazione elettronica**.

    ![Area di lavoro Funzionalità di globalizzazione](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Selezionare **Parametri insieme di credenziali delle chiavi**, quindi selezionare **Nuovo** per creare un segreto dell'insieme di credenziali delle chiavi di Azure.
3. Immettere un nome e una descrizione per l'insieme di credenziali delle chiavi, quindi nel campo **URI insieme di credenziali delle chiavi**, immettere l'URL che identifica la risorsa di tale insieme in Azure.
4. nella Scheda dettaglio **Certificati**, selezionare **Aggiungi** per aggiungere il certificato e imettere un nome e una descrizione per ogni certificato.

    ![Certificato aggiunto](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Selezionare **Nuovo** per creare un nuovo ambiente.
6. Immettere un nome, una descrizione e il segreto del token di firme di accesso condiviso necessario per l'archiviazione.
7. Nella Scheda dettagli **Utenti**, selezionare **Nuovo** per aggiungere un utente che avrà l'autorizzazione di accedere a questo ambiente.
8. Immettere l'ID utente e l'indirizzo e-mail dell'utente.
9. Ripetere i passaggi 7 e 8 per aggiungere altri utenti.
10. Selezionare **Pubblica** per pubblicare l'ambiente.

    ![Ambiente pubblicato](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]