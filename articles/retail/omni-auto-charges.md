<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="omni-auto-charges.md" target-language="it-IT">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>omni-auto-charges.2f6e37.47829a6fcae37e03510929dc46b942455016df0b.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>47829a6fcae37e03510929dc46b942455016df0b</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\omni-auto-charges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Addebiti automatici avanzati omnicanale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes capabilities for managing additional order charges for Retail channel orders using advanced auto charges features.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo argomento vengono descritte le funzionalità per la gestione delle spese ordine aggiuntive relative agli ordini dei canali di vendita al dettaglio utilizzando funzionalità di addebiti automatici avanzati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Addebiti automatici avanzati omnicanale</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information on configuration and deployment of the advanced auto-charges feature which are available in Dynamics 365 for Retail version 10.0.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo argomento vengono fornite informazioni sulla configurazione e la distribuzione delle funzionalità di addebiti automatici avanzati disponibili in Dynamics 365 for Retail versione 10.0.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When the advanced auto-charges features are enabled, orders created in any supported Retail channel (point of sale (POS), call center, and online), can take advantage of the <bpt id="p1">[</bpt>auto-charges<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations defined in the ERP application for both header and line-level related charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando le funzionalità di addebiti automatici avanzati sono abilitate, per gli ordini creati in qualsiasi canale di vendita al dettaglio (POS, servizio clienti, online) è possibile utilizzare le configurazioni degli <bpt id="p1">[</bpt>addebiti automatici<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> definite nell'applicazione ERP per le spese correlate a livello di riga e intestazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In releases prior to Dynamics 365 for Retail version 10.0, <bpt id="p1">[</bpt>auto-charge<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations are only accessible by orders created in e-Commerce and call center channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nelle versioni precedenti alla versione 10.0 di Dynamics 365 for Retail, le configurazioni di <bpt id="p1">[</bpt>addebiti automatici<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> sono accessibili solo tramite ordini creati nei canali e-Commerce e del servizio clienti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>In versions 10.0 and later, POS-created orders can leverage the auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nelle versioni 10.0 e successive, gli ordini creati dal POS possono utilizzare le configurazioni degli addebiti automatici.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>That way, additional miscellaneous charges can systematically be added to sales transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In tal modo, le spese varie aggiuntive possono essere aggiunte in modo sistematico alle transazioni di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>When using releases prior to version 10.0, a POS user is prompted to manually enter a shipping fee during the creation of a "ship all" or "ship selected" POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando si utilizzano le versioni precedenti alla versione 10.0, a un utente POS viene richiesto di immettere manualmente le spese di spedizione durante la creazione di una transazione POS "Spedisci tutto" o "Spedizione selezionata".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>While the miscellaneous charges capabilities of the application are utilized in respect to how the charges are written to the order, no systematic calculation is provided – the calculation relies on the user's input to determine the value of the charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Sebbene le funzionalità relative alle spese varie dell'applicazione siano utilizzate secondo il modo in cui le spese sono scritte nell'ordine, non viene fornito un calcolo sistematico; il calcolo è basato sull'input dell'utente per determinare il valore delle spese.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The charges can only be added as a single "shipping" related charges code and cannot easily be edited or changed in the POS after they are created.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le spese possono essere aggiunte solo come singolo codice spese relativo alla "spedizione" e non possono essere modificate facilmente nel POS dopo la creazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The use of manual prompts to add shipping charges is still available in versions 10.0 and later.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utilizzo di richieste manuali per l'aggiunta di spese di spedizione è ancora disponibile nelle versioni 10.0 e successive.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If an organization does not enable the <bpt id="p1">**</bpt>Advanced Auto-charges<ept id="p1">**</ept> parameter, the POS prompts for manual entry of charges will remain the same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se un'organizzazione non abilita il parametro <bpt id="p1">**</bpt>Spese automatiche avanzate<ept id="p1">**</ept>, le richieste POS per l'immissione manuale delle spese rimarranno invariate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>With the advanced auto-charges feature, POS users can have systematic calculations for any defined miscellaneous charges based on auto-charges setup tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Con le funzionalità di addebiti automatici avanzati, gli utenti POS possono avere calcoli sistematici per qualsiasi spese varie definite basate sulle tabelle di impostazione degli addebiti automatici.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In addition, users will have the ability to add or edit an unlimited amount of additional charges and fees to any POS sales transaction at the header or line-level (for a cash and carry or customer order).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inoltre, gli utenti avranno la possibilità di aggiungere o modificare un importo illimitato di spese e commissioni aggiuntive a una transazione di vendita POS a livello di riga o intestazione (per un ordine cliente o cash and carry).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Enabling advanced auto-charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Abilitazione degli addebiti automatici avanzati</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept> page, go to the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab. On the <bpt id="p3">**</bpt>Charges<ept id="p3">**</ept> FastTab, set <bpt id="p4">**</bpt>Use advanced auto-charges<ept id="p4">**</ept> to <bpt id="p5">**</bpt>Yes<ept id="p5">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Nella pagina <bpt id="p1">**</bpt>Vendita al dettaglio <ph id="ph1">\&gt;</ph> Impostazione sedi centrali <ph id="ph2">\&gt;</ph> Parametri <ph id="ph3">\&gt;</ph> Parametri di vendita al dettaglio<ept id="p1">**</ept>, passare alla scheda <bpt id="p2">**</bpt>Ordini cliente<ept id="p2">**</ept>. Nella scheda Dettaglio <bpt id="p3">**</bpt>Addebiti<ept id="p3">**</ept>, immettere <bpt id="p4">**</bpt>Utilizza addebiti automatici avanzati<ept id="p4">**</ept> su <bpt id="p5">**</bpt>Sì<ept id="p5">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Advanced Auto-Charges Parameter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parametro Addebiti automatici avanzati</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When advanced auto-charges are enabled, users are no longer prompted to manually enter a shipping charge at the POS terminal when creating a ship-all or ship-selected customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando gli addebiti automatici avanzati sono abilitati, agli utenti non viene più richiesto di immettere manualmente le spese di spedizione nel terminale POS quando si crea un ordine cliente con Spedisci tutto o Spedizione selezionata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>POS order charges are systematically calculated and added to the POS transaction (if a corresponding auto-charges table that matches the criterion of the order being created are found).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le spese ordine POS sono calcolate in modo sistematico e aggiunte alla transazione POS (se viene trovata una tabella di addebiti automatici corrispondente che soddisfa il criterio dell'ordine creato).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Users can also add or maintain header or line-level charges manually through newly added POS operations that can be added to the POS screen layouts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gli utenti possono anche aggiungere o gestire le spese a livello di riga o intestazione manualmente mediante operazioni POS aggiunte di recente che possono essere aggiunte ai layout dello schermo POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>When advanced auto-charges are enabled, the existing <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> for <bpt id="p2">**</bpt>Shipping charges code<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> are no longer utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando gli addebiti automatici avanzati sono abilitati, i <bpt id="p1">**</bpt>parametri di vendita al dettaglio<ept id="p1">**</ept> esistenti per <bpt id="p2">**</bpt>Codice spese di spedizione<ept id="p2">**</ept> e <bpt id="p3">**</bpt>Rimborso spese di spedizione<ept id="p3">**</ept> non sono più utilizzati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>These parameters are only applicable if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questi parametri sono applicabili solo se il parametro <bpt id="p1">**</bpt>Utilizza addebiti automatici avanzati<ept id="p1">**</ept> è impostato su <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Before you enable this feature, ensure that you have tested and trained your employees, as this will change the business process flow of how shipping or other charges are calculated and added to POS sales orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prima di abilitare questa funzionalità, assicurarsi di formare i dipendenti, in quanto modifica il flusso di processo aziendale relativo al modo in cui le spese di spedizione o altre spese sono calcolate e aggiunte agli ordini cliente POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Make sure that you understand the impact of the process flow to the creation of transactions from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Assicurarsi di comprendere l'impatto del flusso di processo sulla creazione delle transazioni dal POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For call center and e-Commerce orders, the impact of enabling advanced auto-charges is minimal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per gli ordini e-Commerce e del servizio clienti, l'impatto dell'abilitazione degli addebiti automatici avanzati è minimo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Call center and e-Commerce applications will continue to have the same behavior they have had historically related to the auto-charges tables to calculate additional order fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le applicazioni e-Commerce e del servizio clienti continueranno ad avere lo stesso comportamento in relazione alle tabelle di addebiti automatici per calcolare ulteriori spese di ordine.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Call center channel users will continue to have the ability to manually edit any system calculated auto-charges at the header or line level, or manually add additional miscellaneous charges at the header or line level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gli utenti dei canali del servizio utenti continueranno ad avere la possibilità di modificare manualmente gli addebiti automatici calcolati dal sistema a livello di riga o intestazione o di aggiungere manualmente ulteriori spese varie a livello di riga o di intestazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Additional POS operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ulteriori operazioni POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>For advanced auto-charges to work properly in your POS application environment, new POS operations have been added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Affinché gli addebiti automatici avanzati funzionino correttamente nell'ambiente dell'applicazione POS sono state aggiunte nuove operazioni POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>These operations must be added to your <bpt id="p1">[</bpt>POS screen layouts<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> and deployed to the POS devices as you deploy advanced auto-charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Queste operazioni devono essere aggiunte ai <bpt id="p1">[</bpt>layout dello schermo POS<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> e distribuite ai dispositivi POS quando si distribuiscono gli addebiti automatici avanzati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>If these operations are not added, users will not be able to manage or maintain miscellaneous charges on the POS transactions and will have no way of adjusting or changing the charges values that are systematically calculated based on auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se queste operazioni non sono aggiunte, gli utenti non potranno gestire le spese varie nelle transazioni POS e non potranno rettificare o modificare i valori spese calcolati in modo sistematico in base alle configurazioni di addebiti automatici.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>At minimum, it is suggested that you deploy the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation to your POS layout.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Si consiglia di distribuire almeno l'operazione <bpt id="p1">**</bpt>Gestisci spese<ept id="p1">**</ept> al layout POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The new operations are as follows.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Le nuove operazioni sono descritte di seguito.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source><bpt id="p1">**</bpt>142 - Manage charges<ept id="p1">**</ept> – Use this operation to allow POS users to view and edit miscellaneous charges for the POS transaction that were either added manually or systematically through auto-charges calculations.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>142 - Gestisci spese<ept id="p1">**</ept> – Utilizzare questa operazione per consentire agli utenti POS di visualizzare e modificare spese varie per la transazione POS aggiunte manualmente o in modo sistematico mediante calcoli degli addebiti automatici.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>141 - Add header charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a header-level miscellaneous charge to any POS sales transaction (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>141 - Aggiungi spese intestazione<ept id="p1">**</ept> – Utilizzare questa operazione per consentire all'utente di aggiungere manualmente spese varie a livello di intestazione a qualsiasi transazione di vendita POS (e selezionare il codice spese da utilizzare).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>140 - Add line charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a line level miscellaneous charge to any POS sales transaction line (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>140 - Aggiungi spese riga<ept id="p1">**</ept> – Utilizzare questa operazione per consentire all'utente di aggiungere manualmente spese varie a livello di riga a qualsiasi riga di transazione di vendita POS (e selezionare il codice spese da utilizzare).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>143 - Recalculate charges<ept id="p1">**</ept> – Use this operation to perform a full re-calculation of the charges for the sales transaction.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>143 - Ricalcola spese<ept id="p1">**</ept> – Utilizzare questa operazione per eseguire un ricalcolo completo delle spese per la transazione di vendita.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Any previously user-overwritten auto-charges will be recalculated based on the current cart configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Qualsiasi addebito automatico sovrascritto dall'utente in precedenza verrà ricalcolato in base alla configurazione corrente del carrello.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>As with all POS operations, security configurations can be made to require manager approval in order to execute the operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Come con le operazioni POS, le configurazioni di protezione possono essere effettuate per richiedere l'approvazione del responsabile per l'esecuzione dell'operazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It is important to note that the above listed POS operations can also be added to the POS layout even if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È importante notare che le operazioni POS elencate sopra possono anche essere aggiunte al layout POS anche se il parametro <bpt id="p1">**</bpt>Utilizza spese automatiche avanzate<ept id="p1">**</ept> è disabilitato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In this scenario, organizations will still get added benefits of being able to view manually added charges and edit them using the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo scenario, le organizzazioni avranno ancora il vantaggio di poter visualizzare manualmente le spese aggiunte e di modificarle utilizzando l'operazione <bpt id="p1">**</bpt>Gestisci spese<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Users may also use the <bpt id="p1">**</bpt>Add header charges<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Add line charges<ept id="p2">**</ept> operations for POS transactions even when <bpt id="p3">**</bpt>Use advanced auto-charges<ept id="p3">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gli utenti possono anche utilizzare le operazioni <bpt id="p2">**</bpt>Aggiungi spese intestazione<ept id="p2">**</ept> e <bpt id="p1">**</bpt>Aggiungi spese riga<ept id="p1">**</ept> per le transazioni POS anche se il parametro <bpt id="p3">**</bpt>Utilizza spese automatiche avanzate<ept id="p3">**</ept> è disabilitato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation has less functionality if used when <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'operazione <bpt id="p1">**</bpt>Ricalcola spese<ept id="p1">**</ept> è meno funzionale se utilizzata quando <bpt id="p2">**</bpt>Utilizza spese automatiche avanzate<ept id="p2">**</ept> è disabilitato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In this sceanrio, nothing would be recalculated and any charges manually added to the transaction would just reset to $0.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questo scenario, non viene ricalcolato nulla e tutte le spese aggiunte manualmente alla transazione vengono reimpostate su $0.00.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Use case examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempi di casi di utilizzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In this section, sample use cases are presented to help you understand the configuration and usage of auto-charges and miscellaneous charges within the context of Retail channel orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">In questa sezione vengono presentati casi di utilizzo di esempio allo scopo di facilitare la comprensione della configurazione e dell'utilizzo degli addebiti automatici e delle spese varie nel contesto degli ordini dei canali di vendita al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>These examples illustrate the behavior of the application when the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter has been enabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questi esempi illustrano il comportamento dell'applicazione quando il parametro <bpt id="p1">**</bpt>Utilizza addebiti automatici avanzati<ept id="p1">**</ept> è stato abilitato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Auto-charges header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di spese intestazione con addebiti automatici</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenario del caso di utilizzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>A retailer wants to automatically add charges for freight when transactions are created in any Retail channel that require a shipment of products to the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un rivenditore desidera aggiungere automaticamente le spese di spedizione quando si creano transazioni in qualsiasi canale di vendita al dettaglio che richiedono la spedizione dei prodotti al cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The retailer offers 2 methods of delivery: Ground and Air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il rivenditore offre 2 metodi di consegna: Su strada e Via aerea.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>If a customer chooses Ground delivery and the order value is less than $100, the retailer wants to charge the customer a freight charge of $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se un cliente sceglie la consegna Su strada e il valore dell'ordine è inferiore a $100, il rivenditore vuole addebitare al cliente una spesa di trasporto di $10.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>If the order is over $100 in value and the customer chooses ground shipping, the customer will not be charged any additional freight fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se il valore dell'ordine è superiore a $100 e il cliente sceglie la spedizione via terra, al cliente non saranno addebitate ulteriori spese di spedizione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If the customer chooses the Air method of delivery for all orders, regardless of their total value, will be charged a freight fee of $20.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se il cliente sceglie la spedizione Via aerea per tutti gli ordini, indipendentemente dal valore totale degli stessi, gli verranno addebitate delle spese di spedizione di $20.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostazione e configurazione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>This scenario requires the configuration of two auto-charges tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo scenario richiede la configurazione di due tabelle di addebiti automatici.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Go to <bpt id="p1">**</bpt>Accounts receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accedere a <bpt id="p1">**</bpt>Contabilità clienti <ph id="ph1">\&gt;</ph> Impostazione spese <ph id="ph2">\&gt;</ph> Spese automatiche<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Configure two different header-level auto charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurare due differenti addebiti automatici a livello di intestazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Configure one for the "Ground mode" of delivery and one for the "Air mode" of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurarne uno per la modalità di consegna "Su strada" e uno per la consegna "Via aerea".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>For this scenario, configure them to be used for "All customers".</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per questo scenario, configurarli per l'utilizzo di "Tutti i clienti".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For the ground delivery charges, in the lines section of the <bpt id="p1">**</bpt>Auto-charges<ept id="p1">**</ept> page, define a charge that will be applied for orders between $.01 and $100 as $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per le spese di consegna su strada, nella sezione delle righe della pagina <bpt id="p1">**</bpt>Spese automatiche<ept id="p1">**</ept>, definire un addebito di $10 che verrà applicato per gli ordini tra $0,01 e $100.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Create another charges line to indicate orders over $100.01 will have no charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Creare un'altra riga spese per indicare che gli ordini superiori a $100,01 non comporteranno spese.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di addebiti automatici</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>For the air delivery charges, in the lines section of the auto-charges form, define a charge of $20.00 that will be applied to all orders (between a value of $.01 to $9,999,999).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per le spese di consegna via aerea, nella sezione delle righe del modulo degli addebiti automatici, definire un addebito di $20 che verrà applicata a tutti gli ordini (per un valore tra $0,01 e $9.999.999).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Send the changes to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inviare le spese a un server di vendita al dettaglio/database canale di modo che il POS possa utilizzarle eseguendo il processo <bpt id="p1">**</bpt>1040 - Programmazione della distribuzione<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione delle vendite per questo scenario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>After the configuration steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have the ground or air delivery methods set at the header level will utilize these charges and automatically apply them to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dopo il completamento della procedura di configurazione descritta sopra e l'applicazione delle spese al database del canale, qualsiasi ordine cliente o transazione di vendita creato nel POS, nel servizio clienti o nei canali di e-Commerce che hanno i metodi di spedizione Su strada e Via aerea impostati a livello di intestazione utilizzerà tali spese e le applicherà automaticamente alla vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>At this time the charges will apply to all sales transactions created within the legal entity that utilize these delivery modes, as there is no functionality to designate that an auto-charge configuration will only apply to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A questo punto, le spese verranno applicate a tutte le transazioni di vendita create nell'ambito della persona giuridica che utilizzano queste modalità di consegna, in quanti non è presente una funzionalità per designare che una configurazione di addebito automatico verrà applicata solo a uno specifico canale di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For POS and e-Commerce scenarios, because there is no clearly defined "header" on these orders, header-level charges will only apply if all sales lines on the transaction are set to ship with the exact same mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per gli scenari relativi a POS e e-Commerce, poiché non si ha un'"intestazione" definita chiaramente su tali ordini, le spese a livello di intestazione verranno applicate solo se tutte le righe di vendita nella transazione sono impostate per la spedizione con la stessa identica modalità di consegna.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If there are "mixed-modes" of fulfillment on the transactions created by POS or e-Commerce, only line-level auto-charges will be considered and applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se sono presenti "modalità miste" di evasione nelle transazioni create mediante POS o e-Commerce, soltanto gli addebiti automatici a livello di riga verranno considerati e applicati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>In call center scenarios, the user has control over the setting of the delivery mode at the order header, therefore header-level charges will apply for these orders even if some of the sales lines have been configured to use a different mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Negli scenari relativi al servizio clienti, l'utente controlla l'impostazione della modalità di consegna nell'intestazione dell'ordine, quindi le spese a livello di intestazione verranno applicate per tali ordini anche se alcune delle righe di vendita sono state configurate per utilizzare una modalità di consegna differente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Header-level charges for call center orders will always be based on the mode of delivery that is defined at the order header level of the sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le spese a livello di intestazione per gli ordini del servizio clienti saranno sempre basate sulla modalità di consegna definita a livello di intestazione dell'ordine cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Auto-charges line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di spese riga con addebiti automatici</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenario del caso di utilizzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>A retailer wants to add an additional charge to the customer for setup fees when the customer purchases a particular model of computer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un rivenditore desidera aggiungere ulteriori spese al cliente per le commissioni di impostazione quando il cliente acquista un determinato modello di computer.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>This computer requires additional non-optional setup actions that the retailer will perform for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo computer richiede ulteriori azioni di configurazione non opzionali che il rivenditore eseguirà per il cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The retailer has informed customers that there will be an additional fee for this setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il rivenditore ha informato i clienti che verrà applicata un'ulteriore commissione per questa configurazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The retailer prefers to manage the charges related to this fee separately from the product sales price for financial reporting purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il rivenditore preferisce gestire le spese relative a questa commissione separatamente dal prezzo di vendita del prodotto per i report finanziari.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>A setup fee of $19.99 will be charged to the customer when this specific computer is purchased in any retail channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Una commissione di impostazione di $19,99 verrà addebitata al cliente quando questo specifico computer viene acquistato in un qualsiasi canale di vendita al dettaglio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostazione e configurazione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This scenario requires the configuration of one line-level auto charges table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo scenario richiede la configurazione di una tabella di addebiti automatici a livello di riga.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Go to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accedere a <bpt id="p1">**</bpt>Contabilità clienti <ph id="ph1">\&gt;</ph> Impostazione spese <ph id="ph2">\&gt;</ph> Spese automatiche<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Set the <bpt id="p1">**</bpt>Level<ept id="p1">**</ept> drop-down menu to <bpt id="p2">**</bpt>Line<ept id="p2">**</ept>, and create a new auto-charges record for all customers and for the specific product or product group where the setup fees will be charged.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostare il menu a discesa <bpt id="p1">**</bpt>Livello<ept id="p1">**</ept> su <bpt id="p2">**</bpt>Riga<ept id="p2">**</ept> e creare un nuovo record di addebiti automatici per tutti i clienti e per lo specifico prodotto o gruppo di prodotti a cui le commissioni di impostazione verranno addebitate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di addebiti automatici</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inviare le spese a un server di vendita al dettaglio/database del canale di modo che il POS possa utilizzarle eseguendo il processo <bpt id="p1">**</bpt>1040 - Programmazione della distribuzione<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione delle vendite per questo scenario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>After the configurations steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have this item on the order will trigger a line-level charge to be systematically added to the order total.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dopo il completamento della procedura di configurazione precedente e l'applicazione delle modifiche al database del canale, qualsiasi ordine cliente o transazione di vendita creata nel POS, nel servizio clienti o nei canali di e-Commerce che include questo articolo genererà una spesa a livello di riga da aggiungere sistematicamente al totale dell'ordine.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>At this time the charges will apply to any sales line that matches the configuration of the line-level auto charges within the legal entity, as there is no functionality to configure a line-level auto-charge to apply only to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A questo punto, le spese verranno applicate a qualsiasi riga di vendita che corrisponde alla configurazione degli addebiti automatici a livello di riga della persona giuridica, in quanto non è presente una funzionalità per configurare un addebito automatico a livello di riga da applicare solo a uno specifico canale di vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Manual header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di spese intestazione manuali</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Use case scenario description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Descrizione dello scenario del caso di utilizzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>A retailer is making an exception to typical processes by offering to provide a special home delivery of products to a customers who order products in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un rivenditore fa un'eccezione ai processi tipici fornendo una speciale consegna a domicilio dei prodotti ai clienti che ordinano prodotti nel punto vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The retailer and the customer have agreed that the customer will pay an additional $25 handling fee for this service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il rivenditore e il cliente hanno concordato che il cliente pagherà una spesa di movimentazione aggiuntiva di $25 per tale servizio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The order-taker needs to add this additional fee to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'incaricato dell'ordine deve aggiungere questa commissione aggiuntiva alla transazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Because the fee is a blanket fee and not related to any single product on the order, a header charge will be utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Poiché la commissione è una commissione di copertura non correlata a un qualsiasi singolo prodotto nell'ordine, verrà utilizzata una spesa intestazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostazione e configurazione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Verificare che il codice spese che verrà utilizzato in questo scenario sia stato configurato correttamente selezionando <bpt id="p1">**</bpt>Contabilità clienti <ph id="ph1">\&gt;</ph> Impostazione spese <ph id="ph2">\&gt;</ph> Spese<ept id="p1">**</ept> per definire un codice spese appropriato per lo scenario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempi di spese</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Se la spesa deve essere considerata come una spesa relativa alla "spedizione" nell'ambito di sconti o promozioni inerenti allo spedizione, impostare <bpt id="p1">**</bpt>Spese di spedizione<ept id="p1">**</ept> nel codice spese su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>If this charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se questa spesa può inoltre essere sistematicamente rimborsata durante l'elaborazione di una transazione di reso nell'applicazione POS, impostare <bpt id="p1">**</bpt>Rimborsabile<ept id="p1">**</ept> su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il flag <bpt id="p1">**</bpt>Rimborsabile<ept id="p1">**</ept> è applicabile solo quando il parametro <bpt id="p2">**</bpt>Utilizza addebiti automatici avanzati<ept id="p2">**</ept> è impostato su <bpt id="p3">**</bpt>Sì<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inviare le spese a un server di vendita al dettaglio/database del canale di modo che il POS possa utilizzarle eseguendo il processo <bpt id="p1">**</bpt>1040 - Programmazione della distribuzione<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>The <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 141).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'operazione <bpt id="p1">**</bpt>Aggiungi spese intestazione<ept id="p1">**</ept> deve essere configurata nel <bpt id="p2">[</bpt>layout dello schermo POS<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> di modo che sia possibile chiamare questa operazione (141) tramite un pulsante accessibile all'utente dal POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le modifiche al layout dello schermo devono essere distribuite al canale di vendita al dettaglio nonché attraverso la funzione di programmazione della distribuzione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Sales processing of manual header charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione delle vendite delle spese intestazione manuali</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per eseguire lo scenario nell'applicazione POS, l'utente POS creerà la transazione di vendita come al solito, aggiungendo i prodotti e qualsiasi altra configurazione alla vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Prior to collecting payment, the user should execute the <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation, which will prompt the user to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prima della riscossione del pagamento, l'utente deve eseguire l'operazione <bpt id="p1">**</bpt>Aggiungi spese intestazione<ept id="p1">**</ept>, che richiederà all'utente di selezionare un codice spese e di immettere il valore delle spese.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Once the user completes the process, the charge will be added to the sales order as a header-level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dopo che l'utente ha completato il processo, la spesa viene aggiunta all'ordine cliente come spesa a livello di intestazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>This process can be applied in the call center by using the existing <bpt id="p1">**</bpt>Charges<ept id="p1">**</ept> feature found on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab on the toolbar.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questo processo può essere applicato al servizio clienti utilizzando le funzionalità <bpt id="p1">**</bpt>Spese<ept id="p1">**</ept> presente nella scheda <bpt id="p2">**</bpt>Vendi<ept id="p2">**</ept> nella barra degli strumenti.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page, the user can add a new charges line to the order header.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Gestisci spese<ept id="p1">**</ept>, l'utente può aggiungere una nuove riga spese all'intestazione dell'ordine.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Manual line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esempio di spese riga manuali</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scenario del caso di utilizzo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>A customer has requested that 2 of the 5 items on their sales order be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un cliente ha richiesto una confezione regalo per 2 dei 5 articoli nell'ordine cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>The retailer offers this optional service for a fee of $2.00 per item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il rivenditore fornisce questo servizio opzionale per una spesa di $2 per articolo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The order-taker will need to add these fees to the specific items that need to be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'incaricato dell'ordine dovrà aggiungere queste spese agli articoli per i quali è stata richiesta la confezione regalo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impostazione e configurazione</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Verificare che il codice spese che verrà utilizzato in questo scenario sia stato configurato correttamente selezionando <bpt id="p1">**</bpt>Contabilità clienti <ph id="ph1">\&gt;</ph> Impostazione spese <ph id="ph2">\&gt;</ph> Spese<ept id="p1">**</ept> per definire un codice spese appropriato per lo scenario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set the <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se la spesa deve essere considerata come relativa alla "spedizione" nell'ambito di sconti o promozioni inerenti allo spedizione, impostare <bpt id="p1">**</bpt>Spese di spedizione<ept id="p1">**</ept> nel codice spese su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>If the charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se la spesa può inoltre essere sistematicamente rimborsata durante l'elaborazione di una transazione di reso nell'applicazione POS, impostare <bpt id="p1">**</bpt>Rimborsabile<ept id="p1">**</ept> su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il flag <bpt id="p1">**</bpt>Rimborsabile<ept id="p1">**</ept> è applicabile solo quando il parametro <bpt id="p2">**</bpt>Utilizza addebiti automatici avanzati<ept id="p2">**</ept> è impostato su <bpt id="p3">**</bpt>Sì<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inviare le spese a un server di vendita al dettaglio/database del canale di modo che il POS possa utilizzarle eseguendo il processo <bpt id="p1">**</bpt>1040 - Programmazione della distribuzione<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 140).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'operazione <bpt id="p1">**</bpt>Aggiungi spese riga<ept id="p1">**</ept> deve essere configurata nel <bpt id="p2">[</bpt>layout dello schermo POS<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> di modo che sia possibile chiamare questa operazione (140) tramite un pulsante accessibile all'utente dal POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le modifiche al layout dello schermo devono essere distribuite al canale di vendita al dettaglio nonché attraverso la funzione di programmazione della distribuzione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Sales processing of the manual line charge</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Elaborazione delle vendite delle spese riga manuali</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per eseguire lo scenario nell'applicazione POS, l'utente POS creerà la transazione di vendita come al solito, aggiungendo i prodotti e qualsiasi altra configurazione alla vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Prior to collecting payment, the user should select the specific line where the charge will apply from the POS item list display and execute the <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prima della riscossione del pagamento, l'utente deve selezionare la riga specifica in cui la spesa verrà applicata dal display dell'elenco di articoli POS ed eseguire l'operazione <bpt id="p1">**</bpt>Aggiungere spese riga<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>The user will be prompted to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">All'utente verrà richiesto di selezionare un codice spese e immettere il valore delle spese.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Once the user completes the process, the charge will be linked to the line and added to the order total as a line level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dopo che l'utente ha completato il processo, la spesa viene collegata alla riga e aggiunta al totale dell'ordine come spesa a livello di riga.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The user can repeat the process to add additional line charges to other items lines on the transaction if needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utente può ripetere il processo per aggiungere ulteriori spese riga ad altre righe di articoli nella transazione se necessario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The same process can be applied in the call center by using the "maintain charges" feature found under the <bpt id="p1">**</bpt>Financials<ept id="p1">**</ept> drop-down menu in the <bpt id="p2">**</bpt>Sales order lines<ept id="p2">**</ept> section on the <bpt id="p3">**</bpt>Sales order<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lo stesso processo può essere applicato nel call center mediante la funzionalità di "gestione delle spese" nel menu a discesa <bpt id="p1">**</bpt>Dati finanziari<ept id="p1">**</ept> della sezione <bpt id="p2">**</bpt>Righe ordine cliente<ept id="p2">**</ept> nella pagina <bpt id="p3">**</bpt>Ordine cliente<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>This will open the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page where the user can add a new line specific charge to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Questa operazione visualizzerà la pagina <bpt id="p1">**</bpt>Gestisci spese<ept id="p1">**</ept> dove l'utente può aggiungere una nuova spesa riga alla transazione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Additional features</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Funzionalità aggiuntive</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Editing charges on a POS sales transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Modifica delle spese in una transazione di vendita POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>The <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation (142) should be added to the <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a user can view and edit or override any system-calculated or manually-created header or line-level charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'operazione <bpt id="p1">**</bpt>Gestisci spese<ept id="p1">**</ept> (142) deve essere aggiunta al <bpt id="p2">[</bpt>layout dello schermo POS<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> di modo che un utente possa visualizzare e modificare o sostituire qualsiasi spesa a livello di riga o di intestazione creata manualmente o calcolata dal sistema.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>If the operation is not added, users will not be able to adjust the value of the charges on the POS transaction, nor will they be able to view the details of the charges such as the type of charges code tied to the charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se l'operazione non viene aggiunta, gli utenti non potranno rettificare il valore delle spese nella transazione POS e nemmeno visualizzare i dettagli delle spese come il tipo di codice spese associato alla spesa.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>On the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> page in POS, the user can view both header and line-level charges details.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nella pagina <bpt id="p1">**</bpt>Gestisci spese<ept id="p1">**</ept> nel POS, l'utente può visualizzare i dettagli relativi alle spese a livello di intestazione o riga.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The user can use the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> function available on this page to make changes to the amount charged to a specific charges line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utente può utilizzare la funzione <bpt id="p1">**</bpt>Modifica<ept id="p1">**</ept> disponibile in questa pagina per apportare modifiche all'importo addebitato a una specifica riga spese.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>Once a charges line is overwritten manually, it will not be systematically recalculated unless the user initiates the <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando una riga spese viene sovrascritta manualmente, non verrà ricalcolata in modo sistematico a meno che l'utente non esegua l'operazione <bpt id="p1">**</bpt>Ricalcola spese<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>If the <bpt id="p1">**</bpt>Charge override reason code<ept id="p1">**</ept> has been configured on the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> setup page, the user will be prompted to provide a reason code when charges have been modified in the POS application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se l'opzione <bpt id="p1">**</bpt>Codice motivo forzatura spese<ept id="p1">**</ept> è stata configurata nella pagina di configurazione <bpt id="p2">**</bpt>Parametri di vendita al dettaglio<ept id="p2">**</ept>, all'utente verrà richiesto di fornire un codice motivo quando le spese vengono modificate nell'applicazione POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>If reason codes have been captured for overwritten charges, a new report is also available to review and audit these overrides.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se i codici motivo sono stati acquisiti per le spese sovrascritte, un nuovo report è inoltre disponibile per esaminare e controllare tali modifiche.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The report can be found in <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge override history<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il report si trova in <bpt id="p1">**</bpt>Vendita al dettaglio <ph id="ph1">\&gt;</ph> Richieste di informazioni e report <ph id="ph2">\&gt;</ph> Storico sostituzione spese<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Refunding charges on a POS return transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rimborso delle spese in una transazione di reso POS</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>If the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the existing retail parameter for <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> is no longer applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se il parametro <bpt id="p1">**</bpt>Utilizza addebiti automatici avanzati<ept id="p1">**</ept> è impostato su <bpt id="p2">**</bpt>Sì<ept id="p2">**</ept>, il parametro di vendita al dettaglio esistente per <bpt id="p3">**</bpt>Rimborso spese di spedizione<ept id="p3">**</ept> non è più applicabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>To indicate which charges should be systematically refunded to a customer when using advanced auto-charges, ensure the related charges code has been configured as <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per indicare quali spese devono essere rimborsate in modo sistematico a un cliente quando si utilizzano gli addebiti automatici avanzati, assicurarsi che il codice spese correlato sia stato configurato come <bpt id="p1">**</bpt>Rimborsabile<ept id="p1">**</ept> nella pagina <bpt id="p2">**</bpt>Codice spese<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Make sure that the settings have been synchronized to your Retail channel databases through distribution schedule processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Verificare che le impostazioni siano state sincronizzate ai database dei canali di vendita al dettaglio mediante l'elaborazione della programmazione della distribuzione.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Refunding charges on a return order transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Rimborso delle spese in una transazione ordine di reso</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Charges are not systematically refunded to <bpt id="p1">**</bpt>Return orders<ept id="p1">**</ept> created in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le spese non vengono rimborsate sistematicamente agli <bpt id="p1">**</bpt>ordini di reso<ept id="p1">**</ept> creati in Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>Users are required to select the <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> option when creating the <bpt id="p2">**</bpt>Return order<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Agli utenti viene richiesto di selezionare l'opzione <bpt id="p1">**</bpt>Copia spese<ept id="p1">**</ept> quando si crea l'<bpt id="p2">**</bpt>ordine di reso<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is not selected, charges from the original sales transaction will not be automatically refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se l'opzione <bpt id="p1">**</bpt>Copia spese<ept id="p1">**</ept> non è selezionata, le spese della transazione di vendita originale non verranno automaticamente rimborsate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is selected, all charges will be copied to the return order and the user can manually edit or remove any charges they do not want to have refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se l'opzione <bpt id="p1">**</bpt>Copia spese<ept id="p1">**</ept> è stata selezionata, tutte le spese verranno copiate nell'ordine di reso e l'utente può modificare o rimuovere manualmente tutte le spese che non desidera siano rimborsate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The call center return order process currently does not acknowledge the <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il processo dell'ordine di reso nel servizio clienti attualmente non consente l'utilizzo del flag <bpt id="p1">**</bpt>Rimborsabile<ept id="p1">**</ept> in <bpt id="p2">**</bpt>Codice spese<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Configuring POS receipts to show charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurazione di ricevute POS per visualizzare le spese</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>The following receipt elements have been added to the receipt line and footer to support the advanced auto-charges functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">I seguenti elementi di ricevuta sono stati aggiunti alla riga e al piè di pagina delle ricevute per supportare la funzionalità di addebiti automatici avanzati.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source><bpt id="p1">**</bpt>Line Shipping Charges<ept id="p1">**</ept> – This line-level element can be used to recap specific charges codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Spese di spedizione riga<ept id="p1">**</ept> – Questo elemento a livello di riga può essere utilizzato per ricapitolare specifici codici spese applicati alla riga di vendita.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Only charges codes that have been flagged as <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> charges on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page will be displayed here.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Solo i codici spese che sono stati contrassegnati come spese di <bpt id="p1">**</bpt>Spedizione<ept id="p1">**</ept> nella pagina <bpt id="p2">**</bpt>Codice spese<ept id="p2">**</ept> saranno visualizzati qui.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source><bpt id="p1">**</bpt>Line Other Charges<ept id="p1">**</ept> – This line-level element can be used to recap any non-shipping specific charge codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Altre spese riga<ept id="p1">**</ept> – Questo elemento a livello di riga può essere utilizzato per ricapitolare qualsiasi codice spese non di spedizione applicato alla riga di vendita.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>These are charges codes where the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page has not been enabled.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Questi sono codici spese in cui il flag <bpt id="p1">**</bpt>Spedizione<ept id="p1">**</ept> nella pagina <bpt id="p2">**</bpt>Codice spese<ept id="p2">**</ept> non è stato abilitato.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source><bpt id="p1">**</bpt>Order Shipping Charges Details<ept id="p1">**</ept> – This footer-level element displays the descriptions of the charge codes applied to the order that have been flagged as <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept> charges on the <bpt id="p3">**</bpt>Charges code<ept id="p3">**</ept> setup page.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Dettagli spese di spedizione ordine<ept id="p1">**</ept> – Questo elemento a livello di piè di pagina visualizza le descrizioni dei codici spese applicati all'ordine che sono stati contrassegnati come spese di <bpt id="p2">**</bpt>Spedizione<ept id="p2">**</ept> nella pagina di impostazione <bpt id="p3">**</bpt>Codice spese<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source><bpt id="p1">**</bpt>Order Shipping Charges<ept id="p1">**</ept> – This footer-level element shows the dollar value of the shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Spese di spedizione ordine<ept id="p1">**</ept> – Questo elemento a livello di piè di pagina mostra il valore in dollari delle spese correlate alla spedizione.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source><bpt id="p1">**</bpt>Order Other Charges Details<ept id="p1">**</ept> – This footer-level element displays the description of the charges codes applied to the order that have not been flagged as shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Dettagli altre spese ordine<ept id="p1">**</ept> – Questo elemento a livello di piè di pagina visualizza la descrizione dei codici spese applicati all'ordine che non sono stati contrassegnati come spese relative alla spedizione.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source><bpt id="p1">**</bpt>Order Other Charges<ept id="p1">**</ept> – This footer-level element displays the dollar value of the other charges that are not shipping-related.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match"><bpt id="p1">**</bpt>Altre spese ordine<ept id="p1">**</ept> – Questo elemento a livello di piè di pagina visualizza il valore in dollari delle altre spese non relative alla spedizione.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>It is recommended that the organization also add free text fields to the receipt footer, in order to define the areas where charges will be recapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si consiglia inoltre l'aggiunta di campi di testo libero al piè di pagina della ricevuta, per definire le aree in cui le spese verranno ricapitolate.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Preventing charges from being calculated until the POS order is completed</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Impedire il calcolo delle spese fino a che l'ordine POS sia completato</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Some organizations may prefer to wait until the user has finished adding all of the sales lines to the POS transaction before calculating charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Alcune organizzazioni possono preferire di attendere che l'utente abbia finito di aggiungere tutte le righe di vendita alla transazione POS prima di calcolare le spese.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>To prevent calculation of charges as items are added to the POS transaction, turn on the <bpt id="p1">**</bpt>Manual charge calculation<ept id="p1">**</ept> parameter in the <bpt id="p2">**</bpt>Functionality profile<ept id="p2">**</ept> used by the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Per impedire il calcolo delle spese quando degli articoli sono aggiunti alla transazione POS, attivare il parametro <bpt id="p1">**</bpt>Calcolo addebito manuale<ept id="p1">**</ept> nel <bpt id="p2">**</bpt>profilo funzionalità<ept id="p2">**</ept> utilizzato dal punto vendita.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Enabling this parameter will require the POS user to use the <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation when they have completed adding the products to the POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'attivazione di questo parametro richiederà all'utente POS di utilizzare l'operazione <bpt id="p1">**</bpt>Calcola totali<ept id="p1">**</ept> una volta completata l'aggiunta dei prodotti alla transazione POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>The <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation will then trigger the calculation of any auto charges for the order header or lines as applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'operazione <bpt id="p1">**</bpt>Calcola totali<ept id="p1">**</ept> avvierà il calcolo di tutti gli addebiti automatici per l'intestazione o le righe dell'ordine come applicabile.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Charges override reports</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Report di sostituzione delle spese</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>If users manually override the calculated charges or add a manual charge to the transaction, this data will available for auditing in the <bpt id="p1">**</bpt>Charge Override History<ept id="p1">**</ept> report.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se gli utenti sostituiscono manualmente le spese calcolate o aggiungono una spesa manuale alla transazione, questi dati saranno disponibili per il controllo nel report <bpt id="p1">**</bpt>Storico sostituzione spese<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>The report can be accessed from <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge Override History<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il report è accessibile da <bpt id="p1">**</bpt>Vendita al dettaglio <ph id="ph1">\&gt;</ph> Richieste di informazioni e report <ph id="ph2">\&gt;</ph> Storico sostituzione spese<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>It is important to note that the data needed for this report is imported from the channel database into HQ through the "P" distribution schedule jobs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">È importante notare che i dati necessari per questo report vengono importati dal database del canale in HQ mediante processi di programmazione della distribuzione "P".</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Therefore, information about overrides just performed in the POS may not be immediately available on this report until this job has uploaded the store transaction data into HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Di conseguenza, le informazioni sulle sostituzioni appena eseguite nel POS possono non essere immediatamente disponibili in questo report fino a che il processo non ha caricato i dati della transazione del punto vendita in HQ.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>