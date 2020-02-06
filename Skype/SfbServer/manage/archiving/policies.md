---
title: Gerenciar políticas de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumo: saiba como gerenciar políticas de usuário para o arquivamento do Skype for Business Server.'
ms.openlocfilehash: f2dca47dd7fd3095b2865ff72516b6be84144352
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818883"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gerenciar políticas de arquivamento no Skype for Business Server

**Resumo:** Saiba como gerenciar políticas de usuário para arquivamento para o Skype for Business Server.
  
Inicialmente, você define as políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação. As políticas de arquivamento determinam se devem ser arquivadas: 
  
- Comunicações internas
    
- Comunicações externas
    
As políticas de arquivamento podem ser definidas no nível global, do site ou do usuário.
  
> [!NOTE]
> Se você ativou a integração do Microsoft Exchange para a sua implantação, as políticas do Exchange controlam se o arquivamento está habilitado para os usuários que são hospedados no Exchange e têm suas caixas de correio colocadas no bloqueio in-loco. Para obter detalhes, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configurar a integração com o armazenamento do Exchange para o Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gerenciar políticas de arquivamento usando o Painel de Controle

Você pode gerenciar políticas de arquivamento usando o Painel de Controle da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Política de arquivamento**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gerenciar políticas de arquivamento usando o Windows PowerShell

Você também pode configurar políticas de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Shell de gerenciamento do Skype for Business Server](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento de sessões de mensagens instantâneas (IM) da sua organização.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui a usuários ou grupos de usuários políticas de arquivamento de sessões de mensagens instantâneas (IM). Essas políticas permitem arquivar sessões de IM entre usuários internos e/ou arquivar sessões de IM entre usuários internos e externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove a política de arquivamento de mensagens instantâneas (IM) especificada que determina se o Skype for Business Server salvará automaticamente todas as sessões de mensagens instantâneas que ocorrem entre usuários internos e/ou todas as sessões de mensagens instantâneas entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências entre usuários internos; é possível também arquivar sessões que entre usuários internos e parceiros federados.  <br/> |
   

