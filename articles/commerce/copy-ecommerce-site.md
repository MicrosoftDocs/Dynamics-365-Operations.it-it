---
title: Copiare un sito di e-commerce
description: Questo articolo descrive come copiare un sito di e-commerce esistente all'interno o tra ambienti di e-commerce nel generatore di siti di Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 9b74e0d48be29272b893c855c229e4003f0c161e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276294"
---
# <a name="copy-an-e-commerce-site"></a>Copiare un sito di e-commerce

[!include [banner](../includes/banner.md)]

Questo articolo descrive come copiare un sito di e-commerce esistente all'interno o tra ambienti di e-commerce nel generatore di siti di Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce supporta la copia o la clonazione di siti come operazione self-service nel generatore di siti di Commerce. I siti possono essere copiati all'interno di un unico ambiente di e-commerce o tra due ambienti di e-commerce. L'utente che avvia l'operazione di copia del sito deve essere un amministratore del tenant sia nell'ambiente di e-commerce di origine che in quello di destinazione.

L'operazione di copia del sito copia tutto il contenuto di e-commerce del sito di origine. Questo contenuto include pagine, frammenti, modelli, URL e risorse. Prima di poter utilizzare un nuovo sito, è necessario inizializzarlo tramite il processo FRE (first run experience). I canali possono essere mappati e gestiti nel generatori di siti, all'indirizzo **Impostazioni sito \> Canali**.

La durata dell'operazione di copia del sito dipende principalmente dal numero di risorse nel sito di origine. Per i siti eccezionalmente grandi, si consiglia di prendere in considerazione l'utilizzo dell'operazione di copia dell'ambiente. (Questa operazione è anche nota come operazione di portabilità dei dati).

> [!NOTE]
> - Il sito di origine sarà di sola lettura per la durata dell'operazione di copia del sito.
> - Vengono copiate solo le versioni pubblicate dei documenti. Se non sono state pubblicate versioni, vengono copiate solo le ultime versioni.
> - La cronologia delle versioni per il contenuto non sarà disponibile nel sito di destinazione.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Copiare un sito all'interno di un ambiente di e-commerce

Per copiare un sito all'interno di un ambiente di e-commerce, attenersi alla seguente procedura.

1. Accedi al generatore di siti per l'ambiente in cui vuoi eseguire l'operazione di copia.
1. Apri la visualizzazione elenco dei siti selezionando **Cambia sito** nell'angolo in alto a destra, quindi selezionando **Gestisci siti**.
1. Trova il sito che desideri copiare o clonare e sceglilo selezionando la casella di controllo accanto al nome del sito.
1. Nella barra dei comandi, seleziona **Copia sito**.
1. Nel menu a comparsa **Copia sito**, nel campo **Nome nome sito** immetti un nome per il nuovo sito. Il nuovo nome del sito deve essere univoco nell'ambiente di e-commerce. I campi **Tenant di origine** e **Sito di origine** vengono impostati automaticamente sulle informazioni per il tenant corrente e il sito selezionato.
1. Seleziona **Crea copia**.

Dopo che le informazioni sono state convalidate, una notifica indica che è stato creato un nuovo processo di copia del sito. È possibile monitorare lo stato di avanzamento del processo nel [riquadro destro della pagina **Processi tenant**](#monitor-the-site-copy-operation). Quando l'operazione di copia è stata completata, il nuovo sito viene visualizzato nell'elenco dei siti nella visualizzazione elenco siti.

La figura seguente mostra un esempio del menu a comparsa **Copia sito** nel generatore di siti.

![Menu a comparsa Copia sito nel generatore di siti.](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Copiare un sito tra due ambienti di e-commerce

Per copiare un sito tra due ambienti di e-commerce, attenersi alla seguente procedura.

1. Accedi al generatore di siti per l'ambiente e-commerce di destinazione.
1. Nella barra dei comandi, seleziona **Copia sito**.
1. Nel menu a comparsa **Copia sito**, nel campo **Nome nome sito** immetti un nome per il nuovo sito. Il nuovo nome del sito deve essere univoco nell'ambiente di e-commerce.
1. Nel campo **Tenant di origine**, seleziona il nome del tenant di origine.
1. Nel campo **Sito di origine** seleziona il sito di origine.
1. Seleziona **Crea copia**.

> [!NOTE]
> Le autorizzazioni di amministratore del tenant sono necessarie sia per l'ambiente di e-commerce di origine che per quello di destinazione.

Dopo che le informazioni sono state convalidate, una notifica indica che è stato creato un nuovo processo di copia del sito. È possibile monitorare lo stato di avanzamento del processo nel [riquadro destro della pagina **Processi tenant**](#monitor-the-site-copy-operation). Quando l'operazione di copia è stata completata, il nuovo sito viene visualizzato nell'elenco dei siti nella visualizzazione elenco siti.

## <a name="map-channels-during-the-site-copy-operation-optional"></a>Mappare i canali durante l'operazione di copia del sito (opzionale)

I canali e le impostazioni locali di origine possono essere mappati ai canali e alle impostazioni locali di destinazione come parte dell'operazione di copia del sito. Se il mapping dei canali viene eseguito come parte dell'operazione di copia del sito, non è necessario inizializzare il sito utilizzando il processo FRE e configurare i canali nelle impostazioni del sito. 

Per mappare tutti i canali e le impostazioni locali "così come sono" (1 a 1) in Creazione di siti Web, segui questi passaggi.

1. Apri la visualizzazione elenco dei siti selezionando **Cambia sito** nell'angolo in alto a destra, quindi selezionando **Gestisci siti**.
1. Trova il sito che desideri copiare o clonare e sceglilo selezionando la casella di controllo accanto al nome del sito.
1. Nella barra dei comandi, seleziona **Copia sito**.
1. Nel menu a comparsa **Copia sito**, immetti i valori per **Nuovo nome sito**, **Tenant di origine**, e **Sito di origine** (se non già presente).
1. Seleziona **Aggiungi mapping canale**.
1. Nel menu a comparsa **Configura canali e impostazioni locali del sito** seleziona **Canale di origine**, quindi seleziona il canale di origine.  
1. Seleziona **Canale di destinazione** e quindi seleziona lo stesso canale di origine. 
1. Seleziona **Aggiungi impostazioni locali**.
1. Seleziona **Impostazioni locali di origine** e quindi seleziona le impostazioni locali di origine.
1. Seleziona **Impostazioni locali di destinazione** e quindi seleziona le stesse impostazioni locali di origine. 
1. Per **Percorso URL**, inserisci un percorso URL univoco che non è attualmente utilizzato nell'ambiente di destinazione.
1. Ripeti i passaggi da 8 a 11 per ogni impostazione locale da mappare per il canale.
1. Selezionare **Applica**.
1. Ripeti i passaggi da 6 a 11 per ogni canale di origine.
1. Selezionare **Chiudi**.
1. Esamina la configurazione per verificarne l'accuratezza, quindi seleziona **Copia sito**.

> [!NOTE]
> Tutti i canali di origine e le impostazioni locali devono essere mappati e possono essere mappati solo una volta.

## <a name="monitor-the-site-copy-operation"></a>Monitorare l'operazione di copia del sito

Per monitorare lo stato di avanzamento dell'operazione di copia del sito, attenersi alla seguente procedura.

1. Accedi al generatore di siti per l'ambiente e-commerce di destinazione.
1. Nel riquadro a sinistra, seleziona **Processi tenant**.
1. Nella pagina **Processi tenant**, trova e seleziona il processo di copia del sito nell'elenco. Viene visualizzato un riquadro sulla destra e mostra lo stato ei dettagli del processo selezionato.

È possibile annullare un processo con stato **In corso**. Seleziona il processo nell'elenco, quindi seleziona **Annulla** nella barra dei comandi.

Puoi riprovare un processo con lo stato di **Non riuscito** o **Completato con errori**. Seleziona il processo nell'elenco, quindi seleziona **Riprova** nella barra dei comandi.

> [!NOTE]
> L'elaborazione delle risorse video potrebbe continuare dopo il completamento di un processo di copia del sito.

La figura seguente mostra un esempio del riquadro destro della pagina **Processi tenant** nel generatore di siti.

![Dettagli del processo nel riquadro di destra della pagina Processi tenant nel generatore di siti.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Inizializzare un nuovo sito utilizzando il processo FRE

Prima di poter utilizzare un nuovo sito, è necessario inizializzarlo tramite il processo FRE.

Per inizializzare un nuovo sito utilizzando il processo FRE, attenersi alla seguente procedura.

1. Accedi al generatore di siti per il nuovo sito.
1. Apri la visualizzazione elenco dei siti selezionando **Cambia sito** nell'angolo in alto a destra, quindi selezionando **Gestisci siti**.
1. Trova e seleziona il nuovo sito che vuoi inizializzare.
1. Nella finestra di dialogo **Configura il sito**, nel campo **Seleziona un dominio**, seleziona un dominio. Tutti i domini associati all'ambiente di e-commerce durante l'inizializzazione sono disponibili per la selezione.
1. Nel campo **Seleziona un canale predefinito**, seleziona il canale del punto vendita online associato. Il canale selezionato fornirà assortimenti e altre informazioni archiviate in Commerce Headquarters.
1. Nel campo **Seleziona una lingua predefinita**, seleziona la lingua di creazione predefinita. Tutte le lingue che sono state configurate per il canale del punto vendita online selezionato sono disponibili per la selezione.
1. Nel campo **Percorso**, il valore è costituito dal dominio di base e da un percorso URL facoltativo che è possibile immettere. Puoi lasciare vuoto il percorso dell'URL se il canale verrà servito dalla radice del dominio o se desideri inserire queste informazioni in un secondo momento nella visualizzazione della configurazione del canale nel generatore di siti. Il percorso del sito deve essere univoco nell'ambiente di e-commerce.
1. Seleziona **OK**. Il sito viene inizializzato con le informazioni che hai fornito e vieni reindirizzato alla visualizzazione di gestione del sito.

La figura seguente mostra un esempio della finestra di dialogo **Configura il sito** nel generatore di siti.

![Configura la finestra di dialogo del sito nel generatore di siti.](media/site-copy_3.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare reindirizzamenti URL in blocco](upload-bulk-redirects.md)

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-b2c-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
