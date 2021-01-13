---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
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
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817351"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados no Skype for Business Server

No momento em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se enviaria automaticamente a isenção de arquivamento para parceiros federados. Se você arquiva comunicações externas, deverá habilitar o envio de uma isenção de arquivamento. Use o procedimento deste tópico para alterar essa configuração.

> [!NOTE]
> O procedimento a seguir assume que você já habilitou a federação para sua organização. Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Acesso de Usuário Externo** e clique em **Configuração de Borda de Acesso**.

4.  Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, em **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção de responsabilidade de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.

6.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários em sua implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado. Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o aviso de isenção de responsabilidade de arquivamento usando cmdlets do Windows PowerShell

O uso do aviso de isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar o aviso de isenção de responsabilidade de arquivamento

  - Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para desabilitar o aviso de isenção de responsabilidade de arquivamento

  - Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


