---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: O FQDN externo de Webconferência permite que usuários externos ingressem em reuniões locais. Digite o FQDN (nome de domínio totalmente qualificado) da interface externa de Webconferência do Servidor de Borda herdado.
ms.openlocfilehash: 9e39d14ab59ab32e74162bdfa00447fddb68fa613fd33ccce445b11c0ae85ac6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333603"
---
# <a name="legacy-merge"></a>Mesclagem Herdada

O **FQDN externo de Webconferência** permite que usuários externos ingressem em reuniões locais. Digite o FQDN (nome de domínio totalmente qualificado) da interface externa de Webconferência do Servidor de Borda herdado.

O valor de **Porta externa de Webconferência Externa** de **443** é a porta SIP (Session Initiation Protocol) TCP (Transmission Control Protocol) configurada para clientes de conferência. Caso o valor padrão não tenha sido usado, atualize o valor **Porta externa de Webconferência Externa**.

Marque a caixa de seleção **Este pool de Borda é usado para conectividade de IM pública e de federação** se você planeja usar este Servidor de Borda para federação. Caso você tenha múltiplos Servidores de Borda implantados, apenas um deles será habilitado para federação. Caso você não marque essa caixa e decida mais tarde que você deseja habilitar federação, você deve executar o assistente para Mescla de Construtor de Topologia e também publicar sua topologia novamente. Para maiores detalhes, consulte [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).