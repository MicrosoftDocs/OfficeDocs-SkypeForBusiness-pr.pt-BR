---
title: Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd18381a8d889a1cebad04234e56bf11def9197e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563891"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
======================================================================

No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams. No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online. Isso envolve a habilitação da funcionalidade de write-back do grupo no Azure AD Connect juntamente com vários scripts de inicialização: [configurar grupos do Office 365 com híbrido Exchange local](https://go.microsoft.com/fwlink/?linkid=854389).
