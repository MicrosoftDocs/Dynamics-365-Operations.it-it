---
title: Impostare le risorse del progetto
description: Questo argomento fornisce informazioni sulla configurazione o sulla richiesta delle risorse di progetto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760588"
---
# <a name="set-up-project-resources"></a>Impostare le risorse del progetto

[!include [banner](../includes/banner.md)]

È necessario impostare un calendario e associarlo a un dipendente o un lavoratore. Il calendario viene utilizzato per programmare il progetto e l'orario di lavoro delle risorse per esso prenotate. Durante l'impostazione del calendario, i manager di progetto possono eseguire il livellamento delle risorse nell'ambito della relativa ottimizzazione. In base alla programmazione del calendario, è possibile porre restrizioni sulle risorse. È possibile impostare un calendario nella pagina **calendari**.

Quando si imposta un lavoratore come risorsa di progetto, è possibile selezionare uno dei lavoratori che lavorano nella società per il quale si desidera impostare le risorse. In alternativa, è possibile selezionare i lavoratori da altre società della propria organizzazione. Questi lavoratori sono noti come risorse interaziendali.

Nelle procedure indicate di seguito viene descritto come impostare un lavoratore come risorsa di progetto nella società e come impostare una risorsa di progetto interaziendale.

## <a name="set-up-a-worker-as-a-project-resource"></a>Impostare un lavoratore come risorsa del progetto

1. Nella pagina **Lavoratori**, in **Lavoratori** selezionare il lavoratore che si intende aggiungere come risorsa del progetto e aprire il relativo record.
2. Nel Riquadro azioni, selezionare **Progetto** &gt; **Impostazioni** &gt; **Impostazione progetto**.
3. Selezionare un calendario, quindi chiudere la pagina.

È anche possibile specificare progetti predefiniti per una risorsa come tipo di pre-assegnazione. Le pre-assegnazioni possono essere utilizzate quando il manager di risorse o progetto sa in anticipo su quali progetti la risorsa lavorerà. Le pre-assegnazioni possono anche essere basate sulla richiesta di uno sponsor o di un cliente del progetto. Per pre-assegnare un progetto, nella pagina **Assegna progetti**, scheda **Progetti**, elenco **Progetti rimanenti**, selezionare il progetto appropriato.

## <a name="set-up-an-intercompany-resource"></a>Impostare una risorsa interaziendale

Quando si imposta un lavoratore come risorsa interaziendale, è necessario completare l'impostazione nella società che concede in prestito la risorsa e nella società che la prende in prestito.

### <a name="in-the-lending-company"></a>Nella società che concede in prestito la risorsa

1. In Finance, verificare che la società di concessione sia selezionata e quindi completare la procedura nella sezione precedente, "Impostare un lavoratore come risorsa del progetto".
2. Nella pagina **Contabilità interaziendale**, selezionare **Nuovo**.
3. Nel campo **ID persona giuridica** selezionare la società di concessione. Completare i campi rimanenti come appropriati e selezionare **Salva**.
4. Nella pagina **Prezzo di trasferimento**, selezionare **Nuovo**.
5. Nel campo **Persona giuridica richiedente** selezionare la società appropriata.
6. Per concedere alla società richiedente solo la risorsa creata all'inizio di questa sezione nel campo **Risorsa**, selezionare il nome della risorsa creata. Per redenre disponibili tutte le risorse nella società di concessione alla società richiedente, lasciare vuoto il campo **Risorsa**.
7. Nella pagina **Parametri Gestione progetti e contabilità**, nella scheda **Interaziendale**, impostare il campo **Abilita programmazione risorse interaziendale e fogli presenze** su **Sì**.

### <a name="in-the-borrowing-company"></a>Nella società che prende in prestito la risorsa

- Nella pagina **Elenco risorse**, nel filtro di ricerca, immettere il nome della risorsa creata nella procedura precedente per la società di concessione per verificare che il nome sia incluso nell'elenco di risorse per la società di prestito.

## <a name="request-project-resources"></a>Richiedere risorse di progetto
La funzionalità per la programmazione di risorse di progetto consente solo ai manager di risorse di distribuire risorse con personale per gli impegni o progetti. Per attivare questa funzionalità, è necessario completare le seguenti attività o verificare che siano state completate:

- Consente di impostare sequenze numeriche.
- Impostare i flussi di lavoro di Gestione progetti e contabilità.
- Abilitare i flussi di lavoro della richiesta di risorse.

Una volta completate le attività precedenti, è possibile completare le seguenti attività come necessario:

- Creare una richiesta di risorse da una risorsa con personale e prenotazione preliminare.
- Monitorare le richieste risorsa.
- Completare le richieste risorsa.
- Richiedere una risorsa con personale da un WBS.
- Prenotare le risorse per un progetto senza avere una richiesta per una risorsa con personale.
