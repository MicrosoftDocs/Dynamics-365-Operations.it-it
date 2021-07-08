---
title: Libro contabile di contabilità inventario globale
description: Questo argomento descrive i libri contabili di Contabilità inventario globale, definiti da una combinazione di valuta, calendario, convenzione e associazione con una persona giuridica.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273178"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="fb241-103">Libro contabile di contabilità inventario globale</span><span class="sxs-lookup"><span data-stu-id="fb241-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="fb241-104">Contabilità inventario globale ha un proprio set di libri contabili.</span><span class="sxs-lookup"><span data-stu-id="fb241-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="fb241-105">Ogni volta che viene elaborata una transazione relativa all'inventario per una persona giuridica pertinente, il sistema può contabilizzare tale transazione in qualsiasi numero di libri contabili di Contabilità inventario globale, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="fb241-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="fb241-106">Un libro contabile è un registro di misure in Dare e Avere.</span><span class="sxs-lookup"><span data-stu-id="fb241-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="fb241-107">Queste misure sono classificate utilizzando elementi di costo e conti CoGe secondari.</span><span class="sxs-lookup"><span data-stu-id="fb241-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="fb241-108">Un libro contabile di Contabilità inventario globale è definito da una combinazione di valuta, calendario, convenzione e associazione con una persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="fb241-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="fb241-109">Per impostare i libri contabili di contabilità inventario globale, vai a **Contabilità inventario globale \> Impostazioni \> Libri contabilità inventario globale**.</span><span class="sxs-lookup"><span data-stu-id="fb241-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="fb241-110">Per ciascun libro imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="fb241-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="fb241-111">**Nome**: immetti il nome del libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="fb241-112">**Descrizione** - Immettere una descrizione del libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="fb241-113">**Calendario fiscale** – Specifica il calendario fiscale per il libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="fb241-114">**Tipo di tasso di cambio e valuta** – Utilizza i campi di questa Scheda dettaglio per selezionare la valuta contabile utilizzata dal libro contabile e il tipo di tasso di cambio.</span><span class="sxs-lookup"><span data-stu-id="fb241-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="fb241-115">La valuta selezionata può essere diversa dalla valuta utilizzata dalla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="fb241-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="fb241-116">In Contabilità inventario globale, gli utenti possono definire tutti i libri contabili di determinazione dei costi di cui hanno bisogno.</span><span class="sxs-lookup"><span data-stu-id="fb241-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="fb241-117">Contabilità inventario globale supporta la contabilità inventario in più valute e in più valutazioni.</span><span class="sxs-lookup"><span data-stu-id="fb241-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="fb241-118">Imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="fb241-118">Set the following fields:</span></span>

    - <span data-ttu-id="fb241-119">**Valuta** – Seleziona la valuta di determinazione dei costi in cui vengono mantenuti i valori relativi all'inventario.</span><span class="sxs-lookup"><span data-stu-id="fb241-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="fb241-120">Questi valori includono il valore dell'inventario, il costo delle merci vendute, l'inventario in transito e tutti i tipi di scostamento.</span><span class="sxs-lookup"><span data-stu-id="fb241-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="fb241-121">**Tipo di tasso di cambio** – Seleziona il tasso di cambio che il sistema deve utilizzare per convertire l'importo della transazione nella valuta di transazione e il costo standard degli articoli nella valuta di determinazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="fb241-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="fb241-122">**Nome convenzione** – Specifica una convenzione.</span><span class="sxs-lookup"><span data-stu-id="fb241-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="fb241-123">Una convenzione è una raccolta di criteri che stabiliscono come verranno contabilizzati i costi in questo libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="fb241-124">**Persona giuridica** – Il libro contabile contabilizzerà i documenti registrati nella persona giuridica selezionata.</span><span class="sxs-lookup"><span data-stu-id="fb241-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="fb241-125">**Preparazione** – Seleziona se le transazioni di inventario create prima della creazione del libro contabile devono essere elaborate in base alla valuta e alla convenzione nel libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="fb241-126">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="fb241-126">Select one of the following values:</span></span>

    - <span data-ttu-id="fb241-127">**Attivato** – Il libro contabile deve elaborare le transazioni create prima della creazione del libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="fb241-128">**Disattivato** – Il libro contabile deve elaborare solo le transazioni create dopo della creazione del libro contabile.</span><span class="sxs-lookup"><span data-stu-id="fb241-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fb241-129">**Non** sarai in grado di tornare indietro e impostare questo campo dopo aver inserito nuovi documenti.</span><span class="sxs-lookup"><span data-stu-id="fb241-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="fb241-130">**Stato** – Il sistema imposta automaticamente lo stato dei libri contati appena creati su *Preparazione*.</span><span class="sxs-lookup"><span data-stu-id="fb241-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
