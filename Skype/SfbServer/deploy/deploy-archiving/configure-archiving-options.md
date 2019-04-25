---
title: Configurar opções de arquivamento para Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumo: Leia este tópico para saber como configurar opções de arquivamento iniciais para Skype para Business Server. Inicialmente, você define as configurações de arquivamento quando faz a implementação, mas você pode alterar, adicionar e excluir configurações depois da implementação.'
ms.openlocfilehash: 80501c01c4e05e0578685b42f8fb83b7faed6c59
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236135"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurar opções de arquivamento para Skype para Business Server
 
**Resumo:** Leia este tópico para saber como configurar opções de arquivamento iniciais para Skype para Business Server. Inicialmente, você define as configurações de arquivamento quando faz a implementação, mas você pode alterar, adicionar e excluir configurações depois da implementação.
  
Para configurar inicial de arquivamento configurações, você use Skype para painel de controle do Business Server para especificar o seguinte:
  
- Configuração no nível global criada por padrão quando você implanta o Skype para Business Server
    
- Configurações opcionais em nível de site que especificam como o arquivamento é implementado para um site específico
    
- Configurações opcionais de nível do pool que especificam como o arquivamento é implementado para um pool específico
    
Você terá que configurar opções para definir:
  
- Habilitar ou desabilitar o arquivamento
    
- Arquivar ou não sessões de mensagens instantâneas
    
- Arquivar ou não sessões de webconferência
    
- Bloquear ou não uma atividade quando o arquivamento não estiver disponível
    
- Usar ou não integração com o Exchange
    
- Como configurar a limpeza e exportação de dados
    
> [!NOTE]
> Você deve especificar todas as opções apropriadas antes de habilitar o arquivamento. 
  
Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo as opções que você pode especificar e a hierarquia de arquivamento configurações, consulte [Plan para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre como gerenciar configurações após a implantação usando o painel de controle ou usando o Windows PowerShell, consulte [Gerenciar opções de arquivamento no Skype para Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurar opções de arquivamento em nível global

Quando você adicionar arquivamento à topologia e publica a topologia, Skype para Business Server cria uma configuração global para arquivamento. Por padrão, nenhuma opção de arquivamento está ativada na configuração global. A configuração global controla quais opções são habilitadas para toda a sua implantação, a não ser que você defina configurações de site ou pool que substituam a configuração global.
  
Para configurar opções de arquivamento em nível global:
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.
    
5. Em **Editar configuração de arquivamento - Global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:
    
   - **Desativar arquivamento**
    
   - **Arquivar sessões de IM**
    
   - **Arquivar sessões de IM e conferência da Web**
    
6. Também na página **Editar configuração de arquivamento - Global** , faça o seguinte:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.
    
   - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:
    
   - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
   - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
7. Clique em **Confirmar**.
    
## <a name="configure-site-level-archiving-options"></a>Configurar opções de arquivamento em nível de site

Você pode especificar opções de arquivamento para um site específico. Uma configuração de site substitui a configuração global, mas só se aplica ao site específico definido na configuração de site. 
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Na página **Configuração do Arquivamento**, clique em **Nova** e depois em **Configuração do site**.
    
5. Em **Selecionar um Site**, selecione o site a ser configurado para arquivamento.
    
6. Em **Nova configuração de arquivamento**, na caixa de lista suspensa **Configuração de arquivamento**, execute uma das seguintes ações:
    
   - Para habilitar o arquivamento apenas para sessões de IM, clique em **Arquivar sessões de IM**.
    
   - Para habilitar o arquivamento para sessões de IM e conferências, clique em **Arquivar sessões de IM e webconferência**.
    
   - Para desabilitar o arquivamento da política, clique em **Desabilitar arquivamento**.
    
7. Também em **Nova configuração de arquivamento**, execute uma das seguintes ações:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.
    
   - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:
    
   - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
   - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
8. Clique em **Confirmar**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurar opções de arquivamento em nível de pool

Você pode especificar opções de arquivamento para um pool específico. Uma configuração de pool substitui a configuração global e de site, mas só se aplica ao pool específico definido na configuração de pool.
  
1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.
    
4. Na página **Configuração de arquivamento**, clique em **Nova** e em **Configuração de pool**.
    
5. Em **Selecionar um serviço**, selecione o pool que será configurado para arquivamento.
    
6. Em **Nova configuração de arquivamento**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:
    
   - **Desativar arquivamento**
    
   - **Arquivar sessões de IM**
    
   - **Arquivar sessões de IM e conferência da Web**
    
7. Na página **Nova configuração de arquivamento**, faça o seguinte:
    
   - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou webconferência se o arquivamento falhar**.
    
   - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique em caixa de seleção **integração do Microsoft Exchange** .
    
   - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e execute uma das seguintes ações:
    
   - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
    
   - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.
    
8. Clique em **Confirmar**.
    

