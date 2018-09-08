---
title: Configure a federação para um provedor de serviços de audioconferência em sua implantação híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Resumo: Saiba como configurar a federação para um provedor de serviços de audioconferência no Skype para Business Online.'
ms.openlocfilehash: 2c79799c6f68eba9af41cdadc8f0a16346b8a522
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885647"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Configure a federação para um provedor de serviços de audioconferência em sua implantação híbrida

**Resumo:** Saiba como configurar a federação para um provedor de serviços de audioconferência no Skype para Business Online.

Se você pretende usar um Provedor de Conferência de Áudio (ACP) em sua implantação híbrida (no local com online), será necessário configurar a federação entre sua implantação no local e o parceiro ACP como um Servidor Parceiro Permitido. É possível configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (também conhecido como Proxy de Acesso) à lista de Domínios de Federação para sua implantação no local. Seu parceiro ACP precisará adicionar o FQDN de seu pool de Servidor de Borda no local à lista de domínios de federação permitidos. Entre em contato com o provedor ACP para obter detalhes adicionais. Seu parceiro ACP precisará adicionar o FQDN de seu pool de Servidor de Borda no local à lista de domínios de federação permitidos.

- **Adição do domínio ACP e do servidor de borda como um domínio federado permitido**

    Para adicionar o domínio de ACP como um servidor de parceiro permitido (permitido domínio federado), siga as etapas em [Configurar suporte a domínios externos permitidos](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx). Para o servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP. Pode ser necessário entrar em contato com seu parceiro ACP para obter o FQDN do Servidor de Borda, que também pode ser mencionado pelo ACP como Proxy de Acesso.

- **Forneça o FQDN do seu pool do servidor de borda ao parceiro ACP**

    O parceiro ACP precisa configurar a federação para adicionar seu domínio no local como um Servidor Parceiro Permitido, adicionando o FQDN de seu pool de Servidor de Borda como um domínio de Federação permitido.


