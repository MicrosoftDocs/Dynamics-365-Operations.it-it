---
title: I dipendenti selezionano i piani tramite il self-service dipendenti (opzionale)
description: Questo argomento descrive come i dipendenti possono selezionare o aggiornare i propri benefit.
author: twheeloc
ms.date: 12/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 190eb7e437af7edd8eee97b8f2b7601254cbd240
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066420"
---
# <a name="employees-select-plans-by-using-employee-self-service-optional"></a>I dipendenti selezionano i piani tramite il self-service dipendenti (opzionale)


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Quando viene assunto un nuovo dipendente o si verifica un evento reale, il dipendente può utilizzare **Self service dipendente** per selezionare o aggiornare i propri benefit durante l'iscrizione aperta.

Per accedere ai propri benefit per l'iscrizione, il dipendente va in **Self-service dipendente** e poi seleziona **Self-service benefit** nel riquadro **Benefit**.

Nella pagina **Self-service benefit**, i piani di benefit sono raggruppati per tipo di piano. Per visualizzare i piani di benefit in un tipo di piano, il dipendente seleziona un riquadro nella pagina **Benefit dipendente**. Il dipendente vedrà solo i benefit a cui ha diritto.

> [!IMPORTANT]
> Prima che un tipo di piano possa essere mostrato in **Self-service dipendenti**, deve essere configurato. Per ulteriori informazioni, vedi [Configurare il self-service dipendenti](/hr-benefits-setup-employee-self-service.md).

A seconda del tipo di piano, è possibile selezionare uno o più benefit per l'iscrizione. Ad esempio, un tipo di piano medico potrebbe essere configurato per limitare il dipendente a un piano medico. Un tipo di piano di assicurazione sulla vita potrebbe consentire al dipendente di selezionare più piani di assicurazione sulla vita.

Dopo che il dipendente ha deciso a quale piano iscriversi, potrebbe essere richiesto di selezionare le persone a carico. Se il dipendente ha selezionato un'opzione di copertura che è **Dipendente +1**, **Dipendente + figli**, o **Famiglia**, le persone a carico devono essere selezionate. Per ulteriori informazioni sulle opzioni di copertura vedi [Creare le opzioni di copertura](/hr-benefits-setup-coverage-options.md).

Per selezionare un piano di benefit, il dipendente seleziona il pulsante con i puntini di sospensione (**...**) o **Aggiungi al carrello**. Dopo che il dipendente ha finito di aggiungere tutte le selezioni di benefit al carrello, seleziona **Visualizza carrello**. Il dipendente viene quindi portato alla pagina **Piani** dove può visualizzare i piani di benefit selezionati e rinunciati.

Il dipendente deve selezionare l'opzione **Accetto** prima di poter selezionare il pulsante **Pagamento**. La dichiarazione che appare a destra dell'opzione **Accetta** può essere personalizzata nella scheda **Gestione benefit** della pagina **Parametri condivisi delle risorse umane**.

Quando il dipendente conferma la selezione del piano di benefit utilizzando **Self-service dipendenti**, tali selezioni vengono registrate e mostrate nelle pagine **Piani di benefit per i lavoratori** e **Aggiornamento in blocco dei piani di benefit per i lavoratori**.

Dopo che il dipendente ha selezionato i propri piani, lo stato dei benefit è indicato come **Selezionato**. Quando il dipendente seleziona **Pagamento** nella pagina **Self-service beneffit** l'opzione **Pagato** sarà selezionata.

> [!IMPORTANT]
> Per completare l'iscrizione, l'amministratore dei benefit deve selezionare **Conferma** per ogni benefit dei dipendenti selezionato. La conferma può essere completata nelle pagine **Piano di benefit per i lavoratori** o **Aggiornamento in blocco dei piani di benefit per i lavoratori**.
>

I dipendenti non sono tenuti a selezionare i benefit utilizzando **Self-service dipendenti**. I benefici possono essere selezionati per conto di un dipendente nella pagina **Piano di benefit per i lavoratori** o **Aggiornamento in blocco dei piani di benefit per i lavoratori**. Il dipendente non sarà iscritto a tali benefit fino a quando l'amministratore dei benefit non li conferma.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
