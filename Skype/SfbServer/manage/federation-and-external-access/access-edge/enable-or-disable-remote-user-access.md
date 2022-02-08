---
title: Habilitar ou desabilitar acesso de usuário remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos com suporte se conectam pela Internet e não têm que se conectar usando uma VPN para colaborar com usuários internos usando Skype for Business Server.
ms.openlocfilehash: 94ff8263e61e8113a2f1d47104524d073a082665
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395273"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Habilitar ou desabilitar o acesso de usuário remoto Skype for Business Server

Usuários remotos são usuários em suas organizações com uma identidade do Active Directory persistente dentro da organização. Os usuários remotos geralmente fazem login Skype for Business Server de fora da sua rede usando uma VPN (rede virtual privada) quando não estão conectados à rede da sua organização. Os usuários remotos incluem funcionários trabalhando em casa ou na estrada e outros trabalhadores remotos, como vendedores confiáveis, que foram concedidos com credenciais empresariais. Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos com suporte se conectam pela Internet e não têm que se conectar usando uma VPN para colaborar com usuários internos usando Skype for Business Server.

Para suportar acesso de usuário remoto, você deve habilitar o acesso de usuário remoto. Ao habilitar o acesso de usuário remoto, você o habilita para toda sua organização. Se posteriormente você quiser impedir temporariamente ou permanentemente o acesso dos domínios federados pelos usuários, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso do usuário federado para sua organização.


> [!NOTE]  
> Habilitar o acesso de usuário remoto apenas especifica que seus servidores executando as comunicações de suporte do serviço de Borda de Acesso com usuário remotos, mas os usuários remotos não podem participar de mensagem instantânea (IM) ou conferências em sua organização até que você também configure pelo menos uma política para gerenciar o uso do acesso de usuário remoto. Skype for Business Server configurações de política aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto. Para obter detalhes sobre como configurar políticas para o uso do acesso de usuário remoto, consulte [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso do usuário federado na sua organização

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
    - Para habilitar o acesso ao usuário remoto para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários federados**.
    
    - Para desabilitar o acesso ao usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.

6.  Clique em **Confirmar**.

Para permitir que os usuários remotos entre em seus servidores que executam Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário remoto. Para obter detalhes, consulte [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o acesso de usuário remoto usando Windows PowerShell cmdlets

O acesso de usuário remoto pode ser gerenciado usando Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration usuário. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server 2013 ou em uma sessão remota de Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Para habilitar o acesso de usuário remoto

Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):

```powershell
Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True
```

## <a name="to-disable-remote-user-access"></a>Para desabilitar o acesso de usuário remoto

Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):

```powershell
Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False
```
