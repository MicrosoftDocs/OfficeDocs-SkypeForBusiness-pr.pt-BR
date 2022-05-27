---
title: Habilitar ou desabilitar federação e conectividade de IM pública
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: O suporte para federação é necessário para permitir que os usuários que têm uma conta com um cliente confiável ou uma organização parceira, incluindo domínios de parceiros e usuários de usuários do provedor de mensagens instantâneas públicas que você dá suporte, colaborem com usuários em sua organização.
ms.openlocfilehash: 0b78eacd473422c204f8614464b406657f3dc92b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675743"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar ou desabilitar a federação e a conectividade de mensagens instantâneas públicas Skype for Business Server

O suporte para federação é necessário para permitir que os usuários que têm uma conta com um cliente confiável ou uma organização parceira, incluindo domínios de parceiros e usuários de usuários do provedor de mensagens instantâneas públicas que você dá suporte, colaborem com usuários em sua organização. A federação também é necessária para usar um provedor de serviços Exchange hospedado para fornecer caixa postal Enterprise Voice usuários cujas caixas de correio estão localizadas em um serviço Exchange hospedado, como Microsoft Exchange Online. Quando tiver estabelecido uma relação de confiança com esses domínios externos, você poderá autorizar os usuários nesses domínios a acessar sua implantação e participar de Skype for Business Server comunicações. Essa relação de confiança é chamada de federação e não está relacionada ou depende de uma relação de confiança do Active Directory.

Para dar suporte ao acesso de usuários de domínios federados, você deve habilitar a federação. Se você habilitar a federação para sua organização, também deverá especificar se deseja implementar as seguintes opções:

  - **Habilitar a descoberta de domínio de parceiro**   Se você habilitar essa opção, o Skype for Business Server usará registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações do administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes sobre como controlar o acesso por domínios federados, consulte [Configurar suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Enviar um aviso de isenção de responsabilidade de arquivamento para parceiros federados**    Aviso de isenção de responsabilidade é enviado a parceiros federados que o arquivamento em sua implantação está em vigor. Se você dá suporte ao arquivamento de comunicações externas com domínios de parceiros federados, habilite a notificação de isenção de responsabilidade de arquivamento para avisar os parceiros de que suas mensagens estão sendo arquivadas.

Se posteriormente você quiser impedir temporaria ou permanentemente o acesso por usuários de domínios federados, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso de usuário federado para sua organização, incluindo a especificação das opções de federação apropriadas para a sua organização.

> [!NOTE]  
> Habilitar a federação para sua organização especifica apenas que os servidores que executam o serviço do Access Edge dão suporte ao roteamento para domínios federados. Os usuários em domínios federados não podem participar de mensagens instantâneas ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte ao acesso de usuário federado. Os usuários de provedores de serviços de mensagens instantâneas públicas não poderão participar de mensagens instantâneas ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte à conectividade de mensagens instantâneas públicas. Skype for Business Server não pode usar um serviço Exchange hospedado para fornecer atendimento a chamadas, Outlook Voice Access (incluindo caixa postal) ou serviços de atendedor automático para usuários cujas caixas de correio estão localizadas em um serviço Exchange hospedado até que você configure uma política de caixa postal hospedada que fornece roteamento Informações. Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte [Gerenciar domínios federados SIP para sua organização](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Além disso, se você quiser dar suporte à comunicação com usuários de provedores de serviços de mensagens instantâneas, deverá configurar políticas para dar suporte a ela e também configurar o suporte para os provedores de serviços individuais aos quais deseja dar suporte. Para obter detalhes,   [consulte Gerenciar provedores federados SIP para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado para sua organização

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL Administração para abrir o Skype for Business Server Painel de Controle. 

3.  No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso de usuário federado para sua organização, marque a caixa de seleção Habilitar comunicações **com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado para sua organização, desmarque a caixa de seleção Habilitar comunicações **com usuários federados** .

6.  Se você selecionou **a caixa de seleção Habilitar comunicações com usuários federados** , faça o seguinte:
    
    1.  Se você quiser dar suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção **Habilitar descoberta de domínio de** parceiro.
    
    2.  Se sua organização der suporte ao arquivamento de comunicações externas, marque a caixa de seleção Enviar aviso de **isenção** de responsabilidade de arquivamento para parceiros federados.

7.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários em sua implantação do Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário federado. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuário federado](../external-access-policies/configure-policies-to-control-federated-user-access.md). Para controlar o acesso a domínios federados específicos, consulte [Configurar suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a federação e a conectividade de mensagens instantâneas públicas usando Windows PowerShell cmdlets

A federação e a conectividade de mensagens instantâneas públicas também podem ser gerenciadas usando Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration servidor. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a federação e a conectividade de mensagens instantâneas públicas

  - Para habilitar a federação e a conectividade de mensagens instantâneas públicas, defina o valor da propriedade **AllowFederatedUsers** como True ($True):<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a federação e a conectividade de mensagens instantâneas públicas

  - Para desabilitar a federação e a conectividade de mensagens instantâneas públicas, defina o valor da propriedade **AllowFederatedUsers** como False ($False):<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

