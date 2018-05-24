---
title: Sicurezza degli utenti del portale fornitori
description: In questo articolo viene illustrato come configurare la sicurezza dei fornitori esterni che utilizzano il portale fornitori. Queste informazioni si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 5819d21a91ac2a7c91f19fd6d80fd7b983411545
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="vendor-portal-user-security"></a>Sicurezza degli utenti del portale fornitori

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come configurare la sicurezza dei fornitori esterni che utilizzano il portale fornitori. Queste informazioni si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX.

La funzionalità portale fornitori è stata sostituita da funzionalità estese di collaborazione fornitore in Dynamics 365 for Operations versione 1611. Per ulteriori informazioni su come impostare la sicurezza per la collaborazione fornitore, vedere [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md). Il portale fornitori espone un set limitato di informazioni sugli ordini fornitore per i fornitori esterni. È importante impostare correttamente le autorizzazioni utente del portale fornitori in Microsoft Dynamics AX, in modo che i fornitori non abbiano accesso in modo non intenzionale a informazioni aggiuntive nella soluzione Dynamics AX. **Importante**: a differenza degli altri utenti, i fornitori esterni non devono avere il ruolo **SystemUser**. Il ruolo **SystemUser** consente l'accesso a un set di privilegi non appropriati per gli utenti esterni.

## <a name="setting-up-a-vendor-portal-user"></a>Impostazione di un utente del portale fornitori
Prima di creare un account utente per una persona che utilizzerà il portale fornitori, è necessario impostare il fornitore per consentire collaborazione tramite il portale fornitori. Utilizzare il campo **Collaborazione su ordine fornitore** nella scheda **Generale** della pagina **Fornitori**. I fornitori esterni che utilizzano il portale fornitori devono avere la seguente impostazione:

-   Un account utente di Microsoft Azure Active Directory (AAD) deve essere registrato per il fornitore nella pagina **Utenti** in Dynamics AX.
-   Il fornitore deve avere il ruolo di sicurezza **Fornitore (esterno)**, non il ruolo **SystemUser**. **Nota**: il ruolo **SystemUser** viene concesso automaticamente quando si crea un nuovo account utente in Dynamics AX. Di conseguenza, è necessario rimuovere questo ruolo e verificare il messaggio di avviso ricevuto.
-   All'utente fornitore non deve essere concessa l'autorizzazione ad aggiungere ulteriori campi delle tabelle dell'ordine fornitore nella visualizzazione dell'ordine fornitore. Nella scheda **Personalizzazione** della scheda **Utenti** impostare l'opzione **Personalizzazione esplicita consentita** per l'utente su **No**.
-   L'account utente deve essere associato a un contatto registrato. Nella pagina **Utenti**, selezionare un contatto nel campo **Nome**. La persona selezionata deve avere il ruolo **Contatto** per il fornitore pertinente.

Se la stessa persona richiede l'accesso al portale fornitori per più conti fornitori (magari per persone giuridiche diverse), ogni account utente di tale persona deve essere associato allo stesso contatto registrato. Il ruolo **Fornitore (esterno)** include tutte le funzionalità di base necessarie per utilizzare la funzionalità disponibile nel portale fornitori. Questa impostazione garantisce che l'interfaccia utente che l'utente esterno visualizza sia incentrata solo sullo scenario desiderato.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Collaborazione fornitore](collaborate-vendors-vendor-portal.md)




