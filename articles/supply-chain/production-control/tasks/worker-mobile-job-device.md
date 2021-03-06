---
title: Configurare un lavoratore tramite il dispositivo di processo mobile
description: Questa argomento spiega come assegnare i ruoli corretti all'account utente di un lavoratore e abilitare il lavoratore a effettuare le registrazioni del reparto produzione.
author: ShylaThompson
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, HcmWorker, JmgRegistrationSetupTouch, JmgRegistrationSetupAssignUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3fe4e195763f5329ee7732a2f087094acbad595a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810944"
---
# <a name="configure-a-worker-using-the-mobile-job-device"></a>Configurare un lavoratore tramite il dispositivo di processo mobile

[!include [banner](../../includes/banner.md)]

Questa argomento spiega come assegnare i ruoli corretti all'account utente di un lavoratore e abilitare il lavoratore a effettuare le registrazioni del reparto produzione.

## <a name="verify-that-a-worker-is-assigned-a-certain-role"></a>Verificare che a un lavoratore è assegnato un determinato ruolo

Per questo esempio, verificare che all'utente "SHANNON " sia assegnato il ruolo di operatore prima di configurare l'account del lavoratore.

1. Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti**.
2. Cercare un utente nel filtro rapido. Per questo esempio, immettere `shannon`.
3. Selezionare il collegamento nella colonna **ID utente** dell'account utente visualizzato.
4. Nella struttura **Ruoli utente**, selezionare **Ruoli > Operatore macchina**.
5. Chiudere le pagine **dettagli utente** e **utenti** per tornare alla home page.

## <a name="configure-worker-account"></a>Configurare l'account del lavoratore
1. Passare a **Pannello di navigazione > Moduli > Risorse umane > Lavoratori > Lavoratori**.
2. Cercare un utente nel filtro rapido. Per questo esempio, immettere `shannon`.
3. Selezionare il collegamento nella colonna **Nome** dell'account utente visualizzato.
4. Fare clic sulla scheda **Registrazione ore**.
5. Selezionare **Attiva su terminali registrazioni**.
6. Immettere o selezionare i valori nei seguenti campi:  

    - **Gruppo di calcolo**  
    - **Gruppo di calcolo predefinito**  
    - **Gruppo di approvazione**  
    - **Profilo standard**  
    - **Gruppo profilo**  

7. Selezionare **OK**.
8. Fare clic su **Modifica** per immettere un numero di badge per il nuovo lavoratore per registrazione ore. Nel campo **ID badge** immettere un valore.
9. Selezionare **Salva**.
10. Chiudere le pagine **Dettagli lavoratore** e **Lavoratori**.

## <a name="assign-worker-to-device-group"></a>Assegnare il lavoratore a un gruppo di dispositivi
1. Andare a **Controllo produzione > Impostazioni > Esecuzione produzione > Configura scheda processo per dispositivi**.
2. Selezionare **Aggiungi**.
3. Selezionare il lavoratore desiderato nell'elenco. Per questo esempio, selezionare **SHANNON**.
4. Selezionare **OK**.
5. Selezionare **Modifica**.
6. Nel campo **Unità di produzione**, è possibile impostare il filtro predefinito per il lavoratore. In tal modo si assicura che solo i processi di produzione per l'unità di produzione selezionata vengano visualizzati quando il lavoratore accede al dispositivo. Immettere il valore desiderato.
7. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]