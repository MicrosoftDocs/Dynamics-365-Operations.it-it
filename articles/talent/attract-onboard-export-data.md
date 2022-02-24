---
title: Esportare dati da Attract e Onboard
description: Esportare dati da Dynamics 365 Talent - Attract e Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461583"
---
# <a name="export-data-from-attract-and-onboard"></a>Esportare dati da Attract e Onboard

[!include [banner](includes/banner.md)]

Come annunciato in [Ritiro delle app Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard verranno ritirate il 1° febbraio 2022. Per facilitare la migrazione verso un altro prodotto, entrambe le app offrono ora funzionalità di esportazione dei dati.

## <a name="export-data-from-attract"></a>Esportare dati da Attract

È possibile esportare i propri dati senza limitare l'accesso all'ambiente. È possibile che si voglia eseguire questa operazione per scopo di test o per comprendere la nostra struttura dati. Quando si è pronti per migrare, limitare l'accesso all'ambiente Attract usando le istruzioni dopo questa procedura. Assicurarsi di esportare di nuovo i propri dati. 

1. Accedere a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Sotto **Esportazione dati**, selezionare **Richiedi un'esportazione di dati**.

   ![[Richiedere un'esportazione di dati da Attract](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. Quando viene visualizzata la finestra di messaggio **Elaborazione della richiesta in corso**, selezionare **OK**. L'esportazione di dati può richiedere fino a 20 minuti, a seconda delle dimensioni dell'esportazione.

4. Al termine dell'esportazione, selezionare il pulsante **Scarica**. 

   >[!NOTE]
   >Tutte le esportazioni di dati sono disponibili per sette giorni, dopodiché il collegamento **Scarica** scade.</br>
   
Il download contiene un file zip con i dati di Attract, incluse le seguenti cartelle:

| Nome cartella | Descrizione |
| --- | --- |
| Impostazioni di amministrazione | Le configurazioni dell'interfaccia di amministrazione di Attract. |
| Candidati | Tutti i candidati aggiunti a posti di lavoro o pool di talenti. |
| Modelli di messaggio di posta elettronica | Tutti i modelli di posta elettronica configurati per l'ambiente. |
| Modelli di pacchetti di offerte di lavoro | Tutti i modelli di pacchetti di offerte di lavoro creati, oltre alle relative configurazioni associate. |
| Set di regole per offerte di lavoro |  Tutti i file di set di regole caricati per la gestione delle offerte. |
| Modelli di offerte di lavoro | Tutti i modelli di documenti di offerte di lavoro creati per l'ambiente. |
| Posizioni aperta | Tutte le posizioni create. Le posizioni eliminate non vengono esportate. Le sottocartelle contengono domande di lavoro dei candidati, con sottocartelle per gli allegati delle domande di lavoro e pacchetti di offerte, dove applicabile. |
| Modelli di posizioni lavorative | Modelli di elaborazione delle posizioni lavorative configurati per l'ambiente. |
| Pool di talenti | Tutti i gruppi di talenti creati, gli elenchi dei relativi contributori e gli elenchi dei candidati per i gruppi di talenti. |
| Lavoratori | Elenco di tutti i lavoratori presenti nell'ambiente, oltre ai loro ruoli. |
| (cartella principale) | Un file di schema JSON che descrive i campi della struttura dei dati. |

### <a name="restrict-access-to-attract"></a>Limitare l'accesso a Attract

Quando si è pronti per migrare, impedire ai non amministratori di accedere all'ambiente Attract e di esportare i dati.

>[!IMPORTANT]
>La limitazione dell'accesso all'ambiente Attract è permanente e non può essere annullata. Se si desidera che gli utenti non amministratori continuino ad accedere all'ambiente, saltare questo passaggio.

1. Accedere a [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. Per impedire ai non amministratori di accedere all'ambiente Attract, in **Limita accesso a questa app**, selezionare **Limita l'accesso ora**. La limitazione dell'accesso inoltre annulla le posizioni lavorative attive che sono state pubblicate.

   ![[Impedire l'accesso a Attract ai non amministratori](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Quando viene visualizzato l'avvertimento **Questa è una modifica permanente**, selezionare **Limita accesso** per limitare in modo permanente l'accesso degli utenti non amministratori da questo ambiente. Se non si è pronti per completare questo passaggio, selezionare **Annulla**.

   ![[Avviso che informa che la limitazione dell'accesso è una modifica permanente](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >Gli amministratori possono continuare ad accedere alle pagine di esportazione dei dati e dei report personali dopo la limitazione dell'accesso all'ambiente Attract.

## <a name="export-data-from-onboard"></a>Esportare dati da Onboard

Quando si è pronti, è possibile scaricare modelli, guide e dati sui candidati da Onboard.

1. Accedere a [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. Sotto **Esportazione dati**, selezionare **Richiedi un'esportazione di dati**. 

   ![[Richiedere un'esportazione di dati da Onboard](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. Quando viene visualizzata la finestra di messaggio **Elaborazione della richiesta in corso**, selezionare **OK**. L'esportazione di dati può richiedere fino a 20 minuti, a seconda delle dimensioni dell'esportazione.

4. Al termine dell'esportazione, selezionare il pulsante **Scarica**. 

   ![[Scaricare un esportazione di dati da Onboard](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >L'esportazione di dati è disponibile per sette giorni. Dopo sette giorni, il collegamento **Scarica** scade ed è necessario richiedere una nuova esportazione per scaricare di nuovo i dati. Quando si avvia una nuova esportazione di dati, tutti i download esistenti scadranno al completamento della nuova esportazione.

Il download è un file zip che contiene:

- Una cartella **Modelli** che contiene i modelli di Onboard nel formato documento di Word.

- Una cartella **Guide** che contiene le guide di Onboard nel formato documento di Word.

## <a name="see-also"></a>Vedere anche

[Ritiro delle app Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)