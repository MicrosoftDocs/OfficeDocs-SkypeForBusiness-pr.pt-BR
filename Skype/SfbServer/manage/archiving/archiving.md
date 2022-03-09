---
title: Gerenciar arquivamento em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumo: saiba como gerenciar o arquivamento para Skype for Business Server.'
ms.openlocfilehash: 0849a9fbc3db95579a1711e2934b0bafdc7b6e23
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392653"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gerenciar arquivamento em Skype for Business Server

**Resumo:** Saiba como gerenciar o arquivamento para Skype for Business Server.
  
Ao implantar o arquivamento para sua organização, especifique a configuração inicial durante a implantação. No entanto, pode haver momentos em que você deseja alterar como implementar o suporte de arquivamento para gerenciamento do dia a dia ou para atender aos novos requisitos para sua organização. Por exemplo, talvez seja necessário configurar o suporte de arquivamento de forma diferente para um site específico, um pool específico ou usuários específicos em sua organização. Para usuários que estão Skype for Business Server, você faz isso criando e personalização de opções de configuração de arquivamento e políticas de usuário. 
  
Antes de ler este tópico, certifique-se de que você está familiarizado com as informações em [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Se você habilitar Exchange integração do Microsoft Exchange para sua implantação, as políticas Exchange controlam se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Hold. Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opções de configuração de arquivamento

As opções de configuração de arquivamento especificam se:
  
- Habilitar ou desabilitar o arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear atividade quando o arquivamento não estiver disponível
    
- Usar Exchange integração
    
- Configurar a purgação e a exportação de dados
    
Essas opções podem ser definidas no nível global, do site ou do pool. Para obter mais informações, consulte [Gerenciar opções de arquivamento em Skype for Business Server](options.md).
  
## <a name="archiving-policies"></a>Políticas de arquivamento

As políticas de arquivamento determinam se arquivar o seguinte:
  
- Comunicações internas
    
- Comunicações externas
    
Essas políticas podem ser definidas no nível global, do site ou do usuário. Para obter mais informações, consulte [Gerenciar políticas de arquivamento em Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gerenciar arquivamento usando o Painel de Controle ou usando Windows PowerShell

Você pode gerenciar o arquivamento usando o Painel de Controle ou usando Windows PowerShell. A tabela a seguir resume os cmdlets disponíveis para ajudá-lo a gerenciar o arquivamento. Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, [consulte Skype for Business Server Shell de Gerenciamento](../management-shell.md). 


|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta registros armazenados no banco de dados Skype for Business Server arquivamento.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as configurações de arquivamento em sua organização.  <br/> |
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento da sua organização para comunicações internas e externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui políticas de arquivamento de sessão de mensagens instantâneas (IM) a usuários ou conjuntos de usuários. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Exclui manualmente registros do banco de dados de Arquivamento.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações de mensagens instantâneas (IM), que pode ser usado para habilitar ou desabilitar a economia automática de sessões de mensagens instantâneas e bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar a economia automática de sessões de mensagens instantâneas (IM) e, opcionalmente, bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove a política de arquivamento de mensagens instantâneas especificada (IM) que determina se o Skype for Business Server salvará automaticamente todas as sessões de mensagens instantâneas que ocorrem entre usuários internos e/ou todas as sessões de mensagens instantâneas entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências que ocorrerem entre usuários internos; é possível também arquivar sessões que ocorrerem entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar um novo local de banco de dados para um ou mais Servidores de Arquivamento.  <br/> |
   

