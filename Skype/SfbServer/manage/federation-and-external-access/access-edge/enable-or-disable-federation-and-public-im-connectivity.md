---
title: Habilitar ou desabilitar federação e conectividade de IM pública
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O suporte para Federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização de parceiro confiável, incluindo domínios de parceiros e usuários de provedores de serviços de mensagens instantâneas (IM) que você dá suporte a colaborar com os usuários em seu porte.
ms.openlocfilehash: 86cc3e66b2e3252b6b25ff4bef09d3abeb4badf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280240"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação no Skype for Business Server

O suporte para Federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização de parceiro confiável, incluindo domínios de parceiros e usuários de provedores de serviços de mensagens instantâneas (IM) que você dá suporte a colaborar com os usuários em seu porte. A Federação também é necessária para usar um provedor de serviços do Exchange hospedado para fornecer correio de voz para usuários do Enterprise Voice cujas caixas de correio estão localizadas em um serviço hospedado do Exchange, como o Microsoft Exchange Online. Quando tiver estabelecido uma relação de confiança com esses domínios externos, você poderá autorizar os usuários desses domínios a acessarem sua implantação e participar das comunicações do Skype for Business Server. Essa relação de confiança é chamada de Federação e não é relacionada à relação de confiança do Active Directory, ou depende dela.

Para dar suporte ao acesso por usuários de domínios federados, você deve habilitar a Federação. Se você habilitar a Federação para sua organização, também deverá especificar se deseja implementar as seguintes opções:

  - **Habilitar a descoberta**   de domínio de parceiro se você habilitar essa opção, o Skype for Business Server usará os registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de descoberto parceiros federados e limitando ou bloqueando o tráfego de acordo com o nível de confiança, a quantidade de tráfego e as configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para os usuários nos domínios que você incluir na lista de domínios permitidos. Independentemente de você selecionar essa opção, você pode especificar que domínios individuais sejam bloqueados ou permitidos, incluindo a restrição de acesso a servidores específicos que executam o serviço de borda de acesso no domínio federado. Para obter detalhes sobre o controle do acesso a domínios federados, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Enviar uma isenção de responsabilidade de arquivamento a**     um aviso de isenção de responsabilidade de parcerias federadas é enviada para parceiros federados que o arquivamento em sua implantação está em vigor. Se você oferecer suporte ao arquivamento de comunicações externas com domínios de parceiros federados, habilite a notificação de exclusão de isenção de arquivo para avisar os parceiros de que suas mensagens estão sendo arquivadas.

Se, mais tarde, você quiser impedir o acesso temporário ou permanente por usuários de domínios federados, poderá desabilitar a Federação para a sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário federado à sua organização, incluindo a especificação das opções de Federação adequadas para ter suporte para sua organização.

> [!NOTE]  
> Habilitar a Federação para a sua organização especifica apenas que os servidores que executam o serviço de borda de acesso dão suporte a roteamento para domínios federados. Os usuários em domínios federados não podem participar de mensagens instantâneas nem conferências em sua organização até você também configurar pelo menos uma política para dar suporte ao acesso de usuários federados. Os usuários de provedores de serviços públicos de mensagens instantâneas não podem participar de mensagens instantâneas nem conferências em sua organização até você também configurar pelo menos uma política para dar suporte à conectividade de mensagens de chat públicas. O Skype for Business Server não pode usar um serviço hospedado do Exchange para fornecer atendimento de chamada, Outlook Voice Access (incluindo caixa postal) ou serviços de atendedor automático para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado até você configurar uma voz hospedada política de email que fornece informações de roteamento. Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte [gerenciar domínios federados SIP para sua organização](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Além disso, se quiser dar suporte à comunicação com usuários de provedores de serviços de mensagens instantâneas, você deve configurar políticas para dar suporte a ele e também configurar o suporte para provedores de serviços individuais aos quais você deseja dar suporte. Para obter detalhes, consulte [gerenciar provedores federados SIP para a sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado à sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**e, em seguida, clique em **configuração de borda de acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário federado à sua organização, marque a caixa de seleção **habilitar comunicações com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado à sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .

6.  Se você tiver marcado a caixa de seleção **habilitar comunicações com usuários federados** , faça o seguinte:
    
    1.  Se você quiser dar suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção **habilitar descoberta de domínio de parceiro** .
    
    2.  Se a sua organização oferecer suporte para o arquivamento de comunicações externas, marque a caixa de seleção Enviar isenção de arquivo **para parceiros federados** .

7.  Clique em **Confirmar**.

Para habilitar os usuários federados a colaborar com os usuários na implantação do Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados](../external-access-policies/configure-policies-to-control-federated-user-access.md). Para controlar o acesso a domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a conectividade de mensagens de chat pública e de Federação usando cmdlets do Windows PowerShell

A Federação e a conectividade de mensagens de chat públicas também podem ser gerenciadas usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a conectividade de mensagens de chat pública e de Federação

  - Para habilitar a conectividade de mensagens de chat pública e de Federação, defina o valor da propriedade **AllowFederatedUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a conectividade de mensagens de chat pública e de Federação

  - Para desabilitar a conectividade de mensagens de chat pública e de Federação, defina o valor da propriedade **AllowFederatedUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

