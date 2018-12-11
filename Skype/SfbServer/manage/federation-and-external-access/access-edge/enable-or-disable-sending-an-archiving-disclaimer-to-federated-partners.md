---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 3e076e1044a65c45a8fc72d0e7d54369d4c3196f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222776"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Skype para Business Server

No momento você implantado servidores de borda e habilitado a federação para sua organização, você deve especificou se é enviar automaticamente a isenção de responsabilidade de arquivamento para parceiros federados. Se você arquivar comunicações externas, você deve habilitar o envio de uma isenção de responsabilidade de arquivamento. Use o procedimento neste tópico para alterar essa configuração.

> [!NOTE]
> O procedimento a seguir pressupõe que você já tiver habilitado a federação para sua organização. Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**, clique em **Configuração de borda de acesso**.

4.  Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, sob **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção para parceiros federados de arquivamento** para habilitar ou desabilitar o envio automaticamente o arquivamento isenção de responsabilidade.

6.  Clique em **Confirmar**.

Para habilitar os usuários federados colaborar com usuários em sua Skype para implantação Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado. Para obter detalhes sobre como controlar o acesso de domínios federados específicos, consulte [Configure suporte a domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a isenção de responsabilidade de arquivamento usando cmdlets do Windows PowerShell

O uso da isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar a isenção de responsabilidade de arquivamento

  - Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Verdadeiro ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para desabilitar a isenção de responsabilidade de arquivamento

  - Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Falso ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


