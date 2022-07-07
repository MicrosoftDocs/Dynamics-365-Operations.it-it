---
title: Cespiti in prestito
description: In questo articolo viene descritta la procedura per la registrazione dei cespiti in prestito in Gestione cespiti.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f70b29ef69b80160f108e6f53edda12b86c2c9db
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015756"
---
# <a name="asset-loans"></a>Cespiti in prestito

[!include [banner](../../includes/banner.md)]

 

Se la società riceve cespiti per i processi di manutenzione o di riparazione da ubicazioni interne o dai clienti e presta temporaneamente cespiti a tali ubicazioni o clienti, Gestione cespiti può tenere traccia dei cespiti in prestito.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Registrare cespiti in prestito in una richiesta di intervento di manutenzione

1. Seleziona **Gestione cespiti** \> **Richieste di intervento di manutenzione** \> **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.
2. Selezionare la richiesta di intervento di manutenzione in cui registrare un cespite in prestito e selezionare **Modifica**.
3. Nella pagina **Richiesta**, selezionare **Invia cespite in prestito**.
4. Selezionare il cespite e immettere la data di restituzione prevista.
5. Selezionare **OK**.

> [!NOTE]
> - È possibile inviare un cespite in prestito solo se un cespite dello stesso tipo del cespite è disponibile.
> - Cespite prestato deve avere uno stato del ciclo di vita del cespite che ne consenta l'uso come cespite in prestito, ad esempio **InStorage**. Quando il cespite in prestito viene registrato, lo stato del ciclo di vita del cespite viene aggiornato automaticamente in, ad esempio, **OnLoan**.

Per visualizzare un elenco di tutti i cespiti pestati ad altre ubicazioni o clienti, seleziona **Gestione cespiti** \> **Cespite in prestito** \> **Tutti i cespiti in prestito**. Se la casella di controllo **Finito** è selezionata per un cespite, il cespite è stato registrato come restituito alla società.

![Gestire le richieste di manutenzione.](media/06-manage-maintenance-requests.png)

Nella pagina **Prestiti attivi cespiti**, è possibile visualizzare un elenco di tutti i cespiti in prestito che non sono stati restituiti alla società.

## <a name="register-loan-assets-as-returned"></a>Registrare cespiti in prestito come restituiti

1. Seleziona **Gestione cespiti** \> **Cespite in prestito** \> **Prestiti attivi cespiti**.
2. Selezionare il cespite in prestito da registrare come restituito e selezionare **Restituisci cespite in prestito**.
3. Nel campo **Restituito** immettere la data e l'ora.
4. Selezionare **OK**.
5. Aggiornare la pagina elenco **Prestiti attivi cespiti** e osservare che il cespite in prestito non è più presente nell'elenco.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]