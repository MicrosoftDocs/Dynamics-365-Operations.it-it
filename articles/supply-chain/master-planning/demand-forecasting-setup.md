---
title: Impostazione della previsione della domanda
description: In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda.
author: ChristianRytt
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f71d7a1ef2e8b6a113124d3fb17f1681d62aed9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575754"
---
# <a name="demand-forecasting-setup"></a>Impostazione della previsione della domanda

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le attività di impostazione che è necessario eseguire per la preparazione delle previsioni della domanda.  

Queste attività di configurazione comprendono l'impostazione dei dati e parametri indicati di seguito.

## <a name="item-allocation-keys"></a>Chiavi di allocazione articoli

Una previsione della domanda viene calcolata per un articolo e le relative dimensioni solo se l'articolo fa parte di una chiave di allocazione articolo. Questa regola viene applicata per raggruppare numerosi articoli, in modo da consentire una creazione più rapida delle previsioni della domanda. La percentuale della chiave di allocazione articolo viene ignorata quando vengono generate le previsioni della domanda. Le previsioni vengono create solo in base ai dati storici.

Un articolo e le relative dimensioni devono essere parte solo di una chiave di allocazione articolo se la chiave di allocazione articolo viene utilizzata durante la creazione della previsione.

Per aggiungere un'unità di stockkeeping (SKU) predefinita a una chiave di allocazione articolo, passare a **Pianificazione generale \> Impostazione \> Previsione della domanda \> Chiavi di allocazione articoli**. Utilizzare la pagina **Assegna articoli** per assegnare un articolo a una chiave di allocazione.

## <a name="intercompany-planning-groups"></a>Gruppi di pianificazione interaziendale

Le previsioni della domanda generano previsioni interaziendali. In Dynamics 365 Supply Chain Management, le società pianificate insieme vengono raggruppate in un gruppo di pianificazione interaziendale. Per specificare, per ogni società, quale chiave di allocazione articolo utilizzare per la previsione della domanda, associare una chiave di allocazione articolo al membro del gruppo di pianificazione interaziendale tramite **Pianificazione generale \> Impostazioni \> Gruppi di pianificazione interaziendale**.

Per impostazione predefinita, se nessuna chiave di allocazione articolo è assegnata ai membri del gruppo di pianificazione interaziendale, una previsione della domanda viene calcolata per tutti gli articoli assegnati a tutte le chiavi di allocazione articolo da tutte le società. Le opzioni aggiuntive di filtro per le società e le chiavi di allocazione articolo sono disponibili nella pagina **Genera previsione di base statistica**.

Verificare il numero di articoli che vengono previsti. Gli articoli non necessari possono determinare un aumento nei costi quando si utilizza Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Parametri di previsione della domanda

Per impostare i parametri di previsione della domanda, andare a **Pianificazione generale \> Impostazioni \> \> Previsione della domanda \> Parametri di previsione della domanda**. Poiché le previsioni della domanda vengono eseguite a livello interaziendale, l'impostazione è globale. Ciò significa che l'impostazione si applica a tutte le società.

La previsione della domanda genera la previsione in quantità. Di conseguenza, l'unità di misura in cui la quantità deve essere espressa deve essere specificata nel campo **Unità previsione domanda**. L'unità di misura deve essere univoca per garantire che l'aggregazione e la percentuale di distribuzione siano appropriate. Per ulteriori informazioni su aggregazione e percentuale di distribuzione, vedere [Effettuare correzioni manuali alla previsione di base](manual-adjustments-baseline-forecast.md). Per ciascuna unità di misura utilizzata per le SKU incluse nella previsione della domanda, assicurarsi che sia presente una regola di conversione per l'unità di misura e l'unità di misura della previsione generale. Durante la generazione della previsione, viene registrato l'elenco di articoli che non dispongono di una conversione dell'unità di misura, in modo da poter facilmente correggere l'impostazione.

Le previsioni della domanda possono essere utilizzate per prevedere la domanda dipendente e indipendente. Ad esempio, se è selezionata solo la casella di controllo **Ordine cliente** e se tutti gli articoli che vengono considerati per la previsione della domanda sono articoli venduti, il sistema calcolerà la domanda indipendente. Tuttavia, i sottocomponenti critici possono essere aggiunti alle chiavi di allocazione articolo e inclusi nelle previsioni della domanda. In questo caso, se la casella di controllo **Riga produzione** è selezionata, viene calcolata una previsione dipendente.

Sono disponibili due metodi per creare una previsione di base. È possibile utilizzare modelli di previsione con i dati storici oppure copiare semplicemente i dati storici nella previsione. Il campo **Strategia di generazione previsione** consente di selezionare uno dei due metodi. Per utilizzare i modelli previsionali, selezionare **Azure Machine Learning**.

Selezionando **Dimensioni previsione** nel riquadro sinistro della pagina **Parametri di previsione della domanda**, è possibile selezionare il set di dimensioni di previsione da utilizzare quando la previsione della domanda viene generata. Una dimensione di previsione indica il livello di dettaglio per cui la previsione è definita. Società, sito e chiave di allocazione articolo sono dimensioni di previsione richieste, ma è inoltre possibile generare le previsioni a livello di dimensioni di magazzino, stato inventario, gruppo clienti, conto cliente, paese/area geografica o stato e articolo oltre a tutti i livelli di dimensione articolo.

In qualsiasi punto, è possibile aggiungere le dimensioni di previsione all'elenco delle dimensioni utilizzate per previsione della domanda. È anche possibile eliminare una dimensione previsione dall'elenco. Tuttavia, le correzioni manuali vengono perse se si aggiunge o rimuove una dimensione previsione.

Non tutti gli articoli si comportano nello stesso modo da un punto di vista della previsione della domanda. Gli articoli simili possono essere raggruppati in una chiave di allocazione articolo e i parametri come tipi di transazione e impostazioni del metodo di previsione possono essere impostati per chiave di allocazione articolo. Selezionare **Chiavi di allocazione articolo** nella pagina **Parametri di previsione della domanda**.

Per generare la previsione, Supply Chain Management utilizza un servizio Web di Machine Learning. Per connettersi al servizio, è necessario immettere le informazioni seguenti, se si accede a Microsoft Azure Machine Learning Studio (classico):

- Chiave dell'API del servizio Web
- URL dell'endpoint del servizio Web
- Nome account di archiviazione Azure
- Chiave account di archiviazione Azure

> [!NOTE]
> Il nome account e la chiave di archiviazione Azure sono necessari solo se si utilizza un account di archiviazione personalizzato. Se si distribuisce la versione locale, è necessario disporre di un account di archiviazione personalizzato in Azure, in modo che il servizio Machine Learning possa accedere ai dati storici.

Per creare le previsioni della domanda, è possibile distribuire un servizio personalizzato tramite Machine Learning Studio o gli esperimenti di previsione della domanda di Supply Chain Management. Le istruzioni per la distribuzione degli esperimenti di previsione della domanda come servizio Web sono disponibili in Supply Chain Management. Nella pagina **Parametri di previsione della domanda** aprire la scheda **Azure Machine Learning**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Impostazioni per il servizio di Machine Learning della previsione della domanda

Per visualizzare i parametri che possono essere configurati per il servizio di previsione della domanda, andare a **Pianificazione generale \> Impostazioni \> Previsione della domanda \> Previsione parametri di algoritmo**. La pagina **Previsione parametri di algoritmo predefiniti** mostra i valori predefiniti dei parametri. È possibile sovrascrivere questi parametri andando su **Pianificazione generale \> Impostazione \> Previsione della domanda \> Parametri di previsione della domanda**, dove è possibile effettuare le seguenti operazioni:

- Utilizzare la scheda **Generale** per sovrascrivere i parametri globalmente.
- Utilizzare la scheda **Chiavi di allocazione articoli** per sovrascrivere i parametri per chiave di allocazione articolo. I parametri che vengono sovrascritti per una chiave di allocazione articolo hanno effetto solo sulla previsione degli articoli associati alla chiave di allocazione articolo.

### <a name="forecast-algorithm-parameters"></a>Parametri dell'algoritmo di previsione

Sulla scheda **Chiavi di allocazione articoli** della pagina **Parametri di previsione della domanda**, è possibile usare la Scheda dettaglio **Parametri dell'algoritmo di previsione** per assegnare i parametri dell'algoritmo di previsione per la chiave di allocazione dell'articolo attualmente selezionata nella griglia a sinistra. Utilizzare i pulsanti **Aggiungi** e **Rimuovi** sulla barra degli strumenti per stabilire la raccolta di parametri richiesta. Per ogni parametro nell'elenco, selezionare uno dei seguenti valori nel campo **Nome** e quindi immettere un valore appropriato nel campo **Valore**:

- **Percentuale livello di fiducia** - Un intervallo di fiducia è costituito da una gamma di valori che rappresentano una buona stima per la previsione della domanda. Un livello di fiducia del 95% indica che è presente una percentuale di rischio del 5% che la domanda futura non sia compresa nell'intervallo di fiducia.
- **Forza stagionalità** - Specifica se forzare il modello a utilizzare un certo tipo di stagionalità. Si applica solo a ARIMA e ETS. Opzioni: AUTO (predefinita), NESSUNO, ADDITIVO, MOLTIPLICATIVO.
- **Modello previsionale** - Opzioni: ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, TUTTI. Per selezionare il modello più adatto, utilizzare **TUTTI**.
- **Valore previsto massimo** - Specifica il valore massimo da utilizzare per le previsioni. Formato: +1E[n] o costante numerica.
- **Valore previsto minimo** - Specifica il valore minimo da utilizzare per le previsioni. Formato: -1E[n] o costante numerica.
- **Sostituzione di valore mancante** - Specifica la modalità di riempimento dei vuoti nei dati storici. Opzioni: valore numerico, MEDIA, PRECEDENTE, INTERPOLAZIONE LINEARE, INTERPOLAZIONE POLINOMIALE.
- **Sostituzione di valore mancante** - Specifica se la sostituzione del valore si applica solo all'intervallo di date di ogni singolo attributo di granularità oppure all'intero gruppo di dati. Sono disponibili le seguenti opzioni per stabilire l'intervallo di date che il sistema utilizza per colmare le lacune nei dati cronologici:

  - GLOBAL - Il sistema utilizza l'intero intervallo di date di tutti gli attributi di granularità.
  - HISTORY_DATE_RANGE - Il sistema utilizza un intervallo di date specifico definito dai campi **Dal** e **Al** sul gruppo di campi **Orizzonte storico** nella finestra di dialogo **Genera previsione di base statistica**.
  - GRANULARITY_ATTRIBUTE - Il sistema utilizza l'intervallo di date dell'attributo di granularità attualmente elaborato.

  > [!NOTE]
  > Un attributo di granularità è una combinazione di dimensioni di previsione rispetto alle quali viene eseguita la previsione. È possibile definire le dimensioni della previsione nella pagina **Parametri di previsione della domanda**.

- **Suggerimento stagionalità** - Per i dati stagionali, fornire un suggerimento al modello previsionale per migliorare la precisione della previsione. Formato: numero intero, che rappresenta il periodo di ripetizione di un modello di domanda. Utilizzare ad esempio "6" per dati che si ripetono ogni 6 mesi.
- **Percentuale dimensione set di test** - Percentuale di dati storici da utilizzare come set di test per il calcolo della precisione della previsione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica previsioni della domanda](introduction-demand-forecasting.md)
- [Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)
- [Implementare correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
