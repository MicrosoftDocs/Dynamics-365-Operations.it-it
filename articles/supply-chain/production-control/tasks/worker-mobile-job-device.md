---
title: Configurare un lavoratore tramite il dispositivo di lavoro mobile
description: Questa procedura consente di assegnare i ruoli corretti all'account utente di un lavoratore e quindi consente al lavoratore di effettuare le registrazioni del reparto produzione.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bb4d806810660e55ef13a9ff21c07e0ce194496
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571360"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurare un lavoratore tramite il dispositivo di lavoro mobile

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura consente di assegnare i ruoli corretti all'account utente di un lavoratore e quindi consente al lavoratore di effettuare le registrazioni del reparto produzione.


## <a name="assign-roles-to-user-account"></a>Assegnare ruoli all'account utente
1. Andare a Amministrazione sistema > Utenti > Utenti.
2. Utilizzare il filtro rapido per filtrare il nome di un lavoratore nell'account utente associato al ruolo operatore macchina. Nei dati di esempio, il nome sarà Shannon.
3. Evidenziare il record dell'account utente.
4. Nell'elenco, fare clic sul collegamento 'Nome' nella riga selezionata per visualizzare i dettagli dell'account utente.
5. Nella struttura, selezionare 'Ruoli\Operatore macchina'.
6. Chiudere la pagina dei dettagli dell'account utente.
7. Chiudere la pagina.

## <a name="configure-worker-account"></a>Configurare l'account del lavoratore.
1. Andare a Risorse umane > Lavoratori > Lavoratori.
2. Utilizzare il filtro rapido per filtrare il nome di un lavoratore nell'account utente associato al ruolo operatore macchina. Nei dati di esempio, il nome sarà Shannon.
3. Evidenziare il record dell'account utente.
4. Nell'elenco, fare clic sul collegamento 'Nome' nella riga selezionata per visualizzare i dettagli dell'account utente.
5. Fare clic sulla scheda Impiego.
6. Espandere la scheda dettaglio Registrazione ore e fare clic su Attiva su terminali registrazioni.
7. Fare clic su Attiva su terminali registrazioni.
8. Nel campo Gruppo di calcolo immettere o selezionare un valore.
9. Nel campo Gruppo di calcolo predefinito immettere o selezionare un valore.
10. Nel campo Gruppo di approvazione immettere o selezionare un valore.
11. Nel campo Profilo standard immettere o selezionare un valore.
12. Nel campo Gruppo di profili immettere o selezionare un valore.
13. Fare clic su OK.
14. Fare clic su Modifica per immettere un numero di badge per il nuovo lavoratore per registrazione ore.
15. Digitare un valore nel campo ID badge.
16. Fare clic su Salva.
17. Utilizzare il collegamento SaveRecord.
18. Chiudere la pagina del dettagli del lavoratore.
19. Chiudere la pagina.

## <a name="assign-worker-to-device-group"></a>Assegnare il lavoratore al gruppo di dispositivi.
1. Andare a Controllo produzione > Impostazioni > Esecuzione produzione > Configura scheda processo per dispositivi.
2. Scegliere Aggiungi.
3. Nell'elenco contrassegnare la riga selezionata.
4. Fare clic su OK.
5. Fare clic su Modifica.
6. Nel campo Unità di produzione, è possibile impostare il filtro predefinito per il lavoratore. In tal modo si assicura che solo i processi di produzione per l'unità di produzione selezionata vengano visualizzati quando il lavoratore accede al dispositivo.
7. Chiudere la pagina.

