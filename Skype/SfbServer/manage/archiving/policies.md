---
title: Gerenciar políticas de arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumo: Saiba como gerenciar políticas de usuário para arquivamento para Skype para Business Server.'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211052"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gerenciar políticas de arquivamento no Skype para Business Server

**Resumo:** Saiba como gerenciar políticas de usuário para arquivamento para Skype para Business Server.
  
Inicialmente, você configurar políticas de arquivamento quando você implanta o arquivamento, mas você pode alterar, adicionar e excluir configurações após a implantação. Políticas de arquivamento determinam se deseja arquivar: 
  
- Comunicações internas
    
- Comunicações externas
    
Políticas de arquivamento podem ser definido no nível global, site ou nível de usuário.
  
> [!NOTE]
> Se você ativou a integração do Microsoft Exchange para sua implantação, o controle de políticas do Exchange se o arquivamento estiver habilitado para os usuários hospedados no Exchange e tem colocado de suas caixas de correio em bloqueio In-loco. Para obter detalhes, consulte [Planejar o arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configure integração com Exchange storage para Skype para Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gerenciar políticas de arquivamento usando o Painel de Controle

Você pode gerenciar políticas de arquivamento usando o Painel de Controle da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação esquerda, clique em **Política de arquivamento**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gerenciar políticas de arquivamento usando o Windows PowerShell

Você também pode configurar políticas de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do servidor de negócios](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento de sessões de mensagens instantâneas (IM) da sua organização.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui a usuários ou grupos de usuários políticas de arquivamento de sessões de mensagens instantâneas (IM). Essas políticas permitem arquivar sessões de IM entre usuários internos e/ou arquivar sessões de IM entre usuários internos e externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove o especificado mensagens instantâneas (IM) que determina se o Skype para Business Server salvará automaticamente todas as sessões IM ocorridas entre usuários internos e/ou todas as sessões de mensagens Instantâneas entre usuários internos e parceiros federados política de arquivamento.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências entre usuários internos; é possível também arquivar sessões que entre usuários internos e parceiros federados.  <br/> |
   

