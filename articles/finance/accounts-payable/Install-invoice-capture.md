---
title: Installare la soluzione Invoice Capture
description: Questo articolo fornisce informazioni su come installare la soluzione Invoice Capture e integrarla con Microsoft Dynamics 365 Finance.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691232"
---
# <a name="install-the-invoice-capture-solution"></a>Installare la soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Se hai installato la soluzione in anteprima privata, devi disinstallare la vecchia soluzione prima di continuare.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter installare la soluzione Invoice Capture, è necessario soddisfare i seguenti prerequisiti:

1. Registra un'applicazione e aggiungi un segreto cliente a Microsoft Azure Active Directory (Azure AD) sotto il tuo abbonamento Azure. Per ulteriori informazioni, vedi [Registrare un'applicazione Web con AAD](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Prendi nota dei valori **ID dell'applicazione (cliente)**, **segreto del cliente** e **ID tenant** , perché ne avrai bisogno in seguito.

2. Registra l'applicazione Azure in un ambiente Dynamics 365 Finance. Per ulteriori informazioni, vedi [Registrare un'applicazione esterna](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>Installare e configurare la soluzione

Per installare la soluzione Invoice Capture, vai a AppSource e seleziona il collegamento per la versione di anteprima di [Dynamics 365 Invoice Capture](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). Al termine dell'installazione, vedrai la soluzione installata nell'ambiente selezionato in Power Apps.

Per completare la configurazione, segui questi passaggi.

1. Scarica la [soluzione dell'assistente](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip) per configurare i seguenti dettagli:

    - La comunicazione tra Microsoft Power Platform e l'ambiente Finance
    - Il riferimento a una connessione per Dataverse e Office 365 Outlook che verrà utilizzato dal canale

2. In Power Apps, vai al tuo ambiente e seleziona **Importa soluzione**.
3. Seleziona **Sfoglia**, seleziona il pacchetto della soluzione dell'assistente che hai scaricato, quindi seleziona **Avanti**.
4. Selezionare **Avanti**.
5. Assegna una connessione esistente o creane una nuova selezionando **Nuova connessione**.
6. Dopo che il pacchetto è stato importato correttamente, apri **Dynamics 365 Invoice Capture – Strumenti di installazione**.
7. Esegui il flusso cloud per configurare la connessione tra la soluzione Invoice Capture in Microsoft Power Platform e Finance.
8. Seleziona **Esegui** e specifica i seguenti parametri:

    - **URL di Dynamics 365 Finance** – L'URL dell'ambiente Finance con cui si desidera eseguire l'integrazione.
    - **ID tenant** - L'ID tenant per l'ambiente Finance.
    - **ID client** – L'ID dell'applicazione Azure che è stato registrato.
    - **Segreto client** - Il segreto client generato per l'applicazione Azure.
