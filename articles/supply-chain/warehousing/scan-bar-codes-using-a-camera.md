---
title: Eseguire la scansione dei codici a barre utilizzando una fotocamera nell'app Dynamics 365 Supply Chain Management - Magazzino
description: In questo argomento viene descritto come installare l'app Dynamics 365 Supply Chain Management - Magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8062a981f792bcfed2713d3cb6a42f414394f6a4
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251464"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-supply-chain-management---warehousing-app"></a>Eseguire la scansione dei codici a barre utilizzando una fotocamera nell'app Dynamics 365 Supply Chain Management - Magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come installare l'app Dynamics 365 Supply Chain Management - Magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile. 

## <a name="prerequisites"></a>Prerequisiti
Per utilizzare questa funzione, è necessario disporre della versione 1.2.0.0 dell'app Magazzino e il dispositivo deve disporre di una fotocamera. Quando si apre l'app dopo l'aggiornamento, verrà richiesto di consentire all'app di utilizzare la fotocamera. Se il dispositivo non dispone di una fotocamera, non verrà visualizzato alcun messaggio e non sarà possibile utilizzare una fotocamera come scanner. 

## <a name="setup"></a>Imposta
Nelle impostazioni di visualizzazione dell'applicazione Magazzino, è possibile specificare se la fotocamera deve essere utilizzata per la scansione del codice a barre. Se si consente l'**utilizzo della fotocamera come scanner**, è possibile utilizzare la fotocamera per ogni campo di input con modalità di input preferito impostata su **Scansione**. 

Per verificare se un campo di input deve essere sottoposto a scansione, nella pagina **Nomi campo per app magazzino** impostare **Modalità di input preferita** su **Scansione**. Quando questa opzione è selezionata, una fotocamera può essere utilizzata per la scansione nell'app Magazzino. Per informazioni su come configurare i nomi dei campi dell'app in Magazzino, vedere [Configurare i nomi di campo app nell'app Magazzino](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Formati di codice a barre supportati
I formati di codice a barre più comuni sono supportati, inclusi Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A e i codici QR. 

## <a name="navigation"></a>Navigazione
La pagina della fotocamera verrà avviata in ogni pagina in cui il campo di input ha modalità di input preferita impostata su Scansione. Nella pagina Fotocamera utilizzare le seguenti opzioni per navigare:
- Fare clic sul pulsante Indietro per tornare alla pagina dei dettagli e delle attività. 
- Fare clic sulla matita alla pagina dei dettagli di attività e passare alla finestra in cui è possibile immettere manualmente l'input.
- Fare clic sulla fotocamera alla pagina dei dettagli e delle attività per tornare alla pagina della fotocamera. 

| Pagina dei dettagli e delle attività | Pagina della fotocamera | 
| :---------------------: | :--------------------: |
| ![pagina dettagli attività di esempio scansione fotocamera](./media/camera-scanning-example-task-detail-page50.png)          | ![pagina fotocamera di esempio scansione fotocamera minori dimensioni](./media/camera-scanning-example-camera-page50.png)          |

Nella pagina della fotocamera, facendo clic sul pulsante Fotocamera, questo appare inattivo durante il tentativo di identificare un codice a barre. Se un codice a barre non viene identificato entro 5 secondi, il processo si interrompe e il pulsante Fotocamera diventa nuovamente disponibile. Sarà quindi possibile provare ad eseguire di nuovo la scansione di un codice a barre.

Quando si punta la fotocamera su un codice a barre, mantenere il codice a barre allineato alle parentesi per ottenere il miglior risultato. Se la scansione di un codice a barre viene effettuata correttamente, il risultato verrà elaborato e si verrà indirizzati al passaggio successivo. Se il passaggio successivo contiene un altro campo di input con la modalità di input preferita impostata su Scansione, la pagina della fotocamera verrà riavviata. Se il passaggio successivo non contiene un campo di scansione, la pagina della fotocamera non verrà avviata.

