---
title: (ER) Importare configurazioni da RCS
description: In questo argomento vengono fornite informazioni su come un utente può importare una nuova versione di una configurazione ER da RCS.
author: NickSelin
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5674c418baaac7817c27780e2f0137ce6e7137eb3f1665f768ad843cc5b3114
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720786"
---
# <a name="er-import-configurations-from-rcs"></a>(ER) Importare configurazioni da RCS

[!include [banner](../../includes/banner.md)]

I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può importare una nuova configurazione per la creazione di report elettronici (ER) da Microsoft Regulatory Configuration Service (RCS). In questo esempio si selezionerà la versione della configurazione ER configurata in un'istanza di RCS e la si importerà nell'istanza corrente per la società di esempio, Litware, Inc. Questi passaggi possono essere eseguiti in qualsiasi società in quanto le configurazioni ER sono condivise tra tutte le società. Per completare questi passaggi, è necessario dapprima completare i passaggi nell'argomento [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). Per effettuare questi passaggi, è inoltre necessario accedere a un'istanza di RCS che contiene almeno una configurazione ER il cui stato è **Completato** o **Condiviso**.

1. Andare a **Amministrazione organizzazione** > **Aree di lavoro** > **Creazione di report elettronici**. 
2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se questo provider di configurazione non è visualizzato, completare i passaggi nell'argomento [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). 
3. Se si dispone di un ambiente RCS di cui è stato effettuato il provisioning per la società, selezionare il collegamento esterno **Regulatory services - Configurazione** e seguire le istruzioni per il provisioning di un ambiente RCS. 
4. Selezionare i **parametri per la creazione di report elettronici**. 
5. Selezionare la scheda **RCS**. 
6. Se si è già eseguito il provisioning dell'ambiente RCS per la società, utilizzare gli URL nella pagina per accedervi. 
7. Chiudere la pagina. 

## <a name="register-a-new-er-repository"></a>Registrare un nuovo archivio ER. 
1. Nell'elenco contrassegnare la riga selezionata. 
2. Selezionare il provider Litware, Inc. 
3. Selezionare Archivi. 
4. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa. 
5. Nel campo Tipo di archivio di configurazioni immettere "RCS". 
6. Selezionare Crea archivio. 
7. Nel campo Nome visualizzato ambiente RCS, immettere o selezionare un valore. 
8. Selezionare l'istanza di RCS desiderata. Possono esistere varie istanze. 
9. Selezionare OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importare le configurazioni ER dall'archivio basato su RCS
1. Seleziona **Mostra filtri**. 
2. Immettere un valore di filtro "RCS" nel campo **Nome** utilizzando l'operatore di filtro **inizia con**. 
3. Quando si apre l'archivio selezionato, nella pagina **Connessione a Regulatory Configuration Service**, selezionare il collegamento **Fare clic qui per connettersi a Regulatory Configuration Services**. 
4. Selezionare **Apri**. 
5. Selezionare **Chiudi**. 
6. Selezionare la versione desiderata della configurazione ER e selezionare **Importa** per importarla nell'istanza.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]