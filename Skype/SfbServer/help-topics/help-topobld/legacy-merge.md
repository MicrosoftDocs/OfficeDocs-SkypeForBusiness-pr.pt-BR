---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: O FQDN externo de Webconferência permite que usuários externos ingressem em reuniões locais. Digite o FQDN (nome de domínio totalmente qualificado) da interface externa de Webconferência do Servidor de Borda herdado.
ms.openlocfilehash: 2541de3efa0a1585699edcb11ae5187dbe9c425b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395463"
---
# <a name="legacy-merge"></a>Mesclagem Herdada

O **FQDN externo de Webconferência** permite que usuários externos ingressem em reuniões locais. Digite o FQDN (nome de domínio totalmente qualificado) da interface externa de Webconferência do Servidor de Borda herdado.

O valor de **Porta externa de Webconferência Externa** de **443** é a porta SIP (Session Initiation Protocol) TCP (Transmission Control Protocol) configurada para clientes de conferência. Caso o valor padrão não tenha sido usado, atualize o valor **Porta externa de Webconferência Externa**.

Marque a caixa de seleção **Este pool de Borda é usado para conectividade de IM pública e de federação** se você planeja usar este Servidor de Borda para federação. Caso você tenha múltiplos Servidores de Borda implantados, apenas um deles será habilitado para federação. Caso você não marque essa caixa e decida mais tarde que você deseja habilitar federação, você deve executar o assistente para Mescla de Construtor de Topologia e também publicar sua topologia novamente. Para maiores detalhes, consulte [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).