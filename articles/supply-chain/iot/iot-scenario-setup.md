---
title: Configurazione dello scenario per l'Intelligence IoT
description: Questo argomento descrive come configurare uno scenario in Supply Chain Management per l'Intelligence IoT.
author: robinarh
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b87a9b73f49e73fe13b98fb11da939c9b30e0f6e
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386530"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="ce149-103">Configurazione dello scenario per l'Intelligence IoT</span><span class="sxs-lookup"><span data-stu-id="ce149-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ce149-104">Questo argomento descrive come configurare uno scenario in Supply Chain Management per l'Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="ce149-105">Prima di poter impostare gli scenari, devi [configurare LCS](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="ce149-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="ce149-106">In questo argomento, configurerai lo scenario **Tempo morto dell'attrezzatura** per generare una notifica in Supply Chain Management quando un computer si arresta.</span><span class="sxs-lookup"><span data-stu-id="ce149-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="ce149-107">Configura lo scenario **Tempo morto dell'attrezzatura** in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ce149-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="ce149-108">Lo scenario **Tempo morto dell'attrezzatura** associa un segnale di part-out a una soglia di avviso del computer.</span><span class="sxs-lookup"><span data-stu-id="ce149-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="ce149-109">Il computer viene monitorato solo quando il computer è selezionato per lo scenario ed è impostato per funzionare in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ce149-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="ce149-110">Se il tempo trascorso dall'ultimo segnale Part Out della computer è superiore alla soglia di avviso, viene quindi attivata una notifica **Macchina giù**.</span><span class="sxs-lookup"><span data-stu-id="ce149-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="ce149-111">Se la macchina è ancora in funzione, al successivo segnale **PartOut** ricevuto viene attivata una notifica **Macchina su**.</span><span class="sxs-lookup"><span data-stu-id="ce149-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="ce149-112">Se una macchina rimane ferma per 30 minuti viene attivata una nuova notifica **Macchina giù**.</span><span class="sxs-lookup"><span data-stu-id="ce149-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="ce149-113">Lo scenario **Tempo morto dell'attrezzatura** ha queste dipendenze:</span><span class="sxs-lookup"><span data-stu-id="ce149-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="ce149-114">Un ordine di produzione deve essere in esecuzione su un computer mappato per attivare un avviso.</span><span class="sxs-lookup"><span data-stu-id="ce149-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="ce149-115">Un segnale che rappresenta il segnale di part-out di un computer mappato deve essere inviato all'hub IoT con un nome di proprietà univoco.</span><span class="sxs-lookup"><span data-stu-id="ce149-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="ce149-116">Una proprietà del timestamp dei millisecondi Unix deve essere presente nel messaggio dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="ce149-117">Per configurare lo scenario, attieniti a questa procedura:</span><span class="sxs-lookup"><span data-stu-id="ce149-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="ce149-118">Accedi a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ce149-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="ce149-119">Abilita il flag della funzionalità di Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="ce149-120">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ce149-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="ce149-121">Configurare le metriche.</span><span class="sxs-lookup"><span data-stu-id="ce149-121">Configure the metrics.</span></span> <span data-ttu-id="ce149-122">Per ulteriori informazioni, vedi [Come configurare le metriche](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="ce149-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="ce149-123">Accedi a **Controllo di produzione**.</span><span class="sxs-lookup"><span data-stu-id="ce149-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="ce149-124">Accedi a **Impostazioni \> Intelligence IoT \> Gestione scenario**.</span><span class="sxs-lookup"><span data-stu-id="ce149-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="ce149-125">Fai clic su **Configura** nel riquadro **Tempo morto dell'attrezzatura**.</span><span class="sxs-lookup"><span data-stu-id="ce149-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="ce149-126">La procedura guidata di configurazione inizia con la pagina **Definizione dello schema del sensore dell'apparecchiatura**.</span><span class="sxs-lookup"><span data-stu-id="ce149-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="ce149-127">L'obiettivo qui è configurare lo schema in Supply Chain Management in modo che corrisponda al formato JSON dei messaggi IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="ce149-128">È possibile definire più schemi di messaggi multipli.</span><span class="sxs-lookup"><span data-stu-id="ce149-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="ce149-129">Per ulteriori informazioni, vedi [Formati dello schema dei messaggi per l'hub IoT](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="ce149-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="ce149-130">In questo esempio, il payload del messaggio contiene un batch di messaggi con questo formato:</span><span class="sxs-lookup"><span data-stu-id="ce149-130">In this example, the message payload contains a batch of messages with this format:</span></span>

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. <span data-ttu-id="ce149-131">Aggiungi una riga alla tabella.</span><span class="sxs-lookup"><span data-stu-id="ce149-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="ce149-132">Imposta il **Nome dello schema** per **ID**.</span><span class="sxs-lookup"><span data-stu-id="ce149-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="ce149-133">Imposta **Percorso schema** su **/payload[\*]/id**.</span><span class="sxs-lookup"><span data-stu-id="ce149-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="ce149-134">Imposta **Descrizione** su **ID messaggio**.</span><span class="sxs-lookup"><span data-stu-id="ce149-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="ce149-135">Aggiungi una riga alla tabella.</span><span class="sxs-lookup"><span data-stu-id="ce149-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="ce149-136">Imposta **Nome schema** su **Timestamp**.</span><span class="sxs-lookup"><span data-stu-id="ce149-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="ce149-137">Imposta **Percorso schema** su **/payload[\*]/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="ce149-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="ce149-138">Imposta **Descrizione** su **Timestamp messaggio**.</span><span class="sxs-lookup"><span data-stu-id="ce149-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="ce149-139">Aggiungi una riga alla tabella.</span><span class="sxs-lookup"><span data-stu-id="ce149-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="ce149-140">Imposta **Nome schema** su **Valore**.</span><span class="sxs-lookup"><span data-stu-id="ce149-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="ce149-141">Imposta **Percorso schema** su **/payload[\*]/value**.</span><span class="sxs-lookup"><span data-stu-id="ce149-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="ce149-142">Imposta **Descrizione** su **Valore messaggio**.</span><span class="sxs-lookup"><span data-stu-id="ce149-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="ce149-143">Non devi definire tutte le proprietà nel messaggio, solo quelle necessarie.</span><span class="sxs-lookup"><span data-stu-id="ce149-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="ce149-144">In questo esempio, non è stata creata una riga per **Timestamp radice**.</span><span class="sxs-lookup"><span data-stu-id="ce149-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="ce149-145">Il percorso per **Timestamp radice** sarebbe **/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="ce149-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="ce149-146">Fai clic su **Avanti** per andare alla pagina **Mappa dello schema del sensore dell'apparecchiatura**.</span><span class="sxs-lookup"><span data-stu-id="ce149-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="ce149-147">In fila per **ID risorsa attrezzatura** imposta **Nome schema** su **ID**.</span><span class="sxs-lookup"><span data-stu-id="ce149-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="ce149-148">I valori validi sono visualizzati in una tabella a discesa.</span><span class="sxs-lookup"><span data-stu-id="ce149-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="ce149-149">Nella fila per **Ora UTC** imposta **Nome schema** su **Timestamp**.</span><span class="sxs-lookup"><span data-stu-id="ce149-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="ce149-150">I valori validi sono visualizzati in una tabella a discesa.</span><span class="sxs-lookup"><span data-stu-id="ce149-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="ce149-151">Nella riga per **Parte prodotta da segnale** imposta **Nome schema** su **Valore**.</span><span class="sxs-lookup"><span data-stu-id="ce149-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="ce149-152">I valori validi sono visualizzati in una tabella a discesa.</span><span class="sxs-lookup"><span data-stu-id="ce149-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="ce149-153">Fai clic su **Avanti** per la pagina **Configurazione ID risorsa apparecchiatura**.</span><span class="sxs-lookup"><span data-stu-id="ce149-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="ce149-154">In questo passaggio, si mappano i valori dei messaggi dell'hub IoT sulle risorse Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ce149-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="ce149-155">Nella tabella **Valori dati segnale**, aggiungi una nuova riga e inserisci **IoTInt.Machine1225.PartOut** nella colonna **Valore**.</span><span class="sxs-lookup"><span data-stu-id="ce149-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="ce149-156">Il valore **IoTInt.Machine1225.PartOut** viene dalla proprietà JSON **id** nel messaggio dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="ce149-157">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce149-157">Click **Save**.</span></span>
    3. <span data-ttu-id="ce149-158">Nella tabella **Mappatura record aziendali**, fai clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ce149-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="ce149-159">Il valore predefinito per **Tipo di record aziendale** viene popolato automaticamente e non è necessario modificarlo.</span><span class="sxs-lookup"><span data-stu-id="ce149-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="ce149-160">Nella colonna **Record aziendali**, seleziona la risorsa della macchina Supply Chain Management da cui viene inviato il valore del segnale.</span><span class="sxs-lookup"><span data-stu-id="ce149-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="ce149-161">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce149-161">Click **Save**.</span></span>
    6. <span data-ttu-id="ce149-162">Ripeti questi passaggi, aggiungendo una nuova mappatura dei record aziendali per **Machine1226**.</span><span class="sxs-lookup"><span data-stu-id="ce149-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="ce149-163">Puoi mappare più valori dei dati del segnale su un singolo record in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ce149-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="ce149-164">Usa la colonna **Selezionato** per scegliere quali computer desideri elaborare.</span><span class="sxs-lookup"><span data-stu-id="ce149-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="ce149-165">Non devi definire tutti i valori del segnale e non devi selezionare tutte le macchine.</span><span class="sxs-lookup"><span data-stu-id="ce149-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="ce149-166">Fai clic su **Avanti** per andare alla pagina **Configurazione segnale prodotto dalla parte**.</span><span class="sxs-lookup"><span data-stu-id="ce149-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="ce149-167">Nella tabella **Valori dati segnale**, aggiungi una riga e imposta **Valore** su **True**.</span><span class="sxs-lookup"><span data-stu-id="ce149-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="ce149-168">Il valore **True** viene dalla proprietà JSON **valore** nel messaggio dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="ce149-169">Puoi aggiungere tutti i valori di cui hai bisogno per il tuo scenario.</span><span class="sxs-lookup"><span data-stu-id="ce149-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="ce149-170">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce149-170">Click **Save**.</span></span>
20. <span data-ttu-id="ce149-171">Fai clic su **Avanti** per andare alla pagina **Soglia tempo di fermo dell'apparecchiatura**.</span><span class="sxs-lookup"><span data-stu-id="ce149-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="ce149-172">I computer elencati sono computer precedentemente mappati ai valori dei segnali.</span><span class="sxs-lookup"><span data-stu-id="ce149-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="ce149-173">In questo passaggio, definisci una soglia per determinare se un computer è inattivo.</span><span class="sxs-lookup"><span data-stu-id="ce149-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="ce149-174">Ad esempio, se imposti la soglia su 10, Supply Chain Management genera una notifica se non viene inviato alcun messaggio di part-out da un computer per 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="ce149-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="ce149-175">Scegli **Avanti** per andare alla pagina **Abilita scenario**.</span><span class="sxs-lookup"><span data-stu-id="ce149-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="ce149-176">Attiva/disattiva il dispositivo di scorrimento per abilitare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="ce149-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="ce149-177">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ce149-177">Click **Finish**.</span></span>

<span data-ttu-id="ce149-178">La configurazione dello scenario è completa.</span><span class="sxs-lookup"><span data-stu-id="ce149-178">The scenario setup is complete.</span></span> <span data-ttu-id="ce149-179">Intelligence IoT inizierà automaticamente l'elaborazione dei messaggi dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="ce149-180">Configura lo scenario **Qualità prodotto** in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ce149-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="ce149-181">Lo scenario **Qualità prodotto** genera una notifica se un attributo di un articolo è al di fuori di un intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="ce149-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="ce149-182">Ad esempio, un sensore potrebbe inviare il peso di ciascun articolo all'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="ce149-183">In Supply Chain Management, verrebbe generata una notifica se l'articolo fosse troppo pesante o troppo leggero.</span><span class="sxs-lookup"><span data-stu-id="ce149-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="ce149-184">Lo scenario ha queste dipendenze:</span><span class="sxs-lookup"><span data-stu-id="ce149-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="ce149-185">Un ordine di produzione deve essere in esecuzione su un computer mappato e procedere un prodotto con un attributo batch mappato per attivare un avviso.</span><span class="sxs-lookup"><span data-stu-id="ce149-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="ce149-186">Un segnale che rappresenta l'attributo batch deve essere inviato all'hub IoT con un nome di proprietà univoco.</span><span class="sxs-lookup"><span data-stu-id="ce149-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="ce149-187">Una proprietà del timestamp dei millisecondi Unix deve essere presente nel messaggio dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="ce149-188">Configura lo scenario **Ritardi produzione** in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ce149-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="ce149-189">Lo scenario **Ritardi produzione** genera una notifica se la produttività scende al di sotto di un valore di soglia.</span><span class="sxs-lookup"><span data-stu-id="ce149-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="ce149-190">In questo scenario, un segnale **PartOut** viene inviato all'hub IoT per ciascun articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="ce149-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="ce149-191">In Supply Chain Management, il ritardo dell'ordine viene calcolato in base alla durata di esecuzione dell'ordine di produzione, al numero di articoli da produrre, alla durata del processo e al numero di segnali **PartOut** ricevuti.</span><span class="sxs-lookup"><span data-stu-id="ce149-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="ce149-192">Una notifica di ritardo verrebbe generata se il numero di segnali **PartOut** per il lavoro scendono al di sotto del valore della soglia del valore previsto.</span><span class="sxs-lookup"><span data-stu-id="ce149-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="ce149-193">Lo scenario ha queste dipendenze:</span><span class="sxs-lookup"><span data-stu-id="ce149-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="ce149-194">Un ordine di produzione deve essere in esecuzione su un computer mappato per attivare un avviso.</span><span class="sxs-lookup"><span data-stu-id="ce149-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="ce149-195">Un segnale che rappresenta il segnale di part-out di un computer mappato deve essere inviato all'hub IoT con un nome di proprietà univoco.</span><span class="sxs-lookup"><span data-stu-id="ce149-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="ce149-196">Una proprietà del timestamp dei millisecondi Unix deve essere presente nel messaggio dell'hub IoT.</span><span class="sxs-lookup"><span data-stu-id="ce149-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="ce149-197">Come disabilitare uno scenario</span><span class="sxs-lookup"><span data-stu-id="ce149-197">How to disable a scenario</span></span>

<span data-ttu-id="ce149-198">Per disabilitare uno scenario, attieniti alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ce149-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="ce149-199">In Supply Chain Management, accedi a **Controllo produzione \> Impostazioni \> Intelligence IoT \> Gestione scenario**.</span><span class="sxs-lookup"><span data-stu-id="ce149-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="ce149-200">Fai clic su **Configura** sullo scenario.</span><span class="sxs-lookup"><span data-stu-id="ce149-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="ce149-201">Fai clic su **Avanti** per andare all'ultima scheda della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ce149-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="ce149-202">Attiva/disattiva il dispositivo di scorrimento per disabilitare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="ce149-202">Toggle the slider to disable the scenario.</span></span>
