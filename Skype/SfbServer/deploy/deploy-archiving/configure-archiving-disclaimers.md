---
title: Configurar avisos de isenção de arquivamento para usuários externos no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumo: Leia este tópico para saber como configurar uma isenção de responsabilidade de arquivamento do Skype para Business Server 2015.'
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a>Configurar avisos de isenção de arquivamento para usuários externos no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como configurar uma isenção de responsabilidade de arquivamento do Skype para Business Server 2015.
  
Se a sua organização se comunica com parceiros externos, você precisa avisá-los de que está arquivando sua comunicação com eles. Quando você implanta um servidor de borda e habilitar a federação para sua organização, você será solicitado que se você deseja enviar automaticamente uma isenção de responsabilidade de arquivamento para parceiros externos. 
  
Se você precisar alterar essa configuração, você pode usar o Skype para painel de controle do Business Server ou o cmdlet do Windows PowerShell **Set-CsAccessEdgeConfiguration** . Cmdlets pode ser executados a partir do Skype do shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.
  
Para permitir que usuários externos colaborar com usuários em sua Skype para implantação Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário externo. Para obter detalhes, consulte Manage XMPP Federated Partners for Your Organization. Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte Controlar Acesso por Domínios Federados Individuais.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar ou desabilitar um aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle

1. Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.
    
4. Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Configuração de Borda de Acesso**, em **Habilitar federação e conectividade de IM pública**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção de responsabilidade de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.
    
6. Clique em **Confirmar**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Habilitar ou desabilitar um aviso de isenção de responsabilidade de arquivamento usando o Windows PowerShell

Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Verdadeiro ($True):
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Falso ($False):
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


