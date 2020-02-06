---
title: Gerenciar o arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumo: saiba como gerenciar o arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818993"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Gerenciar o arquivamento no Skype for Business Server

**Resumo:** Saiba como gerenciar o arquivamento para o Skype for Business Server.
  
Ao implantar arquivamento para a sua organização, você especifica a configuração inicial durante a implantação. Entretanto, pode ocorrer vezes em que você deseja alterar como implementa o suporte a arquivamento para gerenciamento dia a dia ou para atender novos requisitos da sua organização. Por exemplo, você pode precisar definir o suporte a arquivamento de maneira diferente para um site, pool ou usuários específicos na sua organização. Para os usuários hospedados no Skype for Business Server, você faz isso criando e personalizando opções de configuração de arquivamento e políticas de usuário. 
  
Antes de ler este tópico, verifique se você está familiarizado com as informações em [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [implantar o arquivamento para o Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Caso tenha habilitado a integração com o Microsoft Exchange na sua implantação, as políticas do Exchange controlam se o arquivamento está habilitado para usuários que estão hospedados no Exchange e cujas caixas de correio estão em Bloqueio In-loco. Para obter detalhes, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configurar a integração com o armazenamento do Exchange para o Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opções de configuração de arquivamento

As opções de configuração de arquivamento especificam:
  
- Habilitar ou desabilitar arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear uma atividade quando o arquivamento não estiver disponível
    
- Usar integração com o Exchange
    
- Configurar a limpeza e exportação de dados
    
Essas opções podem ser configuradas no nível global, de site ou de pool. Para obter mais informações, consulte [Gerenciar opções de arquivamento no Skype for Business Server](options.md).
  
## <a name="archiving-policies"></a>Políticas de arquivamento

Políticas de arquivamento determine se deseja arquivar o seguinte:
  
- Comunicações internas
    
- Comunicações externas
    
Essas políticas podem ser configuradas no nível global, de site ou de usuário. Para obter mais informações, consulte [gerenciar políticas de arquivamento no Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gerencie o arquivamento usando o Painel de Controle ou o Windows PowerShell

Você pode gerenciar o arquivamento usando o Painel de Controle ou o Windows PowerShell. A tabela a seguir lista os cmdlets disponíveis para ajudar você a gerenciar o arquivamento. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Shell de gerenciamento do Skype for Business Server](../management-shell.md). 


|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta registros que foram armazenados no banco de dados de arquivamento do Skype for Business Server.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as configurações de arquivamento na sua organização.  <br/> |
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento na sua organização para comunicações internas e externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui a usuários ou grupos de usuários políticas de arquivamento de sessões de mensagens instantâneas (IM). Essas políticas permitem arquivar sessões de IM entre usuários internos e/ou arquivar sessões de IM entre usuários internos e externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Exclui manualmente registros do banco de dados de Arquivamento.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações do sistema de mensagens instantâneas (IM), que podem ser usadas para habilitar ou desabilitar a gravação automática de sessões de IM, e também para bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvamento automático de sessões de mensagem instantânea (IM) e bloquear opcionalmente qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove a política de arquivamento de mensagens instantâneas (IM) especificada que determina se o Skype for Business Server salvará automaticamente todas as sessões de mensagens instantâneas que ocorrem entre usuários internos e/ou todas as sessões de mensagens instantâneas entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências entre usuários internos; é possível também arquivar sessões que entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar um novo local do banco de dados para um ou mais Servidores de Arquivamento.  <br/> |
   

