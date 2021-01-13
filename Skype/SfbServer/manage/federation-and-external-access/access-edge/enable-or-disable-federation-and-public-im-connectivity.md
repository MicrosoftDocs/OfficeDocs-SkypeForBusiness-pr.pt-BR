---
title: Habilitar ou desabilitar federação e conectividade de IM pública
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O suporte para federação é necessário para permitir que os usuários que possuem uma conta com um cliente confiável ou uma organização parceira, incluindo domínios de parceiros e usuários de provedores públicos de mensagens instantâneas (IM) que você suporta, colaborem com usuários em sua organização.
ms.openlocfilehash: 390b23a92f91d762c3703a36c063dde54dff1de1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817411"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar ou desabilitar a federação e a conectividade de IM pública no Skype for Business Server

O suporte para federação é necessário para permitir que os usuários que possuem uma conta com um cliente confiável ou uma organização parceira, incluindo domínios de parceiros e usuários de provedores públicos de mensagens instantâneas (IM) que você suporta, colaborem com usuários em sua organização. A federação também é necessária para usar um provedor de serviços do Exchange hospedado para fornecer caixa postal aos usuários do Enterprise Voice cujas caixas de correio estão localizadas em um serviço hospedado do Exchange, como o Microsoft Exchange Online. Quando você tiver estabelecido uma relação de confiança com esses domínios externos, poderá autorizar os usuários nesses domínios a acessar sua implantação e participar das comunicações do Skype for Business Server. Essa relação de confiança é chamada de federação e não está relacionada ou depende de uma relação de confiança do Active Directory.

Para suportar o acesso de usuários de domínios federados, você deve habilitar a federação. Se você habilitar a federação para sua organização, também deverá especificar se implementará as seguintes opções:

  - **Habilitar a descoberta de domínio do parceiro**   Se você habilitar essa opção, o Skype for Business Server usará registros DNS (Sistema de Nomes de Domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, quantidade de tráfego e configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes sobre como controlar o acesso por domínios federados, consulte [Configurar o suporte para domínios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)

  - **Enviar um aviso de isenção de responsabilidade de arquivamento a parceiros federados**    Aviso de isenção de responsabilidade é enviado aos parceiros federados de que o arquivamento em sua implantação está em uso. Se você suportar o arquivamento de comunicações externas com domínios de parceiros federados, habilita a notificação de aviso de isenção de responsabilidade de arquivamento para avisar os parceiros de que suas mensagens estão sendo arquivadas.

Se posteriormente você quiser impedir temporariamente ou permanentemente o acesso de usuários de domínios federados, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso de usuário federado para sua organização, incluindo a especificação das opções de federação apropriadas a serem suportadas para sua organização.

> [!NOTE]  
> A habilitação da federação para sua organização apenas especifica que os servidores que executam o serviço de Borda de Acesso suportam o roteamento para domínios federados. Os usuários em domínios federados não podem participar de IMs ou conferências em sua organização até que você também configure pelo menos uma política para suportar o acesso de usuário federado. Os usuários de provedores de serviços públicos de IM não podem participar de IMs ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte à conectividade a IM pública. O Skype for Business Server não pode usar um serviço hospedado do Exchange para fornecer atendimento de chamadas, Outlook Voice Access (incluindo caixa postal) ou serviços de atendedores automáticos para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado até que você configure uma política de caixa postal hospedada que forneça informações de roteamento. Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte [Gerenciar domínios SIP federados para sua organização.](../sip-domains/manage-sip-federated-domains-for-your-organization.md) Além disso, se você quiser dar suporte à comunicação com usuários de provedores de serviços de IM, configure políticas para dar suporte a ele e também configure o suporte para os provedores de serviços individuais aos quais deseja dar suporte. Para obter detalhes, [consulte Gerenciar provedores SIP federados para sua organização.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado para sua organização

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso de usuário federado para sua organização, marque a caixa de seleção Habilitar **comunicações com usuários federados.**
    
      - Para desabilitar o acesso de usuário federado para sua organização, des limpe a caixa de seleção Habilitar comunicações **com usuários federados.**

6.  Se você **selecionou a caixa de seleção Habilitar comunicações** com usuários federados, faça o seguinte:
    
    1.  Se você quiser dar suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção Habilitar descoberta **de domínio** do parceiro.
    
    2.  Se sua organização oferece suporte ao arquivamento de comunicações externas, marque a caixa de seleção Enviar aviso de isenção de responsabilidade de arquivamento para parceiros **federados.**

7.  Clique em **Confirmar**.

Para permitir que os usuários federados colaborem com usuários em sua implantação do Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário federado. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário federado.](../external-access-policies/configure-policies-to-control-federated-user-access.md) Para controlar o acesso a domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando a federação e a conectividade a redes públicas de IM usando cmdlets do Windows PowerShell

A federação e a conectividade de IM pública também podem ser gerenciadas usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a federação e a conectividade pública de IM

  - Para habilitar a federação e a conectividade de IM pública, de definida o valor da **propriedade AllowFederatedUsers** como True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a federação e a conectividade pública de IM

  - Para desabilitar a federação e a conectividade pública de IM, de definida o valor da **propriedade AllowFederatedUsers** como False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

