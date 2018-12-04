---
title: Calendari orario di lavoro
description: "Questo argomento descrive i calendari orario di lavoro in Dynamics 365 for Talent - Core HR, nonché come impostare i calendari."
author: jcart1106
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1bf37d65cd8ce6a98fc2d2fb11ae9587cf6958a3
ms.openlocfilehash: 2465065d7db18a5468d7c979e0d6cb9c7e76f969
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---

# <a name="working-time-calendars"></a>Calendari orario di lavoro

[!include [banner](includes/banner.md)]

Il calendario orario di lavoro consente di creare un calendario con gli orari e i giorni in cui i dipendenti lavorano nell'organizzazione. I calendari semplificano il processo di richiesta di permessi per impostazione predefinita in ore o in giorni. Quando un dipendente invia una richiesta di permesso, non deve preoccuparsi delle vacanze e delle chiusure, perché queste vengono gestite automaticamente nel calendario orario di lavoro.

## <a name="setting-up-a-working-time-calendar"></a>Impostazione di un calendario orario di lavoro

I calendari includono dettagli di generazione, i giorni e gli orari che si desidera includere, i giorni del calendario, gli orari di lavoro per quei giorni nonché i dipendenti iscritti. 

Per impostare un calendario, seguire questi passaggi:

1. Nella pagina **Amministrazione organizzazione** fare clic su **Calendari**.

2. Nel riquadro azioni selezionare **Nuovo** e immettere un nome e una descrizione.

3. Scegliere i giorni di lavoro per l'organizzazione e immettere l'orario di lavoro.

4. Aggiungere le festività e le chiusure utilizzando il pulsante **Aggiungi**.

5. Immettere il nome e la descrizione delle festività e delle chiusure, ad esempio le festività negli Stati Uniti o le festività pubbliche. Immettere le date delle festività e delle chiusure. Salvare l'elenco delle festività e delle chiusure e chiudere la pagina.

6. Selezionare l'elenco delle festività e delle chiusure nel menu a discesa.

7. Se i dipendenti dispongono di tempo non lavorativo, ad esempio pause pranzo o intervalli, aggiungere anche queste informazioni. Selezionare **Orario non lavorativo** e immettere il nome e la fascia oraria. Chiudere la pagina. 

8. Fare clic su **Aggiungi** per aggiungere l'orario non lavorativo al calendario.

9. Nella scheda **Giorni** selezionare **Genera** per generare i giorni nel calendario. Immettere l'intervallo di dati per il calendario. I giorni e gli orari di lavoro vengono generati in base ai giorni e alle ore di lavoro definiti nelle opzioni di generazione insieme alle date selezionate.

10. Per assegnare un calendario ai dipendenti, nel riquadro azioni selezionare **Assegna ai dipendenti**. Selezionare i dipendenti a cui si desidera assegnare il calendario e quindi fare clic su **Assegna**.

Per i dipendenti non è obbligatorio avere calendari assegnati. Se è presente un calendario orario di lavoro definito, i giorni non lavorativi vengono esclusi automaticamente dalla richiesta. La quantità, in ore o giorni, è per impostazione predefinita pari alle ore di lavoro definite nel calendario. Se a un dipendente non è assegnato un calendario, tutti i giorni sono disponibili per il permesso e la quantità di permessi non è il valore predefinito per la richiesta. 

