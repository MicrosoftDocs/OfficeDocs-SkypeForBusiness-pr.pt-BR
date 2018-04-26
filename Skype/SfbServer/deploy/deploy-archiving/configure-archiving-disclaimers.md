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
description: 'Resumo: Leia este tópico para aprender como configurar um aviso de isenção de responsabilidade de arquivamento para o .'
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a>Configurar avisos de isenção de arquivamento para usuários externos no Skype for Business Server 2015
 
Resumo: Leia este tópico para aprender como configurar um aviso de isenção de responsabilidade de arquivamento para o .
  
Se a sua organização se comunica com parceiros externos, você precisa avisá-los de que está arquivando sua comunicação com eles. Ao implantar um Servidor de Borda e habilitar a federação para a sua organização, você deverá dizer se quer ou não enviar um aviso de isenção de responsabilidade automaticamente para os parceiros externos. 
  
Se for necessário alterar esta configuração, use o Painel de Controle do  ou o cmdlet  Set-CsAccessEdgeConfiguration. Cmdlets podem ser executados a partir do shell de gerenciamento do  ou de uma sessão remota do .
  
Para permitir que os usuários externos colaborem com usuários em sua implantação do , é necessário configurar pelo menos uma política de acesso externa para suportar o acesso de usuário externo. Para obter detalhes, consulte Gerenciar Parceiros XMPP Federados para Sua Organização. Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte Controlar Acesso por Domínios Federados Individuais.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar ou desabilitar um aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle

1. Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
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


