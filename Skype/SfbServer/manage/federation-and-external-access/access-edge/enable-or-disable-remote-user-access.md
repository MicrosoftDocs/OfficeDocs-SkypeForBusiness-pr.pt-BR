---
title: Habilitar ou desabilitar acesso de usuário remoto
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se você habilitar o acesso de usuário remoto para usuários remotos, usuários remotos com suporte se conectar à Internet e não precisará conectar usando uma VPN para colaborar com usuários internos usando Skype para o servidor de negócios.
ms.openlocfilehash: 34733c4d1912461090ef868e24ae24dc1c870a94
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222874"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuário remoto no Skype para Business Server

Usuários remotos são usuários em sua organização que têm uma identidade persistente do Active Directory dentro da organização. Usuários remotos com frequência entram Skype para Business Server de fora da rede usando uma rede virtual privada (VPN) quando não estiverem conectados à rede da sua organização. Usuários remotos incluem funcionários que trabalham em casa ou em trânsito e outros trabalhadores remotos, como fornecedores confiáveis, aos quais foram concedidas credenciais da empresa. Se você habilitar o acesso de usuário remoto para usuários remotos, usuários remotos com suporte se conectar à Internet e não precisará conectar usando uma VPN para colaborar com usuários internos usando Skype para o servidor de negócios.

Para suportar o acesso de usuário remoto, você deve habilitar o acesso de usuário remoto. Quando você habilita o acesso de usuário remoto, você pode habilitá-lo para toda sua organização. Se você quiser mais tarde temporária ou permanentemente impedir o acesso de usuário remoto, você pode desabilitá-lo para sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário remoto para sua organização.


> [!NOTE]  
> Permitindo o acesso de usuário remoto especifica apenas que os servidores que executam o serviço de borda de acesso suportam a comunicações com usuários remotos, mas usuários remotos não podem participar de conferências em sua organização ou de mensagens instantâneas (IM) até que você também configurar no pelo menos uma política para gerenciar o uso de acesso de usuário remoto. Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro. Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto. Para obter detalhes sobre como configurar políticas para o uso de acesso de usuário remoto, consulte [Configure políticas para controlar o acesso de usuário remoto no Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário remoto para sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, execute um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para sua organização, marque a caixa de seleção **Habilitar acesso de usuário remoto** .
    
      - Para desabilitar o acesso de usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar acesso de usuário remoto** .

6.  Clique em **Confirmar**.

Para permitir que usuários remotos entrar em seus servidores executando o Skype para Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário remoto. Para obter detalhes, consulte [Configure políticas para controlar o acesso de usuário remoto no Skype para Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o acesso de usuário remoto usando cmdlets do Windows PowerShell

Acesso de usuários remotos pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Skype para Business Server 2013 Management Shell ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar o acesso de usuário remoto

  - Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Para desabilitar o acesso de usuário remoto

  - Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


