---
title: Funzionalità di accessibilità
description: In questo argomento vengono descritte le funzionalità progettate per aiutare gli utenti con varie disabilità.
author: TLeforMicrosoft
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 2d0dd3ebf4b50f43f9fb1893081ede2a93428c72
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798697"
---
# <a name="accessibility-features"></a>Funzionalità di accessibilità

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità progettate per consentire agli utenti con varie disabilità di utilizzare questa app. Ad esempio, sono disponibili funzionalità per le persone che utilizzano assistive technology per la vista come Microsoft Windows Narrator.

## <a name="windows-narrator-and-keyboard-only-access"></a>Windows Narrator e accesso solo tramite tastiera

Ciascun campo e controllo ha un'etichetta e una descrizione di collegamenti applicabili. Un'utilità per la lettura dello schermo riesce a leggere l'etichetta e la descrizione.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Collegamenti per le azioni più frequenti

Per la maggior parte degli utenti, l'utilizzo quotidiano del sistema implica l'immissione di molti dati e un'elevata interazione con la tastiera. Per migliorare l'esperienza utente, abbiamo creato dei collegamenti che aiutano a utilizzare lo schermo e i collegamenti per azioni specializzate. Per ulteriori informazioni, vedere [Tasti di scelta rapida](shortcut-keys.md).

## <a name="navigation-search"></a>Ricerca per navigazione

Qualsiasi pagina a cui è possibile accedere utilizzando il menu Pannello di navigazione, nel riquadro a sinistra, è disponibile anche tramite la casella **Cerca**. Premere ALT+G per spostare lo stato attivo nella casella **Cerca** e quindi digitare il nome o la descrizione della pagina.

!["Conti bancari" immesso nella casella Cerca](media/6d08b0be32808221023e2aa92d69fd70.png "'Conti bancari' immesso nella casella Cerca")

Per ulteriori informazioni, vedere [Ricerca per navigazione](navigation-search.md).

> [!NOTE]
> È possibile passare direttamente solo alle pagine di primo livello. Le pagine secondarie si basano sulle informazioni o sul contesto della pagina padre.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Ricerca di azioni per utenti che utilizzano solo la tastiere o per immissione di un elevato numero di dati

Ogni azione che viene fornita in una pagina è disponibile da una tastiera, tramite la sequenza di tabulazione. Informazioni sulla sequenza di tabulazione vengono fornite più avanti in questo argomento. Per eseguire le azioni più direttamente, è possibile utilizzare la funzionalità di ricerca di azione.

### <a name="example"></a>Esempio

Si desidera eseguire l'azione **Registro notifiche tramite posta elettronica** che appare nel gruppo **Notifica tramite posta elettronica** della scheda **Ordine cliente** nel riquadro azioni.

![Azione Registro notifiche tramite posta elettronica nel riquadro Azioni](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "Azione 'Registro notifiche tramite posta elettronica' nel riquadro Azioni")

Un'opzione consiste nell'utilizzare la tastiera. Premere CTRL+F6 per spostare lo stato attivo nel riquadro azioni, quindi premere TAB ripetutamente per spostarsi tra tutte le tabulazioni e le azioni fino a raggiungere l'azione **Registro notifiche tramite posta elettronica**.

Tuttavia, è possibile eseguire l'azione più direttamente. Da un punto qualsiasi nella pagina, premere CTRL+Apostrofo (') per visualizzare la casella di ricerca per le azioni.

![Casella di ricerca delle azioni](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "Casella di ricerca delle azioni")

Nella casella di ricerca, digitare parole che descrivono l'azione. L'azione viene resa disponibile e l'utente può eseguirla direttamente. Ad esempio, digitando **registro**, **notific** (parola parziale) o **posta elettronica**, è possibile passare alla funzionalità Registro notifiche tramite posta elettronica.

!["Posta elettronica" immessa nella casella Cerca](media/image4.png "'Posta elettronica' immessa nella casella Cerca")

!["Notifica" immessa nella casella Cerca](media/image5.png "'Notifica' immessa nella casella Cerca")

!["Registro" immesso nella casella Cerca](media/image6.png "'Registro' immesso nella casella Cerca")

Al termine, è possibile premere di nuovo CTRL+Apostrofo per riportare lo stato attivo sul campo che si stava utilizzando prima di eseguire la ricerca dell'azione.

Per ulteriori informazioni, vedere [Ricerca di azioni](action-search.md).

## <a name="tab-sequence"></a>Sequenza di tabulazione

Nell'utilizzo quotidiano del sistema, non tutti i campi sono obbligatori per l'esecuzione di attività tipiche. Pertanto, per impostazione predefinita, la sequenza di tabulazione è "ottimizzata". Gli arresti della tabulazione sono impostati solo su quei campi che sono fondamentali per gli scenari tipici.

Tuttavia, è possibile che alcuni campi che si utilizzano spesso per eseguire attività non siano inclusi nella sequenza di tabulazione predefinita. In questo caso, se si utilizza Windows Narrator, è possibile utilizzare le azioni della tastiera di Windows Narrator per accedere a questi campi e ispezionarne il contenuto. In alternativa, è possibile attivare l'opzione **Sequenza di schede migliorata** nella pagina **Opzioni**. Questa opzione integra nella sequenza di tabulazione tutti i campi modificabili e di sola lettura. È possibile utilizzare la personalizzazione della pagina per creare una sequenza di tabulazione personalizzata e omettere i campi che non devono fare parte della sequenza di tabulazione. Per ulteriori informazioni sulla personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

![Opzione "Sequenza di schede migliorata"](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "Opzione 'Sequenza di schede migliorata'")

## <a name="form-patterns"></a>Schemi di modulo

Quasi il 90 per cento delle pagine nell'app è basato su un piccolo set di schemi. Questi schemi sono indicati come *schemi di modulo*. Ogni schema di modulo viene utilizzato per fornire le azioni di uso più frequente nella pagina. Uno schema di modello aiuta a garantire la familiarità e la facilità di comprensione, perché le azioni e i dati di uso più frequente sono sempre presentati nella stessa posizione nelle diverse pagine. Grazie a questo numero ridotto di schemi di modulo, gli utenti possono facilmente apprendere l'utilizzo del sistema, indipendentemente dal numero delle pagine che lo compongono e possono utilizzarlo tranquillamente dopo che hanno riconosciuto gli schemi di modulo.

Per ulteriori informazioni sugli schemi di modulo, vedere [Stili e schemi di modulo](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Layout responsivo

Il prodotto è progettato per funzionare in vari dispositivi e fattori di forma, dagli schermi più piccoli agli schermi di grandi dimensioni che hanno la risoluzione massima. Il motore del layout responsivo consente agli utenti di ingrandire del 200 percento (o, in alcuni scenari, più del 200 percento).

Sugli smartphone e altri piccoli schermi, i controlli e il layout del modulo si adatteranno in modo reattivo per garantire la preferenza dei dati di base. Questi comportamenti reattivi possono anche includere la riduzione del numero di colonne in gruppi e schede in una singola colonna, nascondendo elementi shell e comprimendo il riquadro Azioni.

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Istruzioni per aiutare gli sviluppatori e i clienti a incorporare i concetti di accessibilità nelle proprie personalizzazioni

Per ulteriori informazioni sulle procedure consigliate da Microsoft per consentire all'accessibilità, vedere [Accessibilità per moduli, prodotti e controlli](../../dev-itpro/user-interface/enable-accessibility.md).
