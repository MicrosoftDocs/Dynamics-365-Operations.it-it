---
title: Incorporare app Power Apps in Dynamics 365 Human Resources
description: In questo argomento viene descritto come risolvere il problema in cui la voce di menu Microsoft Power Apps non è più visualizzata nel modulo Amministrazione sistema.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8275a8a7c68fa13d6b9880c4c411deaa2dcbb998
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461597"
---
# <a name="embed-power-apps-apps-in-dynamics-365-human-resources"></a>Incorporare app Power Apps in Dynamics 365 Human Resources

**Problema**

La voce di menu **Power Apps** non è più visualizzata nel modulo **Amministrazione sistema**.

**Causa**

Il design dell'interfaccia utente è stato modificato e Microsoft Power Apps è ora incluso nel modello di personalizzazione standard.

**Risoluzione**

Il modo in cui le Power Apps sono incorporate è stato modificato. Le Power Apps ora vengono aggiunte tramite il modello di personalizzazione. È possibile aggiungere le Power Apps a quasi tutte le pagine in Microsoft Dynamics 365 Talent.

Per informazioni su come incorporare Power Apps in Talent, vedere [Incorporare Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Qualsiasi cliente Power Apps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.

Il pulsante **Power Apps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent. È possibile utilizzare questo pulsante per inserire app.

Ecco un esempio.

1. Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.
2. Selezionare il pulsante **Power Apps**, quindi selezionare **Aggiungi un'app da Power Apps**.

    ![Pulsante Power Apps](media/png.png)

3. Completare i campi nella finestra di dialogo **Aggiungi un'app da Power Apps**.

    ![Finestra di dialogo Aggiungi un'app da Power Apps](media/insert-powerapp.png)

In alternativa, seguire la procedura seguente.

1. Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza questa pagina**.

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    Viene visualizzata la barra degli strumenti di personalizzazione.

2. Nella barra degli strumenti, selezionare **Aggiungi un'app da Power Apps**.

    ![Aggiungere un'app da Power Apps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]