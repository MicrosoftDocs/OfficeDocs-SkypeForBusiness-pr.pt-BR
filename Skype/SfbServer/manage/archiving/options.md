---
title: Gerenciar opções de arquivamento no Skype for Business Server
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
description: 'Resumo: saiba como configurar opções de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817531"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Gerenciar opções de arquivamento no Skype for Business Server

**Resumo:** Saiba como configurar opções de arquivamento para o Skype for Business Server.
  
Inicialmente, você configura o arquivamento na implantação, mas pode alterar, adicionar e excluir configurações após a implantação. As opções de arquivamento determinam se: 
  
- Habilitar ou desabilitar o arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear atividade quando o arquivamento não estiver disponível
    
- Usar a integração com o Exchange
    
- Configurar a purgação e a exportação de dados
    
Você pode especificar opções de configuração nos seguintes níveis:
  
- Configuração de nível global criada por padrão ao implantar o Skype for Business Server
    
- Configurações opcionais no nível do site que especificam como o arquivamento é implementado para um site específico
    
- Configurações opcionais no nível do pool que especificam como o arquivamento é implementado para um pool específico
    
Você pode excluir uma configuração de site ou configuração de pool, mas não pode excluir a configuração global. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão. Para obter detalhes sobre como as configurações de arquivamento são implementadas e a hierarquia das configurações de arquivamento, consulte Plano para arquivamento no [Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar opções de arquivamento usando o Painel de Controle

Você pode configurar opções de arquivamento usando o Painel de Controle da seguinte forma:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
    
3. Na barra de navegação esquerda, clique em **Configuração de Arquivamento.**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar opções de arquivamento usando o Windows PowerShell

Você também pode configurar opções de arquivamento usando os cmdlets do Windows PowerShell listados na tabela a seguir. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as definições de configuração de arquivamento em sua organização.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações de mensagens instantâneas (IM), que pode ser usado para habilitar ou desabilitar o salvar automático de sessões de IM e para bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove o conjunto especificado de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvar automático de sessões de mensagens instantâneas (IM) e, opcionalmente, bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
