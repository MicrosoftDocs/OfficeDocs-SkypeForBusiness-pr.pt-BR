---
title: Criar uma configuração de arquivamento em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Resumo: saiba como criar uma configuração de arquivamento para Skype for Business Server.'
ms.openlocfilehash: 76fd2785f172cc9dd4b76df97d3c29a78e831e46
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850034"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Criar uma configuração de arquivamento em Skype for Business Server

**Resumo:** Saiba como criar uma configuração de arquivamento para Skype for Business Server.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Configurar opções de arquivamento usando o Painel de Controle

Para configurar opções de arquivamento para um site ou pool específico: 
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna. 
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Na página **Configuração de arquivamento**, clique em **Novo** e siga um destes procedimentos: 
    
   - Para criar uma configuração de arquivamento de site, clique em **Configuração** do Site e, em Selecionar um **site,** selecione o site a ser configurado para arquivamento.
    
   - Para criar uma configuração de arquivamento de pool, clique em **Configuração** do Pool e, em Selecionar um **pool,** selecione o pool a ser configurado para arquivamento.
    
5. Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, faça um dos seguintes:
    
   - Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para sessões de IM e conferências da Web, clique em **Arquivar sessões de IM e conferência da Web**.
    
   - Para desabilitar o arquivamento para essa configuração, clique em **Desabilitar arquivamento**.
    
6. Também em **Nova configuração de arquivamento**, faça o seguinte:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.
    
   - Para usar Microsoft Exchange Server armazenar dados de arquivamento, clique na caixa de seleção Integração Exchange **Microsoft.**
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:
    
     - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
     - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
7. Clique em **Confirmar**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Configurar opções de arquivamento usando Windows PowerShell

Você também pode configurar opções de arquivamento para um site ou pool específico usando o cmdlet **New-CsArchivingConfiguration.**
  
O comando a seguir cria um novo conjunto de definições de configuração de arquivamento para o local Redmond:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. 
  
Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. O exemplo a seguir cria uma coleção de configurações de arquivamento que, por padrão, permitem o arquivamento apenas de sessões de mensagens instantâneas:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, este comando define a nova configuração para arquivar sessões de mensagem instantânea e o bloqueio de mensagem instantânea do serviço de arquivamento não está disponível:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingConfiguration.](/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)