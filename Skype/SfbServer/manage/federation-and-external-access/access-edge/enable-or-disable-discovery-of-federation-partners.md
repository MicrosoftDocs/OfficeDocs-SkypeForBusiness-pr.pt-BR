---
title: Habilitar ou desabilitar descoberta de parceiros de federação
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No momento você implantado servidores de borda e habilitado a federação para sua organização, você deve especificou se deseja suportar a descoberta automática de domínios de parceiro federado.
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199938"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar a descoberta de parceiros de federação no Skype para Business Server

No momento você implantado servidores de borda e habilitado a federação para sua organização, você deve especificou se deseja suportar a descoberta automática de domínios de parceiro federado. Use o procedimento neste tópico para alterar essa configuração.

> [!NOTE]  
> O procedimento a seguir pressupõe que você já tiver habilitado a federação para sua organização. Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar ou desabilitar a descoberta automática de domínios federados para sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**, clique em **Configuração de borda de acesso**.

4.  Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, sob **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Habilitar a descoberta de domínio do parceiro** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.

6.  Clique em **Confirmar**.

Para habilitar os usuários federados colaborar com usuários em sua Skype para implantação Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado. Para obter detalhes, consulte [Habilitar ou desabilitar a federação e conectividade IM pública](enable-or-disable-federation-and-public-im-connectivity.md). Para obter detalhes sobre como controlar o acesso de domínios federados específicos, consulte [Gerenciar SIP domínios federados](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [provedores federados de SIP de gerenciar](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a descoberta de parceiros de Federação usando os cmdlets do Windows PowerShell

Descoberta de parceiros de Federação pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar a descoberta de parceiros de Federação

  - Para habilitar a descoberta de parceiros federados, defina o valor da propriedade **EnablePartnerDiscovery** como True ($True). Observe que você deve habilitar o roteamento para alterar esse valor de propriedade de SRV de DNS.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Para desabilitar a descoberta de parceiros de Federação

  - Para desabilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como falso ($False):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

