---
title: Configurar a Federação para um provedor de audioconferência em sua implantação híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como configurar a Federação para um provedor de conferência de áudio no Skype for Business online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726881"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar a Federação para um provedor de audioconferência em sua implantação híbrida

**Resumo:** Saiba como configurar a Federação para um provedor de conferência de áudio no Skype for Business online.

Se quiser usar um provedor de serviços de audioconferência (ACP) em sua implantação híbrida (local com online), você precisará configurar a Federação entre sua implantação local e o parceiro ACP como um servidor parceiro permitido. Você pode configurar a Federação adicionando o domínio de parceiro ACP e o servidor de borda (isso também pode ser chamado de proxy de acesso) à lista de domínios federados para sua implantação local. O parceiro ACP precisará adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos. Entre em contato com seu provedor ACP para obter mais detalhes. O parceiro ACP precisará adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.

- **Adicionar o domínio ACP e o servidor de borda como um domínio federado permitido**

    Para adicionar o domínio ACP como um servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configurar suporte para domínios externos permitidos](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Para o servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP. Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN do servidor de borda, que também pode ser mencionado pelo ACP como proxy de acesso.

- **Fornecer o FQDN do pool do servidor de borda ao parceiro ACP**

    O parceiro ACP precisa configurar a Federação para adicionar seu domínio local como um servidor parceiro permitido adicionando o FQDN do seu pool de servidor de borda como um domínio federado permitido.


