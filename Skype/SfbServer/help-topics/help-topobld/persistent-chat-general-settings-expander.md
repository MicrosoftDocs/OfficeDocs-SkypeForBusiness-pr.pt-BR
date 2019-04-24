---
title: Expansor de Configurações Gerais de Chat Persistente
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Você pode editar as configurações gerais para o servidor de Chat persistente ou o pool de servidor de Chat persistente configurando ou definindo essas propriedades:'
ms.openlocfilehash: 5300a6353bb683bfe2a010cda00c43e0faa839b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219286"
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de Configurações Gerais de Chat Persistente
 
Você pode editar as configurações **gerais** para o servidor de Chat persistente ou o pool de servidor de Chat persistente configurando ou definindo essas propriedades:
  
 **Geral**
  
- **FQDN**: edite essa configuração para definir o nome de domínio totalmente qualificado do seu servidor de Chat persistente ou o pool do servidor de Chat persistente
    
- **Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool. Essa configuração será facilitam para os usuários associar a um determinado servidor de Chat persistente ou o pool de servidor de Chat persistente com base no nome para exibição, em vez de um mais difíceis de entender o nome de domínio totalmente qualificado.
    
- **Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.
    
Você pode editar as configurações de **associações** para o servidor de Chat persistente ou o pool de servidor de Chat persistente configurando ou definindo essas propriedades:
  
 **Associações**
  
- **Repositório do SQL Server**: escolha o repositório do SQL Server e a instância nomeada opcional na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento para o SQL Server store principal.
    
    Se você escolher habilitar o espelhamento do repositório do SQL Server, selecione o repositório e a instância na lista **espelhando o SQL Server store**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server principal.
    
    Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **usar backup repositórios do SQL Server para habilitar a recuperação de desastre** se quiser habilitar o uso de recuperação de desastre do SQL Server
    
    Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Repositório do SQL Server de backup**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento do SQL Server backup espelhamento do repositório.
    
    Se você escolher habilitar o espelhamento do repositório do SQL Server backup, selecione o repositório e a instância na lista **Backup do SQL Server store espelho**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server backup.
    
    Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade
    
    Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento para o SQL Server store de conformidade.
    
    Se você escolher habilitar o espelhamento de repositório do SQL Server de conformidade, selecione o repositório e a instância na lista **conformidade SQL Server store espelho**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server de conformidade.
    
    Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Repositório do SQL Server de conformidade de backup**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **espelhamento do repositório de habilitar o SQL Server** se desejar habilitar o espelhamento para o SQL Server store de conformidade.
    
    Se você escolher habilitar o espelhamento de repositório do SQL Server de conformidade, selecione o repositório e a instância na lista **espelho de store de conformidade de Backup do SQL Server**.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional.
    
- Marque a caixa de seleção **usar SQL Server espelhamento testemunha para habilitar o failover automático** se quiser failover automático do repositório do SQL Server de backup de conformidade.
    
    Se você escolher habilitar a testemunha para habilitar failover automático de espelhamento do SQL Server store, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo repositório do SQL Server e instância opcional para o repositório de testemunha.
    
- **Repositório de arquivo** Selecione um local do repositório de arquivo na lista ou clique em **novo** para criar um novo repositório de arquivo.
    
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  
## <a name="see-also"></a>Confira também

[Planejar Servidor de Chat Persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de Chat persistente à sua Skype para a topologia de negócios Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurar a alta disponibilidade e a recuperação de desastres para o Servidor de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
