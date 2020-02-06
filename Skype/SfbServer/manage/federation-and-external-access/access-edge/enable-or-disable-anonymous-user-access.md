---
title: Habilitar ou desabilitar acesso de usuário anônimo
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818402"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuários anônimos no Skype for Business Server

Usuários anônimos são usuários que não têm uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência local. Ao permitir a participação anônima em reuniões, usuários anônimos (ou seja, usuários cuja identidade são verificadas apenas na reunião ou na chave da conferência) para ingressar em reuniões. Permitir a participação anônima exige a habilitação da sua organização.

Se, mais tarde, você quiser impedir o acesso temporário ou permanente de usuários anônimos, pode desabilitá-lo para a sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos para sua organização.

> [!NOTE]  
> Ao habilitar o acesso de usuários anônimos para sua organização, você está especificando que seus servidores que executam o serviço de borda de acesso oferecem suporte a usuários anônimos. Usuários anônimos não podem participar de nenhuma reunião em sua organização até você também configurar pelo menos uma política de conferência e aplicá-la a um ou mais usuários ou grupos de usuários. Os únicos usuários que podem convidar usuários anônimos para reuniões são os usuários que recebem uma política de conferência configurada para dar suporte a usuários anônimos. Para obter detalhes sobre como configurar as políticas de conferência para dar suporte ao convite para usuários anônimos, consulte [gerenciar políticas de conferência](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuários anônimos para a sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**e, em seguida, clique em **configuração de borda de acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, siga um destes procedimentos:
    
      - Para habilitar o acesso de usuários anônimos para sua organização, marque a caixa de seleção **habilitar comunicações com usuários anônimos** .
    
      - Para desabilitar o acesso de usuários anônimos para sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários anônimos** .

6.  Clique em **Confirmar**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o acesso de usuários anônimos usando cmdlets do Windows PowerShell

Você pode gerenciar o acesso de usuários anônimos usando o Windows PowerShell e o cmdlet **set-CsAccessEdgeConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar o acesso de usuários anônimos

  - Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para desativar o acesso de usuários anônimos

  - Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Confira também

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
