---
title: Implementare campi personalizzati per l'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet in IOS e Android
description: In questo argomento vengono forniti modelli comuni per l'utilizzo di estensioni con cui implementare campi personalizzati.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 4343c875da05641c57b7784bf52f1c814dd26d20
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "1617998"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="753d5-103">Implementare campi personalizzati per l'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet in IOS e Android</span><span class="sxs-lookup"><span data-stu-id="753d5-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="753d5-104">In questo argomento vengono forniti modelli comuni per l'utilizzo di estensioni con cui implementare campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="753d5-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="753d5-105">Sono trattati i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="753d5-105">The following topics are covered:</span></span>

- <span data-ttu-id="753d5-106">I vari tipi di dati supportati dal framework dei campi personalizzati</span><span class="sxs-lookup"><span data-stu-id="753d5-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="753d5-107">Il modo in cui visualizzare campi modificabili o di sola lettura nelle voci del foglio presenze e salvare i valori forniti dall'utente nel database</span><span class="sxs-lookup"><span data-stu-id="753d5-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="753d5-108">Il modo in cui visualizzare campi di sola lettura nell'intestazione del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="753d5-109">Il modo in cui integrare altra logica di business per immettere valori predefiniti nei campi ed effettuare una convalida aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="753d5-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="753d5-110">Destinatari</span><span class="sxs-lookup"><span data-stu-id="753d5-110">Audience</span></span>

<span data-ttu-id="753d5-111">Questo argomento è destinato agli sviluppatori che eseguono l'integrazione dei relativi campi personalizzati nell'applicazione per dispositivi mobili Microsoft Dynamics 365 Project Timesheet disponibile per Apple iOS e Google Android.</span><span class="sxs-lookup"><span data-stu-id="753d5-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="753d5-112">Si presuppone che i lettori abbiano familiarità con lo sviluppo X++ e la funzionalità del foglio presenze progetto.</span><span class="sxs-lookup"><span data-stu-id="753d5-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="753d5-113">Contratto dati – Classe X++ TSTimesheetCustomField</span><span class="sxs-lookup"><span data-stu-id="753d5-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="753d5-114">La classe **TSTimesheetCustomField** è la classe di contratto dati X++ che rappresenta le informazioni su un campo personalizzato per la funzionalità del foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="753d5-115">Gli elenchi di oggetti di campi personalizzati vengono passati al contratto dati TSTimesheetDetails e al contratto dati TSTimesheetEntry per visualizzare campi personalizzati nell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="753d5-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="753d5-116">**TSTimesheetDetails** - Il contratto dell'intestazione del foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="753d5-117">**TSTimesheetEntry** - Il contratto della transazione del foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="753d5-118">Gruppi di questi oggetti che hanno le stesse informazioni sul progetto e il valore **timesheetLineRecId** costituiscono una riga.</span><span class="sxs-lookup"><span data-stu-id="753d5-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="753d5-119">fieldBaseType (tipi)</span><span class="sxs-lookup"><span data-stu-id="753d5-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="753d5-120">La proprietà **FieldBaseType** nell'oggetto **TsTimesheetCustom** determina il tipo del campo visualizzato nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="753d5-121">Sono supportati i seguenti valori **Tipi**.</span><span class="sxs-lookup"><span data-stu-id="753d5-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="753d5-122">Valore Tipi</span><span class="sxs-lookup"><span data-stu-id="753d5-122">Types value</span></span> | <span data-ttu-id="753d5-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="753d5-123">Type</span></span>              | <span data-ttu-id="753d5-124">Note</span><span class="sxs-lookup"><span data-stu-id="753d5-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="753d5-125">0</span><span class="sxs-lookup"><span data-stu-id="753d5-125">0</span></span>           | <span data-ttu-id="753d5-126">String (e Enum)</span><span class="sxs-lookup"><span data-stu-id="753d5-126">String (and Enum)</span></span> | <span data-ttu-id="753d5-127">Il campo è visualizzato come campo di testo.</span><span class="sxs-lookup"><span data-stu-id="753d5-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="753d5-128">1</span><span class="sxs-lookup"><span data-stu-id="753d5-128">1</span></span>           | <span data-ttu-id="753d5-129">Intero</span><span class="sxs-lookup"><span data-stu-id="753d5-129">Integer</span></span>           | <span data-ttu-id="753d5-130">Il valore è visualizzato come numero senza posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="753d5-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="753d5-131">2</span><span class="sxs-lookup"><span data-stu-id="753d5-131">2</span></span>           | <span data-ttu-id="753d5-132">Reale</span><span class="sxs-lookup"><span data-stu-id="753d5-132">Real</span></span>              | <span data-ttu-id="753d5-133">Il valore è visualizzato come numero con posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="753d5-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="753d5-134">Per visualizzare il valore real come valuta nell'app, utilizzare la proprietà **fieldExtenededType**.</span><span class="sxs-lookup"><span data-stu-id="753d5-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="753d5-135">È possibile utilizzare la proprietà **numberOfDecimals** per impostare il numero di posizioni decimali visualizzate.</span><span class="sxs-lookup"><span data-stu-id="753d5-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="753d5-136">3</span><span class="sxs-lookup"><span data-stu-id="753d5-136">3</span></span>           | <span data-ttu-id="753d5-137">Data</span><span class="sxs-lookup"><span data-stu-id="753d5-137">Date</span></span>              | <span data-ttu-id="753d5-138">I formati data sono determinati dall'impostazione **Formato data, ora e numeri** specificata sotto **Preferenze di lingua e paese** in **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="753d5-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="753d5-139">4</span><span class="sxs-lookup"><span data-stu-id="753d5-139">4</span></span>           | <span data-ttu-id="753d5-140">Booleano</span><span class="sxs-lookup"><span data-stu-id="753d5-140">Boolean</span></span>           | |
| <span data-ttu-id="753d5-141">15</span><span class="sxs-lookup"><span data-stu-id="753d5-141">15</span></span>          | <span data-ttu-id="753d5-142">GUID</span><span class="sxs-lookup"><span data-stu-id="753d5-142">GUID</span></span>              | |
| <span data-ttu-id="753d5-143">16</span><span class="sxs-lookup"><span data-stu-id="753d5-143">16</span></span>          | <span data-ttu-id="753d5-144">Int64</span><span class="sxs-lookup"><span data-stu-id="753d5-144">Int64</span></span>             | |

- <span data-ttu-id="753d5-145">Se la proprietà **stringOptions** non viene fornita nell'oggetto **TSTimesheetCustomField**, all'utente viene fornito un campo a testo libero.</span><span class="sxs-lookup"><span data-stu-id="753d5-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="753d5-146">La proprietà **stringLength** può essere utilizzata per impostare la lunghezza di stringa massima che gli utenti possono immettere.</span><span class="sxs-lookup"><span data-stu-id="753d5-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="753d5-147">Se la proprietà **stringOptions** viene fornita nell'oggetto **TSTimesheetCustomField**, tali elementi dell'elenco sono i soli valori che gli utenti possono selezionare utilizzando i pulsanti di opzione (pulsanti di scelta).</span><span class="sxs-lookup"><span data-stu-id="753d5-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="753d5-148">In questo caso, il campo string può essere un valore enum per l'immissione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="753d5-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="753d5-149">Per salvare il valore nel database come enum, mappare di nuovo manualmente il valore string al valore enum prima del salvataggio utilizzando la catena di comando (vedere la sezione "Utilizzare la catena di comando nella classe di servizio TSTimesheetEntryService per salvare una voce del foglio presenze" in seguito in questo argomento per un esempio).</span><span class="sxs-lookup"><span data-stu-id="753d5-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="753d5-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="753d5-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="753d5-151">È possibile utilizzare questa proprietà per formattare valori real come valuta.</span><span class="sxs-lookup"><span data-stu-id="753d5-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="753d5-152">Questo approccio è applicabile solo quando il valore **fieldBaseType** è **Real**.</span><span class="sxs-lookup"><span data-stu-id="753d5-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="753d5-153">**TSCustomFieldExtendedType:None** – Non viene applicata alcuna formattazione.</span><span class="sxs-lookup"><span data-stu-id="753d5-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="753d5-154">**TSCustomFieldExtendedType::Currency** – Formatta il valore come valuta.</span><span class="sxs-lookup"><span data-stu-id="753d5-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="753d5-155">Quando la formattazione della valuta è attiva, il campo **stringValue** può essere utilizzato per passare il codice valuta da visualizzare nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="753d5-156">Il valore è un valore di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="753d5-156">The value is a read-only value.</span></span>

    <span data-ttu-id="753d5-157">Il campo **realValue** contiene l'importo di denaro che deve essere salvato nel database.</span><span class="sxs-lookup"><span data-stu-id="753d5-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="753d5-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="753d5-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="753d5-159">È possibile utilizzare questa proprietà per specificare dove il campo personalizzato deve essere visualizzato nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="753d5-160">**TSCustomFieldSection::Header** - Il campo verrà visualizzato nella sezione **Visualizza ulteriori dettagli** nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="753d5-161">Questi campi sono sempre di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="753d5-161">These fields are always read-only.</span></span>
- <span data-ttu-id="753d5-162">**TSCustomFieldSection::Line** - Il campo verrà visualizzato dopo tutti i campi riga predefiniti nelle voci del foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="753d5-163">Questi campi possono essere modificabili o di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="753d5-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="753d5-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="753d5-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="753d5-165">Questa proprietà identifica il campo quando i valori che l'app fornisce vengono salvati di nuovo nel database.</span><span class="sxs-lookup"><span data-stu-id="753d5-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="753d5-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="753d5-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="753d5-167">Questa proprietà identifica il campo quando i valori che l'app fornisce vengono salvati di nuovo nel database.</span><span class="sxs-lookup"><span data-stu-id="753d5-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="753d5-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="753d5-168">isEditable (NoYes)</span></span>

<span data-ttu-id="753d5-169">Impostare questa proprietà su **Sì** per specificare che il campo nella sezione delle voci del foglio presenze può essere modificato dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="753d5-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="753d5-170">Impostare la proprietà su **No** per rendere il campo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="753d5-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="753d5-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="753d5-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="753d5-172">Impostare questa proprietà su **Sì** per specificare che il campo nella sezione delle voci del foglio presenze deve essere obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="753d5-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="753d5-173">label (str)</span><span class="sxs-lookup"><span data-stu-id="753d5-173">label (str)</span></span>

<span data-ttu-id="753d5-174">Questa proprietà specifica l'etichetta visualizzata accanto al campo nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="753d5-175">stringOptions (List of Strings)</span><span class="sxs-lookup"><span data-stu-id="753d5-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="753d5-176">Questa proprietà è applicabile solo quando **fieldBaseType** è impostata su **String**.</span><span class="sxs-lookup"><span data-stu-id="753d5-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="753d5-177">Se **stringOptions** è impostata, i valori stringa disponibili per la selezione mediante i pulsanti di opzione (pulsanti di scelta) vengono specificati dalle stringhe nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="753d5-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="753d5-178">Se non si specificano stringhe, la voce a testo libero nel campo string è consentita (vedere la sezione "Utilizzare la catena di comando nella classe di servizio TSTimesheetEntryService per salvare una voce del foglio presenze" in seguito in questo argomento per un esempio).</span><span class="sxs-lookup"><span data-stu-id="753d5-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="753d5-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="753d5-179">stringLength (int)</span></span>

<span data-ttu-id="753d5-180">Questa proprietà specifica la lunghezza massima di un campo string.</span><span class="sxs-lookup"><span data-stu-id="753d5-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="753d5-181">È applicabile solo quando **fieldBaseType** è impostata su **String**.</span><span class="sxs-lookup"><span data-stu-id="753d5-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="753d5-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="753d5-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="753d5-183">Questa proprietà specifica il numero di posizioni decimali visualizzato per un campo real.</span><span class="sxs-lookup"><span data-stu-id="753d5-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="753d5-184">È applicabile solo quando **fieldBaseType** è impostata su **Real**.</span><span class="sxs-lookup"><span data-stu-id="753d5-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="753d5-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="753d5-185">orderSequence (int)</span></span>

<span data-ttu-id="753d5-186">Questa proprietà controlla l'ordine in cui i campi personalizzati vengono visualizzati nell'app quando si specificano più campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="753d5-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="753d5-187">I campi con numeri più bassi sono visualizzati per primi.</span><span class="sxs-lookup"><span data-stu-id="753d5-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="753d5-188">booleanValue (boolean)</span><span class="sxs-lookup"><span data-stu-id="753d5-188">booleanValue (boolean)</span></span>

<span data-ttu-id="753d5-189">Per i campi di tipo **Boolean**, questa proprietà passa il valore Boolean del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="753d5-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="753d5-190">guidValue (guid)</span></span>

<span data-ttu-id="753d5-191">Per i campi di tipo **GUID**, questa proprietà passa il valore GUID del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="753d5-192">int64Value (int64)</span><span class="sxs-lookup"><span data-stu-id="753d5-192">int64Value (int64)</span></span>

<span data-ttu-id="753d5-193">Per i campi di tipo **Int64**, questa proprietà passa il valore int64 del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="753d5-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="753d5-194">intValue (int)</span></span>

<span data-ttu-id="753d5-195">Per i campi di tipo **Int**, questa proprietà passa il valore int del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="753d5-196">realValue (real)</span><span class="sxs-lookup"><span data-stu-id="753d5-196">realValue (real)</span></span>

<span data-ttu-id="753d5-197">Per i campi di tipo **Real**, questa proprietà passa il valore real del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="753d5-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="753d5-198">stringValue (str)</span></span>

<span data-ttu-id="753d5-199">Per i campi di tipo **String**, questa proprietà passa il valore string del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="753d5-200">È inoltre utilizzato per i campi di tipo **Real** formattati come valuta.</span><span class="sxs-lookup"><span data-stu-id="753d5-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="753d5-201">Per tali campi, la proprietà viene utilizzata per passare il codice valuta all'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="753d5-202">dateValue (date)</span><span class="sxs-lookup"><span data-stu-id="753d5-202">dateValue (date)</span></span>

<span data-ttu-id="753d5-203">Per i campi di tipo **Date**, questa proprietà passa il valore date del campo tra il server e l'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="753d5-204">Visualizzare e salvare un campo personalizzato nella sezione delle voci del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="753d5-205">Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra la creazione di una voce del foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="753d5-206">Questa schermata mostra i campi predefiniti e un campo personalizzato nella sezione "Inserimento ore" denominata "Stringa di prova" con un valore enum "Seconda opzione" già impostato.</span><span class="sxs-lookup"><span data-stu-id="753d5-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Campo predefinito Stringa di prova nell'app](media/timesheet-entry.jpg)



<span data-ttu-id="753d5-208">Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra la selezione di una delle opzioni di enumerazione disponibili per il campo personalizzato "Stringa di prova".</span><span class="sxs-lookup"><span data-stu-id="753d5-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="753d5-209">Le due opzioni sono "Prima opzione "e "Seconda opzione" visualizzate come pulsanti di scelta.</span><span class="sxs-lookup"><span data-stu-id="753d5-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="753d5-210">L'opzione Seconda opzione è quella selezionata.</span><span class="sxs-lookup"><span data-stu-id="753d5-210">The second option is currently selected.</span></span>

![Pulsanti di opzione (pulsanti di scelta) per il campo personalizzato Stringa di prova](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="753d5-212">Estendere la tabella TSTimesheetLine affinché abbia un campo personalizzato</span><span class="sxs-lookup"><span data-stu-id="753d5-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="753d5-213">Negli scenari comuni, è probabile che i dati per un campo personalizzato nella sezione delle voci del foglio presenze verranno salvati nella tabella TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="753d5-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="753d5-214">Tuttavia, è possibile utilizzare altre tabelle se i dati possono essere recuperati in base al record TSTimesheetTrans fornito o se non hanno un contesto record specifico (ad esempio se il campo è di sola lettura nei parametri del progetto).</span><span class="sxs-lookup"><span data-stu-id="753d5-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="753d5-215">Si noti che i campi personalizzati non devono avere alcun record di database di supporto.</span><span class="sxs-lookup"><span data-stu-id="753d5-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="753d5-216">I campi possono essere generati in modo dinamico in base alla logica X++.</span><span class="sxs-lookup"><span data-stu-id="753d5-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="753d5-217">Tale approccio può risultare utile negli scenari di sola lettura (vedere la sezione "Utilizzare la catena di comando nel metodo buildCustomFieldListForHeader della classe TSTimesheetDetails per specificare i dettagli del foglio presenze" per un esempio di valori di campi personalizzati generati in modo dinamico).</span><span class="sxs-lookup"><span data-stu-id="753d5-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="753d5-218">Di seguito è riportata una schermata di Visual Studio che illustra la struttura a oggetti applicativi.</span><span class="sxs-lookup"><span data-stu-id="753d5-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="753d5-219">La schermata raffigura un'estensione della tabella TSTimesheetLine con il campo TestLineString aggiunto come campo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="753d5-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Stringa riga](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="753d5-221">Utilizzare la catena di comando nel metodo buildCustomFieldList della classe TSTimesheetSettings per visualizzare un campo nella sezione delle voci del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="753d5-222">Questo codice controlla le impostazioni di visualizzazione del campo nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="753d5-223">Ad esempio, controlla il tipo di campo, l'etichetta, se il campo è obbligatorio e la sezione in cui il campo viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="753d5-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="753d5-224">L'esempio seguente illustra un campo string nelle voci relative alle ore.</span><span class="sxs-lookup"><span data-stu-id="753d5-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="753d5-225">Questo campo ha due opzioni, **Prima opzione** e **Seconda opzione**, disponibili tramite pulsanti di opzione (pulsanti di scelta).</span><span class="sxs-lookup"><span data-stu-id="753d5-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="753d5-226">Il campo nell'app è associato al campo **TestLineString** che viene aggiunto alla tabella TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="753d5-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="753d5-227">Da notare l'utilizzo del metodo **TSTimesheetCustomField::newFromMetatdata()** per semplificare l'inizializzazione delle proprietà dei campi personalizzati: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** e **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="753d5-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="753d5-228">È anche possibile impostare tali parametri manualmente.</span><span class="sxs-lookup"><span data-stu-id="753d5-228">You can also set these parameters manually, as you prefer.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="753d5-229">Utilizzare la catena di comando nel metodo buildCustomFieldListForEntry della classe TSTimesheetEntry per immettere valori in una voce del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="753d5-230">Il metodo **buildCustomFieldListForEntry** viene utilizzato per immettere valori nelle righe del foglio presenze salvato nell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="753d5-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="753d5-231">Utilizza il record TSTimesheetTrans come parametro.</span><span class="sxs-lookup"><span data-stu-id="753d5-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="753d5-232">I campi di quel record possono essere utilizzati per immettere il valore dei campi personalizzati nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="753d5-233">Utilizzare la catena di comando nella classe TSTimesheetEntryService per salvare una voce del foglio presenze dall'app nel database</span><span class="sxs-lookup"><span data-stu-id="753d5-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="753d5-234">Per salvare di nuovo un campo personalizzato in un utilizzo tipico, è necessario estendere più metodi:</span><span class="sxs-lookup"><span data-stu-id="753d5-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="753d5-235">Il metodo **timesheetLineNeedsUpdating** viene utilizzato per determinare se il record della riga è stato modificato dall'utente nell'app e deve essere salvato nel database.</span><span class="sxs-lookup"><span data-stu-id="753d5-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="753d5-236">Se le prestazioni non sono una priorità, questo metodo può essere semplificato di modo che restituisca sempre **true**.</span><span class="sxs-lookup"><span data-stu-id="753d5-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="753d5-237">I metodi **populateTimesheetLineFromEntryDuringCreate** e **populateTimesheetLineFromEntryDuringUpdate** possono essere estesi in modo che dei valori siano immessi nel record di database TSTimesheetLine dal record del contratto dati TSTimesheetEntry fornito.</span><span class="sxs-lookup"><span data-stu-id="753d5-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="753d5-238">Nell'esempio riportato di seguito, notare come il mapping tra il campo del database e il campo di immissione viene eseguito manualmente tramite il codice X++.</span><span class="sxs-lookup"><span data-stu-id="753d5-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="753d5-239">Il metodo **populateTimesheetWeekFromEntry** può anche essere esteso se il campo personalizzato mappato all'oggetto **TSTimesheetEntry** deve eseguire il writeback nella tabella di database TSTimesheetLineweek.</span><span class="sxs-lookup"><span data-stu-id="753d5-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="753d5-240">L'esempio seguente salva il valore **secondOption** o **firstOption** che l'utente seleziona per il database come valore string non elaborato.</span><span class="sxs-lookup"><span data-stu-id="753d5-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="753d5-241">Se il campo del database è un campo di tipo **Enum**, questi valori possono essere mappati manualmente a un valore enum e quindi salvati in un campo enum nella tabella di database.</span><span class="sxs-lookup"><span data-stu-id="753d5-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="753d5-242">Visualizzare un campo personalizzato nella sezione dell'intestazione del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="753d5-243">Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra un utente che visualizza un foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="753d5-244">Il pulsante "Ulteriori informazioni" è stato selezionato nell'angolo superiore destro per visualizzare l'opzione "Visualizza altri dettagli".</span><span class="sxs-lookup"><span data-stu-id="753d5-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![Comando Visualizza altri dettagli](media/show-more.png)



<span data-ttu-id="753d5-246">Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra la sezione "Altro" di un foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="753d5-247">Un campo personalizzato denominato "Tasso di utilizzo di questo foglio presenze (campo personalizzato calcolato)" è stato aggiunto alla sezione dell'intestazione del foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="753d5-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="753d5-248">Il valore di sola lettura "0.667 "è impostato nel campo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="753d5-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Sezione Altro](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="753d5-250">Estendere la tabella TSTimesheetLine affinché abbia un campo personalizzato</span><span class="sxs-lookup"><span data-stu-id="753d5-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="753d5-251">Negli scenari comuni, è probabile che i dati per un campo personalizzato nella sezione dell'intestazione saranno acquisiti dalla tabella TSTimesheetHeader .</span><span class="sxs-lookup"><span data-stu-id="753d5-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="753d5-252">Tuttavia, è possibile utilizzare altre tabelle se i dati possono essere recuperati in base al record TSTimesheetTable fornito o se non hanno un contesto record specifico (ad esempio se il campo è di sola lettura nei parametri del progetto).</span><span class="sxs-lookup"><span data-stu-id="753d5-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="753d5-253">Si noti che i campi personalizzati non devono avere alcun record di database di supporto.</span><span class="sxs-lookup"><span data-stu-id="753d5-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="753d5-254">I campi possono essere generati in modo dinamico in base alla logica X++.</span><span class="sxs-lookup"><span data-stu-id="753d5-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="753d5-255">Nell'esempio riportato di seguito mostra questo approccio.</span><span class="sxs-lookup"><span data-stu-id="753d5-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="753d5-256">I campi nella sezione dell'intestazione sono sempre di sola lettura nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="753d5-257">Utilizzare la catena di comando nel metodo buildCustomFieldList della classe TSTimesheetSettings per visualizzare un campo nella sezione dell'intestazione</span><span class="sxs-lookup"><span data-stu-id="753d5-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="753d5-258">Questo codice controlla le impostazioni di visualizzazione del campo nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="753d5-259">Ad esempio, controlla il tipo di campo, l'etichetta, se il campo è obbligatorio e la sezione in cui il campo viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="753d5-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="753d5-260">Nel seguente esempio viene illustrato un valore calcolato nella sezione dell'intestazione nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-260">The following example shows a computed value in the header section in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="753d5-261">Utilizzare la catena di comando nel metodo buildCustomFieldListForHeader della classe TSTimesheetDetails per immettere i dettagli del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="753d5-262">Il metodo **buildCustomFieldListForHeader** viene utilizzato per immettere dettagli dell'intestazione del foglio presenze nell'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="753d5-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="753d5-263">Utilizza il record TSTimesheetTable come parametro.</span><span class="sxs-lookup"><span data-stu-id="753d5-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="753d5-264">I campi di quel record possono essere utilizzati per immettere il valore dei campi personalizzati nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="753d5-265">Nel seguente esempio nessun valore viene letto dal database.</span><span class="sxs-lookup"><span data-stu-id="753d5-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="753d5-266">Viene invece utilizzata la logica X++ per generare un valore calcolato che viene visualizzato nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="753d5-267">Altre opportunità di configurabilità/estendibilità</span><span class="sxs-lookup"><span data-stu-id="753d5-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="753d5-268">Aggiunta di convalida aggiuntiva per l'app</span><span class="sxs-lookup"><span data-stu-id="753d5-268">Adding additional validation for the app</span></span>

<span data-ttu-id="753d5-269">La logica esistente per la funzionalità del foglio presenze a livello del database continuerà a funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="753d5-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="753d5-270">Per interrompere il completamento delle operazioni di salvataggio o invio e visualizzare uno specifico messaggio di errore, è possibile aggiungere **throw error("message to user")** al codice tramite l'estensione di una catena di comando.</span><span class="sxs-lookup"><span data-stu-id="753d5-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="753d5-271">Di seguito sono riportati tre esempi di metodi estendibili utili:</span><span class="sxs-lookup"><span data-stu-id="753d5-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="753d5-272">Se **validateWrite** nella tabella TSTimesheetLine restituisce **false** durante un'operazione di salvataggio per una riga del foglio presenze, viene visualizzato un messaggio di errore nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="753d5-273">Se **validateSubmit** nella tabella TSTimesheetTable restituisce **false** durante l'invio del foglio presenze nell'app, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="753d5-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="753d5-274">La logica che compila i campi (ad esempio **Proprietà riga**) durante il metodo **insert** nella tabella TSTimesheetLine verrà ancora eseguita.</span><span class="sxs-lookup"><span data-stu-id="753d5-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="753d5-275">Nascondere e contrassegnare campi predefiniti come campi di sola lettura mediante la configurazione</span><span class="sxs-lookup"><span data-stu-id="753d5-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="753d5-276">A partire dai parametri di progetto, è possibile impostare i campi predefiniti come campi di sola lettura o nasconderli nell'app.</span><span class="sxs-lookup"><span data-stu-id="753d5-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="753d5-277">Impostare le opzioni nella sezione **Fogli presenze per dispositivi mobili** della scheda **Foglio presenze** nella pagina **Parametri Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="753d5-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Parametri progetto](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="753d5-279">Modifica delle attività selezionabili tramite le estensioni</span><span class="sxs-lookup"><span data-stu-id="753d5-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="753d5-280">Le attività selezionabili per un progetto vengono immesse mediante i metodi **getActivitiesForProject()** and **getActivityQuery()** nella classe **TsTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="753d5-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="753d5-281">È possibile utilizzare la catena di comando per modificare questo comportamento e associare lo scenario aziendale alle attività selezionabili per un progetto specifico.</span><span class="sxs-lookup"><span data-stu-id="753d5-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="753d5-282">Immissione di una categoria di progetto predefinita nelle voci del foglio presenze</span><span class="sxs-lookup"><span data-stu-id="753d5-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="753d5-283">L'immissione di una categoria di progetto predefinita nelle voci del foglio presenze si verifica su tre livelli.</span><span class="sxs-lookup"><span data-stu-id="753d5-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="753d5-284">È possibile utilizzare la catena di comando per estendere il comportamento a uno di questi livelli o a tutti per ottenere il comportamento desiderato.</span><span class="sxs-lookup"><span data-stu-id="753d5-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="753d5-285">Viene utilizzata la gerarchia seguente:</span><span class="sxs-lookup"><span data-stu-id="753d5-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="753d5-286">L'app tenta di inserire la categoria predefinita dalla risorsa di progetto.</span><span class="sxs-lookup"><span data-stu-id="753d5-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="753d5-287">Questa categoria predefinita viene impostata nei metodi **getCurrentUserResource** e **getDelegatedResourcesForCurrentUser** della classe **TSTimesheetSettingsService**.</span><span class="sxs-lookup"><span data-stu-id="753d5-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="753d5-288">Se la categoria predefinita non viene specificata a livello di risorsa del progetto, l'app tenta di acquisirla dall'attività di progetto.</span><span class="sxs-lookup"><span data-stu-id="753d5-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="753d5-289">Questa categoria predefinita viene impostata nel metodo **getActivitiesForProject** della classe **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="753d5-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="753d5-290">Se la categoria predefinita non viene specificata a livello di attività del progetto, viene acquisita dai parametri del progetto.</span><span class="sxs-lookup"><span data-stu-id="753d5-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="753d5-291">Questa categoria predefinita viene impostata nel metodo **getProjectDetailsbyRule** della classe **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="753d5-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>
