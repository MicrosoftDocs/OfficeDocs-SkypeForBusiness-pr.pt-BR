---
title: Gerenciar opções de arquivamento no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumo: Saiba como configurar opções de arquivamento para Skype para Business Server.'
ms.openlocfilehash: 235a0170a4301e48caeae17b7315a174ca2c8aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993564"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gerenciar opções de arquivamento no Skype para Business Server

**Resumo:** Saiba como configurar opções de arquivamento para Skype para Business Server.
  
Inicialmente, você configura o arquivamento no momento da implantação, mas você e pode alterar, adicionar e excluir configurações após a implantação. As opções de arquivamento determinam: 
  
- Habilitar ou desabilitar arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear uma atividade quando o arquivamento não estiver disponível
    
- Usar integração com o Exchange
    
- Configurar a limpeza e exportação de dados
    
Você pode especificar opções de configuração nos seguintes níveis:
  
- Configuração no nível global criada por padrão quando você implanta o Skype para Business Server
    
- Configurações opcionais em nível de site que especificam como o arquivamento é implementado para um site específico
    
- Configurações opcionais de nível do pool que especificam como o arquivamento é implementado para um pool específico
    
Você pode excluir uma configuração de site ou de pool, mas não a configuração global. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão. Para obter detalhes sobre como as configurações de arquivamento são implementadas e a hierarquia de arquivamento configurações, consulte [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar opções de arquivamento usando o Painel de Controle

Você pode configurar opções de arquivamento usando o Painel de Controle da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação esquerda, clique em **Configuração de arquivamento**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar opções de arquivamento usando o Windows PowerShell

Você também pode configurar opções de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do servidor de negócios](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as configurações de arquivamento na sua organização.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações do sistema de mensagens instantâneas (IM), que podem ser usadas para habilitar ou desabilitar a gravação automática de sessões de IM, e também para bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvamento automático de sessões de mensagem instantânea (IM) e bloquear opcionalmente qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |