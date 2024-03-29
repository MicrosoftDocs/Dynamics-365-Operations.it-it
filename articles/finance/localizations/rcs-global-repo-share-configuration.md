---
title: Condividi le configurazioni per la creazione di report elettronici in RCS/repository globale con organizzazioni esterne
description: Questo articolo spiega come condividere le configurazioni di report elettronici (ER) in Microsoft Regulatory Configuration Services (RCS)/repository globale direttamente con organizzazioni esterne.
author: kfend
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
ms.openlocfilehash: d9400ffcede9924a01391a433b570651d3f0c5e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284817"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>Condividere le configurazioni di report elettronici (ER) nel repository globale di Regulatory Configuration Services (RCS) con organizzazioni esterne

[!include [banner](../includes/banner.md)]

Puoi utilizzare Microsoft Regulatory Configuration Services (RCS) per condividere configurazioni di reporting elettronico (ER) e pubblicarle su organizzazioni esterne.

Le seguenti procedure spiegano come un utente RCS può condividere una versione di una configurazione ER che è stata configurata in un'istanza RCS con un'organizzazione esterna. Prima di poter completare queste procedure, devi completare i seguenti prerequisiti:

- Accesso a un'istanza RCS.
- Creare fornitore di configurazioni attivo. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
- Crea e carica una nuova versione di una configurazione ER. Per ulteriori informazioni, vedi [Crea e carica una nuova versione di una configurazione di creazione di report elettronici (ER)](rcs-global-repo-upload.md).

Puoi inoltre assicurarti che venga fornito un ambiente RCS per la tua azienda.

1. In un'app per la finanza e le operazioni, vai a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Se non è stato effettuato il provisioning di nessun ambiente RCS per la società, seleziona **Regulatory services - Configurazione** e segui le istruzioni per il provisioning di un ambiente.

Se è già stato eseguito il provisioning di un ambiente RCS per la tua azienda, utilizza l'URL della pagina per accedervi selezionando l'opzione di accesso.

## <a name="verify-the-configuration-that-you-want-to-share"></a>Verifica la configurazione che desideri condividere

Segui questi passaggi per verificare che la configurazione che si desidera condividere sia già stata caricata nel repository globale.

1. Nell'area di lavoro **Creazione di report elettronici**, seleziona **Repository** per il tuo provider di configurazioni.

    ![Provider di configurazione.](media/1_RCS_Repo_for_config_provider.JPG)

2. Seleziona **Repository globale** \> **Apri**.
3. Cerca la configurazione che desideri condividere. Puoi utilizzare il campo del filtro per restringere la ricerca. Se non riesci a trovare la configurazione nel repository globale, segui i passaggi in [Crea e carica una nuova versione di una configurazione di creazione di report elettronici (ER)](rcs-global-repo-upload.md).

## <a name="share-er-configurations-with-external-organizations"></a>Condividi le configurazioni ER con organizzazioni esterne

Dopo aver creato una configurazione con il tuo provider di configurazione, puoi condividerla direttamente con organizzazioni esterne utilizzando la Scheda dettaglio **Condiviso con** nella pagina **Repository di configurazioni globali**.

1. Nell'area di lavoro **Creazione di report elettronici**, seleziona **Repository** per il tuo provider di configurazioni.
2. Seleziona **Repository globale** \> **Apri**. 
3. Seleziona la configurazione che desideri condividere.
4. Nella Scheda dettaglio **Condiviso con**, seleziona **Organizzazione**.

    ![Condiviso con Scheda dettaglio.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. Nella finestra di dialogo, immetti il nome di dominio per l'organizzazione esterna, quindi seleziona **OK**.

    ![Condividere la versione di configurazione con la finestra di dialogo dell'organizzazione esterna.](media/1_RCS_Repo_for_Share_with_form.JPG)

La configurazione è condivisa con l'organizzazione esterna ed è disponibile per tale organizzazione nel repository globale. Da lì, può essere importata nell'istanza di RCS dell'organizzazione o nelle sue istanze delle app per la finanza e le operazioni.

6. Per annullare la condivisione di una configurazione precedentemente condivisa con un'organizzazione esterna, seleziona la configurazione e fai clic su **Annulla la condivisione**, quindi seleziona **OK**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
