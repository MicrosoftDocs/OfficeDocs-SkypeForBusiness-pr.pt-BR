---
title: Configurar avisos de isenção de responsabilidade de arquivamento para usuários externos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumo: Leia este tópico para saber como configurar um aviso de isenção de responsabilidade de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820661"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurar avisos de isenção de responsabilidade de arquivamento para usuários externos no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar um aviso de isenção de responsabilidade de arquivamento para o Skype for Business Server.
  
Se sua organização se comunica com parceiros externos, você precisa informar a eles que está arquivando as comunicações com eles. Ao implantar um Servidor de Borda e habilitar a federação para sua organização, você será perguntado se deseja enviar automaticamente um aviso de isenção de responsabilidade de arquivamento para parceiros externos. 
  
Se você precisar alterar essa configuração, poderá usar o Painel de Controle do Skype for Business Server ou o cmdlet **Set-CsAccessEdgeConfiguration** do Windows PowerShell. Os cmdlets podem ser executados a partir do shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.
  
Para permitir que usuários externos colaborem com usuários em sua implantação do Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuários externos. Para obter detalhes, consulte Gerenciar Parceiros Federados XMPP para Sua Organização. Para obter detalhes sobre como controlar o acesso a domínios federados específicos, consulte Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar ou desabilitar o aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle

1. Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.
    
4. Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar** Configuração de Borda de Acesso, em Habilitar federação e conectividade de **IM** pública, marque ou des limpe a caixa de seleção Enviar aviso de isenção de responsabilidade de arquivamento para parceiros **federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.
    
6. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Habilitar ou desabilitar o aviso de isenção de responsabilidade de arquivamento usando o Windows PowerShell

Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para True ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para False ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


