---
title: Impostazione della previsione della domanda
description: "In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 974edd06460df4afe594b0a033a042b8c2763f7f
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="demand-forecasting-setup"></a>Impostazione della previsione della domanda

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda.  

Queste attività di configurazione comprendono l'impostazione dei dati e parametri indicati di seguito.

## <a name="item-allocation-key"></a>Chiave di allocazione articolo
Una previsione della domanda viene calcolata per un articolo e le relative dimensioni solo se l'articolo fa parte di una chiave di allocazione articolo. Questa regola viene applicata per raggruppare numerosi articoli, in modo da consentire una creazione più rapida delle previsioni della domanda. La percentuale della chiave di allocazione articolo viene ignorata quando vengono generate le previsioni della domanda. Le previsioni vengono create solo in base ai dati storici. 

Un articolo e le relative dimensioni devono essere parte solo di una chiave di allocazione articolo se la chiave di allocazione articolo viene utilizzata durante la creazione della previsione. 

Per aggiungere un'unità di stockkeeping (SKU) predefinita a una chiave di allocazione articolo, passare a **Pianificazione generale** &gt; **Impostazione** &gt; **Previsione della domanda** &gt; **Chiavi di allocazione articoli**. Utilizzare la pagina **Assegna articoli** per assegnare un articolo a una chiave di allocazione.

## <a name="intercompany-planning-groups"></a>Gruppi di pianificazione interaziendale
Le previsioni della domanda generano previsioni interaziendali. In Microsoft Dynamics 365 for Finance and Operations, le società pianificate insieme vengono raggruppate in un gruppo di pianificazione interaziendale. Per specificare, per ogni società, quale chiave di allocazione articolo utilizzare per la previsione della domanda, associare una chiave di allocazione articolo al membro del gruppo di pianificazione interaziendale tramite **Pianificazione generale** &gt; **Impostazioni** &gt; **Gruppi di pianificazione interaziendale**. 

Per impostazione predefinita, se nessuna chiave di allocazione articolo è assegnata ai membri del gruppo di pianificazione interaziendale, una previsione della domanda viene calcolata per tutti gli articoli assegnati a tutte le chiavi di allocazione articolo da tutte le società di Finance and Operations. Le opzioni aggiuntive di filtro per le società e le chiavi di allocazione articolo sono disponibili nella pagina **Genera previsione di base statistica**. 

Verificare il numero di articoli che vengono previsti. Gli articoli non necessari possono determinare un aumento nei costi quando si utilizza Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Parametri di previsione della domanda
Per impostare i parametri di previsione della domanda, andare a **Pianificazione generale** &gt; **Impostazioni** &gt; **Parametri di previsione della domanda**. Poiché le previsioni della domanda vengono eseguite a livello interaziendale, l'impostazione è globale. Ovvero l'impostazione si applica a tutte le società. 

La previsione della domanda genera la previsione in quantità. Di conseguenza, l'unità di misura in cui la quantità deve essere espressa deve essere specificata nel campo **Unità previsione domanda**. L'unità di misura deve essere univoca per garantire che l'aggregazione e la percentuale di distribuzione siano appropriate. Per ulteriori informazioni su aggregazione e percentuale di distribuzione, vedere [Effettuare correzioni manuali alla previsione di base](manual-adjustments-baseline-forecast.md). Per ciascuna unità di misura utilizzata per le SKU incluse nella previsione della domanda, assicurarsi che sia presente una regola di conversione per l'unità di misura e l'unità di misura della previsione generale. Durante la generazione della previsione, viene registrato l'elenco di articoli che non dispongono di una conversione dell'unità di misura, in modo da poter facilmente correggere l'impostazione. 

Le previsioni della domanda possono essere utilizzate per prevedere la domanda dipendente e indipendente. Ad esempio, se è selezionata solo la casella di controllo **Ordine cliente** e se tutti gli articoli che vengono considerati per la previsione della domanda sono articoli venduti, il sistema calcolerà la domanda indipendente. Tuttavia, i sottocomponenti critici possono essere aggiunti alle chiavi di allocazione articolo e inclusi nelle previsioni della domanda. In questo caso, se la casella di controllo **Riga produzione** è selezionata, viene calcolata una previsione dipendente. 

Sono disponibili due metodi per creare una previsione di base in Finance and Operations. È possibile utilizzare modelli di previsione con i dati storici oppure copiare semplicemente i dati storici nella previsione. Il campo **Strategia di generazione previsione** consente di selezionare uno dei due metodi. Per utilizzare i modelli previsionali, selezionare **Azure Machine Learning**. 

Facendo clic su **Dimensioni previsione** nel riquadro sinistro della pagina **Parametri di previsione della domanda**, è possibile selezionare il set di dimensioni di previsione da utilizzare quando la previsione della domanda viene generata. Una dimensione di previsione indica il livello di dettaglio per cui la previsione è definita. Società, sito e chiave di allocazione articolo sono dimensioni di previsione obbligatorie, ma è inoltre possibile generare le previsioni a livello di dimensioni di magazzino, stato inventario, gruppo clienti, conto cliente, paese/regione o stato e articolo oltre a tutti i livelli di dimensione articolo. 

In qualsiasi punto, è possibile aggiungere le dimensioni di previsione all'elenco delle dimensioni utilizzate per previsione della domanda. È anche possibile eliminare una dimensione previsione dall'elenco. Tuttavia, le correzioni manuali vengono perse se si aggiunge o rimuove una dimensione previsione. 

Non tutti gli articoli si comportano nello stesso modo da un punto di vista della previsione della domanda. Gli articoli simili possono essere raggruppati in una chiave di allocazione articolo e i parametri come tipi di transazione e impostazioni del metodo di previsione possono essere impostati per chiave di allocazione articolo. Fare clic su **Chiavi di allocazione articolo** nella pagina **Parametri di previsione della domanda** . 

Per generare la previsione, Finance and Operations utilizza un servizio Web di Machine Learning. Per connettersi al servizio, è necessario immettere le informazioni di Finance and Operations seguenti, se si accede a Microsoft Azure Machine Learning Studio:

-   Chiave dell'API del servizio Web
-   URL dell'endpoint del servizio Web
-   Nome account di archiviazione Azure
-   Chiave account di archiviazione Azure

**Nota:** il nome account e la chiave di archiviazione Azure sono necessari solo se si utilizza un account di archiviazione personalizzato. Se si distribuisce la versione locale, è necessario disporre di un account di archiviazione personalizzato in Azure, in modo che il servizio Machine Learning possa accedere ai dati storici. 

Per creare le previsioni della domanda, è possibile distribuire un servizio personalizzato tramite Machine Learning Studio o gli esperimenti di previsione della domanda di Finance and Operations. Le istruzioni per la distribuzione degli esperimenti di previsione della domanda di Finance and Operations come servizio Web sono disponibili in Finance and Operations. Nella pagina **Parametri di previsione della domanda** fare clic sulla scheda **Azure Machine Learning**.

## <a name="settings-for-the-finance-and-operations-demand-forecasting-machine-learning-service"></a>Impostazioni per il servizio di Machine Learning della previsione della domanda di Finance and Operations
Per visualizzare i parametri che possono essere configurati per il servizio di previsione della domanda di Finance and Operations, andare a **Pianificazione generale** &gt; **Impostazioni** &gt; **Previsione della domanda** &gt; **Previsione parametri di algoritmo**. La pagina **Previsione parametri di algoritmo** mostra i valori predefiniti dei parametri. È possibile sovrascrivere questi parametri nella pagina **Parametri di previsione della domanda**. Utilizzare la scheda **Generale** per sovrascrivere i parametri globalmente oppure utilizzare la scheda **Chiavi di allocazione articoli** per sovrascrivere la chiave di allocazione per chiave di allocazione articolo. I parametri che vengono sovrascritti per una chiave di allocazione articolo hanno effetto solo sulla previsione degli articoli associati alla chiave di allocazione articolo.

<a name="see-also"></a>Vedere anche
--------

[Introduzione alla previsione della domanda](introduction-demand-forecasting.md)

[Generazione di una previsione di base statistica](generate-statistical-baseline-forecast.md)

[Implementazione di correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)




