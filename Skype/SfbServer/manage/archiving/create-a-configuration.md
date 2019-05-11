---
title: Criar uma configuração de arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumo: Saiba como criar uma configuração de arquivamento para Skype for Business Server.'
ms.openlocfilehash: 3f20b763644f74b0b2265706d4190d27b28ddffd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885021"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Criar uma configuração de arquivamento no Skype para Business Server

**Resumo:** Saiba como criar uma configuração de arquivamento para Skype for Business Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar opções de arquivamento usando o Painel de Controle

Para configurar opções e arquivamento para um site ou pool específico: 
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Na página **Configuração de arquivamento**, clique em **Novo** e siga um destes procedimentos: 
    
   - Para criar uma configuração de arquivamento local, clique em **Configuração local**e, em **Selecionar um local**, selecione o local a ser configurado para arquivamento.
    
   - Para criar uma configuração de arquivamento do pool, clique em **Configuração do pool**e, em **Selecionar um pool**, selecione o pool a ser configurado para arquivamento.
    
5. Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, execute uma das seguintes ações:
    
   - Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para sessões de IM e webconferência, clique em **Arquivar sessões de IM e webconferência**.
    
   - Para desabilitar o arquivamento desta política, clique em **Desabilitar arquivamento**.
    
6. Também em **Nova configuração de arquivamento**, execute uma das seguintes ações:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.
    
   - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:
    
     - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
     - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
7. Clique em **Confirmar**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar opções de arquivamento usando o Windows PowerShell

Você também pode configurar opções de arquivamento para um site ou pool específico usando o cmdlet **New-CsArchivingConfiguration**.
  
O comando a seguir cria um novo conjunto de definições de configuração de arquivamento para o local Redmond:
  
```
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. 
  
Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e valor de parâmetro adequados. O exemplo a seguir cria uma coleção de configurações de arquivamento que, por padrão, permitem arquivar somente sessões de mensagens instantâneas:
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, este comando define a nova configuração para arquivar sessões de mensagem instantânea e o bloqueio de mensagem instantânea do serviço de arquivamento não está disponível:
  
```
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .
