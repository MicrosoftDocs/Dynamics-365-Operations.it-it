---
title: Ricerca estesa di formati di report elettronici (ER)
description: Questo articolo descrive come impostare un riferimento al formato ER nella ricerca di formati ER quando il formato richiesto si trova nel repository globale.
author: kfend
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace
ms.openlocfilehash: 624f5c347c27cc2075f9602087c1c49e84340565
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274921"
---
# <a name="allow-users-to-set-up-an-er-format-reference-inquiring-a-format-from-the-global-repository"></a>Consentire agli utenti di impostare un riferimento al formato ER richiedendo un formato presente nel repository globale

[!include [banner](../includes/banner.md)]

È possibile utilizzare il framework di [report elettronici (ER)](general-electronic-reporting.md) per configurare formati per documenti in uscita in base ai requisiti legali dei vari paesi/aree geografiche. È inoltre possibile utilizzare il framework ER per configurare formati  per l'analisi di documenti in entrata e utilizzare le informazioni in tali documenti per aggiungere o aggiornare i dati dell'applicazione. Ognuno di questi formati può essere utilizzato nella propria istanza Dynamics 365 Finance per la gestione di documenti aziendali in entrata o in uscita come parte di un determinato processo aziendale.

Di solito, è necessario specificare quale formato ER deve essere utilizzato in un determinato processo aziendale. Per fare ciò, selezionare un singolo formato ER in un campo di ricerca configurato come parte dei parametri specifici del processo aziendale. Questi campi di ricerca vengono generalmente implementati utilizzando l'API appropriata del framework ER. Per ulteriori informazioni, vedere [API framework ER - codice per visualizzare una ricerca di mapping di formato](er-apis-app73.md#code-to-display-a-format-mapping-lookup).

Ad esempio, quando si configurano [parametri per il commercio estero](../../../finance/localizations/emea-intrastat.md#set-up-foreign-trade-parameters), è necessario impostare i riferimenti a singoli formati ER che verranno utilizzati per generare la dichiarazione Intrastat e il report di controllo della dichiarazione Intrastat. Le schermate seguenti mostrano l'aspetto del campo di ricerca di formati ER nella pagina **Parametri per il commercio estero**.

Se l'attuale istanza di Finance non contiene formati ER relativi a processi aziendali Intrastat, questo campo di ricerca sarà vuoto.

[![Pagina dei parametri del commercio estero, campo mapping formato report vuoto.](./media/ER-ExtLookup-Lookup1.gif)](./media/ER-ExtLookup-Lookup1.gif)

Se l'attuale istanza di Finance contiene formati ER relativi a processi aziendali Intrastat, questo campo di ricerca include i formati ER.

[![Pagina dei parametri del commercio estero, campo mapping formato report con opzioni.](./media/ER-ExtLookup-Lookup2.png)](./media/ER-ExtLookup-Lookup2.png)

Questa ricerca offre solo i formati ER che sono già stati importati nell'istanza corrente di Finance. Per [importare](./tasks/er-import-configuration-lifecycle-services.md) soluzioni ER nell'istanza corrente di Finance, è necessario disporre delle autorizzazioni per eseguire la funzione appropriata del framework ER che supporta il [ciclo di vita](general-electronic-reporting-manage-configuration-lifecycle.md) delle soluzioni ER che contengono formati ER.

A partire dalla versione 10.0.9 di Finance (versione di aprile 2020), l'interfaccia utente della ricerca di formati ER implementata mediante l'API del framework ER è stata estesa. È ancora possibile selezionare i formati ER esistenti, che si trovano nella scheda dettaglio **Seleziona la configurazione del formato**. Inoltre, la ricerca estesa offre la nuova opzione per la ricerca di formati ER specifici nel repository globale (GR). Tutti i formati ER del repository globale sono disponibili nella scheda dettaglio **Importa da repository globale**.

[![Pagina dei parametri del commercio estero, scheda dettaglio Importa da repository globale.](./media/ER-ExtLookup-Lookup3.png)](./media/ER-ExtLookup-Lookup3.png)

Analogamente alla scheda **Seleziona la configurazione del formato**, la scheda dettaglio **Importa da repository globale** mostra solo i formati ER applicabili al processo aziendale per il quale un formato ER è selezionato in questo campo di ricerca. In questo esempio, la generazione della dichiarazione Intrastat. Il formato ER è applicabile per l'azienda a cui l'utente è attualmente connesso, a seconda del contesto del paese dell'azienda.

Quando si seleziona un formato ER nella scheda dettaglio **Importa da repository globale**, la [configurazione](general-electronic-reporting.md#Configuration) di formato ER selezionata viene importata dl repository globale nell'istanza corrente di Finance.

[![Pagina dei parametri del commercio estero, nota sull'operazione di elaborazione.](./media/ER-ExtLookup-FormatImport.png)](./media/ER-ExtLookup-FormatImport.png)

Quindi, se l'importazione viene completata correttamente, il riferimento al formato ER importato viene archiviato in questo campo di ricerca. Quando si accede al repository globale per la prima volta, è necessario seguire il collegamento fornito per iscriversi al servizio [Regulatory Configuration Service](https://aka.ms/rcs) (RCS) utilizzato per gestire l'accesso al repository globale.

[![Pagina dei parametri del commercio estero, collegamento per iscriversi a RCS.](./media/ER-ExtLookup-RepoSignUp.png)](./media/ER-ExtLookup-RepoSignUp.png)

Per impostazione predefinita, la scheda dettaglio **Importa da repository globale** visualizza l'elenco di formati ER presenti nell'archivio temporaneo che viene creato automaticamente in base al contenuto del repository globale per miglioramenti delle prestazioni. Ciò avviene quando la scheda dettaglio **Importa da repository globale** viene aperta la prima volta, il che può richiedere alcuni secondi.

Se il formato ER richiesto non è visualizzato nella scheda dettaglio **Importa da repository globale**, ma si è certi della sua presenza nel repository globale, selezionare l'opzione **Sincronizza**. Questa opzione aggiornerà l'archivio temporaneo e lo sincronizzerà con il contenuto corrente del repository globale.

## <a name="feature-activation"></a>Attivazione della funzionalità

La disponibilità di questa funzionalità è controllata dalla funzionalità **Ricerca estesa di configurazioni di formati ER che consente di consultare il repository globale** in **Gestione funzionalità**. Questo funzionalità è abilitata per impostazione predefinita.

[![Pagina Gestione funzionalità.](./media/ER-ExtLookup-FeatureMngt.png)](./media/ER-ExtLookup-FeatureMngt.png)

## <a name="security-considerations"></a>Considerazioni sulla sicurezza

Il privilegio **Gestisci repository di configurazioni** (**ERMaintainSolutionRepositories**) controlla l'accesso al repository globale per un utente che avvia la ricerca di formati ER con la scheda dettaglio **Importa da repository globale** abilitata. Per consentire agli utenti di accedere al contenuto del repository globale dalle ricerche di formati ER, è necessario modificare le impostazioni di sicurezza concedendo il privilegio **ERMaintainSolutionRepositories** agli utenti direttamente oppure utilizzando ruoli e compiti già assegnati.

La schermata seguente mostra come questo privilegio può essere concesso agli utenti a cui è assegnato il ruolo **Contabile**. Questo ruolo consente agli utenti di configurare i parametri per il commercio estero e impostare i riferimenti ai formati ER nei campi **Mapping formato file** e **Mapping formato report** nella pagina **Parametri per il commercio estero**.

[![Pagina Configurazione sicurezza.](./media/ER-ExtLookup-SecuritySetting.png)](./media/ER-ExtLookup-SecuritySetting.png)

## <a name="limitations"></a>Limiti

L'accesso al repository globale nella ricerca di formati ER è attualmente supportato solo per la selezione di formati ER utilizzati per generare documenti in uscita.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="why-cant-i-access-the-global-repository-from-the-er-format-lookup"></a>Perché non è possibile accedere al repository globale dalla ricerca di formati ER?

Se è stata abilitata la funzionalità **Ricerca estesa di configurazioni di formati ER che consente di consultare il repository globale** nella pagina **Gestione funzionalità**, ma gli utenti non possono vedere i formati ER nella scheda dettaglio **Importa da repository globale** e l'opzione **Sincronizza** è visibile ma disabilitata, assicurarsi che il privilegio **Gestisci repository di configurazioni** (**ERMaintainSolutionRepositories**) sia stato concesso all'utente. Per ricevere questo privilegio, contattare l'amministratore di sistema.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [API del framework di report elettronici (ER)](er-apis-app73.md)
- [Gestire il ciclo di vita delle configurazioni per la creazione di report elettronici](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
