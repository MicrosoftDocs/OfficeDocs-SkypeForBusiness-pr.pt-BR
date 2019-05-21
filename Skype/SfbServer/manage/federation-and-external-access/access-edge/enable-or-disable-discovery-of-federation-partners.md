---
title: Habilitar ou desabilitar descoberta de parceiros de federação
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No momento em que você implantou seus servidores de borda e habilitou a Federação para a sua organização, você deve especificar se deseja dar suporte à descoberta automática de domínios de parceiro federado.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280254"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar a descoberta de parceiros de Federação no Skype for Business Server

No momento em que você implantou seus servidores de borda e habilitou a Federação para a sua organização, você deve especificar se deseja dar suporte à descoberta automática de domínios de parceiro federado. Use o procedimento deste tópico para alterar essa configuração.

> [!NOTE]  
> O procedimento a seguir pressupõe que você já habilitou a Federação para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte [habilitar ou desabilitar o acesso de usuários remotos](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar ou desabilitar a descoberta automática de domínios federados para a sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**, clique em **configuração de borda de acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, em **habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **habilitar descoberta de domínio parceiro** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.

6.  Clique em **Confirmar**.

Para permitir que os usuários federados colaborem com usuários na implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados. Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação](enable-or-disable-federation-and-public-im-connectivity.md). Para obter detalhes sobre o controle do acesso a domínios federados específicos, consulte [gerenciar domínios federados SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [gerenciar provedores federados SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a descoberta de parceiros de Federação usando cmdlets do Windows PowerShell

A descoberta de parceiros de Federação pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar a descoberta de parceiros de Federação

  - Para habilitar a descoberta de parceiros de Federação, defina o valor da propriedade **EnablePartnerDiscovery** como True ($true). Observe que você deve habilitar o roteamento de SRV DNS para alterar esse valor de propriedade.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Para desabilitar a descoberta de parceiros de Federação

  - Para desabilitar a descoberta de parceiros de Federação, defina o valor da propriedade **EnablePartnerDiscovery** como False ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

