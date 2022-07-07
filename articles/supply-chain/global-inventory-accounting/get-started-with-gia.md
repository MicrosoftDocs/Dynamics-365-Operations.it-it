---
title: Introduzione alla Contabilità inventario globale
description: Questo articolo descrive come iniziare a usare la Contabilità inventario globale.
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
ms.openlocfilehash: cbe6bff6fab96900b8bd4e112a8858363fff86d1
ms.sourcegitcommit: 9870b773a2ea8f5675651199fdbc63ca7a1b4453
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013557"
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

## <a name="how-to-get-the-global-inventory-accounting-add-in"></a><a name="sign-up"></a>Come ottenere il componente aggiuntivo Contabilità inventario globale

> [!IMPORTANT]
> Per utilizzare Contabilità inventario globale, è necessario disporre di un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox). Inoltre, è necessario eseguire Supply Chain Management versione 10.0.19 o successiva.

### <a name="supply-chain-management-version-10019-to-10026"></a>Supply Chain Management versione da 10.0.19 a 10.0.26

Per installare Contabilità inventario globale per Supply Chain Management dalla versione 10.0.19 alla 10.0.26, inizia [installando il componente aggiuntivo](#install). Quindi invia l'ID dell'ambiente LCS e il nome dell'azienda tramite e-mail al [Team di contabilità inventario globale](mailto:GlobalInvAccount@microsoft.com). Il team ti invierà un'e-mail di completamento che contiene gli endpoint del servizio di contabilità inventario globale.

### <a name="supply-chain-management-version-10027-and-later"></a>Supply Chain Management versione 10.0.27 e successive

Per installare Contabilità inventario globale per Supply Chain Management dalla versione 10.0.27 e successive, [installa il componente aggiuntivo](#install). Per queste versioni di Supply Chain Management, gli endpoint del servizio Contabilità inventario globale verranno impostati automaticamente, quindi non è necessario trovarli manualmente. In caso di problemi durante la configurazione del componente aggiuntivo, contatta il [Team di contabilità inventario globale](mailto:GlobalInvAccount@microsoft.com).

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

## <a name="install-the-add-in"></a><a name="install"></a>Installare il componente aggiuntivo

Segui questi passaggi per installare il componente aggiuntivo in modo da poter utilizzare Contabilità inventario globale.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index).
1. Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.
1. Andare a **Dettagli completi**.
1. Vai a **Integrazione di Power Platform** e seleziona **Impostazioni**.
1. Nella finestra di dialogo **Configurazione ambiente Power Platform** seleziona la casella di controllo, quindi seleziona **Impostazioni**. In genere, la configurazione richiede tra 60 e 90 minuti.
1. Dopo l'installazione dell'ambiente Microsoft Power Platform, accedi all'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com) e quindi installa il componente aggiuntivo Contabilità inventario globale procedendo come segue:
   1. Seleziona l'ambiente in cui vuoi installare il componente aggiuntivo.
   1. Seleziona **App Dynamics 365**.
   1. Seleziona **Installa app**.
   1. Seleziona **Contabilità inventario globale Dynamics 365**.
   1. Seleziona **Avanti** per installare.
1. Torna all'ambiente LCS. Nella Scheda dettaglio **Componenti aggiuntivi per l'ambiente**, seleziona **Installa un nuovo componente aggiuntivo**.
1. Seleziona **Contabilità inventario globale**.
1. Seguire la guida all'installazione e accettare le condizioni.
1. Seleziona **Installa**.
1. Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** viene indicato che Contabilità inventario globale è stato installato. Dopo alcuni minuti, lo stato cambia da *Installazione in corso* in *Installato*. Potrebbe essere necessario aggiornare la pagina per vedere questa modifica. A quel punto, Contabilità inventario globale è pronto per l'uso.

Se la lingua predefinita dell'installazione di Dataverse non è inglese, segui questi passaggi:
1. Vai a **Impostazioni avanzate \> Amministrazione \> Lingue**.
1. Seleziona *Inglese* (*LanguageCode=1033*) e seleziona **Applica**.

## <a name="set-up-the-integration"></a>Impostare l'integrazione

Segui questi passaggi per impostare l'integrazione tra Contabilità inventario globale e Supply Chain Management.

1. Accedere a Supply Chain Management.
1. Vai a **Amministrazione sistema \> Gestione funzionalità**.
1. Selezionare **Controlla aggiornamenti**.
1. Nella scheda **Tutti** cerca la funzione denominata *(Anteprima) Contabilità inventario globale*.
1. Selezionare **Abilita ora**.
1. Vai a **Contabilità inventario globale \> Impostazioni \> Parametri contabilità inventario globale \> Parametri integrazione**.
1. A seconda della versione di Supply Chain Management in esecuzione, esegui una delle seguenti operazioni:
    - **Supply Chain Management dalla versione 10.0.19 a 10.0.26**: Nei campi **Endpoint del servizio dati** ed **Endpoint di contabilità inventario globale**, inserisci gli URL che ti sono stati inviati via e-mail dal team Contabilità inventario globale (vedi anche [Come ottenere il componente aggiuntivo Contabilità inventario globale](#sign-up)).
    - **Supply Chain Management versione 10.0.27 e successive**: non è necessario inserire gli endpoint, quindi puoi saltare questo passaggio.

Contabilità inventario globale è ora pronto per l'uso.
