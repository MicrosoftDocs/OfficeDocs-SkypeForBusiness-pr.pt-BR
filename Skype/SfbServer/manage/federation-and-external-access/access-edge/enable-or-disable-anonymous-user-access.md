---
title: Habilitar ou desabilitar o acesso de usuário anônimo
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
ms.openlocfilehash: cc0d779e2728fd2a82547b52bda57c05c7a983a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005996"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuário anônimo no Skype for Business Server

Usuários anônimos são usuários que não possuem uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência local. Ao permitir a participação anônima em reuniões, você habilita os usuários anônimos (isto é, usuários cuja identidade é verificada apenas por meio da chave de reunião ou conferência) a participarem de reuniões. Para permitir a participação anônima em sua organização, é necessário que você habilite esse recurso.

Se mais tarde você quiser prevenir o acesso de usuários anônimos temporariamente ou permanentemente, é possível desabilitar esse acesso à sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos à sua organização.

> [!NOTE]  
> Habilitar o acesso de usuários anônimos à sua organização apenas especifica que seus servidores que estão executando o serviço de Borda de Acesso dão suporte ao acesso de usuários anônimos. Os usuários anônimos não podem participar de nenhuma reunião da sua organização até que seja configurada ao menos uma política de conferência e que esta seja aplicada a um ou mais usuários ou grupos de usuários. Os únicos usuários que podem convidar usuários anônimos para reuniões são aqueles com uma política de conferência designada configurada para dar suporte aos usuários anônimos. Para obter detalhes sobre como configurar as políticas de conferência para suportar o convite de usuários anônimos, consulte [Manage Conferencing Policies](../../conferencing/conferencing-policies.md).

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuários anônimos à sua organização

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server. 

3.  No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso de usuários anônimos à sua organização, marque a caixa de seleção **Habilitar comunicações com usuários anônimos**.
    
      - Para desabilitar o acesso de usuários anônimos à sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários anônimos**.

6.  Clique em **Confirmar**


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o acesso de usuário anônimo usando cmdlets do Windows PowerShell

Você pode gerenciar o acesso de usuários anônimos usando o Windows PowerShell e o cmdlet **set-CsAccessEdgeConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-anonymous-user-access"></a>Para habilitar o acesso de usuário anônimo

  - Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Verdadeiro ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>Para desabilitar o acesso de usuário anônimo

  - Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Falso ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>Confira também

[Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
