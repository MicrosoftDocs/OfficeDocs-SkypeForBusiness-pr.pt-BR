---
title: Gerenciar políticas de arquivamento em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumo: saiba como gerenciar políticas de usuário para arquivamento para Skype for Business Server.'
ms.openlocfilehash: 53292377876f63a016c0720ec61f65da31650077
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754940"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a>Gerenciar políticas de arquivamento em Skype for Business Server

**Resumo:** Saiba como gerenciar políticas de usuário para arquivamento para Skype for Business Server.
  
Inicialmente, você configura políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação. As políticas de arquivamento determinam se são arquivadas: 
  
- Comunicações internas
    
- Comunicações externas
    
As políticas de arquivamento podem ser definidas no nível global, do site ou do usuário.
  
> [!NOTE]
> Se você habilitar Exchange integração do Microsoft Exchange para sua implantação, as políticas Exchange controlarão se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Hold. Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for [Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Gerenciar políticas de arquivamento usando o Painel de Controle

Você pode gerenciar políticas de arquivamento usando o Painel de Controle da seguinte forma:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Política de Arquivamento**
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Gerenciar políticas de arquivamento usando Windows PowerShell

Você também pode configurar políticas de arquivamento usando os cmdlets de Windows PowerShell listados na tabela a seguir. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, [consulte Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento de sessões de mensagens instantâneas (IM) da sua organização.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui políticas de arquivamento de sessão de mensagens instantâneas (IM) a usuários ou conjuntos de usuários. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove a política de arquivamento de mensagens instantâneas especificada (IM) que determina se o Skype for Business Server salvará automaticamente todas as sessões de mensagens instantâneas que ocorrem entre usuários internos e/ou todas as sessões de mensagens instantâneas entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências que ocorrerem entre usuários internos; é possível também arquivar sessões que ocorrerem entre usuários internos e parceiros federados.  <br/> |
   

