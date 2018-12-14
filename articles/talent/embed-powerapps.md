---
title: Incorporare app di PowerApps in Core HR
description: "In questo argomento viene descritto come risolvere il problema in cui la voce di menu PowerApps non è più visualizzata nel modulo Amministrazione sistema."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.contentlocale: it-it
ms.lasthandoff: 12/04/2018

---

# <a name="embed-powerapps-apps-in-core-hr"></a>Incorporare app di PowerApps in Core HR

[!include [banner](includes/banner.md)]

**Uscita**

La voce di menu **PowerApps** non è più visualizzata nel modulo **Amministrazione sistema**.

**Causa**

Il design dell'interfaccia utente è stato modificato e Microsoft PowerApps è ora incluso nel modello di personalizzazione standard.

**Risoluzione**

Il modo in cui le app di PowerApps sono incorporate è stato modificato. Le app di PowerApps ora vengono aggiunte tramite il modello di personalizzazione. È possibile aggiungere app di PowerApps a quasi tutte le pagine in Microsoft Dynamics 365 for Talent.

Per informazioni su come incorporare app di PowerApp in Talent, consultare [Incorporare le app di PowerApps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Qualsiasi cliente PowerApps che ha incorporato app prima della modifica deve eseguire l'aggiornamento al nuovo modello.

Il pulsante **PowerApps** è disponibile nell'angolo superiore destro di quasi ogni pagina in Talent. È possibile utilizzare questo pulsante per inserire un app di PowerApps.

Ecco un esempio.

1. Accedere a **Gestione dipendente \> Collegamenti \> Lavoratori \> Dipendenti**.
2. Selezionare il pulsante **PowerApps** e quindi selezionare **Inserisci una PowerApp**.

    ![Pulsante PowerApps](media/png.png)

3. Completare i campi nella finestra di dialogo **Inserisci una PowerApp**.

    ![Finestra di dialogo Inserisci una PowerApp](media/insert-powerapp.png)

In alternativa, seguire la procedura seguente.

1. Nella scheda **Opzioni** del riquadro azioni della pagina, nel gruppo **Personalizza**, selezionare **Personalizza modulo**.

    ![Gruppo Personalizza nella scheda Opzioni](media/options.png)

    Viene visualizzata la barra degli strumenti di personalizzazione.

2. Nella barra degli strumenti, selezionare **Inserisci \> PowerApp**.

    ![Inserire un app di PowerApps utilizzando la barra degli strumenti di personalizzazione](media/powerapp-bar.png)

