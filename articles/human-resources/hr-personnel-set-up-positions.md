---
title: Impostare le posizioni
description: Questo argomento descrive le posizioni come un elemento importante del livello inferiore di una gerarchia organizzativa.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmWorkforceWorkspace, HcmWorkerActivityChart, HcmAllWorkersListPart, HcmPosition, HcmPositionNewPosition, HcmJobLookup, HcmPositionReportsToDialog, HcmPositionLookup, FinancialDimensionDefaultTemplatesLookup, DimensionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9121df9571b037478fb901cb6ac9f3298177548a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694797"
---
# <a name="set-up-positions"></a>Impostare le posizioni


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Le posizioni sono un elemento importante del livello inferiore di una gerarchia organizzativa. Una posizione è una singola istanza di un processo. Ad esempio, la posizione "Manager vendite (Est") è una delle posizioni associate alla mansione "Manager vendite". Una posizione esiste in un reparto e può avere associato solo un lavoratore. In questa attività eseguiremo i passaggi necessari per creare una posizione. Questa procedura è destinata agli specialisti delle risorse umane.

1. Seleziona **Gestione forza lavoro**.
2. Seleziona **Posizioni aperte**.
3. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
4. Nel campo **Mansione** immettere o selezionare un valore.

    I campi **Descrizione mansione**, **Titolo** e **Fattore di impiego equivalente al tempo pieno** verranno automaticamente copiati dalla mansione selezionata alla posizione.

5. Seleziona **Crea posizione**.
6. Nel campo **Reparto** immettere o selezionare un valore.
7. Nel campo **Tipo di posizione** immettere o selezionare un valore.
8. Nel campo **Retribuzione** immettere o selezionare un valore.

    Il campo **Paese di retribuzione** determina le regole di idoneità di retribuzione e i budget per incentivi fissi applicabili a un dipendente in quella posizione.

9. Nel campo **Disponibile per l'assegnazione** immettere una data e un'ora.
10. Espandere la sezione **Durata posizione**.

    La durata della posizione viene immessa per impostazione predefinita in base alle date di attivazione e pensionamento immesse in precedenza.

11. Espandere la sezione **Subordinato a**.

    Quando si assegna un lavoratore a una posizione che riporta a un'altra posizione, viene creata una relazione gerarchica diretta tra i lavoratori assegnati alle due posizioni.

12. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.
13. Nel campo **Subordinato a** immettere o selezionare un valore.
14. Selezionare **Crea**.
15. Espandere la sezione **Assegnazione lavoratore**.
16. Espandere la sezione **Relazioni**.

    Se l'organizzazione utilizza una gerarchia a matrice o un'altra gerarchia personalizzata, è possibile impostare i tipi di gerarchia delle posizioni e aggiungere le relazioni gerarchiche alle posizioni per ogni tipo di gerarchia impostata.

17. Seleziona **Aggiungi**.
18. Nell'elenco contrassegnare la riga selezionata.
19. Nel campo **Nome gerarchia** immettere o selezionare un valore.
20. Nel campo **Subordinato a** immettere o selezionare un valore.
21. Espandere la sezione **Retribuzioni**.
22. Nel campo **Ciclo retributivo** immettere o selezionare un valore.
23. Nel campo **Pagato da** immettere o selezionare un valore.
24. Nel campo **Ore regolari annuali** immettere un numero.

    Il valore immesso è il numero di ore pagate regolarmente che il lavoratore in questa posizione dovrà lavorare ogni anno.

25. Espandere la sezione **Sindacato**.
26. Comprimere la sezione **Sindacato**.
27. Espandere la sezione **Dimensioni finanziarie**.
28. Nel campo **Modello di distribuzione** immettere o selezionare un valore.
29. Nel campo **Reparto** immettere o selezionare un valore.
30. Seleziona **Salva**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
