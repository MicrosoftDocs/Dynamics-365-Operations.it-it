---
title: Configurare una connessione SharePoint
description: Questo articolo spiega come configurare una connessione in modo che la fatturazione elettronica possa accedere a un sito di Microsoft SharePoint.
author: gionoder
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: a2762178686d1f29c457b6de2a9b052fd048484b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283989"
---
# <a name="configure-a-sharepoint-connection"></a>Configurare una connessione SharePoint

[!include [banner](../includes/banner.md)]

Il servizio di fatturazione elettronica può leggere file dalle cartelle di Microsoft SharePoint e caricare file in SharePoint. Per fare in modo che la fatturazione elettronica possa accedere a un sito SharePoint specifico, è necessario fornire le credenziali del sito al servizio di fatturazione elettronica. Inoltre, per fare in modo che le credenziali siano archiviate in modo sicuro, non fornirle direttamente. Al contrario, archiviale in un Azure Key Vault e fornisci un segreto di Azure Key Vault.

## <a name="grant-access-to-a-sharepoint-folder"></a>Concedere l'accesso ad una cartella di SharePoint

1. Crea una registrazione dell'app nel tenant in cui è installato Regulatory Configuration Service (RCS).

    1. Accedere al [portale Azure](https://portal.azure.com/).
    2. Vai a **Registrazioni app**.
    3. Seleziona **Nuova registrazione**.
    4. Immetti un nome, ad esempio **App SharePoint per la fatturazione elettronica** e completare la registrazione
    5. Seleziona la nuova registrazione dell'app.
    6. Nella scheda **Autenticazione**, abilita l'opzione **Consenti flussi client pubblici**.
    4. Nella scheda **Certificati e segreti**, seleziona **Nuovo segreto client** per creare un segreto client.
    5. Copia il valore del segreto che è stato creato.

    Segui queste linee guida:

    - Non utilizzare la stessa registrazione dell'app per servizi diversi.
    - Segui le [raccomandazioni sui criteri delle password](/microsoft-365/admin/misc/password-policy-recommendations?view=o365-worldwide).
    - Configura la rotazione delle password. Durante la rotazione, crea un nuovo segreto client per la registrazione dell'app, aggiorna il Key Vault e quindi elimina il vecchio segreto.

2. Salva i valori **Segreto registrazione app** e **ID applicazione (client)** come due nuovi segreti nel Key Vault durante la configurazione dell'ambiente di fatturazione elettronica.
3. Aggiungi i segreti creati sui parametri del Key Vault nella configurazione dell'ambiente di fatturazione elettronica in RCS.
4. Nel portale di Azure, concedi l'accesso a SharePoint. Questo passaggio deve essere completato dall'amministratore del tenant.

    1. Seleziona la registrazione dell'app creata.
    2. Nella scheda **Autorizzazioni API**, seleziona **Aggiungi un'autorizzazione**.
    3. Seleziona **Microsoft Graph (autorizzazioni dell'applicazione)** \> **Sites.Selected**.
    4. Seleziona **Concedi il consenso dell'amministratore per \<user&nbsp;name\>**.
    5. Rivedi il campo **Stato** per assicurarti che le autorizzazioni siano concesse.

        ![Autorizzazioni concesse nella scheda Autorizzazioni API.](media/configured-permissions.jpg)

    6. Apri [Graph explorer - Microsoft Graph](https://developer.microsoft.com/graph/graph-explorer) e accedi.
    7. Nel riquadro di sinistra, nella scheda **Query di esempio**, in **Siti di SharePoint**, seleziona **Recupera sito di SharePoint in base al percorso relativo del sito**.
    8. Riempi i parametri **\{host-name\}** e **\{server-relative-path\}**. Ad esempio, inserisci `<domain>.sharepoint.com` per **\{host-name\}** e `sites/<siteName>` per **\{server-relative-path\}**.

        > [!NOTE]
        > Per il sito Web predefinito, lascia il parametro **\{server-relative-path\}** vuoto.

    9. Seleziona **Esegui query** e salva il risultato.
    10. Configura la seguente query.

        `POST https://graph.microsoft.com/v1.0/sites/{site-id}/permissions`

        In questa query, **\{site-id\}** è il valore del nodo **ID** dalla risposta alla query precedente.

        Ecco il corpo della richiesta.

        ```json
        {
            "roles": [
                "read",
                "write"
            ],
            "grantedToIdentities": [
                {
                    "application": {
                        "id": "{app-id}",
                        "displayName": "{app-name}"
                    }
                }
            ]
        }
        ```

        In questo corpo di richiesta, **\{app-id\}** è il valore **ID applicazione (cliente)** e **\{app-name\}** è il valore **Nome applicazione**.

        ![Query POST.](media/app-id-query.jpg)

    11. Nella scheda **Modifica autorizzazioni**, seleziona **Apri il pannello delle autorizzazioni**, quindi seleziona **Siti** \> **Sites.FullControl.All** \> **Consenso**.
    12. Seleziona **Esegui query**.

Il servizio di fatturazione elettronica ha ora accesso al tuo sito di SharePoint.
