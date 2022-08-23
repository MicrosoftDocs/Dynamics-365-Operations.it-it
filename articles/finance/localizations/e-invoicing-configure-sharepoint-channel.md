---
title: Configurare un canale SharePoint
description: Questo articolo spiega come configurare un canale Microsoft SharePoint per elaborare fatture elettroniche in entrata.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 92eaa357c6d72cc637d4ce353702e5d41ecf4338
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272306"
---
# <a name="configure-a-sharepoint-channel"></a>Configurare un canale SharePoint

[!include [banner](../includes/banner.md)]

Come prerequisito per la configurazione di un canale Microsoft SharePoint per elaborare i documenti in arrivo, completa i passaggi descritti in [Configurare una connessione SharePoint](e-invoicing-create-sharepoint-connection.md).

È quindi possibile utilizzare il canale SharePoint per importare fatture fornitori elettroniche da file archiviati nelle cartelle di SharePoint.

1. Nel sito di SharePoint, crea le seguenti cartelle:

    - **Cartella principale** – La cartella da cui il servizio elaborerà i file.
    - **Cartella di archivio** – La cartella in cui verranno archiviati i file elaborati.
    - **Cartella di errore** – La cartella in cui il sistema sposterà i file se l'elaborazione non riesce.

2. In Regulatory Configuration Service (RCS), seleziona la funzionalità di fatturazione elettronica che hai creato. Assicurati di selezionare la versione con lo stato **Bozza**.
3. Nella scheda **Configurazioni** seleziona **Aggiungi**.
4. Nella finestra di dialogo a discesa **Crea configurazione funzionalità**, nel gruppo di campi **Nuovo**, selezionare l'opzione **Configurazione personalizzata**.
5. Nel gruppo di campi **Tipo di configurazione**, seleziona l'opzione **Canale dati**.
6. Nel campo **Seleziona canale dati**, seleziona **Cartella SharePoint**.
7. Selezionare **Crea**.
8. Seleziona la riga che hai creato e seleziona **Modifica**.
9. Nella scheda **Canale dati**, nella sezione **Parametri**, imposta i seguenti campi obbligatori.

    | Campo                 | Description |
    |-----------------------|-------------|
    | Canale dati          | Immetti un nome univoco per identificare il canale dati. Il nome può contenere un massimo di 10 caratteri. Verrà fatto riferimento nelle regole di applicabilità e nelle applicazioni connesse durante il processo di comunicazione. |
    | Indirizzo SharePoint    | Immetti l'URL di SharePoint. Ad esempio, immettere `<domain>.sharepoint.com`. |
    | ID applicazione        | Immetti il nome del segreto di Azure Key Vault che contiene l'ID dell'account utente SharePoint. Questo segreto deve essere creato in Key Vault e configurato nell'ambiente del servizio. Il valore è il valore **ID applicazione (client)** da [Configura connessione SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Segreto applicazione    | Immetti il nome del segreto Key Vault che contiene la password dell'account utente SharePoint. Il valore è il valore **Segreto registrazione app** da [Configura connessione SharePoint](e-invoicing-create-sharepoint-connection.md). |
    | Nome sito             | Immettere il nome del sito di SharePoint. |
    | Nome raccolta documenti | Immetti il nome della raccolta documenti di SharePoint. |
    | Timeout               | Immetti il tempo massimo, in millisecondi (ms), che il sistema deve attendere per una risposta. Il valore predefinito è pari a 10.000 ms (10 secondi). |
    | Cartella principale           | Specifica l'origine dell'importazione del file o la cartella da cui il servizio deve elaborare i file. |
    | Cartella di archiviazione        | Specifica la cartella in cui devono essere archiviati i file elaborati. |
    | Cartella di errore          | Specifica la cartella in cui il sistema deve spostare i file se l'elaborazione non riesce. |
    | Dimensioni massime file         | Immetti la dimensione massima, in byte, di un singolo file che viene elaborato. Il valore predefinito è 20.000,000 byte. |
    | Numero massimo di file      | Immetti il numero massimo di file da elaborare per una singola azione. Se non vuoi limitare il numero di file, imposta il valore su **0** (zero). |
    | Filtro file           | Immetti una stringa da filtrare per nome file. Questo campo è facoltativo. Una semplice maschera come **\*smth\*.est** è supportata, dove ogni asterisco (\*) rappresenta zero o più occorrenze di qualsiasi carattere. Ad esempio, inserisci **\*.pdf** per configurare il canale per la lettura dei file PDF. |
    | Nome file personalizzato      | Immetti il nome file personalizzato dal client. |

10. Nella scheda **Regole di applicabilità**, esaminare e aggiornare i criteri in base alle necessità. Il valore del campo **Canale** deve essere uguale al valore che hai inserito nel campo **Canale dati** nel passaggio precedente.
11. Selezionare **Salva**, quindi chiudere la pagina.
