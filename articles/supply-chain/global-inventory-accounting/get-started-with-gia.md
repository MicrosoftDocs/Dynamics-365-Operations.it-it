---
title: Introduzione alla Contabilità inventario globale
description: Questo argomento descrive come iniziare a usare la Contabilità inventario globale.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 17d4816fc5fcad0b0665640a8347b1f4ea032dd7
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679445"
---
# <a name="get-started-with-global-inventory-accounting"></a>Introduzione alla Contabilità inventario globale

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Contabilità inventario globale ti consente di eseguire più contabilità di inventario nei libri contabili di Contabilità inventario globale impostati. È necessario associare ogni libro contabile di Contabilità inventario globale a una *convenzione*. Una convenzione è la raccolta dei seguenti tipi di principi contabili:

- Oggetto di costo
- Base di misura di input
- Presupposto per flussi di costo
- Elemento di costo

> [!NOTE]
> Anche dopo aver attivato Contabilità inventario globale, è ancora possibile eseguire la contabilità di inventario in Microsoft Dynamics 365 Supply Chain Management, come di consueto.

Contabilità inventario globale è un componente aggiuntivo. Per rendere disponibili le funzionalità, è necessario installarlo da Microsoft Dynamics Lifecycle Services (LCS). È possibile scegliere di valutarlo in un ambiente di test prima di attivarlo per gli ambienti di produzione.

Contabilità inventario globale attualmente non supporta tutte le funzionalità di gestione dei costi integrate in Supply Chain Management. Pertanto, è importante valutare se il set di funzionalità attualmente disponibile soddisfa i requisiti.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>Come ottenere l'anteprima pubblica di Contabilità inventario globale

> [!IMPORTANT]
> Per utilizzare Contabilità inventario globale, è necessario disporre di un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox). Inoltre, è necessario eseguire Supply Chain Management versione 10.0.19 o successiva.

Per iscriverti all'anteprima pubblica di Contabilità inventario globale, invia il tuo ID ambiente LCS via e-mail al [Team di Contabilità inventario globale](mailto:GlobalInvAccount@microsoft.com). Dopo che sei stato approvato per il programma, il team ti invierà un'e-mail di follow-up che contiene una chiave beta di Contabilità inventario globale e gli endpoint del servizio. Dopo aver ricevuto la chiave beta, puoi [installare il componente aggiuntivo](#install).

## <a name="licensing"></a>Licenze

Contabilità inventario globale è concesso in licenza insieme alle funzionalità standard della contabilità di magazzino disponibili per Supply Chain Management. Non è necessario acquistare una licenza aggiuntiva per utilizzare Contabilità inventario globale.

## <a name="prerequisites"></a>Prerequisiti

### <a name="set-up-microsoft-power-platform-integration"></a>Impostare l'integrazione con Microsoft Power Platform

Prima di poter abilitare la funzionalità del componente aggiuntivo, è necessario eseguire l'integrazione con Microsoft Power Platform seguendo questi passaggi.

1. Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.
1. Andare a **Dettagli completi**.
1. Nella sezione **Integrazione di Power Platform**, seleziona **Configurazione**.
1. Nella finestra di dialogo **Configurazione ambiente Power Platform** seleziona la casella di controllo, quindi seleziona **Impostazioni**. In genere, la configurazione richiede tra 60 e 90 minuti.
1. Quando la configurazione dell'ambiente Microsoft Power Platform è completata viene visualizzata la pagina con il nome del tuo ambiente. Inoltre, la sezione **Integrazione di Power Platform** mostra il messaggio "Configurazione dell'ambiente Power Platform completata." Contabilità inventario globale non richiede un'applicazione a doppia scrittura.

Per ulteriori informazioni, vedi [Abilitare dopo la distribuzione dell'ambiente](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

### <a name="set-up-dataverse"></a>Configura Dataverse

Prima di configurare Dataverse, aggiungi i principi del servizio Contabilità inventario globale al tuo tenant seguendo questi passaggi.

1. Installare il modulo Azure AD per Windows PowerShell v2 come descritto in [Installare Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).
1. Eseguire il comando PowerShell seguente.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

Quindi, crea gli utenti dell'applicazione per Contabilità inventario globale in Dataverse seguendo questi passaggi.

1. Aprire l'URL del proprio ambiente Dataverse.
1. Selezionare **Impostazioni avanzate \> Sistema \> Sicurezza \> Utenti** e creare un utente applicazione. Utilizza il campo **Visualizza** per cambiare la visualizzazione della pagina in *Utenti applicazione*.
1. Selezionare **Nuovo**.
1. Impostare il campo **ID applicazione** su *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. Selezionare **Assegna ruolo** e quindi selezionare *Amministratore di sistema*. Se è presente un ruolo denominato *Utente Common Data Service*, selezionarlo.
1. Ripeti i passaggi precedenti, ma imposta il campo **ID applicazione** su *5f58fc56-0202-49a8-ac9e-0946b049718b*.

Per ulteriori informazioni, vedere [Creare un utente applicazione](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

Se la lingua predefinita dell'installazione di Dataverse non è inglese, segui questi passaggi.

1. Vai a **Impostazioni avanzate \> Amministrazione \> Lingue**.
1. Seleziona *Inglese* (*LanguageCode=1033*) e seleziona **Applica**.

## <a name="install-the-add-in"></a><a name="install"></a>Installare il componente aggiuntivo

Segui questi passaggi per installare il componente aggiuntivo in modo da poter utilizzare Contabilità inventario globale.

1. [Iscriviti](#sign-up) per l'anteprima pubblica di Contabilità inventario globale.
1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index).
1. Accedere a **Gestione funzionalità di anteprima**.
1. Selezionare il segno più (**+**).
1. Nel campo **Codice**, inserisci la chiave beta del componente aggiuntivo Contabilità inventario globale. Dovresti aver ricevuto la tua chiave beta via e-mail quando ti sei registrato.
1. Selezionare **Sblocca**.
1. Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.
1. Andare a **Dettagli completi**.
1. Vai a **Integrazione di Power Platform** e seleziona **Impostazioni**.
1. Nella finestra di dialogo **Configurazione ambiente Power Platform** seleziona la casella di controllo, quindi seleziona **Impostazioni**. In genere, la configurazione richiede tra 60 e 90 minuti.
1. Dopo l'installazione dell'ambiente Microsoft Power Platform, nella scheda dettaglio **Componenti aggiuntivi ambiente** seleziona **Installa un nuovo componente aggiuntivo**.
1. Seleziona **Contabilità inventario globale**.
1. Seguire la guida all'installazione e accettare le condizioni.
1. Seleziona **Installa**.
1. Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** viene indicato che Contabilità inventario globale è stato installato. Dopo alcuni minuti, lo stato cambia da *Installazione in corso* in *Installato*. Potrebbe essere necessario aggiornare la pagina per vedere questa modifica. A quel punto, Contabilità inventario globale è pronto per l'uso.

## <a name="set-up-the-integration"></a>Impostare l'integrazione

Segui questi passaggi per impostare l'integrazione tra Contabilità inventario globale e Supply Chain Management.

1. Accedere a Supply Chain Management.
1. Vai a **Amministrazione sistema \> Gestione funzionalità**.
1. Selezionare **Controlla aggiornamenti**.
1. Nella scheda **Tutti** cerca la funzione denominata *(Anteprima) Contabilità inventario globale*.
1. Selezionare **Abilita ora**.
1. Vai a **Contabilità inventario globale \> Impostazioni \> Parametri contabilità inventario globale \> Parametri integrazione**.
1. Nei campi **Endpoint servizio dati** e **Endpoint contabilità inventario globale** inserisci gli URL dall'e-mail che il team di contabilità inventario globale ha inviato quando ti sei registrato per l'anteprima.

Contabilità inventario globale è ora pronto per l'uso.
