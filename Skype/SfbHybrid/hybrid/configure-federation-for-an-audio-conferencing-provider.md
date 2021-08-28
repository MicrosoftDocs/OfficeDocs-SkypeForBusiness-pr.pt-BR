---
title: Configurar federação para um provedor de audioconferência em sua implantação híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como configurar a federação para um provedor de audioconferência no Skype for Business Online.'
ms.openlocfilehash: 25bd691186d5d37dc272b420e68bb71a7d181de1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597885"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configurar federação para um provedor de audioconferência em sua implantação híbrida

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**Resumo:** Saiba como configurar a federação para um provedor de audioconferência no Skype for Business Online.

Se você quiser usar um Provedor de Audioconferência (ACP) em sua implantação híbrida (local com online), você precisará configurar a federação entre sua implantação local e o parceiro ACP como um Servidor parceiro permitido. Você pode configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (isso também pode ser chamado de Proxy de Acesso) à lista Domínios Federados para sua implantação local. Em seguida, seu parceiro ACP precisa adicionar o FQDN do pool de Servidor de Borda local à lista de domínios federados permitidos. Entre em contato com seu provedor ACP para obter detalhes adicionais. Em seguida, seu parceiro ACP precisa adicionar o FQDN do pool de Servidor de Borda local à lista de domínios federados permitidos.

- **Adicionando o Domínio ACP e o Servidor de Borda como um Domínio Federado Permitido**

    Para adicionar o domínio ACP como um Servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains). Para o Servidor de Borda, adicione o FQDN do Servidor de Borda do parceiro ACP. Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN para seu Servidor de Borda, que também pode ser chamado pelo seu ACP como Proxy de Acesso.

- **Fornecendo o FQDN do pool de servidores de borda para o parceiro ACP**

    O parceiro ACP precisa configurar a federação para adicionar seu domínio local como um Servidor parceiro permitido adicionando o FQDN do pool do Servidor de Borda como um domínio federado permitido.