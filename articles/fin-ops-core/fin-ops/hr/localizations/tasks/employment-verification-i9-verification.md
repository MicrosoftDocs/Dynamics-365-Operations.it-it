---
title: Verifica impiego verifica i9
description: In conformità con l'Immigration Reform and Control Act, i datori di lavoro negli Stati Uniti sono tenuti a verificare l'idoneità all'impiego dei nuovi dipendenti assunti.
author: ShielaSogge
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, HcmPersonIdentificationNumber, Hcmi9Document
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea77f112413a5b7d5c96768ad46fdb361023bd84
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964885"
---
# <a name="employment-verification-i9-verification"></a>Verifica impiego verifica i9

[!include [banner](../../../includes/banner.md)]

In conformità con l'Immigration Reform and Control Act, i datori di lavoro negli Stati Uniti sono tenuti a verificare l'idoneità all'impiego dei nuovi dipendenti assunti. Questa procedura descrive i passaggi per la registrazione dei documenti necessari per la verifica I-9. Per questa procedura, utilizzare la società dimostrativa USMF.

1. Vai a **Risorse umane \> Lavoratori \> Dipendenti**.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applica un filtro al campo **Nome** in base al valore **Vince**.
3. Selezionare il dipendente. Ad esempio, seleziona **Vince Prado**.
4. Seleziona la scheda dettaglio **Informazioni personali**.
5. Seleziona **Numeri di identificazione**.
6. Selezionare **Nuovo**.
7. Seleziona il tipo di identificazione per la registrazione. Seleziona, ad esempio, **Passaporto**.
8. Nel campo **Numero**, immetti un valore.
9. Seleziona **Sì** nel campo **Principale**.
10. Nel campo **Descrizione** immetti una breve descrizione del record di identificazione.
11. Nel campo **Agenzia emittente** seleziona l'agenzia che ha emesso il documento di identificazione del lavoratore. Seleziona, ad esempio, **Governo**.
12. Immetti a data in cui l'agenzia ha rilasciato il documento di identificazione al lavoratore. Ad esempio, immetti la data **15-02-2011** (15 febbraio 2011).
13. Immettere la data di scadenza del documento d'identificazione. Ad esempio, immetti la data **15-2-2021** (15 febbraio 2021).
14. Seleziona **Salva**.
15. Chiudi la pagina.
16. Seleziona la scheda **Impiego**.
17. Seleziona **I-9**.
18. Selezionare **Nuovo**.
19. Seleziona un'opzione nel campo **Idoneità al lavoro**.

    Se il dipendente non è un cittadino degli Stati Uniti, è inoltre necessario immettere l'identificativo estero o il numero di ingresso del lavoratore.

20. Seleziona l'opzione **GroupListA**.

    L'elenco selezionato dipende dal documento di identificazione che il lavoratore ha fornito. Un lavoratore deve fornire un documento dell'elenco A o un documento dell'elenco B e dell'elenco C. Ad esempio, se il lavoratore ha fornito un passaporto, è possibile selezionare l'elenco A. Tuttavia, se il lavoratore ha fornito solo una patente di guida e la carta della previdenza sociale, devi selezionare l'elenco B e l'elenco C.

21. Nel campo **Tipo di documento I-9** seleziona il tipo di documento fornito dal dipendente.
22. Nel campo **Numero documento** immetti o seleziona un valore.
23. Seleziona **Salva**.

[!INCLUDE[footer-include](../../../../../includes/footer-banner.md)]
