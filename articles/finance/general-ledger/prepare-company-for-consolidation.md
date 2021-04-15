---
title: Preparare una persona giuridica per il processo di consolidamento
description: Durante un consolidamento le transazioni di alcuni set di conti di persone giuridiche vengono raccolte in un unico set di conti. In questo argomento viene illustrato come preparare una persona giuridica per un consolidamento.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 6f718bef3b1b07d3bb03dbf6acbf1cdf58aa7b8a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815478"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Preparare una persona giuridica per il processo di consolidamento

[!include [banner](../includes/banner.md)]

Durante un consolidamento le transazioni di alcuni set di conti di persone giuridiche vengono raccolte in un unico set di conti. In questo argomento viene illustrato come preparare una persona giuridica per un consolidamento.

> [!NOTE]
> Ti consigliamo di utilizzare Management Reporter per Microsoft Dynamics 365 Finance per combinare i risultati finanziari per più persone giuridiche in un formato consolidato. Management Reporter ti consente di creare report finanziari consolidati tra persone giuridiche, utilizzare Excel per importare dati di consolidamento da altre origini e convertire gli importi in un numero qualsiasi di valute di reporting senza dover eseguire il processo di consolidamento in Dynamics 365 Finance.

Puoi stampare report, ad esempio rendiconti finanziari, dalla persona giuridica consolidata. Tuttavia, non è possibile utilizzare la persona giuridica consolidata per le transazioni giornaliere.

Puoi consolidare i dati delle persone giuridiche che utilizzano database diversi da quello della persona giuridica consolidata. Questo processo di consolidamento è denominato *consolidamento di importazione*. In alternativa, le persone giuridiche possono utilizzare lo stesso database della persona giuridica consolidata. Questo processo di consolidamento è denominato *consolidamento online*.

La persona giuridica consolidata raccoglie i risultati e i saldi delle filiali. Per preparare una persona giuridica consolidata per un consolidamento, è necessario completare i seguenti passaggi.

1. Vai a **Contabilità generale \> Impostazione \> Organizzazione \> Persone giuridiche**.
2. Seleziona **Nuovo** per creare una nuova persona giuridica che sarà la persona giuridica consolidata.
3. Seleziona la casella di controllo **Utilizza per processo di consolidamento finanziario** quindi immetti le informazioni sulla persona giuridica consolidata. Assicurati di immettere le informazioni esattamente come vuoi che vengano riportate nei rendiconti finanziari per la persona giuridica consolidata.
4. Chiudere la pagina.
5. Seleziona la persona giuridica consolidata nel campo nell'angolo in alto a destra della pagina, quindi seleziona **OK**.
6. Vai a **Contabilità generale \> Impostazione \> Contabilità generale**.
7. Seleziona il piano dei conti, il calendario fiscale, la valuta di contabilizzazione, la valuta di dichiarazione facoltativa e il tipo di tasso di cambio predefinito per la persona giuridica consolidata. 
8. Vai a **Contabilità generale \> Impostazione \> Valuta \> Tassi di cambio valutario**.
9. Imposta i tassi di cambio valutario in periodi appropriati per le valute delle persone giuridiche affiliate.
10. Chiudere la pagina.
11. Se la persona giuridica consolidata ha filiali che utilizzano valute estere, segui questi passaggi:

    1. Vai a **Contabilità generale \> Impostazione \> Registrazione \> Conti per transazioni automatiche**.
    2. Nel campo **Tipo di registrazione** seleziona un conto appropriato:

        - Se la persona giuridica ha filiali estere che sono finanziariamente o operativamente interdipendenti con la persona giuridica madre, seleziona un conto appropriato per il tipo di registrazione **Conto profitti e perdite per differenze di consolidamento**.
        - Se stai consolidando una filiale che è finanziariamente e funzionalmente indipendente dalla persona giuridica padre o una persona giuridica che contiene i risultati di più società affiliate finanziariamente e funzionalmente indipendente dalla persona giuridica padre e se usi i metodi di conversione per consolidare i dati, seleziona un conto appropriato per il tipo di registrazione **Conto collettivo per differenze di consolidamento**.

    3. Nel campo **Conto principale** seleziona i conti principali che devono essere utilizzati per le rettifiche di rivalutazione valuta estera.
    4. Chiudere la pagina.

    Se crei la persona giuridica consolidata nella parte iniziale di un periodo, puoi rivalutare gli importi in valuta estera conformemente alla modifica dei tassi di cambio durante il periodo di consolidamento.

La persona giuridica consolidata ora è impostata per il processo periodico **Consolidamento**. È possibile eseguire un consolidamento dell'importazione o un consolidamento online.

- Per eseguire un consolidamento dell'importazione, vai a **Contabilità generale \> Periodico \> Consolida \> Consolida \[Importa da\]**.
- Per eseguire un consolidamento online, vai a **Contabilità generale \> Periodico \> Consolida \> Consolida \[Online\]**.

> [!NOTE]
> Prima di eseguire il consolidamento, devi preparare le persone giuridiche affiliate per il consolidamento. Per ulteriori informazioni, vedi [Impostare una persona giuridica affiliata per il consolidamento](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]