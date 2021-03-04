---
title: Pubblicare posizioni in Broadbean da Attract
description: In questo argomento viene descritto come utilizzare Dynamics 365 Talent - Attract per pubblicare posizioni su Broadbean
author: pganapmsft
manager: AnnBe
ms.date: 05/16/2019
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
ms.openlocfilehash: 41fa057606887069a9ea0f1f2178eeaff59f33ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461682"
---
# <a name="post-jobs-to-broadbean-from-attract"></a>Pubblicare posizioni in Broadbean da Attract

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Attract aiuta a trovare i talenti necessari a un'azienda attraverso la pubblicazione di posizioni direttamente da Attract in Broadbean. Dopo la [creazione di una posizione](./creating-jobs-attract.md), è sufficiente selezionare un pulsante per presentarla a tutti i potenziali candidati su Broadbean.

Per pubblicare le posizioni su Broadbean è necessario disporre di una licenza Broadbean appropriata. Broadbean offre vari prodotti e piani. Per ulteriori informazioni sulle licenze e sui prezzi di Broadbean, [contattare Broadbean](https://www.broadbean.com/contact-us/).

Se si è un amministratore e sono necessarie ulteriori informazioni su come configurare l'integrazione di Broadbean con Attract, vedere [Abilitare l'integrazione di Broadbean in Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md).

## <a name="post-jobs-to-broadbean"></a>Pubblicare posizioni in Broadbean

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
2. Nella scheda **Registrazioni**, selezionare il pulsante con i puntini di sospensione (**...**) corrispondente a Broadbean, quindi selezionare **Visualizza**.

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

### <a name="troubleshoot-job-posting-to-broadbean"></a>Risolvere i problemi relativi alla pubblicazione di posizioni su Broadbean

In caso di problemi nel pubblicare un annuncio di lavoro su Broadbean, effettuare quanto segue.

1. Verificare che le credenziali di Broadbean immesse in Attract siano valide e corrette.
2. Se le credenziali sono valide e corrette, contattare il [supporto Broadbean](https://www.broadbean.com/resources/support/).
3. Se il problema persiste, contattare il [supporto tecnico Microsoft](./talent-support.md).

## <a name="see-also"></a>Vedere anche

[Creare, approvare e pubblicare annunci di mansioni in Attract](./creating-jobs-attract.md)

[Abilitare l'integrazione di Broadbean in Microsoft Dynamics 365 Talent - Attract](./attract-admin-job-board-settings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]