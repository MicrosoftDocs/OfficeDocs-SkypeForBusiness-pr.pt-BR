---
title: Configurar uma Exchange híbrida
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Saiba como configurar uma organização Exchange híbrida para uso com Microsoft Teams para garantir que as associações de grupo sejam sincronizadas.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4a0480ff8a795addb9ae322478fddb69e9aeceeed14ebca83f27cac34b01bfbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284471"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
======================================================================

No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams. No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online. Isso envolve a habilitação da funcionalidade de Writeback de Grupo no Azure AD Conexão juntamente com vários [scripts](/exchange/hybrid-deployment/set-up-microsoft-365-groups)de inicialização: Configure Microsoft 365 Groups com o Exchange híbrido .