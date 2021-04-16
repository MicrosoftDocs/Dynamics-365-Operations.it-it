---
title: Eseguire la scansione dei codici a barre utilizzando una fotocamera nell'app per dispositivi mobili Gestione magazzino
description: In questo argomento viene descritto come installare l'app per dispositivi mobili Gestione magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831220"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Eseguire la scansione dei codici a barre utilizzando una fotocamera nell'app per dispositivi mobili Gestione magazzino

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come installare l'app per dispositivi mobili Gestione magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.

## <a name="setup"></a>Attrezzaggio

Nelle impostazioni di visualizzazione dell'app per dispositivi mobili Gestione magazzino, è possibile specificare se la fotocamera deve essere utilizzata per la scansione del codice a barre. Se si consente l'**utilizzo della fotocamera come scanner**, è possibile utilizzare la fotocamera per ogni campo di input con modalità di input preferito impostata su **Scansione**.

Per verificare se un campo di input deve essere sottoposto a scansione, nella pagina **Nomi campo per app magazzino** impostare **Modalità di input preferita** su **Scansione**. Quando questa opzione è selezionata, una fotocamera può essere utilizzata per la scansione nell'app per dispositivi mobili Gestione magazzino. Per ulteriori informazioni, vedi [Configurare i campi per l'app per dispositivi mobili Gestione magazzino](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Formati di codice a barre supportati

I formati di codice a barre più comuni sono supportati, inclusi Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A e i codici QR.

## <a name="navigation"></a>Navigazione

La pagina della fotocamera verrà avviata in ogni pagina in cui il campo di input ha **modalità di input preferita** impostata su *Scansione*. Nella pagina della fotocamera utilizza le seguenti opzioni per navigare:

- Seleziona il pulsante Indietro per tornare alla pagina **dei dettagli e delle attività**.
- Seleziona la matita nella pagina **dei dettagli delle attività** e passa alla finestra in cui è possibile immettere manualmente l'input.
- Seleziona la fotocamera nella pagina **dei dettagli e delle attività** per tornare alla pagina della fotocamera.

Nella pagina della fotocamera, quando selezioni il pulsante Fotocamera, questo appare inattivo durante il tentativo di identificare un codice a barre. Se un codice a barre non viene identificato entro 5 secondi, il processo si interrompe e il pulsante Fotocamera diventa nuovamente disponibile. Sarà quindi possibile provare ad eseguire di nuovo la scansione di un codice a barre.

Quando si punta la fotocamera su un codice a barre, mantenere il codice a barre allineato alle parentesi per ottenere il miglior risultato. Se la scansione di un codice a barre viene effettuata correttamente, il risultato verrà elaborato e si verrà indirizzati al passaggio successivo. Se il passaggio successivo contiene un altro campo di input con la modalità di input preferita impostata su Scansione, la pagina della fotocamera verrà riavviata. Se il passaggio successivo non contiene un campo di scansione, la pagina della fotocamera non verrà avviata.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]