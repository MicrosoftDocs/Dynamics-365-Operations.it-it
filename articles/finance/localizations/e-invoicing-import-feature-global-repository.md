---
title: Importare funzionalità dal repository globale
description: Questo argomento spiega come importare le funzionalità di globalizzazione dal repository globale.
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ff3019986d089a286f7aef94346398b3d328ad54
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371630"
---
# <a name="import-features-from-the-global-repository"></a>Importare funzionalità dal repository globale

[!include [banner](../includes/banner.md)]

Il repository globale contiene funzionalità di fatturazione elettronica condivise con il provider di configurazione. Tutte le funzionalità di fatturazione elettronica fornite da Microsoft sono condivise con tutte le società. Hai automaticamente accesso a tutte le funzionalità di fatturazione elettronica che Microsoft rilascia e pubblica nel repository globale.

Per iniziare a lavorare con le funzionalità di fatturazione elettronica condivise con il tuo provider di configurazione, importale nella tua istanza di Regulatory Configuration Service (RCS) dal repository globale. Quindi rivedi i dettagli delle funzionalità, come le configurazioni di Creazione di report elettronici (ER) e le pipeline di elaborazione.

## <a name="import-a-feature-from-the-global-repository"></a>Importare una funzionalità dal repository globale

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Selezionare **Importa** per aprire la ricerca **Importa funzionalità da repository globale**.
4. Per esplorare le funzionalità di fatturazione elettronica disponibili nel repository globale per un provider di configurazione specifico, sincronizza l'istanza RCS della tua organizzazione selezionando **Sincronizza**. Al termine della sincronizzazione, l'elenco delle funzioni di fatturazione elettronica disponibili viene aggiornato dal repository globale. L'aggiornamento può richiedere alcuni minuti.
5. Seleziona la funzionalità da importare, quindi seleziona **Importa**.

Per visualizzare la funzionalità di fatturazione elettronica importata, verifica che sia selezionato il provider di configurezioni corretto. Per impostazione predefinita, le funzionalità create dal provider di configurazione attivo vengono automaticamente filtrate. È possibile regolare il filtro per visualizzare le funzionalità create da altri provider, ad esempio il provider di configurazione Microsoft.

Ora puoi lavorare con la funzionalità importata. Puoi esaminarne i dettagli e creare una nuova funzionalità utilizzando la funzionalità importata come modello.

> [!NOTE]
> Puoi modificare una funzionalità solo se è stata creata dal provider di configurazione attualmente attivo. Puoi creare una nuova funzionalità utilizzando la funzionalità originale come base. Puoi quindi apportare le modifiche richieste o configurare i parametri.

Quando Microsoft o un'altra azienda che condivide le funzionalità di globalizzazione con la tua azienda aggiorna le funzionalità che hai importato, puoi verificare la presenza di versioni aggiornate selezionando **Controlla gli aggiornamenti delle funzionalità** nella sezione **Impostazioni correlate** dell'area di lavoro **Funzionalità di globalizzazione**.

Se vedi che ci sono aggiornamenti per una funzionalità che usi come modello, puoi importare una nuova versione dopo aver sincronizzato l'elenco delle funzionalità pubblicate nel repository globale.
