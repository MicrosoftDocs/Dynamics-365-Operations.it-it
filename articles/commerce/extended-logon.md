---
title: Configurare e utilizzare la funzionalità di accesso esteso
description: In questo argomento viene descritto come configurare e utilizzare la funzionalità di accesso esteso dell'applicazione punto vendita (POS) di Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: d211ecfe1550f6093e1d35e7c2b37c036b50dd4a
ms.sourcegitcommit: 5aebb181004eb63210503fb566dcda5c55032bee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491441"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>Configurare e utilizzare la funzionalità di accesso esteso

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come configurare e utilizzare la funzionalità di accesso esteso dell'applicazione punto vendita (POS) di Microsoft Dynamics 365 Commerce.

Cloud POS (CPOS) e Modern POS (MPOS) forniscono una funzionalità di accesso esteso che consente agli operatori dei punti vendita al dettaglio di accedere all'applicazione POS scansionando un codice a barre o strisciando una carta utilizzando un lettore di strisce magnetiche (MSR).

## <a name="set-up-extended-logon"></a>Impostare l'accesso esteso

Per configurare l'accesso esteso per i registri POS in un punto vendita al dettaglio, attieniti alla seguente procedura.

1. In Commerce headquarters vai a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**. 
2. Nel riquadro di spostamento a sinistra, seleziona il profilo di funzionalità associato al punto vendita al dettaglio.
3. Nella scheda dettaglio **Funzioni** sotto **Opzioni di autenticazione di accesso aggiuntive**, imposta le seguenti opzioni su **sì** o **no** a seconda dei casi:

    - **Accesso personale con codice a barre** – Imposta questa opzione su **sì** se vuoi che i tuoi dipendenti accedano al POS scansionando un codice a barre. 
    - **Accesso personale con codice a barre richiede la password** – Imposta questa opzione su **sì** se vuoi che i tuoi dipendenti accedano al POS scansionando un codice a barre e immettendo una password.
    - **Accesso personale con badge** – Imposta questa opzione su **sì** se vuoi che i tuoi dipendenti accedano al POS strisciando un badge.
    - **Accesso personale con badge richiede la password** – Imposta questa opzione su **sì** se vuoi che i tuoi dipendenti accedano al POS strisciando un badge e immettendo una password.

Il codice a barre o la tessera sono associati a credenziali che possono essere assegnate a un lavoratore. Le credenziali devono avere almeno sei caratteri. La stringa che contiene i primi cinque caratteri deve essere univoca ed è considerata l'*ID credenziale* che viene utilizzato per cercare un lavoratore. I caratteri rimanenti vengono utilizzati per la verifica della sicurezza. Ad esempio, hai due tessere, una delle quali ha le credenziali 12345DGYDEYTDW e l'altra ha le credenziali 12345EWUTBDAJH. Poiché queste due tessere hanno la stessa credenziale ID, 12345, non possono essere assegnate entrambe ai lavoratori.

## <a name="assign-extended-logon"></a>Assegnare l'accesso esteso

Per impostazione predefinita, solo i responsabili possono assegnare l'accesso esteso lavoratori. Per assegnare l'accesso esteso, passare a **Accesso esteso** nel POS. Quindi cercare un lavoratore immettendone l'ID operatore nel campo di ricerca. Selezionare il lavoratore e quindi fare clic su **Assegna**. Nella pagina successiva, passare o leggere con lo scanner l'accesso esteso per assegnarlo al lavoratore. Se il passaggio o la scansione ha esito positivo, il pulsante **OK** diventa disponibile. Fare clic su **OK** per salvare l'accesso esteso per il lavoratore.

## <a name="delete-extended-logon"></a>Eliminare un accesso esteso

Per eliminare l'accesso esteso assegnato a un lavoratore, individuare il lavoratore utilizzando l'operazione **Accesso esteso**. Selezionare il lavoratore e fare clic sulla scheda **Annulla assegnazione**. Tutte le credenziali di accesso esteso associate al lavoratore verranno rimosse.

## <a name="use-extended-logon"></a>Utilizzare l'accesso esteso

Se l'accesso esteso è configurato e un lavoratore è stato assegnato a un codice a barre o una banda magnetica, il lavoratore dovrà semplicemente passare o eseguire la scansione della scheda durante la visualizzazione della pagina di accesso del POS. Se è necessaria anche una password prima che l'accesso possa continuare, al lavoratore viene richiesto di immettere la relativa password.

## <a name="extend-extended-logon"></a>Estendere l'accesso esteso

L'implementazione predefinita della funzionalità di accesso esteso richiede che le credenziali abbiano una lunghezza minima di sei caratteri e che i primi cinque caratteri (l'ID credenziale) siano univoci. Inizialmente era inteso come un esempio che gli sviluppatori potevano personalizzare per soddisfare i requisiti di un'implementazione specifica. Ad esempio, può essere personalizzato per supportare più caratteri o utilizzare regole di verifica della sicurezza diverse. Per informazioni dettagliate su come creare estensioni per l'accesso esteso, vedi [Estensione della funzionalità di accesso esteso per MPOS e Cloud POS](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/).

Il servizio di accesso può essere esteso anche per supportare dispositivi di accesso estesi aggiuntivi, ad esempio scanner palmari. Per ulteriori informazioni, vedi la [documentazione di POS sull'estendibilità](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
