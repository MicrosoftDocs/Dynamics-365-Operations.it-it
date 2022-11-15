---
title: Configurare le attività in Gestione attività
description: Questo articolo spiega come configurare le attività in Gestione attività in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745388"
---
# <a name="set-up-tasks-in-task-management"></a>Configurare le attività in Gestione attività

[!INCLUDE [PEAP](../includes/peap-1.md)]

Nelle versioni di Microsoft Dynamics 365 Human Resources precedenti alla versione 10.0.30, gli utenti che desideravano modificare un'attività dovevano modificare individualmente quell'attività su ogni elenco di controllo che la conteneva. Tuttavia, a partire dalla versione 10.0.30 di Human Resources, gli utenti possono selezionare la modalità di gestione delle attività modificate. Se un'attività in fase di modifica è in un elenco di controllo, l'opzione **Abilita aggiornamento gestione attività** deve essere selezionata nella scheda **Gestione attività** della pagina **Parametri condivisi Risorse umane** per consentire all'elenco di controllo di utilizzare l'attività modificata.

[![Abilitare l'opzione di aggiornamento della gestione delle attività nella pagina dei parametri condivisi di Human Resources.](./media/task-update.png)](./media/task-update.png)

Se le modifiche alle attività devono essere applicate a tutte le attività dell'elenco di controllo associate, deve già esistere una relazione tra l'attività nella libreria delle attività e l'attività nell'elenco di controllo. È stata aggiunta un'opzione per creare la relazione tra l'attività della libreria e l'attività dell'elenco di controllo.

Puoi creare attività individualmente e quindi riutilizzarle in più elenchi di controllo. Per creare un'attività, nella pagina **Impostazione onboarding** nella scheda **Attività** seleziona **Nuovo**.

## <a name="set-up-tasks"></a>Configurare le attività

Per assegnare un'attività creata a più elenchi di controllo, seleziona l'attività e quindi seleziona **Applica a elenchi di controllo** nel menu.

In alternativa, puoi aggiungere attività direttamente a un elenco di controllo. Per aggiungere un'attività a un elenco di controllo, nella pagina **Impostazione onboarding** nella scheda **Elenco di controllo** crea un nuovo elenco di controllo a cui aggiungere l'attività o aggiungi l'attività a un elenco di controllo esistente.

Per modificare un'attività nella libreria, seleziona **Modifica** nel menu della libreria delle attività. Se l'attività è associata a delle liste di controllo, tali liste di controllo verranno visualizzate nella pagina **Modifica attività**. Se desideri che le attività in uno qualsiasi degli elenchi di controllo vengano aggiornate con le modifiche, seleziona tali elenchi di controllo nella sezione **Applica a elenchi di controllo**.

Per eliminare le attività dalla libreria delle attività, seleziona **Elimina**. Se l'attività è associata a un elenco di controllo, questa azione non eliminerà l'attività dall'elenco di controllo. È necessaria un'azione separata per rimuovere un'attività da un elenco di controllo.

### <a name="set-up-checklists"></a>Configurare elenchi di controllo

Un elenco di controllo è un gruppo di attività. Puoi creare tutti gli elenchi di controllo di cui hai bisogno e puoi assegnare le stesse attività a più elenchi di controllo. Quando crei un elenco di controllo, specifichi un proprietario e un calendario.

Per creare una nuova attività in un elenco di controllo, seleziona **Nuovo** nella barra dei menu delle attività. Quando crei una nuova attività, puoi scegliere facoltativamente di aggiungerla alla libreria delle attività, in modo che possa essere condivisa tra più elenchi di controllo. Per aggiungere l'attività alla libreria delle attività, devi impostare l'opzione **Applica attività alla libreria** su **Sì**. Se scegli di aggiungere l'attività alla libreria delle attività, puoi anche aggiungerla ad altri elenchi di controllo contemporaneamente selezionando tali elenchi di controllo nella sezione **Applica a elenchi di controllo**. Se scegli di non aggiungere l'attività alla libreria delle attività, esisterà solo nell'elenco di controllo in cui la crei.

Per modificare un'attività in un elenco di controllo, seleziona **Modifica** nel menu delle attività. Se l'attività è associata a delle liste di controllo, tali liste di controllo verranno visualizzate nella pagina **Modifica attività**. Se desideri che le attività in uno qualsiasi degli altri elenchi di controllo vengano aggiornate con le modifiche, seleziona tali elenchi di controllo nella sezione **Applica a elenchi di controllo**.

Per rimuovere le attività da un elenco di controllo, seleziona **Rimuovi**. Questa azione rimuoverà semplicemente le attività dall'elenco di controllo. Tuttavia, non eliminerà le attività dalla libreria delle attività. Per eliminare le attività dalla libreria, apri la pagina **Libreria attività** e seleziona **Elimina**.
