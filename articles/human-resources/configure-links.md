---
title: Creare collegamenti da Human Resources a un altro ambiente
description: Questo argomento spiega come creare un collegamento da Microsoft Dynamics 365 Human Resources a un altro ambiente Dynamics 365.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d20eef4b4861d85ead1d47ca493c3a5c2d2d85e8
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712627"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Creare collegamenti da Human Resources a un altro ambiente Finance

Un cliente potrebbe avere due ambienti Dynamics 365 in cui sta lavorando. Ad esempio, il cliente potrebbe avere un ambiente Dynamics 365 Human Resources nell'infrastruttura Finance e la necessità di connettersi a un altro ambiente Dynamics 365 Finance. 

Questa funzionalità consentirà i collegamenti da una pagina di Human Resources a una pagina specifica in un altro ambiente Finance. Quando i collegamenti sono configurati, è possibile specificare dove sarà disponibile il collegamento in Human Resources e la pagina di destinazione che verrà aperta nell'altro ambiente.

> [!Note] 
> È necessario attivare **Miglioramenti dell'esperienza utente Human Resources** in **Gestione funzionalità** per ottenere questa funzionalità.

## <a name="configure-target-systems"></a>Configurare i sistemi di destinazione

In Human Resources, gli amministratori di sistema possono definire collegamenti che verranno presentati nelle pagine di **Human Resources**. Parti della configurazione sono gli ambienti Finance a cui si desidera spostarsi come destinazione del collegamento. 

Per configurare il sistema di destinazione:
1. Nella pagina **Configura collegamenti**, selezionare **Configura sistema di destinazione**.  
2. Immettere il nome del sistema di destinazione e fornire l'URL dell'ambiente Finance. Dopo aver configurato i sistemi di destinazione, è possibile definire i collegamenti.

## <a name="configure-links"></a>Configura collegamenti

Ogni collegamento creato conterrà le seguenti informazioni definite:
 - **Collegamento**: nome del collegamento. Usato solo per l'identificazione.
 - **Abilita questo collegamento**: impostare su **Sì** se si desidera visualizzare il collegamento per gli utenti di Human Resources.
 - **Nome visualizzato**: immettere il nome che apparirà come collegamento all'ambiente secondario. 
 - **Collegamento area nel modulo**: scegliere su quale pagina visualizzare il collegamento. I collegamenti possono essere visualizzati solo nell'area di lavoro **Dipendente self-service** e nelle pagine **Mansione**, **Posizione**, **Lavoratore** e **Lavoratore semplificato**.
 - **Gruppo**: è possibile organizzare i collegamenti utilizzando i gruppi. Selezionare un gruppo esistente o crearne uno nuovo usando la colonna **Gruppo**.
 - **Sistema di destinazione**: selezionare il sistema di destinazione che è stato creato utilizzando l'opzione **Configura sistema di destinazione**. Questo sarà l'ambiente secondario che verrà utilizzato per spostarsi usando il collegamento.
 - **Usa società corrente dell'utente**: selezionare **Sì** per utilizzare la società corrente dell'utente quando ci si sposta in Finance. Selezionare **No** per selezionare la società da utilizzare.
 - Voce di menu di **destinazione**: immettere la voce di menu dell'ambiente Finance che il collegamento dovrebbe utilizzare durante la navigazione. Sono disponibili voci di menu sulle quali è possibile spostarsi direttamente. 

   Per trovare la voce di menu richiesta:
   1. Andare all'ambiente Finance e aprire la pagina che corrisponde alla destinazione dello spostamento. 
   2. Copiare la voce di menu dall'URL. Ad esempio, se si desidera che il collegamento porti all'elenco dei dipendenti in Finance and Operations, immettere il valore visualizzato dopo "&mi" nell'URL. 
   3. La voce di menu per navigare alla pagina con l'elenco dei dipendenti in questo esempio è: HcmWorkerListPage_Employees.

 - **Collegamento a origine dati**: selezionare l'origine dei dati a cui si riferisce il collegamento. Le origini più comuni come **Lavoratore** e **Posizione** sono disponibili.

### <a name="access-to-links"></a>Accedere ai collegamenti

Gli amministratori di sistema vedranno i collegamenti appena creati nelle pagine definite anche se l'opzione **Abilitare questo collegamento** è impostata su **No**. Ciò può essere utilizzato per verificare i collegamenti prima di renderli disponibili ad altri dipendenti. Tutti gli altri ruoli vedranno i collegamenti configurati solo dopo che l'opzione **Abilita questo collegamento** è stata impostata su **Sì**. I dipendenti che hanno accesso alle pagine in cui i collegamenti vengono resi disponibili potranno accedere ad essi.

Gli utenti devono inoltre disporre dei diritti di sicurezza all'interno dell'ambiente secondario definito per accedere alle pagine in tale ambiente. In caso contrario, viene visualizzata una finestra di dialogo di protezione quando si utilizza il collegamento.

