---
title: Impostazione di Operational Insights
description: Questo articolo descrive come configurare e usare la funzionalità Operational Insights in Microsoft Dynamics 365 Commerce.
author: ashishMSFT
ms.date: 12/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: ca0d31e403275d6131fa6d53f0a7b46a7ddb651d
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832127"
---
# <a name="set-up-operational-insights"></a>Impostazione di Operational Insights

[!include [banner](../includes/banner.md)]

Questo articolo descrive come configurare e usare la funzionalità Operational Insights in Microsoft Dynamics 365 Commerce.

Operational Insights è una funzione di Dynamics 365 Commerce progettata per offrire ai clienti una migliore visibilità sull'integrità del loro servizio e sulla funzionalità aziendale inviando dati di telemetria direttamente a un account Application Insights di proprietà del cliente.

Abilitando Operational Insights per i tuoi ambienti in Commerce headquarters, puoi raccogliere un elenco curato di eventi sia da Commerce Scale Unit (CSU) che dai tuoi dispositivi point-of-sale (POS). Questi eventi possono aiutarti a capire meglio le prestazioni dei tuoi sistemi e ti consentono di monitorare le principali metriche tecniche e aziendali.

Anche se non vuoi raccogliere questi dati di telemetria, puoi trarre vantaggio abilitando o disabilitando rapidamente la raccolta per ambienti specifici. In questo modo, la telemetria può aiutarti a risolvere i problemi o eseguire il debug durante lo sviluppo o in produzione.

## <a name="access-logs-in-application-insights"></a>Accedere ai log in Application Insights

Per accedere ai registri eventi di diagnostica per i componenti Commerce CSU e POS tramite Application Insights, completa le procedure in questa sezione.

### <a name="minimum-version-requirements-for-csu"></a>Requisiti di versione minima per CSU

CSU ha i seguenti requisiti di versione minima:

- 10.0.23 (versione Retail Server 9.33.22062.15 e successive)
- 10.0.24 (versione Retail Server 9.34.22062.14 e successive)
- 10.0.25 (versione Retail Server 9.35.22062.13 e successive)
- 10.0.26 e successive (tutte le versioni)

### <a name="enable-diagnostic-events-in-application-insights"></a>Abilitare gli eventi diagnostici in Application Insights

> [!IMPORTANT]
> Se in precedenza hai utilizzato una versione di anteprima di Operational Insights, devi utilizzare la procedura seguente per abilitare Operational Insights. In questo modo, ti assicuri che l'accesso affidabile e sicuro agli eventi possa continuare.

Per abilitare gli eventi diagnostici del componente Commerce, devi disporre di un account Application Insights. Puoi usare un account esistente o [creare un nuovo account](/azure/azure-monitor/app/create-workspace-resource#create-workspace-based-resource). Per motivi di riservatezza dei dati, ti consigliamo di utilizzare account Application Insights separati per ambienti di produzione, sandbox e sviluppo. Dopo aver creato un account, devi abilitare la funzione **Operational Insights** in headquarters.

Per abilitare gli eventi diagnostici in Application Insights, procedi nel seguente modo.

1. In headquarters, apri l'area di lavoro **Gestione funzionalità** e abilita la funzionalità **Operational Insights**.
1. Vai a **Amministrazione sistema \> Impostazioni \> Operational Insights**.
1. Nella scheda **Configura** , imposta l'opzione **Eventi del canale Commerce** su **Sì**.
1. Nella scheda **Ambienti**, inserisci i valori **ID ambiente LCS** e **Modalità ambiente** per ogni ambiente in cui prevedi di utilizzare Application Insights. Puoi trovare l'ID ambiente di ciascun ambiente nella pagina **Dettagli ambiente** per quell'ambiente in Microsoft Dynamics Lifecycle Services. Questo passaggio è necessario per evitare che gli eventi di diagnostica vengano inviati inavvertitamente a un ambiente non corretto quando vengono eseguite operazioni di copia del database.
1. Nella scheda **Registro di Application Insights** specifica il valore Application Insights **Chiave di strumentazione** e il valore corrispondente **Modalità ambiente** degli ambienti in cui prevedi di utilizzare ogni account Application Insights.
1. Dopo aver completato la configurazione precedente, è necessario eseguire il processo **CDX Job 1110**. È possibile attendere che questo processo venga eseguito secondo la propria pianificazione oppure puoi eseguirlo manualmente.
1. In Lifecycle Services, vai a **Dettagli ambiente \> Commercio \> Gestisci**, seleziona un'istanza CSU, quindi seleziona **Riavvia**. Ripetere questo passaggio per ogni CSU.
1. Ripeti i passaggi precedenti per ogni ambiente in cui intendi utilizzare Application Insights.

> [!NOTE]
> - Gli eventi di telemetria in Operational Insights sono soggetti a modifiche. Ti consigliamo di utilizzare gli eventi di Operational Insights per eseguire autonomamente analisi preliminari e risoluzione dei problemi, ma non per definire dashboard o avvisi. Se utilizzi gli eventi per scopi che vanno oltre la risoluzione dei problemi self-service, ti consigliamo di convalidare e aggiornare le tue query dopo ogni rilascio di CSU/POS.
> - A partire dalla versione 10.0.29 di Commerce, le procedure in questa sezione consentono anche lo streaming di eventi POS di Operational Insights all'account Application Insights. Per ulteriori informazioni, consulta [Operational Insights per POS – Eventi e query](https://download.microsoft.com/download/9/2/b/92be35b0-0e24-4a4d-940d-6f4db29791c0/Operational-Insights-Commerce-POS-events-queries.pdf).

#### <a name="use-the-dllhostexeconfig-file-to-control-pos-operational-insights-events"></a>Utilizzare il file DLLHost.exe.config per controllare gli eventi di Operational Insights POS

Per utilizzare il file DLLHost.exe.config per controllare gli eventi di Operational Insights POS, segui questa procedura.

1. In un editor di testo, apri il file **DLLHost.exe.config** in **C:\\Programmi (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\ClientBroker**.
1. Nella sezione **diagnosticsSection**, rimuovi l'elemento XML sink con il nome della classe **Microsoft.Dynamics.Retail.Diagnostics.OperationalInsights.OperationalInsightsLogger**.
1. Salva il file.

### <a name="disable-diagnostic-events-in-application-insights"></a>Disabilitare gli eventi diagnostici in Application Insights

> [!IMPORTANT]
> Se desideri disabilitare gli eventi di diagnostica e non inviarli più ad Application Insights, devi completare la seguente procedura. Non è possibile solo disabilitare questa funzione in Gestione funzionalità.

Per disabilitare gli eventi diagnostici in Application Insights, procedi nel seguente modo.

1. In headquarters, vai a **Amministrazione sistema \> Operational Insights**.
1. Nella scheda **Configura** , imposta l'opzione **Eventi del canale Commerce** su **No**.
1. Dopo aver completato la configurazione precedente, è necessario eseguire il processo **CDX Job 1110**. È possibile attendere che questo processo venga eseguito secondo la propria pianificazione oppure puoi eseguirlo manualmente.
1. In Lifecycle Services, vai a **Dettagli ambiente \> Commercio \> Gestisci**, seleziona un'istanza CSU, quindi seleziona **Riavvia**. Ripetere questo passaggio per ogni CSU.
1. Ripeti i passaggi precedenti per ogni ambiente in cui intendi disattivare Application Insights.

Per disabilitare gli eventi diagnostici per un singolo ambiente, elimina la chiave di strumentazione nella scheda **Registro di Application Insights** della pagina **Operational Insights**. Quindi completa i passaggi 3 e 4 della procedura precedente.

> [!NOTE]
> A partire dalla versione 10.0.29 di Commerce, i passaggi in questa sezione consentono anche di disabilitare lo streaming di eventi POS di Operational Insights all'account Application Insights. 
