---
title: Habilitar ou desabilitar descoberta de parceiros de federação
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Na ocasião em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se haveria suporte para a descoberta automática de domínios parceiros federados.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817421"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar a descoberta de parceiros de federação no Skype for Business Server

Na ocasião em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se haveria suporte para a descoberta automática de domínios parceiros federados. Use o procedimento deste tópico para alterar essa configuração.

> [!NOTE]  
> O procedimento a seguir assume que você já habilitou a federação para sua organização. Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar ou desabilitar a descoberta automática de domínios federados para a sua organização

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3.  Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e em **Configuração da Borda de Acesso**.

4.  Na página **Configuração da Borda de Acesso**, clique em **Global**, **Editar** e em **Exibir detalhes**.

5.  Em **Editar Configuração da Borda de Acesso**, sob **Habilitar comunicações com usuários federados**, selecione ou desmarque a opção **Habilitar descoberta de domínios de parceiros** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.

6.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários em sua implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado. Para obter detalhes, [consulte Habilitar ou desabilitar federação e conectividade de IM pública.](enable-or-disable-federation-and-public-im-connectivity.md) Para obter detalhes sobre como controlar o acesso a domínios federados específicos, consulte [Gerenciar domínios sip federados](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e gerenciar [provedores sip federados.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando a descoberta de parceiros de federação usando cmdlets do Windows PowerShell

A descoberta de parceiros de federação pode ser gerenciada usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar a descoberta de parceiros de federação

  - Para habilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Verdadeiro ($True). Observe que é necessário habilitar o roteamento DNS SRV para alterar o valor dessa propriedade.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Para desabilitar a descoberta de parceiros de federação

  - Para desabilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Falso ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

