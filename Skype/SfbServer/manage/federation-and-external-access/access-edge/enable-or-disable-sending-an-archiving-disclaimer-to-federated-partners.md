---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Ativar ou desativar o envio de um aviso de isenção de responsabilidade de arquivamento para parceiros federados Skype for Business Server.
ms.openlocfilehash: 020ba61ed45a214466ac22e1d13cbe27563697a1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386660"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de arquivamento para parceiros federados Skype for Business Server

No momento em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se enviaria automaticamente a isenção de arquivamento para parceiros federados. Se você arquiva comunicações externas, deverá habilitar o envio de uma isenção de arquivamento. Use o procedimento deste tópico para alterar essa configuração.

> [!NOTE]
> O procedimento a seguir assume que você já habilitou a federação para sua organização. Para obter detalhes sobre como habilitar a federação, consulte [Enable or disable remote user access](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Acesso de Usuário Externo** e clique em **Configuração de Borda de Acesso**.

4.  Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, em **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção de responsabilidade de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.

6.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários em sua implantação Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuário federado. Para obter detalhes sobre como controlar o acesso a domínios federados específicos, consulte [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o aviso de isenção de responsabilidade de arquivamento usando Windows PowerShell cmdlets

O uso do aviso de isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration de arquivamento. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar o aviso de isenção de responsabilidade de arquivamento

  - Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para True ($True):<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para desabilitar o aviso de isenção de responsabilidade de arquivamento

  - Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para False ($False):<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

