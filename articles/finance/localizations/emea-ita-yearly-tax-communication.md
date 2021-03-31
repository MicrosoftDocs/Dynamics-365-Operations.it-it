---
title: Comunicazione annuale imposte
description: Questo argomento fornisce informazioni sul report di comunicazione annuale delle imposte in Italia.
author: anasyash
manager: AnnBe
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 264294
ms.search.region: Italy
ms.author: anasyash
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: a673d283cdfbf386482cd7b17a1403ded7c61f2f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230184"
---
# <a name="yearly-tax-communication"></a><span data-ttu-id="522e8-103">Comunicazione annuale imposte</span><span class="sxs-lookup"><span data-stu-id="522e8-103">Yearly tax communication</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="522e8-104">Il report **Comunicazione annuale imposte** contiene le informazioni della dichiarazione annuale delle imposte per l'Italia da inviare all'ufficio tributario.</span><span class="sxs-lookup"><span data-stu-id="522e8-104">The **Yearly tax communication** report contains annual tax information for Italy that will be submitted to the tax authority.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="522e8-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="522e8-105">Prerequisites</span></span>

<span data-ttu-id="522e8-106">Configurare i libri IVA italiani seguendo le istruzioni in [Libri IVA italiani](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-ita-fiscal-books.md#set-up-sales-tax-books).</span><span class="sxs-lookup"><span data-stu-id="522e8-106">Set up Italian sales tax books by following the instructions in [Italian sales tax books](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/finance/localizations/emea-ita-fiscal-books.md#set-up-sales-tax-books).</span></span>

## <a name="set-up-the-yearly-tax-communication-report"></a><span data-ttu-id="522e8-107">Configurare il report di comunicazione annuale delle imposte</span><span class="sxs-lookup"><span data-stu-id="522e8-107">Set up the Yearly tax communication report</span></span>

1. <span data-ttu-id="522e8-108">In Microsoft Dynamics 365 Finance, andare a **Amministrazione organizzazione** \> **Organizzazioni** \> **Persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="522e8-108">In Microsoft Dynamics 365 Finance, go to **Organization administration** \> **Organizations** \> **Legal entities**.</span></span>
2. <span data-ttu-id="522e8-109">Nella Scheda dettaglio **Numeri di registrazione**, nel campo **Partita IVA** immetter la partita IVA della propria società.</span><span class="sxs-lookup"><span data-stu-id="522e8-109">On the **Registration numbers** FastTab, in the **Tax registration number** field, enter the tax registration number of your company.</span></span>
3. <span data-ttu-id="522e8-110">Nella Scheda dettaglio **Registrazione fiscale**, nel campo **Codice fiscale** immettere il codice fiscale della propria società.</span><span class="sxs-lookup"><span data-stu-id="522e8-110">On the **Tax registration** FastTab, in the **Fiscal code** field, enter the fiscal code of your company.</span></span>
4. <span data-ttu-id="522e8-111">In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), nella raccolta di risorse condivise scaricare le ultime versioni delle configurazioni per la creazione di report elettronici per i seguenti formati della dichiarazione IVA:</span><span class="sxs-lookup"><span data-stu-id="522e8-111">In [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/V2), in the Shared asset library, download the latest versions of the Electronic reporting (ER) configurations for the following value-added tax (VAT) declaration formats:</span></span>

    - <span data-ttu-id="522e8-112">**Modello dei report fiscali italiani**</span><span class="sxs-lookup"><span data-stu-id="522e8-112">**Italian tax reports model**</span></span>
    - <span data-ttu-id="522e8-113">**Comunicazione annuale imposte (IT)**</span><span class="sxs-lookup"><span data-stu-id="522e8-113">**Yearly tax communication (IT)**</span></span>
    - <span data-ttu-id="522e8-114">**Mapping dei modelli di comunicazione annuale IVA**</span><span class="sxs-lookup"><span data-stu-id="522e8-114">**Yearly VAT communication model mapping**</span></span>

<span data-ttu-id="522e8-115">Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span><span class="sxs-lookup"><span data-stu-id="522e8-115">For more information, see [Download Electronic reporting configurations from Lifecycle Services](https://docs.microsoft.com/dynamics365/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span>

5. <span data-ttu-id="522e8-116">In Finance andare a **Imposte \> Impostazione \> Parametri \> Parametri di Contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="522e8-116">In Finance, go to **Tax \> Setup \> Parameters \> General ledger parameters**.</span></span>
6. <span data-ttu-id="522e8-117">Nella scheda **Sequenze numeriche** selezionare una sequenza numerica per il riferimento **ID comunicazione imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-117">On the **Number sequences** tab, select a number sequence for the **Tax communication ID** reference.</span></span>
7. <span data-ttu-id="522e8-118">Nella scheda **IVA**, nel campo **Mapping formato** della Scheda dettaglio **Comunicazione annuale imposte** selezionare il formato **Comunicazione annuale imposte (IT)** scaricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="522e8-118">On the **Sales tax** tab, on the **Yearly tax communication** FastTab, in the **Format mapping** field, select the **Yearly tax communication (IT)** format that you downloaded earlier.</span></span>
8. <span data-ttu-id="522e8-119">Andare a **Imposta \> Impostazione \> IVA \> Impostazioni comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-119">Go to **Tax \> Setup \> Sales tax \> Yearly tax communication setup**.</span></span>

![Pagina Impostazioni comunicazione annuale imposte](media/1_Yearly_tax_communication_setup.png)

> [!NOTE]
> <span data-ttu-id="522e8-121">Per visualizzare il modulo "Comunicazione annuale IVA" per l'anno 2020 e le relative istruzioni, vedere [Modello e istruzioni - IVA 2020](https://www.agenziaentrate.gov.it/portale/web/guest/iva-2020/modello-e-istruzioni-imprese).</span><span class="sxs-lookup"><span data-stu-id="522e8-121">To view the "Yearly VAT communication" form for the year 2020, and instructions for it, see [Model and instructions - VAT 2020](https://www.agenziaentrate.gov.it/portale/web/guest/iva-2020/modello-e-istruzioni-imprese).</span></span>

9. <span data-ttu-id="522e8-122">Nella scheda **Impostazione campi** creare righe e impostare i seguenti campi su di esse.</span><span class="sxs-lookup"><span data-stu-id="522e8-122">On the **Field setup** tab, create lines, and set the following fields on them.</span></span>

<table>
<tbody>
<tr>
<td>
<p><span data-ttu-id="522e8-123"><strong>Campo</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-123"><strong>Field</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-124"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-124"><strong>Description</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-125">ID campo</span><span class="sxs-lookup"><span data-stu-id="522e8-125">Field ID</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-126">Immettere il numero di identificazione del campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-126">Enter the identification number of the field.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522e8-127">Description</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-128">Immettere una descrizione del campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-128">Enter a description of the field.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-129">Formattazione</span><span class="sxs-lookup"><span data-stu-id="522e8-129">Format</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-130">Selezionare il formato richiesto del campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-130">Select the required format of the field.</span></span> <span data-ttu-id="522e8-131">Per ulteriori informazioni sui formati disponibili, vedere la sezione <a href="https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/IT_Yearly_tax_communication/articles/finance/localizations/emea-ita-yearly-tax-communication.md#formats-of-the-fields">Formati dei campi</a> più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="522e8-131">For more information about the available formats, see the <a href="https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/IT_Yearly_tax_communication/articles/finance/localizations/emea-ita-yearly-tax-communication.md#formats-of-the-fields">Formats of the fields</a> section later in this topic.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-132">Calcolo</span><span class="sxs-lookup"><span data-stu-id="522e8-132">Calculation</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-133">Selezionare un metodo di calcolo:</span><span class="sxs-lookup"><span data-stu-id="522e8-133">Select a calculation method:</span></span></p>
<ul>
<li><span data-ttu-id="522e8-134"><strong>Manuale</strong> &ndash; Il valore viene immesso manualmente.</span><span class="sxs-lookup"><span data-stu-id="522e8-134"><strong>Manual</strong> &ndash; The value is manually entered.</span></span></li>
<li><span data-ttu-id="522e8-135"><strong>Transazione fiscale</strong> &ndash; Il valore viene raccolto dalle transazioni fiscali.</span><span class="sxs-lookup"><span data-stu-id="522e8-135"><strong>Tax transaction</strong> &ndash; The value is collected from the tax transactions.</span></span></li>
<li><span data-ttu-id="522e8-136"><strong>Totale</strong> &ndash; Il valore viene calcolato utilizzando una formula composta dai valori di altri campi (solo i campi per i quali il valore del campo <strong>Calcolo</strong> non è selezionato).</span><span class="sxs-lookup"><span data-stu-id="522e8-136"><strong>Total</strong> &ndash; The value is calculated by using a formula that consists of the values of other fields (but only fields where in <strong>Calculation</strong> field value is not selected).</span></span></li>
</ul>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-137">Valore</span><span class="sxs-lookup"><span data-stu-id="522e8-137">Value</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-138">Immettere un valore per il campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-138">Enter a value for the field.</span></span> <span data-ttu-id="522e8-139">È possibile modificare questo valore solo quando il campo <strong>Calcolo</strong> è impostato su <strong>Manuale</strong>.</span><span class="sxs-lookup"><span data-stu-id="522e8-139">You can edit this value only when the <strong>Calculation</strong> field is set to <strong>Manual.</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-140">Imposta sul reddito</span><span class="sxs-lookup"><span data-stu-id="522e8-140">Tax</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-141">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="522e8-141">Select one of the following values:</span></span></p>
<p><span data-ttu-id="522e8-142">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Imponibile</strong> &ndash; Il campo dovrebbe rappresentare un imponibile.</span><span class="sxs-lookup"><span data-stu-id="522e8-142">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Tax base</strong> &ndash; The field should represent a tax base.</span></span></p>
<p><span data-ttu-id="522e8-143">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Importo imposta </strong>&ndash; Il campo dovrebbe rappresentare un importo dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="522e8-143">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Tax amount </strong>&ndash; The field should represent a tax amount.</span></span></p>
<p><span data-ttu-id="522e8-144">È possibile modificare questo valore solo quando il campo <strong>Calcolo</strong> è impostato su <strong>Transazioni fiscali</strong>.</span><span class="sxs-lookup"><span data-stu-id="522e8-144">You can edit this value only when the <strong>Calculation</strong> field is set to <strong>Tax transactions.</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-145">Segno</span><span class="sxs-lookup"><span data-stu-id="522e8-145">Sign</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-146">Immettere <strong>1</strong> se il valore deve essere rappresentato così com'è.</span><span class="sxs-lookup"><span data-stu-id="522e8-146">Enter <strong>1</strong> if the value should be represented as is.</span></span> <span data-ttu-id="522e8-147">Immettere <strong>-1</strong> se i valori devono essere invertiti.</span><span class="sxs-lookup"><span data-stu-id="522e8-147">Enter <strong>-1</strong> if the value should be inverted.</span></span></p>
<p><span data-ttu-id="522e8-148">È possibile modificare questo valore solo quando il campo <strong>Calcolo</strong> è impostato su <strong>Transazioni fiscali o Totale</strong>.</span><span class="sxs-lookup"><span data-stu-id="522e8-148">You can edit this value only when the <strong>Calculation</strong> field is set to <strong>Tax transactions or Total.</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-149">IVA non deducibile</span><span class="sxs-lookup"><span data-stu-id="522e8-149">Nondeductible sales tax</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-150">Se il <strong>campo Calcolo è impostato su Transazione fiscale </strong>e il <strong>campo Imposta è impostato su Importo imposta, selezionare questa casella di controllo</strong> per ridurre l'importo dell'imposta calcolato in base all'importo dell'imposta non detraibile.</span><span class="sxs-lookup"><span data-stu-id="522e8-150">If the <strong>Calculation field is set to Tax transaction, </strong>and the <strong>Tax field is set to Tax amount, select this check box</strong> to reduce the calculated tax amount on the non-deductible tax amount.</span></span></p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>

> [!NOTE]
> <span data-ttu-id="522e8-151">Se vengono apportate modifiche nella dichiarazione, è necessario modificare le impostazioni del campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-151">If any changes are made in the declaration, you must change the field settings.</span></span>

10. <span data-ttu-id="522e8-152">Per i campi in cui il campo **Calcolo** è impostato su **Transazioni fiscali** nella scheda **Codici imposta selezionati**, selezionare **Nuovo** per aggiungere una riga per ogni codice IVA che deve essere reso disponibile come valore di campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-152">For fields where the **Calculation** field is set to **Tax transactions**, on the **Selected tax codes** tab, select **New** to a add a line for each sales tax code that should be available as a field value.</span></span>

    ![Pagina Impostazioni comunicazione annuale imposte, scheda Codici imposta selezionati](media/2_Yearly_tax_communication_setup.png)

11. <span data-ttu-id="522e8-154">Selezionare **Eccezioni** per configurare i conti principali che dovrebbero essere esclusi dalla query.</span><span class="sxs-lookup"><span data-stu-id="522e8-154">Select **Exceptions** to set up main accounts that should be excluded from the query.</span></span>

    <span data-ttu-id="522e8-155">Creare un numero sufficiente di codici IVA univoci in modo che ciascuno sia collegato a un singolo campo nella dichiarazione annuale.</span><span class="sxs-lookup"><span data-stu-id="522e8-155">Create enough unique sales tax codes so that each is linked to a single field in the yearly declaration.</span></span> <span data-ttu-id="522e8-156">Questo approccio consente di semplificare la configurazione della dichiarazione annuale.</span><span class="sxs-lookup"><span data-stu-id="522e8-156">This approach helps simplify the setup of the yearly declaration.</span></span>

    <span data-ttu-id="522e8-157">Se lo stesso codice IVA può essere collegato a più campi, è tuttavia necessario configurare filtri aggiuntivi per la transazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="522e8-157">However, if the same sales tax code can be linked to multiple fields, you should set up additional filters for the tax transaction.</span></span>

12. <span data-ttu-id="522e8-158">Selezionare **Query** e specificare regole di filtro aggiuntive per l'IVA registrata.</span><span class="sxs-lookup"><span data-stu-id="522e8-158">Select **Query**, and specify additional filtering rules for posted sales tax.</span></span> <span data-ttu-id="522e8-159">È ad esempio possibile specificare filtri aggiuntivi per la sezione relativa a direzione IVA o libro IVA.</span><span class="sxs-lookup"><span data-stu-id="522e8-159">For example, you can specify additional filters for the sales tax direction or sales tax book section.</span></span>

<span data-ttu-id="522e8-160">È possibile effettuare la seguente configurazione aggiuntiva per i campi in cui il campo **Calcolo** è impostato su **Totale**.</span><span class="sxs-lookup"><span data-stu-id="522e8-160">You can do the following additional setup for fields where the **Calculation** field is set to **Total**.</span></span> <span data-ttu-id="522e8-161">Il sistema può quindi calcolare automaticamente i valori per i tag che dovrebbero rappresentare un risultato calcolato utilizzando una formula composta dai valori di altri campi (solo i campi in cui il campo **Calcolo** non è impostato su **Totale**).</span><span class="sxs-lookup"><span data-stu-id="522e8-161">The system can then automatically calculate values for tags that should represent a result that is calculated by using a formula that consists of the values of other fields (but only fields where the **Calculation** field isn't set to **Total**).</span></span>

13. <span data-ttu-id="522e8-162">Seleziona la riga in cui il campo **Calcolo** è impostato su **Totale**.</span><span class="sxs-lookup"><span data-stu-id="522e8-162">Select the line where the **Calculation** field is set to **Total**.</span></span>
14. <span data-ttu-id="522e8-163">Nella scheda **Importo totale** selezionare **Nuovo** per aggiungere righe per tutti i campi da sommare.</span><span class="sxs-lookup"><span data-stu-id="522e8-163">On the **Total amount** tab, select **New** to add lines for all fields that should be totaled.</span></span>

    ![Pagina Impostazioni comunicazione annuale imposte, scheda Importo totale](media/3_Yearly_tax_communication_setup.png)

15. <span data-ttu-id="522e8-165">Impostare i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="522e8-165">Set the following fields.</span></span>

    | <span data-ttu-id="522e8-166">Nome campo</span><span class="sxs-lookup"><span data-stu-id="522e8-166">Field name</span></span> | <span data-ttu-id="522e8-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522e8-167">Description</span></span>                                                                                                                 |
    |------------|-----------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="522e8-168">Segno</span><span class="sxs-lookup"><span data-stu-id="522e8-168">Sign</span></span>       | <span data-ttu-id="522e8-169">Immettere **1** se il valore del campo deve essere accettato così com'è.</span><span class="sxs-lookup"><span data-stu-id="522e8-169">Enter **1** if the value from the field should be taken as is.</span></span> <span data-ttu-id="522e8-170">Immettere **-1** se il valore del campo deve essere invertito.</span><span class="sxs-lookup"><span data-stu-id="522e8-170">Enter **-1** if the value from the field should be inverted.</span></span> |
    | <span data-ttu-id="522e8-171">ID campo</span><span class="sxs-lookup"><span data-stu-id="522e8-171">Field ID</span></span>   | <span data-ttu-id="522e8-172">Selezionare il campo da sommare.</span><span class="sxs-lookup"><span data-stu-id="522e8-172">Select the field that should be totaled.</span></span> <span data-ttu-id="522e8-173">I campi in cui il campo **Calcolo** è impostato su **Totale** non possono essere selezionato qui.</span><span class="sxs-lookup"><span data-stu-id="522e8-173">Fields where the **Calculation** field is set to **Total** can't be selected here.</span></span> |

### <a name="formats-of-the-fields"></a><span data-ttu-id="522e8-174">Formati dei campi</span><span class="sxs-lookup"><span data-stu-id="522e8-174">Formats of the fields</span></span>

<span data-ttu-id="522e8-175">I valori dei campi possono in genere essere numerici (formato **NU**) o alfanumerici (formato **UN**).</span><span class="sxs-lookup"><span data-stu-id="522e8-175">Usually, fields values can be either numeric (**NU** format) or alphanumeric (**AN** format).</span></span>

- <span data-ttu-id="522e8-176">**Numerico (NU)** - Questi valori sono importi.</span><span class="sxs-lookup"><span data-stu-id="522e8-176">**Numeric (NU)** – These values are amounts.</span></span> <span data-ttu-id="522e8-177">Sono allineati a destra e hanno una lunghezza fissa di 16 caratteri.</span><span class="sxs-lookup"><span data-stu-id="522e8-177">They are right-aligned and have a fixed length of 16 characters.</span></span> <span data-ttu-id="522e8-178">I caratteri di spazio vengono utilizzati come riempimento,</span><span class="sxs-lookup"><span data-stu-id="522e8-178">Space characters are used for padding,</span></span>
- <span data-ttu-id="522e8-179">**Alfanumerico (AN)** - Questi valori sono stringhe.</span><span class="sxs-lookup"><span data-stu-id="522e8-179">**Alphanumeric (AN)** – These values are strings.</span></span> <span data-ttu-id="522e8-180">Sono allineati a sinistra e hanno una lunghezza fissa di 16 caratteri.</span><span class="sxs-lookup"><span data-stu-id="522e8-180">They are left-aligned and have a fixed length of 16 characters.</span></span> <span data-ttu-id="522e8-181">I caratteri di spazio vengono utilizzati come riempimento.</span><span class="sxs-lookup"><span data-stu-id="522e8-181">Space characters are used for padding.</span></span>

<span data-ttu-id="522e8-182">Nella colonna **Formato** è possibile specificare un formato di campo.</span><span class="sxs-lookup"><span data-stu-id="522e8-182">In the **Format** column, you can specify a field format.</span></span> <span data-ttu-id="522e8-183">Oltre a **NU** e **AN**, sono disponibili per la selezione anche i seguenti formati.</span><span class="sxs-lookup"><span data-stu-id="522e8-183">In addition to **NU** and **AN**, the following formats are available for selection.</span></span>

| <span data-ttu-id="522e8-184">Formattazione</span><span class="sxs-lookup"><span data-stu-id="522e8-184">Format</span></span> | <span data-ttu-id="522e8-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522e8-185">Description</span></span>                                                                                                                                               | <span data-ttu-id="522e8-186">Carattere di spaziatura interna</span><span class="sxs-lookup"><span data-stu-id="522e8-186">Padding character</span></span> | <span data-ttu-id="522e8-187">Esempio</span><span class="sxs-lookup"><span data-stu-id="522e8-187">Example</span></span>                                    |
|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|--------------------------------------------|
| <span data-ttu-id="522e8-188">CF</span><span class="sxs-lookup"><span data-stu-id="522e8-188">CF</span></span>     | <span data-ttu-id="522e8-189">Codice fiscale (16 caratteri)</span><span class="sxs-lookup"><span data-stu-id="522e8-189">Fiscal code (16 characters)</span></span>                                                                                                                               | <span data-ttu-id="522e8-190">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-190">Space</span></span>             | <span data-ttu-id="522e8-191">"XXXXXX11X11X111X"</span><span class="sxs-lookup"><span data-stu-id="522e8-191">"XXXXXX11X11X111X"</span></span>                         |
| <span data-ttu-id="522e8-192">PI</span><span class="sxs-lookup"><span data-stu-id="522e8-192">PI</span></span>     | <span data-ttu-id="522e8-193">Partita IVA (11 caratteri)</span><span class="sxs-lookup"><span data-stu-id="522e8-193">Tax-exempt number (11 characters)</span></span>                                                                                                                         | <span data-ttu-id="522e8-194">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-194">Space</span></span>             | <span data-ttu-id="522e8-195">"11111111111"</span><span class="sxs-lookup"><span data-stu-id="522e8-195">"11111111111"</span></span>                              |
| <span data-ttu-id="522e8-196">CN</span><span class="sxs-lookup"><span data-stu-id="522e8-196">CN</span></span>     | <span data-ttu-id="522e8-197">Codice fiscale numerico (11 caratteri)</span><span class="sxs-lookup"><span data-stu-id="522e8-197">Numeric fiscal code (11 characters)</span></span>                                                                                                                       | <span data-ttu-id="522e8-198">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-198">Space</span></span>             | <span data-ttu-id="522e8-199">"11111111111"</span><span class="sxs-lookup"><span data-stu-id="522e8-199">"11111111111"</span></span>                              |
| <span data-ttu-id="522e8-200">PN</span><span class="sxs-lookup"><span data-stu-id="522e8-200">PN</span></span>     | <span data-ttu-id="522e8-201">Abbreviazione automobilistica per la provincia italiana (ad esempio, la provincia di nascita), un simbolo di spazio e il valore "EE" per paesi o regioni estere</span><span class="sxs-lookup"><span data-stu-id="522e8-201">Automotive abbreviation for the Italian province (for example, the province of birth), a space symbol and the value "EE" for foreign countries or regions</span></span> | <span data-ttu-id="522e8-202">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-202">Space</span></span>             | <span data-ttu-id="522e8-203">"BO   "</span><span class="sxs-lookup"><span data-stu-id="522e8-203">"BO   "</span></span>                                    |
| <span data-ttu-id="522e8-204">Nx</span><span class="sxs-lookup"><span data-stu-id="522e8-204">Nx</span></span>     | <span data-ttu-id="522e8-205">Come **NU**, ma rappresenta formati come **N1**, **N2** e **N3** nelle linee guida ufficiali</span><span class="sxs-lookup"><span data-stu-id="522e8-205">Like **NU**, but represents formats such as **N1**, **N2**, and **N3** in official guidelines</span></span>                                                             | <span data-ttu-id="522e8-206">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-206">Space</span></span>             | <span data-ttu-id="522e8-207">"            1234"</span><span class="sxs-lookup"><span data-stu-id="522e8-207">"            1234"</span></span>                         |
| <span data-ttu-id="522e8-208">CB</span><span class="sxs-lookup"><span data-stu-id="522e8-208">CB</span></span>     | <span data-ttu-id="522e8-209">Casella di controllo, dove i valori sono **1** per uno stato selezionato e **0** per uno stato cancellato</span><span class="sxs-lookup"><span data-stu-id="522e8-209">Check box, where the values are **1** for a selected state and **0** for a cleared state</span></span>                                                                  | <span data-ttu-id="522e8-210">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="522e8-210">Not applicable</span></span>    | <span data-ttu-id="522e8-211">"1"</span><span class="sxs-lookup"><span data-stu-id="522e8-211">"1"</span></span>                                        |
| <span data-ttu-id="522e8-212">NN</span><span class="sxs-lookup"><span data-stu-id="522e8-212">NN</span></span>     | <span data-ttu-id="522e8-213">Importo positivo (11 caratteri) o importo negativo (11 caratteri)</span><span class="sxs-lookup"><span data-stu-id="522e8-213">Positive amount (11 characters) or negative amount (11 characters)</span></span>                                                                                        | <span data-ttu-id="522e8-214">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-214">Space</span></span>             | <span data-ttu-id="522e8-215">"       1234" "      -1234"</span><span class="sxs-lookup"><span data-stu-id="522e8-215">"       1234" "      -1234"</span></span>                |
| <span data-ttu-id="522e8-216">DT</span><span class="sxs-lookup"><span data-stu-id="522e8-216">DT</span></span>     | <span data-ttu-id="522e8-217">Data in formato GGMMAAAA format</span><span class="sxs-lookup"><span data-stu-id="522e8-217">Date in DDMMYYYY format</span></span>                                                                                                                                   | <span data-ttu-id="522e8-218">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="522e8-218">Not applicable</span></span>    | <span data-ttu-id="522e8-219">"01012020"</span><span class="sxs-lookup"><span data-stu-id="522e8-219">"01012020"</span></span>                                 |
| <span data-ttu-id="522e8-220">DA</span><span class="sxs-lookup"><span data-stu-id="522e8-220">DA</span></span>     | <span data-ttu-id="522e8-221">Data in formato AAAA</span><span class="sxs-lookup"><span data-stu-id="522e8-221">Date in YYYY format</span></span>                                                                                                                                       | <span data-ttu-id="522e8-222">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="522e8-222">Not applicable</span></span>    | <span data-ttu-id="522e8-223">"2020"</span><span class="sxs-lookup"><span data-stu-id="522e8-223">"2020"</span></span>                                     |
| <span data-ttu-id="522e8-224">NP</span><span class="sxs-lookup"><span data-stu-id="522e8-224">NP</span></span>     | <span data-ttu-id="522e8-225">Campo numerico positivo</span><span class="sxs-lookup"><span data-stu-id="522e8-225">Positive numeric field</span></span>                                                                                                                                    | <span data-ttu-id="522e8-226">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-226">Space</span></span>             | <span data-ttu-id="522e8-227">"            1234"</span><span class="sxs-lookup"><span data-stu-id="522e8-227">"            1234"</span></span>                         |
| <span data-ttu-id="522e8-228">PC</span><span class="sxs-lookup"><span data-stu-id="522e8-228">PC</span></span>     | <span data-ttu-id="522e8-229">Percentuale e tasso, con un massimo di tre posizioni decimali</span><span class="sxs-lookup"><span data-stu-id="522e8-229">Percentage and rate that have a maximum of three decimal places</span></span>                                                                                           | <span data-ttu-id="522e8-230">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-230">Space</span></span>             | <span data-ttu-id="522e8-231">"   100" "   33,333"</span><span class="sxs-lookup"><span data-stu-id="522e8-231">"   100" "   33,333"</span></span>                       |
| <span data-ttu-id="522e8-232">PR</span><span class="sxs-lookup"><span data-stu-id="522e8-232">PR</span></span>     | <span data-ttu-id="522e8-233">Abbreviazione automobilistica per la provincia italiana (ad esempio, la provincia di residenza)</span><span class="sxs-lookup"><span data-stu-id="522e8-233">Automotive abbreviation for the Italian province (for example, the province of residence)</span></span>                                                                 | <span data-ttu-id="522e8-234">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-234">Space</span></span>             | <span data-ttu-id="522e8-235">"BO   "</span><span class="sxs-lookup"><span data-stu-id="522e8-235">"BO   "</span></span>                                    |
| <span data-ttu-id="522e8-236">QU</span><span class="sxs-lookup"><span data-stu-id="522e8-236">QU</span></span>     | <span data-ttu-id="522e8-237">Campo numerico con un massimo di cinque posizioni decimali</span><span class="sxs-lookup"><span data-stu-id="522e8-237">Numeric field that has a maximum of five decimal places</span></span>                                                                                                   | <span data-ttu-id="522e8-238">BARRA SPAZIATRICE</span><span class="sxs-lookup"><span data-stu-id="522e8-238">Space</span></span>             | <span data-ttu-id="522e8-239">"    1000,16234" "   0,99" "   3000000,50"</span><span class="sxs-lookup"><span data-stu-id="522e8-239">"    1000,16234" "   0,99" "   3000000,50"</span></span> |

## <a name="create-a-yearly-tax-declaration"></a><span data-ttu-id="522e8-240">Creare una dichiarazione fiscale annuale</span><span class="sxs-lookup"><span data-stu-id="522e8-240">Create a yearly tax declaration</span></span>

1. <span data-ttu-id="522e8-241">Andare a **Imposta \> Dichiarazioni \> IVA \> Comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-241">Go to **Tax \> Declarations \> Sales tax \> Yearly tax communication**.</span></span>
2. <span data-ttu-id="522e8-242">Selezionare **Creare nuovo** per creare informazioni sull'intestazione per il report **Comunicazione annuale imposte** per l'anno precedente.</span><span class="sxs-lookup"><span data-stu-id="522e8-242">Select **Create new** to create header information for the **Yearly tax communication** report for the previous year.</span></span> <span data-ttu-id="522e8-243">Il numero di righe create corrisponde al numero di libri IVA italiani.</span><span class="sxs-lookup"><span data-stu-id="522e8-243">The number of lines that are created matches the number of Italian sales tax books.</span></span>

![Pagina Comunicazione annuale imposte, scheda Panoramica](media/4_Yearly_tax_communication_setup.png)

3. <span data-ttu-id="522e8-245">Nella scheda **Generale** rivedere le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="522e8-245">On the **General** tab, review the following information.</span></span>

    | <span data-ttu-id="522e8-246">Campo</span><span class="sxs-lookup"><span data-stu-id="522e8-246">Field</span></span>                | <span data-ttu-id="522e8-247">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522e8-247">Description</span></span>                                                                                                                                                                                                                                                                                                                |
    |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="522e8-248">ID comunicazione imposte</span><span class="sxs-lookup"><span data-stu-id="522e8-248">Tax communication ID</span></span> | <span data-ttu-id="522e8-249">Numero di identificazione del report **Comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-249">The identification number of the **Yearly tax communication** report.</span></span>                                                                                                                                                                                                                                                      |
    | <span data-ttu-id="522e8-250">Anni</span><span class="sxs-lookup"><span data-stu-id="522e8-250">Years</span></span>                | <span data-ttu-id="522e8-251">Anno della comunicazione imposte.</span><span class="sxs-lookup"><span data-stu-id="522e8-251">The year of the tax communication.</span></span> <span data-ttu-id="522e8-252">Questo campo viene automaticamente impostato sull'anno precedente.</span><span class="sxs-lookup"><span data-stu-id="522e8-252">This field is automatically set to the previous year.</span></span> <span data-ttu-id="522e8-253">Se si crea il report nel 2020, questo campo è ad esempio impostato su **2019**.</span><span class="sxs-lookup"><span data-stu-id="522e8-253">For example, if you're creating the report in 2020, this field is set to **2019**.</span></span>                                                                                                                                                |
    | <span data-ttu-id="522e8-254">Codice ATECOFIN</span><span class="sxs-lookup"><span data-stu-id="522e8-254">ATECOFIN Code</span></span>        | <span data-ttu-id="522e8-255">Codice imposta associato alla classificazione di possibili attività della società.</span><span class="sxs-lookup"><span data-stu-id="522e8-255">The tax code that is associated with the classification of possible company activities.</span></span> <span data-ttu-id="522e8-256">Questo campo viene compilato dalla pagina **Libri IVA italiani**.</span><span class="sxs-lookup"><span data-stu-id="522e8-256">This field is filled in from the **Italian sales tax books** page.</span></span> <span data-ttu-id="522e8-257">Per ulteriori informazioni, vedere [Libri IVA italiani](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-fiscal-books#set-up-sales-tax-books).</span><span class="sxs-lookup"><span data-stu-id="522e8-257">For more information, see [Italian sales tax books](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-fiscal-books#set-up-sales-tax-books).</span></span> |
    | <span data-ttu-id="522e8-258">Esportato</span><span class="sxs-lookup"><span data-stu-id="522e8-258">Exported</span></span>             | <span data-ttu-id="522e8-259">Valore che indica se il file con estensione ivc è stato esportato.</span><span class="sxs-lookup"><span data-stu-id="522e8-259">A value that indicates whether the .ivc file has been exported.</span></span> <span data-ttu-id="522e8-260">Questo campo e i due campi successivi vengono impostati automaticamente quando si seleziona **Esporta e genera file**.</span><span class="sxs-lookup"><span data-stu-id="522e8-260">This field and the next two fields are automatically set when you select **Export and generate file**.</span></span>                                                                                                                                                     |
    | <span data-ttu-id="522e8-261">Data di esportazione</span><span class="sxs-lookup"><span data-stu-id="522e8-261">Date of export</span></span>       | <span data-ttu-id="522e8-262">Data in cui è stato esportato il file con estensione .ivc.</span><span class="sxs-lookup"><span data-stu-id="522e8-262">The date when the .ivc file was exported.</span></span>                                                                                                                                                                                                                                                                                  |
    | <span data-ttu-id="522e8-263">Nome file di esportazione</span><span class="sxs-lookup"><span data-stu-id="522e8-263">Export file name</span></span>     | <span data-ttu-id="522e8-264">Nome del file con estensione ivc che è stato esportato.</span><span class="sxs-lookup"><span data-stu-id="522e8-264">The name of the .ivc file that was exported.</span></span>                                                                                                                                                                                                                                                                               |

4. <span data-ttu-id="522e8-265">Selezionare la riga richiesta, quindi selezionare **Apri** per aprire la pagina **Comunicazione annuale imposte** che contiene le informazioni sulla dichiarazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="522e8-265">Select the required line, and then select **Open** to open the **Yearly tax communication** page, which has the information about the selected declaration.</span></span>
5. <span data-ttu-id="522e8-266">Nella scheda **Intestazione** rivedere le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="522e8-266">On the **Header** tab, review the following information.</span></span>

<table>
<tbody>
<tr>
<td>
<p><span data-ttu-id="522e8-267"><strong>Campo</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-267"><strong>Field</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-268"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-268"><strong>Description</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-269"><strong>ID comunicazione imposte</strong>, <strong>Codice ATECOFIN</strong> e <strong>Anni</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-269"><strong>Tax communication ID</strong>, <strong>ATECOFIN Code</strong>, and <strong>Years</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-270">Questi campi vengono impostati come descritto nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="522e8-270">These fields are set as described in the previous table.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-271">Sezione <strong>Informazioni società</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-271"><strong>Company information</strong> section</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-272">Rivedi le informazioni sulla società.</span><span class="sxs-lookup"><span data-stu-id="522e8-272">Review the information about the company.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-273"><strong>Ragione sociale</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-273"><strong>Company name</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-274">Nome della società per cui è creato il report <strong>Comunicazione annuale imposte</strong>.</span><span class="sxs-lookup"><span data-stu-id="522e8-274">The name of the company that the <strong>Yearly tax communication</strong> report is created for.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-275"><strong>Codice fiscale</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-275"><strong>Fiscal code</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-276">Codice fiscale della società.</span><span class="sxs-lookup"><span data-stu-id="522e8-276">The fiscal code of the company.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-277"><strong>Partita IVA società</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-277"><strong>Company tax registration number</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-278">Partita IVA della società.</span><span class="sxs-lookup"><span data-stu-id="522e8-278">The tax registration number of the company.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-279">Sezione <strong>Dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-279"><strong>Declarer</strong> section</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-280">Immettere le informazioni sul dichiarante.</span><span class="sxs-lookup"><span data-stu-id="522e8-280">Enter information about declarer.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-281"><strong>Tipo di dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-281"><strong>Type of declarer</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-282">Selezionare il tipo di dichiarante.</span><span class="sxs-lookup"><span data-stu-id="522e8-282">Select the type of declarer:</span></span></p>
<p><span data-ttu-id="522e8-283">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Registrazione per la stessa persona giuridica</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-283">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Filing for same legal entity</strong></span></span></p>
<p><span data-ttu-id="522e8-284">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-284">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Filing through fiscal assistance center (CAF)</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-285"><strong>Codice fiscale CAF</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-285"><strong>CAF fiscal code</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-286">Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> immettere il codice fiscale del centro di assistenza fiscale.</span><span class="sxs-lookup"><span data-stu-id="522e8-286">If you selected <strong>Filing through fiscal assistance center (CAF)</strong> in the <strong>Type of declarer</strong> field, enter the fiscal code of the fiscal assistance center.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-287"><strong>Obbligo CAF</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-287"><strong>CAF obligation</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-288">Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="522e8-288">If you selected <strong>Filing through fiscal assistance center (CAF)</strong> in the <strong>Type of declarer</strong> field, select one of the following values:</span></span></p>
<p><span data-ttu-id="522e8-289">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazione preparata da persona giuridica</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-289">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Declaration prepared by legal entity</strong></span></span></p>
<p><span data-ttu-id="522e8-290">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazione preparata dal dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-290">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Declaration prepared by declarer</strong></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-291"><strong>Numero iscrizione CAF</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-291"><strong>CAF inscription number</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-292">Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> immettere il numero di iscrizione del centro di assistenza fiscale.</span><span class="sxs-lookup"><span data-stu-id="522e8-292">If you selected <strong>Filing through fiscal assistance center (CAF)</strong> in the <strong>Type of declarer</strong> field, enter the inscription number of the fiscal assistance center.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-293"><strong>Data di trasmissione CAF</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-293"><strong>CAF transmission date</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-294">Se è stato selezionato <strong>Registrazione attraverso il centro di assistenza fiscale (CAF)</strong> nel campo <strong>Tipo di dichiarante</strong> immetter la data di trasmissione.</span><span class="sxs-lookup"><span data-stu-id="522e8-294">If you selected <strong>Filing through fiscal assistance center (CAF)</strong> in the <strong>Type of declarer</strong> field, enter transmission date.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-295">Sezione <strong>Dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-295"><strong>Writer</strong> section</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-296">Specificare le informazioni sul dichiarante, se il dichiarante è diverso dal contribuente.</span><span class="sxs-lookup"><span data-stu-id="522e8-296">Specify information about the declarer, if the declarer differs from the taxpayer.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-297"><strong>Dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-297"><strong>Writer</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-298">Selezionare il nome del dipendente.</span><span class="sxs-lookup"><span data-stu-id="522e8-298">Select the employee's name.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-299"><strong>Codice fiscale dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-299"><strong>Writer fiscal code</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-300">Immettere il codice fiscale del dichiarante.</span><span class="sxs-lookup"><span data-stu-id="522e8-300">Enter the fiscal code of the declarer.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-301"><strong>Ruolo dichiarante</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-301"><strong>Writer role</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-302">Selezionare il ruolo del dichiarante:</span><span class="sxs-lookup"><span data-stu-id="522e8-302">Select the declarer's role:</span></span></p>
<p><span data-ttu-id="522e8-303">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Rappresentante legale</strong> &ndash; Il dichiarante è un socio gerente.</span><span class="sxs-lookup"><span data-stu-id="522e8-303">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Legal representative</strong> &ndash; The declarer is a managing partner.</span></span></p>
<p><span data-ttu-id="522e8-304">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Amministratore di minorenni</strong> &ndash; Il dichiarante è un amministratore per minori o per persone con disabilità.</span><span class="sxs-lookup"><span data-stu-id="522e8-304">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Administrator of underaged</strong> &ndash; The declarer is an administrator for minors or for people who have disabilities.</span></span></p>
<p><span data-ttu-id="522e8-305">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Controllore delle merci sequestrate</strong> &ndash; Il dichiarante è un amministratore di beni confiscati.</span><span class="sxs-lookup"><span data-stu-id="522e8-305">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Controller of sequestered goods</strong> &ndash; The declarer is an administrator for seized goods.</span></span></p>
<p><span data-ttu-id="522e8-306">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Rappresentante fiscale</strong> &ndash; Il dichiarante è un rappresentante fiscale per non residenti.</span><span class="sxs-lookup"><span data-stu-id="522e8-306">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Fiscal representative</strong> &ndash; The declarer is a tax representative for non-residents.</span></span></p>
<p><span data-ttu-id="522e8-307">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Legatario generale</strong> &ndash; Il dichiarante è un erede della società.</span><span class="sxs-lookup"><span data-stu-id="522e8-307">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>General legatee</strong> &ndash; The declarer is an heir to the company.</span></span></p>
<p><span data-ttu-id="522e8-308">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore</strong> &ndash; Il dipendente è l'amministratore di una liquidazione volontaria.</span><span class="sxs-lookup"><span data-stu-id="522e8-308">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidator</strong> &ndash; The declarer is an administrator for voluntary liquidation.</span></span></p>
<p><span data-ttu-id="522e8-309">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Operatore straordinario</strong> &ndash; Il dipendente è un rappresentante che invia le dichiarazioni fiscali per conto di una società che non esiste più in seguito a una fusione, un'acquisizione o un'altra transazione straordinaria.</span><span class="sxs-lookup"><span data-stu-id="522e8-309">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Extraordinary operator</strong> &ndash; The declarer is a representative who submits tax declarations on behalf of a company that no longer exists because of a merger, acquisition, or other extraordinary transaction.</span></span></p>
<p><span data-ttu-id="522e8-310">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Curatore fallimentare</strong> &ndash; Il dichiarante è un curatore fallimentare.</span><span class="sxs-lookup"><span data-stu-id="522e8-310">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Bankruptcy curator</strong> &ndash; The declarer is an administrator for bankruptcy.</span></span></p>
<p><span data-ttu-id="522e8-311">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore commissionato</strong> &ndash; Il dipendente è l'amministratore di una liquidazione.</span><span class="sxs-lookup"><span data-stu-id="522e8-311">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Commissioned liquidator</strong> &ndash; The declarer is an administrator for liquidation.</span></span></p>
<p><span data-ttu-id="522e8-312">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Non residente</strong> &ndash; Il dichiarante è un rappresentante fiscale per non residenti.</span><span class="sxs-lookup"><span data-stu-id="522e8-312">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Non-resident</strong> &ndash; The declarer is a tax representative for non-residents.</span></span> <span data-ttu-id="522e8-313">Il rappresentante fiscale trasferisce gli articoli per conto di un non residente e non paga l'IVA.</span><span class="sxs-lookup"><span data-stu-id="522e8-313">The tax representative transfers items on behalf of a non-resident and doesn't pay VAT.</span></span> <span data-ttu-id="522e8-314">La società o l'individuo che accetta gli articoli è tenuto a pagare l'IVA.</span><span class="sxs-lookup"><span data-stu-id="522e8-314">The company or individual who accepts the items is required to pay VAT.</span></span> <span data-ttu-id="522e8-315">Per maggiori informazio, vedere l'articolo 44, comma 3, del D.L.</span><span class="sxs-lookup"><span data-stu-id="522e8-315">For more information, see article 44, paragraph 3, of D.L.</span></span> <span data-ttu-id="522e8-316">N. 331/1993.</span><span class="sxs-lookup"><span data-stu-id="522e8-316">No 331/1993.</span></span></p>
<p><span data-ttu-id="522e8-317">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Tutore legale</strong> &ndash; Il dipendente è tutore di un minore che è erede della società.</span><span class="sxs-lookup"><span data-stu-id="522e8-317">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Legal guardian</strong> &ndash; The declarer is a guardian for a minor who is an heir to the company.</span></span></p>
<p><span data-ttu-id="522e8-318">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore un unico proprietario</strong> &ndash; Il dipendente è un amministratore responsabile della liquidazione delle apparecchiature della società durante una liquidazione volontaria.</span><span class="sxs-lookup"><span data-stu-id="522e8-318">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Sole proprietor liquidator</strong> &ndash; The declarer is an administrator who is responsible for disposing of company equipment during a voluntary liquidation.</span></span></p>
<p><span data-ttu-id="522e8-319">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Responsabile proprietà</strong> &ndash; Il dichiarante è il responsabile di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="522e8-319">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Property manager</strong> &ndash; The declarer is a manager of the property.</span></span></p>
<p><span data-ttu-id="522e8-320">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Rappresentante pubblico</strong> &ndash; Il dichiarante è un rappresentante che firma le dichiarazioni per conto del governo.</span><span class="sxs-lookup"><span data-stu-id="522e8-320">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Public representative</strong> &ndash; The declarer is a representative who signs the declarations on behalf of the government.</span></span></p>
<p><span data-ttu-id="522e8-321">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Liquidatore pubblico</strong> &ndash; Il dichiarante è un liquidatore che lavora per conto del governo.</span><span class="sxs-lookup"><span data-stu-id="522e8-321">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Public liquidator</strong> &ndash; The declarer is a liquidator who works on behalf of the government.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-322"><strong>Data appuntamento</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-322"><strong>Appointment date</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-323">Immettere la data di nomina del dichiarante.</span><span class="sxs-lookup"><span data-stu-id="522e8-323">Enter the date of the declarer's nomination.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-324"><strong>Codice fiscale</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-324"><strong>Fiscal code</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-325">Immettere il codice fiscale della società dichiarante.</span><span class="sxs-lookup"><span data-stu-id="522e8-325">Enter the fiscal code of the declaring company.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-326"><strong>Città o paese straniero di nascita</strong>, <strong>Provincia di nascita</strong>, <strong>Data di nascita</strong>, <strong>Genere</strong>, <strong>Nome</strong>, <strong>Cognome</strong> e <strong>Telefono</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-326"><strong>Birth city or foreign country</strong>, <strong>Birth county</strong>, <strong>Birth date</strong>, <strong>Gender</strong>, <strong>First name</strong>, <strong>Last name</strong>, and <strong>Telephone</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-327">Immettere informazioni aggiuntive sul dichiarante.</span><span class="sxs-lookup"><span data-stu-id="522e8-327">Enter additional information about declarer.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-328"><strong>Appuntamenti</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-328"><strong>Dates</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-329">Specificare le informazioni sull'avvio della procedura e le date di fine.</span><span class="sxs-lookup"><span data-stu-id="522e8-329">Specify information about procedure start and end dates.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-330"><strong>Data di inizio procedura</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-330"><strong>Procedure start date</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-331">Immettere una data di inizio della procedura.</span><span class="sxs-lookup"><span data-stu-id="522e8-331">Enter the start date of the procedure.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-332"><strong>Data di fine procedura</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-332"><strong>Procedure end date</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-333">Immettere una data di fine della procedura.</span><span class="sxs-lookup"><span data-stu-id="522e8-333">Enter the end date of the procedure.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-334"><strong>Correzione</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-334"><strong>Correction</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-335">Selezionare il tipo di correzione:</span><span class="sxs-lookup"><span data-stu-id="522e8-335">Select the type of correction:</span></span></p>
<p><span data-ttu-id="522e8-336">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Correzione</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-336">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Correction</strong></span></span></p>
<p><span data-ttu-id="522e8-337">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazione supplementare</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-337">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Supplementary declaration</strong></span></span></p>
<p><span data-ttu-id="522e8-338">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazioni aggiuntive</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-338">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Additional declarations</strong></span></span></p>
<p><span data-ttu-id="522e8-339">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Dichiarazioni aggiuntive (2)</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-339">&middot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Additional declarations (2)</strong></span></span></p>
</td>
</tr>
</tbody>
</table>
<p>&nbsp;</p>
<p>&nbsp;</p>

6. <span data-ttu-id="522e8-340">Nella scheda **Righe del report** rivedi o modifica le righe e gli importi configurati in precedenza per il report **Comunicazione annuale imposte** nella pagina **Impostazioni comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-340">On the **Report lines** tab, review or edit the lines and amounts that you previously set up for the **Yearly tax communication** report on the **Yearly tax communication setup** page.</span></span> <span data-ttu-id="522e8-341">Per le righe in cui il campo **Calcolo** è impostato su **Manuale**, inserisci manualmente gli importi.</span><span class="sxs-lookup"><span data-stu-id="522e8-341">For lines where the **Calculation** field is set to **Manual**, manually enter the amounts.</span></span>
7. <span data-ttu-id="522e8-342">Nella scheda **Dettagli** rivedere o modificare i dettagli di ciascuna riga del report **Comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-342">On the **Details** tab, review or edit the details of each line on the **Yearly tax communication** report.</span></span>
8. <span data-ttu-id="522e8-343">Chiudi la pagina **Comunicazione annuale imposte** che contiene le informazioni sulla dichiarazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="522e8-343">Close the **Yearly tax communication** page that has the information about the selected declaration.</span></span>
9. <span data-ttu-id="522e8-344">Nella pagina **Comunicazione annuale imposte** che contiene l'elenco delle dichiarazioni, selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="522e8-344">On the **Yearly tax communication** page that has the list of declarations, select **Export**.</span></span>
10. <span data-ttu-id="522e8-345">Nella finestra di dialogo **Crea file di esportazione** immettere un valore nel campo **Nome file**.</span><span class="sxs-lookup"><span data-stu-id="522e8-345">In the **Create export file** dialog box, in the **File name** field, enter a value.</span></span> <span data-ttu-id="522e8-346">Selezionare quindi **OK** per creare ed esportare il file con estensione ivc.</span><span class="sxs-lookup"><span data-stu-id="522e8-346">Then select **OK** to create and export the .ivc file.</span></span>
11. <span data-ttu-id="522e8-347">Selezionare **Elimina esportazione** per eliminare il file con estensione ivc creato ed esportato.</span><span class="sxs-lookup"><span data-stu-id="522e8-347">Select **Delete export** to delete the .ivc file that has been created and exported.</span></span>

## <a name="appendix-1-structure-of-the-yearly-vat-declaration"></a><span data-ttu-id="522e8-348">Appendice 1.</span><span class="sxs-lookup"><span data-stu-id="522e8-348">Appendix 1.</span></span> <span data-ttu-id="522e8-349">Struttura della dichiarazione IVA annuale</span><span class="sxs-lookup"><span data-stu-id="522e8-349">Structure of the yearly VAT declaration</span></span>

<span data-ttu-id="522e8-350">La tabella seguente fornisce un esempio della struttura della dichiarazione IVA annuale.</span><span class="sxs-lookup"><span data-stu-id="522e8-350">The following table provides an example of the structure of the yearly VAT declaration.</span></span> <span data-ttu-id="522e8-351">Questo esempio si basa sulla dichiarazione del 2020.</span><span class="sxs-lookup"><span data-stu-id="522e8-351">This example is based on the 2020 declaration.</span></span> <span data-ttu-id="522e8-352">Le sezioni che non sono incluse nell'esempio di configurazione sono riportate in *corsivo*.</span><span class="sxs-lookup"><span data-stu-id="522e8-352">Sections that aren't included in the setup example are *italicized*.</span></span>

<table>
<tbody>
<tr>
<td>
<p><span data-ttu-id="522e8-353"><strong>Sezione (EN)</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-353"><strong>Section (EN)</strong></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-354"><strong>Campi</strong></span><span class="sxs-lookup"><span data-stu-id="522e8-354"><strong>Fields</strong></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-355"><em>PARTE VA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-355"><em>PART VA</em></span></span></p>
<p><span data-ttu-id="522e8-356"><em>INFORMAZIONI E DATI RELATIVI ALL'ATTIVITÀ</em></span><span class="sxs-lookup"><span data-stu-id="522e8-356"><em>INFORMATION AND DATA RELATING TO THE ACTIVITY</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-357"><em>Sezione 1 - Dati analitici generali</em></span><span class="sxs-lookup"><span data-stu-id="522e8-357"><em>Section 1 - General analytical data</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-358"><em>VA001001-VA005004</em></span><span class="sxs-lookup"><span data-stu-id="522e8-358"><em>VA001001-VA005004</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-359"><em>Sezione 2 - Riepilogo dei dati relativi a tutte le attività svolte</em></span><span class="sxs-lookup"><span data-stu-id="522e8-359"><em>Section 2 - Data summary relating to all activities carried out</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-360"><em>VA010001-VA015001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-360"><em>VA010001-VA015001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-361"><em>PARTE VB</em></span><span class="sxs-lookup"><span data-stu-id="522e8-361"><em>PART VB</em></span></span></p>
<p><span data-ttu-id="522e8-362"><em>DATI RELATIVI AI DETTAGLI IDENTIFICATIVI DEI RAPPORTI FINANZIARI</em></span><span class="sxs-lookup"><span data-stu-id="522e8-362"><em>DATA RELATING TO IDENTIFICATION DETAILS OF FINANCIAL RELATIONS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-363"><em>VB001001-VB007004</em></span><span class="sxs-lookup"><span data-stu-id="522e8-363"><em>VB001001-VB007004</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-364">PARTE VC</span><span class="sxs-lookup"><span data-stu-id="522e8-364">PART VC</span></span></p>
<p><span data-ttu-id="522e8-365">ESPORTATORI E OPERATORI ASSOCIATI</span><span class="sxs-lookup"><span data-stu-id="522e8-365">EXPORTERS AND ASSOCIATED OPERATORS</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-366">Acquisti e importazioni senza l'applicazione dell'imposta sul valore aggiunto (IVA) relativa a tutte le attività svolte.</span><span class="sxs-lookup"><span data-stu-id="522e8-366">Purchases and imports without the application of value added tax relating to all activities carried out.</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-367">VC001001-VC014003</span><span class="sxs-lookup"><span data-stu-id="522e8-367">VC001001-VC014003</span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-368"><em>PARTE VD</em></span><span class="sxs-lookup"><span data-stu-id="522e8-368"><em>PART VD</em></span></span></p>
<p><span data-ttu-id="522e8-369"><em>CESSIONE DEL CREDITO IVA DA PARTE DI SOCIETÀ DI GESTIONE CESPITI</em></span><span class="sxs-lookup"><span data-stu-id="522e8-369"><em>TRANSFER OF VAT CREDIT BY ASSET MANAGEMENT COMPANIES</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-370"><em>Sezione 1 - Società che effettua la cessione - Elenco delle società o degli enti cessionari</em></span><span class="sxs-lookup"><span data-stu-id="522e8-370"><em>Section 1 - Transferring company - List of transferee companies or body</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-371"><em>VD001001-VD021002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-371"><em>VD001001-VD021002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-372"><em>Sezione 2 - Società o enti che effettuano la cessione - Elenco delle società cedenti</em></span><span class="sxs-lookup"><span data-stu-id="522e8-372"><em>Section 2 - Company or transferring body - List of ceding companies</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-373"><em>VD031001-VD056001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-373"><em>VD031001-VD056001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-374">PARTE VE</span><span class="sxs-lookup"><span data-stu-id="522e8-374">PART VE</span></span></p>
<p><span data-ttu-id="522e8-375">CALCOLO DEL FATTURATO AZIENDALE E DELL'IMPOSTA RELATIVA ALLE OPERAZIONI TASSABILI</span><span class="sxs-lookup"><span data-stu-id="522e8-375">CALCULATION OF BUSINESS TURNOVER AND THE TAX RELATIVE TO TAXABLE OPERATIONS</span></span></p>
<p><span data-ttu-id="522e8-376">(Commento: vendite e IVA a debito sulle vendite)</span><span class="sxs-lookup"><span data-stu-id="522e8-376">(Comment: Sales and output VAT on sales)</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-377"><em>Sezione 1 - Conferimento di prodotti agricoli e cessioni da parte di agricoltori esenti (in caso di superamento del limite di più di un terzo)</em></span><span class="sxs-lookup"><span data-stu-id="522e8-377"><em>Section 1 - Conferring of agricultural products and transfers by exempt agriculturalists (in the case of the limit being exceeded by more than a third)</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-378"><em>VE001001-VE012002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-378"><em>VE001001-VE012002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-379">Sezione 2 - Operazioni agricole tassabili e operazioni commerciali o professionali tassabili</span><span class="sxs-lookup"><span data-stu-id="522e8-379">Section 2 - Taxable agricultural operations and taxable commercial or professional operations</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-380">VE020001-VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-380">VE020001-VE023002</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-381">Sezione 3 - Totale importo tassabile e imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-381">Section 3 - Total taxable amount and tax</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-382">VE024001-VE026002</span><span class="sxs-lookup"><span data-stu-id="522e8-382">VE024001-VE026002</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-383">Sezione 4 - Altre operazioni</span><span class="sxs-lookup"><span data-stu-id="522e8-383">Section 4 - Other operations</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-384">VE030001-VE040001</span><span class="sxs-lookup"><span data-stu-id="522e8-384">VE030001-VE040001</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-385">Sezione 5 - Fatturato aziendale</span><span class="sxs-lookup"><span data-stu-id="522e8-385">Section 5 - Business turnover</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-386">VE050001</span><span class="sxs-lookup"><span data-stu-id="522e8-386">VE050001</span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-387">PARTE VF</span><span class="sxs-lookup"><span data-stu-id="522e8-387">PART VF</span></span></p>
<p><span data-ttu-id="522e8-388">OPERAZIONI PASSIVITÀ E IVA AMMISSIBILE IN DETRAZIONE</span><span class="sxs-lookup"><span data-stu-id="522e8-388">LIABILITY OPERATIONS AND ADMISSIBLE DEDUCTIBLE VAT</span></span></p>
<p><span data-ttu-id="522e8-389">(Commento: acquisti e IVA a credito sugli acquisti)</span><span class="sxs-lookup"><span data-stu-id="522e8-389">(Comment: Purchases and input VAT on purchases)</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-390">Sezione 1 - Importo totale degli acquisti effettuati nel territorio nazionale di acquisti e importazioni intracomunitarie</span><span class="sxs-lookup"><span data-stu-id="522e8-390">Section 1 - Total amount of purchases carried out in the national territory of intracommunity purchases and imports</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-391">VF001001-VF022001</span><span class="sxs-lookup"><span data-stu-id="522e8-391">VF001001-VF022001</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-392">Sezione 2 - Totale acquisti e importazioni, totale imposte, acquisti intracomunitari, importazioni e acquisti da San Marino</span><span class="sxs-lookup"><span data-stu-id="522e8-392">Section 2 - Total purchases and imports, total tax, intra-community purchases, imports, and purchases from San Marino</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-393">VF023001-VF027004</span><span class="sxs-lookup"><span data-stu-id="522e8-393">VF023001-VF027004</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-394">Sezione 3 - Calcolo dell'IVA ammissibile in detrazione</span><span class="sxs-lookup"><span data-stu-id="522e8-394">Section 3 - Calculation of admissible deductible VAT</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-395">VF030001-VF030009</span><span class="sxs-lookup"><span data-stu-id="522e8-395">VF030001-VF030009</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-396">Sezione 3-A - Operazioni esenti</span><span class="sxs-lookup"><span data-stu-id="522e8-396">Section 3-A - Exempt operations</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-397"><em>VF031001-VF033001</em>, VF034001-VF037001</span><span class="sxs-lookup"><span data-stu-id="522e8-397"><em>VF031001-VF033001</em>, VF034001-VF037001</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-398"><em>Sezione 3-B - Azienda agricola (art. 34)</em></span><span class="sxs-lookup"><span data-stu-id="522e8-398"><em>Section 3-B - Agricultural business (art.34)</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-399"><em>VF038001-VF055001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-399"><em>VF038001-VF055001</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-400"><em>Sezione 3-C - Casi speciali</em></span><span class="sxs-lookup"><span data-stu-id="522e8-400"><em>Section 3-C - Special cases</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-401"><em>VF060001-VF062002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-401"><em>VF060001-VF062002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-402">Sezione 4 - IVA ammissibile in detrazione</span><span class="sxs-lookup"><span data-stu-id="522e8-402">Section 4 - Admissible deductible VAT</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-403">VF070001-VF071001</span><span class="sxs-lookup"><span data-stu-id="522e8-403">VF070001-VF071001</span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-404">PARTE VJ</span><span class="sxs-lookup"><span data-stu-id="522e8-404">PART VJ</span></span></p>
<p><span data-ttu-id="522e8-405">CALCOLO DELL'IMPOSTA SU ALCUNI TIPI DI OPERAZIONI</span><span class="sxs-lookup"><span data-stu-id="522e8-405">CALCULATION OF TAX ON CERTAIN TYPES OF OPERATIONS</span></span></p>
<p><span data-ttu-id="522e8-406">(Commento: IVA a debito su reverse charge su acquisti)</span><span class="sxs-lookup"><span data-stu-id="522e8-406">(Comment: Output VAT on purchase reverse charge)</span></span></p>
</td>
</tr>
<tr>
<td>
<p>&nbsp;</p>
</td>
<td>
<p><span data-ttu-id="522e8-407">VJ001001-VJ019002</span><span class="sxs-lookup"><span data-stu-id="522e8-407">VJ001001-VJ019002</span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-408"><em>PARTE VI</em></span><span class="sxs-lookup"><span data-stu-id="522e8-408"><em>PART VI</em></span></span></p>
<p><span data-ttu-id="522e8-409"><em>DICHIARAZIONI DI INTENTO RICEVUTE</em></span><span class="sxs-lookup"><span data-stu-id="522e8-409"><em>DECLARATIONS OF INTENT RECEIVED</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-410"><em>VI001001-VI006002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-410"><em>VI001001-VI006002</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-411"><em>PARTE VH</em></span><span class="sxs-lookup"><span data-stu-id="522e8-411"><em>PART VH</em></span></span></p>
<p><span data-ttu-id="522e8-412"><em>MODIFICHE DELLE COMUNICAZIONI PERIODICHE</em></span><span class="sxs-lookup"><span data-stu-id="522e8-412"><em>CHANGES OF PERIODIC COMMUNICATIONS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-413"><em>VH001001-VH017001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-413"><em>VH001001-VH017001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-414"><em>PARTE VM</em></span><span class="sxs-lookup"><span data-stu-id="522e8-414"><em>PART VM</em></span></span></p>
<p><span data-ttu-id="522e8-415"><em>PAGAMENTO PER LE REGISTRAZIONI DI AUTOMOBILI UE</em></span><span class="sxs-lookup"><span data-stu-id="522e8-415"><em>PAYMENT FOR EU AUTOMOBILE REGISTRATIONS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-416"><em>VM001001-VM012001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-416"><em>VM001001-VM012001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-417"><em>PARTE VK</em></span><span class="sxs-lookup"><span data-stu-id="522e8-417"><em>PART VK</em></span></span></p>
<p><span data-ttu-id="522e8-418"><em>AZIENDA CONTROLLANTE E CONTROLLATA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-418"><em>CONTROLLING AND CONTROLLED COMPANY</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-419"><em>Sezione 1 &ndash; Dati generali</em></span><span class="sxs-lookup"><span data-stu-id="522e8-419"><em>Section 1 &ndash; General data</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-420"><em>VK001001-VK001004</em></span><span class="sxs-lookup"><span data-stu-id="522e8-420"><em>VK001001-VK001004</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-421"><em>Sezione 2 - Calcolo dell'eccedenza fiscale</em></span><span class="sxs-lookup"><span data-stu-id="522e8-421"><em>Section 2 - Calculation of tax surplus</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-422"><em>VK020001-VK028001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-422"><em>VK020001-VK028001</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-423"><em>Sezione 3 - Cessazione del controllo durante l'anno Dati relativi al periodo di controllo</em></span><span class="sxs-lookup"><span data-stu-id="522e8-423"><em>Section 3 - Termination of control during the year Data relating to the period of control</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-424"><em>VK030001-VK036001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-424"><em>VK030001-VK036001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-425"><em>PARTE VN</em></span><span class="sxs-lookup"><span data-stu-id="522e8-425"><em>PART VN</em></span></span></p>
<p><span data-ttu-id="522e8-426"><em>DICHIARAZIONI SUPPLEMENTARI A FAVORE</em></span><span class="sxs-lookup"><span data-stu-id="522e8-426"><em>SUPPLEMENTAL DECLARATIONS IN FAVOUR</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-427"><em>VN001001-VN004005</em></span><span class="sxs-lookup"><span data-stu-id="522e8-427"><em>VN001001-VN004005</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-428"><em>PARTE VQ</em></span><span class="sxs-lookup"><span data-stu-id="522e8-428"><em>PART VQ</em></span></span></p>
<p><span data-ttu-id="522e8-429"><em>PAGAMENTI PERIODICI OMESSI</em></span><span class="sxs-lookup"><span data-stu-id="522e8-429"><em>OMITTED PERIODICAL PAYMENTS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-430"><em>VQ001001-VQ005010</em></span><span class="sxs-lookup"><span data-stu-id="522e8-430"><em>VQ001001-VQ005010</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-431">PARTE VL</span><span class="sxs-lookup"><span data-stu-id="522e8-431">PART VL</span></span></p>
<p><span data-ttu-id="522e8-432">PAGAMENTO DELL'IMPOSTA ANNUALE</span><span class="sxs-lookup"><span data-stu-id="522e8-432">PAYMENT OF ANNUAL TAX</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-433">Sezione 1 - Calcolo dell'IVA dovuta o dell'IVA a credito per il periodo fiscale</span><span class="sxs-lookup"><span data-stu-id="522e8-433">Section 1 - Calculation of VAT due or input VAT for the tax period</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-434">VL001001-VL004001</span><span class="sxs-lookup"><span data-stu-id="522e8-434">VL001001-VL004001</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-435">Sezione 2 - Credito dell'anno precedente</span><span class="sxs-lookup"><span data-stu-id="522e8-435">Section 2 - Credit from previous year</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-436">VL008001-VL012002</span><span class="sxs-lookup"><span data-stu-id="522e8-436">VL008001-VL012002</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-437">Sezione 3 - Calcolo dell'IVA a debito o a credito relativa a tutte le attività svolte</span><span class="sxs-lookup"><span data-stu-id="522e8-437">Section 3 - Calculation of output or input VAT relating to all the activities carried out</span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-438">VL020001-VL040001</span><span class="sxs-lookup"><span data-stu-id="522e8-438">VL020001-VL040001</span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-439"><em>PARTE VP</em></span><span class="sxs-lookup"><span data-stu-id="522e8-439"><em>PART VP</em></span></span></p>
<p><span data-ttu-id="522e8-440"><em>PAGAMENTO IMPOSTE</em></span><span class="sxs-lookup"><span data-stu-id="522e8-440"><em>TAX PAYMENT</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-441"><em>VP001001-VP014002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-441"><em>VP001001-VP014002</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-442"><em>PARTE VT</em></span><span class="sxs-lookup"><span data-stu-id="522e8-442"><em>PART VT</em></span></span></p>
<p><span data-ttu-id="522e8-443"><em>INDICAZIONE SEPARATA DELLE OPERAZIONI EFFETTUATE RIGUARDANTE I CONSUMATORI FINALI E I TITOLARI DI PARTITA IVA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-443"><em>SEPARATE INDICATION OF OPERATIONS CARRIED OUT REGARDING END CONSUMERS AND HOLDERS OF VAT NUMBERS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-444"><em>VT001001-VT022002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-444"><em>VT001001-VT022002</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-445"><em>PARTE VX</em></span><span class="sxs-lookup"><span data-stu-id="522e8-445"><em>PART VX</em></span></span></p>
<p><span data-ttu-id="522e8-446"><em>CALCOLO DELL'IVA DA PAGARE O DEL CREDITO D'IMPOSTA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-446"><em>CALCULATION OF VAT TO BE PAID OR OF TAX CREDIT</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-447"><em>Per le persone che presentano il reso con più moduli compilare solo il modulo n. 01</em></span><span class="sxs-lookup"><span data-stu-id="522e8-447"><em>For persons presenting the return with several forms only fill in form no. 01</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-448"><em>VX001001-VX006002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-448"><em>VX001001-VX006002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-449"><em>RISERVATO ALLE SOCIETÀ PARTECIPANTI AL PAGAMENTO IN FASCIA IVA V</em></span><span class="sxs-lookup"><span data-stu-id="522e8-449"><em>RESERVED FOR THE COMPANIES PARTICIPATING IN THE VAT GROUP PAYMENT V</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-450"><em>VX007001-VX008001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-450"><em>VX007001-VX008001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-451"><em>PARTE VO</em></span><span class="sxs-lookup"><span data-stu-id="522e8-451"><em>PART VO</em></span></span></p>
<p><span data-ttu-id="522e8-452"><em>COMUNICAZIONE DI OPZIONI E REVOCHE</em></span><span class="sxs-lookup"><span data-stu-id="522e8-452"><em>COMMUNICATION OF OPTIONS AND REVOCATIONS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-453"><em>Sezione 1 - Opzioni, rinunce e revoche ai fini dell'IVA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-453"><em>Section 1 - Options, waivers, and revocations for the purpose of VAT</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-454"><em>VO001001-VO015002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-454"><em>VO001001-VO015002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-455"><em>Sezione 2 - Opzioni e revoche ai fini dell'IVA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-455"><em>Section 2 - Options, and revocations for the purpose of VAT</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-456"><em>VO020001-VO026001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-456"><em>VO020001-VO026001</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-457"><em>Sezione 3 - Opzioni e revoche ai fini dell'IVA e dell'imposta sul reddito</em></span><span class="sxs-lookup"><span data-stu-id="522e8-457"><em>Section 3 - Options and revocations for both VAT and income tax purposes</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-458"><em>VO030001-VO035001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-458"><em>VO030001-VO035001</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-459"><em>Sezione 4 - Opzioni e revoca in materia di imposte sull'intrattenimento</em></span><span class="sxs-lookup"><span data-stu-id="522e8-459"><em>Section 4 - Options and revocation regarding tax on entertainment</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-460"><em>VO040001-VO040002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-460"><em>VO040001-VO040002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-461"><em>Sezione 5 - Opzioni e revoca in materia di IRAP</em></span><span class="sxs-lookup"><span data-stu-id="522e8-461"><em>Section 5 - Options and revocation regarding IRAP</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-462"><em>VO050001-VO050002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-462"><em>VO050001-VO050002</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-463"><em>PARTE VG</em></span><span class="sxs-lookup"><span data-stu-id="522e8-463"><em>PART VG</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-464"><em>Sezione 1 - Società che partecipano alla compensazione dell'IVA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-464"><em>Section 1 - Companies participating in VAT compensation</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-465"><em>VG001001-VG004007</em></span><span class="sxs-lookup"><span data-stu-id="522e8-465"><em>VG001001-VG004007</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-466"><em>Sezione 2 - Società che partecipano alla catena di controllo ma non alla compensazione dell'IVA</em></span><span class="sxs-lookup"><span data-stu-id="522e8-466"><em>Section 2 - Companies participating in the control chain but not in VAT compensation</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-467"><em>VG005001-VG007006</em></span><span class="sxs-lookup"><span data-stu-id="522e8-467"><em>VG005001-VG007006</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-468"><em>Sezione 3 - Revoca</em></span><span class="sxs-lookup"><span data-stu-id="522e8-468"><em>Section 3 - Revocation</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-469"><em>VG008001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-469"><em>VG008001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-470"><em>PARTE VS</em></span><span class="sxs-lookup"><span data-stu-id="522e8-470"><em>PART VS</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-471"><em>Sezione 1 - Elenco delle società del gruppo</em></span><span class="sxs-lookup"><span data-stu-id="522e8-471"><em>Section 1 - List of companies in the group</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-472"><em>VS001001-VS012012</em></span><span class="sxs-lookup"><span data-stu-id="522e8-472"><em>VS001001-VS012012</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-473"><em>Sezione 2 - Dati di riepilogo</em></span><span class="sxs-lookup"><span data-stu-id="522e8-473"><em>Section 2 - Summary data</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-474"><em>VS020001-VS022002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-474"><em>VS020001-VS022002</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-475"><em>Sezione 3 - Garanzie della società controllante</em></span><span class="sxs-lookup"><span data-stu-id="522e8-475"><em>Section 3 - Guarantees of the controlling company</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-476"><em>VS030001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-476"><em>VS030001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-477"><em>PARTE VV</em></span><span class="sxs-lookup"><span data-stu-id="522e8-477"><em>PART VV</em></span></span></p>
<p><span data-ttu-id="522e8-478"><em>PAGAMENTI IMPOSTE PERIODICI DI GRUPPO</em></span><span class="sxs-lookup"><span data-stu-id="522e8-478"><em>PERIODICAL TAX PAYMENTS OF GROUP</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-479"><em>VV001001-VV017003</em></span><span class="sxs-lookup"><span data-stu-id="522e8-479"><em>VV001001-VV017003</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-480"><em>PARTE VW</em></span><span class="sxs-lookup"><span data-stu-id="522e8-480"><em>PART VW</em></span></span></p>
<p><span data-ttu-id="522e8-481"><em>PAGAMENTO DELL'IMPOSTA ANNUALE DI GRUPPO</em></span><span class="sxs-lookup"><span data-stu-id="522e8-481"><em>PAYMENT OF ANNUAL TAX OF GROUP</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-482"><em>Sezione 1 - Calcolo dell'IVA dovuta o dell'IVA a credito per il periodo fiscale</em></span><span class="sxs-lookup"><span data-stu-id="522e8-482"><em>Section 1 - Calculation of VAT due or input VAT for the tax period</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-483"><em>VW001001-VW004001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-483"><em>VW001001-VW004001</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="522e8-484"><em>Sezione 2 - Calcolo dell'IVA a debito o a credito</em></span><span class="sxs-lookup"><span data-stu-id="522e8-484"><em>Section 2 - Calculation of output or input VAT</em></span></span></p>
</td>
<td>
<p><span data-ttu-id="522e8-485"><em>VW020001-VW040001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-485"><em>VW020001-VW040001</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-486"><em>PARTE VY</em></span><span class="sxs-lookup"><span data-stu-id="522e8-486"><em>PART VY</em></span></span></p>
<p><span data-ttu-id="522e8-487"><em>CALCOLO DELL'IVA DOVUTA O DEL CREDITO D'IMPOSTA DI GRUPPO</em></span><span class="sxs-lookup"><span data-stu-id="522e8-487"><em>CALCULATION OF VAT PAYABLE OR GROUP TAX CREDIT</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-488"><em>VY001001-VY006002</em></span><span class="sxs-lookup"><span data-stu-id="522e8-488"><em>VY001001-VY006002</em></span></span></p>
</td>
</tr>
<tr>
<td colspan="2">
<p><span data-ttu-id="522e8-489"><em>PARTE VZ</em></span><span class="sxs-lookup"><span data-stu-id="522e8-489"><em>PART VZ</em></span></span></p>
<p><span data-ttu-id="522e8-490"><em>ECCEDENZE DI GRUPPO DETRAIBILI (ANNI PRECEDENTI)</em></span><span class="sxs-lookup"><span data-stu-id="522e8-490"><em>DEDUCTIBLE GROUP SURPLUSES (PREVIOUS YEARS)</em></span></span></p>
</td>
</tr>
<tr>
<td>
<p><em>&nbsp;</em></p>
</td>
<td>
<p><span data-ttu-id="522e8-491"><em>VZ001001-VZ002001</em></span><span class="sxs-lookup"><span data-stu-id="522e8-491"><em>VZ001001-VZ002001</em></span></span></p>
</td>
</tr>
</tbody>
</table>

### <a name="example"></a><span data-ttu-id="522e8-492">Esempio</span><span class="sxs-lookup"><span data-stu-id="522e8-492">Example</span></span>

<span data-ttu-id="522e8-493">Ecco un esempio per la persona giuridica **ITCO**.</span><span class="sxs-lookup"><span data-stu-id="522e8-493">Here is an example for the **ITCO** legal entity.</span></span>

1. <span data-ttu-id="522e8-494">Andare a **Imposta** \> **Imposte indirette** \> **IVA** \> **Codici IVA** e configurare i seguenti codici IVA.</span><span class="sxs-lookup"><span data-stu-id="522e8-494">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**, and set up the following sales tax codes.</span></span>

    | <span data-ttu-id="522e8-495">Codice IVA</span><span class="sxs-lookup"><span data-stu-id="522e8-495">Sales tax code</span></span> | <span data-ttu-id="522e8-496">Percentuale</span><span class="sxs-lookup"><span data-stu-id="522e8-496">Percentage</span></span> | <span data-ttu-id="522e8-497">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522e8-497">Description</span></span>                                                                              |
    |----------------|------------|------------------------------------------------------------------------------------------|
    | <span data-ttu-id="522e8-498">DOMP22</span><span class="sxs-lookup"><span data-stu-id="522e8-498">DOMP22</span></span>         | <span data-ttu-id="522e8-499">22</span><span class="sxs-lookup"><span data-stu-id="522e8-499">22</span></span>         | <span data-ttu-id="522e8-500">Acquisti nazionali con un'aliquota del 22%.</span><span class="sxs-lookup"><span data-stu-id="522e8-500">Domestic purchases at a rate of 22 percent.</span></span>                                              |
    | <span data-ttu-id="522e8-501">DOMS22</span><span class="sxs-lookup"><span data-stu-id="522e8-501">DOMS22</span></span>         | <span data-ttu-id="522e8-502">22</span><span class="sxs-lookup"><span data-stu-id="522e8-502">22</span></span>         | <span data-ttu-id="522e8-503">Vendite nazionali con un'aliquota del 22%.</span><span class="sxs-lookup"><span data-stu-id="522e8-503">Domestic sales at a rate of 22 percent.</span></span>                                                  |
    | <span data-ttu-id="522e8-504">EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-504">EUP22</span></span>          | <span data-ttu-id="522e8-505">22</span><span class="sxs-lookup"><span data-stu-id="522e8-505">22</span></span>         | <span data-ttu-id="522e8-506">Acquisti UE con un'aliquota del 22%, dove l'opzione **IVA intracomunitaria** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="522e8-506">EU purchases at a rate of 22 percent, where the **Use tax** option is set to **Yes**.</span></span>    |
    | <span data-ttu-id="522e8-507">RC</span><span class="sxs-lookup"><span data-stu-id="522e8-507">RC</span></span>             | <span data-ttu-id="522e8-508">22</span><span class="sxs-lookup"><span data-stu-id="522e8-508">22</span></span>         | <span data-ttu-id="522e8-509">Reverse charge sulle vendite interne per cui l'opzione **Esenzione** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="522e8-509">Domestic sales reverse charge where the **Exempt** option is set to **Yes**.</span></span>             |
    | <span data-ttu-id="522e8-510">EUS</span><span class="sxs-lookup"><span data-stu-id="522e8-510">EUS</span></span>            | <span data-ttu-id="522e8-511">22</span><span class="sxs-lookup"><span data-stu-id="522e8-511">22</span></span>         | <span data-ttu-id="522e8-512">Vendite nell'UE per cui l'opzione **Esenzione** è impostata su **Sì** nella pagina **Fasce IVA**.</span><span class="sxs-lookup"><span data-stu-id="522e8-512">EU sales where the **Exempt** option is set to **Yes** on the **Sales tax groups** page.</span></span> |

2. <span data-ttu-id="522e8-513">Andare a **Imposta** \> **Impostazione** \> **Parametri** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="522e8-513">Go to **Tax** \> **Setup** \> **Parameters** \> **General ledger parameters**.</span></span>
3. <span data-ttu-id="522e8-514">Nella scheda **Sequenze numeriche** selezionare una sequenza numerica per il riferimento **ID comunicazione imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-514">On the **Number sequences** tab, select a number sequence for the **Tax communication ID** reference.</span></span>
4. <span data-ttu-id="522e8-515">Nella scheda **IVA**, nel campo **Mapping formato** della Scheda dettaglio **Comunicazione annuale imposte** selezionare il formato **Comunicazione annuale imposte (IT)**.</span><span class="sxs-lookup"><span data-stu-id="522e8-515">On the **Sales tax** tab, on the **Yearly tax communication** FastTab, in the **Format mapping** field, select **Yearly tax communication (IT)**.</span></span>
5. <span data-ttu-id="522e8-516">Andare a **Imposta** \> **Impostazione** \> **IVA** \> **Impostazioni comunicazione annuale imposte** e aggiungere le seguenti righe.</span><span class="sxs-lookup"><span data-stu-id="522e8-516">Go to **Tax** \> **Setup** \> **Sales tax** \> **Yearly tax communication setup**, and add the following lines.</span></span>

    | <span data-ttu-id="522e8-517">ID campo</span><span class="sxs-lookup"><span data-stu-id="522e8-517">Field ID</span></span> | <span data-ttu-id="522e8-518">Descrizione</span><span class="sxs-lookup"><span data-stu-id="522e8-518">Description</span></span>                                                                                                                                              | <span data-ttu-id="522e8-519">Formattazione</span><span class="sxs-lookup"><span data-stu-id="522e8-519">Format</span></span> | <span data-ttu-id="522e8-520">Calcolo</span><span class="sxs-lookup"><span data-stu-id="522e8-520">Calculation</span></span>      | <span data-ttu-id="522e8-521">Imposta sul reddito</span><span class="sxs-lookup"><span data-stu-id="522e8-521">Tax</span></span>        | <span data-ttu-id="522e8-522">Segno</span><span class="sxs-lookup"><span data-stu-id="522e8-522">Sign</span></span> | <span data-ttu-id="522e8-523">Scheda Codice IVA selezionato</span><span class="sxs-lookup"><span data-stu-id="522e8-523">Selected sales tax code tab</span></span> | <span data-ttu-id="522e8-524">Scheda Totali</span><span class="sxs-lookup"><span data-stu-id="522e8-524">Totals tab</span></span>                   |
    |----------|----------------------------------------------------------------------------------------------------------------------------------------------------------|--------|------------------|------------|------|-----------------------------|------------------------------|
    | <span data-ttu-id="522e8-525">VE023001</span><span class="sxs-lookup"><span data-stu-id="522e8-525">VE023001</span></span> | <span data-ttu-id="522e8-526">Imponibile del 22% delle transazioni fiscali agricole (art. 34, c.1) e delle operazioni professionali</span><span class="sxs-lookup"><span data-stu-id="522e8-526">22% tax base of agricultural tax transactions (art.34, c.1) and professional operations</span></span>                                                                  | <span data-ttu-id="522e8-527">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-527">NU</span></span>     | <span data-ttu-id="522e8-528">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-528">Tax transactions</span></span> | <span data-ttu-id="522e8-529">Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-529">Tax base</span></span>   | <span data-ttu-id="522e8-530">1</span><span class="sxs-lookup"><span data-stu-id="522e8-530">1</span></span>    | <span data-ttu-id="522e8-531">DOMS22</span><span class="sxs-lookup"><span data-stu-id="522e8-531">DOMS22</span></span>                      |                              |
    | <span data-ttu-id="522e8-532">VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-532">VE023002</span></span> | <span data-ttu-id="522e8-533">Base imponibile del 22% su transazioni fiscali agricole (art. 34, c.1) e operazioni professionali</span><span class="sxs-lookup"><span data-stu-id="522e8-533">22% tax on agricultural tax transactions (art.34, c.1) and professional operations</span></span>                                                                       | <span data-ttu-id="522e8-534">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-534">NU</span></span>     | <span data-ttu-id="522e8-535">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-535">Tax transactions</span></span> | <span data-ttu-id="522e8-536">Imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-536">Tax amount</span></span> | <span data-ttu-id="522e8-537">1</span><span class="sxs-lookup"><span data-stu-id="522e8-537">1</span></span>    | <span data-ttu-id="522e8-538">DOMS22</span><span class="sxs-lookup"><span data-stu-id="522e8-538">DOMS22</span></span>                      |                              |
    | <span data-ttu-id="522e8-539">VE030003</span><span class="sxs-lookup"><span data-stu-id="522e8-539">VE030003</span></span> | <span data-ttu-id="522e8-540">Vendite intracomunitarie</span><span class="sxs-lookup"><span data-stu-id="522e8-540">Intra-community sales</span></span>                                                                                                                                    | <span data-ttu-id="522e8-541">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-541">NU</span></span>     | <span data-ttu-id="522e8-542">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-542">Tax transactions</span></span> | <span data-ttu-id="522e8-543">Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-543">Tax base</span></span>   | <span data-ttu-id="522e8-544">1</span><span class="sxs-lookup"><span data-stu-id="522e8-544">1</span></span>    | <span data-ttu-id="522e8-545">EUS</span><span class="sxs-lookup"><span data-stu-id="522e8-545">EUS</span></span>                         |                              |
    | <span data-ttu-id="522e8-546">VE030001</span><span class="sxs-lookup"><span data-stu-id="522e8-546">VE030001</span></span> | <span data-ttu-id="522e8-547">Operazioni totali che contribuiscono alla formazione del limite massimo (plafond)</span><span class="sxs-lookup"><span data-stu-id="522e8-547">Total operations which contribute to formation of ceiling (plafond)</span></span>                                                                                      | <span data-ttu-id="522e8-548">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-548">NU</span></span>     | <span data-ttu-id="522e8-549">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-549">Total</span></span>            |            | <span data-ttu-id="522e8-550">1</span><span class="sxs-lookup"><span data-stu-id="522e8-550">1</span></span>    |                             | <span data-ttu-id="522e8-551">VE030003</span><span class="sxs-lookup"><span data-stu-id="522e8-551">VE030003</span></span>                     |
    | <span data-ttu-id="522e8-552">VE035007</span><span class="sxs-lookup"><span data-stu-id="522e8-552">VE035007</span></span> | <span data-ttu-id="522e8-553">Vendite di prodotti elettronici</span><span class="sxs-lookup"><span data-stu-id="522e8-553">Sales of electronic products</span></span>                                                                                                                             | <span data-ttu-id="522e8-554">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-554">NU</span></span>     | <span data-ttu-id="522e8-555">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-555">Tax transactions</span></span> | <span data-ttu-id="522e8-556">Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-556">Tax base</span></span>   | <span data-ttu-id="522e8-557">1</span><span class="sxs-lookup"><span data-stu-id="522e8-557">1</span></span>    | <span data-ttu-id="522e8-558">RC</span><span class="sxs-lookup"><span data-stu-id="522e8-558">RC</span></span>                          |                              |
    | <span data-ttu-id="522e8-559">VE035001</span><span class="sxs-lookup"><span data-stu-id="522e8-559">VE035001</span></span> | <span data-ttu-id="522e8-560">Operazioni con applicazione di reverse charge</span><span class="sxs-lookup"><span data-stu-id="522e8-560">Operations with application of reverse charge</span></span>                                                                                                            | <span data-ttu-id="522e8-561">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-561">NU</span></span>     | <span data-ttu-id="522e8-562">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-562">Total</span></span>            |            | <span data-ttu-id="522e8-563">1</span><span class="sxs-lookup"><span data-stu-id="522e8-563">1</span></span>    |                             | <span data-ttu-id="522e8-564">VE035007</span><span class="sxs-lookup"><span data-stu-id="522e8-564">VE035007</span></span>                     |
    | <span data-ttu-id="522e8-565">VE050001</span><span class="sxs-lookup"><span data-stu-id="522e8-565">VE050001</span></span> | <span data-ttu-id="522e8-566">Fatturato aziendale</span><span class="sxs-lookup"><span data-stu-id="522e8-566">Business turnover</span></span>                                                                                                                                        | <span data-ttu-id="522e8-567">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-567">NU</span></span>     | <span data-ttu-id="522e8-568">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-568">Total</span></span>            |            | <span data-ttu-id="522e8-569">1</span><span class="sxs-lookup"><span data-stu-id="522e8-569">1</span></span>    |                             | <span data-ttu-id="522e8-570">VE023001, VE030003, VE035007</span><span class="sxs-lookup"><span data-stu-id="522e8-570">VE023001, VE030003, VE035007</span></span> |
    | <span data-ttu-id="522e8-571">VF014001</span><span class="sxs-lookup"><span data-stu-id="522e8-571">VF014001</span></span> | <span data-ttu-id="522e8-572">Acquisti e importazioni tassabili (22%)</span><span class="sxs-lookup"><span data-stu-id="522e8-572">Taxable purchases and imports (22%)</span></span>                                                                                                                      | <span data-ttu-id="522e8-573">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-573">NU</span></span>     | <span data-ttu-id="522e8-574">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-574">Tax transactions</span></span> | <span data-ttu-id="522e8-575">Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-575">Tax base</span></span>   | <span data-ttu-id="522e8-576">1</span><span class="sxs-lookup"><span data-stu-id="522e8-576">1</span></span>    | <span data-ttu-id="522e8-577">DOMP22, EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-577">DOMP22, EUP22</span></span>               |                              |
    | <span data-ttu-id="522e8-578">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-578">VF014002</span></span> | <span data-ttu-id="522e8-579">Imposta su acquisti e importazioni (22%)</span><span class="sxs-lookup"><span data-stu-id="522e8-579">Tax on purchases and imports (22%)</span></span>                                                                                                                       | <span data-ttu-id="522e8-580">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-580">NU</span></span>     | <span data-ttu-id="522e8-581">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-581">Tax transactions</span></span> | <span data-ttu-id="522e8-582">Imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-582">Tax amount</span></span> | <span data-ttu-id="522e8-583">1</span><span class="sxs-lookup"><span data-stu-id="522e8-583">1</span></span>    | <span data-ttu-id="522e8-584">DOMP22, EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-584">DOMP22, EUP22</span></span>               |                              |
    | <span data-ttu-id="522e8-585">VF023001</span><span class="sxs-lookup"><span data-stu-id="522e8-585">VF023001</span></span> | <span data-ttu-id="522e8-586">Totale ACQUISTI E IMPORTAZIONI</span><span class="sxs-lookup"><span data-stu-id="522e8-586">Total PURCHASES AND IMPORTS</span></span>                                                                                                                              | <span data-ttu-id="522e8-587">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-587">NU</span></span>     | <span data-ttu-id="522e8-588">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-588">Total</span></span>            |            | <span data-ttu-id="522e8-589">1</span><span class="sxs-lookup"><span data-stu-id="522e8-589">1</span></span>    |                             | <span data-ttu-id="522e8-590">VF014001</span><span class="sxs-lookup"><span data-stu-id="522e8-590">VF014001</span></span>                     |
    | <span data-ttu-id="522e8-591">VF023002</span><span class="sxs-lookup"><span data-stu-id="522e8-591">VF023002</span></span> | <span data-ttu-id="522e8-592">Totale ACQUISTI E IMPORTAZIONI - IMPOSTA</span><span class="sxs-lookup"><span data-stu-id="522e8-592">Total PURCHASES AND IMPORTS - TAX</span></span>                                                                                                                        | <span data-ttu-id="522e8-593">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-593">NU</span></span>     | <span data-ttu-id="522e8-594">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-594">Total</span></span>            |            | <span data-ttu-id="522e8-595">1</span><span class="sxs-lookup"><span data-stu-id="522e8-595">1</span></span>    |                             | <span data-ttu-id="522e8-596">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-596">VF014002</span></span>                     |
    | <span data-ttu-id="522e8-597">VF025002</span><span class="sxs-lookup"><span data-stu-id="522e8-597">VF025002</span></span> | <span data-ttu-id="522e8-598">Totale IMPOSTA SU ACQUISTI E IMPORTAZIONI TASSABILI</span><span class="sxs-lookup"><span data-stu-id="522e8-598">Total TAX ON TAXABLE PURCHASES AND IMPORTS</span></span>                                                                                                               | <span data-ttu-id="522e8-599">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-599">NU</span></span>     | <span data-ttu-id="522e8-600">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-600">Total</span></span>            |            | <span data-ttu-id="522e8-601">1</span><span class="sxs-lookup"><span data-stu-id="522e8-601">1</span></span>    |                             | <span data-ttu-id="522e8-602">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-602">VF014002</span></span>                     |
    | <span data-ttu-id="522e8-603">VF026001</span><span class="sxs-lookup"><span data-stu-id="522e8-603">VF026001</span></span> | <span data-ttu-id="522e8-604">Acquisti intracomunitari - Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-604">Intra-Community purchases – tax base</span></span>                                                                                                                     | <span data-ttu-id="522e8-605">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-605">NU</span></span>     | <span data-ttu-id="522e8-606">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-606">Tax transactions</span></span> | <span data-ttu-id="522e8-607">Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-607">Tax base</span></span>   | <span data-ttu-id="522e8-608">1</span><span class="sxs-lookup"><span data-stu-id="522e8-608">1</span></span>    | <span data-ttu-id="522e8-609">EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-609">EUP22</span></span>                       |                              |
    | <span data-ttu-id="522e8-610">VF026002</span><span class="sxs-lookup"><span data-stu-id="522e8-610">VF026002</span></span> | <span data-ttu-id="522e8-611">Acquisti intracomunitari - Imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-611">Intra-Community purchases - tax</span></span>                                                                                                                          | <span data-ttu-id="522e8-612">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-612">NU</span></span>     | <span data-ttu-id="522e8-613">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-613">Tax transactions</span></span> | <span data-ttu-id="522e8-614">Imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-614">Tax amount</span></span> | <span data-ttu-id="522e8-615">1</span><span class="sxs-lookup"><span data-stu-id="522e8-615">1</span></span>    | <span data-ttu-id="522e8-616">EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-616">EUP22</span></span>                       |                              |
    | <span data-ttu-id="522e8-617">VJ009001</span><span class="sxs-lookup"><span data-stu-id="522e8-617">VJ009001</span></span> | <span data-ttu-id="522e8-618">Acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art.</span><span class="sxs-lookup"><span data-stu-id="522e8-618">Intra-community purchases of goods (including purchases of industrial gold, pure silver, and goods as referred to in art.</span></span> <span data-ttu-id="522e8-619">74, commi 7 e 8)</span><span class="sxs-lookup"><span data-stu-id="522e8-619">74, paragraphs 7 and 8)</span></span>        | <span data-ttu-id="522e8-620">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-620">NU</span></span>     | <span data-ttu-id="522e8-621">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-621">Tax transactions</span></span> | <span data-ttu-id="522e8-622">Imponibile</span><span class="sxs-lookup"><span data-stu-id="522e8-622">Tax base</span></span>   | <span data-ttu-id="522e8-623">1</span><span class="sxs-lookup"><span data-stu-id="522e8-623">1</span></span>    | <span data-ttu-id="522e8-624">EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-624">EUP22</span></span>                       |                              |
    | <span data-ttu-id="522e8-625">VJ009002</span><span class="sxs-lookup"><span data-stu-id="522e8-625">VJ009002</span></span> | <span data-ttu-id="522e8-626">Imposta su acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art.</span><span class="sxs-lookup"><span data-stu-id="522e8-626">Tax on Intra-community purchases of goods (including purchases of industrial gold, pure silver, and goods as referred to in art.</span></span> <span data-ttu-id="522e8-627">74, commi 7 e 8)</span><span class="sxs-lookup"><span data-stu-id="522e8-627">74, paragraphs 7 and 8)</span></span> | <span data-ttu-id="522e8-628">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-628">NU</span></span>     | <span data-ttu-id="522e8-629">Transazioni fiscali</span><span class="sxs-lookup"><span data-stu-id="522e8-629">Tax transactions</span></span> | <span data-ttu-id="522e8-630">Imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-630">Tax amount</span></span> | <span data-ttu-id="522e8-631">1</span><span class="sxs-lookup"><span data-stu-id="522e8-631">1</span></span>    | <span data-ttu-id="522e8-632">EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-632">EUP22</span></span>                       |                              |
    | <span data-ttu-id="522e8-633">VJ019002</span><span class="sxs-lookup"><span data-stu-id="522e8-633">VJ019002</span></span> | <span data-ttu-id="522e8-634">Totale imposta</span><span class="sxs-lookup"><span data-stu-id="522e8-634">Total tax</span></span>                                                                                                                                                | <span data-ttu-id="522e8-635">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-635">NU</span></span>     | <span data-ttu-id="522e8-636">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-636">Total</span></span>            |            | <span data-ttu-id="522e8-637">1</span><span class="sxs-lookup"><span data-stu-id="522e8-637">1</span></span>    |                             | <span data-ttu-id="522e8-638">VJ009002</span><span class="sxs-lookup"><span data-stu-id="522e8-638">VJ009002</span></span>                     |
    | <span data-ttu-id="522e8-639">VE024001</span><span class="sxs-lookup"><span data-stu-id="522e8-639">VE024001</span></span> | <span data-ttu-id="522e8-640">Totale IMPONIBILE per operazioni attive</span><span class="sxs-lookup"><span data-stu-id="522e8-640">Total TAX BASE of active operations</span></span>                                                                                                                      | <span data-ttu-id="522e8-641">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-641">NU</span></span>     | <span data-ttu-id="522e8-642">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-642">Total</span></span>            |            | <span data-ttu-id="522e8-643">1</span><span class="sxs-lookup"><span data-stu-id="522e8-643">1</span></span>    |                             | <span data-ttu-id="522e8-644">VE023001</span><span class="sxs-lookup"><span data-stu-id="522e8-644">VE023001</span></span>                     |
    | <span data-ttu-id="522e8-645">VE024002</span><span class="sxs-lookup"><span data-stu-id="522e8-645">VE024002</span></span> | <span data-ttu-id="522e8-646">Totale IMPOSTA su operazioni attive</span><span class="sxs-lookup"><span data-stu-id="522e8-646">Total TAX on active operations</span></span>                                                                                                                           | <span data-ttu-id="522e8-647">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-647">NU</span></span>     | <span data-ttu-id="522e8-648">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-648">Total</span></span>            |            | <span data-ttu-id="522e8-649">1</span><span class="sxs-lookup"><span data-stu-id="522e8-649">1</span></span>    |                             | <span data-ttu-id="522e8-650">VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-650">VE023002</span></span>                     |
    | <span data-ttu-id="522e8-651">VE026002</span><span class="sxs-lookup"><span data-stu-id="522e8-651">VE026002</span></span> | <span data-ttu-id="522e8-652">Totale imposta (VE24 +/- VE25)</span><span class="sxs-lookup"><span data-stu-id="522e8-652">Total tax (VE24 +/- VE25)</span></span>                                                                                                                                | <span data-ttu-id="522e8-653">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-653">NU</span></span>     | <span data-ttu-id="522e8-654">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-654">Total</span></span>            |            | <span data-ttu-id="522e8-655">1</span><span class="sxs-lookup"><span data-stu-id="522e8-655">1</span></span>    |                             | <span data-ttu-id="522e8-656">VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-656">VE023002</span></span>                     |
    | <span data-ttu-id="522e8-657">VF037001</span><span class="sxs-lookup"><span data-stu-id="522e8-657">VF037001</span></span> | <span data-ttu-id="522e8-658">IVA ammissibile in detrazione (Sezione 3-A)</span><span class="sxs-lookup"><span data-stu-id="522e8-658">Admissible deductible VAT (Section 3-A)</span></span>                                                                                                                  | <span data-ttu-id="522e8-659">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-659">NU</span></span>     | <span data-ttu-id="522e8-660">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-660">Total</span></span>            |            | <span data-ttu-id="522e8-661">1</span><span class="sxs-lookup"><span data-stu-id="522e8-661">1</span></span>    |                             | <span data-ttu-id="522e8-662">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-662">VF014002</span></span>                     |
    | <span data-ttu-id="522e8-663">VF071002</span><span class="sxs-lookup"><span data-stu-id="522e8-663">VF071002</span></span> | <span data-ttu-id="522e8-664">IVA ammissibile in detrazione (Sezione 4)</span><span class="sxs-lookup"><span data-stu-id="522e8-664">Admissible deductible VAT (Section 4)</span></span>                                                                                                                    | <span data-ttu-id="522e8-665">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-665">NU</span></span>     | <span data-ttu-id="522e8-666">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-666">Total</span></span>            |            | <span data-ttu-id="522e8-667">1</span><span class="sxs-lookup"><span data-stu-id="522e8-667">1</span></span>    |                             | <span data-ttu-id="522e8-668">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-668">VF014002</span></span>                     |
    | <span data-ttu-id="522e8-669">VL001001</span><span class="sxs-lookup"><span data-stu-id="522e8-669">VL001001</span></span> | <span data-ttu-id="522e8-670">IVA a debito</span><span class="sxs-lookup"><span data-stu-id="522e8-670">Output VAT</span></span>                                                                                                                                               | <span data-ttu-id="522e8-671">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-671">NU</span></span>     | <span data-ttu-id="522e8-672">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-672">Total</span></span>            |            | <span data-ttu-id="522e8-673">1</span><span class="sxs-lookup"><span data-stu-id="522e8-673">1</span></span>    |                             | <span data-ttu-id="522e8-674">VJ009002, VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-674">VJ009002, VE023002</span></span>           |
    | <span data-ttu-id="522e8-675">VL002001</span><span class="sxs-lookup"><span data-stu-id="522e8-675">VL002001</span></span> | <span data-ttu-id="522e8-676">IVA deducibile</span><span class="sxs-lookup"><span data-stu-id="522e8-676">Deductible VAT</span></span>                                                                                                                                           | <span data-ttu-id="522e8-677">NU</span><span class="sxs-lookup"><span data-stu-id="522e8-677">NU</span></span>     | <span data-ttu-id="522e8-678">Totale</span><span class="sxs-lookup"><span data-stu-id="522e8-678">Total</span></span>            |            | <span data-ttu-id="522e8-679">1</span><span class="sxs-lookup"><span data-stu-id="522e8-679">1</span></span>    |                             | <span data-ttu-id="522e8-680">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-680">VF014002</span></span>                     |

> [!NOTE]
> <span data-ttu-id="522e8-681">Per visualizzare il modulo "Comunicazione annuale IVA" per l'anno 2020 e le relative istruzioni, vedere [Modello e istruzioni - IVA 2020](https://www.agenziaentrate.gov.it/portale/web/guest/iva-2020/modello-e-istruzioni-imprese).</span><span class="sxs-lookup"><span data-stu-id="522e8-681">To view the "Yearly VAT communication" form for the year 2020, and instructions for it, see [Model and instructions - VAT 2020](https://www.agenziaentrate.gov.it/portale/web/guest/iva-2020/modello-e-istruzioni-imprese).</span></span>

6. <span data-ttu-id="522e8-682">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="522e8-682">Refresh the page.</span></span>
7. <span data-ttu-id="522e8-683">Registrare le seguenti transazioni.</span><span class="sxs-lookup"><span data-stu-id="522e8-683">Post the following transactions.</span></span> <span data-ttu-id="522e8-684">Ad esempio, per le fatture cliente, andare a **contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="522e8-684">For example, for customer invoices, go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span> <span data-ttu-id="522e8-685">Per le fatture fornitore, andare a **Contabilità fornitori \> Fatture \> Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="522e8-685">For vendor invoices, go to **Accounts payable \> Invoices \> Invoice journal**.</span></span>

    | <span data-ttu-id="522e8-686">Data</span><span class="sxs-lookup"><span data-stu-id="522e8-686">Date</span></span>              | <span data-ttu-id="522e8-687">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="522e8-687">Transaction type</span></span> | <span data-ttu-id="522e8-688">Importo netto</span><span class="sxs-lookup"><span data-stu-id="522e8-688">Amount net</span></span> | <span data-ttu-id="522e8-689">Importo IVA</span><span class="sxs-lookup"><span data-stu-id="522e8-689">VAT amount</span></span> | <span data-ttu-id="522e8-690">Codice IVA</span><span class="sxs-lookup"><span data-stu-id="522e8-690">Sales tax code</span></span> | <span data-ttu-id="522e8-691">Campo previsto</span><span class="sxs-lookup"><span data-stu-id="522e8-691">Expected field</span></span>                                        | <span data-ttu-id="522e8-692">Somma prevista</span><span class="sxs-lookup"><span data-stu-id="522e8-692">Expected sum</span></span>            |
    |-------------------|------------------|------------|------------|----------------|-------------------------------------------------------|-------------------------|
    | <span data-ttu-id="522e8-693">1 febbraio 2019</span><span class="sxs-lookup"><span data-stu-id="522e8-693">February 1, 2019</span></span>  | <span data-ttu-id="522e8-694">Fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="522e8-694">Vendor invoice</span></span>   | <span data-ttu-id="522e8-695">1000</span><span class="sxs-lookup"><span data-stu-id="522e8-695">1000</span></span>       | <span data-ttu-id="522e8-696">220</span><span class="sxs-lookup"><span data-stu-id="522e8-696">220</span></span>        | <span data-ttu-id="522e8-697">DOMP22</span><span class="sxs-lookup"><span data-stu-id="522e8-697">DOMP22</span></span>         | <span data-ttu-id="522e8-698">VF014001 VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-698">VF014001 VF014002</span></span>                                     | <span data-ttu-id="522e8-699">1000 220</span><span class="sxs-lookup"><span data-stu-id="522e8-699">1000 220</span></span>                |
    | <span data-ttu-id="522e8-700">10 febbraio 2019</span><span class="sxs-lookup"><span data-stu-id="522e8-700">February 10, 2019</span></span> | <span data-ttu-id="522e8-701">Fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="522e8-701">Vendor invoice</span></span>   | <span data-ttu-id="522e8-702">800</span><span class="sxs-lookup"><span data-stu-id="522e8-702">800</span></span>        | <span data-ttu-id="522e8-703">176</span><span class="sxs-lookup"><span data-stu-id="522e8-703">176</span></span>        | <span data-ttu-id="522e8-704">EUP22</span><span class="sxs-lookup"><span data-stu-id="522e8-704">EUP22</span></span>          | <span data-ttu-id="522e8-705">VF014001 VF014002 VF026001 VF026002 VJ009001 VJ009002</span><span class="sxs-lookup"><span data-stu-id="522e8-705">VF014001 VF014002 VF026001 VF026002 VJ009001 VJ009002</span></span> | <span data-ttu-id="522e8-706">800 176 800 176 800 176</span><span class="sxs-lookup"><span data-stu-id="522e8-706">800 176 800 176 800 176</span></span> |
    | <span data-ttu-id="522e8-707">2 febbraio 2019</span><span class="sxs-lookup"><span data-stu-id="522e8-707">February 2, 2019</span></span>  | <span data-ttu-id="522e8-708">Fattura cliente</span><span class="sxs-lookup"><span data-stu-id="522e8-708">Customer invoice</span></span> | <span data-ttu-id="522e8-709">1000</span><span class="sxs-lookup"><span data-stu-id="522e8-709">1000</span></span>       | <span data-ttu-id="522e8-710">220</span><span class="sxs-lookup"><span data-stu-id="522e8-710">220</span></span>        | <span data-ttu-id="522e8-711">DOMS22</span><span class="sxs-lookup"><span data-stu-id="522e8-711">DOMS22</span></span>         | <span data-ttu-id="522e8-712">VE023001 VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-712">VE023001 VE023002</span></span>                                     | <span data-ttu-id="522e8-713">1000 220</span><span class="sxs-lookup"><span data-stu-id="522e8-713">1000 220</span></span>                |
    | <span data-ttu-id="522e8-714">5 febbraio 2019</span><span class="sxs-lookup"><span data-stu-id="522e8-714">February 5, 2019</span></span>  | <span data-ttu-id="522e8-715">Fattura cliente</span><span class="sxs-lookup"><span data-stu-id="522e8-715">Customer invoice</span></span> | <span data-ttu-id="522e8-716">1500</span><span class="sxs-lookup"><span data-stu-id="522e8-716">1500</span></span>       | <span data-ttu-id="522e8-717">0</span><span class="sxs-lookup"><span data-stu-id="522e8-717">0</span></span>          | <span data-ttu-id="522e8-718">EUS</span><span class="sxs-lookup"><span data-stu-id="522e8-718">EUS</span></span>            | <span data-ttu-id="522e8-719">VE030003</span><span class="sxs-lookup"><span data-stu-id="522e8-719">VE030003</span></span>                                              | <span data-ttu-id="522e8-720">1500</span><span class="sxs-lookup"><span data-stu-id="522e8-720">1500</span></span>                    |
    | <span data-ttu-id="522e8-721">1 marzo 2019</span><span class="sxs-lookup"><span data-stu-id="522e8-721">March 1, 2019</span></span>     | <span data-ttu-id="522e8-722">Fattura cliente</span><span class="sxs-lookup"><span data-stu-id="522e8-722">Customer invoice</span></span> | <span data-ttu-id="522e8-723">500</span><span class="sxs-lookup"><span data-stu-id="522e8-723">500</span></span>        | <span data-ttu-id="522e8-724">0</span><span class="sxs-lookup"><span data-stu-id="522e8-724">0</span></span>          | <span data-ttu-id="522e8-725">RC</span><span class="sxs-lookup"><span data-stu-id="522e8-725">RC</span></span>             | <span data-ttu-id="522e8-726">VE035007</span><span class="sxs-lookup"><span data-stu-id="522e8-726">VE035007</span></span>                                              | <span data-ttu-id="522e8-727">500</span><span class="sxs-lookup"><span data-stu-id="522e8-727">500</span></span>                     |

8. <span data-ttu-id="522e8-728">Andare a **Imposta \> Dichiarazioni \> IVA \> Comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-728">Go to **Tax \> Declarations \> Sales tax \> Yearly tax communication**.</span></span>
9. <span data-ttu-id="522e8-729">Selezionare **Crea nuovo** per creare un record di comunicazione annuale imposte per l'anno precedente (2019).</span><span class="sxs-lookup"><span data-stu-id="522e8-729">Select **Create new** to create a yearly tax communication record for the previous year (2019).</span></span>
10. <span data-ttu-id="522e8-730">Selezionare la nuova riga, selezionare **Apri**, quindi rivedere i dati generati per la dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="522e8-730">Select the new line, select **Open**, and review the data that is generated for the declaration.</span></span>

<span data-ttu-id="522e8-731">I campi con **Totale** selezionato nel campo **Calcolo** sono contrassegnati in grassetto.</span><span class="sxs-lookup"><span data-stu-id="522e8-731">Fields with **Total** selected in the **Calculation** field are marked in bold.</span></span>

| <span data-ttu-id="522e8-732">ID campo</span><span class="sxs-lookup"><span data-stu-id="522e8-732">Field ID</span></span>     | <span data-ttu-id="522e8-733">Valore</span><span class="sxs-lookup"><span data-stu-id="522e8-733">Value</span></span>                      | <span data-ttu-id="522e8-734">Descrizione (EN)</span><span class="sxs-lookup"><span data-stu-id="522e8-734">Description (EN)</span></span>                                                                                                                                         |
|--------------|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="522e8-735">VE023001</span><span class="sxs-lookup"><span data-stu-id="522e8-735">VE023001</span></span>     | <span data-ttu-id="522e8-736">1000</span><span class="sxs-lookup"><span data-stu-id="522e8-736">1000</span></span>                       | <span data-ttu-id="522e8-737">Imponibile del 22% delle transazioni fiscali agricole (art. 34, c.1) e delle operazioni professionali.</span><span class="sxs-lookup"><span data-stu-id="522e8-737">22% tax base of agricultural tax transactions (art.34, c.1) and professional operations.</span></span>                                                                 |
| <span data-ttu-id="522e8-738">VE023002</span><span class="sxs-lookup"><span data-stu-id="522e8-738">VE023002</span></span>     | <span data-ttu-id="522e8-739">220</span><span class="sxs-lookup"><span data-stu-id="522e8-739">220</span></span>                        | <span data-ttu-id="522e8-740">Base imponibile del 22% su transazioni fiscali agricole (art. 34, c.1) e operazioni professionali.</span><span class="sxs-lookup"><span data-stu-id="522e8-740">22% tax on agricultural tax transactions (art.34, c.1) and professional operations.</span></span>                                                                      |
| <span data-ttu-id="522e8-741">**VE024001**</span><span class="sxs-lookup"><span data-stu-id="522e8-741">**VE024001**</span></span> | <span data-ttu-id="522e8-742">1000</span><span class="sxs-lookup"><span data-stu-id="522e8-742">1000</span></span>                       | <span data-ttu-id="522e8-743">Totale IMPONIBILE per operazioni attive.</span><span class="sxs-lookup"><span data-stu-id="522e8-743">Total TAX BASE of active operations.</span></span>                                                                                                                     |
| <span data-ttu-id="522e8-744">**VE024002**</span><span class="sxs-lookup"><span data-stu-id="522e8-744">**VE024002**</span></span> | <span data-ttu-id="522e8-745">220</span><span class="sxs-lookup"><span data-stu-id="522e8-745">220</span></span>                        | <span data-ttu-id="522e8-746">Totale IMPOSTA su operazioni attive.</span><span class="sxs-lookup"><span data-stu-id="522e8-746">Total TAX on active operations.</span></span>                                                                                                                          |
| <span data-ttu-id="522e8-747">**VE026002**</span><span class="sxs-lookup"><span data-stu-id="522e8-747">**VE026002**</span></span> | <span data-ttu-id="522e8-748">220</span><span class="sxs-lookup"><span data-stu-id="522e8-748">220</span></span>                        | <span data-ttu-id="522e8-749">Totale imposta (VE24 +/- VE25).</span><span class="sxs-lookup"><span data-stu-id="522e8-749">Total tax (VE24 +/- VE25).</span></span>                                                                                                                               |
| <span data-ttu-id="522e8-750">VE030003</span><span class="sxs-lookup"><span data-stu-id="522e8-750">VE030003</span></span>     | <span data-ttu-id="522e8-751">1500</span><span class="sxs-lookup"><span data-stu-id="522e8-751">1500</span></span>                       | <span data-ttu-id="522e8-752">Vendite intracomunitarie.</span><span class="sxs-lookup"><span data-stu-id="522e8-752">Intra-community sales.</span></span>                                                                                                                                   |
| <span data-ttu-id="522e8-753">**VE030001**</span><span class="sxs-lookup"><span data-stu-id="522e8-753">**VE030001**</span></span> | <span data-ttu-id="522e8-754">1500</span><span class="sxs-lookup"><span data-stu-id="522e8-754">1500</span></span>                       | <span data-ttu-id="522e8-755">Operazioni totali che contribuiscono alla formazione del limite massimo (plafond).</span><span class="sxs-lookup"><span data-stu-id="522e8-755">Total operations which contribute to formation of ceiling (plafond).</span></span>                                                                                     |
| <span data-ttu-id="522e8-756">VE035007</span><span class="sxs-lookup"><span data-stu-id="522e8-756">VE035007</span></span>     | <span data-ttu-id="522e8-757">500</span><span class="sxs-lookup"><span data-stu-id="522e8-757">500</span></span>                        | <span data-ttu-id="522e8-758">Vendite di prodotti elettronici.</span><span class="sxs-lookup"><span data-stu-id="522e8-758">Sales of electronic products.</span></span>                                                                                                                            |
| <span data-ttu-id="522e8-759">**VE035001**</span><span class="sxs-lookup"><span data-stu-id="522e8-759">**VE035001**</span></span> | <span data-ttu-id="522e8-760">500</span><span class="sxs-lookup"><span data-stu-id="522e8-760">500</span></span>                        | <span data-ttu-id="522e8-761">Operazioni con applicazione di reverse charge.</span><span class="sxs-lookup"><span data-stu-id="522e8-761">Operations with application of reverse charge.</span></span>                                                                                                           |
| <span data-ttu-id="522e8-762">**VE050001**</span><span class="sxs-lookup"><span data-stu-id="522e8-762">**VE050001**</span></span> | <span data-ttu-id="522e8-763">3000 (= 1000 + 1500 + 500)</span><span class="sxs-lookup"><span data-stu-id="522e8-763">3000 (= 1000 + 1500 + 500)</span></span> | <span data-ttu-id="522e8-764">Fatturato aziendale.</span><span class="sxs-lookup"><span data-stu-id="522e8-764">Business turnover.</span></span>                                                                                                                                       |
| <span data-ttu-id="522e8-765">VF014001</span><span class="sxs-lookup"><span data-stu-id="522e8-765">VF014001</span></span>     | <span data-ttu-id="522e8-766">1800</span><span class="sxs-lookup"><span data-stu-id="522e8-766">1800</span></span>                       | <span data-ttu-id="522e8-767">Acquisti e importazioni tassabili (22%).</span><span class="sxs-lookup"><span data-stu-id="522e8-767">Taxable purchases and imports (22%).</span></span>                                                                                                                     |
| <span data-ttu-id="522e8-768">VF014002</span><span class="sxs-lookup"><span data-stu-id="522e8-768">VF014002</span></span>     | <span data-ttu-id="522e8-769">396</span><span class="sxs-lookup"><span data-stu-id="522e8-769">396</span></span>                        | <span data-ttu-id="522e8-770">Imposta su acquisti e importazioni (22%).</span><span class="sxs-lookup"><span data-stu-id="522e8-770">Tax on purchases and imports (22%).</span></span>                                                                                                                      |
| <span data-ttu-id="522e8-771">**VF023001**</span><span class="sxs-lookup"><span data-stu-id="522e8-771">**VF023001**</span></span> | <span data-ttu-id="522e8-772">1800</span><span class="sxs-lookup"><span data-stu-id="522e8-772">1800</span></span>                       | <span data-ttu-id="522e8-773">Totale ACQUISTI E IMPORTAZIONI.</span><span class="sxs-lookup"><span data-stu-id="522e8-773">Total PURCHASES AND IMPORTS.</span></span>                                                                                                                             |
| <span data-ttu-id="522e8-774">**VF023002**</span><span class="sxs-lookup"><span data-stu-id="522e8-774">**VF023002**</span></span> | <span data-ttu-id="522e8-775">396</span><span class="sxs-lookup"><span data-stu-id="522e8-775">396</span></span>                        | <span data-ttu-id="522e8-776">Totale ACQUISTI E IMPORTAZIONI - IMPOSTA.</span><span class="sxs-lookup"><span data-stu-id="522e8-776">Total PURCHASES AND IMPORTS – TAX.</span></span>                                                                                                                       |
| <span data-ttu-id="522e8-777">**VF025002**</span><span class="sxs-lookup"><span data-stu-id="522e8-777">**VF025002**</span></span> | <span data-ttu-id="522e8-778">396</span><span class="sxs-lookup"><span data-stu-id="522e8-778">396</span></span>                        | <span data-ttu-id="522e8-779">Totale IMPOSTA SU ACQUISTI E IMPORTAZIONI TASSABILI.</span><span class="sxs-lookup"><span data-stu-id="522e8-779">Total TAX ON TAXABLE PURCHASES AND IMPORTS.</span></span>                                                                                                              |
| <span data-ttu-id="522e8-780">VF026001</span><span class="sxs-lookup"><span data-stu-id="522e8-780">VF026001</span></span>     | <span data-ttu-id="522e8-781">800</span><span class="sxs-lookup"><span data-stu-id="522e8-781">800</span></span>                        | <span data-ttu-id="522e8-782">Acquisti intracomunitari - Imponibile.</span><span class="sxs-lookup"><span data-stu-id="522e8-782">Intra-Community purchases – tax base.</span></span>                                                                                                                    |
| <span data-ttu-id="522e8-783">VF026002</span><span class="sxs-lookup"><span data-stu-id="522e8-783">VF026002</span></span>     | <span data-ttu-id="522e8-784">176</span><span class="sxs-lookup"><span data-stu-id="522e8-784">176</span></span>                        | <span data-ttu-id="522e8-785">Acquisti intracomunitari - Imposta.</span><span class="sxs-lookup"><span data-stu-id="522e8-785">Intra-Community purchases – tax.</span></span>                                                                                                                         |
| <span data-ttu-id="522e8-786">**VF037001**</span><span class="sxs-lookup"><span data-stu-id="522e8-786">**VF037001**</span></span> | <span data-ttu-id="522e8-787">396 (= 220 + 176)</span><span class="sxs-lookup"><span data-stu-id="522e8-787">396 (= 220 + 176)</span></span>          | <span data-ttu-id="522e8-788">IVA ammissibile in detrazione.</span><span class="sxs-lookup"><span data-stu-id="522e8-788">Admissible deductible VAT.</span></span>                                                                                                                               |
| <span data-ttu-id="522e8-789">**VF071002**</span><span class="sxs-lookup"><span data-stu-id="522e8-789">**VF071002**</span></span> | <span data-ttu-id="522e8-790">396</span><span class="sxs-lookup"><span data-stu-id="522e8-790">396</span></span>                        | <span data-ttu-id="522e8-791">IVA ammissibile in detrazione.</span><span class="sxs-lookup"><span data-stu-id="522e8-791">Admissible deductible VAT.</span></span>                                                                                                                               |
| <span data-ttu-id="522e8-792">VJ009001</span><span class="sxs-lookup"><span data-stu-id="522e8-792">VJ009001</span></span>     | <span data-ttu-id="522e8-793">800</span><span class="sxs-lookup"><span data-stu-id="522e8-793">800</span></span>                        | <span data-ttu-id="522e8-794">Acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art.</span><span class="sxs-lookup"><span data-stu-id="522e8-794">Intra-community purchases of goods (including purchases of industrial gold, pure silver and goods as referred to in art.</span></span> <span data-ttu-id="522e8-795">74, commi 7 e 8).</span><span class="sxs-lookup"><span data-stu-id="522e8-795">74, paragraphs 7 and 8).</span></span>        |
| <span data-ttu-id="522e8-796">VJ009002</span><span class="sxs-lookup"><span data-stu-id="522e8-796">VJ009002</span></span>     | <span data-ttu-id="522e8-797">176</span><span class="sxs-lookup"><span data-stu-id="522e8-797">176</span></span>                        | <span data-ttu-id="522e8-798">Imposta su acquisti intracomunitari di beni (inclusi gli acquisti di oro industriale, argento puro e beni di cui all'art.</span><span class="sxs-lookup"><span data-stu-id="522e8-798">Tax on Intra-community purchases of goods (including purchases of industrial gold, pure silver and goods as referred to in art.</span></span> <span data-ttu-id="522e8-799">74, commi 7 e 8).</span><span class="sxs-lookup"><span data-stu-id="522e8-799">74, paragraphs 7 and 8).</span></span> |
| <span data-ttu-id="522e8-800">**VJ019002**</span><span class="sxs-lookup"><span data-stu-id="522e8-800">**VJ019002**</span></span> | <span data-ttu-id="522e8-801">176</span><span class="sxs-lookup"><span data-stu-id="522e8-801">176</span></span>                        | <span data-ttu-id="522e8-802">Totale imposta.</span><span class="sxs-lookup"><span data-stu-id="522e8-802">Total tax.</span></span>                                                                                                                                               |
| <span data-ttu-id="522e8-803">**VL001001**</span><span class="sxs-lookup"><span data-stu-id="522e8-803">**VL001001**</span></span> | <span data-ttu-id="522e8-804">396</span><span class="sxs-lookup"><span data-stu-id="522e8-804">396</span></span>                        | <span data-ttu-id="522e8-805">IVA a debito.</span><span class="sxs-lookup"><span data-stu-id="522e8-805">Output VAT.</span></span>                                                                                                                                              |
| <span data-ttu-id="522e8-806">**VL002001**</span><span class="sxs-lookup"><span data-stu-id="522e8-806">**VL002001**</span></span> | <span data-ttu-id="522e8-807">396</span><span class="sxs-lookup"><span data-stu-id="522e8-807">396</span></span>                        | <span data-ttu-id="522e8-808">IVA deducibile.</span><span class="sxs-lookup"><span data-stu-id="522e8-808">Deductible VAT.</span></span>                                                                                                                                          |

## <a name="appendix-2-example-of-the-yearly-tax-communication-setup-for-2020"></a><span data-ttu-id="522e8-809">Appendice 2.</span><span class="sxs-lookup"><span data-stu-id="522e8-809">Appendix 2.</span></span> <span data-ttu-id="522e8-810">Esempio di impostazioni comunicazione annuale imposte per il 2020</span><span class="sxs-lookup"><span data-stu-id="522e8-810">Example of the Yearly tax communication setup for 2020</span></span>

<span data-ttu-id="522e8-811">Per scaricare l'impostazione di esempio per la dichiarazione 2020, vedere [Impostazione di esempio IVA 2020](https://docs.microsoft.com/dynamics/s-e/ax/ItalianAnnualVATdeclaration_delta).</span><span class="sxs-lookup"><span data-stu-id="522e8-811">To download example setup for the 2020 declaration, see [IVA example setup 2020](https://docs.microsoft.com/dynamics/s-e/ax/ItalianAnnualVATdeclaration_delta).</span></span> <span data-ttu-id="522e8-812">Per accedere al collegamento, è necessario avere accesso a CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="522e8-812">To access the link, you need to have access to CustomerSource.</span></span>

1. <span data-ttu-id="522e8-813">Andare a **Imposta \> Impostazione \> IVA \> Impostazioni comunicazione annuale imposte**.</span><span class="sxs-lookup"><span data-stu-id="522e8-813">Go to **Tax \> Setup \> Sales tax \> Yearly tax communication setup**.</span></span>
2. <span data-ttu-id="522e8-814">Selezionare il pulsante **Apri in Microsoft Office**, quindi in **Apri in Excel** selezionare **Impostazioni comunicazione annuale imposte (DEMF)**.</span><span class="sxs-lookup"><span data-stu-id="522e8-814">Select the **Open in Microsoft Office** button, and then, under **Open in Excel**, select **Yearly tax communication setup (DEMF)**.</span></span>

    ![Seleziona di Impostazioni comunicazione annuale imposte (DEFM)](media/6_Export_to_Excel.png)

3. <span data-ttu-id="522e8-816">Selezionare **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="522e8-816">Select **Download**.</span></span>
4. <span data-ttu-id="522e8-817">Apri il file scaricato e abilita la modifica.</span><span class="sxs-lookup"><span data-stu-id="522e8-817">Open the downloaded file, and enable editing.</span></span>
5. <span data-ttu-id="522e8-818">Copiare i dati dal file scaricato in precedenza e incollarli nel file che aperto, quindi selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="522e8-818">Copy the data from the file downloaded above and paste the data to the file that is opened, and then select **Publish**.</span></span>

    ![Pulsante Pubblica](media/5_Export_to_Excel.png)

6. <span data-ttu-id="522e8-820">Rivedere le impostazioni e apportare gli aggiornamenti necessari.</span><span class="sxs-lookup"><span data-stu-id="522e8-820">Review settings and make necessary updates.</span></span> <span data-ttu-id="522e8-821">Ad esempio, impostare i codici IVA esistenti nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="522e8-821">For example, set up sales tax codes that exist in the application.</span></span>
7. <span data-ttu-id="522e8-822">Considerare le seguenti informazioni.</span><span class="sxs-lookup"><span data-stu-id="522e8-822">Consider the following information.</span></span> <span data-ttu-id="522e8-823">Alcuni totali non sono configurati nell'esempio e devono essere calcolati manualmente utilizzando la formula specificata nelle linee guida ufficiali.</span><span class="sxs-lookup"><span data-stu-id="522e8-823">Some totals are not configured in the example and should be calculated manually using the formula specified in official guidance.</span></span> <span data-ttu-id="522e8-824">Di seguito sono riportati tali totali:</span><span class="sxs-lookup"><span data-stu-id="522e8-824">These are the following totals:</span></span>

   - <span data-ttu-id="522e8-825">VF037001 IVA ammissibile in detrazione (IVA ammessa in detrazione)</span><span class="sxs-lookup"><span data-stu-id="522e8-825">VF037001 VAT admissible for deduction (IVA ammessa in detrazione)</span></span>
   - <span data-ttu-id="522e8-826">VF071002 IVA ammissibile in detrazione (IVA ammessa in detrazione)</span><span class="sxs-lookup"><span data-stu-id="522e8-826">VF071002 VAT admissible for deduction (IVA ammessa in detrazione)</span></span>
   - <span data-ttu-id="522e8-827">VL032001 IVA dovuta (IVA a debito)</span><span class="sxs-lookup"><span data-stu-id="522e8-827">VL032001 VAT payable (IVA a debito)</span></span>
   - <span data-ttu-id="522e8-828">VL033001 Credito (IVA a credito)</span><span class="sxs-lookup"><span data-stu-id="522e8-828">VL033001 VAT credit (IVA a credito)</span></span>
   


[!INCLUDE[footer-include](../../includes/footer-banner.md)]