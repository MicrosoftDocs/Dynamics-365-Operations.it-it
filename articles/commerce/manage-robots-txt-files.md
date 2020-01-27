---
title: Gestire i file robots.txt
description: Questo argomento descrive come gestire i file robots.txt in Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: e472f3612bd6860e7262bb128035f2aed3b39372
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946034"
---
# <a name="manage-robotstxt-files"></a>Gestire i file robots.txt

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Questo argomento descrive come gestire i file robots.txt in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Lo standard di esclusione dei robot, o robots.txt, è uno standard utilizzato dai siti Web per comunicare con i robot Web. Indica ai robot Web le aree di un sito Web che non devono essere visitate. I robot vengono spesso utilizzati dai motori di ricerca per indicizzare i siti Web.

Per escludere i robot da un server, si crea un file sul server. In questo file, si specificano i criteri di accesso per i robot. Il file deve essere accessibile tramite HTTP all'URL locale **/robots.txt**. Il file robots.txt aiuta i motori di ricerca a indicizzare il contenuto del sito.

Dynamics 365 Commerce consente di caricare un file robots.txt per il dominio. Per ogni dominio nell'ambiente Commerce, è possibile caricare un file robots.txt e associarlo a quel dominio.

Per ulteriori informazioni sul file robots.txt, visitare [Le pagine dei robot Web](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Caricare un file robots.txt

Dopo aver creato e modificato il file robots.txt in base allo [standard di esclusione dei robot](https://www.robotstxt.org/orig.html), assicurarsi che il file sia accessibile sul computer in cui verranno utilizzati gli strumenti di creazione di Commerce. Il file deve essere denominato **robots.txt**. Per risultati ottimali, deve essere nel formato indicato nello standard. Ogni cliente Commerce è responsabile della convalida e della manutenzione dei contenuti del suo file robots.txt. Per caricare un file robots.txt, è necessario effettuare l'accesso a Commerce come amministratore di sistema.

Per caricare un file robots.txt in Commerce, effettuare le seguenti operazioni.

1. Accedere a Commerce come amministratore di sistema.
2. Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.
3. Sotto **Impostazioni tenant**, selezionare **robots.txt**. Un elenco di tutti i domini associati all'ambiente appare nella parte principale della finestra.
4. Selezionare **Gestisci** per caricare un file robots.txt per un dominio nell'ambiente.
5. Nel menu a destra, selezionare il pulsante **Carica** (la freccia rivolta verso l'alto) accanto al dominio associato al file robots.txt. Viene visualizzata una finestra di dialogo del browser di file.
6. Nella finestra di dialogo, individuare e selezionare il file robots.txt che si desidera caricare per il dominio associato, quindi selezionare **Apri** per completare il caricamento.

> [!NOTE] 
> Durante il caricamento, Commerce verifica che il file sia un file di testo, ma non convalida il contenuto del file.

## <a name="download-a-robotstxt-file"></a>Scaricare un file robots.txt

Per scaricare un file robots.txt in Commerce, effettuare le seguenti operazioni.

1. Accedere a Commerce come amministratore di sistema.
2. Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.
3. Sotto **Impostazioni tenant**, selezionare **robots.txt**. Un elenco di tutti i domini associati all'ambiente appare nella parte principale della finestra.
4. Selezionare **Gestisci** per scaricare un file robots.txt per un dominio nell'ambiente.
5. Nel menu a destra, selezionare il pulsante **Scarica** (la freccia rivolta verso il basso) accanto al dominio associato al file robots.txt. Viene visualizzata una finestra di dialogo del browser di file.
6. Nella finestra di dialogo, andare alla posizione desiderata sull'unità locale, confermare o inserire un nome file e quindi selezionare **Salva** per completare il download.

> [!NOTE]
> Questa procedura può essere utilizzata per scaricare solo i file robots.txt precedentemente caricati tramite gli strumenti di creazione di Commerce.

## <a name="delete-a-robotstxt-file"></a>Eliminare un file robots.txt

Per eliminare un file robots.txt in Commerce, effettuare le seguenti operazioni.

1. Accedere a Commerce come amministratore di sistema.
2. Nel riquadro di spostamento sinistro, selezionare **Impostazioni tenant** (accanto al simbolo dell'ingranaggio) per espanderlo.
3. Sotto **Impostazioni tenant**, selezionare **robots.txt**. Un elenco di tutti i domini associati all'ambiente appare nella parte principale della finestra.
4. Selezionare **Gestisci** per eliminare un file robots.txt per un dominio nell'ambiente.
5. Nel menu a destra, selezionare il pulsante **Elimina** (il simbolo del cestino) accanto al dominio associato al file robots.txt. Viene visualizzata una finestra del browser di file.
6. Nella finestra del browser di file, individuare e selezionare il file robots.txt che si desidera eliminare per il dominio, quindi selezionare **Apri**. Viene visualizzata una finestra di messaggio di avviso.
7. Nella finestra del messaggio, selezionare **Elimina** per confermare l'eliminazione del file robots.txt.

> [!NOTE] 
> Questa procedura può essere utilizzata per eliminare solo i file robots.txt precedentemente caricati tramite gli strumenti di creazione di Commerce.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo sito di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito online a un canale](associate-site-online-store.md)

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
