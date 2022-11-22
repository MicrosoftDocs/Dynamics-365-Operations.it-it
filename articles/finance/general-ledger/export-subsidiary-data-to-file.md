---
title: Esportare i dati delle filiali in file
description: Questo articolo spiega come prepararsi all'esportazione di dati da Microsoft Dynamics 365 Finance e quindi importarli in una persona giuridica consolidata.
author: jinniew
ms.date: 11/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 30d69f9a2813621df410a29568644f264392fb49
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779963"
---
# <a name="export-subsidiary-data-to-files"></a>Esportare i dati delle filiali in file

[!include [banner](../includes/banner.md)]

Usi la pagina **Esporta** (**Amministrazione di sistema \> Aree di lavoro \> Importa/Esporta**) per prepararsi a esportare i dati delle filiali in file che possono poi essere importati in una persona giuridica consolidata. Per ulteriori informazioni sui processi di importazione ed esportazione vedi [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Crea una persona giuridica per il processo di consolidamento. Per ulteriori informazioni su come creare persone giuridiche, vedi [Creare una persona giuridica](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Per ulteriori informazioni, vedi [Preparare una persona giuridica da utilizzare nel processo di consolidamento](prepare-company-for-consolidation.md) e [Impostare una persona giuridica affiliata per il consolidamento](set-up-subsidiary-company-for-consolidation.md). 

2. Vai a **Consolidamenti \> Esporta saldi aziendali**. Nella pagina **Esporta saldi aziendali** nella scheda **Criteri** specifica i dettagli del consolidamento impostando i seguenti campi.

    | Campo                             | Descrizione |
    |-----------------------------------|-------|
    | **Conto principale**                      | Specifica i conti da consolidare. Per includere tutti i conti lascia vuoto questo campo. |
    | **Utilizza conto di consolidamento**         | Se hai specificato conti di consolidamento, imposta questa opzione su **Sì**. |
    | **Selezionare il conto di consolidamento di origine** | Seleziona **Conto principale** o **Gruppo di conti di consolidamento**. |
    | **Gruppo di conti di consolidamento**       | Selezionare un gruppo di conti di consolidamento per il conto di consolidamento selezionato. |
    | **Periodo di consolidamento**              | Specifica le date "da" e "a" per il consolidamento. |
    | **Includi importi effettivi**            | Imposta questa opzione su **Sì** per includere gli importi effettivi. |
    | **Includi importi di budget**            | Imposta questa opzione su **Sì** per includere gli importi di budget in consolidamento. |
    | **Modelli di budget**                     | Specifica il modello di budget da includere. |

3. Nella scheda **Dimensioni finanziarie** specifica i dettagli del consolidamento:

    - Specifica le informazioni sulle dimensioni finanziarie che devono essere trasferite dalle transazioni nei conti delle società affiliate alle transazioni della persona giuridica consolidata.
    - Seleziona le dimensioni finanziarie nell'elenco.
    - Identifica la specifica corretta per ciascuna dimensione finanziaria consolidata. Le opzioni disponibili includono **Dimensione**, **Dimensione gruppo**, **Conti aziendali** e **Conto**.

        > [!NOTE]
        > L'opzione **Dimensione gruppo** consente di definire il valore della dimensione utilizzato dal gruppo di società che si sta consolidando.

    - Specifica l'ordine dei segmenti da consolidare.

4. Nella scheda **Persone giuridiche** segui questi passaggi per specificare la persona giuridica che stai esportando:

    1. Selezionare **Nuovo**.
    2. Nel campo **Persona giuridica di origine** immetti la persona giuridica.

        Se gli stessi criteri sono applicabili a più affiliate nello stesso database, sarà possibile trasferire i dati di queste ultime dallo stesso database a file di esportazione distinti in un'unica operazione:

        1. Crea una riga per ogni persona giuridica affiliata i cui conti devono essere esportati in file. Questi ultimi verranno in seguito importati nella persona giuridica consolidata.
        2. Per ogni società affiliata, immettere il nome della società stessa e il nome del file di esportazione che verrà creato durante il processo di esportazione.

    3. Nel campo **Tipo di conto di differenze di conversione** seleziona **Profitti e perdite** o **Stato patrimoniale**.
    4. Immetti un nome file per il file di esportazione che verrà creato.

5. Seleziona **OK** per eseguire l'esportazione.

Al termine dell'esportazione, verrà visualizzato un messaggio con il numero di record salvati in ogni file. È quindi possibile importare i file nella persona giuridica consolidata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
