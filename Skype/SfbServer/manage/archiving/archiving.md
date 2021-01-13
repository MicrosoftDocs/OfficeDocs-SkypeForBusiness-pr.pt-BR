---
title: Gerenciar arquivamento no Skype for Business Server
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumo: saiba como gerenciar o arquivamento do Skype for Business Server.'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817731"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gerenciar arquivamento no Skype for Business Server

**Resumo:** Saiba como gerenciar o arquivamento do Skype for Business Server.
  
Ao implantar o arquivamento para sua organização, você especifica a configuração inicial durante a implantação. No entanto, pode haver momentos em que você queira alterar a forma como implementa o suporte de arquivamento para gerenciamento do dia a dia ou para atender aos novos requisitos da sua organização. Por exemplo, talvez seja necessário configurar o suporte ao arquivamento de maneira diferente para um site específico, um pool específico ou usuários específicos dentro da sua organização. Para usuários que estão no Skype for Business Server, você faz isso criando e personalização de opções de configuração de arquivamento e políticas de usuário. 
  
Antes de ler este tópico, certifique-se de estar familiarizado com as informações em [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Deploy [archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Espera. Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opções de configuração de arquivamento

As opções de configuração de arquivamento especificam se:
  
- Habilitar ou desabilitar o arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear atividade quando o arquivamento não estiver disponível
    
- Usar a integração com o Exchange
    
- Configurar a purgação e a exportação de dados
    
Essas opções podem ser definidas no nível global, de site ou de pool. Para obter mais informações, [consulte Gerenciar opções de arquivamento no Skype for Business Server.](options.md)
  
## <a name="archiving-policies"></a>Políticas de arquivamento

As políticas de arquivamento determinam se arquivarão o seguinte:
  
- Comunicações internas
    
- Comunicações externas
    
Essas políticas podem ser definidas no nível global, de site ou de usuário. Para obter mais informações, [consulte Gerenciar políticas de arquivamento no Skype for Business Server.](policies.md)
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gerenciar arquivamento usando o Painel de Controle ou o Windows PowerShell

Você pode gerenciar o arquivamento usando o Painel de Controle ou o Windows PowerShell. A tabela a seguir resume os cmdlets disponíveis para ajudá-lo a gerenciar o arquivamento. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype for Business Server Management Shell](../management-shell.md). 


|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta registros armazenados no banco de dados de Arquivamento do Skype for Business Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as definições de configuração de arquivamento em sua organização.  <br/> |
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento da sua organização para comunicações internas e externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui políticas de arquivamento de sessões de mensagens instantâneas (IM) a usuários ou conjuntos de usuários. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Exclui manualmente registros do banco de dados de Arquivamento.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações de mensagens instantâneas (IM), que pode ser usado para habilitar ou desabilitar o salvar automático de sessões de IM e para bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove o conjunto especificado de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvar automático de sessões de mensagens instantâneas (IM) e, opcionalmente, bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove a política de arquivamento de mensagens instantâneas (IM) especificada que determina se o Skype for Business Server salvará automaticamente todas as sessões de IM que ocorrerem entre usuários internos e/ou todas as sessões de IM entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências que ocorrerem entre usuários internos; é possível também arquivar sessões que ocorrerem entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar um novo local de banco de dados para um ou mais Servidores de Arquivamento.  <br/> |
   

