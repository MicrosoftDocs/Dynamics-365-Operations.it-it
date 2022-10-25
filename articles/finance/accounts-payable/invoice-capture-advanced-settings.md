---
title: Impostazioni avanzate della soluzione Invoice Capture
description: In questo articolo vengono fornite informazioni sulle impostazioni avanzate nella soluzione Invoice Capture.
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
ms.openlocfilehash: a1e24b700d0f30fd90f2619dd6e6687736a86774
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691197"
---
# <a name="invoice-capture-solution-advanced-settings"></a>Impostazioni avanzate della soluzione Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo articolo vengono fornite informazioni sulle impostazioni avanzate nella soluzione Invoice Capture.

## <a name="create-additional-connections-for-channels"></a>Creare connessioni aggiuntive per i canali

È necessario creare connessioni all'e-mail o all'archiviazione di file per consentire il monitoraggio delle fatture in arrivo da diversi canali. È necessario registrare le connessioni all'inizio per concedere l'accesso ai flussi automatizzati utilizzati nella soluzione.

I seguenti tipi di connessione vengono utilizzati per importare le fatture:

- Office 365 Outlook
- Outlook.com
- OneDrive
- SharePoint

Il canale per l'importazione delle fatture utilizzerà le connessioni in ulteriori passaggi di configurazione. Prima che gli utenti possano creare un canale di una connessione specifica, il ruolo di sicurezza **Amministratore** deve essere loro concesso e devono creare connessioni.

Per creare una connessione a Microsoft Dataverse, segui questi passaggi.

1. Vai a **Amministrazione sistema \> Soluzione predefinita**.
2. Seleziona **Nuovo** e quindi seleziona **Riferimento a una connessione**.
3. Nel campo **Nome visualizzato** immetti un nome.
4. Seleziona **Microsoft Dataverse** come connettore.
5. Se stai configurando la connessione per la prima volta, seleziona **Nuova connessione**.
6. Nella finestra di dialogo visualizzata, crea una connessione Dataverse e quindi seleziona **Crea**.
7. Immetti l'account e la password Dataverse.
8. Dopo aver superato la convalida, vai alla pagina di connessione, seleziona **Aggiorna**, seleziona l'account, quindi seleziona **Crea**.

Per creare una connessione e-mail o archivio file, segui questi passaggi.

1. Sulla pagina **Creazione connessione**, nel campo **Tipo di connessione**, seleziona **Office 365 Outlook**.
2. Per una connessione e-mail, puoi selezionare **Outlook.com** o **Office 365 Outlook** come connettore. Per una connessione di archiviazione file, puoi selezionare **OneDrive** o **SharePoint**.

Per rivedere le connessioni esistenti, vai a **Soluzione predefinita \> Oggetti \> Riferimenti a una connessione**. L'utente che crea i canali deve avere almeno una connessione Dataverse oltre a specifiche connessioni di posta elettronica o di archiviazione file. Il creatore del nuovo canale deve essere il proprietario della connessione.
