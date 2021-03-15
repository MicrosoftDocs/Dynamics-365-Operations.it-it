---
title: Importare dati delle società affiliate da file
description: Questo argomento spiega come preparare i dati da sistemi esterni in modo che possano essere importati in Microsoft Dynamics 365 Finance.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 7ced1b970aefa20a27ab16e005dff8fabace78d1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988827"
---
# <a name="import-subsidiary-data-from-files"></a>Importare dati delle società affiliate da file

[!include [banner](../includes/banner.md)]

Questo argomento spiega come preparare i dati da sistemi esterni in modo che possano essere importati in Microsoft Dynamics 365 Finance. Usa la pagina **Consolida con importazione** (**Consolidamenti \> Consolida con importazione**) per preparare il trasferimento dei dati delle società affiliate da sistemi esterni.

1. Crea una persona giuridica affiliata per il consolidamento. Per ulteriori informazioni su come creare persone giuridiche, vedi [Creare una persona giuridica](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Per ulteriori informazioni, vedi [Preparare una persona giuridica da utilizzare nel processo di consolidamento](prepare-company-for-consolidation.md) e [Impostare una persona giuridica affiliata per il consolidamento](set-up-subsidiary-company-for-consolidation.md).

2. Preparare un file che conterrà i dati importati. Per ulteriori informazioni sul processo di importazione, vedi [Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Esportare i dati in un file seguendo i passaggi della procedura "Processo di importazione/esportazione di dati" in [Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Puoi utilizzare tale procedura per consolidare i dati da un'altra istanza di Dynamics 365 Finance o da Dynamics 365 Business Central. Se stai importando dati da sistemi esterni, i dati devono essere nel formato descritto in [Esportare i dati delle filiali in file](export-subsidiary-data-to-file.md).
4. Vai a **Consolidamenti \> Consolida con importazione**. Nella pagina **Consolida con importazione** nella scheda **Criteri** specifica i dettagli del report e/o eseguire l'importazione impostando i seguenti campi.

    | Campo                                 | Valore per il report | Valore per l'importazione |
    |---------------------------------------|----------------------|----------------------|
    | descrizione                           | Non applicabile | Immettere una descrizione per identificare l'importazione. |
    | Conto principale                          | Definisci l'intervallo di account che il rapporto deve includere. Se non si definisce un intervallo, verranno inclusi tutti gli account. | Definisci l'intervallo di account che l'importazione deve includere. Se non si definisce un intervallo, verranno inclusi tutti gli account. |
    | Periodo di consolidamento                  | Definisci l'intervallo di date da consolidare. | Definisci l'intervallo di date da consolidare. |
    | Includi importi effettivi                | Imposta questa opzione su **Sì** per includere gli importi effettivi. | Imposta questa opzione su **Sì** per includere gli importi effettivi. |
    | Includi importi di budget                | Imposta questa opzione su **Sì** per includere gli importi di budget in consolidamento. | Imposta questa opzione su **Sì** per includere gli importi di budget in consolidamento. |
    | Ricostruire i saldi durante il consolidamento | Imposta questa opzione su **Sì** se il processo di ricostruzione dovrebbe cancellare completamente il saldo e nuovi record e ricreare il saldo. | Imposta questa opzione su **Sì** se il processo di ricostruzione dovrebbe cancellare completamente il saldo e nuovi record e ricreare il saldo. |
    | Modelli di budget                         | Non applicabile | Se hai scelto di importare gli importi del budget, immetti i modelli di budget da consolidare. |
    | Tipo di tasso del budget                      | Non applicabile | Immetti il tipo di tasso di cambio del budget. |

6. Se hai diverse valute contabili, utilizza i campi nella scheda **Conversione valuta** per configurare la traduzione eseguita durante il consolidamento.

    | Campo                      | descrizione |
    |----------------------------|-------------|
    | Persona giuridica di origine        | Seleziona la persona giuridica da cui stai eseguendo l'importazione. |
    | Valuta di contabilizzazione di origine | Questa valuta predefinita è la valuta associata alla persona giuridica di origine selezionata nel campo **Persona giuridica di origine**. |
    | Conti Da e A       | Definire l'intervallo di conti da importare dalla persona giuridica di origine. |
    | Tipo di tasso di cambio         | Seleziona il tipo di tasso di cambio. I tipi di tasso di cambio vengono assegnati quando crei un conto principale. Per ulteriori informazioni, vedere [Creare un conto principale](tasks/create-main-account.md). |
    | Applica tasso di cambio da   | Immetti una data per applicare il tasso di cambio in vigore in quella data. In alternativa, inserisci il valore da utilizzare come tasso di cambio. |
    | Tasso di cambio              | Il tasso di cambio dipende dal tipo di tasso di cambio selezionato nel campo **Tipo di tasso di cambio**. Se hai inserito un tasso di cambio definito dall'utente, puoi definire un tasso. |

7. Imposta l'opzione **Esegui in background** su **Sì** per abilitare l'esecuzione in background del processo di importazione.
8. Imposta l'opzione **Elaborazione batch** su **Sì** per eseguire il consolidamento come processo batch in un momento specifico. Per eseguire immediatamente il consolidamento, seleziona **OK**. 

Le transazioni e i saldi specificati per il consolidamento nelle affiliate verranno aggiunti ai conti appropriati della persona giuridica consolidata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]