---
title: Configurar avisos de isenção de responsabilidade de arquivamento para usuários externos Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumo: leia este tópico para saber como configurar um aviso de isenção de responsabilidade de arquivamento para Skype for Business Server.'
ms.openlocfilehash: 05eaec40556b383525331405463ee6d0a10e0a13
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834709"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurar avisos de isenção de responsabilidade de arquivamento para usuários externos Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar um aviso de isenção de responsabilidade de arquivamento para Skype for Business Server.
  
Se sua organização se comunicar com parceiros externos, você precisará informar a eles que está arquivando comunicações com eles. Quando você implanta um Servidor de Borda e habilita a federação para sua organização, é perguntado se deseja enviar automaticamente um aviso de isenção de responsabilidade de arquivamento para parceiros externos. 
  
Se você precisar alterar essa configuração, poderá usar o Painel de Controle Skype for Business Server ou o cmdlet **Windows PowerShell Set-CsAccessEdgeConfiguration.** Os cmdlets podem ser executados no shell de gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell.
  
Para permitir que usuários externos colaborem com usuários em sua implantação Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário externo. Para obter detalhes, consulte Manage XMPP Federated Partners for Your Organization. Para obter detalhes sobre como controlar o acesso a domínios federados específicos, consulte Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar ou desabilitar o aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.
    
4. Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Configuração** de Borda de Acesso , em Habilitar a conectividade de **IM** pública e federação, selecione ou desembolse a caixa de seleção Enviar aviso de isenção de responsabilidade de arquivamento para parceiros **federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.
    
6. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Habilitar ou desabilitar o aviso de isenção de responsabilidade de arquivamento usando Windows PowerShell

Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para True ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para False ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


