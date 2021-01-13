---
title: Habilitar ou desabilitar acesso de usuário remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos suportados se conectam pela Internet e não têm que se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817391"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuário remoto no Skype for Business Server

Usuários remotos são usuários em suas organizações com uma identidade do Active Directory persistente dentro da organização. Os usuários remotos frequentemente fazem login no Skype for Business Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização. Os usuários remotos incluem funcionários trabalhando em casa ou na estrada e outros trabalhadores remotos, como vendedores confiáveis, que foram concedidos com credenciais empresariais. Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos suportados se conectam pela Internet e não têm que se conectar usando uma VPN para colaborar com usuários internos usando o Skype for Business Server.

Para suportar acesso de usuário remoto, você deve habilitar o acesso de usuário remoto. Ao habilitar o acesso de usuário remoto, você o habilita para toda sua organização. Se posteriormente você quiser impedir temporariamente ou permanentemente o acesso dos domínios federados pelos usuários, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso do usuário federado para sua organização.


> [!NOTE]  
> Habilitar o acesso de usuário remoto apenas especifica que seus servidores executando as comunicações de suporte do serviço de Borda de Acesso com usuário remotos, mas os usuários remotos não podem participar de mensagem instantânea (IM) ou conferências em sua organização até que você também configure pelo menos uma política para gerenciar o uso do acesso de usuário remoto. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto. Para obter detalhes sobre como configurar políticas para o uso do acesso de usuário remoto, consulte Configurar políticas para controlar o acesso de usuário remoto [no Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso do usuário federado na sua organização

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso ao usuário remoto para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários federados**.
    
      - Para desabilitar o acesso ao usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.

6.  Clique em **Confirmar**.

Para permitir que os usuários remotos se inscrevam em seus servidores que executam o Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário remoto. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário remoto no Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o acesso de usuário remoto usando cmdlets do Windows PowerShell

O acesso de usuário remoto pode ser gerenciado usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet. Este cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server 2013 ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar o acesso de usuário remoto

  - Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Para desabilitar o acesso de usuário remoto

  - Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


