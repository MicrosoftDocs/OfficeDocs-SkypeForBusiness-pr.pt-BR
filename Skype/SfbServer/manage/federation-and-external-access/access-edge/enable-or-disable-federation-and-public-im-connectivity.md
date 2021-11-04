---
title: Habilitar ou desabilitar federação e conectividade de IM pública
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: O suporte para federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização parceira confiável, incluindo domínios de parceiros e usuários de provedores de mensagens instantâneas públicas (IM) que você suporta, colaborem com usuários em sua organização.
ms.openlocfilehash: 7c87ad567bef1b073dae80e8bc669d6f0d52e3a6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765469"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar ou desabilitar a conectividade de IM pública e federação Skype for Business Server

O suporte para federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização parceira confiável, incluindo domínios de parceiros e usuários de provedores de mensagens instantâneas públicas (IM) que você suporta, colaborem com usuários em sua organização. A federação também é necessária para usar um provedor de serviços Exchange hospedado para fornecer caixa postal Enterprise Voice usuários cujas caixas de correio estão localizadas em um serviço Exchange hospedado, como Microsoft Exchange Online. Quando você tiver estabelecido uma relação de confiança com esses domínios externos, poderá autorizar os usuários nesses domínios a acessar sua implantação e participar de Skype for Business Server comunicações. Essa relação de confiança é chamada de federação e não está relacionada ou dependente de uma relação de confiança do Active Directory.

Para dar suporte ao acesso de usuários de domínios federados, você deve habilitar a federação. Se você habilitar a federação para sua organização, também deverá especificar se deve implementar as seguintes opções:

  - **Habilitar a descoberta de domínio do parceiro**   Se você habilitar essa opção, o Skype for Business Server usa registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes sobre como controlar o acesso por domínios federados, consulte [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Enviar um aviso de isenção de responsabilidade de arquivamento para parceiros federados**    Aviso de isenção de responsabilidade é enviado a parceiros federados que o arquivamento em sua implantação está em uso. Se você suportar o arquivamento de comunicações externas com domínios de parceiros federados, habilita a notificação de isenção de responsabilidade de arquivamento para avisar os parceiros de que suas mensagens estão sendo arquivadas.

Se você quiser impedir temporariamente ou permanentemente o acesso por usuários de domínios federados, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso de usuário federado para sua organização, incluindo a especificação das opções de federação apropriadas a serem suportadas para sua organização.

> [!NOTE]  
> A habilitação da federação para sua organização especifica apenas que seus servidores executando o roteamento de suporte do serviço de Borda de Acesso para domínios federados. Os usuários em domínios federados não podem participar de IMs ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte ao acesso de usuário federado. Os usuários de provedores de serviços públicos de IM não podem participar de IMs ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte à conectividade de IM pública. Skype for Business Server não pode usar um serviço de Exchange hospedado para fornecer atendimento de chamadas, acesso de voz do Outlook (incluindo caixa postal) ou serviços de atendimento automático para usuários cujas caixas de correio estão localizadas em um serviço Exchange hospedado até configurar uma política de caixa postal hospedada que forneça informações de roteamento. Para obter detalhes sobre como configurar políticas de comunicação com usuários de domínios federados em outras organizações, consulte [Manage SIP federated domains for your organization](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Além disso, se você deseja dar suporte à comunicação com usuários de provedores de serviços de IM, configure políticas para dar suporte a ela e também configure o suporte para os provedores de serviços individuais que deseja dar suporte. Para obter detalhes,   [consulte Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado para sua organização

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso de usuário federado para sua organização, marque a caixa de seleção Habilitar comunicações **com usuários federados.**
    
      - Para desabilitar o acesso de usuário federado para sua organização, desembaixe a caixa de seleção Habilitar comunicações **com usuários federados.**

6.  Se você selecionou **a caixa de seleção Habilitar comunicações** com usuários federados, faça o seguinte:
    
    1.  Se quiser dar suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção **Habilitar** descoberta de domínio do parceiro.
    
    2.  Se sua organização oferece suporte ao arquivamento de comunicações externas, marque a caixa de seleção Enviar aviso de **isenção** de responsabilidade de arquivamento para parceiros federados.

7.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários em sua implantação Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário federado. Para obter detalhes, consulte [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md). Para controlar o acesso a domínios federados específicos, consulte [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando a federação e a conectividade de IM pública usando Windows PowerShell cmdlets

A conectividade de IM pública e federação também pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a federação e a conectividade de IM pública

  - Para habilitar a conectividade de IM pública e federação, de definir o valor da **propriedade AllowFederatedUsers** como True ($True):<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a federação e a conectividade de IM pública

  - Para desabilitar a federação e a conectividade de IM pública, de definir o valor da **propriedade AllowFederatedUsers** como False ($False):<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

