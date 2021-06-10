---
title: Aprire i modelli di giornale di registrazione finanziario in Office
description: In questo argomento vengono descritti i problemi che potrebbero verificarsi quando si creano giornali di registrazione finanziari personalizzati utilizzando un modello Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089459"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="61115-103">Aprire i modelli di giornale di registrazione finanziario in Office</span><span class="sxs-lookup"><span data-stu-id="61115-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61115-104">In questo argomento vengono descritti i problemi che potrebbero verificarsi quando si creano giornali di registrazione finanziari personalizzati utilizzando un modello Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="61115-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="61115-105">Sintomo</span><span class="sxs-lookup"><span data-stu-id="61115-105">Symptom</span></span>

<span data-ttu-id="61115-106">È stato creato un modello di Excel personalizzato per i giornali di registrazione finanziari, ma non viene visualizzato nel menu **Apri righe in Excel**.</span><span class="sxs-lookup"><span data-stu-id="61115-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="61115-107">In alternativa, è presente nel menu, ma quando lo si seleziona viene aperto un modello diverso.</span><span class="sxs-lookup"><span data-stu-id="61115-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="61115-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="61115-108">Resolution</span></span>

<span data-ttu-id="61115-109">La funzionalità predefinita Apri in Excel utilizza l'origine dati radice (tabella) della pagina corrente per determinare quali modelli o entità di dati di Office vengono visualizzati come opzioni nel menu **Apri in Excel**.</span><span class="sxs-lookup"><span data-stu-id="61115-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="61115-110">Questo comportamento non è un'esperienza ideale per i giornali di registrazione finanziari, perché utilizzano le stesse tabelle (LedgerJournalTable e LedgerJournalTrans) come origine dati radice di molti altri tipi di giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="61115-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="61115-111">Per i giornali di registrazione finanziari, la funzionalità Apri righe in Excel ha lo scopo di mostrare i modelli progettati per il giornale di registrazione nel quale si sta attualmente lavorando, come il giornale di registrazione generale o un giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="61115-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="61115-112">Ad esempio, un modello da utilizzare con un giornale di registrazione pagamenti fornitore è progettato per impostare il conto principale come conto fornitore.</span><span class="sxs-lookup"><span data-stu-id="61115-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="61115-113">Per promuovere un modello in modo che sia disponibile nei menu **Apri righe in Excel** e **Apri in Excel**, una semplice esperienza per sviluppatori consiste nell'implementare l'interfaccia **LedgerIJournalExcelTemplate** ed estendere la classe **DocuTemplateRegistrationBase**.</span><span class="sxs-lookup"><span data-stu-id="61115-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="61115-114">Molti esempi di questo approccio sono implementati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="61115-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="61115-115">Un esempio da usare come riferimento è l'interfaccia **LedgerDailyJournalExcelTemplate** che è stata creata per il giornale di registrazione generale (o il giornale di registrazione giornaliero).</span><span class="sxs-lookup"><span data-stu-id="61115-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="61115-116">Quando l'interfaccia **LedgerIJournalExcelTemplate** è implementata per il modello, il menu **Apri righe in Excel** filtra i modelli in base al tipo di giornale di registrazione in uso e mostra solo i modelli disponibili per quel giornale.</span><span class="sxs-lookup"><span data-stu-id="61115-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="61115-117">L'interfaccia fornisce anche un metodo di convalida che garantisce che un modello non possa essere aperto per un giornale di registrazione se non soddisfa i requisiti del tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="61115-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="61115-118">Ad esempio, è possibile specificare che il tipo di conto debba essere di tipo **Fornitore** o **Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="61115-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="61115-119">Per ulteriori informazioni su questa funzionalità, vedere [Aggiungere modelli al menu Apri righe in Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="61115-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
