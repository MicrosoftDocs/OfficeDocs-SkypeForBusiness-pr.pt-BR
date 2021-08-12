---
title: Gerenciar opções de arquivamento em Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumo: saiba como configurar opções de arquivamento para Skype for Business Server.'
ms.openlocfilehash: b2ed0644e64df1606141b94157920d98599fb020db7bdf39d522699fb88555ef
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338139"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gerenciar opções de arquivamento em Skype for Business Server

**Resumo:** Saiba como configurar opções de arquivamento para Skype for Business Server.
  
Inicialmente, você configura o arquivamento na implantação, mas pode alterar, adicionar e excluir configurações após a implantação. As opções de arquivamento determinam se: 
  
- Habilitar ou desabilitar o arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear atividade quando o arquivamento não estiver disponível
    
- Usar Exchange integração
    
- Configurar a purgação e a exportação de dados
    
Você pode especificar opções de configuração nos seguintes níveis:
  
- Configuração de nível global criada por padrão quando você implanta Skype for Business Server
    
- Configurações opcionais no nível do site que especificam como o arquivamento é implementado para um site específico
    
- Configurações opcionais no nível do pool que especificam como o arquivamento é implementado para um pool específico
    
Você pode excluir uma configuração de site ou configuração de pool, mas não pode excluir a configuração global. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão. Para obter detalhes sobre como as configurações de arquivamento são implementadas e a hierarquia de configurações de arquivamento, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar opções de arquivamento usando o Painel de Controle

Você pode configurar opções de arquivamento usando o Painel de Controle da seguinte forma:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Configuração de Arquivamento.**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar opções de arquivamento usando Windows PowerShell

Você também pode configurar opções de arquivamento usando os cmdlets de Windows PowerShell listados na tabela a seguir. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, [consulte Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as configurações de arquivamento em sua organização.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações de mensagens instantâneas (IM), que pode ser usado para habilitar ou desabilitar a economia automática de sessões de mensagens instantâneas e bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar a economia automática de sessões de mensagens instantâneas (IM) e, opcionalmente, bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
