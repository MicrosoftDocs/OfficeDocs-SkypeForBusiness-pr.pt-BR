---
title: Configurar opções de arquivamento para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumo: leia este tópico para saber como configurar as opções iniciais de arquivamento para Skype for Business Server. Você inicialmente configurações de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.'
ms.openlocfilehash: b27a6bdd85b935b0751abf3da2bac94488234cdb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749510"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurar opções de arquivamento para Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar as opções iniciais de arquivamento para Skype for Business Server. Você inicialmente configurações de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.
  
Para configurar as configurações iniciais de arquivamento, use Skype for Business Server Painel de Controle para especificar o seguinte:
  
- Configuração de nível global criada por padrão quando você implanta Skype for Business Server
    
- Configurações opcionais no nível do site que especificam como o arquivamento é implementado para um site específico
    
- Configurações opcionais no nível do pool que especificam como o arquivamento é implementado para um pool específico
    
Você precisará configurar opções para o seguinte:
  
- Se deve habilitar ou desabilitar o arquivamento
    
- Se as sessões de IM de arquivo morto
    
- Se arquivar sessões de webconferência
    
- Se a atividade deve ser bloqueado quando o arquivamento não estiver disponível
    
- Se deve usar Exchange integração
    
- Como configurar a coleta e a exportação de dados
    
> [!NOTE]
> Você deve especificar todas as opções apropriadas antes de habilcar o arquivamento. 
  
Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia de configurações de arquivamento, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre como gerenciar configurações após a implantação usando o Painel de Controle ou usando o Windows PowerShell, consulte Gerenciar opções de arquivamento [em Skype for Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurar opções de arquivamento de nível global

Quando você adiciona arquivamento à sua topologia e publica a topologia, Skype for Business Server cria uma configuração global para arquivamento. Por padrão, nenhuma opção de arquivamento está habilitada na configuração global. Os controles de configuração global que habilitam configurações para a implantação inteira, a não ser que você defina configurações de site ou pool que substituem a configuração global.
  
Para configurar opções de arquivamento no nível global:
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.
    
5. Em **Editar configuração de arquivamento - global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:
    
   - **Desativar arquivamento**
    
   - **Arquivar sessões de IM**
    
   - **Arquivar sessões de IM e conferência da Web**
    
6. Também na **página Editar Configuração de Arquivamento - Global,** faça o seguinte:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.
    
   - Para usar Microsoft Exchange Server armazenar dados de arquivamento, clique na caixa de seleção Integração Exchange **Microsoft.**
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:
    
   - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
   - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
7. Clique em **Confirmar**.
    
## <a name="configure-site-level-archiving-options"></a>Configurar opções de arquivamento de nível de site

Você pode especificar opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas só se aplica ao site específico definido na configuração de site. 
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Na página **Configuração do Arquivamento**, clique em **Novo** e depois em **Configuração do site**.
    
5. Em **Selecionar um Site**, selecione o site a ser configurado para arquivamento.
    
6. Em **Nova Configuração de Arquivamento**, na caixa da lista suspensa **Configuração do Arquivamento**, execute um dos seguintes procedimentos:
    
   - Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e webconferências**.
    
   - Para desabilitar o arquivamento para a política, clique em **Desabilitar arquivamento**.
    
7. Também em **Nova configuração de arquivamento**, faça o seguinte:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.
    
   - Para usar Microsoft Exchange Server armazenar dados de arquivamento, clique na caixa de seleção Integração Exchange **Microsoft.**
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:
    
   - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
   - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
8. Clique em **Confirmar**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurar opções de arquivamento de nível de pool

Você pode especificar opções de arquivamento para um pool específico. Uma configuração de pool substitui a configuração global e de site, mas somente para o pool especificado na configuração de pool.
  
1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.
    
4. Na página **Configuração de arquivamento**, clique em **Nova** e em **Configuração de pool**.
    
5. Em **Selecionar um serviço**, selecione o pool que será configurado para arquivamento.
    
6. Em **Nova configuração de arquivamento**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:
    
   - **Desativar arquivamento**
    
   - **Arquivar sessões de IM**
    
   - **Arquivar sessões de IM e conferência da Web**
    
7. Na página **Nova configuração de arquivamento**, faça o seguinte:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.
    
   - Para usar Microsoft Exchange Server armazenar dados de arquivamento, clique na caixa de seleção Integração Exchange **Microsoft.**
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:
    
   - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
   - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
8. Clique em **Confirmar**.
    

