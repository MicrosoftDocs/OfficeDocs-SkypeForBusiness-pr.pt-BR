---
title: Gerenciar opções de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumo: saiba como configurar opções de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: c7353c305125e8e35523c573150471821f53301e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278416"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gerenciar opções de arquivamento no Skype for Business Server

**Resumo:** Saiba como configurar opções de arquivamento para o Skype for Business Server.
  
Inicialmente, você configura o arquivamento no momento da implantação, mas você e pode alterar, adicionar e excluir configurações após a implantação. As opções de arquivamento determinam: 
  
- Habilitar ou desabilitar arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear uma atividade quando o arquivamento não estiver disponível
    
- Usar integração com o Exchange
    
- Configurar a limpeza e exportação de dados
    
Você pode especificar opções de configuração nos seguintes níveis:
  
- Configuração de nível global que é criada por padrão quando você implanta o Skype for Business Server
    
- Configurações opcionais em nível de site que especificam como o arquivamento é implementado para um site específico
    
- Configurações opcionais de nível de pool que especificam como o arquivamento é implementado para um pool específico
    
Você pode excluir uma configuração de site ou de pool, mas não pode excluir a configuração global. Se você excluir a configuração global, ela automaticamente retorna para os valores padrão. Para obter detalhes sobre como as configurações de arquivamento são implementadas e a hierarquia de configurações de arquivamento, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar opções de arquivamento usando o Painel de Controle

Você pode configurar opções de arquivamento usando o Painel de Controle da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Configuração de arquivamento**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar opções de arquivamento usando o Windows PowerShell

Você também pode configurar opções de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Shell de gerenciamento do Skype for Business Server](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as configurações de arquivamento na sua organização.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações do sistema de mensagens instantâneas (IM), que podem ser usadas para habilitar ou desabilitar a gravação automática de sessões de IM, e também para bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvamento automático de sessões de mensagem instantânea (IM) e bloquear opcionalmente qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
