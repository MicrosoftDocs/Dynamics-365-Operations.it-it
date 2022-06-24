---
title: Utilizzare le configurazioni
description: In questo articolo viene fornita una panoramica dello scenario principale per l'utilizzo delle configurazioni di reporting elettronico (ER) dall'area di lavoro Funzionalità di globalizzazione.
author: dkalyuzh
ms.date: 01/26/2022
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
ms.openlocfilehash: 359f00336811efd5f21463a325627df0e01a5f3a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875944"
---
# <a name="work-with-configurations"></a>Utilizzare le configurazioni

[!include [banner](../includes/banner.md)]

Le configurazioni di reporting elettronico (ER) sono uno dei principali insiemi di componenti delle funzionalità di fatturazione elettronica. Una configurazione ER contiene l'impostazione della struttura del file e un insieme di regole di trasformazione per trasformare i dati in due modi:

- **Esporta configurazione formato ER** – Questa configurazione trasforma i dati dalla struttura interna unificata (modello ER) al formato di file elettronico.
- **Importa configurazione formato ER** – Questa configurazione trasforma i dati dal formato di file elettronico alla struttura interna unificata (modello ER).

Oltre a generare file elettronici in uscita nel formato predefinito, le configurazioni ER sono ampiamente utilizzate per analizzare i messaggi in arrivo da servizi Web esterni come risposte. Questa funzionalità consente di creare una logica configurabile per ottenere i risultati della comunicazione con i canali esterni, convertire tali risultati (codici, messaggi e registri) nella struttura leggibile dall'utente e quindi passare tali informazioni all'applicazione client.

Per iniziare a utilizzare le configurazioni ER nella tua funzione di fatturazione elettronica, devi collegarle alla funzione e renderle disponibili nella scheda **Configurazioni** per la versione della funzione corrente. È possibile lavorare con una configurazione ER collegata selezionando **Aggiungi**, **Elimina**, **Modifica** o **Visualizza**.

Prima di poter aggiungere un collegamento a una configurazione ER, la configurazione deve esistere nel repository di Regulatory Configuration Service (RCS). Per rivedere le configurazioni ER disponibili nel tuo repository RCS, segui questi passaggi.

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.

Per informazioni su come creare una nuova configurazione ER o importare una configurazione ER esistente dal repository globale, vedi [Creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Per regolare una configurazione ER collegata, selezionare **Modifica** nella scheda **Configurazioni** per la funzionalità di fatturazione elettronica corrente. Il sistema crea automaticamente una versione della configurazione ER. Se la versione corrente non è stata creata dal provider di configurazione attivo, il sistema crea una versione derivata che utilizza il provider di configurazione. Se la versione corrente è stata creata dal provider di configurazione attivo, il sistema crea una nuova versione. In entrambi i casi è possibile modificare la versione creata e quindi eseguire automaticamente tutti gli aggiornamenti richiesti.
