---
title: Incorporare app di Power Apps in Dynamics 365 - Core HR
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
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830211"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Incorporare app di Power Apps in Dynamics 365 - Core HR

[!include [banner](includes/banner.md)]

**Problema**

La voce di menu **Power Apps** non è più visualizzata nel modulo **Amministrazione sistema**.

**Causa**

Il design dell'interfaccia utente è stato modificato e Microsoft Power Apps è ora incluso nel modello di personalizzazione standard.

**Risoluzione**

Il modo in cui le Power Apps sono incorporate è stato modificato. Le Power Apps ora vengono aggiunte tramite il modello di personalizzazione. È possibile aggiungere le Power Apps a quasi tutte le pagine in Microsoft Dynamics 365 Talent.

Per informazioni su come incorporare Power Apps in Talent, vedere [Incorporare Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Qualsiasi cliente Power Apps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.

Il pulsante **Power Apps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent. È possibile utilizzare questo pulsante per inserire le Power Apps.

Ecco un esempio.

1. Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.
2. Selezionare il pulsante **Power Apps** e quindi selezionare **Inserisci una PowerApp**.

    ![Pulsante Power Apps](media/png.png)

3. Completare i campi nella finestra di dialogo **Inserisci una PowerApp**.

    ![Finestra di dialogo Inserisci una PowerApp](media/insert-powerapp.png)

In alternativa, seguire la procedura seguente.

1. Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza modulo**.

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    Viene visualizzata la barra degli strumenti di personalizzazione.

2. Nella barra degli strumenti, selezionare **Inserisci \> PowerApp**.

    ![Inserire un app di Power Apps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)
