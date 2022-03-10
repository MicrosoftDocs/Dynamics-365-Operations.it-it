---
title: Rendiconto benefit
description: Il report Rendiconto benefit spiega i benefit a cui un dipendente è attualmente iscritto.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 65bf91faba049b3fed4d80e020d77b82e48cceb6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068997"
---
# <a name="benefit-statement"></a>Rendiconto benefit


[!INCLUDE [PEAP](../includes/peap-2.md)]

Il report **Rendiconto benefit** fornisce un rendiconto dei benefit a cui un dipendente è attualmente iscritto. Il report può essere consultato direttamente da un dipendente o dall'amministratore dei benefit. Il report **Rendiconto benefit** fornisce un elenco dei benefit a cui il dipendente è iscritto, delle opzioni di copertura, dei costi e di eventuali dipendenti o beneficiari iscritti. Il rendiconto può essere stampato per un singolo lavoratore o più lavoratori.

> [!NOTE]
La funzionalità **Rendiconto benefit** deve essere abilitata nell'area di lavoro **Gestione funzionalità**. Per eseguire questa operazione, la funzionalità **Gestione benefit** deve essere attivata in Gestione funzionalità. 


## <a name="importing-the-benefit-statement"></a>Importazione del rendiconto benefit 

È necessario importare il **Rendiconto benefit** utilizzando la configurazione del report affinché il **Rendiconto benefit** sia disponibile. Per effettuare questa operazione, attenersi alla seguente procedura:

1.  Andare all'area di lavoro **Amministrazione sistema**.

2.  Selezionare il riquadro **Creazione di report elettronici**.

3.  Andare a **Provider di configurazione** e selezionare **Archivi**.

  ![Selezione degli archivi.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Selezionare **Risorse HR** dall'elenco, quindi selezionare **Apri**.

    ![Archivi di configurazioni.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Selezionare il **Modello rendiconto benefit** nel riquadro di sinistra ed espanderlo in modo che **Formato rendiconto benefit** venga visualizzato.

6.  Selezionare **Formato rendiconto benefit** nel riquadro di sinistra.

7.  Sul lato destro dello schermo sarà disponibile una Scheda dettaglio **Versioni**. Selezionare **Importa**.

    ![Scheda dettaglio Versioni.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Generare il rendiconto benefit come file PDF

Per impostazione predefinita, il **rendiconto benefit** verrà stampato come documento di Microsoft Word. Per stamparlo in formato PDF, è necessario configurare l'opzione PDF in **Destinazione Creazione di report elettronici**. 

1. Per farlo, andare all'**Area di lavoro Amministrazione sistema** > **Creazione di report elettronici** > **Collegamenti correlati** > **Destinazione Creazione di report elettronici**.

1.  Selezionare **Nuovo**.

2.  Nel campo **Riferimento**, selezionare **Formato rendiconto benefit**.

3.  Sulla Scheda dettaglio **Destinazione file**, selezionare **Nuovo**.

4.  Nel campo **Nome**, immettere **PDF rendiconto benefit**.

5.  Nel campo **Nome componente file**, selezionare **Rendiconto benefit**.

6.  Selezionare la casella di controllo **Converti in PDF**.

7.  Selezionare **Impostazioni** dalla voce di menu. 

    ![Destinazione file.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Selezionare la Scheda dettaglio **File**, quindi selezionare **Abilitato**.

9.  Selezionare **OK**.
   
> [!NOTE]
> La funzionalità di gestione benefit è nello stato Anteprima. Esiste un problema noto quando si utilizza l'impostazione della destinazione di posta elettronica nel report **Destinazione Creazione di report elettronici**. Si potrebbe ricevere un messaggio di errore e il messaggio di posta elettronica non verrà inviato.

Il **Rendiconto benefit** può essere generato dalle seguenti pagine:

-   **Area di lavoro gestione benefit** > **Collegamenti** > **Report** > **Rendiconto benefit**

-   **Dipendenti (modulo legacy)** > **Scheda Informazioni personali** > **Rendiconto benefit**

-   **Inserimento dipendenti semplificato** > **Report benefit** > **Rendiconto benefit**

-   **Self-service dipendenti** > **Benefit** > **Visualizza rendiconto benefit**

> [!NOTE]
>  L'accesso al **Rendiconto benefit** in **Self-service dipendenti** è controllato dal privilegio **Visualizza rendiconto benefit**. Si trova nei diritti **Benefit self-service dipendenti**. Questo privilegio è concesso ai dipendenti per impostazione predefinita.

## <a name="report-contents"></a>Contenuti del report

Il **Rendiconto benefit** stamperà le selezioni del piano confermato del dipendente, inclusi eventuali piani a cui ha rinunciato. L'immagine seguente illustra un esempio di questo report. 

![Report Rendiconto benefit.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

Il report mostrerà **Piano**, **Opzione di copertura**, **Costo dipendente** e **Costo datore di lavoro**. Il rapporto elencherà anche gli eventuali dipendenti coperti. Se al piano sono associati dei beneficiari, questi e la relativa priorità di distribuzione e percentuale verranno visualizzati.

Il report **Rendiconto benefit** può essere stampato per più dipendenti contemporaneamente utilizzando la Scheda dettaglio **Record da includere** nella pagina **Rendiconto benefit**.
