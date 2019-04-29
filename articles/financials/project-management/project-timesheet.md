---
title: App per dispositivi mobili Project timesheet
description: In questo argomento vengono fornite informazioni sull'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet. L'app per dispositivi mobili Project Timesheet consente agli utenti di inviare e approvare fogli presenze progetto sul loro dispositivo mobile.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: a475085001b8fa10814c864ef35129eb6ebfdfef
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "969669"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>App per dispositivi mobili Microsoft Dynamics 365 Project Timesheet

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

L'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet consente agli utenti di inviare e approvare fogli presenze progetto sul loro dispositivo mobile (iPhone o Android). Questa app per dispositivi mobili utilizza la funzionalità per fogli presenze che si trova nell'area Gestione progetti e contabilità di Microsoft Dynamics 365 for Finance and Operations, migliorando la produttività e l'efficienza degli utenti e consentendo l'immissione e l'approvazione in breve tempo di fogli presenze progetto.

## <a name="download-and-install-the-mobile-app"></a>Scaricare e installare l'app per dispositivi mobili

Scaricare l'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet per Android o iPhone dallo store e installarla sul proprio dispositivo.

## <a name="enable-the-app"></a>Abilitare l'app 

In Dynamics 365 for Finance and Operations, l'app Project Timesheet deve essere abilitata. Per abilitare la funzionalità, andare a **Parametri Gestione progetti e contabilità \> Foglio presenze** e selezionare il parametro **Abilita Microsoft Dynamics 365 Project Timesheet**.

## <a name="sign-in-to-the-app"></a>Accedere all'app

1.  Avviare l'app sul dispositivo mobile.

2.  Immettere l'URL di Microsoft Dynamics 365 for Finance and Operations.

3.  La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.

4.  Si avrà accesso alla società predefinita.

## <a name="submit-a-project-timesheet"></a>Inviare un foglio presenze progetto

È possibile creare e inviare un foglio presenze progetto nell'app. È possibile creare un nuovo foglio presenze in base a informazioni di un foglio presenze precedente, righe salvate o assegnazioni di progetto. Se si è designati come delegato, è possibile immettere un foglio presenze per un altro lavoratore. Per creare un foglio presenze come delegato, selezionare il pulsante **Menu**, quindi selezionare un nome di risorsa.

La pagina del foglio presenze creerà un nuovo foglio presenze per il periodo del foglio presenze, in base alla data corrente. Verrà visualizzata la settimana lavorativa. Se il periodo del foglio presenze è relativo a più settimane, è possibile selezionare un'altra settimana lavorativa dalle schede delle settimane relative.
Se un foglio presenze esiste per la data corrente, verrà visualizzato. Se è necessario creare un nuovo foglio presenze in un altro periodo, selezionare il pulsante **Menu** e quindi **Nuova foglio presenze**.

È possibile immettere informazioni sul progetto facendo clic sull'azione **Aggiungi ora** o **Copia ora da**. L'azione **Copia ora da** copierà le informazioni delle righe del progetto, ma non le ore. Il menu **Copia ora da** include le opzioni seguenti:

- **Copia da foglio presenze esistente** - Consente di copiare le righe da un foglio presenze esistente.

- **Copia da Preferiti** - Consente di creare nuove righe del foglio presenze utilizzando le impostazioni del foglio presenze selezionato nei preferiti.

- **Copia da assegnazione** - Consente di creare righe foglio presenze da progetti assegnati.

Le informazioni di progetto visualizzate dipendono dai parametri definiti nella pagina **Parametri Gestione progetti e contabilità**.

Nel campo **Persona giuridica** selezionare la persona giuridica per cui è stato eseguito il progetto. Il campo **Persona giuridica** è disponibile solo se per la persona giuridica è stato abilitato il supporto per i fogli presenze interaziendali.

Selezionare il cliente associato con il progetto per il foglio presenze. Per la versione iniziale sul dispositivo Android, l'immissione da parte del cliente non è supportata, in quanto è necessario selezionare dapprima il progetto. Se è stato selezionato dapprima il progetto, il campo **Cliente** viene completato automaticamente.

Nel campo **Progetto** selezionare il progetto per il quale si sta immettendo l'ora. Il campo **Cliente** viene completato automaticamente.

Le ricerche clienti e progetti abilitano la ricerca nei clienti e nei progetti.

Selezionare le informazioni nei campi **Categoria**, **Attività**, **Proprietà riga**, **Fascia IVA** e **Fascia IVA articoli** come necessario. Questi campi possono essere ignorati.

Il campo **Proprietà riga** verrà impostato su un valore predefinito, in base ai parametri di Gestione progetti e contabilità. Quando i parametri Progetto/Categoria e Categoria/Risorsa sono abilitati, il campo **Proprietà riga** verrà impostato sul valore predefinito definito per questa convalida. Quando i parametri Progetto/Categoria e Categoria/Risorsa non sono abilitati, per impostazione predefinita il valore del campo **Proprietà riga** sarà basato sul campo **Abilita proprietà riga predefinita** nella pagina **Parametri Gestione progetti e contabilità**. Il valore di **Proprietà riga** può essere ignorato.

Selezionare un giorno per aggiungere ore. Immettere il numero di ore che si è lavorato ogni giorno.

Per aggiungere commenti sulle ore che si stanno immettendo, fare clic su **Aggiungi commenti**, quindi immettere i commenti per i destinatari interni, i clienti o per entrambi.
I commenti interni possono essere visualizzati dai manager di progetto, mentre i commenti per i clienti sono inclusi nelle fatture.

Per salvare le righe nella cartella Preferiti, selezionare la casella di controllo, quindi fare clic su **Salva come preferito**.

La dimensione finanziaria e il supporto di collegamento non sono forniti nell'app per dispositivi mobili.

Continuare ad aggiungere righe di progetto come necessario per completare il foglio presenze.

Fare clic su **Invia** per inviare il foglio presenze al flusso di lavoro di approvazione.

## <a name="review-timesheets"></a>Esaminare i fogli presenze

Un elenco dei fogli presenze che devono essere esaminati è disponibile nel menu. Questa opzione è disponibile solo se si è stati designati come approvatore del flusso di lavoro. L'approvazione della riga e dell'intestazione sono supportate. L'approvazione a livello di riga offre la possibilità di contrassegnare una o più righe per l'approvazione. Dopo aver esaminato le informazioni del foglio presenze, fare clic su **Approva**, **Delega** o **Restituisci** per continuare il flusso di lavoro.
