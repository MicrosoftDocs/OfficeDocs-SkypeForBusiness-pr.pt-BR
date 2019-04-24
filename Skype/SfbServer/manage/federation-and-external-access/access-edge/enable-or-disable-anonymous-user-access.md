---
title: Habilitar ou desabilitar acesso de usuário anônimo
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a68790f870a6c62b513caab559580695763cd4df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199945"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuário anônimo no Skype para Business Server

Usuários anônimos são usuários que não têm uma conta de usuário no Active Directory Domain Services da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência no local. Permitindo a participação anônima em reuniões permitir que usuários anônimos (ou seja, os usuários cuja identidade é confirmada através a chave de reunião ou conferência somente) para participar de reuniões. Permitindo a participação anônima requer ativá-lo para sua organização.

Se você quiser mais tarde temporária ou permanentemente impedir o acesso por usuários anônimos, você pode desabilitá-lo para sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário anônimo para sua organização.

> [!NOTE]  
> Habilitando o acesso de usuário anônimo para sua organização estiver apenas especificando que os servidores que executam o serviço de borda de acesso para suportam o acesso por usuários anônimos. Usuários anônimos não podem participar de qualquer reuniões em sua organização até que você também configurar pelo menos uma política de conferência e aplicá-la a um ou mais usuários ou grupos de usuários. Os usuários só podem convidar usuários anônimos para reuniões são os usuários que estão atribuídos a uma política de conferência que está configurada para oferecer suporte a usuários anônimos. Para obter detalhes sobre como configurar políticas de conferência para suportar convidem usuários anônimos, consulte [Gerenciar políticas de conferência](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário anônimo para sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Configuração de borda de acesso**.

4.  Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, execute um destes procedimentos:
    
      - Para habilitar o acesso de usuário anônimo para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários anônimos** .
    
      - Para desabilitar o acesso de usuário anônimo para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários anônimos** .

6.  Clique em **Confirmar**.


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o acesso de usuário anônimo usando os cmdlets do Windows PowerShell

Você pode gerenciar o acesso de usuário anônimo usando o Windows PowerShell e o cmdlet **Set-CsAccessEdgeConfiguration** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar o acesso de usuário anônimo

  - Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para verdadeiro ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para desabilitar o acesso de usuário anônimo

  - Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para FALSO ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Consulte Também

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
