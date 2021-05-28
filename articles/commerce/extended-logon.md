---
title: Impostare la funzionalità di accesso esteso per MPOS e Cloud POS
description: Questo argomento illustra le opzioni per l'impostazione dell'accesso esteso per POS cloud e Retail Modern POS (MPOS).
author: rubencdelgado
ms.date: 06/20/2017
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
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9d8889581e2e11fa5261805c866a6014df57611
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027578"
---
# <a name="set-up-extended-logon-functionality-for-mpos-and-cloud-pos"></a>Impostare la funzionalità di accesso esteso per MPOS e Cloud POS

[!include [banner](includes/banner.md)]

Questo argomento illustra le opzioni per l'impostazione dell'accesso esteso per POS cloud e Retail Modern POS (MPOS).

## <a name="setting-up-extended-logon"></a>Impostazione dell'accesso esteso

Le impostazioni per le maschere dei codici a barre sono disponibili in **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **Profili POS** &gt; **Profili funzionalità**. La scheda Dettaglio **Funzioni** include le seguenti opzioni correlate all'accesso esteso.

### <a name="staff-bar-code-logon"></a>Accesso personale con codice a barre

Se l'opzione **Accesso personale con codice a barre** è attivata, i lavoratori con accesso esteso assegnato alle credenziali del POS possono collegarsi mediante un codice a barre.

### <a name="staff-bar-code-logon-requires-password"></a>L'accesso personale con codice a barre richiede la password

Se l'opzione **L'accesso personale con codice a barre richiede la password** è attivata, l'accesso personale con codice a barre seleziona solo il lavoratore assegnato all'accesso esteso che viene presentato. I lavoratori devono comunque immettere la propria password se questa opzione è abilitata.

### <a name="staff-card-logon"></a>Accesso personale con badge

Se l'opzione **Accesso personale con badge** è attivata, i lavoratori con accesso esteso assegnato alle credenziali del POS possono collegarsi mediante una banda magnetica.

### <a name="staff-card-logon-requires-password"></a>L'accesso personale con badge richiede la password

Se l'opzione **L'accesso personale con badge richiede la password** è attivata, l'accesso personale con badge seleziona solo il lavoratore assegnato all'accesso esteso che viene presentato. I lavoratori devono comunque immettere la propria password se questa opzione è abilitata.

## <a name="assigning-an-extended-logon"></a>Assegnazione di un accesso esteso

Per impostazione predefinita, solo i responsabili possono assegnare l'accesso esteso lavoratori. Per assegnare l'accesso esteso, passare a **Accesso esteso** nel POS. Quindi cercare un lavoratore immettendone l'ID operatore nel campo di ricerca. Selezionare il lavoratore e quindi fare clic su **Assegna**. Nella pagina successiva, passare o leggere con lo scanner l'accesso esteso per assegnarlo al lavoratore. Se il passaggio o la scansione ha esito positivo, il pulsante **OK** diventa disponibile. Fare clic su **OK** per salvare l'accesso esteso per il lavoratore.

## <a name="deleting-an-extended-logon"></a>Eliminazione di un accesso esteso

Per eliminare l'accesso esteso assegnato a un lavoratore, individuare il lavoratore utilizzando l'operazione **Accesso esteso**. Selezionare il lavoratore e fare clic sulla scheda **Annulla assegnazione**. Tutte le credenziali di accesso esteso associate al lavoratore verranno rimosse.

## <a name="extending-extended-logon"></a>Estensione dell'accesso esteso

Il servizio di accesso può essere esteso per supportare dispositivi di accesso estesi aggiuntivi, ad esempio scanner palmari. Per ulteriori informazioni, vedere la documentazione di POS sull'estendibilità.

## <a name="using-extended-logon"></a>Utilizzo dell'accesso esteso

Se l'accesso esteso è configurato e un lavoratore è stato assegnato a un codice a barre o una banda magnetica, il lavoratore dovrà semplicemente passare o eseguire la scansione della propria scheda durante la visualizzazione della pagina di accesso del POS. Se è necessaria anche una password prima che l'accesso possa continuare, al lavoratore viene richiesto di immettere la sua password.


[!INCLUDE[footer-include](../includes/footer-banner.md)]