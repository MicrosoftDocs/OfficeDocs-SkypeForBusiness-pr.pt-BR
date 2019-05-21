---
title: Configurar o arquivamento de avisos de isenção de responsabilidade para usuários externos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumo: Leia este tópico para saber como configurar uma isenção de responsabilidade de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 86430ac80d85ed166ae091119f4261cdc5e1ff9b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278980"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurar o arquivamento de avisos de isenção de responsabilidade para usuários externos no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar uma isenção de responsabilidade de arquivamento para o Skype for Business Server.
  
Se a sua organização se comunica com parceiros externos, você precisa avisá-los de que está arquivando sua comunicação com eles. Ao implantar um servidor de borda e habilitar a Federação para sua organização, você será perguntado se deseja enviar automaticamente uma isenção de responsabilidade para os parceiros externos. 
  
Se precisar alterar essa configuração, você pode usar o painel de controle do Skype for Business Server ou o cmdlet **set-CsAccessEdgeConfiguration** do Windows PowerShell. Cmdlets podem ser executados do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.
  
Para permitir que usuários externos colaborem com usuários na implantação do Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuários externos. Para obter detalhes, consulte Gerenciar parceiros federados XMPP para sua organização. Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte Controlar Acesso por Domínios Federados Individuais.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar ou desabilitar um aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle

1. Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
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


