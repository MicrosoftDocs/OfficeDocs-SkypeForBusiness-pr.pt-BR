---
title: Configurar uma organização híbrida do Exchange
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Saiba como configurar uma organização híbrida do Exchange para uso com o Microsoft Teams para garantir que as associações de grupo sejam sincronizadas.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551957"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar uma organização híbrida do Exchange para uso com o Microsoft Teams
======================================================================

No geral, você não precisa configurar nenhuma funcionalidade do Exchange Online para uso com o Microsoft Teams. No entanto, em cenários do Exchange Hybrid, há etapas necessárias para garantir que as assinaturas do Group estejam sincronizadas com o Exchange Server (local) e com o Exchange Online. Isso envolve a habilitação da funcionalidade de write-back do grupo no Azure AD Connect juntamente com vários scripts de inicialização: [configurar os grupos do Microsoft 365 com o Exchange híbrido local](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups).
