---
title: Gerenciar arquivamento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Resumo: Saiba como gerenciar o arquivamento para Skype para Business Server 2015.'
ms.openlocfilehash: fb8359d47b1933e2575685bc532d69e6b9bb6c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-in-skype-for-business-server-2015"></a>Gerenciar arquivamento no Skype for Business Server 2015

**Resumo:** Saiba como gerenciar o arquivamento de Skype para Business Server 2015.
  
Ao implantar arquivamento para a sua organização, você especifica a configuração inicial durante a implantação. Entretanto, pode ocorrer vezes em que você deseja alterar como implementa o suporte a arquivamento para gerenciamento dia a dia ou para atender novos requisitos da sua organização. Por exemplo, você pode precisar definir o suporte a arquivamento de maneira diferente para um site, pool ou usuários específicos na sua organização. Para usuários hospedados no Skype para Business Server, você pode fazer isso criando e personalizando as opções de configuração de arquivamento e políticas de usuário. 
  
Antes de ler este tópico, certifique-se de que estar familiarizado com as informações em [Planejar para arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Deploy arquivamento para Skype para Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Caso tenha habilitado a integração com o Microsoft Exchange na sua implantação, as políticas do Exchange controlam se o arquivamento está habilitado para usuários que estão hospedados no Exchange e cujas caixas de correio estão em Bloqueio In-loco. Para obter detalhes, consulte [Planejar o arquivamento no Skype para Business Server 2015](../../plan-your-deployment/archiving/archiving.md) e [Configure integração com Exchange storage para Skype para Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Opções de configuração de arquivamento

As opções de configuração de arquivamento especificam:
  
- Habilitar ou desabilitar arquivamento
    
- Arquivar sessões de IM
    
- Arquivar sessões de webconferência
    
- Bloquear uma atividade quando o arquivamento não estiver disponível
    
- Usar integração com o Exchange
    
- Configurar a limpeza e exportação de dados
    
Essas opções podem ser configuradas no nível global, de site ou de pool. Para obter mais informações, consulte [Gerenciar opções de arquivamento no Skype para Business Server 2015](options.md).
  
## <a name="archiving-policies"></a>Políticas de arquivamento

Políticas de arquivamento determinam se deseja arquivar o seguinte:
  
- Comunicações internas
    
- Comunicações externas
    
Essas políticas podem ser configuradas no nível global, de site ou de usuário. Para obter mais informações, consulte [Gerenciar políticas de arquivamento no Skype para Business Server 2015](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Gerencie o arquivamento usando o Painel de Controle ou o Windows PowerShell

Você pode gerenciar o arquivamento usando o Painel de Controle ou o Windows PowerShell. A tabela a seguir lista os cmdlets disponíveis para ajudar você a gerenciar o arquivamento. Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md). 


|**Cmdlet**|**Descrição**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exporta os registros que foram armazenados no Skype para banco de dados de arquivamento do servidor de negócios.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Retorna informações sobre as configurações de arquivamento na sua organização.  <br/> |
|Get-CsArchivingPolicy  <br/> |Retorna informações sobre as políticas de arquivamento na sua organização para comunicações internas e externas.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Atribui a usuários ou grupos de usuários políticas de arquivamento de sessões de mensagens instantâneas (IM). Essas políticas permitem arquivar sessões de IM entre usuários internos e/ou arquivar sessões de IM entre usuários internos e externos.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Exclui manualmente registros do banco de dados de Arquivamento.  <br/> |
|New-CsArchivingConfiguration  <br/> |Cria um novo conjunto de configurações do sistema de mensagens instantâneas (IM), que podem ser usadas para habilitar ou desabilitar a gravação automática de sessões de IM, e também para bloquear qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|New-CsArchivingPolicy  <br/> |Cria novas políticas de arquivamento de sessões de IM. Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvamento automático de sessões de mensagem instantânea (IM) e bloquear opcionalmente qualquer mensagem instantânea que não possa ser arquivada.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Remove o especificado mensagens instantâneas (IM) que determina se o Skype para Business Server salvará automaticamente todas as sessões IM ocorridas entre usuários internos e/ou todas as sessões de mensagens Instantâneas entre usuários internos e parceiros federados política de arquivamento.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).  <br/> |
|Set-CsArchivingPolicy  <br/> |Modifica uma política existente de arquivamento de mensagens instantâneas (IM). As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências entre usuários internos; é possível também arquivar sessões que entre usuários internos e parceiros federados.  <br/> |
|Set-CsArchivingServer  <br/> |Permite especificar um novo local do banco de dados para um ou mais Servidores de Arquivamento.  <br/> |
   

