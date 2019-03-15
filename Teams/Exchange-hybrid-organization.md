---
title: Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4dfc6b476498fef4484718a90f9c242a565cd64
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568556"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
======================================================================

No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams. No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online. Isso envolve a habilitação da funcionalidade de write-back de grupo no Azure Connect AD, juntamente com diversos scripts de inicialização: [Configurar o Office 365 grupos com Exchange híbrido local](https://go.microsoft.com/fwlink/?linkid=854389).
