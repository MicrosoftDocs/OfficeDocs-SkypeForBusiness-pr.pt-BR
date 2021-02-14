---
title: Configurar federação para um provedor de serviços de audioconferência em sua implantação híbrida
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
description: 'Resumo: saiba como configurar a federação para um provedor de serviços de audioconferência no Skype for Business Online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726881"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar federação para um provedor de serviços de audioconferência em sua implantação híbrida

**Resumo:** Saiba como configurar a federação para um provedor de serviços de audioconferência no Skype for Business Online.

Se você quiser usar um Provedor de Audioconferência (ACP) em sua implantação híbrida (local com online), será necessário configurar a federação entre sua implantação local e o parceiro ACP como um Servidor parceiro permitido. Você pode configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (isso também pode ser chamado de Proxy de Acesso) à lista de Domínios Federados para sua implantação local. Seu parceiro ACP precisa adicionar o FQDN do pool do Servidor de Borda local à lista de domínios federados permitidos. Entre em contato com seu provedor ACP para obter detalhes adicionais. Seu parceiro ACP precisa adicionar o FQDN do pool do Servidor de Borda local à lista de domínios federados permitidos.

- **Adicionando o domínio ACP e o servidor de borda como um domínio federado permitido**

    Para adicionar o domínio ACP como um Servidor parceiro permitido (domínio federado permitido), siga as etapas em Configurar Suporte [para Domínios Externos Permitidos.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx) Para o Servidor de Borda, adicione o FQDN do Servidor de Borda do parceiro ACP. Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN do Servidor de Borda, que também pode ser chamado pelo seu ACP como Proxy de Acesso.

- **Fornecendo o FQDN do seu Pool de Servidores de Borda para o parceiro ACP**

    O parceiro ACP precisa configurar a federação para adicionar seu domínio local como um Servidor parceiro permitido adicionando o FQDN do seu pool de Servidores de Borda como um domínio federado permitido.


