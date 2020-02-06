---
title: Habilitar ou desabilitar acesso de usuário remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se você habilitar o acesso de usuários remotos para usuários remotos, os usuários remotos compatíveis se conectarem pela Internet e não precisarão se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.
ms.openlocfilehash: b562dbe7a849ca4266a45303008ff9081903658d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818372"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuários remotos no Skype for Business Server

Usuários remotos são usuários de sua organização que têm uma identidade persistente do Active Directory dentro da organização. Usuários remotos geralmente se conectam ao Skype for Business Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização. Os usuários remotos incluem funcionários que trabalham em casa ou em trânsito e outros trabalhadores remotos, como fornecedores confiáveis, que receberam credenciais da empresa. Se você habilitar o acesso de usuários remotos para usuários remotos, os usuários remotos compatíveis se conectarem pela Internet e não precisarão se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.

Para dar suporte ao acesso de usuário remoto, você deve habilitar o acesso de usuários remotos. Ao habilitar o acesso de usuário remoto, habilite-o para toda a sua organização. Se, mais tarde, você quiser impedir temporariamente ou permanentemente o acesso do usuário remoto, você pode desabilitá-lo para a sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários remotos para sua organização.


> [!NOTE]  
> Habilitar o acesso de usuários remotos especifica que os servidores que executam o serviço de borda de acesso dão suporte a comunicações com usuários remotos, mas os usuários remotos não podem participar de mensagens instantâneas (IM) nem conferências em sua organização até você também configurar ao mesmo tempo. menos uma política para gerenciar o uso de acesso de usuário remoto. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto. Para obter detalhes sobre a configuração de políticas para o uso de acesso de usuário remoto, consulte [Configurar políticas para controlar o acesso de usuários remotos no Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuários remotos para sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para sua organização, marque a caixa de seleção **habilitar acesso do usuário remoto** .
    
      - Para desabilitar o acesso de usuário remoto para sua organização, desmarque a caixa de seleção **habilitar acesso de usuário remoto** .

6.  Clique em **Confirmar**.

Para permitir que os usuários remotos entrem em seus servidores que executam o Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuários remotos. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários remotos no Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o acesso de usuário remoto usando cmdlets do Windows PowerShell

O acesso do usuário remoto pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server 2013 ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar o acesso de usuários remotos

  - Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Para desabilitar o acesso de usuários remotos

  - Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


