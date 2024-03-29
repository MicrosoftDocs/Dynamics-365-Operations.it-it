---
title: Importare versioni aggiornate delle configurazioni ER
description: In questo articolo viene descritto come importare le versioni aggiornate delle configurazioni per la creazione di report elettronici (ER) dall'archivio globale del servizio di configurazione.
author: kfend
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
ms.openlocfilehash: 0eef9c9a112fd58a43f6c3a85163ccf44bea3d61
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292648"
---
# <a name="import-updated-versions-of-er-configurations"></a>Importare versioni aggiornate delle configurazioni ER

[!include [banner](../includes/banner.md)]

Gli [archivi](general-electronic-reporting.md#Repository) per la creazione di report elettronici sono usati per condividere le [configurazioni ER](general-electronic-reporting.md#Configuration). Puoi [importare](download-electronic-reporting-configuration-lcs.md) configurazioni ER da diversi archivi nell'istanza di Microsoft Dynamics 365 Finance. Quando importi configurazioni ER, i [provider di configurazione](general-electronic-reporting.md#Provider) possono pubblicare nuove versioni di archivi in modo che possano essere condivisi.

In questo articolo viene descritto come importare le versioni aggiornate delle configurazioni ER dall'archivio globale del servizio di configurazione. Per ulteriori informazioni, vedere [Microsoft Dynamics 365 Finance - Regulatory services, Servizio di configurazione](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).

## <a name="review-the-available-updated-versions"></a>Rivedere le versioni aggiornate disponibili

1. Accedi a Finance utilizzando uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Importa aggiornamenti versioni di configurazione**.

    ![Pagina Configurazioni Localizzazione.](./media/er-download-updated-versions-global-repo1.png)

4. Nella finestra di dialogo **Importa aggiornamenti versioni delle configurazioni per la creazione di report elettronici**, nel campo **Modalità di esecuzione**, seleziona **Mostra solo gli aggiornamenti disponibili**. Selezionare **OK**. 

    ![Campo modalità di esecuzione impostato su Mostra solo gli aggiornamenti disponibili.](./media/er-download-updated-versions-global-repo2.png)

5. Rivedi i messaggi che ricevi. Questi messaggi forniscono le seguenti informazioni sulle configurazioni ER nell'istanza di Finance corrente e su come si confrontano con il contenuto dell'archivio globale:

    - Il numero totale di configurazioni ER
    - Configurazioni ER che non sono presenti nell'archivio globale
    - Configurazioni ER per le quali l'ultima versione è già disponibile nell'istanza Finance corrente (per visualizzare l'elenco completo di queste configurazioni ER, seleziona il collegamento **Dettagli messaggio**.)

        ![Dettagli messaggio e messaggio "Le ultime versioni delle seguenti configurazioni sono già importate"](./media/er-download-updated-versions-global-repo3.png)

    - Configurazioni ER per le quali l'ultima versione è già disponibile nell'archivio globale e che possono essere importate nell'istanza Finance corrente (per visualizzare l'elenco completo di queste configurazioni ER, seleziona il collegamento **Dettagli messaggio**.)

        ![Messaggio "Aggiornamenti disponibili" e dettagli del messaggio](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a>Importare le versioni aggiornate disponibili

1. Accedi a Finance utilizzando uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

2. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
3. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Importa aggiornamenti versioni di configurazione**.
4. Nella finestra di dialogo **Importa aggiornamenti versioni delle configurazioni per la creazione di report elettronici**, nel campo **Modalità di esecuzione**, seleziona **Importa gli ultimi aggiornamenti** per importare le ultime versioni delle configurazioni ER dall'archivio globale nell'istanza Finance corrente.
5. Per pianificare un processo batch per l'importazione, nella Scheda dettaglio **Esegui in background**, imposta l'opzione **Elaborazione in batch** su **Sì**. Se vuoi ripetere periodicamente l'importazione, configura la ricorrenza richiesta.

    ![Campo modalità di esecuzione impostato su Importa gli ultimi aggiornamenti.](./media/er-download-updated-versions-global-repo5.png)

6. Selezionare **OK**.
7. Per sapere quali versioni di configurazione sono state importate, segui uno di questi passaggi:

    - Se esegui l'importazione in modo interattivo anziché utilizzare un processo batch, rivedi i messaggi ricevuti.

        ![Messaggi ricevuti durante un'esecuzione di importazione interattiva.](./media/er-download-updated-versions-global-repo6.png)

    - Se esegui l'importazione in modalità batch, attieniti alla seguente procedura:

        1. Vai a **Elementi comuni** \> **Richieste di informazioni** \> **Processi batch** \> **Processi batch personali**.
        2. Trova e seleziona il processo **Importa aggiornamenti versioni delle configurazioni per la creazione di report elettronici**, quindi, nel riquadro azioni, nella scheda **Processo in batch**, seleziona **Cronologia dei processi batch** per visualizzare la cronologia dei processi.
        3. Nella pagina **Cronologia dei processi batch**, seleziona **Registro**. Quindi, nel messaggio che ricevi, seleziona il collegamento **Dettagli messaggio** per visualizzare il registro del processo.

        ![Registro processo.](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> Non è consigliabile pianificare un processo batch ricorrente per importare le versioni aggiornate delle configurazioni ER direttamente dall'archivio globale in un ambiente di produzione, poiché le versioni importate saranno immediatamente disponibili per l'uso. Utilizza invece questo approccio per distribuire le versioni delle configurazioni ER in un ambiente sandbox. Possono quindi essere valutate nell'ambiente sandbox prima di essere distribuite in un ambiente di produzione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
