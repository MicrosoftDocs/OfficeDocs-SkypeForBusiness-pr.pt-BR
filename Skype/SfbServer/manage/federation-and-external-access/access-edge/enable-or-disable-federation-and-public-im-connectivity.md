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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Suporte para federação é necessária para permitir que os usuários que têm uma conta com uma organização do cliente ou parceiro confiável, incluindo domínios de parceiros e os usuários de públicos de mensagens instantâneas de usuários do provedor de (IM) que recebe suporte, para colaborar com usuários em sua organização.
ms.openlocfilehash: d82833dcd4e477e2c332c01d3d4ba2fdca5123aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896415"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Habilitar ou desabilitar a federação e conectividade de IM pública no Skype para Business Server

Suporte para federação é necessária para permitir que os usuários que têm uma conta com uma organização do cliente ou parceiro confiável, incluindo domínios de parceiros e os usuários de públicos de mensagens instantâneas de usuários do provedor de (IM) que recebe suporte, para colaborar com usuários em sua organização. Federação também é necessário usar um provedor de serviço do Exchange hospedado para oferecer caixa postal para usuários do Enterprise Voice cujas caixas postais estão localizadas em um serviço do Exchange hospedado como o Microsoft Exchange Online. Depois de estabelecer uma relação de confiança com esses domínios externos, você pode autorizar usuários nesses domínios para acessar sua implantação e participar Skype para comunicação entre servidores de negócios. Essa relação de confiança é chamada uma federação e não está relacionado, ou dependentes, uma relação de confiança do Active Directory.

Para suportar o acesso por usuários de domínios federados, você deve habilitar a federação. Se você habilitar a federação para sua organização, você também deve especificar se deseja implementar as seguintes opções:

  - **Habilitar a descoberta de domínio de parceiro**   se você habilitar essa opção, Skype para Business Server usa os registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de descobertas federados parceiros e limitando ou bloqueando esse tráfego com base no nível de confiança, quantidade de tráfego e as configurações do administrador. Se você não selecionar essa opção, o acesso de usuário federado é habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Se ou não você seleciona essa opção, você pode especificar esse indivíduo domínios ser bloqueada ou permitida, incluindo restringir o acesso aos servidores específicos que executem o serviço de borda de acesso no domínio federado. Para obter detalhes sobre como controlar o acesso por domínios federados, consulte [Configure suporte a domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Enviar um aviso de isenção de arquivamento para parceiros federados**     aviso de isenção de responsabilidade é enviado para parceiros federados e arquivamento em sua implantação está em vigor. Caso você ofereça suporte a arquivamento das comunicações externas com domínios de parceiro federado, você deve habilitar a notificação de isenção de responsabilidade de arquivamento avisar aos parceiros que suas mensagens estão sendo arquivadas.

Se você quiser mais tarde temporária ou permanentemente impedir o acesso pelos usuários de domínios federados, é possível desabilitar a federação para sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário federado para sua organização, inclusive especificando as opções de Federação apropriado para ser suportados pela sua organização.

> [!NOTE]  
> Habilitando a federação para sua organização somente Especifica que os servidores que executam o serviço de borda de acesso compatível com o roteamento para domínios federados. Usuários em domínios federados não podem participar de mensagens Instantâneas ou conferências em sua organização, até que você também configurar pelo menos uma política para suportar o acesso de usuário federado. Usuários de provedores de serviços IM públicos não podem participar de mensagens Instantâneas ou conferências em sua organização, até que você também configurar pelo menos uma diretiva para oferecer suporte à conectividade pública de IM. Skype para Business Server não é possível usar um serviço hospedado do Exchange para fornecer atendimento, Outlook Voice Access (incluindo caixa postal), de chamada ou serviços de atendedor automático para usuários cujas caixas de correio estão localizadas em um serviço hospedado do Exchange até que você configure uma voz hospedada política de correio que fornece informações de roteamento. Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte [Gerenciar SIP federated domínios para sua organização](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Além disso, se você quiser suportar a comunicação com usuários de provedores de serviço de mensagens Instantâneas, você deve configurar políticas para oferecer suporte a ele e também configurar o suporte para os provedores de serviço individuais que você deseja suportar. Para obter detalhes, consulte [Gerenciar SIP federated providers para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado para sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Configuração de borda de acesso**.

4.  Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, execute um destes procedimentos:
    
      - Para habilitar o acesso de usuário federado para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários federados** .

6.  Se você marcou a caixa de seleção **Habilitar comunicações com usuários federados** , faça o seguinte:
    
    1.  Se você quiser suportar a descoberta automática de domínios de parceiros, marque a caixa de seleção **Habilitar a descoberta de domínio de parceiro** .
    
    2.  Se sua organização suporta o arquivamento das comunicações externas, marque a caixa de seleção **Enviar aviso de isenção para parceiros federados de arquivamento** .

7.  Clique em **Confirmar**.

Para habilitar os usuários federados colaborar com usuários em sua Skype para implantação Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário federado. Para obter detalhes, consulte [Configure políticas para controlar federados acesso de usuário](../external-access-policies/configure-policies-to-control-federated-user-access.md). Para controlar o acesso de domínios federados específicos, consulte [Configure suporte a domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a federação e conectividade IM pública usando cmdlets do Windows PowerShell

Federação e conectividade IM pública também podem ser gerenciadas usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a federação e conectividade IM pública

  - Para habilitar a federação e conectividade IM pública, defina o valor da propriedade **AllowFederatedUsers** como True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a federação e conectividade IM pública

  - Para desabilitar a federação e conectividade IM pública, defina o valor da propriedade **AllowFederatedUsers** como falsa ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

