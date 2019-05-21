---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280212"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Skype for Business Server

No momento em que você implantou seus servidores de borda e habilitou a Federação para a sua organização, você deve especificar se deseja enviar automaticamente a isenção de arquivo para parceiros federados. Se você arquivar comunicações externas, habilite o envio de uma isenção de arquivo morto. Use o procedimento deste tópico para alterar essa configuração.

> [!NOTE]
> O procedimento a seguir pressupõe que você já habilitou a Federação para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte [habilitar ou desabilitar o acesso de usuários remotos](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**, clique em **configuração de borda de acesso**.

4.  Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, em **habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar isenção de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do arquivamento isenção.

6.  Clique em **Confirmar**.

Para permitir que os usuários federados colaborem com usuários na implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados. Para obter detalhes sobre o controle do acesso a domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o arquivamento de isenção de responsabilidade usando cmdlets do Windows PowerShell

O uso da isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Para habilitar a isenção de responsabilidade de arquivamento

  - Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Verdadeiro ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Para desativar a isenção de responsabilidade de arquivamento

  - Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Falso ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


