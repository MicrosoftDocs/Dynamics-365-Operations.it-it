---
title: Creare gruppi di autorizzazioni POS
description: In questo argomento viene illustrato come creare un gruppo di autorizzazioni POS.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ffc64fd39a390af3ca7110178ef0999527106dc
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141385"
---
# <a name="create-pos-permission-groups"></a>Creare gruppi di autorizzazioni POS

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come creare un gruppo di autorizzazioni POS. La società di dati dimostrativi utilizzata per creare questa attività è USRT. Questa attività è destinata al ruolo Responsabile operativo commercio.

1. Nel pannello di navigazione, andare a **Moduli > Retail e Commerce > Dipendenti > Gruppi di autorizzazioni**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **ID gruppo di autorizzazioni POS**.
4. Digitare un valore nel campo **Descrizione**
5. Selezionare **Sì** nel campo **Visualizza voci orologio**. È ora possibile abilitare o disabilitare le varie autorizzazioni per il gruppo di autorizzazioni POS. Per alcune autorizzazioni è possibile impostare un valore che verrà utilizzato per valutare se l'utente POS può eseguire l'azione. Questa guida attività abilita l'autorizzazione che può essere assegnata al cassiere.  
6. Selezionare **Sì** nel campo **Consenti creazione ordine**.
7. Selezionare **Sì** nel campo **Consenti modifica ordine**.
8. Selezionare **Sì** nel campo **Consenti recupero ordine**.
9. Selezionare **Sì** nel campo **Consenti modifica password**.
10. Selezionare **Sì** nel campo **Consenti chiusura forzata**.
11. Selezionare **Salva**. Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di commercio. 
12. Nel pannello di navigazione, andare a **Moduli > Risorse umane > Posizioni lavorative > Posizioni lavorative**.
13. Quindi, verrà assegnato il gruppo di autorizzazioni POS a un processo. Nell'elenco trovare e selezionare il record desiderato.
14. Selezionare **Modifica**.
15. Espandere la sezione **Classificazione mansione**.
16. Nel campo Gruppo di autorizzazioni POS immettere o selezionare un valore. Tutti i lavoratori nelle posizioni per questo processo utilizzeranno le impostazioni del gruppo di autorizzazioni POS a meno che le autorizzazioni POS del lavoratore siano state ignorate a livello di posizione.  
17. Selezionare **Salva**. Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali.  

