---
title: Impostazione della previsione della domanda
description: In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7b0976494a8bb128ae6bb40cbcdf7c691185f23
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970508"
---
# <a name="demand-forecasting-setup"></a>Impostazione della previsione della domanda

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda.  

Queste attività di configurazione comprendono l'impostazione dei dati e parametri indicati di seguito.

## <a name="item-allocation-key"></a>Chiave di allocazione articolo
Una previsione della domanda viene calcolata per un articolo e le relative dimensioni solo se l'articolo fa parte di una chiave di allocazione articolo. Questa regola viene applicata per raggruppare numerosi articoli, in modo da consentire una creazione più rapida delle previsioni della domanda. La percentuale della chiave di allocazione articolo viene ignorata quando vengono generate le previsioni della domanda. Le previsioni vengono create solo in base ai dati storici. 

Un articolo e le relative dimensioni devono essere parte solo di una chiave di allocazione articolo se la chiave di allocazione articolo viene utilizzata durante la creazione della previsione. 

Per aggiungere un'unità di stockkeeping (SKU) predefinita a una chiave di allocazione articolo, passare a **Pianificazione generale** &gt; **Impostazione** &gt; **Previsione della domanda** &gt; **Chiavi di allocazione articoli**. Utilizzare la pagina **Assegna articoli** per assegnare un articolo a una chiave di allocazione.

## <a name="intercompany-planning-groups"></a>Gruppi di pianificazione interaziendale
Le previsioni della domanda generano previsioni interaziendali. In Dynamics 365 Supply Chain Management, le società pianificate insieme vengono raggruppate in un gruppo di pianificazione interaziendale. Per specificare, per ogni società, quale chiave di allocazione articolo utilizzare per la previsione della domanda, associare una chiave di allocazione articolo al membro del gruppo di pianificazione interaziendale tramite **Pianificazione generale** &gt; **Impostazioni** &gt; **Gruppi di pianificazione interaziendale**. 

Per impostazione predefinita, se nessuna chiave di allocazione articolo è assegnata ai membri del gruppo di pianificazione interaziendale, una previsione della domanda viene calcolata per tutti gli articoli assegnati a tutte le chiavi di allocazione articolo da tutte le società. Le opzioni aggiuntive di filtro per le società e le chiavi di allocazione articolo sono disponibili nella pagina **Genera previsione di base statistica**. 

Verificare il numero di articoli che vengono previsti. Gli articoli non necessari possono determinare un aumento nei costi quando si utilizza Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Parametri di previsione della domanda
Per impostare i parametri di previsione della domanda, andare a **Pianificazione generale** &gt; **Impostazioni** &gt; **Parametri di previsione della domanda**. Poiché le previsioni della domanda vengono eseguite a livello interaziendale, l'impostazione è globale. Ovvero l'impostazione si applica a tutte le società. 

La previsione della domanda genera la previsione in quantità. Di conseguenza, l'unità di misura in cui la quantità deve essere espressa deve essere specificata nel campo **Unità previsione domanda**. L'unità di misura deve essere univoca per garantire che l'aggregazione e la percentuale di distribuzione siano appropriate. Per ulteriori informazioni su aggregazione e percentuale di distribuzione, vedere [Effettuare correzioni manuali alla previsione di base](manual-adjustments-baseline-forecast.md). Per ciascuna unità di misura utilizzata per le SKU incluse nella previsione della domanda, assicurarsi che sia presente una regola di conversione per l'unità di misura e l'unità di misura della previsione generale. Durante la generazione della previsione, viene registrato l'elenco di articoli che non dispongono di una conversione dell'unità di misura, in modo da poter facilmente correggere l'impostazione. 

Le previsioni della domanda possono essere utilizzate per prevedere la domanda dipendente e indipendente. Ad esempio, se è selezionata solo la casella di controllo **Ordine cliente** e se tutti gli articoli che vengono considerati per la previsione della domanda sono articoli venduti, il sistema calcolerà la domanda indipendente. Tuttavia, i sottocomponenti critici possono essere aggiunti alle chiavi di allocazione articolo e inclusi nelle previsioni della domanda. In questo caso, se la casella di controllo **Riga produzione** è selezionata, viene calcolata una previsione dipendente. 

Sono disponibili due metodi per creare una previsione di base. È possibile utilizzare modelli di previsione con i dati storici oppure copiare semplicemente i dati storici nella previsione. Il campo **Strategia di generazione previsione** consente di selezionare uno dei due metodi. Per utilizzare i modelli previsionali, selezionare **Azure Machine Learning**. 

Facendo clic su **Dimensioni previsione** nel riquadro sinistro della pagina **Parametri di previsione della domanda**, è possibile selezionare il set di dimensioni di previsione da utilizzare quando la previsione della domanda viene generata. Una dimensione di previsione indica il livello di dettaglio per cui la previsione è definita. Società, sito e chiave di allocazione articolo sono dimensioni di previsione obbligatorie, ma è inoltre possibile generare le previsioni a livello di dimensioni di magazzino, stato inventario, gruppo clienti, conto cliente, paese/regione o stato e articolo oltre a tutti i livelli di dimensione articolo. 

In qualsiasi punto, è possibile aggiungere le dimensioni di previsione all'elenco delle dimensioni utilizzate per previsione della domanda. È anche possibile eliminare una dimensione previsione dall'elenco. Tuttavia, le correzioni manuali vengono perse se si aggiunge o rimuove una dimensione previsione. 

Non tutti gli articoli si comportano nello stesso modo da un punto di vista della previsione della domanda. Gli articoli simili possono essere raggruppati in una chiave di allocazione articolo e i parametri come tipi di transazione e impostazioni del metodo di previsione possono essere impostati per chiave di allocazione articolo. Fare clic su **Chiavi di allocazione articolo** nella pagina **Parametri di previsione della domanda** . 

Per generare la previsione, Supply Chain Management utilizza un servizio Web di Machine Learning. Per connettersi al servizio, è necessario immettere le informazioni seguenti, se si accede a Microsoft Azure Machine Learning Studio (classico):

-   Chiave dell'API del servizio Web
-   URL dell'endpoint del servizio Web
-   Nome account di archiviazione Azure
-   Chiave account di archiviazione Azure

> [!NOTE]
> Il nome account e la chiave di archiviazione Azure sono necessari solo se si utilizza un account di archiviazione personalizzato. Se si distribuisce la versione locale, è necessario disporre di un account di archiviazione personalizzato in Azure, in modo che il servizio Machine Learning possa accedere ai dati storici. 

Per creare le previsioni della domanda, è possibile distribuire un servizio personalizzato tramite Machine Learning Studio o gli esperimenti di previsione della domanda di Supply Chain Management. Le istruzioni per la distribuzione degli esperimenti di previsione della domanda come servizio Web sono disponibili in Supply Chain Management. Nella pagina **Parametri di previsione della domanda** fare clic sulla scheda **Azure Machine Learning**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Impostazioni per il servizio di Machine Learning della previsione della domanda
Per visualizzare i parametri che possono essere configurati per il servizio di previsione della domanda, andare a **Pianificazione generale** &gt; **Impostazioni** &gt; **Previsione della domanda** &gt; **Previsione parametri di algoritmo**. La pagina **Previsione parametri di algoritmo** mostra i valori predefiniti dei parametri. È possibile sovrascrivere questi parametri nella pagina **Parametri di previsione della domanda**. Utilizzare la scheda **Generale** per sovrascrivere i parametri globalmente oppure utilizzare la scheda **Chiavi di allocazione articoli** per sovrascrivere la chiave di allocazione per chiave di allocazione articolo. I parametri che vengono sovrascritti per una chiave di allocazione articolo hanno effetto solo sulla previsione degli articoli associati alla chiave di allocazione articolo.

### <a name="forecast-algorithm-parameters"></a>Parametri dell'algoritmo di previsione

Nella scheda **Chiavi di allocazione** è possibile impostare **Parametri dell'algoritmo di previsione** per ogni chiave di allocazione articolo. Sono disponibili le seguenti opzioni.
- **Percentuale livello di fiducia**: un intervallo di fiducia è costituito da una gamma di valori che rappresentano una buona stima per la previsione della domanda. Un livello di fiducia del 95% indica che è presente una percentuale di rischio del 5% che la domanda futura non sia compresa nell'intervallo di fiducia.
- **Forza stagionalità**: specifica se forzare il modello a utilizzare un certo tipo di stagionalità. Si applica solo a ARIMA e ETS. Opzioni: AUTO (predefinita), NESSUNO, ADDITIVO, MOLTIPLICATIVO.
- **Modello previsionale**: opzioni: ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, TUTTI. Per selezionare il modello più adatto, utilizzare **TUTTI**.
- **Valore previsto massimo**: specifica il valore massimo da utilizzare per le previsioni Formato: +1E[n] o costante numerica.
- **Valore previsto minimo**: specifica il valore minimo da utilizzare per le previsioni. Formato: -1E[n] o costante numerica.
- **Sostituzione di valore mancante**: specifica la modalità di riempimento dei vuoti nei dati storici. Opzioni: valore numerico, MEDIA, PRECEDENTE, INTERPOLAZIONE LINEARE, INTERPOLAZIONE POLINOMIALE.
- **Sostituzione di valore mancante**: specifica se la sostituzione del valore si applica solo all'intervallo di dati di ogni singolo attributo di granularità oppure all'intero gruppo di dati. Opzioni: GRANULARITY_ATTRIBUTE (predefinita), GLOBAL.
- **Suggerimento stagionalità**: per i dati stagionali, fornire un suggerimento al modello previsionale per migliorare la precisione della previsione. Formato: numero intero, che rappresenta il periodo di ripetizione di un modello di domanda. Utilizzare ad esempio "6" per dati che si ripetono ogni 6 mesi.
- **Percentuale dimensione set di test**: percentuale di dati storici da utilizzare come set di test per il calcolo della precisione della previsione. 

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica previsioni della domanda](introduction-demand-forecasting.md)

[Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)

[Implementare correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]