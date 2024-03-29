---
title: Contenuto Power BI per crediti e riscossioni
description: In questo articolo viene descritto cosa è incluso nel contenuto Power BI Gestione crediti e riscossioni. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.
author: ShivamPandey-msft
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 350c7ff2f0fa93d4ff99e2a11b9418413854a076
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889934"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Contenuto Power BI per crediti e riscossioni

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto cosa è incluso nel contenuto Microsoft Power BI **Gestione crediti e riscossioni**. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Gestione crediti e riscossioni** è stato creato per i responsabili di riscossione e credito e per gli addetti alla riscossione. Fornisce importanti metriche di raccolta e credito, ad esempio il tempo medio di incasso, il saldo scaduto, l'esposizione di credito e i clienti che hanno superato il limite di credito. Usa i dati transazionali e fornisce visualizzazioni aggregate di crediti e riscossioni per tutte le società. Sono inoltre presenti le suddivisioni per società, gruppo di clienti e cliente.

Il contenuto di Power BI è composto da 10 pagine di report:

- Due pagine di panoramica (una pagina per la panoramica dei crediti e una pagina per la panoramica delle riscossioni)
- Otto pagine di dettagli che forniscono informazioni sulle metriche di riscossione e credito suddivise tra le varie dimensioni

Tutti gli importi verranno visualizzati nella valuta di sistema. È possibile impostare la valuta di sistema nella pagina **Paramenti di sistema**.

Per impostazione predefinita, vengono visualizzati i dati di crediti e riscossioni per la società corrente. Per visualizzare i dati di tutte le società, assegnare il diritto **CustCollectionsBICrossCompany** al ruolo.

## <a name="setup-needed-to-view-power-bi-content"></a>Impostazione necessaria per visualizzare il contenuto di Power BI

La seguente impostazione deve essere completata per visualizzare i dati nelle rappresentazioni **Crediti e riscossioni cliente** di Power BI.

1. Andare a **Amministrazione sistema > Impostazioni > Parametri di sistema** per impostare **Valuta di sistema** e **Tipo di tasso di cambio del sistema**.
2. Vai a **Contabilità generale> Calendari > Calendari fiscali** per convalidare le date del calendario fiscale assegnate al periodo di tempo attivo.
3. Andare a **Contabilità generale > Impostazioni > Contabilità generale** e impostare **Valuta di contabilizzazione** e **Tipo di tasso di cambio**.
4. Definire i tassi di cambio tra le valute della transazioni e la valuta di contabilizzazione, la valuta di contabilizzazione e la valuta di sistema. A tale scopo, andare a **Contabilità generale > Valute > Tassi di cambio valutario**.
5. Andare a **Amministrazione sistema > Impostazioni > Archivio entità** per aggiornare la misura di aggregazione **CustCollectionsBIMeasurementsV2**.

>[!NOTE] 
> Le definizioni del periodo di v devono essere impostate in **Parametri contabilità clienti> Riscossioni > Valori predefiniti riscossioni** per abilitare l'aging dei dati nel contenuto Power BI.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI

Il contenuto di Power BI **Gestione crediti e riscossioni** viene visualizzato nell'area di lavoro **Crediti e riscossioni cliente**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

Il contenuto di Power BI **CustCollectionsBICrossCompany** include un report costituito da un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto Power BI **CustCollectionsBICrossCompany**.

| Pagina di report                 | Visualizzazione |
|-----------------------------|---------------|
| Panoramica sulle riscossioni        | <ul><li>Attività clienti scadute</li><li>Clienti con limite di credito superato</li><li>Tempo medio di incasso 30 giorni</li><li>Casi aperti</li><li>Numero medio di giorni per chiusura caso</li><li>Attività aperte</li><li>Numero medio di giorni per chiusura attività</li><li>Note d'interesse aperte</li><li>Lettera di sollecito aperte</li><li>Sospensione cliente</li><li>Sospensione vendite</li><li>Saldi con aging</li><li>Importi stato riscossioni</li><li>Importi codice riscossioni</li><li>Motivo di annullamento</li><li>Saldo esigibile per stato/regione</li><li>Pagamenti previsti</li></ul> |
| Panoramica sul credito             | <ul><li>Attività clienti scadute</li><li>Limite di credito e saldo esigibile</li><li>Griglia dei clienti con limite di credito superato</li><li>Clienti con limite di credito superato per società</li><li>Credito utilizzato rispetto al limite di credito totale</li><li>Limite di credito rispetto al credito utilizzato per stato/regione</li><li>Clienti per posizione finanziaria</li></ul> |
| Limite di credito                | <ul><li>Limite di credito</li><li>Dettagli limite di credito</li><li>Limite di credito per cliente</li><li>Limite di credito per gruppo di clienti</li><li>Limite di credito per posizione finanziaria per società</li><li>Limite di credito rispetto credito utilizzato per stato/regione</li></ul> |
| Clienti con limite di credito superato | <ul><li>Clienti con limite di credito superato</li><li>Dettagli clienti con limite di credito superato</li><li>Clienti con limite di credito superato per società</li><li>Clienti con limite di credito superato per gruppo di clienti</li><li>Clienti con limite di credito superato per stato/regione</li></ul> |
| Attività clienti scadute          | <ul><li>Attività clienti scadute</li><li>Dettagli attività clienti scadute</li><li>Attività clienti scadute per società</li><li>Attività clienti scadute per gruppo di clienti</li><li>Attività clienti scadute per stato/regione</li></ul> |
| Saldi con aging               | <ul><li>Saldi con aging</li><li>Dettagli saldi con aging</li><li>Saldi con aging per società</li><li>Saldi con aging per gruppo di clienti</li></ul> |
| Pagamenti previsti           | <ul><li>Pagamenti previsti</li><li>Dettagli pagamenti previsti</li><li>Pagamenti previsti per società</li><li>Pagamenti previsti per gruppo di clienti</li><li>Pagamenti previsti per stato/regione</li></ul> |
| Annullamenti                  | <ul><li>Annullamenti per stato/regione</li><li>Dettagli annullamenti</li><li>Annullamenti per conto principale</li><li>Annullamenti per società</li><li>Annullamenti per gruppo di clienti</li><li>Annullamenti per stato/regione</li></ul> |
| Stato riscossioni          | <ul><li>In controversia</li><li>Promessa di pagamento non mantenuta</li><li>Promessa di pagamento</li><li>Dettagli stato riscossioni</li><li>Importi stato riscossioni</li><li>Casi aperti</li><li>Attività aperte</li></ul> |
| Lettere di sollecito         | <ul><li>Importi codice riscossioni</li><li>Dettagli importi codice riscossioni</li><li>Importo lettera di sollecito per società</li><li>Importo lettera di sollecito per gruppo di clienti</li><li>Importo lettera di sollecito per stato/regione</li></ul> |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/) È inoltre possibile utilizzare la funzionalità di esportazione dati sottostanti per esportare i dati sottostanti riepilogati in una visualizzazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
