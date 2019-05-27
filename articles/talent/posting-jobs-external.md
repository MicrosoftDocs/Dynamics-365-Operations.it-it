---
title: Pubblicazione di annunci di lavoro su siti di avanzamento professionale esterni da Attract
description: In questo argomento viene descritto come utilizzare Dynamics 365 for Talent - Attract per pubblicare annunci di lavoro su siti di reclutamento esterni
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518375"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a>Pubblicazione di annunci di lavoro su siti di avanzamento professionale esterni da Attract

[!include [banner](../includes/banner.md)]

Se si desidera rendere visibili le posizioni aperte nella propria azienda al maggior numero possibile di candidati, esistono siti di reclutamento come Broadbean che consentono di soddisfare tale esigenza. Microsoft Dynamics 365 Talent: Attract consente ora di pubblicare annunci di lavoro su Broadbean e Microsoft fornisce costantemente nuove offerte in quest'area.

## <a name="post-jobs-to-broadbean"></a>Pubblicare annunci di lavoro su Broadbean

Prima di pubblicare annunci di lavoro su Broadbean, è necessario configurare l'integrazione di tale piattaforma.

> [!NOTE]
> - Per pubblicare annunci di lavoro su siti esterni, è necessario disporre del [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).
> - Questa funzionalità è attualmente in anteprima. Se si desidera provarlo, è necessario [attivarlo nelle impostazioni di amministrazione di Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="configure-broadbean-integration"></a>Configurare l'integrazione di Broadbean

1. Accedere a Attract come amministratore.
2. Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro della pagina, quindi selezionare **Interfaccia di amministrazione**.
3. Nella scheda **Impostazioni bacheca mansioni**, nella sezione **Abilita integrazione di Broadbean**, attivare l'integrazione.
4. Contattare Broadbean e immettere le informazioni in **Nome utente, ID client, Token di crittografia**.

> [!WARNING]
> Le credenziali Broadbean sono sensibili e riservate. Di conseguenza, conservarle e condividerle in modo responsabile. Chiunque abbia un ruolo di amministratore in Attract può visualizzare tali credenziali.

> [!NOTE]
> Microsoft e Attract non partecipano alla creazione e alla gestione di tali dati. È responsabilità dell'utente mantenerli aggiornati in Attract e collaborare con Broadbean per risolvere eventuali problemi relativi alle credenziali.

### <a name="post-a-job-to-broadbean"></a>Pubblicare un annuncio di lavoro su Broadbean

Dopo l'attivazione di Broadbean, i selezionatori e gli amministratori possono pubblicarvi un annuncio di lavoro. È necessario disporre dell'URL della domanda per l'annuncio di lavoro.

1. In Attract, aprire l'annuncio di lavoro che si intende pubblicare su Broadbean.
2. Nella sezione **Registrazioni**, selezionare il pulsante **Pubblica ora** corrispondente a Broadbean.
3. Seguire le istruzioni nella finestra di Broadbean.

Attract passa le seguenti informazioni a Broadbean:

- ID richiesta
- Titolo posizione
- Descrizione posizione
- Ubicazione posizione
- URL della domanda
- Informazioni selezionatore

Dopo il completamento della pubblicazione, lo stato Broadbean nella sezione **Registrazioni** dell'annuncio di lavoro in Attract è **Pubblicato**.

> [!NOTE]
> - Broadbean richiede il campo **Settore**. Attualmente, l'impostazione predefinita di questo campo è **IT**. Tuttavia, è possibile impostare il settore corretto nella finestra per la pubblicazione dell'annuncio di lavoro di Broadbean.
> - La pubblicazione dell'annuncio di lavoro mediante Broadbean in tutte le bacheche mansioni selezionate può richiedere un certo tempo. Di conseguenza, è possibile che lo stato dell'annuncio di lavoro in Attract venga aggiornato con leggero ritardo.

### <a name="view-a-broadbean-job-posting"></a>Visualizzare la pubblicazione di un annuncio di lavoro in Broadbean

Dopo aver pubblicato un annuncio di lavoro su Broadbean, è possibile visualizzarlo da Attract.

1. In Attract, aprire l'annuncio di lavoro da visualizzare in Broadbean.
2. Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.

La pubblicazione dell'annuncio di lavoro in Broadbean è visualizzata in una nuova finestra.

### <a name="update-a-broadbean-job-posting"></a>Aggiornare la pubblicazione di un annuncio di lavoro in Broadbean

È possibile aggiornare la pubblicazione di un annuncio di lavoro in Broadbean in due modi.

1. In Attract, aprire l'annuncio di lavoro da aggiornare.
2. Nella sezione **Registrazioni**, selezionare il pulsante **Aggiorna pubblicazione** corrispondente a Broadbean.
3. Modificare la pubblicazione nella finestra di Broadbean.

oppure

1. In Attract, aprire l'annuncio di lavoro da visualizzare in Broadbean.
2. Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.
3. Nella finestra di Broadbean, modificare i dettagli dell'annuncio di lavoro e quindi ripubblicarlo. I dettagli dell'annuncio di lavoro in Attract non vengono modificati.

### <a name="remove-a-broadbean-job-posting"></a>Rimuovere la pubblicazione di un annuncio di lavoro da Broadbean

È possibile rimuovere la registrazione di un annuncio di lavoro da Broadbean.

1. In Attract, aprire l'annuncio di lavoro da rimuovere.
2. Nella sezione **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Rimuovi pubblicazione**.

Dopo che Broadbean rimuove l'annuncio di lavoro, l'elemento Broadbean in Attract presenta il pulsante **Pubblica ora**. La presenza di questo pulsante indica che l'annuncio di lavoro è stato rimosso e può essere pubblicato nuovamente.

### <a name="troubleshoot-the-broadbean-integration"></a>Risolvere i problemi relativi all'integrazione di Broadbean

In caso di problemi nel pubblicare un annuncio di lavoro su Broadbean, effettuare quanto segue.

1. Verificare che le credenziali di Broadbean immesse in Attract siano valide e corrette.
2. Se le credenziali sono valide e corrette, contattare il [supporto Broadbean](https://www.broadbean.com/resources/support/).
3. Se il problema persiste, contattare il [supporto tecnico Microsoft](./talent-support.md).
