---
title: Creare e inviare un flusso di lavoro budget di progetto
description: In questa procedura viene illustrato come creare e inviare il budget per un progetto.
author: Henrikan
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f410d824be717537e6dfb5dbd8b71ff7d992e0a
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860411"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>Creare e inviare un flusso di lavoro budget di progetto

[!include [banner](../../includes/banner.md)]

Quando si crea un budget del progetto è possibile immettere i costi e i ricavi stimati per un progetto e utilizzare i valori per controllare le transazioni di progetto effettive. I budget di progetto richiedono che tutti i budget e le revisioni originali devono essere inviati al flusso di lavoro del progetto per l'approvazione. Il flusso di lavoro consente un controllo maggiore sul processo di budget e crea un record di storico modifiche. Dopo avere creato [un progettot](/dynamicsax-2012/appuser-itpro/create-a-project) usa questa procedura per creare e inviare il budget.

1. Vai a **Moduli** > **Gestione progetti e contabilità** > **Progetti** > **Tutti i progetti**.
1. Seleziona il progetto dall'elenco.
1. Nella pagina dei dettagli del progetto, seleziona la scheda **Piano**.
1. Sotto il gruppo **Budget** seleziona **Budget di progetto**.
1. Nella scheda dettaglio **Generale** immettere le seguenti informazioni:
   - Digitare un valore nella casella **Descrizione**.
   - Seleziona l'opzione per **Budget originale**.
   - Seleziona l'opzione per **Budget rimanente**.
1. Espandi la scheda dettaglio **Costi** e seleziona **Nuovo**. Quindi effettua le seguenti impostazioni:
   - Seleziona un'opzione per **Tipo di transazione**.
   - Seleziona una **Categoria** appropriata.
   - Inserisci un valore in **Budget originale**.
1. Espandi la scheda dettaglio **Ricavi** e seleziona **Nuovo**. Quindi effettua le seguenti impostazioni:
   - Seleziona un'opzione per **Tipo di transazione**.
   - Seleziona una **Categoria**.
   - Inserisci un valore per **Budget originale**.
1. Seleziona **Salva**.
1. Seleziona **Flusso di lavoro \> Invia**.
1. Nella pagina **Rivedi il flusso di lavoro del budget originale - Invia**, inserisci un **Commento** e seleziona **Invia**.
